---

title: Cross-platform software framework for embedded systems on data storage device
abstract: The embodiments of present invention relates to methods and systems for a cross-platform framework for embedded systems. One embodiment provides a framework for a network attached storage or other storage devices. The framework provides a standardized structure for modules of software, such as plugins, to implement various features on the embedded system. In addition, the framework supports interoperability between software modules written in either native code, such as C, C++, and interpreted code, such as JAVA™.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09110758&OS=09110758&RS=09110758
owner: Western Digital Technologies, Inc.
number: 09110758
owner_city: Irvine
owner_country: US
publication_date: 20130624
---
This application claims priority to U.S. Provisional Application No. 61 798 362 entitled SOFTWARE FRAMEWORK FOR A STORAGE DEVICE filed Mar. 15 2013 which is herein incorporated by reference in its entirety.

On embedded and thus resource limited devices updating to add new functionality and bug fixing becomes more and more necessary. Typically a storage device such as a network attached storage NAS is constructed as a specialized computer or appliance. Normally such devices use low power hardware and having an embedded operating system such as LINUX that is configured specifically as a storage device.

Today due to their increasing complexity storage devices now run software to implement their various features and manage their interactions with other devices. Unfortunately the software for each storage device is custom built and integrated into a single package with the operating system. This form of software development is difficult and often results in bugs etc.

The current software architecture used in embedded devices makes it difficult for developers and vendors to write applications that interact in a consistent manner with other applications for example running on a storage device. It is also difficult for developers and vendors to write applications in different languages and update the program code. Accordingly it would be desirable to provide a different architecture for embedded devices especially storage devices.

The embodiments relate to methods and systems for a cross platform framework for embedded systems. The framework implements a plugin architecture that can be implemented on a variety of platforms including embedded devices such as storage devices. The framework enables creation of components for applications in a modular fashion that can be assembled together and upgraded incrementally in whole or in part. One embodiment provides a framework for a network attached storage or other storage devices. The framework provides a standardized structure for modules of software such as plugins to implement various features on the embedded system. In some embodiments the framework is based on native code that is compiled to run the embedded device and thus can support virtually any programming language used to write applications and plugins for the framework. In addition the framework supports interoperability between software modules written in either native code such as C and various clients. In some embodiments the framework may support applications and plugins written in interpreted code such as JAVA clients or plugins.

The framework provides an abstraction layer and makes code running on an embedded device such as a storage device modular and configurable. Thus various embedded device products can be configurable with different features. In some embodiments the framework also modifies which plugins are served.

A consistent programming model provided by the framework helps bundle developers cope with scalability issues in many different dimensions. The framework may run on a variety of devices whose differing hardware characteristics may affect many aspects of a service implementation. Consistent interfaces provided by the framework can ensure that the software components supported by the framework can be mixed and matched and still result in stable systems.

For example the framework allows bundles to select an available implementation at run time through the framework service registry. Bundles may register new services receive notifications about the state of services or look up existing services to adapt to the current capabilities of the device. This aspect of the framework makes an installed bundle extensible after deployment that is new bundles can be installed for added features or existing bundles can be modified and updated without requiring the system to be restarted.

In one embodiment the framework is implemented using native program code such as C . The native implementation of the framework provides several advantages. Dynamic loading of modules may be implemented with standard mechanisms. Dependencies between modules can be resolved when they are loaded. The framework can also provide significant advantages regarding performance and memory requirements. Some embodiments use open standards and execution of native binary code and are capable of running on any standard Portable Operating System Interface POSIX system.

The embodiments enable dynamic loading of code at runtime on the basis of shared object files and control the visibility of code modules e.g. import export packages . The framework provides a mechanism to load different versions of the same package and if desired supports object oriented code as well as different file formats such as the JAVA Archive File Format JAR to package and deploy bundles. In some embodiments the framework allows updates of bundles at runtime.

Furthermore the embodiments provide functionality of a life cycle layer e.g. resolve start stop update a service layer i.e. services service listeners filters and support for various devices to participate in software defined storage.

In one embodiment the framework of the present invention provides an asynchronous event driven message passing framework that implements a plugin architecture suitable for use across platforms and product lines. It enables the creation of components developed along the lines of a software factory that produces software parts engineered for assembly into products as well as upgrades to and future versions of existing products.

Certain embodiments of the inventions will now be described. These embodiments are presented by way of example only and are not intended to limit the scope of the inventions. Indeed the novel methods and systems described herein may be embodied in a variety of other forms. Furthermore various omissions substitutions and changes in the form of the methods and systems described herein may be made without departing from the spirit of the inventions. To illustrate some of the embodiments reference will now be made to the figures.

As shown the system may comprise a client or host device a network and a storage device . The storage device may be implemented as a NAS device having a plurality of storage media . These components will now be further described.

Host device refers to any computing device used to access files shared by storage device . For example the host device may be a personal computer a laptop computer a tablet computer a mobile phone etc. Such devices are well known to those skilled in the art.

Network provides a communications infrastructure for communications between the host device and the storage device . Network may comprise various components and network elements such as routers switches hubs etc.

The network may support various communications protocols such as Ethernet Internet protocols etc. In addition the network may be implemented as a wired or wireless network or a combination thereof.

Storage device refers to any data storage device capable of providing or sharing access to a file. Storage device may be implemented as a hard disk drive a solid state drive a hybrid drive a direct attached storage device etc.

In the present disclosure by way of example storage device is implemented as a NAS device. As a NAS device storage device provides file level access and shares files with host device over network . The storage device may be implemented using known hardware firmware and software. For example as a NAS device the storage device may be implemented as a specialized computer or appliance configured to store and serve files over the network . In some embodiments the storage device comprises a processor such as an ARM PowerPC or MIPS processor.

Storage media refers to the medium on which the storage device stores data. For example storage media may comprise disks or magnetic media solid state memory optical media etc. As shown the storage device may comprise multiple storage media for purposes of capacity and redundancy. For example as a NAS device the storage device may support various RAID levels.

Controller represents the hardware and software that controls the operations of the storage device. In some embodiments the controller may also comprise one or more other components to supplement its operations such as an on chip RAID controller a memory or disk cache etc. As will be described further below the controller may execute an operating system and a framework .

Operating system represents the software executed by the controller to manage the hardware resources and provide various services such as web services for applications running on the storage device . The controller may support a variety of operating systems such as UNIX LINUX Windows and the like which are known to those skilled in the art. For example in one embodiment the controller may run based on an operating system such as PLAN 9 UNIX LINUX and the like.

In addition in one embodiment the storage device comprises a framework that provides a standardized structure for modules of software such as plugins to implement various features on the storage device . In some embodiments the framework is implemented with native code such as C and thus can support virtually any programming language. In addition the framework supports interoperability between software modules written in either native code such as C and interpreted code such as JAVA For example in one embodiment a JAVA Runtime Environment JRE may be installed on the storage device and execute on the framework to support JAVA based software and plugins.

The embodiments provide a framework that can run on any standard POSIX compliant operating system such as LINUX The embodiments use shared objects to provide software modularity. For example each package i.e. C namespace can be represented by a shared object file in the Executable and Linking Format or Executable and Linkable Format ELF . This allows implementing the dynamic import and export of packages between bundles at runtime with standard dlopen and ELF mechanisms. In some embodiments the framework may support other types of file formats such as Common Object File Format COFF Win32 Object Module Format OMF etc.

Bundles can be implemented as ZIP archives containing a standardized manifest and shared object files representing packages. Without any imports in the manifest shared objects of different bundles may be isolated from each other.

To establish visibility between shared objects the runtime system of the framework adds ELF dependencies to the shared object files after resolving available packages according to specified imports. Thus in some embodiments codesharing functionality is provided by standard ELF mechanisms which are highly mature.

Moreover the embodiments of the framework provide life cycle layer functionality e.g. starting updating and stopping of bundles . For example the framework may implement a service layer with a service registry including support for RFC1960 compliant filters. Finally the embodiments support an event and listener concept by offering framework bundle and service listeners.

In one embodiment the framework employs a message passing interface. For example the framework may employ the BOOST.MPI library. The BOOST.MPI may serve as a wrapper for the message passing interface MPI . The Boost.MPI is a library for message passing in high performance parallel applications. A Boost.MPI program is one or more processes that can communicate either via sending and receiving individual messages point to point communication or by coordinating as a group collective communication . Unlike communication in threaded environments or using a shared memory library. Boost.MPI processes can be spread across many different machines possibly with different operating systems and underlying architectures.

Boost.MPI is a C friendly interface to the standard Message Passing Interface MPI the most popular library interface for high performance distributed computing. MPI defines a library interface available from C Fortran and C for which there are many MPI implementations.

The Boost.MPI library provides an alternative C interface to MPI that better supports modem C development styles including complete support for user defined data types and C Standard Library types arbitrary function objects for collective algorithms and the use of modem C library techniques to maintain maximal efficiency.

In one embodiment the Boost.MPI is configured to support the functionality in MPI 1.1. The abstractions in Boost.MPI allow calls to the underlying C MPI library.

In the embodiments Boost.MPI can be accessed either through its native C bindings or through an alternative such as a PYTHON interface. In another embodiment the framework may utilize a communications protocol such as 9P provided by a PLAN 9 operating system.

The framework provides a general purpose secure and managed framework that supports the deployment of extensible and down loadable applications known as bundles. The framework manages the installation and update of bundles in a dynamic and scalable fashion. To achieve this it manages the dependencies between bundles and services in detail. It provides the bundle developer with the resources necessary to take advantage of the platform independence and dynamic code loading capability in order to easily develop services for small memory devices that can be deployed on a large scale.

In one embodiment the framework enables the storage device to support and implement software defined storage. In particular the framework provides a platform by which the storage device may virtualize its storage capacity and a communications protocol by which to establish virtualized storage on the storage device alone or in cooperation with other storage devices not shown . For example the framework may serve as a platform running on the storage device to deliver block and file storage services. In one embodiment the framework provides an abstraction layer for the underlying hardware of the storage device . Furthermore the framework may provide one or more APIs for various storage management functions such as volume management storage provisioning services RAID configuration etc.

The bundles in bundle layer provide the program code for the plugins requesting various services of the framework and other plugins. In the embodiments the framework defines a unit of modularization called a bundle. A bundle is comprised of binaries and other resources which together can provide functions to end users. Bundles can share bundle capabilities and bundle requirements in a well defined way. Thus in the framework bundles are the entities for deploying applications.

As noted a bundle may be deployed as a ZIP file. ZIP files are used to store applications and their resources in a standard ZIP based file format. A bundle is a ZIP file that contains the resources necessary to provide some functionality. These resources may be HTML files help files icons etc.

The bundle may also contain a manifest file describing the contents of the ZIP file and providing information about the bundle. This file uses headers to specify information that the framework uses to correctly activate a bundle. For example it states dependencies on other resources that must be available to the bundle before it can run.

Once a bundle is started its functionality is provided and services are exported to other bundles installed in the framework . The bundle may comprise various components to determine how the bundle executes. For example a bundle activation policy specifies how the framework should activate the bundle once started. Some embodiments of possible headers are described in the following descriptions below. A bundle activator header specifies the name of the class used to start and stop the bundle. A bundle header may hold a comma separated list of category names.

Another header defines a comma separated list of ZIP file path names or directories inside the bundle containing classes and resources. A version header defines that the bundle has been released according to a serialized version. A native code header contains a specification of native code libraries contained in this bundle.

A symbolic name header specifies a non localizable name for this bundle. The bundle symbolic name together with a version that identifies a unique bundle though it can be installed multiple times in a framework.

An update header specifies a URL where an update for this bundle is available for example in the form of a ZIP file. A dynamic import package header contains a comma separated list of package names that should be dynamically imported when needed.

An export Package header contains a declaration of exported packages. A require bundle header specifies that all exported packages from another bundle must be imported effectively requiring the public interface of another bundle. A require capability header specifies that a bundle requires other bundles to provide a capability.

In one embodiment the execution environment layer establishes the execution environment for running the bundles .

In one embodiment the module layer defines the modularization model. It may have strict rules for sharing between bundles or hiding packages from other bundles. In the module layer since bundles depend on one or more external entities. A bundle can require other bundles an execution environment a specific window system a DLL or shared library an extender a specific peripheral etc. Once a bundle starts it assumes that those dependencies are satisfied. Bundles can express their external dependencies via requirements on capabilities that are provided by the run time environment or other bundles. For example BOOST provides an easy to use interface such as MPI 1.1 and provides the ability to use any version.

Capabilities are attribute sets in a specific name space and requirements are filter expressions that assert the attributes of the capabilities of their corresponding name space. A requirement is satisfied when there is at least one capability that matches the filter. A name space also provides the semantics of matching a requirement to a capability. Bundles can only provide their capabilities when their requirements are satisfied that is requirements are transitive.

In one embodiment the life cycle layer provides a life cycle interface such as an application programming interface API to bundles such as the bundles in bundle layer . This API provides a runtime model for bundles. It defines how bundles are started and stopped as well as how bundles are installed updated and uninstalled. Additionally it provides a comprehensive event API to allow a management bundle to control the operations of the service platform.

In one embodiment the service layer provides a dynamic concise and consistent programming model for bundle developers simplifying the development and deployment of service bundles by de coupling the API used the service s specification from its implementations. The embodiments may support any variety of services including web services web application servers web servers etc. This model allows bundle developers to bind to services only using their interface specifications. The selection of a specific implementation optimized for a specific need or from a specific vendor can thus be deferred to run time.

In the service layer bundles are built around a set of cooperating services available from a shared service registry. Such services are defined semantically by its service interface and implemented as a service object. The service interface can be specified with as few implementation details as possible.

The service object is owned by and runs within a bundle. In one embodiment this bundle must register the service object with the framework service registry so that the service s functionality is available to other bundles under control of the framework.

In one embodiment the framework manages dependencies between the bundle owning the service and the bundles using it. For example when a bundle is stopped all the services registered with the framework by that bundle must be automatically unregistered. The framework maps services to their underlying service objects and provides a simple but powerful query mechanism that enables a bundle to request the services it needs. The framework also provides an event mechanism so that bundles can receive events of services that are registered modified or unregistered.

In one embodiment the security layer defines a secure packaging format as well as the runtime interaction with the framework . In one embodiment the security layer is based on the X.509 v3 digital certificate model. A manifest for approved bundles contains the minimum required capabilities and authorizations. It may be digitally signed using a private key and is authenticated with the public key resident in device firmware. Digitally signing is a security feature that verifies the signer and ensures that the content has not been modified after it was signed by the principal. In one embodiment the digital signing is based on public key cryptography. In one embodiment the plugins running on the framework are signed by a trusted entity such as the manufacturer of the storage device . One or more of a variety of entities may sign the plugins to enhance the security and or authentication of the plugins. In addition a public key of one or more entities may be persistently stored on the storage device . For example a public key may be burned into firmware of the controller . In one embodiment an intermediate certificate installed on the storage device comprises various metadata.

Each bundle object contains a manifest object that provides access to the contents of the manifest file delivered as part of the bundle.

In one embodiment the Manifest Header Factory class is implemented as a singleton. Its purpose is to instantiate specific manifest header objects based on the manifest header name. This class enables polymorphic dispatch and if new header types are required they can be added without changing any existing code. An example is provided below.

When the framework is in the RESOLVED state it is operational but none of its bundles are active. As long as the framework is in this state new bundles can be installed without any installed code interfering. Existing bundles must all be in the INSTALLED state. The framework start event is required to move the framework to the STARTING state.

Alternatively there may be one state where bundles are resolved and another where during shutdown resources previously constructed are destroyed before transitioning bask to the framework INSTALLED state.

In the STARTING state the framework starts all the installed bundles. Once all the bundles have been started the framework transitions to the ACTIVE state.

In the framework ACTIVE state all installed bundles previously recorded as being started must be in the bundle ACTIVE state.

When the framework is shutdown if first enters the framework STOPPING state where all bundles in the ACTIVE state are stopped. The framework then transitions to the RESOLVED state where resources are destroyed.

The bundle has been successfully installed. When a bundle is installed it is stored in the persistent storage of the Framework and remains there until it is explicitly uninstalled. Whether a bundle has been started or stopped must be recorded in the persistent storage of the Framework. A bundle that has been persistently recorded as started must be started whenever the Framework starts until the bundle is explicitly stopped.

All classes that the bundle needs are available. This state indicates that the bundle is either ready to be started or has stopped.

The bundle is being started. The bundle activator.start method will have been called but has not yet returned.

The bundle has been successfully activated and is running. Its bundle activator.start method has been called and has returned.

The bundle is being stopped. The bundle activator.stop method has been called but the stop method has not yet returned.

The service object is owned by and runs within a bundle. This bundle must register the service object with the framework service registry so that the service s functionality is available to other bundles under control of the Framework.

Dependencies between the bundle owning the service and the bundles using it are managed by the framework. The framework maps services to their underlying service objects using the resolver. The framework also provides an event mechanism so that bundles can receive events from services that are registered. illustrates an exemplary services observer object.

The features and attributes of the specific embodiments disclosed above may be combined in different ways to form additional embodiments all of which fall within the scope of the present disclosure. Although the present disclosure provides certain embodiments and applications other embodiments that are apparent to those of ordinary skill in the art including embodiments which do not provide all of the features and advantages set forth herein are also within the scope of this disclosure. Accordingly the scope of the present disclosure is intended to be defined only by reference to the appended claims.

