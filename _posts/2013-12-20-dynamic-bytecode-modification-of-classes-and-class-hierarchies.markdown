---

title: Dynamic bytecode modification of classes and class hierarchies
abstract: Various systems and methods for dynamic bytecode modification of classes and class hierarchies are described herein. In various embodiments, a Java® agent is received at a launch of a Java® Virtual Machine (JVM®), the agent implementing a premain method, the premain method accepting a reference to an instrumentation instance. The instrumentation reference is then stored, a deployment container is initialized, and, within the deployment container, an instance of an application is created. The instrumentation reference is then provided to the application instance. A class transformer is then retrieved from a persistence provider, and the class transformer is wrapped by an O.R. Persistence Container Class Transformer, which is then registered with the instrumentation instance. A class to be transformed is passed to the class transformer, which dynamically modifies the bytecode of the class before the class is loaded by the JVM®.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09378034&OS=09378034&RS=09378034
owner: SAP SE
number: 09378034
owner_city: Walldorf
owner_country: DE
publication_date: 20131220
---
This patent application claims the benefit of priority under 35 U.S.C. 119 e to U.S. Provisional Patent Application Ser. No. 61 824 203 entitled DYNAMIC BYTECODE MODIFICATION OF CLASSES AND CLASS HIERARCHIES filed on May 16 2013 which is hereby incorporated by reference herein in its entirety.

Software engineers have used object oriented programming to model real world entities and concepts for decades. Object oriented languages such as Java allow programmers to model entities and concepts by using object oriented constructs such as encapsulation inheritance and polymorphism. Although object oriented code may be designed to model real world entities and concepts accurately object oriented code is usually integrated with infrastructure code that is designed to interact with particular software packages frameworks and hardware.

The difficulty of modifying an object oriented codebase increases with the size of the codebase. The term codebase or code base is used in software development to mean the entire collection of source code used to build a particular application or component. In some situations the codebase s software engineers may want to integrate the codebase with other software such as another codebase another software framework or another software product. However the other software may require the codebase to have a particular structure or certain features that the codebase does not have. For example some software may require the classes of the codebase to inherit or extend from other classes to implement certain interfaces to call certain methods etc. Although modifying the codebase to accommodate the requirements may be possible the modifications might be costly time consuming and may introduce other problems or errors.

In the following detailed description reference is made to the accompanying drawings that form a part hereof and in which is shown by way of illustration specific embodiments in which the inventive subject matter may be practiced. These embodiments are described in sufficient detail to enable those skilled in the art to practice them and it is to be understood that other embodiments may be utilized and that structural logical and electrical changes may be made without departing from the scope of the inventive subject matter. Such embodiments of the inventive subject matter may be referred to individually and or collectively herein by the term invention merely for convenience and without intending to limit voluntarily the scope of this application to any single invention or inventive concept if more than one is in fact disclosed.

The following description is therefore not to be taken in a limited sense and the scope of the inventive subject matter is defined by the appended claims.

The functions or algorithms described herein are implemented in hardware software or a combination of software and hardware in one embodiment. The software comprises computer executable instructions stored on computer readable media such as memory or other type of storage devices. Further described functions may correspond to modules which may be software hardware firmware or any combination thereof. Multiple functions are performed in one or more modules as desired and the embodiments described are merely examples. The software is executed on a digital signal processor ASIC microprocessor or other type of processor operating on a system such as a personal computer server a router or other device capable of processing data including network interconnection devices.

Some embodiments implement the functions in two or more specific interconnected hardware modules or devices with related control and data signals communicated between and through the modules or as portions of an application specific integrated circuit. Thus the exemplary process flow is applicable to software firmware and hardware implementations.

Bytecode modification is a common technique for weaving logic into an existing object oriented class. Dynamic bytecode modification is a valuable technique for weaving logic into an existing object oriented class in a transparent manner. Using dynamic bytecode modification enhances virtual execution environments for a plethora of purposes such as monitoring profiling or performance analysis. For example a provider implementing the Java Persistence Application Programming Interface a.k.a. JPA may use dynamic bytecode modification to enhance JPA entities for lazy loading change tracking fetching groups and internal optimizations. Although the JPA specification requires a mechanism be provided to JPA persistence providers to include specific logic into existing Java entity classes a.k.a. plain old Java objects or POJO the specification does not specify the mechanism nor does the specification explain how to support major modifications of classes or class hierarchies.

In the Java platform one mechanism for bytecode modification of a class is to use class redefinition which allows modification of a class that has already been loaded into the Java Virtual Machine a.k.a. JVM . However many JVM s restrict the types of modifications that may be performed when redefining a class. For example some JVM s do not allow redefinitions to add remove or rename the fields methods or ancestors of an already loaded class. One mechanism to overcome these limitations is to perform dynamic bytecode modification before the classes to be modified are ever loaded.

Turning now to the figures is a flowchart illustrating a method for dynamic bytecode modification in accordance with various embodiments. At a Java agent is received at a launch of a JVM . A Java agent may be specified to the command line launching of a JVM by adding the option

 javaagent jarpath options to the command line where jarpath is the path to the JAR file containing the Java agent class and options are the agent options. In various embodiments the manifest of the agent JAR file contains the attribute Premain Class . In various embodiments the value of the Premain Class attribute is the class name of the Java agent to be loaded. In various embodiments the jarpath switch may be used multiple times on the same command line in such embodiments multiple agent instances are created if multiple jarpath switches are used.

In various embodiments the agent class specified in the Premain Class attribute implements a method with the signature public static void premain java.lang.String agentArgs java.lang.instrument.Instrumentation inst . After the JVM has initialized the premain method of the agent will be called. In various embodiments if more than one agent was specified at the command line the premain method of each agent will be called in the order the agents were specified on the command line. In various embodiments when the premain method of an agent is called by the JVM an Instrumentation instance whose class implements the java.lang.instrument.Instrumentation interface is passed to the premain method through the inst parameter. In various embodiments the JVM passes each agent the agent s options specified on the command line via the agentArgs parameter.

At a reference to the Instrumentation instance is stored. In various embodiments the Instrumentation reference is stored in a static field of the Java agent class. In various embodiments the Instrumentation reference is stored in an instance field of the Java agent class. In various embodiments the Instrumentation reference is stored by another object which makes the Instrumentation reference available to the Java agent.

At a deployment container is initialized. In various embodiments the deployment container may be an O.R. Object Relational Persistence Deployment Container an Enterprise JavaBeans EJB Deployment Container or a Web Deployment Container. In various embodiments a JPA container is implemented within the O.R. Persistence Deployment Container. In various embodiments the O.R. Persistence Deployment Container integrates the JPA container and the deploy service of the application server. Third party JPA containers may be provided to the application server as a library. In various embodiments the deployment container implements the javax.persistence.spi.PersistenceUnitInfo interface of the JPA specification. In various embodiments that use a JPA container configuration files and metadata within JPA entity classes may be used to create the metadata model for the JPA container. In various embodiments the O.R. Persistence Deployment Container provides integration between third party JPA containers and the deploy service of the application server.

At an instance of an application to be executed is created within the deployment container. In various embodiments the application component may be validated and its metadata model created before the application instance is created.

At the reference to the Instrumentation instance is provided to the application instance created at . The reference may be provided to the application instance through direct method invocation through delegation through a callback method or by other means.

At a class transformer is retrieved from a persistence provider such as the JPA Persistence Provider. In various embodiments the persistence provider implements the PersistenceUnitInfo interface. The persistence provider may call the PersistenceProvider.createContainerEntityManagerFactory method to create an EntityManagerFactory object. This call may be performed before any JPA entity classes i.e. the classes to be transformed are loaded.

During the PersistenceProvider.createContainerEntityManagerFactory call all the ClassTransformers are collected in the PersistenceUnitInfo implementation and each of the collected transformers is wrapped in a JPAClassFileTransformer instance which implements the java.lang.instrument.ClassFileTransformer interface. In various embodiments each JPAClassFileTransformer is registered with the Instrumentation using the Instrumentation.addTransformer method. In various embodiments the registration of each JPAClassFileTransformer occurs in method addTransformers AuditingExtendedPersistenceUnitInfo persistenceUnitInfo of the Application class where AuditingExtendedPersistenceUnitInfo is the container implementation of the interface PersistenceUnitInfo.

At a class transformer is registered with the Instrumentation instance. In various embodiments the persistence provider may register a class transformer by calling the method PersistenceUnitInfo.addTransformer javax.persistence.spi.ClassTransformer transformer and passing the class transformer as the argument to the method. In various embodiments after registration the class transformer will be called for every new class definition or class redefinition that gets loaded by the loader returned by the PersistenceUnitInfo.getClassLoader .

Each JPAClassTransformer may keep a reference to the ClassLoader returned by PersistenceUnitInfo.getClassLoader . Each JPAClassTransformer may also keep a reference to a ClassTransformer which implements interface javax.persistence.spi.ClassTransformer provided by the third party persistence provider.

At a reference to a class that is currently being loaded and is to be transformed is passed to the JPAClassTransformer. In various embodiments the class reference may be passed by the Instrumentation instance to the JPAClassTransformer by the Instrumentation instance calling the transform method of the JPAClassTransformer. In various embodiments the JPAClassTransformer will then delegate to the wrapped ClassTransformer the class reference by calling the transform method of the wrapped ClassTransformer.

In the Java platform an instance of a ClassLoader is created for each application. The ClassLoader is responsible for loading the classes of its associated application. The application may have references to other applications i.e. it is possible that the application s ClassLoader could have references to other ClassLoaders . When one class is present in several ClassLoaders a referenced ClassLoader will have higher priority than the referencing ClassLoader. However in some cases the referencing ClassLoader may need to have a higher priority than the referenced ClassLoader. Such a ClassLoader is called a heavy ClassLoader.

At the bytecode of the class is dynamically modified by the class transformer before the JVM finishes loading the class. The transformation occurs only if the class is loaded by the regular ClassLoader of the application where the Persistence Unit has been defined. Any classes loaded from the application heavy ClassLoader will not be transformed.

To solve this problem in various embodiments one application may have two ClassLoaders. In various embodiments the first ClassLoader may be the normal one i.e. the heavy ClassLoader . In various embodiments the heavy ClassLoader contains only the application components that are located in a specific directory of the application JAR archive. In various embodiments a check may be performed to determine if a JPA entity class will be loaded by the heavy ClassLoader of the same application if a JPA entity class is to be loaded by the heavy ClassLoader that JPA entity class is not transformed.

In various embodiments the JVM then loads the modified bytecode of the class and performs the class definition for the modified class. Because the bytecode modification is performed before the JVM would have loaded the unmodified version of the class class redefinition is avoided and the JVM s restrictions on class redefinitions do not apply.

In various embodiments all the transformers that are registered in the Instrumentation by the Instrumentation.addTransformer during the start phase of an application server are unregistered during the stop phase of the application by the Instrumentation.removeTransformer method.

At step the client sends a start message to the application server startup framework to begin the process of starting the Java server .

At step the application server startup framework launches the JVM of the Java server with a Java agent .

At step the JVM of the Java server passes a java.lang.instrument.Instrumentation instance to the premain method of the Java agent .

At step the Java server invokes the start method of the O.R. Persistence Service . In various embodiments the Java server passes a reference to the java.lang.instrument.Instrumentation instance to the O.R. Persistence Service and the O.R. Persistence Service stores the reference.

At step the O.R. Persistence Service causes a new O.R. Persistence Container to be created and causes the O.R. Persistence Container to be registered in the deploy service.

At step the O.R. Persistence Container requests a reference to the java.lang.instrument.Instrumentation instance from the Java agent . At step . the java.lang.instrument.Instrumentation instance is received and stored by the O.R. Persistence Container .

According to the JPA 1.0 specification the PersistenceUnitInfo interface is implemented by the container and is used by the persistence provider during creation of the EntityManagerFactory i.e. in the PersistenceProvider.createContainerEntityManagerFactory call . Using the PersistenceUnitInfo.addTransformer javax.persistence.spi.ClassTransformer transformer method the persistence provider adds a transformer that will be called for every new class definition that gets loaded by the loader returned by the PersistenceUnitInfo.getClassLoader as well as classes loaded by the application heavy ClassLoader. During the PersistenceProvider.createContainerEntityManagerFactory call all the ClassTransformers are collected in the PersistenceUnitInfo implementation.

At step after the PersistenceProvider.createContainerEntityManagerFactory call each of the collected transformers is wrapped in a new JPA Class Transformer which implements the java.lang.instrument.ClassFileTransformer interface.

At step the O.R. Persistence Container receives a reference to each JPA Class Transformer . At step . each JPA Class Transformer is registered in the java.lang.instrument.Instrumentation instance by the Instrumentation.addTransformer method.

At step . the O.R. Persistence Container returns from the call made by the O.R. Persistence Service at step .

At step .. control is returned from the start method of the O.R. Persistence Service which was invoked by the Java server at step .

At step . the Java server may optionally perform additional initializations before returning control to the application server startup framework .

At step the deploy service calls the deploy method on the O.R. Persistence Container . At step . the deploy service calls the start method on the O.R. Persistence Container .

At step the O.R. Persistence Container calls the create method of the EMF Instance Creator . If instrumentation is disabled which would occur if either dynamic byte code modification was not enabled or if the JPA provider is the default provider the EMF Instance Creator does not create an Entity Manager Factory until a servlet or EJB request occurs as further explained in . Thus step requesting the Entity Manager Factory from the EMF Instance Creator step the EMF Instance Creator creating a new instance of an Entity Manager Factory and step . the Entity Manager Factory loading and transforming classes using dynamic byte code modification will be skipped.

At step the Java Naming and Directory Interface JNDI process causes the getObjectInstance method of the O.R. Persistence Object Factory to be called.

At step the O.R. Persistence Object Factory causes the getEntityManagerFactory method of the EMF Instance Creator to be called.

At step the createContainerEntityManagerFactory auditingInfo intProps method is called on the Persistence Provider.

At step the Persistence Provider adds class transformers during the creation of the Entity Manager Factory which occurs at step by causing the PersistenceUnitInfo.addTransformer javax.persistence.spi.ClassTransformer transformer method to be called. All of the added class transformers are collected in the Auditing Persistence Unit Info and are registered in the Instrumentation instance by the Instrumentation.addTransformer method.

At step the Entity Manager Factory loads the managed entity classes. The O.R. Persistence Container intercepts the class loading and uses the EMF transformers to transform the byte code. For additional details see .

At step the createContainerEntityManagerFactory auditingInfo intProps method returns control to the EMF Instance Creator .

At steps and . the deploy service calls the deploy method and start method on the O.R. Persistence Container .

At step . the O.R. Persistence Container causes a new instance of the Auditing Persistence Unit Info class to be created.

At step . the O.R. Persistence Container requests the Entity Manager Factory from the EMF Instance Creator .

At step the EMF Instance Creator creates an Entity Manager Factory by calling the createContainerEntityManagerFactory auditingInfo intProps method on the Persistence Provider.

At step the Persistence Provider adds class transformers during the creation of the Entity Manager Factory which occurs at step by causing the PersistenceUnitInfo.addTransformer javax.persistence.spi.ClassTransformer transformer method to be called. All of the added class transformers are collected in the Auditing Persistence Unit Info . Each of the collected transformers in the Auditing Persistence Unit Info is wrapped in a JPAClassFileTransformer which implements the java.lang.instrument.ClassFileTransformer interface and is registered in the Instrumentation instance by the Instrumentation.addTransformer method.

At step the Entity Manager Factory loads the managed entity classes. The O.R. Persistence Container intercepts the class loading and uses the EMF transformers to transform the byte code. For additional details see .

At step the createContainerEntityManagerFactory auditingInfo intProps method returns control to the EMF Instance Creator .

At step the O.R. Persistence Container calls the execute method and passes control to the Application Creator .

At step the Application calls the getEMF persistenceProvider method and passes control to the EMF Instance Creator .

At step the EMF Instance Creator calls the createContainerEntityManagerFactory persistenceUnitInfo method and passes control to the Persistence Provider .

At step the Application calls the JPAClassTransformer puInfo.getTransformers .iterate method and passes control to the JPA Class Transformer .

At step the Application calls the addTransformer jpaTransformer method and passes control to the java.lang.instrument.Instrumentation .

At step . the deploy service loads the temporary class loader. When using a temporary class loader no classes will be defined and resolved with the real class loader of the application. This temporary class loader is used to inspect and validate the application classes and metadata.

At step the deploy service starts the O.R. Persistence Container by passing the Persistence Unit to the O.R. Persistence Container . No application classes will be loaded at this point because the O.R. Persistence Container has a higher priority than the containers using the Persistence Unit and because the O.R. Persistence Container reads bytecode directly.

At step the O.R. Persistence Container calls the newInstance method to create a new JPA Class Transformer .

At step the O.R. Persistence Container calls the addTransformer JPAClassTransformer method on the java.lang.instrument.Instrumentation instance passing a reference to the JPA Class Transformer .

At step the O.R. Persistence Container calls the newInstance method to create a new EMF Instance Creator .

At step the O.R. Persistence Container requests a reference to an EntityManagerFactory from the EMF Instance Creator by calling the getEMF method.

At step the EntityManagerFactory adds class transformers by calling the method addTransformer EMFTransformer on the Auditing Persistence Unit Info .

At step the EntityManagerFactory requests a Class Loader from the Auditing Persistence Unit Info by calling the getClassLoader method of the Auditing Persistence Unit Info .

At step after receiving a reference to Class Loader the EntityManagerFactory loads the managed entity classes.

At step the all of the JPA Class Transformers are already registered at step in the java.lang.instrument.Instrumentation . Each JPAClassTransformer holds references to the persistence unit s regular Class Loader heavy ClassLoader and the wrapped javax.persistence.spi.ClassTransformer. The Class Loader then calls the transform byte method of each JPAClassTransformer .

At step the bytecode of the managed entity class is transformed via delegation to the original ClassTransformer.transform method only if the managed entity class is loaded by the application s regular ClassLoader or heavy ClassLoader.

At step the transformed bytecode of the managed entity class is passed back to the JPA Class Transformer .

At step the JPA Class Transformer passes the transformed bytecode of the managed entity class to the Class Loader .

At step the Class Loader passes the transformed and loaded managed entity class to the EntityManagerFactory .

At step the O.R. Persistence Container returns from the starting of the O.R. Persistence Container at step .

Examples as described herein can include or can operate on logic or a number of components modules or mechanisms. Modules are tangible entities capable of performing specified operations and can be configured or arranged in a certain manner. In an example circuits can be arranged e.g. internally or with respect to external entities such as other circuits in a specified manner as a module. In an example the whole or part of one or more computer systems e.g. a standalone client or server computer system or one or more hardware processors can be configured by firmware or software e.g. instructions an application portion or an application as a module that operates to perform specified operations. In an example the software can reside 1 on a non transitory machine readable medium or 2 in a transmission signal. In an example the software when executed by the underlying hardware of the module causes the hardware to perform the specified operations.

Accordingly the term module is understood to encompass a tangible entity be that an entity that is physically constructed specifically configured e.g. hardwired or temporarily e.g. transitorily configured e.g. programmed to operate in a specified manner or to perform part or all of any operation described herein. Considering examples in which modules are temporarily configured each of the modules need not be instantiated at any one moment in time. For example where the modules comprise a general purpose hardware processor configured using software the general purpose hardware processor can be configured as respective different modules at different times. Software can accordingly configure a hardware processor for example to constitute a particular module at one instance of time and to constitute a different module at a different instance of time.

Machine e.g. computer system can include a hardware processor e.g. a central processing unit CPU a graphics processing unit GPU a hardware processor core or any combination thereof a main memory and a static memory some or all of which can communicate with each other via a bus . The machine can further include a display unit an alphanumeric input device e.g. a keyboard and a user interface UI navigation device e.g. a mouse . In an example the display unit input device and UI navigation device can be a touch screen display. The machine can additionally include a storage device e.g. drive unit a signal generation device e.g. a speaker a network interface device and one or more sensors such as a global positioning system GPS sensor compass accelerometer or other sensor. The machine can include an output controller such as a serial e.g. universal serial bus USB parallel or other wired or wireless e.g. infrared IR connection to communicate or control one or more peripheral devices e.g. a printer card reader etc. .

The storage device can include a machine readable medium on which is stored one or more sets of data structures or instructions e.g. software embodying or utilized by any one or more of the techniques or functions described herein. The instructions can also reside completely or at least partially within the main memory within static memory or within the hardware processor during execution thereof by the machine . In an example one or any combination of the hardware processor the main memory the static memory or the storage device can constitute machine readable media.

While the machine readable medium is illustrated as a single medium the term machine readable medium can include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that configured to store the one or more instructions .

The term machine readable medium can include any tangible medium that is capable of storing encoding or carrying instructions for execution by the machine and that cause the machine to perform any one or more of the techniques of the present disclosure or that is capable of storing encoding or carrying data structures used by or associated with such instructions. Non limiting machine readable medium examples can include solid state memories and optical and magnetic media. Specific examples of machine readable media can include non volatile memory such as semiconductor memory devices e.g. Electrically Programmable Read Only Memory EPROM Electrically Erasable Programmable Read Only Memory EEPROM and flash memory devices magnetic disks such as internal hard disks and removable disks magneto optical disks and CD ROM and DVD ROM disks.

The instructions can further be transmitted or received over a communications network using a transmission medium via the network interface device utilizing any one of a number of transfer protocols e.g. frame relay internet protocol IP transmission control protocol TCP user datagram protocol UDP hypertext transfer protocol HTTP etc. . Example communication networks can include a local area network LAN a wide area network WAN a packet data network e.g. the Internet mobile telephone networks e.g. cellular networks Plain Old Telephone POTS networks and wireless data networks e.g. Institute of Electrical and Electronics Engineers IEEE 802.11 family of standards known as Wi Fi IEEE 802.16 family of standards known as WiMax peer to peer P2P networks among others. In an example the network interface device can include one or more physical jacks e.g. Ethernet coaxial or phone jacks or one or more antennas to connect to the communications network . In an example the network interface device can include a plurality of antennas to communicate wirelessly using at least one of single input multiple output SIMO multiple input multiple output MIMO or multiple input single output MISO techniques. The term transmission medium shall be taken to include any intangible medium that is capable of storing encoding or carrying instructions for execution by the machine and includes digital or analog communications signals or other intangible medium to facilitate communication of such software.

Although example machine is illustrated as having several separate functional elements one or more of the functional elements may be combined and may be implemented by combinations of software configured elements such as processing elements including digital signal processors DSPs and or other hardware elements. For example some elements may comprise one or more microprocessors DSPs application specific integrated circuits ASICs radio frequency integrated circuits RFICs and combinations of various hardware and logic circuitry for performing at least the functions described herein. In some embodiments the functional elements of system may refer to one or more processes operating on one or more processing elements.

Embodiments may be implemented in one or a combination of hardware firmware and software. Embodiments may also be implemented as instructions stored on a computer readable storage device which may be read and executed by at least one processor to perform the operations described herein. A computer readable storage device may include any non transitory mechanism for storing information in a form readable by a machine e.g. a computer . For example a computer readable storage device may include read only memory ROM random access memory RAM magnetic disk storage media optical storage media flash memory devices and other storage devices and media. In some embodiments system may include one or more processors and may be configured with instructions stored on a computer readable storage device.

It will be readily understood to those skilled in the art that various other changes in the details material and arrangements of the parts and method stages which have been described and illustrated in order to explain the nature of the inventive subject matter may be made without departing from the principles and scope of the inventive subject matter as expressed in the subjoined claims.

