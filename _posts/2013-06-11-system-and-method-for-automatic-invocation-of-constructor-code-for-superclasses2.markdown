---

title: System and method for automatic invocation of constructor code for superclasses
abstract: A system and method for automatic invocation of object initializers, or constructors, for superclasses featuring the ability to modify the contents of classes of existing applications at runtime, which includes adding new superclasses to the class inheritance hierarchy of the existing classes. The system redefines the content of classes of the existing classes and the new superclasses during the loading of the classes to additionally include code statements that invoke constructors of the redefined classes and the new superclasses. The invocation of the constructors at runtime performs the initialization of the objects.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09639329&OS=09639329&RS=09639329
owner: Syddansk Universitet
number: 09639329
owner_city: Odense
owner_country: DK
publication_date: 20130611
---
This application claims the benefit under 35 U.S.C. 119 e of U.S. Provisional Application No. 61 660 002 filed on Jun. 15 2012 which is incorporated herein by reference in its entirety.

A platform is a combination of hardware architecture and or software platform that enables software to run on user devices such as desktop computers mobile phones and tablets. Software platforms are typically a combination of software libraries and other executables that present well defined Application Programming Interfaces API . Software developers are increasingly utilizing modern software platforms to enable the creation of platform independent applications. Modern software platforms typically include a programming language the compiled output of which executes within the context of machine dependent programs known as virtual machines VM .

A VM is a software program or library that permits an isolated processing environment to exist on a computer system. VMs hide or abstract the details of the underlying computer system from the software that executes within each VM. To create platform independent applications software developers use platform tools to compile the programming language source code into the software executable that runs on the VMs also known as bytecode.

Bytecode is typically a set of binary files that include platform neutral instructions for implementing application behavior. The VMs interpret the bytecodes and execute corresponding native instructions on the target computer system associated with the bytecodes. Examples of software platforms that enable the creation of computer system independent applications include the Java and .Net platforms.

Java is a registered trademark of Oracle Corporation. Oracle associates the Java trademark with its eponymous computer programming language Java Virtual Machine JVM and related infrastructure and tools. .Net is a registered trademark of Microsoft Corporation. For .Net Microsoft provides its C programming language .Net runtime virtual machine and related infrastructure and tools.

The Java programming language and runtime package support the tenets of object oriented programming which includes the principles of inheritance polymorphism and data hiding. Java organizes programming objects into conceptual classes and saves the compiled bytecode for its classes into data files also known as class files. With respect to inheritance Java objects or classes of objects inherit properties and behaviors in a parent child relationship also referred to as superclass subclass respectively.

Java creates an instance of a particular class object via a process called instantiation. The phrase instantiating a class means the same thing as creating an object. An object is an instance of a class. The instantiation process involves allocating memory for the new instance to exist. Java accomplishes this by invoking a special method defined by each class called a constructor. A class object includes one or more constructors. The body of the constructor also provides the ability to initialize the data members of the class. For these reasons constructors are also referred to as object initializers and the software code within the body of the constructors as object initialization code.

A superclass is a class that has been extended by another class. This allows the extending class also known as the subclass to inherit the state and behaviors of the superclass. Subclasses form chains with one or more superclasses to create inheritance hierarchies or inheritance chains.

In an inheritance hierarchy a superclass may itself inherit information from another superclass. When analyzing classes in an inheritance hierarchy it is important to traverse the entire chain of classes in the hierarchy to preserve the data and relationships between the classes. These are also referred to as class hierarchies.

The classes towards the top of an inheritance hierarchy tend to be abstract classes that typically do not have any objects instantiated from them. The bottom most classes of the hierarchy are typically the concrete classes or declaring classes from which applications create objects that accomplish the useful work of an application.

Redefinition of classes is a well known practice. In Java the HotSpot VM has provided the ability to redefine classes at runtime since JDK 1.4. This functionality is based on the work of Mikhail Dmitriev from Safe Class and Data Evolution in Large and Long Lived Java Applications PhD thesis University of Glasgow 2001. This functionality is better known as HotSwap. In addition a publication by Allan Raundahl Gregersen Extending NetBeans with Dynamic Update of Active Modules PhD thesis University of Southern Denmark 2010 discusses dynamic update of code modules using the NetBeans development platform. NetBeans is a registered trademark of Oracle Inc.

While HotSwap provides the ability to change the code bodies of methods within an existing class and add new classes HotSwap does not support changing the superclass of a class or any inheritance related information at runtime. More recent approaches have been suggested that do support changes to the superclass but these approaches have significant limitations.

In Thomas W rthinger s Dynamic Code Evolution for Java. PhD thesis Johannes Kepler University Linz April 2011 W rthinger discloses the Dynamic Code Evolution VM product which is a patch against JDK 7 and JDK 6 that enhances the HotSwap feature with enhanced class redefinition capabilities. One of the class redefinition features is the ability to change the superclass. The Dynamic Code Evolution VM is able to perform class type widening meaning the ability to inject one or more superclasses. In addition the Dynamic Code Evolution VM is able to perform type narrowing under some assumptions.

In W rthinger s thesis the issues involved in type narrowing changes are discussed in extensive detail. On the contrary no issues are mentioned regarding type widening to which the present invention can have applicability. A major issue is that partially uninitialized objects can exist after a type widening class redefinition of a subclass using the Dynamic Code Evolution VM.

In Mario Pukall s JAVADAPTOR Unrestricted Dynamic Updates of Java Applications. PhD thesis University of Magdeburg Germany March 2012 Pukall discloses the JavAdapter product that also claims the ability to support the redefinition of superclasses. As with W rthinger however Pukall does not examine the potential for uninitialized objects to exist subsequent to a type widening class redefinition.

Other dynamic class redefinition systems exist but none other than the aforementioned approaches supports changes to the superclass. Moreover because the W rthinger and Pukall approaches do not adequately handle the case of type widening of superclass constructors during class redefinition these approaches only provide a partial solution to the problem of dynamic class redefinition.

The present invention relates to the ability to dynamically redefine classes in a running application. More particularly the present invention can enable automatic invocation of all or some of the constructors in the chain of superclasses for objects that have changed the superclass at runtime by a class redefinition.

The present invention concerns applications created from statically typed class based object oriented programming languages. The classes of the applications are typically included in class files. The invention provides a system and method for changing the contents of superclasses of the classes for the applications at runtime utilizing class redefinition methods within the classes to modify the superclasses in one example. The ability of the invention to modify superclasses at runtime provides significant advantages over present approaches to dynamic class redefinition.

The system dynamically reconstructs the current contents of objects of the declaring class. During the reconstruction the system first identifies the code associated with the set of superclass constructors that were not originally part of the objects class hierarchy. This is also referred to as newly found class code.

Then the system searches for at least one default constructor within the classes of the class hierarchy of the declaring class. A default constructor is a constructor with zero arguments.

If the system successfully locates a default constructor the system then redefines the set of classes associated with the declaring class and its existing class hierarchy to incorporate the newly added superclasses into the class hierarchy.

The redefined set of classes includes the original contents of each class and additional code generated by the system. For each redefined class the system generates superclass constructors for the newly found class code and relevant code statements to invoke the superclass constructors for the newly found class code. In this way the system creates new class inheritance chains that incorporate newly added superclasses added at runtime for existing objects.

The system starts the search for the default constructors beginning from the declaring class upwards. Ideally the default constructor is located in the lowest new superclass of the declaring class within the inheritance chain.

Current solutions to runtime class redefinition are especially susceptible to variable initialization issues when new superclasses are added. Often there are implicit assumptions within methods declared by the new superclasses about the range of possible values for the member variables of the new superclasses.

These implicit assumptions are compounded by the fact that constructors declared within the set of new superclasses have not yet executed. Typically such assumptions lead to programming errors such as null pointer exceptions. This is because programming languages typically initialize the data members of classes to their corresponding programming language default values such as NULL or primitive equivalent.

The present invention can be used to avoid these pitfalls by automatically invoking the associated constructor of each new superclass during the class reconstruction process.

In general according to one aspect the present invention features a method for automatically invoking object initializers of superclasses added to the inheritance hierarchy of existing objects. The method comprises dynamically updating class definitions of the existing objects traversing an inheritance hierarchy of the existing objects to identify all superclasses added by the dynamic update identifying one or more object initializers for each of the superclasses and invoking the object initializers of the superclasses to initialize the code for each of the superclasses.

In one example identifying one or more object initializers for each of the superclasses is accomplished during the creation of an object for each superclass by analyzing the object initializers of the subclass of each created superclass object in the inheritance hierarchy of each created superclass object.

The method further comprises invoking the object initializers for each of the superclasses in the order specified by the inheritance hierarchy of each created superclass object in some cases.

The method can also further comprise creating code for class redefinition methods for each of the superclasses from the code of object initializers for each of the superclasses and from the code of the object initializers of the subclass of each created superclass object and adding the class redefinition methods to the classes for each of the superclasses. The act of adding the class redefinition methods to the classes for each of the superclasses results in transformed superclasses.

In one implementation the method further comprises invoking the class redefinition methods for each of the transformed superclasses to initialize the code for each of the transformed superclasses. Preferably the dynamic updating of the class definitions of the existing objects accepts redefined classes for the existing objects.

The method can include the creation of code for class redefinition methods from the code of object initializers for each of the superclasses and from the code of the object initializers of the subclass of each created superclass object and adds the class redefinition methods to the redefined classes for the existing objects. The adding of the class redefinition methods to the redefined classes for the existing objects results in transformed redefined methods for the existing objects.

Typically the method further comprises invoking the class redefinition methods for each of the transformed redefined classes for the existing objects to initialize the code for each of the transformed redefined classes. Preferably the method identifies object initializers for each of the new superclasses that include zero arguments.

The method can further include identifying object initializers for each of the new superclasses using information supplied in an application.

The method can transform bytecode of one or more of the superclasses the transforming of the bytecode enables the invoking of the object initializers of the superclasses to initialize the code for each of the superclasses.

In general according to another aspect the invention features a system for automatically invoking object initializers of superclasses added to the inheritance hierarchy of existing objects of an application running on a computing device. The system includes a class loader executing on the computing device for loading dynamically updated class definitions of the existing objects. The system also includes a class file transformer that traverses the inheritance hierarchy of the existing objects to identify all superclasses added by the dynamic update and identifies one or more object initializers for each of the superclasses. In addition the system includes a declaring class interceptor that invokes the object initializers of the superclasses identified by the class file transformer to initialize the code for each of the superclasses.

Objects in a statically typed class based object oriented programming language are constructed by a chain of constructors which is executed once for each object. Constructors are special methods that are only allowed to execute once. Therefore any attempt to execute constructors directly for an already initialized object will fail. The code of every constructor is usually duplicated with slight modifications into equivalent redefinition methods that are allowed to run even for existing objects. Therefore the present invention can enable execution of constructor code represented by the generated redefinition methods for objects that are partially uninitialized due to a changed set of superclasses.

The systems implementing the invention preferably operate on top of a class redefinition system capable of redefining the superclass of a class. In embodiments the code of each constructor for all loaded classes is transformed just before class load time into a corresponding redefinition method. If the class hierarchy for an object has at least one constructor with zero arguments the systems search the specific object s declaring class upwards to each superclass in the chain of superclasses and invokes the redefinition method that corresponds to the first zero argument constructor. The redefinition method is invoked at a point in time after or during class redefinition for each object having been created before a class redefinition of the declaring class.

Code can be generated within the redefinition method to invoke the redefinition method corresponding to that other specific constructor which is invoked at the beginning of the constructor being transformed. Code is then inserted to check if the declaring class of the said class redefinition method belongs to the set of new superclasses for the said specific object s declaring class and if so continues execution of the code copied from the said constructor code. If not then further execution is omitted.

The tasks associated with transforming the constructor code can be equally performed as part of a modified Java Virtual Machine.

The tasks associated with transforming the constructor code can be equally performed by a special purpose Java agent that intercepts class loading events.

The above and other features of the invention including various novel details of construction and combinations of parts and other advantages will now be more particularly described with reference to the accompanying drawings and pointed out in the claims. It will be understood that the particular method and device embodying the invention are shown by way of illustration and not as a limitation of the invention. The principles and features of this invention may be employed in various and numerous embodiments without departing from the scope of the invention.

The processor communicates with storage via the bus . Memory such as Random Access Memory RAM Read Only Memory ROM flash memory etc. is directly accessible while secondary storage device such as a hard or solidstate disk and removable storage device such as a floppy diskette drive CD ROM drive tape storage USB memory stick etc. is accessible with additional interface hardware and software as is known and customary in the art. The removable storage device will have associated therewith an appropriate type of removable media such as a diskette CD tape reel or cartridge solid state storage etc. that will hold computer useable data and is a form of computer useable medium. Note that a computing device may have multiple memories e.g. RAM and ROM secondary storage devices and removable storage devices e.g. floppy drive CD ROM drive and USB memory stick .

The computing device typically includes an interface adapter such as a user interface adaptor that connects the processor via the bus to one or more user interface devices such as a keyboard a mouse or other pointing device a display such as a CRT monitor flatpanel LCD screen etc. a printer or any other user interface device such as a touch sensitive screen digitized entry pad etc. Note that the computing device may use multiple interface adapters in order to make the necessary connections with the user interface devices.

The computing device also commonly communicates with other computing devices computers workstations etc. or networks thereof through a communications adapter such as a telephone cable or wireless modem ISDN Adapter DSL adapter Local Area Network LAN adapter or other communications channel. This gives the computing device direct access to networks LANs Wide Area Networks WANs the Internet etc. telephone lines that may be used to access other networks or computers wireless networks such cellular telephone networks and other communication mechanisms. Note that the computing device may use multiple communication adapters for making the necessary communication connections e.g. a telephone modem card and a Cellular Digital Packet Data CDPD . The computing device may be associated with other computing devices in a LAN or WAN or the computing device can be a client or server in a client server arrangement with another computer etc. All these configurations as well as the appropriate communications hardware and software are known in the art.

The computing device provides the facility for running software such as Operating System software Middleware software and Application software . A virtual machine is a special example of application software . Note that such software executes tasks and may communicate with various software components on this and other computing devices . The computing device also includes a virtual machine .

As will be understood by one of ordinary skill in the art computer programs such as that described herein including Operating System software Middleware software and or Application software are typically distributed as part of a computer program product that has a computer useable media or medium containing or storing the program code. Therefore media medium computer useable medium or computer useable media as used herein may include a computer memory RAM and or ROM a diskette a tape a compact disc an integrated circuit a programmable logic array PLA a remote transmission over a communications circuit a remote transmission over a wireless network such as a cellular network or any other medium useable by computers with or without proper adapter interfaces. Note that examples of a computer useable medium include but are not limited to palpable physical media such as a DVD CD Rom diskette hard drive and the like as well as other non palpable physical media such as a carrier signal whether over wires or wireless when the program is distributed electronically. Note also that servlets or applets according to Java technology available from Oracle Inc. would be considered computer program products.

Although the enabling instructions might be written on on a diskette or tape stored in an integrated circuit or PLA carried over a communications circuit or wireless network it will be appreciated that for purposes herein the computer useable medium will be referred to as bearing the instructions or the instructions or software will be referred to as being on the medium. Thus software or instructions embodied on a medium is intended to encompass the above and all equivalent ways in which the instructions or software can be associated with a computer useable medium.

For simplicity the term computer program product is used to refer to a computer useable medium as defined above which bears or has embodied thereon any form of software or instructions to enable a computer system or multiple cooperating systems to operate according to the above identified invention.

It will be likewise be appreciated that the computer hardware upon which the invention is effected contains one or more processors operating together substantially independently or distributed over a network and further includes memory for storing the instructions and calculations necessary to perform the invention.

Those skilled in the art will recognize that a method according to the present invention may be created in a variety of different ways known in the art. For example a general purpose computing device as described in may be configured with appropriate software so that the computing device functions as described hereafter. Furthermore discrete electronic components may be used to create a system or computer program product that implements all or part of the functional. Finally note that combinations of multiple computing devices running appropriate software or discrete electrical components can be used in like fashion. Essentially the hardware is configured whether by software custom designed etc. to perform the functional elements making up the present invention.

The dynamic program update includes changes to one or more of the original classes such as redefined class for original class Z and can include one or more new superclasses identified as class G in one example. Redefined class is also identified as Z to indicate that it represents a redefined version of original class Z. The class loader loads class files for classes Z and G in response to the dynamic program update .

A class file is updated when the user specifies changes to the class files of one or more of the original classes where the changes redefine the classes at runtime. The class file transformer of the transforming agent transforms newly added classes G and Z as they are loaded by the class loader .

Specifically the redefined classes are those classes for which the user changes or adds new class inheritance relationships. Examples include changing the content of original classes such as Z to create redefined classes such as Z and adding a new superclass such as G to redefined class Z .

The transformer applies its code transformation to all classes in the system as the classes are loaded by the class loader . For the code transformation the transformer generates code for new helper methods called redefinition methods and copies the code for the redefinition methods into the classes of certain redefined classes and new superclasses in one example.

In original classes labeled X Y and Z undergo a dynamic class update . At runtime the user redefines class Z labeled as redefined class Z to be a subclass of new superclass G. Before the class loader can load the bytecodes associated with redefined class Z and new superclass G into virtual machine the transformer intercepts the class loader .

The classes modified by the transformer to include the redefinition methods are referred to as transformed classes and transformed superclasses . The bytecodes that result from the transformed classes and the transformed superclasses are referred to as transformed bytecodes . Finally the transformer loads the transformed bytecodes into the virtual machine such as a Java Virtual Machine which executes the instructions for the application on the computing device .

When invoked the redefinition methods perform tasks such as initializing the member variables or attributes for certain classes of objects that would otherwise be uninitialized during the dynamic class update using current approaches to class redefinition.

During execution of the application or execution of a test program that references objects of the application the runtime environment of the virtual machine encounters code of the application that declares instances of objects also known as the declaring class of an object. The interceptor first locates the class associated with the declaring class .

Then the interceptor makes decisions as to whether the classes for the declaring class include redefinition methods and whether to invoke those redefinition methods . The invocation of the redefinition methods during the instantiation of declaring class objects initializes data members of the redefined classes and classes within the class hierarchies of the redefined classes.

More details will be provided for the creation and usage of the redefinition methods in the descriptions that accompany the remaining figures.

In the preferred embodiment the transforming agent is implemented as a software module or application running within the operating system of a computing device such as a computer workstation network appliance or tablet device. In another implementation the transforming agent is implemented within a virtual machine VM of the computing device such as a Java Virtual Machine.

In step the transformer intercepts the class loader to transform the code of constructors in class files before the class loader loads each class. In step the transformer selects the next class file to process and opens it with write access exiting if no more class files are found. According to step the transformer attempts to identify the next constructor within the class file. If the transformer does not find a constructor within the class file in step the transformer saves the contents of the class file in step and moves to the next class file in step .

If the transformer identifies a constructor within the class file in step the transformer continues to step where the transformer generates an empty redefinition method body for the current constructor with the same signature as the current constructor.

Step includes all steps associated with generating and inserting code statements into the redefinition methods created in step . Step encapsulates the actions for steps and .

Steps and involve the first code insertion action for the created redefinition method . In step the transformer checks if the currently processed constructor has the top level class of the class inheritance hierarchy as its superclass. For each redefinition method created in step the result of step determines the content of statements that the transformer inserts within the body of each redefinition method .

Step first determines if the class for the current constructor has the top level class in the class inheritance hierarchy as its superclass which in the java programming language is java.lang.Object. If this statement is true this indicates the end of the chain of superclasses and the transformer transitions to step . Otherwise the transformer transitions to step .

In step the transformer inserts code that invokes a redefinition method corresponding to a statement at the beginning of the current constructor that invokes either another constructor within the same class definition as the current constructor or invokes a constructor within the superclass of the current constructor. At the conclusion of step the transformer transitions to step to process the second code insertion action.

In step the transformer inserts code for a conditional statement that checks if the declaring class is part of the set of redefined superclasses in the chain of superclasses for the object that initiated the invocation of the redefinition method at runtime. The transformer then proceeds to step .

According to step the transformer inserts the remaining contents of the current constructor inside the branch that yields true of the inserted conditional statement from step . Then the transformer transitions to step to stop writing to the current redefinition method .

When the transformer stops writing to the current redefinition method in step the transformer then transitions back to step to find the next constructor within the class file for the current class. When the transformer cannot find any more constructors in the class file in step the transformer saves the class file in step and then selects the next class file to process in step . The transformer in step exits when it cannot find any more class files to process.

The interceptor operates upon declaring class objects when the classes for the declaring class objects have been redefined with a new set of superclasses. An example of a declaring class object that meets these criteria is described in detail in the example in and associated but is briefly included here for convenience.

For example if class MountainBike was a stand alone class as part of an original application and the user attempts a dynamic class update that injects new superclass Bike and redefines class MountainBike as a subclass of superclass Bike a runtime execution code snippet in the application such as

In step the interceptor identifies the class file associated with the current declaring class object referenced in the running program. Then in step the interceptor determines if a class redefinition has occurred for the object where the redefinition included a new superclass for the object. If this statement is false the interceptor ends processing for the current declaring class object in step . If this statement is true the interceptor proceeds to step to find the class inheritance hierarchy for the object and point to the class at the bottom of the hierarchy which is the class for the declaring class object itself.

If the interceptor in step indicates that the current class for the object has a superclass different from the top level class then the interceptor proceeds to step . If this is not the case the interceptor ends processing for the current declaring class object in step .

According to step the interceptor searches the class to find a zero argument constructor. If the class does not have a zero argument constructor the interceptor does not invoke any redefinition methods for the current class and transitions to step . In step the interceptor overrides the declaring class object with the value of its superclass object.

When step completes the interceptor repeats the check in step to check the class for the object which is now the superclass of the original declaring class object. In this way the interceptor iteratively moves up to the next superclass in the declaring class object s inheritance hierarchy until the top class of the inheritance hierarchy is reached.

If the interceptor in step does find a zero argument constructor for the current object associated with the declaring class the interceptor proceeds to step to invoke the redefinition method associated with the zero argument constructor of the object currently pointed to. Upon completion of step the interceptor transitions back to step to locate the next superclass in the declaring class object s class inheritance hierarchy invoking the associated redefinition methods for all classes in the inheritance chain for the declaring class object.

It is important to note that the redefinition methods themselves create the chain of invocations and the interceptor performs the invocations by executing the redefinition methods. When the bottom most redefinition method is invoked the interceptor will invoke the included superclass redefinition method as if it were a constructor.

In another embodiment a pure Java Virtual Machine implementation looks for the constructors it needs to invoke after redefinition without the need to insert any generated code into the class definitions at load time.

In the example original class MountainBike is part of an application running on a computing device in one implementation. The classes for the application are subjected to a dynamic program update by a class loader when a user at runtime provides updates to the original classes . The updates include redefined class MountainBike and the introduction of a new superclass Bike .

According to object oriented programming terminology redefined class MountainBike is now a subclass of new superclass Bike where redefined class MountainBike inherits information from new superclass Bike . New superclass Bike is also referred to as a parent class of redefined class MountainBike .

During the dynamic program update the class loader loads the classes for the new superclasses and the redefined classes .

The descriptions associated with provide sample code in one implementation using the Java programming language. The code samples in illustrate some of the problems associated with adding new superclasses for existing objects subjected to a class redefinition of classes for the existing objects with reference to the class diagram of .

The descriptions associated with provide sample code in one implementation using the Java programming language. The code samples in illustrate how the invention can be used to overcome the problems raised for the example associated with current class redefinition approaches. The code samples in reference the class diagram of .

However the class declaration of redefined class MountainBike declares an inheritance relationship to new superclass Bike the contents of which appear in . Moreover other information has changed in redefined class MountainBike . The number of data members has changed and the contents of the only non default constructor has changed to provide initialization for only those data members that exist in the redefined class MountainBike .

The code snippet of illustrates problems that class redefinition of existing objects can create. An instance of the declaring class Bike is created in . Then the test program performs an operation on class method addAttribute for object bike of declaring class Bike . The execution of the code in will cause null pointer exception errors.

The errors occur because any objects for original class MountainBike in the application that were constructed before the class redefinition by the user have no knowledge of new superclass Bike . Specifically the call to declaring class to create an object instance of new superclass Bike will not initialize the attributes Map object of data members . Only the non default constructor initializes the attributes Map object allocating memory for the object and assigning initial values.

As a result the call to declaring class for new superclass Bike will cause the Map attributes object of data members to be uninitialized and the java compiler will point this to a NULL object. When the call in attempts to populate the attributes Map object the application will issue a null pointer exception.

As with the example for the sample code in E for the example creates an instance of the declaring class Bike. Then the test program performs an operation on class method addAttribute for object bike of declaring class Bike . Unlike the example for however the execution of the code will not result in null pointer exception errors. This is because the example utilizes the transformer method and the interceptor method to overcome the problems associated with current class redefinition approaches outlined herein.

The application of the transformer method to the code in redefined class MountainBike results in the code in transformed class MountainBike . The transformed class MountainBike includes the contents of redefined class MountainBike and additionally includes generated redefinition methods and .

The transformer intercepts the class loader in transformer method step and selects the class file for redefined class MountainBike in transformer method step . Then in transformer method step the transformer identifies a constructor within the class file constructor . Because the transformer found a constructor within the class file in transformer method step the transformer transitions to transformer method step .

According to transformer method step the transformer creates an empty code body for redefinition method from constructor and transitions to transformer method step to populate the contents of redefinition method .

For populating the contents of redefinition method the transformer in transformer method step first determines that superclass Bike of MountainBike is not the top level class in the class hierarchy for declaring class Bike. This is because the top most class in the class hierarchy for declaring class Bike is java.lang.Object. As a result the transformer in step inserts the code in that invokes superclass redefinition method associated with the call to superclass in constructor . Note that the redefinition method itself is a member of the transformed new superclass Bike in .

Then the transformer according to transformer method step inserts code for the conditional code statement in reference . Next the transformer inserts the remaining contents of the current constructor in reference according to transformer method step . Finally according to transformer method step the transformer completes the code for redefinition method in reference .

Transformer method step returns to step to identify the next constructor in the current class file . Because the transformer found a constructor within the class file in transformer method step the transformer transitions to transformer method step .

In transformer method step the transformer creates an empty code body for redefinition method from constructor and transitions to transformer method step to populate the contents of redefinition method .

For populating the contents of redefinition method the transformer in transformer method step first determines that call in the current constructor does not reference the top level class in the class hierarchy and transitions to transformer method step . According to transformer method step the transformer inserts the code in that invokes redefinition method within the same class file and transitions to transformer method step .

According to transformer method step the transformer determines that there are no remaining contents in constructor beyond reference to include within the conditional statement that transformer method step normally generates. As a result transformer method step omits the insertion of what would otherwise have been an empty conditional statement. The transformer transitions to transformer method to complete the code for redefinition method in reference and transitions to transformer method step to identify the next constructor within the class file.

In transformer method step and the transformer does not find any more constructors to process proceeds to transformer method step to save the contents of the class file and transitions to transformer method step to process the next class file.

The application of the transformer method to the code in new superclass Bike results in the code in transformed new superclass Bike . The transformed new superclass Bike includes the contents of new superclass Bike and additionally includes generated redefinition method .

Applying the transformer method to the new superclass Bike the transformer intercepts the class loader according to transformer method step and selects the class file for new class Bike in transformer method step . Then in transformer method step the transformer identifies a constructor within the class file constructor . Because the transformer found a constructor within the class file in transformer method step the transformer transitions to transformer method step .

In transformer method step the transformer creates an empty code body for redefinition method from constructor and transitions to transformer method step to populate the contents of redefinition method .

For populating the contents of redefinition method the transformer in transformer method step first determines that the superclass of the current constructor is java.lang.Object which is the top level class in the class hierarchy for declaring class Bike. As a result the transformer transitions to transformer method step .

According to transformer method step the transformer then inserts code for the conditional code statement in reference . Next the transformer inserts the remaining contents of the current constructor in reference according to transformer method step . Finally according to transformer method step the transformer completes the code for redefinition method in reference .

Applying the interceptor method to the declaring class Bike in results in the execution chain in which initializes the attributes object of class Map within the data members of transformed new superclass Bike . As a result subsequent calls that reference declaring class Bike such as calls that set the attributes object in of instance bike of declaring class Bike will operate successfully upon existing MountainBike objects without encountering the null pointer exceptions encountered in the example in .

While this invention has been particularly shown and described with references to preferred embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the scope of the invention encompassed by the appended claims.

