---

title: Method and apparatus for performing configuration of aeronautical system in compliance with the ARINC 653 standard
abstract: Disclosed herein are a method and apparatus for performing a configuration of an aeronautical system. The apparatus includes a display unit, an intermediate model generation unit, an Extensible Markup Language (XML) conversion unit, and a translator. The display unit display displays a user interface for receiving aeronautical system setting information in compliance with an ARINC 653 standard. The intermediate model generation unit generates an intermediate model of source code based on the setting information received via the user interface. The XML conversion unit creates an XML document by performing XML conversion on the generated intermediate model. The translator generates a source code file in compliance with the ARINC 653 standard by converting the generated XML document.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09032366&OS=09032366&RS=09032366
owner: Electronics and Telecommunications Research Institute
number: 09032366
owner_city: Daejeon
owner_country: KR
publication_date: 20130213
---
This application claims the benefit of Korean Patent Application No. 10 2012 0039710 filed on Apr. 17 2012 which is hereby incorporated by reference in its entirety into this application.

The present invention relates generally to a method and apparatus for performing a configuration of an aeronautical system which facilitate ARINC 653 configurations when writing an aeronautical application program in accordance with the ARINC 653 standard and more particularly to a method and apparatus that facilitate the setting of an aeronautical system using a method and apparatus for receiving setting information via a user interface a method and apparatus for allowing set information to refer to a target source code template and a method and apparatus for generating source code from the setting information.

The fields of industry requiring a high level of safety such as the aeronautical and nuclear power generation industries have the tendency to adhere to existing system architectures. However this tendency leads system management to high cost low efficient structures and therefore a changeover to architectures that use high performance processors is being called for. A high performance processor allows a plurality of application programs to run on a single processor but it is difficult to guarantee safety in that environment. Therefore safety should be basically provided at the level of a platform.

Accordingly for the management of an aeronautical system Aeronautical Radio Inc. established an avionics standard in order to enhance safety and maintain compatibility in aeronautical management.

In particular ARINC 653 stipulates the interface between a real time Operating System OS and application programs running on the real time OS. That is ARINC 653 is a standard for the development of aeronautical software and is a real time OS Application Programming Interface API standard that is needed for integrated modular avionics systems. ARINC 653 stipulates APplication EXecutive APEX which is the interface between an OS and application programs running on the OS.

Therefore using the standard API the dependency on developing hardware can be reduced the portability to other systems can be enhanced and the simultaneous development of aeronautical system applications can be facilitated in the development of avionics software.

ARINC 653 is used in conjunction with the concept of Integrated Modular Avionics IMA . While an existing federated system runs application software on a plurality of processors IMA is based on a platform concept that replaces a plurality of processors with a single high performance processor. A federated system has the disadvantage of each function separately running on one or more processors and the disadvantage of having software that is poor in terms of reuse portability and modularization. IMA has the advantage of enabling a plurality of functions to be performed on a single processor and the advantage of increasing the reuse portability and modularization of software.

However while ARINC 653 system settings play a decisive role in enhancing the portability of aeronautical application software ARINC 653 system settings have the problem of having the risk of erroneous set values leading to a fatal defect.

Accordingly the present invention has been made keeping in mind the above problems occurring in the prior art and an object of the present invention is to provide a method and apparatus that facilitate ARINC 653 configurations.

That is the object of the present invention is to provide an ARINC 653 configuration method and apparatus that provide a user setting interface a code template and code generation rules assisting in system settings when carrying out development in compliance with the ARINC 653 standard thereby improving the convenience and accuracy of ARINC 653 configurations.

In order to accomplish the above object the present invention provides a method of performing a configuration of an aeronautical system in compliance with an ARINC 653 standard via generation of a source code file the method including displaying a user interface and receiving setting information in compliance with the ARINC 653 standard generating an intermediate model of source code based on the received setting information creating an Extensible Markup Language XML document by performing XML conversion on the generated intermediate model and generating a source code file in compliance with the ARINC 653 standard by converting the generated XML document.

In order to accomplish the above object the present invention provides an apparatus for performing a configuration of an aeronautical system including a display unit display configured to display a user interface for receiving aeronautical system setting information in compliance with an ARINC 653 standard an intermediate model generation unit configured to generate an intermediate model of source code based on the setting information received via the user interface an XML conversion unit configured to create an XML document by performing XML conversion on the generated intermediate model and a translator configured to generate a source code file in compliance with the ARINC 653 standard by converting the generated XML document.

Embodiments of the present invention will be described in detail below with reference to the accompanying drawings. Furthermore the terms device and module added to elements in the following description are used merely for ease of preparation of the specification. The terms device and module may be interchangeable and designed in the form of hardware or software.

While the embodiments of the present invention will be described in detail below with reference to the accompanying drawings and the descriptions given in the accompanying drawings the present invention is not limited to the embodiments of the present invention.

The present invention includes user interfaces for ARINC 653 configurations a set source code template and code generation rules for obtaining source code from the user interface as embodiments.

According to this embodiment when information about ARINC 653 configuration values is received via the user interfaces at step S an intermediate model is first generated and then stored in memory at step S. Thereafter XML conversion is performed based on an ARINC 653 XML schema standard and an XML document is created at step S. Thereafter source codes . . . are generated from the XML file via a translator at step S.

According to this embodiment in order to enable a shared input output IO Shared IO function to be set when writing avionics software the ARINC 653 XML schema standard may be extended as shown in . ShareIO List includes one or more shared IO components and each of the shared IO components includes its name Name its physical address PhysicalAddress and its size Size as its attributes. It further includes at least one authority component having a partition ID and access as its attributes.

The first and second code paragraphs and of are portions that are newly defined and added to the existing ARINC 653 XML schema standard according to the embodiment of the present invention and the remaining portion corresponds to the code of the original ARINC 653 XML schema standard that represents the locations at which the added pieces of code are inserted.

According to this embodiment when a user selects a module configuration item from a menu a user setting interface including a menu item for receiving module configuration information a menu item for receiving module scheduling information and a menu item for receiving information about the shared IO component of a module may be displayed.

The menu item for receiving module configuration information may receive information about the name version and ID of a module.

Furthermore the menu item for receiving module scheduling information may receive information about important frames. The menu item for receiving information about the shared IO component of a module may receive information about the name physical address and size of each shared IO component.

According to this embodiment when a user selects a partition item from a setting menu a user setting interface including a menu item for receiving partition attributes information a menu item for receiving sampling port information a menu item for receiving queuing port information a menu item for receiving memory requirement information a menu item for receiving process information a menu item for receiving scheduling information and a menu item for receiving information about a shared IO component may be displayed.

Furthermore according to this embodiment the menu item for receiving partition attributes information may receive information about the ID id name Name critical Critical sys partition SysPartition and entry point EntryPoint of a partition.

The menu item for receiving sampling port information may receive information about a name the maximum message size MaxMessageSize a direction Direction and refresh rate time RefreshRateSecond.

The menu item for receiving queuing port information may receive information about a name Name the maximum message size MaxMessageSize a direction Direction and the maximum number of messages MaxNbMessage.

The menu item for receiving memory requirement information may receive information about a name Name a type Type a direction Direction a size Size a physical address PhysicalAddress and access Access.

The menu item for receiving process information may receive information about a name Name and a stack size StackSize.

The menu item for receiving scheduling information may receive information about an ID ID a window start Window Start a window duration Window Duration and a partition start Part.PreiodStart.

The menu item for receiving information about a shared IO component may receive information about a name Name and access Access.

According to this embodiment when a user selects a channel item from a setting menu a user setting interface including a menu item for receiving channel attributes information a menu item for receiving source information and a menu item for receiving destination information may be displayed.

Furthermore according to this embodiment the menu item for receiving channel attributes information may receive information about the ID and name of a channel.

Furthermore the menu item for receiving source information may receive information about a selection item capable of the selection of a standard partition or a pseudo partition a port name PortName a partition ID PartitionID a partition name PartitionName a physical address PhysicalAddress a name Name and a procedure Procedure.

Furthermore the menu item for receiving information about a destination Destination may receive information about a selection item capable of the selection of a standard partition Standard Partition or a pseudo partition Pseudo Partition a port name PortName a partition ID PartitionID a partition name PartitionName a physical address PhysicalAddress a name Name and a procedure Procedure.

According to this embodiment when a user selects a health monitor setting item from a setting menu a user setting interface including a system health monitor setting page a module health monitor setting page and a partition health monitor setting page may be displayed.

According to this embodiment an ARINC 653 configuration apparatus may include a display unit for displaying a user interface for receiving information about ARINC 653 configurations via an input interface unit an intermediate model generation unit for generating an intermediate model of source code based on the information about settings received via the user interface an XML conversion unit for creating an XML document by performing XML conversion on the generated intermediate model and a translator for generating an ARINC 653 source code file by converting the created XML document. Furthermore the respective units may be controlled via a control unit .

Furthermore the display unit may display a user interface including a menu for receiving at least one piece of setting information that is selected from among module configuration information partition information channel information and health monitor information.

Furthermore the XML conversion unit may use an extended ARINC 653 XML schema standard that enables a shared IO function to be set.

Furthermore the translator may generate the ARINC 653 source code file in a form corresponding to a preset source code template and may create the ARINC 653 source code file in a form corresponding to the preset source code template based on preset source code conversion rules.

A source code template and code generation rules according to an embodiment of the present invention will be described in detail below.

That is in the following description the source code template will be defined along with simple descriptions and rules that convert an XML file in which set values have been stored into source code which complies with the template will also be described. Each of the rules will be described on the assumption that an XML file has been given.

Furthermore in the following description the sign indicates an XML tag and represents a set of corresponding tags in an input XML file.

That is that is used in the following description of rules means a set of all partition tags that is declared in an input XML file. If p this means that p is one of partition tags. p.PartitionIdentifier means the value of a partition ID attribute that belongs to tag p. Furthermore is used as a sign indicative of the number of sets. That is means the number of all tags that are present in a given XML file. Furthermore p. means a set of process tags that belong to partition p. without a prefix means a set of all process tags in an XML file. When conversion rules are defined below data types such as reserved words and arrays for example print if or the like that are used in general high level languages are used. In particular for each means application to all the elements of a corresponding set and some means application to some element s of a corresponding set. Accordingly when a some syntax is applied to a set having a single element the some indicates the corresponding element. That is when for each p . . . it means that the processing within is applied to each element p of a partition tag set. When some s . . . it means that the processing within is applied to some element s s of a source tag. Here since appears once per channel tag s is a singular value. A comma used in a print statement means string join. In order to define a function the form of func function name par1 . . . parN . . . is used. As in a general high level language the returning of a return value is defined using a return syntax. The sign is used for comments.

NEEDS IO is a macro that indicates that IO services must be activated so that some partitions are made to perform IO.

NEEDS PROTS SAMPLING implies that a sampling port service for inter partition communication is included.

CONFIG NB THREADS specifies the number of threads in a system. This represents how many threads can be handled in a kernel. Furthermore the number of threads is computed like this the number of threads in the system 2. Furthermore in this macro two threads that is a kernel thread and an idle thread are added. Here the thread means the process of an ARINC 653 partition.

CONFIG NB PARTITIONS is a macro that specifies the number of partitions that are handled in the kernel.

CONFIG PARTITIONS NTHREADS is a macro that specifies how many threads reside in partitions. This macro is an array. Each index of this array represents a partition. Each value represents the number of threads of a corresponding partition. The following embodiment is a code that represents four partitions that have 2 2 2 and 4 respectively.

CONFIG SCHEDULERING MAJOR FRAME specifies a major frame. The major frame is the time when inter partition ports are flushed. This corresponds to the end of a scheduling cycle. In the following scheduling setting example four slots of 500 ms are declared. A first slot is for a first partition a second slot is for a second partition and so on. The major frame is 2 s.

CONFIG SCHEDULERING NBSLOTS specifies the number of time frames allocated for the execution of partitions.

CONFIG SCHEDULERING SLOTS ALLOCATION specifies the allocation of each slot. It may be declared using an array. Each index of the array represents a partition and each value represents each slot

CONFIG PARTITIONS SME specifies an array with partition sizes in bytes. Each index of an array represents a partition and each value represents the size of the partition. The following example means that first three partitions have a size of 80000 bytes and the last partition has a size of 85000 bytes.

port local identifier t means a type that represent local port IDs declared in an enum . An invalid ID called invalid identifier must always be added to the type. This enum declaration specifies the local ports of a current node and consequently is dependent on the communication requirements of each node.

A global port identifier is specified by declaring an enum type. This enum declaration must be the same on all nodes.

node identifier t is a type that specifies a node identifier. The type contains the value of each node. The value of CONFIG LOCAL NODE must be in this type. This enum declaration is the same on all nodes. An example thereof is as follows 

CONFIG NB SHARED IO is a macro that means the number of shared IOs. In a kernel source file information about set Shared IOs is indicated.

ports identifiers is an array that specifies the global port of each local port. In the following embodiment the first local port of a current node is the global port node1 partition secret outgoing. 

prots nb destinations is an array that specifies the number of destinations for each local port. prots nb destinations specifies how many ports should receive data because a plurality of receptions are possible for a single transmission port.

ports destinations is an array that specifies a local port routing policy. Each value of this array is a pointer to another array. The array that is connected by pointers contains the values of recipient global ports. In the following example a first local port has one recipient. The recipient list is specified with the first elements of the ports destinations array. These elements are the node1 partition secret outgoing deployment destinations array. In this manner it can be seen that a recipient port identifier is node2 partition secert incoming global. 

local ports to global ports is an array that performs the association conversion between each local and global port. The associated global port value is specified for each local port ID. In the following example the first local port corresponds to the global port ID node1 partition secret outgoing global. 

When it is necessary to convert a global port value to a local port an invalid port value is specified if the global port is not on a current node because the definition of this array is different on all nodes. From the following embodiment it can be seen that the three last ports are not located on the current node.

The location of each global port is specified with this array. This array associates each port with a node identifier. In the following example it can be seen that three global ports are located on node 0 and the remaining three global ports are located on node 1.

The kernel must know the kind of each port queuing or sampling . That requirement is specified with a pok ports kind array. In the following example three local ports are all specified as the sampling port type.

When a develop calls port instantiation a port name can be specified. For this reason the kernel must know the name associated with each port. This information is provided by the ports names declaration. This array contains the name of each local port. The following example is an example in which the name of a port is specified.

The inter partition communication ports are dedicated to some partitions. Therefore which partition is allowed to read write which port should be specified. Two arrays are required. This variable is an array that identifies the number of ports allocated for each partition.

This variable is an array that contains global port identifiers allowed for a corresponding partition. In the following example a first partition has one port whose identifier is node1 partition secret outgoing. The number of partitions is three and each of the partitions has one global port.

In order to define shared IO the following header file sharedio.h should be first defined. This header file defines a structure in which set values will be stored.

Furthermore the Kernel conf.c source code represents information about shared IO. Furthermore a number of values of the shared io t type that is the access authorities of the partitions for each shared IO and shared IOs own attributes equal to the number of shared IOs defined in the header file are described in a single array.

In order to represent set values for a health monitor HM the following types should be defined in the header file erroth in advance.

 12 1 Codes representing the states of the system and types representative of errors that may occur in the system

 12 2 Codes representing error levels to be used in a system HM table and error actions to be used in a module HM table and a partition HM table

Furthermore NB ERROR ID and NB SYSTEM STATE used in the codes represent the number of elements of the type system state t and the number of elements of the type error id t . callback represents a user defined callback function. When the error.h header file is declared as described above the following partition table information is declared in the Kernel conf.h header file.

Furthermore in Kernel conf.c the following HM table initiation function is written. In the initiation function all the values of the HM tables are initialized to NONE.

A number of partition HM tables equal to the number of partitions are created. Accordingly a source file having the following assignment form should be created in each partition directory.

The method and apparatus for performing a configuration of an aeronautical system in compliance with the ARINC 653 standard according to the present invention have the advantage of improving the quality of software and the advantage of improving the efficiency of development by reducing the load of a mere navvy s work because the method and apparatus enable ARINC 653 configurations to be easily and rapidly made.

Although the preferred embodiments of the present invention have been disclosed for illustrative purposes those skilled in the art will appreciate that various modifications additions and substitutions are possible without departing from the scope and spirit of the invention as disclosed in the accompanying claims.

