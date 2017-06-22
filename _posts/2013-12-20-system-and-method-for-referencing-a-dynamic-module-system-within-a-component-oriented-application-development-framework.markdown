---

title: System and method for referencing a dynamic module system within a component oriented application development framework
abstract: A system and method can support a hybrid application development environment. The system allows a client application in the application runtime environment to obtain a reference to a framework instance for a dynamic module system. Furthermore, the system can configure a bundle in the dynamic module system to be a gateway bundle based on the framework instance, and the client application can access the dynamic module system using the gateway bundle.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09152384&OS=09152384&RS=09152384
owner: ORACLE INTERNATIONAL CORPORATION
number: 09152384
owner_city: Redwood Shores
owner_country: US
publication_date: 20131220
---
A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

This application claims priority on U.S. Provisional Patent Application No. 61 865 005 entitled SYSTEM AND METHOD FOR INTEGRATING A DYNAMIC MODULE SYSTEM WITH A COMPONENT ORIENTED APPLICATION DEVELOPMENT FRAMEWORK filed Aug. 12 2013 which application is herein incorporated by reference.

This application is related to the following patent application which is hereby incorporated by reference in its entirety 

U.S. Patent Application entitled SYSTEM AND METHOD FOR PROVISIONING A DYNAMIC MODULE SYSTEM WITHIN A COMPONENT ORIENTED APPLICATION DEVELOPMENT FRAMEWORK application Ser. No. 14 137 455 filed Dec. 20 2013.

The present invention is generally related to computer systems and is particularly related to providing an application development framework for software developers.

As software systems become more complex the component orientation and code modularity have become increasingly important design goals. Assembling software from reusable components enables developers to reuse code to modify software quickly when requirements evolve to mitigate costs of producing multiple versions and to reduce development time by integrating pre written third party components.

Described herein is a system and method that can support an application development framework. The system allows a client application in the application development environment to obtain a reference to a framework instance for a dynamic module system. Furthermore the system can configure a bundle in the dynamic module system to be a gateway to the dynamic module system and the client application can access the dynamic module system using the gateway bundle.

The invention is illustrated by way of example and not by way of limitation in the figures of the accompanying drawings in which like references indicate similar elements. It should be noted that references to an or one or some embodiment s in this disclosure are not necessarily to the same embodiment and such references mean at least one.

The description of the following embodiments of the invention uses the Java Platform Enterprise Edition or Java EE platform as an example for an application development environment. It will be apparent to those skilled in the art that other types of application development environment can be used without limitation. Also the description of the following embodiments of the invention uses the OSGi formerly known as the Open Services Gateway initiative now an obsolete name platform as an example for a dynamic module system. It will be apparent to those skilled in the art that other types of dynamic module systems can be used without limitation.

Described herein is a system and method that can provide a component oriented modular framework for software developers.

Various component oriented modular frameworks can be provided to Java developers. Although these application development frameworks may all have a notion of application container to which software developers can deploy their applications there can be significant differences among them.

For example a component oriented application development framework e.g. the Java EE platform can define a set of services application programming interfaces APIs and protocols that can facilitate component oriented application development. However the Java EE framework which allows the development of secured persistence aware transactional and scalable Java applications may provide limited support for modularity.

On the other hand the OSGi platform provides a framework for building modular service oriented applications and addresses the modularity needs of applications.

For example the OSGi platform allows an application to be decomposed into smaller units called modules a.k.a. bundles . A module in the OSGi platform which is a unit of deployment and management can include a cohesive set of Java classes and resources that can provide a well defined functionality. Also each module can contain additional metadata that explicitly states a module s capabilities and requirements or dependencies .

The OSGi platform can be responsible for matching a module s requirements with capabilities offered by other modules in the runtime. Also the OSGi platform can define a sophisticated service framework which allows modules to registers plain old Java objects POJO as services in a service registry. Additionally the OSGi platform can have excellent support for versioning and dynamicity.

For example each OSGi bundle can have its own class loader which can be created by the OSGi runtime. Every bundle class loader with the exception of the system bundle can have a private classpath which points to resources packaged inside the bundle jar. Additionally every bundle class loader can have a list of other bundle class loaders to be used as delegate loaders in order to satisfy the external dependencies of a bundle.

On the other hand a system bundle which can be considered as a virtual bundle can be based on an OSGi framework instance. The OSGi framework instance can be associated with an org.osgi.framework.launch.Framework type and can implement an org.osgi.framework.Bundle interface. Furthermore the content for the system bundle may not come from a bundle jar file or other bundles. The OSGi environment can load the system bundle using the class loader that is used to load the OSGi framework class. Thus the class loading of system bundle can be under the control of an application developer.

Otherwise the system bundle appears as a regular bundle to the rest of the OSGi environment. The system bundle can publish and consume services. Also the system bundle can export packages. A user can configure an exported package list for a system bundle using properties such as org.osgi.framework.system.packages or org.osgi.framework.system.packages.extra. Furthermore the exported packages can have use constraints which ensure consistent class space in a multi versioned environment. On the other hand the system may not import any packages due to the fact that the class loader for a system bundle is not controlled by the OSGi runtime.

There have been various efforts to integrate the Java EE platform with the OSGi platform. The existing approaches all require a fundamental change to the way that the Java EE application is developed and deployed. For example since the OSGi runtime becomes the deployment platform all applications have to be repackaged and deployed as one or more OSGi bundles.

Thus the existing approaches which require an application to be developed and deployed as a set of modules may have various drawbacks.

For example retrofitting existing monolithic Java EE applications into the OSGi model can be a heavy duty task for the Java EE application developers. Also changes to the existing Java EE tools and practices may waste the investment over the years.

Additionally switching the entire Java EE application to run under the control of the OSGi framework can be inherently risky because the underlying Java EE technologies may not consistently support the application modularity. For example a Java EE application may take advantage of the context loader of a thread in order to achieve extensibility with an assumption of the global visibility which may not be true in the OSGi environment.

In accordance with an embodiment of the invention the system can integrate a dynamic module system e.g. an OSGi platform with a component oriented application development framework e.g. a J2EE platform.

The system can provide a migration path to gradually modularize a Java EE application. For example the system enables the Java EE application developers to leverage OSGi platform while allowing the Java EE application developers to continually using their existing software development environment code and processes.

The incremental process can inherently safeguard the modularization of an application and does not affect developer productivity. Since the changes to the Java EE applications are incremental in nature it is a safer option or solution that is suitable for most enterprise Java developers. Also the incremental process allows the applications to take full advantage of the OSGi platform. Thus the software developers can be successful in developing modular enterprise Java applications.

In accordance with an embodiment of the invention the system can provide a hybrid environment that allows the software developers to take advantage of the features provided by both the J2EE platform and the OSGi platform. These features can include modularity dependency management and service dynamism provided by the OSGi platform. Additionally the system allows the software developers to use different component frameworks such as EJB Servlet JAX RS JSF CDI etc. Also the system allows the software developers to use various infrastructure services such as transaction management security and persistence offered by the Java EE platform.

Furthermore the system allows a Java EE developer to turn an existing application into an OSGi bundle while permitting the Java EE application to run inside the existing Java EE runtime. Also the system allows different Java EE applications to be deployed into a traditional Java EE container while allowing the Java EE applications to expose their resources e.g. classes EJBs beans to the OSGi runtime. Thus the Java EE applications do not have to be restructured as OSGi bundles in order to leverage the OSGi platform and the OSGi runtime can make these resources available for consumption by other Java EE applications and non Java EE applications.

In accordance with an embodiment of the invention the system can leverage the virtual bundle capability e.g. based on the system bundle feature in the OSGi platform in order to provide support for integration between the OSGi platform and the Java EE platform. For example the system enables the following use cases which may otherwise be difficult to achieve in a pure Java EE environment 

Thus the system which can be simple to implement does not require the underlying Java EE server runtime to run on a modular platform such as the OSGi runtime. Also the system allows more development time for modularizing the Java EE server runtime.

The host application can chose to keep the OSGi framework private to itself or make the OSGi framework available globally for other applications. On the other hand an application may need to be a client application in order to export or import resources. Furthermore a host application can be implicitly a client application .

Thus there can be different aspects for enabling the OSGi Java EE integration via supporting using OSGi platform from within Java EE applications. These different aspects can include the provisioning of an OSGi Framework by a Java EE application and the referencing the OSGi runtime from a Java EE application to export import resources. Here the resources can include the classes and static resources such as images properties file available via application class loader chain and application objects such as EJBs JDBC data sources CDI beans etc. which are managed by a Java EE application container.

Furthermore the host application in the Java EE runtime can access and control the OSGi runtime . For example the host application can act as a system bundle for the OSGi runtime and can load the OSGi runtime using a class loader whose parent is an application class loader. Thus the host application can be configured to export its resources to the OSGi runtime and or consume various OSGi services.

Additionally using the host application the system allows for the integration of the OSGi platform and the Java EE platform without requiring any special support from the underlying Java EE runtime . Thus the host application can continue to run as a native Java EE application.

In accordance with an embodiment of the invention the life cycle of the OSGi framework can be tied to the life cycle of the host application . For example the OSGi framework can be activated when the host application is started loaded by the Java EE application container . Also the OSGi framework can be deactivated when the host application is stopped unloaded.

The OSGi framework instance can be published in the Java EE application container if the OSGi framework instance needs to be shared by other applications in Java EE application container . For example the host application can use JNDI Java EE application container to control the visibility of a published OSGi framework instance in order to take advantage of the simplicity versatility and namespace support of JNDI . Alternatively the OSGi framework instance can be published using a JMX server in the Java EE application container .

In accordance with an embodiment of the invention a Java EE application developer can provision the OSGi framework based on a programmatic approach. Here the programmatic approach which can be dynamic and easily customizable may not require any change to the underlying application container. Alternatively a Java EE application developer can provision the OSGi framework based on application configuration mechanism in the Java EE application container .

Furthermore the host application can provision various services in the OSGi runtime. These services can include EJBs DataSources CDI beans POJOs etc. Also the system can install and start a set of OSGi bundles while provisioning the OSGi framework. Here the OSGi bundle jars that contain the OSGi bundles can be embedded inside the application or can be downloaded from an external repository .

An exemplary host application can be based on OSGi related implementation classes contained in a deployment package.

For example the OSGi related implementation classes in a sahoo.samples.wls.ejbosgiservice.server.osgi package can include a WebappMain class which is a servlet context listener. Also this package can include a OSGiFrameworkProvisioner class which can be a utility class used by the WebappMain class and a OSGiServicePublisher class which can be a dummy servlet.

Here the WebappMain class can be the entry point for the examplary host application. The WebappMain class together with the OSGiFrameworkProvisioner class can be responsible for provisioning the OSGi framework in the Java EE application.

For example the WebappMain class can be responsible for participating in the Java EE application life cycle process that includes receiving the notification of application start stop events. Also the WebappMain class can be responsible for creating a class loader that has visibility to application resources and OSGi framework jars. This class loader is used to load the OSGi framework looking up a framework factory using JDK Service Provider META INF services mechanism and using it to instantiate a framework instance e.g. a Felix instance . Additionally the WebappMain class can be responsible for pre provisioning a set of bundles into the framework e.g. Felix shell bundles and publishing the framework in JNDI as java global osgi framework.

Furthermore the OSGiServicePublisher class which can be a dummy servlet is responsible for publishing services to the OSGi runtime. The OSGiServicePublisher class can be set up to be loaded on startup. Since the OSGiServicePublisher class is a servlet the OSGiServicePublisher class is guaranteed to be loaded after the OSGiFrameworkProvisioner class which is a ServletContextListener. Thus the OSGiFrameworkProvisioner class can safely use the OSGi framework from JNDI.

As shown in the above the EJB can be based on a sahoo.samples.wls.ejbosgiservice.server.impl.FooEjb.class which has a local business interface sahoo.samples.wls.ejbosgiservice.server.api.Foo.class. 

Also the host application can use the framework configuration properties file e.g. an osgi.properties file to configure exportation of the package. Here in order to use the exported EJB as an OSGi service the host application can export the EJB business interface packages for other bundles e.g. using the following entry in an osgi.properties configuration file 

As shown in the above the host application is able to export not only packages but also different classes from a parent class loader.

Additionally the system can use shell bundles such as the Felix remote shell bundles in WEB INF bundles . Thus after a user deploy the application into a Java EE server the user can connect to the provisioned OSGi runtime via the Felix remote shell bundle and inspect the application.

The following List 2 shows a manifest for a pure OSGi bundle that can access the EJB interface package and the EJB service based on the OSGi mechanism.

As shown in the above this bundle can import the EJB interface package. Also this bundle may not be aware that it is calling an EJB since it has a bundle activator.

The following List 3 shows an exemplary bundle activator which can look up the service in OSGi service registry and invokes a business method.

In accordance with an embodiment of the invention the system can use a client application to consume a service registered by another application.

In accordance with an embodiment of the invention a client application in the Java EE environment can obtain a reference to an OSGi runtime . As shown in the client application can select a bundle e.g. from its own directory of bundles as the gateway bundle to access the OSGi runtime . Here the gateway bundle allows the client application to have better control over which resources or services that it wants to import from the OSGi runtime . Furthermore the gateway bundle also simplifies security configuration and lifecycle management of the client application .

Additionally in order for the client application in the Java EE environment to have visibility to the host application classes in the bundles the class loader for the client application can be set up to delegate to a referenced bundle class loader . The metadata of the referenced bundle can determine which classes are made available to the client application . For example the system can configure that whatever is loadable via Bundle.loadClass or Bundle.getResource type API can be made available to the client application .

For example the client application can obtain a reference to an OSGi framework instance from JNDI . Here the OSGi framework instance can implement an org.osgi.framework.Bundle interface which provides access to the OSGi runtime . Additionally when the client application is also a host application e.g. in the case of the host application as shown in the object to access the OSGi runtime can be the OSGi framework instance which is provisioned by the host application .

As shown in the system can make the bundle available in a fixed JNDI location which allows another application or any code in the same module to access the bundle . Also the client application can use the bundle as a gateway to access the OSGi runtime for publishing and or consuming OSGi services.

Furthermore the client application can state a dependency on the OSGi runtime and configure a gateway bundle that can be used to access the OSGi runtime . For example the system can be based on the OSGi for Applications feature in the WebLogic environment.

Additionally in order to access the OSGi runtime the application developers can use annotation or deployment descriptor to specify the name of the framework instance to use a directory within the client application which can be used to scan bundle jar files that are automatically installed and started as part of the client application and a bundle that is used as the gateway to the referenced OSGi runtime.

Thus when the application is started the Java EE runtime can parse the above descriptor entries in List 4 or analyze the above annotation in List 5 to set up the environment For example the Java EE application container can install and start a set of bundles in the referenced framework set up the application class loader to also delegate to the class loaders associated with the different referenced bundles and make the referenced bundle available e.g. in a module specific JNDI name such as java module osgi bundle. 

Furthermore the Java EE container can stop and or uninstall the bundles when the client application is stopped.

In accordance with an embodiment of the invention the system can handle inter application dependency among various client applications and host applications involved in the class loader organization. The class loader organization can determine how client applications depend on host applications via the OSGi module layer. Additionally the client application and host applications can use each others published services.

For example the Java EE runtime can support different applications with corresponding class loaders and the OSGi runtime can support different bundles with corresponding class loaders .

As shown in a host application in the Java EE runtime environment can provision the OSGi runtime and a client application in the Java EE environment can obtain a reference to the OSGi runtime .

Furthermore the system involves a life cycle dependency between the host application and client applications . This dependency can be handled in the Java EE runtime frameworks. For example different Java EE servers such as WebLogic Server and GlassFish can support deployment order for various Java EE applications. Inside a deployment file such as an EAR file the deployment order for different modules can be controlled using Java EE configuration file e.g. the application.xml file.

Thus the host applications such as the application can be configured to be loaded ahead of the client applications such as the application and the opposite order can apply during the unloading of the client applications. Furthermore there can be no additional life cycle requirements if the client application does not install any framework extension bundles.

Additionally an OSGi framework can be used only in the local server since the OSGi runtime is not a serializable entity. When an application is deployed to a cluster then the application can automatically get loaded in each cluster instance separately. Thus as part of loading in different cluster instance an OSGi framework can be provisioned separately on each cluster instance. This ensures that the OSGi framework may always be available locally and can make the OSGi Java EE integration working in a cluster.

Furthermore some JNDI implementations such as WebLogic JNDI can support replication in a cluster. In order to publish the OSGi framework to global JNDI context in such an environment the system can make sure that the underlying JNDI implementation does not try to replicate OSGi framework in a cluster. For example in WebLogic JNDI the system can set the weblogic.jndi.replicateBindings property to false while exporting the OSGi framework object to the global JNDI context.

Moreover security can be built into every layer of the OSGi framework and can be used when JVM is started with a security manager. The security manager can define a number of permission classes that control access to OSGi API. Since the OSGi API can be directly accessed by Java EE application code an administrator can control the security at the level of Java EE application code. For example the client application may require being given appropriate OSGi permission to call Bundle.getBundleContext.

As shown in the above the servlet FooServlet can inject a local EJB which can be part of another independently deployed application using a portable JNDI name e.g. java global sahoo.samples.wls.ejbosgiservice.server FooEjb. Furthermore the servlet FooServlet can invoke the business method of the EJB FooEjb and can print the result to response stream in the service method. Here there is no need to bundle the EJB interface classes. Even when the EJB interface classes are bundled the local EJBs are called via call by reference semantics which means that both the callee and the caller shares the same runtime classes for the interfaces.

The following List 7 shows a configuration file in the deployment file e.g. a weblogic.xml file in the WEB INF directory.

Furthermore the exemplary client application can configure a bundle such as sahoo.samples.wls.ejbosgiservice.webclient.bundle as the OSGi gateway bundle. This bundle can be packaged as 

This bundle jar can be an empty jar which imports the EJB interface package. The following List 8 shows a manifest for the bundle jar.

Furthermore this gateway bundle can be installed into the same framework that was provisioned by the exemplary host application as described in the previous section. Also the class loader for the exemplary host application can be set up to delegate to this gateway bundle. The delegate bundle can be wired to the EJB interface package that is part of the host application.

The present invention may be conveniently implemented using one or more conventional general purpose or specialized digital computer computing device machine or microprocessor including one or more processors memory and or computer readable storage media programmed according to the teachings of the present disclosure. Appropriate software coding can readily be prepared by skilled programmers based on the teachings of the present disclosure as will be apparent to those skilled in the software art.

In some embodiments the present invention includes a computer program product which is a storage medium or computer readable medium media having instructions stored thereon in which can be used to program a computer to perform any of the processes of the present invention. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs microdrive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs VRAMs flash memory devices magnetic or optical cards nanosystems including molecular memory ICs or any type of media or device suitable for storing instructions and or data.

The foregoing description of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Many modifications and variations will be apparent to the practitioner skilled in the art. The modification and variation include any relevant combination of the disclosed features. The embodiments were chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalence.

