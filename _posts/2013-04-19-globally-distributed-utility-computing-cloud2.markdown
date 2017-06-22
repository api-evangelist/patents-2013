---

title: Globally distributed utility computing cloud
abstract: Teachings of this application include a computing network that may include multiple different data centers and/or server grids which are deployed in different geographic locations. In at least one embodiment, at least some of the server grids may be operable to provide on-demand, grid and/or utility computing resources for hosting various types of distributed applications. In at least one embodiment, a distributed application may be characterized as an application made up of distinct components (e.g., virtual appliances, virtual machines, virtual interfaces, virtual volumes, virtual network connections, etc.) in separate runtime environments. In at least one embodiment, different ones of the distinct components of the distributed application may be hosted or deployed on different platforms (e.g., different servers) connected via a network. In some embodiments, a distributed application may be characterized as an application that runs on two or more networked computers.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09578088&OS=09578088&RS=09578088
owner: CA, Inc.
number: 09578088
owner_city: New York
owner_country: US
publication_date: 20130419
---
This non provisional application is a continuation of U.S. application Ser. No. 12 400 710 filed Mar. 9 2009 and entitled Globally Distributed Utility Computing Cloud now U.S. Pat. No. 8 429 630 which i claims priority to U.S. Provisional Patent Application No. 61 125 334 filed Apr. 23 2008 and U.S. Provisional Patent Application No. 61 068 659 filed Mar. 7 2008 and ii is a continuation in part of U.S. patent application Ser. No. 11 522 050 filed Sep. 15 2006 which claimed priority to U.S. Provisional Patent Application No. 60 717 381 filed Sep. 15 2005 all of which are incorporated herein by reference.

Traditional data centers tend to run a single operating system instance and a single business application on one physical server. This one server one appliance model leads to extremely poor resource utilization. For example it is not uncommon for a significant portion of data center resources to be unused for a majority of the data center s up time. Wasted resources include CPU RAM Storage and Network Bandwidth. Additionally many traditional data centers are typically implemented by combining a heterogenous mix of different servers operating systems applications and data. Consequently deploying managing and reconfiguring software or hardware on physical servers and the data center s network infrastructure is mostly achieved via manual e.g. human labor and it typically very time consuming. Additionally in such data centers the upgrading of servers typically involves a relatively slow and costly process. Further in situations where workloads grow more rapidly than expected and place heavy demands on server resources such traditional data centers face the problem of overutilizing their servers which may result in business continuity being placed at risk.

Various aspects described herein are directed to different methods systems and computer program products relating to a global utility computing service herein referred to a Cloudware which may combine multiple virtualized utility computing grids into a single scalable highly available computing cloud which for example may be used to run a variety of distributed applications such as for example Web 2.0 applications desktop applications etc.

In at least one embodiment a Cloudware network may be implemented as a unified globally distributed computer system having functionality similar to a mainframe computing system. Thus for example in one embodiment all or selected portions of the Cloudware network may be configured or designed to function as a globally distributed mainframe computing cloud wherein the user or client computer systems may be operable as individual terminals for providing interfaces with the mainframe computing cloud.

In at least one embodiment all or selected resources associated with selected computing grids may be aggregated shared and or combined and collectively represented e.g. to end users as a single entity which represents a virtual globally distributed computing system or computing cloud .

In addition to being able to run various types of server type applications such as for example website applications software Web 2.0 applications etc. various embodiments of the Cloudware network may be operable to provide services for running various types desktop computer software such as for example desktop computer operating system software e.g. Linux MS Windows MAC OS Solaris etc. desktop computer applications etc.

According to different embodiments various aspects described herein are directed to different methods systems and computer program products for use in computing networks such as for example on demand grid and or utility computing networks. Examples of at least a portion of the techniques and or related features aspects and or benefits disclosed herein include techniques for migrating virtual appliances from a first server grid to a second server grid via a communication network techniques for migrating distributed applications from a first server grid to a second server grid via a communication network techniques for delivering pre packaged software in virtual appliances to computing systems for use in operating software applications techniques for managing use of virtualized computing resources implemented in a computing network exchange systems for renting or leasing computing resources provided over a computing network techniques for offering via a computing network virtualized computing resources for use in deployment of one or more distributed applications at one or more server grids of a computing network techniques for offering via a computing network distributed application components for use in deployment of one or more distributed applications at one or more server grids of a computing network techniques for implementing exchange of computing resources between computing resource providers and computing resource subscribers of a computing network an the like.

In at least one embodiment different embodiments of computing networks may include multiple different data centers and or server grids which are deployed different geographic locations. In at least one embodiment at least some of the server grids may be operable to provide on demand grid and or utility computing resources for hosting various types of distributed applications. In at least one embodiment a distributed application may be characterized as an application made up of distinct components e.g. virtual appliances virtual machines virtual interfaces virtual volumes virtual network connections etc. in separate runtime environments. In at least one embodiment different ones of the distinct components of the distributed application may be hosted or deployed on different platforms e.g. different servers connected via a network. In some embodiments a distributed application may be characterized as an application that runs on two or more networked computers.

Additional objects features and advantages of the various aspects described herein will become apparent from the following description of its preferred embodiments which description should be taken in conjunction with the accompanying drawings.

One or more different inventions may be described in the present application. Further for one or more of the invention s described herein numerous embodiments may be described in this patent application and are presented for illustrative purposes only. The described embodiments are not intended to be limiting in any sense. One or more of the invention s may be widely applicable to numerous embodiments as is readily apparent from the disclosure. These embodiments are described in sufficient detail to enable those skilled in the art to practice one or more of the invention s and it is to be understood that other embodiments may be utilized and that structural logical software electrical and other changes may be made without departing from the scope of the one or more of the invention s . Accordingly those skilled in the art will recognize that the one or more of the invention s may be practiced with various modifications and alterations. Particular features of one or more of the invention s is described with reference to one or more particular embodiments or figures that form a part of the present disclosure and in which are shown by way of illustration specific embodiments of one or more of the invention s . It should be understood however that such features are not limited to usage in the one or more particular embodiments or figures with reference to which they are described. The present disclosure is neither a literal description of all embodiments of one or more of the invention s nor a listing of features of one or more of the invention s that must be present in all embodiments.

Headings of sections provided in this patent application and the title of this patent application are for convenience only and are not to be taken as limiting the disclosure in any way.

Devices that are in communication with each other need not be in continuous communication with each other unless expressly specified otherwise. In addition devices that are in communication with each other may communicate directly or indirectly through one or more intermediaries.

A description of an embodiment with several components in communication with each other does not imply that all such components are required. To the contrary a variety of optional components are described to illustrate the wide variety of possible embodiments of one or more of the invention s .

Further although process steps method steps algorithms or the like is described in a sequential order such processes methods and algorithms is configured to work in alternate orders. In other words any sequence or order of steps that is described in this patent application does not in and of itself indicate a requirement that the steps be performed in that order. The steps of described processes may be performed in any order practical. Further some steps is performed simultaneously despite being described or implied as occurring non simultaneously e.g. because one step is described after the other step . Moreover the illustration of a process by its depiction in a drawing does not imply that the illustrated process is exclusive of other variations and modifications thereto does not imply that the illustrated process or any of its steps are necessary to one or more of the invention s and does not imply that the illustrated process is preferred.

When a single device or article is described it will be readily apparent that more than one device article whether or not they cooperate is used in place of a single device article. Similarly where more than one device or article is described whether or not they cooperate it will be readily apparent that a single device article is used in place of the more than one device or article.

The functionality and or the features of a device is alternatively embodied by one or more other devices that are not explicitly described as having such functionality features. Thus other embodiments of one or more of the invention s need not include the device itself.

Techniques and mechanisms described herein will sometimes be described in singular form for clarity. However it should be noted that particular embodiments include multiple iterations of a technique or multiple instantiations of a mechanism unless noted otherwise.

U.S. patent application Ser. No. 11 522 050 entitled APPARATUS METHOD AND SYSTEM FOR RAPID DELIVERY OF DISTRIBUTED APPLICATIONS discloses various techniques for visually constructing and rapidly delivering distributed applications. A commercialized grid operating system referred to as AppLogic developed by 3TERA Inc. www.3TERA.com illustrates an example embodiment of one such technique.

It may be be noted that the following discussion of AppLogic and its features is in no way to be construed as an admission of prior art.

According to a specific embodiment AppLogic may be implemented as a grid operating system designed to enable utility computing for web applications. AppLogic may run distributed transactional and streaming applications on grids of commodity hardware. It does not require a SAN or other expensive shared storage and may be open and vendor neutral. Additionally AppLogic may be completely compatible with existing web applications.

Traditionally grid computing has been limited to running computational applications such as business intelligence simulations derivatives trading etc. However the vast majority of Internet services and business applications are not computational instead they process large numbers of relatively small concurrent transactions transactional applications and or deliver content I O intensive applications .

In at least one embodiment AppLogic may be implemented as a grid operating system that may be designed for web applications and may be optimized for transactional and I O intensive workloads. It uses advanced virtualization technologies to ensure complete compatibility with existing operating systems middleware and applications. As a result AppLogic makes it easy to move existing web applications onto a grid without modifications.

Such subsystems provide a foundation for executing and scaling existing web applications on grids of commodity servers.

In at least one embodiment AppLogic may use virtualization to enable each disposable infrastructure component to run on its own copy of one or more selected operating systems and focuses on providing the abstractions and services needed at the distributed application level. This approach results in a system that may be very robust while capable of integrating and running existing software unchanged.

In at least one embodiment AppLogic may manage and or use disposable infrastructure in order to provide within the application the necessary infrastructure which may be preferred to run a given application. For example in one embodiment whenever a given application is started the system may automatically manufacture and assemble the infrastructure required to run it. Once the application is stopped AppLogic may dispose of all or selected infrastructure associated with it. This dramatically simplifies both the construction and the operation of N tier applications building infrastructure for each individual application may be much simpler than building and managing shared infrastructure. More importantly including the infrastructure within each application makes applications self contained and portable and enables AppLogic to instantiate them on demand and migrate them from one grid to another.

In at least one embodiment AppLogic treats the entire N tier application as a single logical entity that can be copied instantiated configured started stopped cloned exported imported etc. As a result once the application has been integrated and tested it can be manipulated with remarkable ease. For example a user can scale an instance of the application from a fraction of a server to dozens of servers simply by defining how much CPU memory and bandwidth may be be allocated to that specific instance. Any number of instances of the same application can be executed simultaneously on the same grid. Multiple unrelated applications can share the grid. Additionally an instance of an application can be cloned together with its state database and content and exported to run on another grid that may be located half way around the world.

According to specific embodiments AppLogic may be operable to provide a set of functions that for running mainstream web applications. Such functions may include but are not limited to one or more of the following or combinations thereof 

In addition AppLogic may be operable to implement a variety of services that enable the building of real world utility computing systems. Examples of such services may include but are not limited to one or more of the following or combinations thereof 

As described in greater detail below the various features functionality provided by AppLogic and or by the disclosures of U.S. patent application Ser. No. 11 522 050 and U.S. patent application Ser. No. 11 024 641 may be leveraged in a manner which enables one to implement a utility computing service herein referred to a Cloudware which may combine multiple virtualized utility computing grids such as for example multiple AppLogic based grids into a single scalable highly available computing cloud that for example may be used to run distributed Web 2.0 applications. In at least one embodiment the term Cloud Computing may be characterized as a pool of abstracted highly scalable and managed computing resources capable of hosting end customer applications.

Generally the cloudware techniques described herein may be implemented on software and or hardware. For example they can be implemented in an operating system kernel in a separate user process in a library package bound into network applications on a specially constructed machine over a utility computing grid on a network interface card etc. In a specific embodiment of this invention the technique described herein may be implemented in software such as an operating system or in an application running on an operating system.

A software or software hardware hybrid implementation of various cloudware related techniques may be implemented on a general purpose programmable machine selectively activated or reconfigured by a computer program stored in memory. Such programmable machine may be a network device designed to handle network traffic such as for example a router a switch and or a server. Such network devices may have multiple network interfaces including frame relay and ISDN interfaces for example. A general architecture for some of these devices will appear from the description given below. In other embodiments some cloudware techniques described herein may be implemented on a general purpose network host machine such as a personal computer server or workstation. Further at least one embodiment may be at least partially implemented on a card e.g. an interface card for a network device or a general purpose computing device.

In one embodiment server system may be suitable for implementing at least some of the cloudware techniques described herein.

In according to one embodiment network device may include a master central processing unit CPU interfaces and a bus e.g. a PCI bus . When acting under the control of appropriate software or firmware the CPU may be responsible for implementing specific functions associated with the functions of a desired network device. For example when configured as a server the CPU may be responsible for analyzing packets encapsulating packets forwarding packets to appropriate network devices instantiating various types of virtual machines virtual interfaces virtual storage volumes virtual appliances etc. The CPU preferably accomplishes at least a portion of these functions under the control of software including an operating system e.g. Linux and any appropriate system software such as for example AppLogic software .

CPU may include one or more processors such as for example one or more processors from the AMD Motorola Intel and or MIPS families of microprocessors. In an alternative embodiment processor may be specially designed hardware for controlling the operations of server system . In a specific embodiment a memory such as non volatile RAM and or ROM also forms part of CPU . However there may be many different ways in which memory could be coupled to the system. Memory block may be used for a variety of purposes such as for example caching and or storing data programming instructions etc.

The interfaces may be typically provided as interface cards sometimes referred to as line cards . Alternatively one or more of the interfaces may be provided as on board interface controllers built into the system motherboard. Generally they control the sending and receiving of data packets over the network and sometimes support other peripherals used with the server system . Among the interfaces that may be provided may be FC interfaces Ethernet interfaces frame relay interfaces cable interfaces DSL interfaces token ring interfaces Infiniband interfaces and the like. In addition various very high speed interfaces may be provided such as fast Ethernet interfaces Gigabit Ethernet interfaces ATM interfaces HSSI interfaces POS interfaces FDDI interfaces ASI interfaces DHEI interfaces and the like. Other interfaces may include one or more wireless interfaces such as for example 802.11 WiFi interfaces 802.15 interfaces including Bluetooth 802.16 WiMax interfaces 802.22 interfaces Cellular standards such as CDMA interfaces CDMA2000 interfaces WCDMA interfaces TDMA interfaces Cellular 3G interfaces etc.

Generally one or more interfaces may include ports appropriate for communication with the appropriate media. In some cases they may also include an independent processor and in some instances volatile RAM. The independent processors may control such communications intensive tasks as packet switching media control and management. By providing separate processors for the communications intensive tasks these interfaces allow the master microprocessor to efficiently perform routing computations network diagnostics security functions etc.

In at least one embodiment some interfaces may be configured or designed to allow the server system to communicate with other network devices associated with various local area network LANs and or wide area networks WANs . Other interfaces may be configured or designed to allow network device to communicate with one or more direct attached storage device s .

Although the system shown in illustrates one specific network device described herein it is by no means the only network device architecture on which one or more embodiments can be implemented. For example an architecture having a single processor that handles communications as well as routing computations etc. may be used. Further other types of interfaces and media could also be used with the network device.

Regardless of network device s configuration it may employ one or more memories or memory modules such as for example memory block which for example may include random access memory RAM configured to store data program instructions for the general purpose network operations and or other information relating to the functionality of the various cloudware techniques described herein. The program instructions may control the operation of an operating system and or one or more applications for example. The memory or memories may also be configured to store data structures and or other specific non program information described herein.

Because such information and program instructions may be employed to implement the systems methods described herein one or more embodiments relates to machine readable media that include program instructions state information etc. for performing various operations described herein. Examples of machine readable storage media include but are not limited to magnetic media such as hard disks floppy disks and magnetic tape optical media such as CD ROM disks magneto optical media such as floptical disks and hardware devices that may be specially configured to store and perform program instructions such as read only memory devices ROM and random access memory RAM . Some embodiments may also be embodied in transmission media such as for example a carrier wave travelling over an appropriate medium such as airwaves optical lines electric lines etc. Examples of program instructions include both machine code such as produced by a compiler and files containing higher level code that may be executed by the computer using an interpreter.

In at least one embodiment each data center may include a respective plurality of server systems herein servers which may be communicatively coupled together via one or more local area networks e.g. LAN1 and or LAN2 . In at least one embodiment at least a portion of the data center servers may include at least a portion of features and or components similar server system of .

According to specific embodiments at least some of the data centers may include several different types of local area networks such as for example a backbone LAN e.g. LAN1 which may be utilized for providing localized communication between various local network elements within a given data center and an internet LAN e.g. LAN2 which for example may be utilized for providing WAN or Internet access to various local network elements within the data center.

In at least one embodiment one or more of the data centers may be operable to host a variety of different types of applications and or other software. Examples of such applications may include but are not limited to one or more of the following or combinations thereof 

Additionally in at least one embodiment one or more of the data centers may be operable to provide various types of database services such as for example data storage database queries data access etc.

Additionally by utilizing virtualization software such as 3TERA s AppLogic one or more of the servers of a given data center may be implemented as a server grid which may be operable to enable utility computing for distributed applications. Additionally in at least one embodiment multiple server grids from different data centers may be linked together to form a virtual global server grid which may be used to facilitate utility computing for distributed applications.

In at least one embodiment a distributed application may be characterize as an application made up of distinct components e.g. virtual appliances virtual machines virtual interfaces virtual volumes virtual network connections etc. in separate runtime environments. In at least one embodiment different ones of the distinct components of the distributed application may be hosted or deployed on different platforms e.g. different servers connected via a network. In some embodiments a distributed application may be characterize as an application that runs on two or more networked computers.

In the example of users e.g. at client systems and or other network devices may be able to access one or more of the data centers via the WAN .

Additionally as explained in greater detail below one or more of the data centers may include hardware software for implementing a Cloudware System which may be used to provide users and or data centers with various types of different functionalities. In at least one embodiment the global network may be collectively referred to as a Cloudware network.

In at least one embodiment one aspect of the various Cloudware techniques described herein may be directed to a Cloudware based utility computing service. For example in one embodiment Cloudware may be implemented as a global service which for example may be operable to provide computing resources to users according to various pricing models such as for example subscription model pay as you go model etc. . In one embodiment the service may be operated by a business entity e.g. 3Tera and the computing resources may be provided by the business entity s 3Tera s hosting partners or other service subscribers.

As used herein the term Nimbus may be used to characterize a first portion of functionality which may be provided by Cloudware.

By way of illustration the following examples may be intended to help illustrate various aspects and were features relating to the various Cloudware related techniques described herein.

In this example it may be assumed that a user navigates the Internet and accesses the Cloudware network via the Cloudware portal. In one embodiment the Cloudware home page may describe what Cloudware is and may offer the user access to log in and or sign up. During the sign up process the user may choose one or more a data center locations for instantiating and running one or more distributed application s selected by the user. In one embodiment the Cloudware services may be offered at different geographic locations such as for example Texas Germany Japan etc.

In one embodiment once the user has logged into his her account one or more customized user dashboard page s see e.g. may be displayed the user. In one embodiment the user dashboard page may include status information e.g. status summary relating to one or more of the user s associated applications. Additionally in at least one embodiment the user dashboard page may include one or more different types of messages sent to the user s account. The user dashboard page may also include a list of the user s applications and or other Cloudware network resources. For example in at least one embodiment the user can also see a catalog of available application templates by expanding an appropriate side bar and or by accessing an expanded dashboard GUI. According to different embodiments the user dashboard page s may include various functionality for allowing the user to perform a variety of operations such as for example one or more of the following or combinations thereof 

In at least one embodiment a user may edit a selected application using an infrastructure editor such as that shown for example in the example of . The user can assign resources to each component appliance of the user s application separately as well as to the application as a whole.

In at least one embodiment a user may be charged for use of different Cloudware services and or Cloudware resources. For example in one embodiment a user may be charged for one or more of the following Cloudware services resources and or combinations thereof 

According to different embodiments the prices fees may be based on many factors and may differ from data center to data center. In some embodiments various services resources may be bundled together. For example in one embodiment different bundles may be offered which include fixed amounts of CPU memory storage e.g. 10 GB per CPU month and or bandwidth e.g. 100 GB per CPU month . In this way for applications that utilize a typical amount of resources the use may only be charged for costs relating to the monthly account fee plus the CPU memory e.g. because most other resources fit in the bundle and don t require a separate charge . Such bundling also allows for better planning of resources at the datacenters that provide the resources.

According to different embodiments the various prices fee structures may also be based on a periodic e.g. monthly yearly etc. payment plan plus overage schema similar to mobile phone plans in the ONE e.g. like T mobile s Individual Max. . In one embodiment the user can pre pay for a certain amount of resources e.g. 10 000 GB hours of RAM and hours of CPU at a lower per resource price for the pre paid resources and be charged a higher price for resources used in excess of the pre paid resources. This payment schema allows for better planning both on the user side and on the datacenter service operator side. It also allows some users e.g. such as those who are able to better predict and pre buy their resource use to obtain prices that may be low enough and closer to the price of dedicated resources while still allowing the flexibility of dynamically adding additional resources on the fly e.g. to handle bursts in resource need utilization should conditions warrant. In other embodiments the periodic plans may be for different time periods e.g. from hours to years as well as simply a pre bought package of resources e.g. 1 million GB hours that can be used over a specified time period e.g. much like a prepaid phone card .

In at least one embodiment the pre pay and bundle approaches may be combined to achieve predictable and competitive pricing for the service s offered.

According to different embodiments Cloudware and or Cloudware Nimbus may provide various features and or functionalities such as for example one or more of the following or combinations thereof 

According to different embodiments Cloudware and or Cloudware Nimbus may also provide other features and or functionalities such as for example one or more of the following or combinations thereof 

For example in one embodiment Cloudware Nimbus may be configured or designed to follow a shared grid design which allows it to support all or selected desired features of Cloudware.

In at least one embodiment Cloudware can be thought of as operating system for the world s first global distributed computer. In this sense it has resources e.g. grids located at various different locations over the world a kernel and a user interface.

More specifically in one embodiment Cloudware Nimbus also referred to herein as Nimbus may include one or more of the following components or combinations thereof 

All or selected components of CUI and KERNEL may be configured or designed as applications running on a core grid. In one embodiment account shells Shell s may be intended to be active only while someone is logged in on the account. In other embodiments account shells may be kept running at all or selected times e.g. with resources paid for by the user s monthly account fees .

At least one example embodiment described herein comprises an application model a visual method and a system for rapid delivery of distributed applications. In at least one embodiment as described herein the phrase inventive system refers to an example embodiment and or to alternative embodiments described or referenced herein.

In at least one embodiment the application model defines several abstractions which taken together make it possible to express the structures and behavior of complete distributed applications. In at least one embodiment those abstractions can be grouped in the following way virtual resources virtual appliances composite appliances catalogs of appliances and applications.

The present invention uses resource virtualization to abstract the underlying hardware system and to make it possible to define the rest of the application in a hardware independent way. At least one embodiment described herein defines various types of virtual resources such as for example virtual machines virtual volumes and virtual network interfaces.

In an example embodiment described herein the hardware system comprises computing and or storage nodes interconnected through a suitably fast network with at least one node acting as a system controller. Each node on the network preferably exposes one or more pools of virtual resources one pool for each resource type. For each resource type the system controller aggregates multiple discrete resource pools exposed by the various nodes in the system into a single distributed resource pool. As a result there is a single system wide resource pool for each type of virtual resource. Virtual resources are allocated created from their respective system pools and carry a system wide identification which makes it possible to access a given instance of a virtual resource in a uniform fashion independent of where the resource is actually located. In at least one embodiment at least some virtual machines may be implemented by a prior art virtual machine management system. illustrates an example embodiment of an architecture of a virtual machine management system in which a virtual machine monitor partitions a physical host into multiple virtual machines such as the virtual machines and and manages the access from virtual devices and to physical devices and . Each virtual machine is capable of booting a general purpose operating system such as and and any other software that it may be configured to run.

Most virtual machine managers virtualize access to at least two types of peripheral devices namely network interfaces and block storage devices. When configuring an individual virtual machine one can specify a set of virtual network devices and a set of virtual storage devices for that virtual machine and define how those virtual devices should be mapped to the actual physical devices of the host. In addition some virtual machine managers make it possible to map a virtual device of a given virtual machine to a logical device network interface or disk volume implemented by an operating system in another virtual machine. Virtual machine managers also allow individual virtual machines to be migrated from one host to another transparently to the software that runs inside the virtual machine. An example of such prior art virtual machine manager is Xen described in Xen .

In the present invention virtual machines are assigned a set of execution attributes that determine the minimum and maximum amounts of processing power memory and network bandwidth that can be allocated to a given instance of a virtual machine as well as to permit or prohibit the migration of the virtual machine.

Virtual storage volumes are logical block devices exposed by one or more hosts on the system and accessible from virtual machines running on the same or on other hosts. Virtual volumes are persistent named objects the size of which is defined at the time of creation and which reside on the system until explicitly destroyed. In an example embodiment a virtual volume defined and exposed by one node is accessible from any node in the system thereby allowing a virtual machine that uses the volume to be migrated freely to any node. One way to implement virtual volumes is by configuring NBD so that each individual virtual volume is stored in a file on one of the hosts shared on the network as an NBD volume and accessed from the other hosts using the NBD client.

In an example embodiment a virtual volume is typically accessed exclusively by a single virtual machine. This makes it possible and desirable to cache volume contents aggressively on the host on which the virtual machine accessing the volume is being executed. Such caching is easily accomplished for example by layering on top of the NBD client a block device driver that uses a file on a local physical disk to store copies of blocks recently accessed by the virtual machine.

Another aspect described herein is the ability to create multiple instances of the same virtual volume. Those are useful whenever there is a need to share a large set of data among multiple virtual machines in such a way as to permit each virtual machine to make relatively small number of modifications to the common set of data for its own use. Instantiable virtual volumes can be implemented by simply replicating the common volume for each virtual machine.

In an example embodiment however an instantiable volume is implemented by a combination of a master virtual volume which is common to all instances and contains the common data and a differential virtual volume for each virtual volume instance which accumulates the modifications made to the specific instance. The master volume and the differential volume are presented to the client virtual machine as a single block device for example by layering an appropriate block device driver over an NBD client that can access both virtual volumes.

In an example embodiment virtual network interfaces are implemented by combining two types of objects a virtual interface factory such as VNFAC1 and a virtual interface instance such as VNI1. The virtual interface factory is preferably attached to each virtual machine and creates one virtual interface instance for each virtual network adapter configured on its virtual machine. The factory configures each virtual interface instance with the MAC address of its respective virtual network adapter thereby allowing the instance to intercept all outbound traffic from that adapter. The virtual interface instance VNI1 is also configured with information sufficient to establish connection with its counterpart the virtual interface instance VNI3 using the physical network available in the hardware system. VNI1 intercepts outgoing traffic from vNIC1 and forwards it to VNI3 which channels the packets into vNIC3 optionally modifying packet headers to support the tunneling abstraction. Traffic in the opposite direction is handled the same way.

Depending on the physical network used virtual wire VC1 can be implemented by tunneling application traffic packets between two virtual network interfaces through a TCP connection UDP datagrams InfiniBand reliable connection or as direct memory to memory transfer whenever both VNI1 and VNI3 happen to be located on the same host all of which is completely transparent to the communicating virtual machines VM1 and VM2. Indeed it is possible to move the virtual wire VC1 from for example a TCP connection over Gigabit Ethernet to a reliable connection over 10 Gigabit InfiniBand on the fly transparently to the communicating virtual machines.

In an example embodiment virtual appliances are created by first defining a virtual appliance class using descriptor similar to 700 and then creating one or more virtual appliance instances that execute on the target system. The class is used as a template for creating instances.

The system next creates a virtual volume instance by either replicating the class volume or by creating a differential volume using the class volume as a master as described above and binds it to the corresponding block device created above.

The virtual machine of the instance is created using the specific values assigned to the execution attributes. In addition the instance is configured with the values of the properties preferably by modifying the configuration files residing on the volume . Since volume is an instance of the master volume the modifications are private to the instance .

The system then proceeds to execute the virtual machine resulting in the booting the operating system and starting the various services .

The inventive process for defining virtual appliance classes and instances makes it possible to separate a the information and configuration that are common to all virtual appliances of a given class such as the operating system and the application service code and the configuration required to make them work together and b the configuration and connection data that are specific for each instance of the virtual appliance based on its role in the distributed application.

Unlike execution attributes the set of which is preferably common to all classes of virtual appliances in practice each class of virtual appliances would have configuration parameters that are specific to the function and the implementation of the class. The present invention provides a mechanism for exposing the desired set of such configuration parameters to be modified by the application designer through a universal property interface modeled after properties of software components such as Microsoft ActiveX controls .

With the inventive property mechanism the designer of a virtual appliance class defines the set of properties preferably by defining the name data type and default value of each property as part of the class descriptor. In addition within the same descriptor the virtual appliance designer specifies the names of one or more configuration files into which the values of the properties need be transferred at the time of instance creation.

In order to visually build structures of virtual appliances the present invention defines the notion of terminals as connection points that represent endpoints for logical interactions between appliance instances. The inventive terminals are designed so that already existing software packages used inside virtual appliances can communicate through terminals without requiring modifications.

With reference to a terminal could be an input such as the input or an output such as the outputs and . An input terminal is a terminal for accepting network connections an output terminal is a terminal for originating network connections. With respect to the flows of requests and data both types of terminals allow bi directional transfers. A terminal preferably comprises a name a virtual network adapter and a virtual network interface.

When an output terminal of one virtual appliance instance is connected to an input terminal of another instance the system creates a virtual wire between their respective virtual network interfaces and assigns virtual IP addresses to both ends of the connection.

With reference to the virtual appliance VA1 has a virtual machine VM1 and an output terminal OUT1 comprising vNIC1 and VNI1. This terminal is connected to the input terminal IN of the virtual appliance VA2 through the virtual wire VC1. Whenever the software running inside VM1 attempts to resolve the name of the output OUT1 as a network host name the inventive system will provide it with the virtual IP address assigned to the opposite end of the virtual wire VC1 which is connected to the terminal IN. This has the effect of binding the network host name OUT1 in VA1 to the IP address of the terminal IN of VA2.

Assuming that in the virtual machine VM2 of the appliance VA2 a software service is listening on a socket for incoming TCP IP connections an attempt to establish a TCP IP connection to host name OUT1 from inside VM1 will result in the connection being established with the software running inside VM2 with all traffic passing through the virtual wire VC1.

Each instance of the inventive virtual appliances has at least one volume from which it boots operating system and other software. These volumes may be provided as part of the class definition of the appliance and instantiated for each virtual appliance instance. In many cases virtual appliances may have additional volumes that are not part of the class definition but are explicitly configured on each instance of the virtual appliance.

With reference to the boot volume may contain software and configuration necessary to boot a Linux operating system and run an Apache web server this volume is part of the class definition and is instantiated for each instance of the appliance . The volume may contain data specific to a given web site for example HTML files images and JavaScripts.

While the class definition for appliance includes a reference to the specific volume it only defines a placeholder for the volume indicating that each instance of the appliance may be explicitly configured with a reference to such volume.

Instantiating the appliance and configuring the instance with a reference to the volume has the effect of producing an instance of an Apache web server that serves the particular web site the content of which is located on volume . In addition defining a property on the appliance through which the appliance can be configured with a directory name on the volume from which it would access the content allows multiple different instances of the appliance to be configured with the same volume but serve different content located in different directories on the volume.

The same pattern can be applied to design a generic J2EE server appliance that can be configured with a volume containing the EJB code packages for a particular application function or a generic database server configured externally with a volume containing a specific database. In fact using the combination of application volume plus directory path property as described in the paragraph above makes it possible to combine static content code and data of the application on a single application volume which makes the application easier to modify and maintain.

The inventive virtual appliances can easily be combined to form structures that perform advanced application functions. Assuming that all required appliance classes already exist defining such structure involves three general steps defining the set of instances providing the desired configuration values for attributes properties and volumes of each instance and defining the connections between their terminals.

Arbitrarily complex structures of virtual appliances can be described in a uniform way by capturing the set of instances that participate in them configuration parameters for each instance and the connections between their terminals. This allows the inventive system to instantiate such structures automatically by interpreting such structure descriptions instantiating virtual appliances configuring them with the provided values and establishing virtual wires through which the appliances could interact.

To assist the design of appliance structures it is preferable that each described instance is assigned a human readable name that identifies the role that such instance plays within the structure.

Since the inventive system can easily instantiate structures of virtual appliances on demand and in a uniform way it is now possible to define a new inventive type of virtual appliances called Composite Appliances. A composite appliance comprises a boundary and an interior. The boundary of a composite appliance is defined in the same way as the boundary of a regular virtual appliance and the interior of a composite appliance comprises a structure of virtual appliances.

Furthermore property of the composite is redirected to the property of the load balancer while the property of the composite is redirected to the properties and of the web servers.

The resulting composite appliance can be used in any structure or application in the place of a web server such as without having to know anything about its interior or even the fact that it is a composite appliance. Unlike the web server it will deliver increased performance and increased resilience to hardware failures since it can operate with one of the web servers or having failed without increased visible complexity in the target application.

An example embodiment of a text descriptor form of a composite appliance e.g. similar to the composite appliance is illustrated for example at FIG. 14 of U.S. Pub. No. 20070078988. The descriptor preferably assigns a name to the appliance class identifies properties terminals and volumes visible on the boundary of the appliance lists the subordinate instances that form the structure of the appliance assigning a name to each instance identifying the class of the instance and configuring each instance by assigning values to one or more properties attributes and or volumes and describes the connections between terminals of subordinate appliances as well as between the terminals defined on the boundary of the composite appliance and terminals of its subordinates.

In particular an example embodiment of a descriptor provides a simple way to redirect a property of the composite appliance to one or more of its subordinates. For example the property cache sz of the web tier composite appliance assembly is redirected to the property cache sz of its subordinates web1 and web2 by means of specifying .cache sz in place of an explicit value in the configuration section of each of those subordinates. This has the effect of configuring each of the web1 and web2 subordinates with the actual value with which the web tier composite is ultimately configured in the target application.

To implement support for composite appliances the inventive system preferably implements a property mechanism that redirects properties of the composite to one or more properties of its subordinate instances by redirecting configuration values set on an instance of a composite appliance to properties of the appropriate subordinates as defined by the interior structure and a terminal mechanism that forwards the configuration information required to create virtual wires received by the terminals of the composite appliance to the terminals of the appropriate subordinates to which they are connected. Such mechanisms can be implemented by the system runtime support similar to XDL or preferably by a structure linker utility that resolves property and terminal forwarding references prior to instantiating the application.

The present invention defines a way to package multiple classes of virtual appliances into class libraries called Catalogs. The catalogs can be used in multiple applications.

Each virtual appliance class preferably comprises a class descriptor and one or more volume images referenced by the descriptor. Each composite appliance class preferably comprises a class descriptor similar to the class descriptor of the regular virtual appliance classes and an interior descriptor that captures the structure that implements the composite.

A catalog preferably comprises a catalog package descriptor that identifies the classes included in the catalog and the class descriptors volume images and interior descriptors of those classes. A catalog can be implemented as a shared directory on a network in which all descriptors and volume images reside. Alternatively a catalog may be exposed through a web or ftp interface on the Internet.

Classes included in catalogs preferably have names that are unique within the catalog. When a class makes a reference to another class contained within the same catalog the name of that class is sufficient to resolve the reference. Whenever a class has a reference to a class belonging to another catalog the name of the catalog is preferably pre pended to the name of the class to form a name that is unique within the inventive system.

The present invention defines a singleton class as a class of which only a single instance may be created. Singletons may not exist outside of the scope of an application and cannot be included in shared catalogs. Each application preferably has at least one singleton the MAIN which includes the top level structure of the application. In addition to the MAIN singleton other singletons can be used to define subsystems of the application that are not intended to be instantiated by design. All singletons in an application preferably reside directly in the application package and outside of the local catalog.

Each application preferably contains one or more virtual volumes that are not directly associated with any virtual appliance class. Such volumes may be used to store application specific content code packages libraries and databases in a layout convenient for access by the operator and are bound by configuration to virtual appliance instances that require access to such data.

The abstractions defined in the application model are sufficient to describe constructively the structure of an arbitrary distributed application without references to the hardware system on which it would execute and without explicit dependencies on the actual software functionality encapsulated in each of the virtual appliances. Moreover the structure and configuration of the application defined in the terms of the application model can be easily expressed through a set of static descriptors using a structure descriptor language such as XML. Various example embodiments of structure description language are illustrated for example in FIG. 7 and FIG. 14 of U.S. Pub. No. 20070078988. In at least one embodiment as a structure description language this language may be semantically equivalent to XML but is less verbose and more suitable for direct editing by humans.

Using this language an arbitrarily complex distributed application can be described in a set of text files such as for example one or more of the following or combinations thereof 1 virtual appliance descriptors 2 composite appliance boundary descriptors 3 composite appliance interior assembly descriptors and 4 package descriptors. In at least one embodiment this set of descriptors together with the images of class volumes and application volumes is sufficient to instantiate and execute the application on any hardware system that supports resource virtualization and other services defined by the present invention.

Although it is possible to practice the present invention by expressing the application design directly in a structure description language using text editing tools one example embodiment of a method of practicing at least one embodiment described herein is to design implement integrate and deploy applications in a visual manner. This takes full advantage of the fact that all abstractions defined in the application model virtual appliances structures of appliances composite appliances and whole applications are easy to visualize and most operations with them are easy to implement as visual operations on a computer user interface.

This section describes an example embodiment of a user interface for visualizing distributed applications and operations on them. The phrase the user can the editor allows the user to and similar phrases throughout this document are used to also denote that the editor has means to or the system has means to as appropriate in context.

The primary functionality of the user interface is implemented by an application editor that makes it possible to create edit and save the descriptor files that comprise a distributed application. In at least one embodiment the editor is preferably implemented as a web browser based user interface allowing access to the editing functionality from any workstation having network connection to the inventive system. An example embodiment of an application editor with a distributed e commerce application displayed on the canvas is illustrated for example in FIG. 20 of U.S. Pub. No. 20070078988.

Even though the editor preferably operates in a browser its user interface preferably looks feels and behaves as a desktop windowed application. The visual layout and behavior of its user interface is preferably similar to stencil and canvas drawing tools similar to Microsoft Visio Kivio for Linux Corel Draw and others and is further specialized to easily draw and connect structures of components with terminals.

In at least one embodiment the property sheet screens and behavior of the editor may be similar to most desktop windowed applications such as Microsoft Windows Explorer property sheets and follow similar visual design guidelines.

At user s option different scopes e.g. composite appliances of the application can be either opened in different browser windows or may replace the content in the same window. The editor preferably supports both visualization options.

Most operations in the editor may be implemented so that they can be applied to a single component or to a selected set that contains multiple components. Such operations preferably include at least drag and move on the canvas cut copy and delete and modifications achieved through property sheets.

The windows displayed by the editor have titles that preferably contain the name of the component being edited the type of editor and the name of the application. It is also preferable that the editor performs basic file locking on descriptor files on which it presently operates similar to the locking schemas employed typically by text editors such as the vi editor in Linux. This allows multiple users to safely view and or edit one and the same application.

The editor preferably does not save any modifications to the application made by the user until the user explicitly chooses a save operation. If while navigating through the application the user tries to close a window or navigate away from the modified component and changes would be lost the editor preferably prompts the user giving him an option to save or discard the changes.

The editor preferably implements a different screen for each type of entity being edited. These screens preferably include a list of available applications a virtual appliance editor a composite appliance boundary editor and an assembly interior editor. In addition the editor preferably allows visual operations between entities such as dragging virtual appliances from a catalog onto the application canvas and vice versa.

The application list is preferably the first screen that the user sees after logging in. This screen preferably contains the list of applications available for editing and provides the ability to select and open for editing or viewing one of these applications. In addition the screen preferably provides ability to execute certain actions over whole applications such as creating a new application deleting a whole application renaming an application etc.

Each entry in the application list preferably includes the name of the application a human readable description and a unique identifier.

The virtual appliance editor also known as the component editor is preferably a property sheet window for editing virtual appliance classes. All information available in this editor is obtained from and stored in the component descriptor file of the edited virtual appliance class. The appearance of the editor is preferably distinctly different from other property sheets especially from the instance settings property sheet of the assembly editor. illustrates an example embodiment of a visual interface of the virtual appliance editor.

The virtual appliance editor preferably displays a preview of the appliance s graphical shape showing the correct size and color as well as the terminals their names and positions. It is preferred that the editor opens in read only mode for all appliance classes except singletons included directly in the application package.

The virtual appliance editor preferably comprises the following sections with each section implemented as a separate property sheet tab a general section an interfaces section a volumes section a resources section a properties section and a configuration files section.

The general tab preferably contains common class attributes as well as some visual attributes. An example of the fields available through this section includes the class name a description operating system type whether instances of this class can be migrated live from one server to another as well as visual shape size and color.

The interfaces tab preferably allows the user to view edit and create the set of virtual appliance interfaces including both terminals and virtual network adapters. It preferably displays a list of terminals showing for each terminal its name direction input or output communication protocol for connections on that terminal and a mandatory attribute that defines whether the terminal may be connected in order for the appliance to operate. For raw virtual network adapters those that are not associated with a terminal the editor may allow defining and editing the MAC address.

Using the interfaces tab the users can add delete or rename terminals in the list. The terminal s position such as the side of the component s shape on which the terminal appears and its order among other terminals on that side may be editable as well. The editor preferably allows the user to insert gaps between terminals so that terminals can be visually grouped as convenient.

The volumes tab preferably defines the set of volumes to be used by instances of the virtual appliance class being edited. The list includes both class volumes which are to be instantiated with the appliance and placeholders for application volumes which are to be parameterized on each instance of the appliance. For each volume the editor preferably allows the user to define a logical name that determines the role of the volume within the appliance a mount path under which this volume will be visible to the software inside of the appliance and a boot attribute defining whether this volume is the boot volume for the appliance. The user can add delete and rename volumes in the volume list.

In addition the volumes tab preferably allows the user to define a variety of attributes for each volume. Such attributes may include class vs. placeholder a mandatory attribute for placeholders that defines whether the appliance may be parameterized with a valid volume in order to operate. In addition the editor preferably makes it possible to restrict the access of the appliance instances to a given volume to read only access as well as to express constraints such as high bandwidth access and local access only that allow the inventive system to optimize the placement of the volumes and virtual machines that comprise appliance instances.

The resources tab preferably allows the user to set minimum and maximum values for each hardware resource required to execute an instance of the virtual appliance. Such resources include at least CPU time memory size and network bandwidth. The system can use these values to ensure that sufficient resources are available for each virtual appliance instance as well as to prevent any particular instance from depriving the rest of the executing instances of any particular resource.

The property tab preferably allows the user to define view and edit the list of properties made available on each instance of the edited virtual appliance class. It preferably contains a list of properties specifying for each property its name data type whether setting this property is preferred on each instance a default value and optionally constraints such as range for integer properties maximum length for strings and enumerated list of allowed values. The user can add delete and rename properties on the list as well as edit any of the attributes of each property.

The configuration files tab preferably lists the set of configuration files contained within the virtual appliance to which property values are to be applied at instantiation. For each configuration file the tab preferably includes the logical name of the volume as defined in the volumes tab on which the file is to be found the path of the file relative to the specified volume and additional information if needed such as special character escaping rules for that file. The user preferably can add and delete configuration files and edit the information for each file.

The boundary editor is preferably a property sheet that allows the user to define the boundary and other elements of a composite appliance that are not related to appliance s interior structure. This editor is visually and semantically similar to the virtual appliance editor except that it operates on composite appliances.

The editor preferably operates in read only mode for all classes except singletons included directly in the application package and is preferably divided into several sections tabs .

The general tab contains common class attributes as well as visual attributes. Those preferably include the class name a description shape color size and style.

The terminals tab preferably allows the user to view define and edit the set of terminals exposed on the boundary of the composite appliance. It preferably contains a list of terminals including for each terminal its name direction input or output and a mandatory attribute. The user can add delete and rename terminals as well as edit the data related to each terminal. The terminal s visual position on the appliance shape such as side and order of terminals can be edited as well gap insertion is preferably supported if it is supported for virtual appliances.

The properties tab preferably allows the user to define the set of properties that is to be exposed on the boundary of the composite appliance. It preferably includes a list of properties defining for each property name default value and an optional mandatory attribute. The user can add delete and rename properties as well as edit data related to each property.

The volumes tab allows the user to define a set of volume placeholders that can be configured with references to application volumes on the boundary of the instances of the edited composite appliance class. For each volume placeholder the tab preferably provides name an optional mandatory attribute as well as other attributes such as shared or read only. As in other tabs of this editor the user can add rename delete or edit list elements.

The assembly editor is the main screen of the application editor. It allows users to view and edit the interior structures of composite appliances. This includes adding or removing subordinate instances configuring each of those instances and creating the structure by interconnecting their terminals. In addition the assembly editor preferably supports the ability to customize virtual appliance classes in a convenient visual way. To achieve these functions the assembly editor preferably provides the means for opening the other editors such as the virtual appliance editor the boundary editor etc.

In at least one embodiment the assembly editor provides a drawing canvas on which appliance instances virtual or composite are configured and assembled into structures. The editor preferably includes one or more palettes that make it possible to select the classes of virtual appliances to be included in the structure from a catalog recycle bin etc.

To create an instance the user preferably selects an appliance class from a palette and drags it onto the canvas. If the selected class is a virtual or composite appliance the editor will create an instance of that class. If a special blank class is selected the editor will preferably create a new singleton class and place it directly in the application package as well as create an instance of this class. In addition the editor will generate automatically a name for the instance and or optionally for the singleton so that the name is unique within the structure being edited.

The editor preferably displays each instance as a rectangular shape with attached terminals. The color style and size of the shape as well as the positions of the terminals are as specified when defining the virtual appliance class to which this instance belongs.

For each instance the editor preferably displays the class name within the body of the instance the instance name outside of the body the name and direction of each terminal within the terminal and zero or more selected attributes that apply to this appliance.

Once an instance is created on the canvas the editor allows the user to drag it freely around the canvas changing its position and preferably preventing the user from placing it directly over another instance.

The terminals of the instance can be connected by preferably clicking on one of the terminals and dragging a connection to the other terminal. In at least one embodiment the editor preferably allows output terminals to be connected only to input terminals and input terminals only to output terminals. Each output is preferably connected to only one input while many outputs can be connected to the same input.

Whenever multiple outputs are connected to the same input the resulting connections may be joined visually as close to the outputs as possible to prevent clutter.

The editor routes connections automatically by default and preferably allows the user to re route any connection manually by dragging moveable lines and corners of connections and by adding or deleting line segments.

The editor allows the user to select one or more instances and apply various operations to them. Whenever a selected instance or group is moved their connections are preserved as much as possible this includes preserving all connections between the selected instances and re routing any connections from a selected instance to a non selected instance.

An example embodiment of the interior of a composite appliance Web Tier opened in the assembly editor is illustrated for example in FIG. 17 of U.S. Pub. No. 20070078988. In at least one embodiment the terminals of the composite appliance may be visualized on the canvas as small pseudo appliances with one terminal each indicating the name and direction of the respective terminal and can be connected to the interior structure.

In addition to instances terminals and connections the user can preferably add text box annotations on any place on the canvas. The editor will preserve such annotations as comments in the structure describing the appliance interior.

The editor preferably allows the following operations over selected appliance instances cut copy paste view edit class boundary view edit class interior for composite appliances configure instance and branch class. Those operations may be selected by a right button click on the instance shape which opens a context menu and selecting the desired operation from the menu. The semantics of the cut copy and paste operations are the same as in any windowed editor viewing class boundaries and or interiors is accomplished by starting the appropriate editor over the class of the selected instance. Configuring instances is accomplished by displaying a special instance settings property sheet that is preferably part of the assembly editor and displays and modifies data within the same structure descriptor.

The visual editor preferably provides a set of palettes one for each catalog made available to the user. The user is preferably able to select a subset of catalogs to be displayed at any time. Each palette displays an icon for each appliance class found in the respective catalog with the icon visually resembling the shape of the component as much as possible. The icons displayed may be grouped by category of appliance they represent such as servers infrastructure gateways load balancers etc.

Dragging an icon from the catalog onto the canvas preferably has the effect of including a new instance of the selected class into the edited structure. Dragging a special blank appliance or a blank composite appliance from the palette preferably creates a singleton class included directly in the application package and an instance of this class included into the edited structure.

A right button mouse click on an icon in the catalog preferably opens a menu that gives the user options such as deleting or renaming the class creating an instance of the class same as drag to canvas copying the class moving the class to another catalog or converting it to a singleton viewing the appliance boundary and interior if the appliance is a composite . In addition double clicking on an appliance icon in the catalog palette preferably opens up the respective editor to display detailed boundary information about that class.

Branching a class involves creating a copy of the class of the selected instance designating such copy as a singleton class placing the singleton class directly in the application package and changing the class of the selected instance to the new singleton class. Branching creates a tightly coupled pair comprising an instance and a singleton class which can be edited as single entity.

To add a new class to a catalog the user preferably converts a singleton into a class. To do this the user selects the instance of the singleton on the canvas and drags it into the desired catalog s palette. The editor then creates the appropriate class within the catalog structure copies and or moves all class data and volumes into the catalog and preferably deletes the singleton. In addition the instance that was selected to initiate the operation is preferably removed from the structure.

The instance settings property sheet allows users to configure a subordinate instance in a structure of virtual appliances. Unlike in appliance and boundary editors in which changes apply to the all future instances of the edited class instance settings apply only to the selected instance. Instance settings override any default values specified in the class.

In any place within the instance settings property sheet where the user is expected to input a specific value the editor allows the user to specify a reference to a property of the composite that contains that instance. If such reference is specified the system will substitute it at the appropriate time with a value assigned directly or indirectly to the respective property of the composite. This makes it possible to redirect a property attribute or volume of the composite instance to one or more properties attributes or volumes of its subordinate appliances.

The attributes tab contains the instance name as well as a set of attributes that apply to that instance. The tab preferably includes the class name and may include optional attributes such as a start order migrateable standby etc.

The resources tab preferably makes it possible to override the resource constraints specified in the class of the virtual appliance to further reduce the range of resources available to the particular instance if desirable.

FIG. 18 of U.S. Pub. No. 20070078988 illustrates an example embodiment of a design of the instance settings volumes tab. It allows the user to configure the instance so that it can access a specific application volume. To achieve this the instance is preferably configured with the name of the desired application volume.

FIG. 19 of U.S. Pub. No. 20070078988 illustrates an example embodiment of a design of the instance settings properties tab. It allows the user to set property values that configure and specialize the instance for its role within the structure. For each property defined on the class the user may view the default value if any and override it if desired. In addition the user may select one or more properties and their values to be displayed by the editor in the vicinity of the instance s shape on the canvas thereby improving the readability of the diagram.

In addition to editing various sub entities within the application the visual editor preferably allows users to define application level configuration parameters that can be used to modify the behavior of the application as a whole bind it to a particular hardware configuration etc.

The general tab describes the application as a whole including name version human readable description comments unique ID etc.

The application resources tab defines a subset of the hardware resources within the inventive system that are to be assigned to the given application. The tab preferably contains two general groups of fields one for hardware resources and the other for IP network settings.

Hardware resources may be specified in terms of number of CPUs total amount of memory and bandwidth to be committed to the application. In some embodiments of the system it may be preferable to specify the hardware resources in an alternative fashion such as total number of servers assigned to the application or a list of specific servers designated to run it.

The IP network settings group preferably defines the range of IP addresses to be allocated for internal use by the inventive system when running this application.

The property tab is preferably similar to the instance settings property tab discussed above and makes it possible to configure the application as a whole in a manner similar to configuring any other composite appliance.

The application volumes tab preferably enables the user to create and manage a set of application volumes associated with the given application assign their names and sizes and configure the application in using them. The user can add rename and delete volumes and assign reference to volumes to volume placeholders exposed on the boundary of the application in a manner preferably similar to configuring any other composite appliance.

The present invention teaches a visual method for rapid design construction and deployment of distributed applications using the application model and visual interface described herein. In this section we will discuss in more detail the basic steps required for practicing this method. Those steps comprise creating a virtual appliance assembling a composite appliance from existing appliances creating a new appliance class in a catalog and creating the application. In addition this section covers related topics such as troubleshooting applications designed with the inventive system and monitoring their execution.

To create a new virtual appliance using the inventive system the user preferably opens the application editor and drags a blank virtual appliance onto the editor canvas. This creates a new automatically named singleton class and an instance of that class. The user then selects the new instance and opens the virtual appliance editor on its class.

Using the virtual appliance editor the user defines the new virtual appliance by specifying appropriate class name and a set of properties terminals interfaces and volumes. In addition the user selects appropriate values for hardware resources properties and execution attributes that will be used as defaults for new instances of this class.

Through the application settings screen the user creates one or more application volumes that will be later used as class volumes for the new virtual appliance and then installs or copies the desired combination of operating system add on software packages and configuration data for the appliance. The user further configures the various software packages that may operate together inside the appliance in accordance with their documentation. In addition the user selects configuration files and parameters within them that are to be exposed for configuring the virtual appliance and maps them to properties using one of the property mechanism methods described herein.

Further the user configures the software packages within the appliance to use the names of the terminals defined on the boundary of the appliance. If the appliance does not have multiple input terminals with the same protocol the software within the appliance is configured to listen for incoming network sessions in the conventional way e.g. by port number only . If two or more input terminals are defined with the same protocol for each such terminal the user has to configure the software so that it will listen for network sessions using the name of the desired terminal as a network host name.

For output terminals the user configures the appropriate software packages as if the name of the respective output terminal was the name of a remote network host to which the package is expected to establish a communication session.

Once configured the volumes are bound to the appliance being created by opening the instance settings property sheet on the appliance instance and configuring each volume placeholder with the name of its respective application volume.

To create a composite appliance the user drags a blank composite appliance onto the editor canvas thereby creating a singleton composite class with an automatically generated name and an instance of that class. The user then selects the newly created instance and opens the boundary editor on its class.

Using the boundary editor the user defines the new class by selecting an appropriate name for it and defining its terminals properties and volume placeholders as desired.

The user then proceeds to edit the interior of the new class by selecting the instance and choosing the edit interior option from the context menu. A new editor window opens providing a canvas for defining the interior on which the terminals of the composite have already been placed.

The user creates the desired structure by a adding appliance instances by selecting appropriate appliance classes from a catalog and dragging them on the canvas b configuring each instance through the instance settings property sheet and c connecting the terminals of the instances and the terminals of the composite into the desired structure. Note that within the interior an input terminal of the composite behaves as an output e.g. it is connectable to exactly one input of a subordinate appliance and an output terminal of the composite behaves as an input e.g. multiple outputs of various subordinates may be connected to it .

Wherever desired the user redirects properties and or volumes of the composite to properties and or volumes of one or more subordinates by referencing them in configuration of the instance settings of the subordinates as described above.

Once a virtual appliance or a composite appliance is created on the canvas it can be dragged onto one of the available catalogs to create a catalog class from which multiple instances can be created. The act of dragging the appliance onto the catalog converts the singleton into an identically named catalog class includes that class in the package of the desired catalog and deletes the instance used to create and edit the new appliance.

In the process of creating a new catalog class application volumes that are configured as class volumes of the new class are converted into instantiable class volumes by the inventive system and removed from the list of application volumes accessible by the user.

The inventive system preferably implements an application as a combination of a package descriptor a singleton composite appliance named MAIN and an optional catalog. Assuming that all required appliance classes already exist in one or more available catalogs assembling the application is equivalent to creating the interior of the MAIN composite.

The MAIN composite preferably has no terminals since the application is expected to interact with the rest of the computer network through one or more virtual network adapters defined on one or more instances of virtual appliances included in the application. Such interactions may be carried out by means of standardized input and output gateway appliances thereby isolating most of the application from having to know the details and settings of such interactions.

The act of creating an application in general comprises an iterative process that combines top down decomposition of the desired functionality into subsystems which are expressed as composite appliances with the bottom up assembly of subsystems and other composites from available appliance classes. In the process it may be discovered that creating a new virtual appliance class is required to best express a sub function of a given subsystem in this case the appropriate class is created either from scratch or more often by branching and customizing an existing appliance class.

The design of the new application is complete when the MAIN singleton is fully assembled and all subordinates included in it exist and are properly configured. As soon as this stage is achieved the application is immediately ready for execution on a target hardware system the set of descriptors and volumes that comprises the application designed as the present invention teaches contains all necessary software packages data configuration parameters and structural information required to create a running instance of the application under the control of the inventive system.

It is important to realize that the user does not have to wait until the target application is fully elaborated before running it any subset of the application being it a single virtual appliance an incomplete structure of virtual appliances a finished application subsystem such as a database cluster or a web tier or an application that is not completely configured can be started on the inventive system subject only to the software packages included in the existing virtual appliances having sufficient configuration and connectivity to operate.

Considering that the application is a hierarchical structure of composite appliances and is itself a composite appliance it is beneficial to design the application so that any properties volumes or attributes that may be desired to change when deploying the application on different systems and locations are exposed as properties volumes and attributes of the application e.g. of the MAIN composite . This makes the whole application no matter how large and complex configurable and deployable as easy as a single virtual appliance.

When executing an application built using the present invention the inventive system constructs the running image of the application from virtual resources using structural and configuration information captured in virtual appliances and composites. This way of deploying and executing applications has a significant added benefit in that all structural information captured throughout design and development is available to the system at run time. This makes it easy to correlate monitoring data captured as the application runs with the logical structure of the application and significantly simplifies the process of troubleshooting and tuning applications and monitoring the execution in production by making it intuitive.

The inventive system also provides easy means to define thresholds of normal behavior on appliance instances and connections and detect and display abnormal behaviors on the visual layout of the application. This enables the user to formulate and execute corrective actions directly in the terms of the application logic rather than having to continuously translate such actions into the terms of the physical infrastructure on which the application executes.

One of the problems that is exceedingly difficult to resolve within the prior art systems is the ability to capture and manage the full set of configuration and other changes affected on a running application the effect of which is that the user is often unable to roll back to a last known good state of the application. This problem becomes especially acute when the application is large enough to require multiple people to administer tune and troubleshoot the system. The existing approach to solving this problem is to introduce restrictive processes and complex change management systems which often aggravate the situation by adding significant complexity.

The present invention enables a simple and effective approach to change management in distributed applications by making it possible to apply technology that is well understood and proven over decades of use to the problem. The inventive system captures the complete structure and configuration of the application including installed images of operating systems application software configuration files network settings scripts and user data sufficient to execute the application on any instance of the inventive system and retains this data in the form of collection of text files descriptors and logical volume images. This makes it possible to use a commercial version control system developed for use in software code development such as ClearCase or Microsoft Visual SourceSafe to effectively implement version control of distributed applications during design and development as well as for change management in the later stages of application delivery and deployment.

The disclosed visual method makes it possible to construct distributed applications of arbitrary complexity by visually defining a model of the target application that is simple and yet sufficiently complete to allow the inventive system to deploy and execute the application on a variety of target hardware without any further human intervention. This greatly simplifies all activities related to designing constructing deploying and managing large distributed applications by eliminating the need for constant manual translation from application logic to hardware configuration and vice versa.

The present invention includes a system that implements the necessary support for the abstractions defined in the application model and for practicing the visual method. In addition the system provides runtime support for deploying executing monitoring and managing applications constructed as the present invention teaches.

In another embodiment described herein all elements of the inventive system reside on a single server such as and use the storage attached directly to the server.

Servers and blades are configured to boot a suitable host operating system and a virtual machine manager or which enables them to be partitioned into multiple virtual machines . In addition those servers are configured to execute a virtual resource manager or which interacts with the controller . The inventive virtual resource manager implements support for virtual network interfaces and and for virtual storage volumes and sufficient to implement the application model. In addition each virtual resource manager controls its local virtual machine manager and extends its functionality as may be necessary to provide sufficient support for the application model.

In the configuration shown for the server the virtual resource manager makes the hardware resources of the server available to the controller as three distinct pools of virtual resources including virtual machines virtual network interfaces and virtual volumes . The server blade has no storage and so the virtual resource manager is configured to make its resources available to the controller as two pools of virtual resources virtual machines and virtual network interfaces .

Unlike servers and blades the servers are configured to provide access only to the storage resources of the SAN . Accordingly they do not have a virtual machine manager and their local virtual resource manager interfaces with a suitable SAN management system to provide a pool of virtual volumes and which are physically located on the SAN and accessed via a FibreChannel interface .

The controller can access all servers and over the network and can therefore create control and access virtual machines virtual volumes and virtual network interfaces as applicable on any and all of the above servers. The controller includes a resource aggregator an execution control module and a user interface system .

The resource aggregator provides unified access to the virtual resources exposed by the servers and creating thereby three uniform distributed and scalable pools of virtual resources one for each type of resource. The resource aggregator preferably abstracts the actual location e.g. server on which each instance of a virtual resource resides from the rest of the controller and also preferably manages the creation of such resources determining on which server to create each particular resource instance and interacting with that server to this purpose.

The execution control module uses the resource aggregator to create access and manage virtual resources. It provides runtime support for the application model allowing virtual appliances to be instantiated configured interconnected started executed migrated from one server to another and monitored. In addition the execution control module provides the necessary support for composite appliances and applications.

During the execution of an application the execution control module may further interface with external software making such application available for management by conventional data center management software and forwarding alerts and other events related to the running application to such software.

The user interface system has two key functions a it implements command line and visual interface to the execution control module and the rest of the inventive system and b it implements the visual user interface editors for practicing the method taught by the present invention.

The Cloudware User Interface subsystem provides interface to the Cloudware service. The interface may be both for human users and for programmatic use.

As shown in the example of the CUI subsystem comprises the portal application e.g. Portal the account shells e.g. Shell s and the API gateway s e.g. API s .

In at least one embodiment the Portal application provides the common non account specific portion of the Cloudware web site. Its functionality comprises service home page new user registration account creation and management billing service login forums documentation support helpdesk corporate site and brochures etc. In addition the portal application may also be responsible for activating account shells for example either at account creation and during login. Portal makes Shell s instances and may also make instances of API s .

In at least one embodiment the Shell s account shell provides the account user interface including list of applications infrastructure editor monitoring application and appliance control etc pretty much the current grid controller user interface of AppLogic . The Shell s application may be named this way due to its similarity to a shell desktop in a traditional computer operating system this may be the face of the global computer for any particular user. The Shell s application may be designed to be instantiated per account one instance per account other options obviously include one Shell s app for the service maybe scalable as well as one Shell s instance per user login like a shell in a traditional OS . Shell s ideally provides both GUI and text based shell.

In at least one embodiment the API s gateway provides programmatic access to Cloudware services. It provides more or less the same set of services and functions as the Shell s allowing programmatic access control to the same functions that humans use the Shell s shell to achieve. The API s gateway provides a web services interface e.g. via SOAP .

In at least one embodiment the CUI subsystem may also be responsible to ensure a secure and authenticated channel between arbitrarily located end user e.g. anywhere on the Internet or in a organizational network and the Cloudware service. In one embodiment the intended measures may include but are not limited to one or more of the following or combinations thereof 

In at least one embodiment the CUI subsystem may not require persistent state except possibly cached data . It also may not drive composite operations for example application migration may be handled by the kernel with the CUI initiating and then reporting progress of the operation. The Cloudware service may be fully operational if the CUI subsystem may be inoperative for short periods of time for example everything may work except it may not be controllable e.g. temporarily .

In at least one embodiment the CUI subsystem works as a set of AppLogic applications on one or more grids in one or more data centers.

In at least one embodiment the Cloudware Kernel subsystem may provide core controlling functionality of Cloudware. For example in one embodiment it may be responsible for performing all or selected operations that define various Cloudware services resources.

As shown in the example of the KERNEL subsystem comprises the service controller e.g. Controller metering system e.g. METER authentication service e.g. Authentication data center manager e.g. DC Manager and repository e.g. Repository .

In at least one embodiment the Repository stores all or selected metadata for the Cloudware service such as for example one or more of the following or combinations thereof account structure users and their permissions applications catalogs etc. It may be a hierarchical repository organized by entity as described elsewhere in the Cloudware docs. Repository may be highly available and replicated geographically for disaster recovery. The Cloudware service can survive Repository restart with only temporary loss of controlling services and without impacting running applications this may also be true for other subsystems and or components of Cloudware described herein . In at least one embodiment the Repository may be implemented using an lighweight directory access protocol LDAP implementation such as OpenLDAP at www.openldap.org including its directory replication mechanisms for achieving redundancy and geographic distribution.

In at least one embodiment the DC Manager may be responsible to manage the set of data centers and grids in them as well as their relationships associated resources such as IP addresses and metadata e.g. resource prices and costs . It aggregates the multiple data centers and grids and provides a secure and reliable channel to them. All or selected interactions except volume transfers may pass through the DC Manager. DC Manager may be configured or designed to not store persistent data. In such embodiments DC Manager may use the Repository for all or selected storage needs including storage of transient states .

In at least one embodiment the metering system may be responsible for tracking all or selected resource usage such as for example one or more of the following or combinations thereof CPU time memory storage bandwidth licensed appliances etc. The metering system may also be operable to timely e.g. real time report resource usage information to billing system .

In at least one embodiment the authentication service may be responsible for authenticating users as well as Cloudware entities. In one embodiment authentication provides authentication services for logging in users. Optionally it also manages the user and account relationships in a directory service. Further Authentication provides secure authentication between Cloudware subsystems and components including between components that may be geographically distributed and may need to communicate securely over public insecure networks. Authentication allows for maintaining a single unified user login across all or selected content and services of AppLogic so that users authenticate once and obtain access to all or selected aspects of their accounts such as for example applications billing forums helpdesk etc.

In at least one embodiment the service controller may be responsible for controlling various aspects relating to Cloudware resources services information. In one embodiment it may implements all or selected operations and may provide the abstraction entities defined by Cloudware. It may use other services to perform their appropriate functions and may also use grids to operate and or manage applications.

As shown in the example of Controller comprises various subsystems such as for example one or more of the following or combinations thereof 

In at least one embodiment the KERNEL subsystem may be highly available and replicated for disaster recovery. The applications running on the Cloudware service may be fully operational if the KERNEL is down for short periods of time everything may work except it may not be controllable and some aspects of high availability may be delayed until the KERNEL subsystem is restored. In one embodiment the KERNEL subsystem works as a set of AppLogic applications on one or more grids in one or more data centers.

Cloudware preferably operates end user applications on a set of grids e.g. AppLogic based utility computing grids located in multiple data centers. Each data center may have one or more grids possibly with different dimensions e.g. ratio of CPU cores to memory size of storage per server etc. 

In addition to using grids for operating the end user applications Cloudware may use grids to host the Cloudware specific components themselves such as for example the CUI and KERNEL subsystems of the Cloudware System . It may also be possible to operate the external services or portion thereof on grids. In one embodiment the grids used by Cloudware and or Cloudware System for its operation may not be among the grids that Cloudware would schedule end user applications. This allows the Cloudware service to be maintained with minimal impact on the end user applications.

Cloudware may eventually operate grids running different versions of utilizing computing grid software such as AppLogic . It may also be possible and likely to have grids with different versions in the same data center as well as to have a single account that runs applications on grids with different versions concurrently e.g. one app on AppLogic 2.5 another on 2.6 .

To arrange for such flexibility Cloudware components use loose coupling for their interfaces especially for the interface between the Cloudware KERNEL and the grids on which user applications operate. In one embodiment this interface may be implemented using Simple Object Access Protocol SOAP based functionality and may fully utilize the flexibility provided by SOAP including for example optional fields must understand attributes forwarders etc. .

In at least one embodiment the Cloudware System may include and or utilize other external services to provide functions which while not specific to Cloudware may be preferable for its operation. Examples of such other services include one or more of the following or combinations thereof which 

In at least one embodiment the Cloudware System may include and or may be communicatively coupled to a licensing management system not shown which for example may be operable to perform one or more of the following functions 

For example in one example situation where a user has designed a distributed application which includes use of a virtual appliance which has been published by a third party publisher and the user desires to acquire a license from the third party publisher in order to access additional features of the virtual appliance the Cloudware System may be operable to acquire e.g. at the request of the user the desired license s from the licensing entity e.g. third party publisher on behalf of the user and may be operable to coordinate and or manage all billing payment activities e.g. relating to the acquired license for the virtual appliance without the user ever having to deal directly with the third party publisher licensing entity. Additionally the Cloudware System may further be operable to track and report e.g. to the user and or third party licensing entity usage information relating to the usage of the licensed virtual appliance by the user s application which may be running at one or more different server grids.

According to different embodiments at least a portion of the other services described above may be implemented as internal services e.g. internal to the Cloudware system network and or as external services e.g. external to the Cloudware system network .

According to specific embodiments in order to implement or provide functionality relating to one or more of the Cloudware related features described herein it may be preferable to incorporate various types of changes modifications to virtualization software such as AppLogic . Examples of preferred changes modifications may include but are not limited to one or more of the following or combinations thereof 

In the example of GUI may correspond to a data center operator DCO profile page which may be associated with a particular DCO namely NetClime Inc. According to specific embodiments the DCO profile page may be accessible to various entities or Cloudware customers such as for example data center operators e.g employees agents of the DCO end users publishers e.g. publishers of applications appliances etc. In the example of it may be assumed that a DCO employee has logged into the Cloudware System and that at least a portion of the content of DCO profile page has been dynamically generated for that particular DCO employee.

As shown in the example of DCO profile page includes a variety of different types of content which may be related to or associated with NetClime s data center. Examples of such content may include but are not limited to one or more of the following or combinations thereof 

In at least one embodiment the content may be editable by the account owner so that the account owner can modify what appears on the profile page for the account owner as well as for other users of the service.

In at least one embodiment a data center may have a plurality of different types of resources associated therewith. Examples of such resources may include but are not limited to one or more of the following or combinations thereof 

In some embodiments the DCO may charge their customers on a per resource basis wherein a customer may be charged fees based on the various resources which that customer uses. For example in one embodiment a customer may be charged a separate fee each time the customer or the customer s application which may be being hosted at the data center makes use of one or more specified data center resources. According to different embodiments the pricing structures of various fees for data center resource utilization may be based upon a variety of different criteria such as for example one or more of the following or combinations thereof 

In some embodiments a DCO may group different resources together to offer one or more bundled groups of resources for specified fees. In one embodiment a packaged or bundled group of resources may be referred to as a virtual resource bundle VRB . For example in at least one embodiment a DCO may offer a customer e.g. for a specified fee a virtual resource bundle which for example may include 1 CPU 1 GB RAM 250 GB storage and 125 Mbps bandwidth. Rather than charging the customer individually for each type of resource in the virtual resource bundle the customer may be presented with a single fee arrangement for use of the entire virtual resource bundle e.g. for a specified duration of time .

One example of a virtual resource bundle is a BCU. In one embodiment the term BCU may refer to a basic computing unit. In one embodiment a BCU may be defined as having a fixed or predetermined amount of computing resources. For example in one embodiment a BCU may be defined to include a CPU core e.g. the equivalent of a 1.86 MHz single core CPU and RAM e.g. the equivalent of 1 GB RAM . In other embodiments a BCU may be defined to include other combinations of resources such as for example one or more of the following or combinations thereof CPU s RAM storage e.g. 250 GB disk storage bandwidth e.g. 500 GB transfer etc.

In at least one embodiment different portions of the resource metering content e.g. may represent different types of DCO resources such as for example one or more of the following or combinations thereof 

In at least one embodiment all or selected portions of the resource metering content e.g. may relate to a variety of different data center resources which may be used for hosting distributed applications which are implemented across multiple machines and or across multiple nodes of the data center. Additionally as illustrated in the example of the data center resource metering content may be displayed to a user via a graphical user interface.

In at least one embodiment one or more application catalogs e.g. and or applications e.g. may be published e.g. for display on DCO profile page by the DCO by user s and or by appliance publishers e.g. which have an affiliation or relationship with the DCO . In at least one embodiment one or more application catalogs may include pre configured sets of applications e.g. organized according various criteria such as for example theme functionality etc. for use in designing and or implementing distributed applications for example. In one embodiment application content portion may be operable to display a customized list of user selected preferred applications.

In at least one embodiment one or more appliance catalogs may include pre configured sets of appliances for use in designing and or implementing distributed applications for example. In at least one embodiment content information relating to one or more of the appliance catalogs may be globally accessible for example via the Cloudware System and or WAN. For example in at least one embodiment the appliance catalogs and related content may be stored in a centralized location which may be accessible to all or selected data centers and or users e.g. via the Cloudware System . Accordingly in at least one embodiment the appliance catalogs which may be accessible via different data centers may be standardized across the multiple different data centers.

In one embodiment the content relating to one or more appliance and or application catalogs may be available globally using one or more of the following approaches 

In at least one embodiment appliances that are recently used on a particular grid or datacenter may be cached on that grid or datacenter appliances may be cached in a datacenter either on demand e.g. when a first application tries to use the appliance or pushed to the datacenter when the appliance becomes available. The delivery and caching of catalog appliances and applications may be preferably handled using a common approach.

In one embodiment appliance content may be operable to display a customized list of user selected preferred appliances.

In at least one embodiment one or more of the forums or portions thereof such as for example forum threads forum topics etc. may be organized around various types of infrastructure such as for example cloudware related infrastructure AppLogic related infrastructure etc. . Other examples of such infrastructure may include but are not limited to one or more of the following or combinations thereof 

For example in one embodiment a user may click e.g. right click on an icon of a specific application or appliance in order to access one or more specific forums relating to that specific application appliance. In one embodiment when a user clicks on the icon of a particular application or appliance the user may be presented with a menu for accessing one or more online forums which may be related to the selected application appliance. One benefit of this approach may be that the user can submit the question or feedback directly with the entity to which it applies and or who is responsible for servicing such questions and or feedback without having to figure out which company published or supports the entity.

In the example of GUI may correspond to a profile edit page relating to data center operator DCO such as for example NetClime Inc. According to specific embodiments the DCO profile edit page may be accessible to various users e.g. selected DCO employees agents who may be provided with sufficient authorization privileges to access the DCO profile edit page.

In the example of it may be assumed that a DCO employee has logged into the Cloudware System and that at least a portion of the content of DCO profile edit page has been dynamically generated for that particular DCO employee.

As shown in the example of DCO profile edit page includes a variety of different types of content which may be related to or associated with NetClime s data center. Portions of the content illustrated in the example DCO profile edit page of may be similar to corresponding portions of content illustrated in the example DCO profile page of and therefore will not be described in greater detail.

As illustrated in the example of various portions of content e.g. illustrated in the example DCO profile edit page of may be edited and or modified by an appropriate user such as for example a DCO employee agent .

In some embodiments other portions of content e.g. etc. may also be edited and or modified by an appropriate user. For example in at least one embodiment a NetClime employee agent may be given permission to perform a variety of different editing operations such as for example one or more of the following or combinations thereof 

In the example of GUI may correspond to a virtual appliance profile page which is associated with a given virtual appliance. Examples of various virtual appliances may include but are not limited to one or more of the following or combinations thereof 

In the example of it is assumed that virtual appliance profile page is associated with a Simple Web Server virtual appliance which for example may provide functionality for implementing a Web Server application.

Various examples of different virtual appliances are discussed in greater detail in U.S. patent application Ser. No. 11 522 050 by Miloushev et al. entitled APPARATUS METHOD AND SYSTEM FOR RAPID DELIVERY OF DISTRIBUTED APPLICATIONS previously incorporated herein by reference. According to different embodiments an entity which creates a customized virtual appliance may publish the customized virtual appliance and or other information relating to the customized virtual appliance to one or more Cloudware Appliance catalogs.

According to specific embodiments the virtual appliance profile page may be accessible to various entities or Cloudware customers such as for example data center operators e.g employees agents of the DCO end users publishers e.g. publishers of applications appliances etc. etc. In the example of it is assumed that a user e.g. user NetClime as illustrated at has logged into the Cloudware System and that at least a portion of the content of virtual appliance profile page has been dynamically generated for that particular user.

As shown in the example of virtual appliance profile page includes a variety of different types of content which may be related to or associated with the particular virtual appliance e.g. Simple Web Server virtual appliance . Examples of such content may include but are not limited to one or more of the following or combinations thereof 

In at least one embodiment the virtual appliance profile page may include a summary portion e.g. which may include content which provides a summary of various aspects and or features relating to the virtual appliance. Such summary content may make it easier for users to choose an appliance and or to dynamically compare features of similar type appliances. For example as shown in the example of summary portion e.g. At A Glance may include a variety of different types of information relating to the virtual appliance such as for example one or more of the following or combinations thereof 

According to one embodiment all or selected portions of the information and or content provided in summary portion may be automatically updated in real time. In other embodiments all or selected portions of the information and or content provided in summary portion may be automatically updated at periodic intervals e.g. daily and or upon user request.

In at least one embodiment a user may access the virtual appliance profile page GUI for example by clicking e.g. right clicking on an object or image representing the virtual appliance such as for example graphical image which for example may be displayed in one or more other GUIs described or referenced herein.

It will be appreciated that one unique feature of the Cloudware network is the ability of the Cloudware System to monitor track analyze and or process e.g. in real time various types of operational and or configuration information relating to all or selected instances of virtual appliances and or applications across all or selected data centers of the Cloudware network.

Another unique aspect is the ability of the Cloudware System to automatically and or dynamically generate e.g. in real time compiled information content such as for example Appliance Usage Statistical Information Related Appliance Application Information etc. relating to various virtual appliances applications and or other aspects relating to the global Cloudware network. In at least one embodiment such compiled content may be based at least in part upon actual or existing uses of virtual appliances and or applications across all or selected data centers of the Cloudware network.

For example according to various embodiments the Cloudware System is able to analyze various types of operational and or configuration information relating to all or selected instances of virtual appliances and or applications across all or selected data centers of the Cloudware network and is further able to use the analyzed information to automatically and dynamically generate one or more of the following or combinations thereof types of information which for example may correspond to real time information 

In the example of GUI may correspond to a virtual appliance expanded profile page which is associated with a given virtual appliance. In the example of it is assumed that virtual appliance expanded profile page is associated with a Simple Web Server virtual appliance which for example may provide functionality for implementing a Web Server application. Accordingly in at least one embodiment at least a portion of the content of the virtual appliance expanded profile page of may be similar to the content of virtual appliance profile page of .

According to specific embodiments the virtual appliance expanded profile page may be accessible to various entities or Cloudware customers such as for example data center operators e.g employees agents of the DCO end users publishers e.g. publishers of applications appliances etc. etc. In the example of it is assumed that a user has accessed the Cloudware System and that at least a portion of the content of virtual appliance expanded profile page has been dynamically generated for that particular user.

As shown in the example of virtual appliance expanded profile page includes a variety of different types of content which may be related to or associated with a given customized virtual appliance e.g. Simple Web Server virtual appliance . Examples of such content may include but are not limited to one or more of the following or combinations thereof 

In at least one embodiment the boundary content may include one or more of the following type of information or combinations thereof 

In one embodiment the virtual appliance expanded profile page may include usage details such as the memory usage content setting up the content and shared file storage etc.

In at least one embodiment the page may include detailed typical usage info which provides example usage of the appliance in various application use cases. This information may include for example graphical representation of the infrastructure of such application textual description of the purpose and specialization of the usage case as well as details on the role configuration and or limitations of the appliance in such use case.

In one embodiment the page may include additional notes as well as links and references to other appliances and other documents that may be useful in conjunction with the appliance. For example such documents may include the documentation of the application software used in the appliance e.g. http httpd.apache.org and the standards supported by the appliance e.g. HTTP 1.1 .

In at least one embodiment the virtual appliance expanded profile page may include a summary portion e.g. which may include content which provides a summary of various aspects and or features relating to the virtual appliance. For example as shown in the example of summary portion e.g. At A Glance may include a variety of different types of information relating to the virtual appliance such as for example one or more of the following or combinations thereof 

According to one embodiment all or selected portions of the information and or content provided in summary portion may be automatically updated in real time. In other embodiments all or selected portions of the information and or content provided in summary portion may be updated at periodic intervals.

In at least one embodiment a user may access the virtual appliance expanded profile page GUI for example by clicking e.g. right clicking on an object or image representing the virtual appliance which for example may be displayed in one or more other GUIs described or referenced herein.

In the example of GUI may correspond to a user dashboard page which is associated with a particular Cloudware user or customer . For example as shown at in the example of the current logged in user s ID is Joe User .

According to specific embodiments the user dashboard page may be accessible to various entities or Cloudware customers such as for example data center operators end users publishers e.g. publishers of applications appliances etc. In the example of it is assumed that a user e.g. Joe User has logged into the Cloudware System and that at least a portion of the content of user dashboard page has been dynamically generated for that particular user.

As shown in the example of user dashboard page includes a variety of different types of content which may be related to or associated with one or more applications which Joe User is running on the Cloudware network. Examples of such content may include but are not limited to one or more of the following or combinations thereof 

In the example of GUI may correspond to an alternate embodiment of a user dashboard page which is associated with a particular Cloudware user or customer .

According to specific embodiments the user dashboard page may be accessible to various entities or Cloudware customers such as for example data center operators end users publishers e.g. publishers of applications appliances etc. In the example of it is assumed that a user has logged into the Cloudware System and that at least a portion of the content of user dashboard page has been dynamically generated for that particular user.

As shown in the example of user dashboard page includes a variety of different types of content which may be related to or associated with one or more applications which the user is running on the Cloudware network. Examples of such content may include at least a portion of the various content previously described and illustrated with respect to .

As illustrated in the example embodiment of portion of the GUI may include different types of content relating to various applications which may be instantiated at the Cloudware network. In the particular example of region includes an application information table which provides various types of information relating to different instances of applications which may be instantiated at one or more data centers of the Cloudware network.

In at least one embodiment the user may modify or arrange the display of the application objects e.g. in region as desired. For example in one embodiment the user may elect to display and or sort the information displayed in the application information table according to various criteria such as for example one or more of the following or combinations thereof 

In at least one embodiment a user may select a record or entry e.g. in the application information table in order to access additional information relating to the application associated with the selected entry. Thus for example in one embodiment a user may select entry of the application information table in order to access additional information features associated with the SiteKreator 2.0 application which for example is instantiated in the Orangeburg data center. Examples of the various types of additional information features which may be accessed by the user are illustrated for example in of the drawings.

In the example of it is assumed that GUI includes various types of content and or features which are similar to the content features described previously with respect to GUI of .

Additionally in the example of it is assumed that a user has selected entry of the application information table in order to access additional information features associated with the SiteKreator 2.0 application which for example is instantiated in the Orangeburg data center.

As illustrated in the example embodiment of when the user selects entry of the application information table a secondary GUI e.g. Application Settings GUI is displayed to the user which enables the user to access and or modify various settings relating to the selected application instance such as for example one or more of the following or combinations thereof 

In the example of it is assumed that the user has elected to access and or modify various resource settings relating to the selected application instance e.g. SiteKreator 2.0 application corresponding to entry of the application information table .

As illustrated in the example embodiment of the resources portion e.g. of the Application Settings GUI may include various types of content e.g. relating to different types of resources and their current parameter values associated with the selected application instance. Examples of such resource types may include but are not limited to one or more of the following or combinations thereof 

In at least one embodiment the displayed resource information e.g. may include one or more of the following types of information or combinations thereof 

In at least one embodiment the user may use the GUI to adjust or modify the settings of one or more resource types e.g. by increasing or decreasing their current parameter values in order to cause the identified resource types to be dynamically changed to a new parameter value as specified by the user. Thus for example in one embodiment if the user desired to increase the computing resources associated with the selected SiteKreator 2.0 application instantiated in the Orangeburg data center from 5 BCU to 10 BCU the user may input the new desired computing resource parameter of 10 BCU e.g. by sliding the computing resource button from 5 to 10 and click save . Thereafter the Cloudware System may processes the user s resource modification instructions and initiate appropriate actions to automatically and dynamically modify the computing resources associated with the identified SiteKreator 2.0 application instantiated in the Orangeburg data center in accordance with the user s instructions.

In at least one embodiment GUI may be operable to allow the user to create multiple different application setting profiles e.g. for a given application. Additionally in some embodiments GUI may be operable to allow the user to define one or more conditions and or events and or other criteria e.g. as shown at which may automatically trigger the application of specific application setting profiles for the given application upon the occurrence of such events conditions. For example in one embodiment the user may define a first application setting profile e.g. Profile 1 to serve as the default profile under normal operating conditions and may define a second application setting profile e.g. Profile 2 to be implemented upon the occurrence of one or more specified events conditions such as for example the occurrence of a primary power failure at the data center where the application is instantiated or as another example when the application needs additional processing capacity for example during specified peak hours and or based on actual real time requirements needs.

In the example of it is assumed that a user has selected entry of the application information table in order to access additional information features associated with the SiteKreator 2.0 application which for example is instantiated in the Orangeburg data center. Additionally it is assumed that the user has elected to access and or modify various location settings relating to the selected application instance e.g. SiteKreator 2.0 application corresponding to entry of the application information table .

In at least one embodiment when the user selects Location Tab a secondary GUI e.g. Application Settings GUI is displayed to the user which enables the user to access and or modify various settings relating to the hosted location s of the selected application instance.

As illustrated in the example embodiment of the location portion of the Application Settings GUI may include various types of content relating to different data centers of the Cloudware network such as for example one or more of the following or combinations thereof 

In at least one embodiment GUI may show the available data centers in a list or table not shown and or as a geographical map. It may also allow zooming in on specific regions so that additional detail and resolution on the available data centers and their offerings such as grids with different costs may be selected by the user similar in visual operation to speedtest.net Google Maps Google Earth Microsoft Live Virtual Earth etc.

In another usage example the user may select the continent zoom in to the country state city further zoom on a particular data center and or the zoom on a section of the data center with specific characteristics then select an individual grid on which the application runs or should run.

In some embodiments GUI may additionally allow the user to specify filters e.g. in account settings permanently for the account for a specific search etc. in order for example to select a subset of the available data centers based on some criteria such as geographical area service level agreement CPU memory ratio price range etc.

In some embodiments not shown GUI may also be operable to display various types of target user content one or more target user bases for whom the selected application may be targeted toward. Examples of such target user content may include but are not limited to one or more of the following or combinations thereof 

In at least one embodiment different graphical objects e.g. in GUI may have different characteristics e.g. different shapes sizes colors etc. which for example may be used to represent different types of information which may be of use to the user such as for example one or more of the following or combinations thereof 

In at least one embodiment a user may select e.g. click and or mouseover an object displayed in GUI in order to access additional information and or features relating to the data center or other entity associated with the selected object including cost and other data center characteristics discussed herein.

For example as illustrated in the example embodiment of when the user clicks on data center object the user may be presented with additional information e.g. relating to that data center. Additionally in some embodiments the user may be presented with an option to move or migrate the selected application from its current data center location e.g. to the newly selected data center e.g. .

In at least one embodiment user may only be allowed or in able to move or migrate applications which are owned by or managed by that user.

In at least one embodiment GUI may also present the user with an option e.g. via Map List icons for displaying various content presented in GUI via a list or table. In another embodiment GUI may present the user with other visual or graphical representations of the data center and location information as well as other selected data center features services resources attributes etc. .

In the example of it is assumed that a user has selected entry of the application information table in order to access additional information features associated with the SiteKreator 2.0 application which for example is instantiated in the Orangeburg data center. Additionally it is assumed that the user has elected to access and or modify various properties settings relating to the selected application instance e.g. SiteKreator 2.0 application corresponding to entry of the application information table .

In at least one embodiment when the user selects Properties Tab a secondary GUI e.g. Application Settings GUI is displayed to the user which enables the user to access and or modify various properties and or other settings relating to the properties of the selected application instance. In at least one embodiment GUI may enable a user to configure and or assign various properties of the selected application before starting or re starting an instance of the selected application.

As illustrated in the example embodiment of the properties portion of the Application Settings GUI may include various types of content relating to different properties and or parameters to be applied to a running instance of the selected application. In at least one embodiment the user may update or modify at least a portion of the application properties parameters via GUI . Example of various different types of application properties and or parameters are illustrated in the example of . Example of other types of application properties and or parameters are described for example in U.S. patent application Ser. No. 11 522 050 by Miloushev et al. entitled APPARATUS METHOD AND SYSTEM FOR RAPID DELIVERY OF DISTRIBUTED APPLICATIONS previously incorporated herein by reference.

In the example of it is assumed that GUI includes various types of content and or features which are similar to the content features described previously with respect to GUI of . Additionally it is assumed that the user has elected to access various types of Cloudware network related information for example by selecting the Network Tab .

In at least one embodiment when the user selects Network Tab GUI portion displays various types of content to the user for enabling user to access information and were features relating to the Cloudware network such as for example one or more of the following or combinations thereof 

Additionally as shown in the example of GUI portion may also include content e.g. relating to searching filtering functionality which for example may be operable to enable the user to initiate and or perform searches filtering using a variety of different search filtering criteria such as for example one or more of the following or combinations thereof 

Additionally as shown in the example of GUI may also include content portion which in at least one embodiment may be operable to display dynamically generated customized content relating to the user s preferred network resources and or other information. In at least one embodiment the user may browse through various content displayed in GUI portion and selectively add delete modify desired network content resources to from the user s customized or personalized network resource content portion .

It will be appreciated that the various network resources which may be displayed in GUI portion and or selectively add deleted to from the user s customized or personalized network resource content portion may include various different types of network resources which may aid or facilitate the user in implementing and or performing various activities at the Cloudware network. As illustrated in the example of examples of different types of network resources may include but are not limited to one or more of the following or combinations thereof 

In one embodiment the user can drag a resource found in the search results shown in content of GUI portion into his customized network content . In one embodiment this will make the selected resource e.g. appliance application catalog service datacenter etc. available in user s personalized network which may also able it to be more easily accessible for selection for example when the user is performing various other functions e.g. creating new application instances from a catalog editing application infrastructure moving applications from one datacenter to another etc. . In at least one embodiment the Cloudware network may be configured or designed to allow the user to utilize only those entities which are part of the user s personalized network sometimes referred to as favorites . In at least one embodiment a user s personalized or customized network may include for example one or more of the following or combinations thereof lists of approved applications lists of approved appliances and or catalogs lists of approved preferred data centers etc.

In at least one embodiment the Cloudware network may be configured or designed to automatically analyze and select a preferred data center for placing e.g. initial placement or subsequent migration a given application. In one embodiment the Cloudware network may be operable to give preference to particular data centers which are part of the user s or which are part of an account s personalized network and or may give preference to particular data centers which meet selection criteria specified by the user account holder.

In at least one embodiment a user can remove resources from his personalized network for example by selecting them with the mouse and requesting a remove operation. In addition in one embodiment a resource may be removed by dragging the resource s icon or other object representing the resource out of the content and dropping it outside e.g. dragging it back into GUI portion .

In at least one embodiment at least a portion of the various content provided in one or more of the GUIs illustrated in may be generated by the Cloudware System and or may be accessed by a user via the Cloudware network.

In one embodiment the content of GUI portion may also be made available as search results through general purpose search engines such as Google Yahoo and MSN Search for users who are not logged in or who do not even have an account with the Cloudware service. For example in one embodiment the Cloudware System may publish profiles of the resources and or content available at the Cloudware network e.g. datacenters accounts catalogs applications appliances services etc. as static web pages and may submit them to search engines for indexing. This approach allows those who search for a particular solution e.g. clustered MySQL to find solutions available on the Cloudware service even if they themselves are not yet a Cloudware service member user thereby attracting additional customers and content providers to the services provided by or offered at the Cloudware network as well as providing additional demographic data of those interested in a particular solution.

In one embodiment the Cloudware System may further collect statistics on such searches and page hits and provide suggestions for targeted ads. In at least one embodiment the content published as static web pages and searchable on the web without customer login may be limited in certain ways for example without links or details that are available only to logged in users e.g. pricing info may be unavailable without knowing the type of customer for profit non profit reseller academic .

In the example of it is assumed that GUI includes various types of content and or features which are similar to the content features described previously with respect to GUI of . Additionally it is assumed that the user has elected to access various types of Cloudware message related information for example by selecting the Messages Tab .

In at least one embodiment when the user selects Network Tab GUI portion displays various types of content to the user for enabling user to access various types of message related information and or features such as for example one or more of the following or combinations thereof 

For example in at least one embodiment when a user utilizes a given resource of the Cloudware network such as for example a given application appliance data center etc. the user may be eligible to subscribe to and or may be automatically subscribed to receive messages relating to that particular resource. For example in one embodiment a user may be eligible to subscribe to and or may be automatically subscribed to receive different messages relating one or more of the entities resources included in the user s personalized and or customized network resource list e.g. . This may allow the user to not have to determine which organization s publishes or maintains a given resource of the Cloudware network while still allowing the user to receive messages and or other information related to the resource. Additionally in at least one embodiment as the publisher of a given resource changes e.g. upon acquisition and or as an application is moved to a different data center the user s account s subscription may be automatically updated e.g. by the Cloudware System to the new publisher without requiring user interaction.

In at least one embodiment messages relating to a given resource may be generated by various different entities such as for example users the Cloudware System publishers DCO s applications appliances grids data centers and or other network entities.

In at least one embodiment the Cloudware network may include a message distribution system which may include various functionality such as for example one or more of the following or combinations thereof 

For example in one embodiment a user may generate a message relating to a particular network element such as for example a virtual appliance and may send the message to the virtual appliance whereupon the message may then be automatically distributed to subscribers of the virtual appliance. Such subscribers may include for example people and or non human network entities.

In at least one embodiment a user may generate a message relating to a particular network element such as for example a virtual appliance an application a grid or a data center and may send the message to that element or to the element s designated proxy whereupon the message may then be automatically routed to the organization that provides support services for the selected element and or for the user s account. In this way the user may be spared the burden of performing various tasks such as for example separately searching for a support organization figuring out whether his account has a set relationship with a support provider determining which support provider supports the selected element etc.

In some embodiments the Cloudware System may further arrange for a payment scheme between the user and the service provider. For example in one embodiment no payment may be required if the account already has a support contract. Alternatively one time payments and or per incident payment may be arranged through the user s standard payment method s thus simplifying and accelerating user s support request s .

In another embodiment a message sent to a network element may also or instead be posted to a community bulletin board so that information about the element may be shared seamlessly between those who use the element e.g. tips suggestions use cases success stories etc. thereby facilitating community based support mechanisms.

Additionally as shown in the example of GUI portion may also include content relating to searching filtering functionality which for example may be operable to enable the user to initiate and or perform searches filtering using a variety of different search filtering criteria such as for example one or more of the following or combinations thereof 

In one embodiment the messages shown in the content portion may be further grouped by search criteria such as the list in the preceding paragraph. In addition the content portion may further have action buttons such as for replying to a message for viewing a message and other message actions message actions may include typical message actions available in e mail and messaging systems such as Microsoft Outlook Mozilla Thunderbird etc. .

Additionally as shown in the example of GUI may also include content portion which in at least one embodiment may be operable to display dynamically generated customized content relating to the organization of messages and or subscriptions relating the user s preferred network resources and or other information.

In at least one embodiment the content portion may provide a hierarchical list of folders in which messages may be organized. In the example of the folders include and Inbox for organizing incoming messages a Message Archive for organizing older archived messages and a Sent Messages folder for organizing messages sent by the user and or account. In addition the content portion may include content related to actions that can be performed by the user such as a New Message action that allows users to write and send a new message.

In one embodiment the content portion may include messages from systems outside of the Cloudware network. Such systems may include for example RSS subscriptions blog entries podcasts and other subscriptions news services etc.

In at least one embodiment at least a portion of the various content provided in one or more of the GUIs illustrated in may be generated by the Cloudware System and or may be accessed by a user via the Cloudware network.

In one embodiment the message content may also be made available through external systems such as for example webmail e.g. Google Gmail social networks e.g. Facebook business systems Plaxo LinkedIn RSS and other syndication feeds etc. In one embodiment the Cloudware network may provide gateways to off Internet systems such as for example Simple Message Service SMS fax dial up networks bulletin board systems BBS etc.

In at least one embodiment GUI may correspond to an infrastructure editor page which for example may be used to enable a user and or other entity to create configure edit and or manage various appliances and or applications. More specifically in the example of it is assumed that a user has accessed GUI e.g. via the Cloudware network in order to configure edit a distributed application e.g. which for example may be comprised of a plurality of different virtual appliances e.g. etc. .

According to specific embodiments the infrastructure editor page may be accessible to various entities or Cloudware customers such as for example data center operators end users developers IT staff system administrators publishers e.g. publishers of applications appliances etc. In the example of it is assumed that a user has logged into the Cloudware System and that at least a portion of the content of infrastructure editor page has been dynamically generated for that particular user.

As shown in the example of infrastructure editor page includes a variety of different types of content which may be related to or associated with one or more applications and or appliances. Examples of such content may include but are not limited to one or more of the following or combinations thereof 

In at least one embodiment GUI portion may be operable to allow a user to create edit and or modify various features and or characteristics associated with one or more applications and or appliances. For example according to different embodiments GUI portion may be operable to enable a user to perform a variety of different activities operations such as for example one or more of the following or combinations thereof 

For example in at least one embodiment a user may click e.g. right click on an icon of a specific appliance e.g. webserver virtual appliance in order to access various types of information content relating to the selected appliance such as for example one or more of the following or combinations thereof 

Similarly in at least one embodiment a user may click e.g. right click on a specific application e.g. the Main section of the SugarCRM application as shown at or on other locations of the editor canvas in order to access various types of information content relating to the selected application such as for example one or more of the following or combinations thereof 

In one embodiment when a user clicks or selects a given application or appliance the user may be presented with a dynamically generated and or customized menu for accessing various types of information content relating to the selected application appliance.

In this example it is assumed that a user utilizes client computer system to access the Cloudware network. In one embodiment client computer system may be implemented as a personal computer or workstation which is able to access the Cloudware network via the internet using for example conventional Web browsers such as Microsoft Internet Explorer or Mozilla Firefox. In at least one embodiment client computer system may acquire access to the Cloudware network via a Cloudware portal system . An example of a Cloudware portal system is described previously with respect to Cloudware User Interface of .

In the example of it is assumed at 1 that the user initiates a Start Application e.g. Start Test Application request at client system . In at least one embodiment the Start Application request may be forwarded 3 to the Cloudware controller via the Cloudware portal . An example of a Cloudware controller system is described previously with respect to Cloudware System controller of .

At 5 it is assumed that the Cloudware controller processes the received Start Application request. In at least one embodiment the processing of the Start Test Application request may include performing one or more of the following operations or combinations thereof 

In the example of it is assumed that the Test Application is to be instantiated and started at a specific network grid which is managed by grid controller system . In one embodiment where the specific network grid is located at a specific data center the grid controller system may reside at the same data center e.g. where the grid s it controls are located . In at least one embodiment portions of functionality relating to the grid controller system may be incorporated into DC Manager of the Cloudware System such as for example DC Manager of .

As shown at 11 the Cloudware controller may generate and send instructions to grid controller to initiate a running instance of the Test Application at the specified grid.

In at least one embodiment if the Cloudware controller determines that the application should run on a different grid from the one it is currently assigned to the Cloudware controller may initiate and complete a migration of the application to the target grid controller.

At 13 it is assumed that the grid controller processes the received Start Test Application instructions from Cloudware controller . In at least one embodiment the processing of the Start Test Application instructions may result in the grid controller performing one or more of the following operations or combinations thereof 

For example in at least one embodiment in order to determine whether information associated with one or more of the identified boot volumes associated with components of the Test Application is are current or up to date the grid controller may query 17 storage system to verify and or to provide a list of the current boot volumes and or class information to be associated with components in the instance of the Test Application which is to be instantiated started at the specified grid. An example of such a storage system is described previously with respect to storage system of .

In the example of it is assumed that the boot volume query provided from the grid controller to the storage system includes a list of boot volumes which the grid controller has identified as the appropriate boot volumes to be associated with the components in the instance of the Test Application to be started at the designated grid. In some embodiments the grid controller may send this query to the Clowdware Controller and the Clowdware Controller may be configured or designed to handle such requests queries.

At 19 it is assumed that the storage system processes the Test Application boot volume query sent from the Cloudware controller. In at least one embodiment the processing of the Test Application boot volume query may result in the storage system and or other entity of the Cloudware System performing one or more operations including for example one or more of the following or combinations thereof 

At 21 the storage system may generate and send a query response to the grid controller. For example in one embodiment the storage system and or Cloudware System may verify that the list of Test Application boot volumes identified by the grid controller is current up to date. In some embodiments if it is determined that that the list of Test Application boot volumes identified by the grid controller is not current up to date the query response may include updated boot volume information which includes information relating to the current up to date boot volumes which are to be associated with the Test Application. In addition if the component class descriptors and or the boot volumes are found to be out of date the Grid Controller may identify and or obtain the most current versions from the Storage System .

At 23 the grid controller may take appropriate action s for starting a running instance of the Test Application at the designated grid. In at least one embodiment the grid controller may utilize at least a portion of information provided in the query response to start the running instance of the Test Application.

In at least one embodiment the grid controller may be operable to periodically determine and or generate 25 application status information relating to one or more running applications such as for example the Test Application . Further in at least one embodiment at least a portion of the application status information may be forwarded e.g. 27 29 to the Cloudware system client system and or other entities of the Cloudware network and or entities of external networks .

In one embodiment Cloudware may be defined as a global utility computing environment. For example in one embodiment a utility computing service running Cloudware may combine multiple AppLogic based grids into a single scalable highly available computing cloud that may be used to run distributed Web 2.0 applications for example. The individual grids that comprise the cloud can be located anywhere on the net and or at various different geographic locations across the world and may be managed by different hosting providers. Thus for example Cloudware may span continents and provide a truly global computing utility which for example may be accessible with just a browser.

In one embodiment customers may interact with a Cloudware based service through a web portal and an account controller. The portal may be used to create and manage their accounts track charges and make payments browse and search the documentation forums and catalogs of appliances and applications view on line tutorial sessions open support tickets etc. The account controller may be used to create edit and run applications create new appliances publish appliances and applications rate and review other publicly available appliances and applications etc.

According to specific embodiments Cloudware may be implemented via a system e.g. Cloudware System which may be operable to provision and run distributed applications. In one embodiment each individual application instance may reside on a particular grid. In some embodiments different instances belonging to the same customer account can run on different grids.

For example in one embodiment when a user provisions a new application instance from a catalog or creates a new application from scratch the Cloudware System may decide automatically on which grid the application may reside and run. In the case of geographically distributed cloud the user may be asked to select preferred regions in which the application is to run e.g. Western ONE Texas Germany UK etc. and the Cloudware System may then automatically determine on which of the grids located in the selected region s to provision create instances of the application. In one embodiment all or selected applications of the same account running in the same datacenter may have access to a private virtual LAN VLAN . According to different embodiments communications which may be implemented on this VLAN may be free or charged a fee even between applications running on different grids.

In at least one embodiment when the user needs to add resources to a running application e.g. either by restarting the app or by starting one or more standby appliances within it the Cloudware System may first attempt to satisfy the request on the same grid on which the application is running. If that grid has sufficient resources the request may be executed in a manner similar to the techniques described in U.S. patent application Ser. No. 11 522 050 previously incorporated by reference .

However if it is determined that the grid does not have sufficient resources Cloudware may identify a nearby grid with sufficient resources to handle the request and take appropriate action to migrate the application to the identified grid. In one embodiment migration to different grids within the same datacenter and or different data centers may be handled with a minimal interruption of service. For example in one embodiment the total interruption of service may be substantially the same as the downtime which may occur when restarting the application on the same grid.

In some embodiments the definition of an application in AppLogic may be extended for Cloudware. In one embodiment the Cloudware based applications may have properties characteristics similar to appliances for example in one embodiment the users can instantiate applications by dragging them from a catalog onto a canvas and to configure start stop logon and monitor applications with a single click from a right button menu. One goal may be to eliminate completely the need to look inside the application a customer who just wants to use an application rather than modify customize its structure or behavior may be able to do so without even having to know what an infrastructure editor is and or how to use it.

In at least one embodiment Cloudware supports a global repository of appliances and applications. Customers can create their own globally accessible catalogs and publish both appliances and ready application templates in them. Cloudware supports paid appliances and applications with different payment models such as for example one or more of the following or combinations thereof one time charge per account one time charge per instance usage charge per instance usage charge per resource use bcu storage bandwidth etc.

In one embodiment when a user publishes an appliance or application for global access he or she can also specify the license terms pricing method price etc. For example various pricing methods may include one or more of the following or combinations thereof 

In at least one embodiment when an user from another account decides to use a selected appliance or application for example by adding it into his network as described in the user may be presented with the license agreement pricing method price and or other usage terms conditions and may be prompted to accept or agree to each of them. In one embodiment once accepted the user may utilize the selected resources e.g. may create one or more running instances of the selected appliances applications throughout the Cloudware network. Ioe the Cloudware System may bill the user based on his usage and or other terms of the pricing model and remit the collected amount to the publisher possibly retaining a commission.

Through its metering system Cloudware may provide detailed usage statements both to the users of published appliances as well as to the publishers. Additional business opportunities may include but are not limited to one or more of the following or combinations thereof targeted advertising for published appliances e.g. publisher pays for ads or clicks ads may be selected based on criteria specified by publisher such as use of similar or complementary application or appliance etc.

The Cloudware account controller may implement a REST and or SOAP API which may provide full access to all or selected capabilities available on a shell e.g. command line shell or GUI shell including for example ability to create and start application instances etc. In addition the API may enable users to register handlers for receiving system events. In one embodiment the API may be accessible via SSL from anywhere on the net including from appliances that run in the Cloudware network on behalf of a specified account. This latter embodiment allows applications to self manage and or to manage other applications.

In one embodiment the user may also be able to convert an application into a service with terminals and visually assemble a global web operation from instantiable services running in the Cloudware network. In one embodiment the Cloudware service s may be AppLogic based application with a boundary that includes for example properties terminals proper life cycle and or other aspects for using the application as a component for building large scale web systems. In particular services may be fully dynamic e.g. customers may be able to instantiate configure and or connect services on the fly either using the visual tools and or by invoking the API.

In at least one embodiment a Cloudware service may have a very low entry barrier. For example in one embodiment customers may pay a monthly subscription fee e.g. 19.95 month plus the actual amounts of resources they have used during the month. Resources may be preferably metered and billed based on a unit called BCU basic computing unit .

For example in one embodiment one BCU may be equated to the following resources 1 GB of RAM 50 of a CPU and 20 GB of highly available storage. As an illustrative example initial prices may be 0.10 per BCU hr 2 per month for each GB of additional storage and 0.20 per GB of network transfer. Transfer within the same datacenter may be free transfer between datacenters including migration and inter application communications may be billed.

The services and resources uses may also be billed using other methods such as one or more of those described herein including but not limited per individual resource bundles pre pay etc. .

Additionally according to different embodiments monthly subscription fee s may be waived coupons and discounts used e.g. a coupon for 100 GB hours of usage free of charge and or other types of e commerce incentives may be applied.

According to different embodiments the Cloudware server may be operable to provide one or more of the following features or combinations thereof 

According to different embodiments it may be important to keep in mind other opportunities benefits features which Cloudware enables. Example of some opportunities benefits features are described below.

The network effect in the system may be based on one or more of the following or combinations thereof 

This creates a true utility bringing down the cost of doing business together for all or selected other groups in which for example the Cloudware technology provider such as for example 3TERA owns the distribution network and the billing system.

One can for example run an auction to determine the cost of resources in any given geographical region. This can happen in real time using a schema like the clearinghouse auction which establishes the median price using multiple bids and multiple requests. The resulting uniform price can be determined in real time hour by hour resulting in real time optimization of resource usage. A secondary market can be created for futures allowing customers to save money by buying capacity in bulk ahead of time and allowing providers to optimize their loads by selling capacity ahead of time. Inevitably the market may determine the fair price.

A customer may choose to run their database service in one place where storage may be less expensive and take advantage of the fact that front end apps can be moved easily from one place to another to leverage lower cost offshore e.g. Canada Mexico Eastern Europe resources to run the front end of their service.

In at least one embodiment the resulting model may not be unlike Google which brings together three parties consumers who search and read online content advertisers who pay for ads and content providers who serve ads on the content network. By sharing revenue with the content providers Google increases their reach while remaining in control of the whole system as well as of the pricing on each individual ad.

In at least one embodiment it may be preferable to create a critical mass of resources customers and ISVs for the system to obtain sufficient momentum to self propagate. For example in one embodiment we may start by sharing revenue with data center operators who sign into the system and or who provide resources to the Cloudware network in exchange for them assuming the risk of dynamic loads and part of the marketing budget. We can do this with commercial hosting provider partners e.g. Layered Technologies The Planet .

We can also leverage telecommunications providers facilities e.g. AT T BT Cable and Wireless and enterprise data center outsourcers e.g. Savvis T Systems EDS Perot etc for systems resources as well. This may create an initial resource base which may be broad enough to attract customers of various types and size. We may then bring appliances and application providers into the system as well as system integrators and consultants.

It is also possible for system integrators data center operators ISVs SaaS providers enterprise data center outsourcers system integrators etc. to sell products and services from the system under their own brand.

In one embodiment the legal foundation of this may be a consortium comprising 3TERA and or selected data center operators. In some embodiments the membership of the consortium may be expanded to include system integrators ISVs consultants support professionals enterprise data center outsourcers and others. It may allow one to aggregate a common marketing budget and focus it on promoting the service.

As described herein one aspect disclosed herein relates to techniques and mechanisms for automatically migrating instances of distributed applications between geographically different server grids and or data centers.

As illustrated in the example embodiment of Data Center A and Data Center B are each operable to communicate with each other via a wide area network such as for example the Internet a private network etc. . In at least one embodiment multiple different server grids from the different data centers may be linked together to form a virtual global server grid which may be used to facilitate utility computing for distributed applications.

As illustrated in the example embodiment of the cloud computing network may include a Cloudware and Billing System having components and or functionality similar to those described for example with respect to .

For purposes of illustration an example of an application migration procedure will now be described by way of reference to the example embodiment of the geographically distributed cloud computing network of .

In this particular example as illustrated in the example embodiment of it is assumed that Data Center A includes at least one server grid e.g. Server Grid A which is configured or designed to enable utility computing for distributed applications e.g. via the use of virtualized computing resources such as those described herein . Similarly as illustrated in the example embodiment of it is assumed that Data Center B includes at least one server grid e.g. Server Grid B which is also configured or designed to enable utility computing for distributed applications.

In this particular example it is assumed that an instance of a first distributed application e.g. Application A1 has been deployed by a user at Server Grid A. Further it is assumed that Application A1 includes at least one virtual machine e.g. Virtual Machine A1 and at least one virtual volume e.g. Virtual Volume A1 .

In this particular example for purposes of illustration it is assumed that a user e.g. desires to migrate an instance of the Application A1 e.g. identified as Test App from Server Grid A to Server Grid B. Accordingly in this example Server Grid A may be referred to as the Source Grid Server Grid B may be referred to as the Target Grid Application A1 may be referred to as the Source Application and Application A2 may be referred to as the Target Application. 

As shown at 2 it is assumed that a user e.g. accesses the target server grid Server Grid B in order to Initiate Application Migration of the identified application Test App from Source Grid to Target Grid . In at least one embodiment the user may log into the Cloudware System to obtain access to Server Grid B. In other example embodiments the application migration procedure may be manually or automatically initiated by the Cloudware System by one of the server grids e.g. grid controller of Server Grid B or by the application itself.

In at least one embodiment one or more of the following entities may be involved in the migration of an application from the Source Grid to a the Target Grid 

In at least one embodiment a request command or instruction for initiating an application migration may include one or more of the following types of information 

As shown at 6 Server Grid B may process the received command relating to the application migration task and in response may optionally perform one or more of the following operations or combinations thereof 

Accordingly at 20 the Target Grid may query the source grid for information relating to the Source Application and or elements associated therewith . In response the Source Grid may provide to the Target Grid various types of information relating to the identified.

At 22 it is assumed that the Target Grid uses a least a portion of the received Source Application information to determine and or identify one or more set s of elements relating to the Source Application which are to be migrated to the Target Grid. For example according to different embodiments the different set s of elements may include but are not limited to one or more of the following or combinations thereof 

As shown at 24 the Target Grid may request the Source Application descriptor s from the Source Grid and the Source Grid may respond by transferring 26 the requested application descriptor s to the Target Grid.

As shown at 28 the Target Grid may request additional descriptor s and or other information relating to the Source Application and the Source Grid may respond by transferring 30 the requested additional descriptor s and or other information to the Target Grid.

In at least one embodiment the Source Application descriptor s additional descriptor s and or other information relating to the Source Application may include but are not limited to one or more of the following or combinations thereof 

As shown at 32 the Target Grid may request virtual volume information from the Source Grid and the Source Grid may respond by transferring 34 the requested virtual volume information to the Target Grid. In at least one embodiment the virtual volume information may include but are not limited to one or more of the following types of information or combinations thereof 

As shown at 36 the Target Grid may optionally configure the Target Application e.g. which represents a substantially identical instance of the Source Application at the Target Grid. For example in at least one embodiment the Target Grid may modify IP addresses as needed to be compatible with Data Center B resources etc. In one embodiment such configurations may be performed using the transferred application descriptor s and or other migrated information. In at least one embodiment such configurations may be performed during the process of migrating the application descriptor and or other application related information.

As shown at 38 the Target Grid may optionally start the Target Application at the Target Grid. In at least one embodiment this may be desirable in situations where conditions warrant the starting of the application at the Target Grid such as for example in situations where an instance of the application has been migrated to the Target Grid in order to assist in responding to detected high traffic load conditions.

In at least one embodiment the application migration procedure may be implemented as a live application migration procedure wherein the Source Application is running at the Source Grid and continues to run concurrently during the migration procedure. In at least some of these embodiments multiple successive transfers of virtual volume information may be performed e.g. using an incremental approach in order for example to allow the current states of the virtual machine s of the Target Application to be substantially synchronized with the current states of the virtual machine s of the Source Application running at the Source Grid .

As shown at 40 the Target Grid may optionally initiate deletion of the instance of the Source Application at the Source Grid e.g. so that the migration procedure is implemented as a move rather than copy .

In at least one embodiment during the application migration procedure the Cloudware System may optionally be involved with and or may optionally perform one or more of the following or combinations thereof 

Applications submitted to the grid via the REST and or SOAP API from the service manager may be pre compiled. The grid gets a c object descriptor compiled object descriptor which may be a UDL file containing the flattened structure of the application built linked by the build system but without resolving the volumes and assigning MAC IP addresses just doing the assembly compilation .

In the c obj descriptor all or selected volumes may be provided as class volume references. It may be up to the grid to decide whether and when to instantiate a volume this may be true both for appliance class volumes as well as for application volumes coming the first time from an application class .

The grid gets the c obj descriptor on application creation. The descriptor may be replaced one or more times using the application configure operation. On configure and or activate the grid may complete volume instantiation incl. volprep assign MAC IP ADDRESSES and do volfix note volfix may not be needed if using an alternative configuration method such as the DHCP HTTP based configuration introduced in AppLogic 2.3 . The grid may internally create a qobj descriptor for its own controller.

The c object descriptor preferably includes sufficient data to perform all or selected of the above without having to refer to catalog or classes.

The catalog and class entities may be deprecated. They may be still available at the shell level but may not be integrated with Cloudware and may not be exposed through the Representational State Transfer REST API.

The new config operation allows configuring grid s parameters. For example in one embodiment some or all of the same parameters that are configured though aldo may be exposed. In one embodiment aldo may be implemented as a software package used in conjunction with AppLogic by various data center partners. Aldo may be installed by system operators on a server in the data center on the grid backbone and may performs various operations on AppLogic like grid installs adding and removing servers etc.

In addition bindings to outgoing requests notifications may be configured through this operation. The operation allows setting multiple grid parameters with the same command 

In addition grid config prints the full configuration maybe except security sensitive parameters batch option may be supported as may be the stdin option thus allowing exporting and importing the grid settings via UDL file.

The reboot and shutdown operations may also be changed to use IPMI or similar remote power control mechanisms where available. shutdown turns off power after the server shuts down successfully. reboot brings up a server from power down and also does a powercycle if the server does not come back from a soft reboot. In addition the reboot and shutdown operation preferably report these actions and intermediate results to the service controller for example so that Operations Dept can inspect and track down the reasons for which such operations were invoked as well as to track downtime and service level agreement SLA .

One preferred approach may be to have the respool not deal with a fragment list but only with the total amount of various resources but also include the size of the smallest fragment .

Resource pools can be used for individual applications one app per pool or for multiple apps run multiple apps in the same pool . To be able to start an app on the grid you do may need to have a pool.

Then create a pool of the calculated total size in which preferably the minimum fragment may be at least as large as the largest fragment of the application this may ensure that the application can be started in the pool regardless of the pool s fragmentation.

This process may be used separately for the storage pool where the volumes of the application may be created during app create and app config and for the computing resources pool where the application may run on app activate .

Note apps that are in development mode may have the external interface of any appliance turned on for the purpose of outbound internet access e.g. to download install new software . The exact command mechanism my vary. In one embodiment the command may be something like this interface enable external ip 1.2.3.4 netmask 255.255.255.0 gateway 1.2.3.1 dns1 1.2.3.2 . This feature may be disabled for apps in production mode.

This interface may be kept for management purposes to allow remote administration of grids by the service maintainer not for regular users . In one embodiment service users may not invoke this operation on specified grid s .

This interface may be kept for management purposes to allow remote administration of grids by the service maintainer not for regular users as well as for collecting logs and propagating them to the service logs. In one embodiment service users may not invoke this operation on specified grid s .

This interface may be kept for management purposes to allow remote administration of grids by the service maintainer not for regular users In one embodiment service users may not invoke this operation on specified grid s .

Note that any message changes preferably cause notifications to be sent to the service controller e.g. if notifications are registered .

Note in at least some embodiments the terms Cloudware controller and service controller may be used interchangeably.

When operating large grids it may be desirable to support additional resource scheduling algorithms in order to reduce fragmentation and more efficiently utilize the resources available on the grid. Additional algorithms that may be used in grids may be a pool based scheduler and or an optimizing scheduler.

In one embodiment the pool based scheduler may designate server groups within the grid for different resource sizes. For example servers 1 10 may be reserved for appliances that need up to 0.25 CPU cores servers 11 20 for appliances that need up to 0.50 cores servers 21 30 for appliances that need up to 1 core and so on. In one embodiment pools may be defined based on any type of resource including memory. Pool ranges can be dynamically assigned by the scheduler. In at least one embodiment the scheduler can further use the buddy algorithm in order to define the pools and to use pools designated for larger components in order to run smaller components e.g. one example of a well known buddy algorithm is used in the Linux kernel for memory allocation and is frequently described in various references including Understanding the Linux Kernel Third Edition by By Daniel P. Bovet and Marco Cesati .

In another embodiment a scheduler may use optimization algorithms in order to optimally place appliance s in the available resources.

In at least one embodiment one or both algorithms e.g. pool based scheduler and or optimizing scheduler may be used by the scheduler together with the existing AppLogic scheduler algorithms spread and pack .

In one embodiment the underlying AppLogic grid OS may be configured or designed to support live migration of components preferably using the live migration capabilities of the underlying hypervisor. Such migration may be used by the scheduler and other components of the Cloudware network for example to reduce fragmentation and allow better utilization of resources. In addition to live migration it may be possible to migrate appliances by stopping them and restarting them on other server s and or other data center s .

In at least one embodiment the Cloudware Service API may provide one or more of the following objects and methods or combinations thereof 

In one embodiment every entity type that can be linked to in addition to its normal constructor operations create destroy may also have a link constructors link unlink .

The link constructor operation may be preferably invoked with a global name of the entity to which the link may be established as well as a local name under which that entity may be visible. The constructor creates a local link object which appears equal to locally owned objects of the same type and may be listed together with those objects.

For example in one embodiment to create a local appliance link called MySQL the local name will be MySQL and the remote name may be com.mysql.catalog4.mysql5.ver2. Publisher s domain name may be used to ensure uniqueness of global names in a manner similar to the one used by Java classes e.g. using the domain name of the publisher but in reverse order starting with the Top Level Domain TLD for example com.3tera uk.co.3tera etc. 

When invoking an operation on the link the API may verify whether the operation may be valid allowed through a link and forwards it or not accordingly. Generally a subset of the object operations may be available over linked objects for example info may be available destroy may not be .

A link attribute may be preferably defined on each entity the attribute may identify the entity as a real entity or as a link. All or selected sub entities of a linked entity e.g. classes in a linked catalog may be preferably treated as links. That may be on traversing the path to an entity if at least one element may be a link then the entity may be considered as a link. Note that then we may have two types of explicit links manual and inherited. In one embodiment manual links may be unlinked inherited links may not.

Note In one embodiment implicit links such as class to instances and application to grid may be internal to the system and may not exposed through the public API.

In at least one embodiment one may leave CPU memory resources to be specified separately e.g. no BCU . Various reasons for this may include for example 

Leaving this flexibility to the user also allows one to improve the scheduling algorithms gradually so that for example if we can combine two appliances one that needs lots of CPU but little memory and one that needs less CPU but lots of memory then the user may benefit from this.

To avoid fragmentation and make things a bit simpler we may introduce fixed increments powers of 2 starting from of CPU core and of 1 GB . This gives one 

In any case at least per application the billing may be based on a balanced CPU mem combination. The ratio may depend on the hardware configuration of the grid s servers GB RAM per CPU core . This means that the price for running an app with certain resources may be different on different grids.

It would be desirable to make it easier for users to predict the cost for operating an application on the grids and or in the locations they select. One preferred solution may be to show the price for running an app for an hour or for a month in the dashboard in the application list and in the editor configurator. This way the user may see what the application costs to run regardless of how complex the calculation may be and what factors pricing models are being used. We may of course provide an explanation of the general principles somewhere in the docs but it doesn t really matter since users may be able to see the price both before starting the application and while the application is running. This achieves predictable and simple billing e.g. the goal stated above .

Additional resources that may extend the CPU mem billing and or be bundled with it may include but are not limited to one or more of the following or combinations thereof 

According to different embodiments different types of billing accounting mechanisms may be implemented and used to charge users for various uses of Cloudware resources. For example due to the nature of the virtual computing environment enabled by the Cloudware network all or selected aspects of resource usage may be tracked via one or more virtual meters. Such technology provides the capability for unique and novel billing accounting mechanisms to be implemented to track and bill users for various types of resource usage.

For example the resources utilized by a given running instance of virtual appliance associated with a given user may be tracked e.g. over one or more time periods and used to calculate appropriate fees. Such tracked resource usage may include for example one or more of the following or combinations thereof 

Additionally in some embodiments allocation of resource usage may also be tracked based on the entity or components thereof which are utilizing the resource. For example in one embodiment the resources used by a given running instance of virtual appliance may be tracked. In another embodiment where a virtual appliance is configured to run a software application e.g installed at the virtual appliance the resources which are utilized by that specific software application may be tracked e.g. for billing purposes using one or more virtual meters.

In at least one embodiment a least a portion of the information included in the Publisher Server Network Resource Account Statement may be customized based on user specific or customer specific information.

In at least one embodiment a least a portion of the information included in the Publisher Appliance Application Support Account Statement may be customized based on user specific or customer specific information.

It will be appreciated that such resource utilization tracking and billing mechanisms allow for novel types of software licenses and or royalties to be implemented which conventionally have not been possible using existing technology.

For example using existing technology there has traditionally been no easy way for a software provider who provides a downloadable software application to track the actual usage of its software at all the different user computer systems where the software has been downloaded and or installed. For example there has traditionally been no easy way for such a software provider to track at each user s computer system the run time hours for each executed session of the software application at each user s computer system.

As a result a typical software license involves the user paying a one time flat rate e.g. purchase price of the software application which allows of the user to install and use the software application on a single e.g. designated computer system. Once the license fee has been paid the software provider typically does not monitor the user s ongoing usage of the licensed software application at the designee the computer system. Another drawback of traditional software licensing schemes is that they frequently involve a larger upfront license fee which is a barrier to adoption by a wider market lower cost and for certain types of applications markets e.g. hosting costs for just in time provisioning etc. .

As an alternative to such a conventional licensing scheme various features of the Cloudware network embodiments described herein now make it possible for a software provider to provide software e.g. downloadable software applications to users on a pay as you go basis whereby the user may be charged only for actual use of the application at one or more computer system s . Thus for example in one embodiment the software licensing fee may be calculated based on the total active run time hours associated with each executed session of the software application at one or more computer system s . In this way a user is able to install a copy of the software application at multiple different computer systems e.g. managed by or associated with the user and be charged only for the actual usage of the software at each of the different computer systems and or be charged only for resources used by each of the different computer systems during execution of the software application at each respective system .

In the same manner a user who elects to implement at the Cloudware network one or more running instance s of a virtual appliance created by a third party may be charged a fee or royalty which may be based for example on various types of criteria such as for example actual run time usage of each instance of the virtual appliance in the Cloudware network resources used by each running instance of the virtual appliance in the Cloudware network etc.

In at least one embodiment the tracking of various types of Cloudware network resource utilization and or instances of appliances and or applications associated with such network resource utilization may be tracked via the use of different types of virtual meters which have been configured or designed to monitor and or track e.g. in real time activities associated with various resources appliances applications and or other aspects of the Cloudware network.

In one embodiment this mechanism allows the software licensor to allow the user to use the software in multiple locations for example without having to pay separately for each location. Thus for example the user may pay for the actual resources used no matter where they were applied. This may provide further flexibility for the software user allowing more freedom better service and new business models.

As illustrated in the example of one or more metering graphs e.g. etc. may each be operable to simultaneously track and display different attributes associated with different appliances e.g. WEB1 server appliance WEB2 server appliance MYSQL database appliance etc. of the application e.g. TEST Application being monitored.

In other embodiments other virtual meters may be configured or designed to track e.g. in real time and display activities and or attributes associated with selected resources appliances applications and or components thereof such as for example usage of specified software installed at an instance of a virtual computer system running on the Cloudware network.

Various embodiments of the cloudware portal provides an easy way for customers to sign up to utility computing service. It may be a goal that users can self serve at the portal and don t have to call sales or talk to human in order to subscribe for a service or change their account. While sales and support should be available it is anticipated that many of the target users may prefer to perform most operations themselves.

In one embodiment the Cloudware utility computing service may be based on the AppLogic 2.x platform which has been adapted communicate with the Cloudware portal. One enabling feature in AppLogic 2.x may be the SharedGrid.

Aspects of the user facing portion of the portal are described below. Ioe the Cloudware portal may be implemented as a portion of a web site.

The following sections describe one possible scenario in which Cloudware portal functionality may be provided it will be appreciated that many alternative implementations may be possible to achieve similar results.

As illustrated in the example embodiment of Cloudware Portal home page may provide access to and or may include one or more of the following types of information or combinations thereof 

The following design notes describe a set of related definitions and processes that may be used to implement the functions of one example embodiment of the Cloudware network. It will be appreciated that other approaches and designs can be used in alternate embodiments depending on desired design constraints needs and or other factors.

To support Cloudware it may be preferable to provide certain functionalities features in AppLogic . Various examples of such new functionalities features are described below and or other portions described herein . However it is to be noted that the new functionalities features are not limited only to the various examples described herein.

For example in at least one embodiment the following changes modifications may be implemented to existing or previous versions of AppLogic in order to enable various types of Cloudware functionality 

To build a larger system and support effective automation it may be preferable to implement a uniform way for defining interfaces in AppLogic and or Cloudware. Some of those interfaces may be made public while others may be left internal in both cases however it may be preferable to have a way to express common interface design patterns while being able to implement and use those interfaces using PERL PHP Java etc. over an http transport. An additional design goal may be to define the interface mechanism loosely coupled so it can easily accommodate for versioning differences e.g. in the case where the Cloudware service may need to operate grids of different versions .

In at least some embodiments it may be preferable to make a distinction between an interface mechanism and a logical interface or simply interface . In at least one embodiment the interface mechanism defines how interfaces in general are constructed implemented and invoked in a given system. In one embodiment a logical interface may define the semantics of interacting with a given object or set of objects. The same logical interface may be implemented over different interface mechanisms and a single interface mechanism may be used to implement all or selected logical interfaces in a given system or at a given layer within the system.

According to different embodiments an interface mechanism usually includes one or more of the following or combinations thereof 

In at least one embodiment a logical interface may include one or more of the following or combinations thereof 

The following description represents a modified REST architecture style which may deviate from the strict definition of the REST architectural style.

REST Representational State Transfer defines a general method of implementing RPC over HTTP which is simple and language independent. While semantically similar to SOAP REST is much simpler and does not involve pages of hard to parse XML descriptors on every call.

This is just a general convention. Pointers may be represented by URL so to pass anything by reference you pass a URL to it. Also large arguments may be passed by value into the call by using HTTP POST instead of GET. Finally for manipulating truly large binary data one may use partial GET and PUT commands which read write a given range of bytes at a given offset into the data item.

To express logical interfaces it may be preferable to extend the definition of REST in several areas. For example it may be preferable to provide one or more of the following features or combinations thereof 

In one embodiment logical interfaces in REST may be specified in the same way as is done in VSDL etc. namely by defining the bus the set of operations and the semantics in out action status of each operation.

Binding may by name for example by appending the terminal name and the operation name to the base URL of the API. Notice that I used the word terminal rather than object or interface. The difference may be in the ability to access two different instances of the same logical interface on the same boundary.

With very few clearly identified exceptions each or selected interface operation in Cloudware may return a text document in the form similar to the example below 

In one embodiment the status may come first. The allowed values for the status may be textual representations of the standard statuses. The rest of the string may be in the name value format with the names identifying the fields in the bus of the logical interface.

Additional return status information may be defined such as for example human readable error message error message ID useful for localization in different languages log entries etc. 

Further a quoting mechanism for special characters in argument values and for the whole values may be defined thus allowing any text or binary value to be given or returned as argument. Possible quoting mechanisms include URL encoding e.g. a double quote may be encoded as 22 see for example http www.blooberry.com indexdot html topics urlencoding.htm UUENCODE http en.wikipedia.org wiki Uuencode and many others.

In at least one embodiment Cloudware interfaces may be defined in a way that allow the implementor to desynchronize any specific request if it decides to do so. One example of how this may be done is described below 

In one embodiment REST operations may be preferably implemented as scripts under Apache. However this may raise issues relating to how to implement asynchronous operation in such environment. In at least one embodiment such an implementation may be accomplished via the use of one or more of the following operations or combinations thereof 

The following are examples of some preferred containment relationships within Cloudware Note in the examples below only high level entities are shown entities and attributes such as properties and terminals have been omitted for brevity .

In addition to the common attributes the Service entity may have one or more of the following attributes 

In addition to the common attributes the Account entity may have one or more of the following attributes 

In addition to the common attributes the Application Instance entity may have one or more of the following attributes 

In addition to the common attributes the Application Catalog entity may have one or more of the following attributes 

In addition to the common attributes the Appliance Catalog entity may have one or more of the following attributes 

In addition to the common attributes the Application Class entity may have one or more of the following attributes 

In addition to the common attributes the Appliance Class entity may have one or more of the following attributes 

In addition to the common attributes the Datacenter entity may have one or more of the following attributes 

In addition to the common attributes the Grid entity may have one or more of the following attributes 

In at least one embodiment one or more of the following relationships may exist by virtue of operating applications 

These relationships may be used for reference counting so that for example appliance class cannot be deleted for as long as an instance exists and for collecting statistics e.g. total instances of a class runhours etc. 

In at least one embodiment the Cloudware network may be implemented as a unified globally distributed computer system having operational and control characteristics similar to a mainframe computing system. Thus for example in one embodiment all or selected portions of the Cloudware network may be configured or designed to function as a globally distributed mainframe computing cloud wherein the user or client computer systems may be operable as individual terminals for providing interfaces with the mainframe computing cloud. In at least one embodiment the user client systems may function as thin client terminals for providing interfaces with the mainframe computing cloud.

In at least one embodiment the resources attributable to the globally distributed computing cloud may comprise an aggregate of all or selected resources associated with the various systems components devices of the Cloudware network. Thus for example in one embodiment the globally distributed computing cloud may comprise a plurality of physically distinct systems e.g. server systems storage systems computing grids etc. which are deployed in different geographic locations e.g. ONE UK Germany Japan China Australia etc. . In one embodiment the globally distributed computing cloud may comprise a plurality of physically distinct and geographically separate computing grids wherein each computing grid has associated therewith its own respective data storage network. All or selected resources associated with each computing grid may be aggregated shared and or combined and collectively represented e.g. to end users as a single entity which represents a virtual globally distributed computing system or computing cloud . In some embodiments selected resources associated with selected computing grids may be aggregated shared and or combined and collectively represented e.g. to end users as multiple different entities each representing a virtual globally distributed computing system. In some embodiments all or selected resources associated with each computing grid may be aggregated shared and or combined and collectively represented e.g. to end users as a common pool of resources available for use and controlled by a unified virtual globally distributed computing system or computing cloud .

In addition to being able to run various types of server type applications such as for example website applications software Web 2.0 applications etc. various embodiments of the Cloudware network may provide services for running various types desktop computer software such as for example desktop computer operating system software e.g. Linux MS Windows MAC OS Solaris etc. desktop computer applications etc.

In at least one embodiment a desktop computer system may be configured or designed as a stand alone computer system such as a personal computer system or client system for example which includes at least one CPU volatile memory e.g. RAM non volatile memory e.g. hard disk storage and or one or more interfaces e.g. for providing access to the Internet .

For example in at least one embodiment a user may utilize selected resources of the Cloudware network to create and run an instance of a virtual desktop computer system e.g. a virtual PC type computer system which has been configured or designed to run a Microsoft Windows operating system such as for example Windows XP . In one embodiment a user may create an instance of the virtual desktop computer system by utilizing various features and resources of the Cloudware network to create and configure a customized virtual appliance which includes a virtual machine at least one virtual interface and virtual storage.

For example in one embodiment the virtual desktop computer system may be configured or designed to have one or more of the following characteristics and or properties at least a portion of which have been implemented using at least some of the virtualization techniques described herein 

If desired for purposes of compatibility for example the virtual desktop computer system may be configured or designed to have other characteristics and or properties at least a portion of which have been implemented using at least some of the virtualization techniques described herein . Listed below are a few examples 

In at least one embodiment local devices resources connected to the user s terminal such as for example optical drives hard drives ports interfaces e.g. USB ports COM ports Ethernet ports IDE interfaces ATA interfaces SATA interfaces etc. peripheral devices e.g. flash drives printers etc. local area network resources devices networks connections etc. may be attached to the virtual desktop computer system for example by virtualizing one or more local ports interfaces such as for example a local USB interface at the user s terminal and forwarding the virtualized interface s over the terminal connection to the virtual desktop computer system instance at the Cloudware network. In this way local devices connected to or networked to the user s terminal may be virtually attached to the virtual desktop computer system.

In other embodiments a user may utilize selected resources of the Cloudware network to create and run different instances of different virtual desktop computer systems such as for example a first Windows OS based virtual desktop computer system a second MAC OS based virtual desktop computer system a third Linux OS based virtual desktop computer system etc. It may also be possible to run certain virtualization systems such as Parallels so that a single virtual desktop computer in Cloudware may execute multiple operating systems.

It will be appreciated that these are just a few examples of the different virtual appliances which may be created and configured using the Cloudware network resources services and or features. Other types of virtual appliances e.g. such as those described herein may also be created and configured using the Cloudware network resources services and or features. Moreover it will be appreciated that in at least some embodiments the various Cloudware network resources which have been allocated to a running instance of a given virtual appliance may be distributed across multiple different physical computer e.g. server systems associated with one or more grids of the Cloudware network.

In some embodiments a user may search through various Cloudware network catalogs to identify and or select customized virtual appliances such as for example specifically customized virtual desktop computer systems which have been created and or configured by other entities such as for example other users publishers etc. . In one embodiment when the user has identified a particular pre configured virtual appliance e.g. virtual desktop computer system which suits the user s needs the user may initiate an active instance of the selected virtual appliance for example by simply clicking on an appropriate link or button such as for example a GUI button labeled Start a running instance of this virtual appliance for my use. .

In one embodiment the Cloudware network may include various preconfigured desktop appliances with application software preinstalled. Such preinstalled software applications may include accounting packages such as for example QuickBooks Microsoft Money etc. video editing or conversion software image editing and conversion publishing software word processing and other productivity applications such as for example Microsoft Office OpenOffice etc. database applications server side software such as for example Active Directory and Microsoft Exchange Server etc. In this way for example a client who needs a particular software application may create and or connect to an instance of a virtual desktop appliance preconfigured with that application without needing to install the application on his own local or remote desktop. In at least one embodiment this may be used to provide novel business models such as renting applications.

In at least one embodiment once a running instance of the virtual appliance e.g. virtual desktop computer system has been created the user may access the virtual appliance for example via a remote log in protocol interface. For example a user may remotely access and control a specific instance of virtual desktop computer system for example using a remote access protocol such as for example the well known Microsoft RDP Remote Desktop Protocol protocol and or other remote access mechanisms such as for example VNC.

In one embodiment Virtual Network Computing VNC is a graphical desktop sharing system which uses the Remote Frame Buffer RFB protocol to remotely control another computer. It transmits the keyboard and mouse events from one computer to another relaying the graphical screen updates back in the other direction over a network. In one embodiment VNC may be platform independent meaning that a VNC viewer on any operating system can usually connect to a VNC server on any other operating system.

In at least one embodiment a user may use a local computer system e.g. local desktop computer system PDA notebook computer smart phone etc. to gain remote access to the virtual desktop computer system. In one embodiment the local computer system may be operable to function as a thin client for allowing the user to perform remote log in to the virtual desktop computer system. For example in one embodiment the thin client may include functionality for providing a browser based graphical user interface to the Cloudware network which may be used to allow the user to remotely log in to one or more of the user s instantiated virtual appliances. Thus for example in one embodiment when the user remotely logs in to a specific instance of virtual desktop computer system running a Windows XP operating system the display on the user s thin client interface may present the user with a GUI corresponding to a typical Windows XP desktop. Using this remote desktop interface the user may perform various types of activities at the virtual desktop computer system such as for example installing removing software components to from the virtual desktop computer system installing removing virtual hardware components to from the virtual desktop computer system running software applications installed at the virtual desktop computer system storing data at the virtual desktop computer system retrieving data stored at the virtual desktop computer system and or other types of activities which may typically be performed at a desktop computer system.

In one embodiment the Cloudware system may provide the required client software for accessing the remote desktop. For example for appliances using the VNC protocol the VNC client may be downloaded from the appliance or from the Cloudware system as a Java applet. Further Ajax based remote desktop clients may be used to eliminate the need for client side remote desktop software.

In at least some embodiments an integrated virtual desktop may be displayed to the user which incorporates or includes features e.g. icons graphics text services etc. from different virtual computer systems. For example in one embodiment where a user has created a first Windows OS based virtual desktop computer system and a second MAC OS based virtual desktop computer system an integrated virtual desktop may be displayed to the user which includes icons from both the Windows OS based virtual desktop and MAC OS based virtual desktop. In one embodiment when the user clicks on a selected icon on the integrated virtual desktop e.g. to launch an application associated with the selected icon the Cloudware network may be configured or designed to automatically identify the proper virtual desktop computer system which the icon application is associated with and to automatically launch the application associated with the selected icon at the identified virtual desktop computer system in a manner which is transparent to the user. Thus for example from the user s perspective one embodiment of the integrated virtual desktop may allow the user to seamlessly launch a variety of different applications associated with different operating systems wherein different launched applications are automatically transparently and or natively executed at different virtual desktop computer systems running different native operating systems.

It will be appreciated that at least a portion of the above described features of the Cloudware network provide a variety of benefits and or advantages.

For example one advantage relates to the ability of a user to obtain access to one or more selected instances of virtual appliances from anywhere in the world. For example a user who has created a running instance of a virtual desktop computer system may is able to access the virtual desktop computer system from any location in the world which provides Internet access.

Another advantage relates to the ability to create different customized virtual desktop computer systems and or other customized virtual appliances for different purposes. For example a user may create a first customized virtual desktop computer system for personal related tasks and may create a second customized virtual desktop computer system for business related tasks. In other embodiments a user may create a customized virtual desktop computer system which is optimized for performing various activities such as for example video rendering editing complex system modeling etc. .

Another advantage relates to the relative ease by which one or more selected virtual desktop computer systems and or other customized virtual appliances may be migrated to different data centers or grids of the Cloudware network. For example in at least one embodiment a virtual appliance may be completely represented via one or more descriptor file s and or associated instructions which may be used to create one or more running instances of the virtual appliance. Accordingly it is possible to migrate a virtual appliance from a first data center at a first geographic location of the Cloudware network to a second data center at a second geographic location of the Cloudware network by simply using the descriptor file s and or associated instructions to create a running instance of the virtual appliance at the second data center. Thus for example a user who frequently travels to different geographic locations e.g. USA Europe Asia etc may desire to periodically migrate his virtual desktop computer system to a data center of the Cloudware network which is geographically proximate to the user s current location for example in order to reduce data access latency at the virtual desktop computer system. Additionally in at least one embodiment the Cloudware System may be configured or designed to automatically determine the user s current geographic location e.g. using IP address wireless signals etc. and to automatically migrate the user s virtual desktop computer system to a different data center e.g. a data center which is physically closest to the user s current location based upon various rules policies and or other criteria.

In at least one embodiment the Cloudware system may adjust the resources allocated to a virtual desktop appliance based on the historical or current usage. For example if the Cloudware System detects that the virtual desktop appliance is utilizing a relatively large amount of CPU resources the Cloudware System may respond by automatically and dynamically allocating additional CPU resources for the virtual desktop appliance. As another example if the Cloudware System detects that the virtual storage or memory associated with virtual desktop appliance is reaching full capacity the Cloudware System may respond by automatically and dynamically allocating additional storage or memory resources as needed and or may automatically take appropriate action to control or restrict storage memory usage. In at least some embodiments the actions which may be automatically and or dynamically performed by the Cloudware System may be based on various rules policies conditions events and or other criteria. In addition to other advantages this dynamic adjustment of resources may allow less skilled users to obtain optimal performance and price performance ratio.

As illustrated in the example of the Cloudware enabled global network may include for example one or more of the following or combinations thereof 

In at least one embodiment the examples of various subscribers may include but are not limited to one or more of the following or combinations thereof SMB Web 2.0 SaaS Enterprises and or other entities who may be responsible for setting up or managing IT infrastructure and or who may have active e.g. working on line web applications and or services. In at least one embodiment subscribers may have their applications operate in the cloud without the need to own or manage servers data centers network peering etc. They may deploy any desired architecture middleware including existing applications may scale applications per their needs and operate them anywhere in the world paying only for what they use.

In at least one embodiment data center operators may publish computing resources such as for example servers storage and network connectivity making them available to subscribers and or other entities . In at least one embodiment data center operators may include but are not limited to one or more of the following or combinations thereof hosting providers managed service providers enterprise datacenters and or other clouds. In one embodiment the data center operators may determine the prices for the resources they publish and or may also determine or set criteria for who may access or use specific resources which for example may range from individual subscribers e.g. when an enterprise data center adds private resources for use by other subscribers in the enterprise to general use by any subscriber. In addition data centers may publish their excess capacity or have the unused servers shutdown to conserve power until needed. In at least one embodiment the Cloudware network may be configured or designed to automatically detect a need for additional capacity at one or more data centers and may automatically respond by taking appropriate action to power up additional servers at one or more data centers which for example may have been shutdown temporarily to conserve power .

In at least one embodiment examples of different publishers may include for example one or more of the following or combinations thereof independent software vendors virtual appliance vendors infrastructure platform and tool vendors verticals etc. In at least one embodiment one or more publishers may publish in the global catalog for example appliances ready made architectures whole ready to run applications etc. In one embodiment publishers may determine and or specify various criteria relating to access and or use of published resources such as for example which subscribers and or other entities have access to what published resources at what price and or other constraints e.g. timing constraints usage constraints etc. . In at least one embodiment virtual appliances allow among other things hardware appliance vendors to provide software equivalent s of their appliances including for example firewalls load balancers security appliances etc. In at least one embodiment platform and middleware vendors may provide ready to use packages of their software that may be used without complex installation and configuration. IT professionals may productize their expertise by publishing ready to use architectures LAMP Ruby on rails J2EE including scalable versions such as clustered database servers application servers etc. Verticals may publish their applications in a ready to run form that may be delivered by managed service providers or used by customers directly.

In at least one embodiment vendors may provide value adding web services that are available to all or selected subscribers and or other entities . Examples include advanced monitoring tools billing services transaction monitors lifecycle management and policy engines storage e.g. temporary and or persistent etc.

In at least one embodiment outsourcing providers may publish their services and make them easily available on the cloud e.g. . Examples of such outsourced services may include but are not limited to one or more of the following or combinations thereof application development monitoring support application management etc.

In at least one embodiment clients may include various users e.g. end users on the Internet which for example may be connected via wired wireless laptops desktops mobile phones etc. In at least one embodiment services and applications running in the cloud may be accessed e.g. by users over existing protocols which for example may be indistinguishable from services running on traditional architectures except for example for their improved scalability availability etc. .

In at least one embodiment resource pools may provide access to various network and or computing resources such as for example one or more of the following or combinations thereof raw computing power CPUs volatile memory e.g. RAM storage e.g. persistent storage network connectivity e.g. to applications running in the cloud etc. In at least one embodiment various different resource pools may be located anywhere in the world at different physical global locations. In one embodiment individual datacenter operators may publish multiple classes of resource pools in terms of network connectivity power services etc. In one embodiment commodity servers may be configured or adapted for use as resource pools for example via installation and use of an AppLogic execution engine. In at least one embodiment other resources such as for example 3party clouds such as for example Amazon s EC2 and S3 web based services may also be published by providing the appropriate interfaces. In one embodiment the resource pools may be controlled by the Infrastructure Delivery Network via web services interfaces.

In at least one embodiment the global catalog may be implemented as a worldwide distributed catalog service for enabling various publishers to publish or make their appliances architectures and applications available to subscribers and or other entities . In at least one embodiment multiple catalogs may be managed and accessed by subscribers and or other desired entities allowing software publishers to organize their catalogs and specialize them for their target markets. In at least one embodiment the global catalog may include versioning and or distributed caching systems which allow all or selected catalogs to be available to any or selected applications anywhere in the world or at selected locations .

In at least one embodiment the control interface may include a set of user interfaces and APIs for controlling applications and services running in the cloud. In at least one embodiment the control interface may include for example one or more of the following or combinations thereof subscriber portals dashboards monitoring screens infrastructure design tools development tools e.g. Eclipse plugins command and control web based interfaces etc. In some embodiments the control interface may include web services APIs for programming the cloud.

In at least one embodiment the infrastructure delivery network may be configured or designed to aggregate the different components of the cloud and their separate instances in a cohesive distributed cloud. In at least one embodiment the infrastructure delivery network may include functionality for providing for example one or more of the following or combinations thereof authentication access controls registration of resource pools control interfaces catalogs etc.

In at least one embodiment the infrastructure delivery network may include functionality for providing for example one or more of the following or combinations thereof dynamically and automatically deploying infrastructure from one or more catalogs to selected resource pools e.g. as necessary to provide the services specified through the control interface providing data source for the integrated web services facilitating the interactions between components of the cloud managing complex transactions during deployment and migration etc. In at least one embodiment the infrastructure delivery network may be implemented as distributed service providing for example resilient highly available and localized services for maintaining proper operations of the cloud.

In at least one embodiment various embodiments of Cloudware may be configured or designed to allow or enable open cloud computing where individuals and companies will be able to add their distinct capabilities to the cloud. In at least one embodiment Cloudware s flexible architecture empowers customers to build and run large scale applications in the cloud without compromising their choices of operating system middleware security location architecture and vendors. Additionally in at least some embodiments Cloudware architecture may be configured or designed to operate across numerous data centers operating systems and even include important issues like security and high availability to meet the needs for enterprise computing.

Using Cloudware s flexible architecture there is no need to make compromises when using cloud computing. For example in at least one embodiment the Cloudware architecture defines interfaces for resources software and controls that run existing code and middleware.

Generally when a conventional vendor refer to cloud the vendor is referring specifically to that vendor s customized cloud. Typically such customized vendor specific clouds are proprietary and associated exclusively with that vendor s customized data centers. Additionally such customized vendor specific clouds typically do not allow for access or participation by other 3party data center operators and typically do not provide infrastructure within the vendor specific cloud other than that which the vendor has specifically provided. Additionally such vendor specific clouds typically require that 3party software developers utilize the vendor s published APIs when writing software for use with that vendor s specific cloud.

In contrast in at least one embodiment the Cloudware architecture described herein not only provides access to a variety of products and or services but may also be configured or designed to allow 3party entities e.g. independent companies vendors etc. to design and provide inclusive cloud based service within the Cloudware network.

In at least one embodiment because of its open nature the Cloudware Architecture may be configured or designed to allow any existing web applications to run in a Cloudware based cloud with no limitations as to specific language software libraries and or interface.

In at least one embodiment the Cloudware network may be open to all entities such as for example data center operators e.g. who can provide resources appliance vendors system integrators managed service providers developers etc.

Thus one advantage of the Cloudware architecture is that everyone may benefit by being able to combine technologies to deliver a better service to the end user.

In at least one embodiment Cloudware architecture provides a flexible architecture empowering customers to build and run large scale applications in the cloud without compromising their choices of operating system middleware security location architecture and vendors.

In at least one embodiment aspects of the Cloudware architecture may be based upon technology proven in 3Tera s award winning AppLogic grid operating system. In at least one embodiment the Cloudware architecture may incorporate various types of distributed computing resources such as for example storage computing connectivity security etc. Further the Cloudware architecture may define and manage how each different resource relates to the other resources in a far reaching architecture for enabling an open cloud computing system.

In one embodiment the Cloudware architecture may be implemented in a manner which is non vendor specific so that any third party vendor s software can be incorporated in a Cloudware enabled system. Additionally the Cloudware architecture may be implemented in a manner which supports all or selected operating systems such as for example Linux Solaris Windows etc. Additional features include for example choice of multiple data centers worldwide pre built MySQL clusters database replication appliances and NAS integration with third party storage solutions etc.

In at least one embodiment the Cloudware architecture may be implemented in a manner which utilizes 3Tera s AppLogic grid operating system for providing a true distributed utility computing services. In at least one embodiment the Cloudware architecture enables commodity servers to be converted into scalable grids on which users can visually operate deploy and scale transactional Web applications for example without any modification of code. Utilizing various embodiments of the Cloudware architecture Software as a Service providers Web 2.0 companies enterprises and open source developers can now get new online services quickly to market by utilizing resources from commodity hosting providers on a pay as you go basis while maintaining complete control of applications including visual operation scaling and on demand resource provisioning.

The global panel may be an on line control panel for customers who manage applications across multiple AppLogic grids. In at least one embodiment it presents a global list of applications aggregating the applications from multiple grids in a single view. It allows the grid operator to focus on the applications rather than on the locations where they run. The global panel may be intended to be a production quality application running on AppLogic . It may be available to all or selected customers who want to use it. An example embodiment of the global panel graphical user interface GUI may be illustrated for example in .

According to specific embodiments the global user dashboard page may be accessible to various entities or Cloudware customers such as for example data center operators end users publishers e.g. publishers of applications appliances etc. In the example of it is assumed that a user e.g. NetClime has logged into the Cloudware System and that at least a portion of the content of global user dashboard page has been dynamically generated for that particular user.

As shown in the example of user dashboard page includes a variety of different types of content which may be related to or associated with one or more applications which the user has deployed at one or more globally distributed data centers of the Cloudware network. Examples of such content may include at least a portion of the various content previously described and illustrated with respect to for example.

In at least one embodiment the Cloudware System may be operable acquire user specific utility computing information e.g. associated with a specific user associated with a related group of users associated with a given business entity etc. from multiple different geographically distributed data centers and or from multiple different geographically distributed server grids and may aggregate or consolidate selected portions of the acquired information for presentation via the consolidated user dashboard page . In this way for example the user may readily observe and or assess e.g. via observation of the content displayed on the user s consolidated dashboard page application deployment details status information etc. which are related to the various distributed applications which the user has deployed at one or more geographically distributed data centers and or geographically distributed server grids of the global utility computing network.

For example as shown in the example of user dashboard page includes a variety of different types of content such as for example one or more of the following or combinations thereof 

In at least one embodiment the global user dashboard may be implemented as the default dashboard for grids either being integrated in the grid controller or running on the grid optionally as an app the controller GUT can forward to the global panel if the global panel may be running or provide local dashboard if not . In one embodiment it may be operable to allowing peer type clustering of any number of private grids at least two or simply all grids running a copy of the global panel. This may be further coupled with the ability to request additional servers for grids and optionally with the ability to order additional grids in different locations. Further in at least one embodiment the global user dashboard may be used as the account control panel of Cloudware for shared services. For example grid s ACL based permissions may provide the security and isolation to enable using the global panel as the account dashboard for all customers of the Cloudware service

The global user dashboard may run on multiple grids for high availability and locality the grids may or may not be the grids listed in Locations . Multiple different global user dashboards of the same account may be able to synchronize with each other so configuration changes made on one are propagated on the other. In most other aspects the global user dashboards may preferably remain independently operating e.g. their monitoring . There may be no shared state so this may be easy.

The global user dashboard may preferably monitor all Locations configured in it and show the state of each as well as an overall health indicator. In addition the global user dashboard may preferably monitor any other instances of the global user dashboard for the same account and report their state in a similar fashion.

Whenever a change of state may be detected the global user dashboard may preferably send notifications. At least e mail may preferably be supported with SNMP and SMS on the wishlist.

It may be desirable to add support for monitoring applications. This may provide good distributed monitoring. In at least one embodiment one may also define deployment type and entry points monitoring metadata in the applications themselves.

The global user dashboard may preferably be available for use in different deployment models such as for example 

In at least one embodiment the global user dashboard may be operable to manage global account logins and or to improve on the authentication process of the grids or in their security aspects e.g. ACL based access .

The global user dashboard may maintain a list of authorized users login by user name and password with lockout the user name may be in e mail format .

In at least one embodiment the global user dashboard accesses other instances of the global user dashboard for the same account over a web services interface https . The global user dashboard may be configured via properties with a special admin user which can be used to create initial users. The admin user cannot be changed from the global user dashboard user interface it can however be disabled through properties the desire may be to keep it inactive after the initial setup until needed . The global user dashboard may be configured via properties with user and password for SMTP authentication optional . It may also be possible to allow uploading a password protected key and ask the user to unlock it interactively keeping the unlocked key in a key agent until the user logs off subject to automatic logoff timeout given the near statelessness of HTTP based sessions .

The user interface of the global user dashboard may be web based. It comprises a main screen with a dashboard panel on the top and tabbed view below. The dashboard panel comprises three sub panels summary locations and messages. The tabbed views include applications locations and support. Applications view may be the main operational view.

Folders for each location that has the show templates selected. If only one location has it don t show a folder for it. Sub folders may be arranged by category of the template. Leaves are templates shown with icon and name.

In addition the catalog panel may be extended or replaced with a catalog from a central or external catalog service such as described elsewhere in this disclosure.

Monitoring may include a dashboard tracking the performance and operation of all or selected applications among the applications visible in the applications list.

A location may be in a nutshell a grid. Each location entry provides sufficient information to access the grid submit commands to it and or open the user interface on it. In addition Global user dashboard may preferably monitor all locations and report any problems e.g. grid no longer available .

In at least one embodiment geo location may be find able with varying degrees of precision by IP address. One may might be able to fill it in automatically when the controller IP address may be entered.

The global user dashboard may be clustered for high availability and access. This may be useful in general but even more when the GlobalPanel may be deployed on customer s own grids. As a nice bonus the global user dashboard now also monitors all known grids of that customer and having two or more global user dashboards running in different locations may preferably provide enough redundancy.

The panel sites list includes the list of IP addresses plus any authentication data TBD so that the panels can synchronize with each other. For each entry one have 

In at least one embodiment it may be desirable to synchronize the locations list and when defined preferences as well as the panel sites list itself. In its simplest form the synchronization may be performed with rsync with each entry to be synchronized e.g. location being represented in a separate file deleted entries don t remove the file just contain metadata inside saying the entry may be deleted . Latest modification time wins or use unison or anything else that replicates like for example couchDB openldap or master master MySQL .

Synch of data between panels if data is kept in text files that are sufficiently well partitioned no more than one property value per line the text based merge as used in version control systems may do well enough. If merge fails then apply the latest date wins approach and show a warning.

Shows the current notifications rules and allows configuring notifications button Edit settings . . . or similar .

Overall state enabled disabled it may be useful to globally disable the notifications e.g. when maintenance starts may be re enabled manually or on time elapsed since disabled e.g. disable notifications when starting maintenance set re enable timer to maintenance window .

Similar to AppLogic 2.3.9 support tab OEM kit may be installed on the volume in order to customize the appearance and set of links

In at least one embodiment Add may not be a per user operation as the text above implies. One may need either a separate add button or have an empty row in the users list with all fields empty except the user name which may be replaced by a Add new user hyperlink

For example as illustrated in the example embodiment of it is assumed that the user has selected e.g. by left clicking right clicking double clicking etc. the highlighted San Francisco server grid record to access a dynamic GUI e.g. display window or overlay layer which for example may be configured or designed to enable the user to perform additional operations with regard to the currently selected server grid e.g. San Francisco such as for example one or more of the following or combinations thereof 

In at least one embodiment graphical user interface GUI may include additional first outing for enabling the user to selectively add modify and or delete e.g. via GUI portion server grids to from the user s currently displayed server grid list e.g. . For example the user may manually add a new data center or server grid to the users current server grid list by selecting e.g. clicking on the icon displayed in GUT portion . After adding the new data center server grid to the users current server grid list the newly added data center server grid will then be available for subsequent use by the user e.g. for deployment of one or more applications .

In at least one embodiment GUIs and or may be implemented as a web page which may be accessible to users via conventional Web browsers such as Microsoft Internet Explorer Mozilla Firefox etc.

As illustrated in the example embodiment of infrastructure editor status dashboard page includes a variety of different types of content which may be related to or associated with one or more applications and or appliances. Examples of such content may include but are not limited to one or more of the various different types of content previously illustrated and described for example with respect to and or other portions of this disclosure.

In the specific example of it is assumed that a user has accessed GUI e.g. via the Cloudware network in order to edit and or monitor the status of various appliances e.g. which are part of a distributed application e.g. Bugzilla that has been deployed at a selected server grid.

According to specific embodiments the infrastructure editor status dashboard page may be accessible to various entities or customers such as for example data center operators server grid operators end users developers IT staff system administrators publishers e.g. publishers of applications appliances etc. In at least one embodiment at least a portion of the content of infrastructure editor status dashboard page may dynamically generated e.g. for a given user entity account .

In at least one embodiment the infrastructure editor status dashboard GUI may be configured or designed to be operable in at least two modes of operation 1 editor mode e.g. for enabling the user to create configure edit manage control and or otherwise manipulate various appliances and or applications and 2 status monitoring mode e.g. for enabling the user to monitor the current operational status of various appliances and or applications . In at least one embodiment the infrastructure editor status dashboard GUI may be configured or designed to simultaneously operate in both editor mode and status monitoring mode.

For example as illustrated in the example embodiment of the status monitoring mode of the infrastructure editor status dashboard GUI may be operable to acquire and display updated virtual appliance status information e.g. starting maintenance etc. . At the same time the editor mode of the infrastructure editor status dashboard GUI may be operable to enable a user to modify or edit the configuration of one or more displayed virtual appliances e.g. such as for example appliances which are not currently running or started .

As illustrated in the example embodiment of infrastructure editor status dashboard page includes a variety of different types of content which may be related to or associated with one or more applications and or appliances. Examples of such content may include but are not limited to one or more of the various different types of content previously illustrated and described for example with respect to and or other portions of this disclosure.

In at least one embodiment the infrastructure editor status dashboard GUI may be configured or designed to be operable in at least two modes of operation 1 editor mode e.g. for enabling the user to create configure edit manage control and or otherwise manipulate various appliances and or applications and 2 status monitoring mode e.g. for enabling the user to monitor the current operational status of various appliances and or applications . In at least one embodiment the infrastructure editor status dashboard GUI may be configured or designed to simultaneously operate in both editor mode and status monitoring mode.

For example as illustrated in the example embodiment of the status monitoring mode of the infrastructure editor status dashboard GUI may be operable to acquire and display updated virtual appliance status information e.g. starting stopping error etc. . Additionally in at least one embodiment the editor mode of the infrastructure editor status dashboard GUI may concurrently be operable to enable a user to modify or edit the configuration of one or more displayed virtual appliances such as for example appliances which are not currently running or started appliances showing error conditions e.g. etc. Further in at least one embodiment the infrastructure editor status dashboard GUI may be operable to enable the user to edit or modify the displayed application e.g by dragging and dropping additional virtual appliances from the appliance catalogue onto the application editor canvas concurrently while GUT displays updated virtual appliance status information.

As illustrated in the example embodiment of application editor GUI includes window or frame region which may be configured or designed as a text display console that is operable to display textual information relating to various application related operations e.g. current and or historical which 1 have been performed 2 are currently being performed and or 3 are scheduled to be performed e.g. at the server grid where the instance of the application is currently running Examples of such textual information may include for example log file information transcript information etc.

Additionally as illustrated in the example embodiment of application editor GUI may include functionality for enabling a user to access additional information for a selected appliance e.g. via display of overlay window layer . For example as illustrated in the example embodiment of when the user selects virtual appliance e.g. via mouse click operation the application editor GUI may respond by dynamically displaying overlay window layer and populating the displayed overlay window layer with additional content information relating to the selected virtual appliance.

In the specific example embodiment of it is assumed that a user has selected a specific application e.g. from the displayed application list to be accessed via application editor GUI portion .

One notable feature of the application editor GUI is it s ability to enable a user to create display and edit different annotation zones e.g. which for example may be utilized for annotating selected regions or portions of the virtual application canvas in a manner similar to the way software engineers may annotate computer software code.

As illustrated in the example embodiment of the various annotation zones may include graphical content e.g. visually displayed regions of differing colors shadings boundaries etc. and or textual content e.g. DMZ Ingress Web Tier Data Tier etc. . In at least one embodiment graphical and or textual annotations which are added to the application canvas may have no effect on the operation of the application and or its components. However as will readily be appreciated the visual annotations facilitate a more comprehensive understanding of the application s design and enter relationship between the various components e.g. virtual appliances virtual networks etc. of the application.

In some embodiments a least a portion of the annotation zones may be automatically created and or populated e.g. by the server grid where the application is deployed by the Cloudware System etc. . In some embodiments a least a portion of the annotation zones may be manually created e.g. by one or more users . Such a feature advantageously enables and facilitates multi user collaboration in a virtualized application editing environment.

Additionally as illustrated in the example embodiment of application editor GUI may be operable to provide a multi tabbed appliance Instance Settings property sheet which enables a user to specialize or customize an appliance instance for its role in the application.

For example as illustrated in the example embodiment of user selection of virtual appliance may automatically trigger the display of Instance Settings property sheet for enabling the user to to configure and or edit various properties or characteristics of the selected virtual appliance.

As illustrated in the example embodiment of the Instance Settings property sheet includes a Notes tab which provides access to Notes window region which for example may be utilized for providing notes annotations comments and or documentation relating to the selected virtual appliance. In some embodiments a least a portion of the information e.g. included in the Notes window region of the Instance Settings property sheet may be automatically created and or populated.

In at least one embodiment the Notes window region may be utilized to store notes annotations comments and or documentation relating to various features uses and or aspects of the virtual appliance which may serve as an embedded runbook for that particular appliance. In at least one embodiment functionality may be provided for enabling a user to generate a Documentation Manual for the appliance e.g. by clicking on the Generate Documentation Manual button of window wherein at least a portion of the documentation manual is generated using the information contained in the Notes window region .

In at least one embodiment ADL is a language for describing applications within the AppLogic application model where applications are built out of multiple components with each component being an instance of a virtual appliance with its own OS and application software. In the interpretation of ADL host and hardware or any type of resource do not necessarily correspond to physical resources they may be virtual devices that share the same hardware.

ADL may be based on UDL a generic language for describing hierarchically structured data in plain ASCII text form. One may find descriptions of UDL in various references.

Here are the smallest units of grammar used in the ADL language defined as Perl style regular expressions 

ADL may be line oriented that may be it treats the newline character differently from other whitespace. Please note that in all the syntax descriptions below the newlines are significant and the presence of a newline in a syntax example means that it may be required.

entity type may be one of component assembly or package and identifies the type of descriptor that may be contained in the file.

attributes and subentities may be an unordered set which includes any number of attributes and sub entities. Each attribute may be on a single line and has the form name value . where name may be an identifier IDENT and value may be a string value STR . Each sub entity has one of the following forms 

attributes may be a comma separated list of name value pairs. Note that attributes can also be specified in the block following the entity heading line. When attributes are specified on the same line as the entity definition after the colon binary attributes can be specified without a value just the attribute name meaning set to 1 e.g.

Each subentity type defines a namespace and within that namespace only one subentity of a given name can exist. That applies to the sub entities with no type at all one may think of the subentities with no type as having the empty string as the type .

Specifying attributes both in line and in the block may be allowed it may be avoided except in the cases where one particular attribute may preferably stand out e.g. the class attribute in a subordinate component s specification otherwise for simpler sub entities with few attributes the inline syntax may be preferred for more complex entities that have many attributes and or sub entities use the block.

The component descriptor includes one component entity defining either a singleton component or an instantiable class of components. There may be no difference between the definition of a singleton and a class except that instantiable classes are required to reside in a library of components referred to as a catalog . Also either type of component can be used in an assembly but a singleton can appear only once in the structure of an application while an instantiable component can be used multiple times.

Below are two examples of the component descriptor structure the first example may be the current standard form the second example shows the old format of the boot information specification. The old format may be fully supported for compatibility with existing catalog appliances.

All of the attributes are also valid properties of the component which can be overridden in an assembly that includes the component. Note that the attribute names are prefixed with a dot to avoid name conflicts with regular properties see the property entity below .

The table below may be a summary of the valid sub entities in a component followed by sections that explain each sub entity in detail.

Defines a volume that includes a file system used by the component. At least one volume entity may preferably appear in each component. The volume entity has the following attributes 

A volume entity that has no class attribute also defines a configurable property on the boundary of the component which can be set the same way as other properties of the component see the property entity below. The mandatory attribute for such volumes works the same way as the mandatory attribute for properties. A volume property may be set to the logical name of one of the application s volumes as found in the application s package descriptor . Note that this means volumes and properties share namespace and one cannot define a volume and a property of the same name.

The resource entities define the requirements of the component towards the hardware resources that may preferably be made available for it to run. The name of a resource entity may preferably be one of cpu mem or bw. The definition of these entities may be as follows 

The resource entities are mandatory all may preferably be specified in a component s description and all may preferably have the min and the max value specified. The abs value may be omitted and may be assumed to be equal to min by default.

These entities define terminals of the component which are network interfaces intended for connection with other components in the same application. A terminal may be a special kind of network interface it may be used only for one specific protocol and only in one direction direction here refers to flow of control not of data e.g. an output terminal may be an interface used by a protocol client while an input terminal may be for a server . The presence of a terminal entity automatically defines a host name that resolves to the remote side of the connection in which this terminal participates. The terminal entities have the following attributes 

This entity type may be used with one of two fixed names external and default . It may be used to enable and configure network interfaces that are not meant for connecting to other components as the terminals are see above and have no restrictions on the type of connections that can be made. The syntax for the interface entities may be as follows 

The interface external entry enables the device named eth0 to be used as the external network interface of the component accessible from outside the application . If enabled eth0 may not be used for terminals and its IP configuration may not be set up automatically. Instead it may be expected that properties are defined to configure the network adapter.

The interface default entry enables configuring an unused network interface for unrestricted use with an automatically assigned IP address on the same subnet as the ones used for terminal connections. The assigned IP address may be made available to the AppLogic controller as the IP address of the component this can be used for maintenance logins.

The property entity defines a configurable property of the component. Any parameter that may need to be configured can be defined as a property. The values of properties are made available to the component s software in the following ways 

Note that since a volume can appear as a configurable property on the boundary volumes and properties share namespace and one cannot define both a volume and a property of the same name.

In at least one embodiment this parameter may be used to define the configuration files that need to be checked for property markup and updated accordingly. This entity may be an array each entry defines one configuration file and has these attributes 

This entity includes the boot information needed to start the component in the virtual environment for which it may be designed. The virtualization entity supersedes the kernel os info definitions and may be used instead of them. The presence of this entity also indicates a new style component descriptor and turns off the compatibility mode which includes forced .config mode volfix.

In one embodiment this parameter relates to virtualization. The presence of a kernel or os info sub entity in the descriptor may indicate an old descriptor and the volfix configuration mode may be forced automatically.

This entity includes OS specific boot information its contents depend on the value of the .os type attribute of the component. The keywords kernel and os info are equivalent kernel may be retained for backward compatibility.

initrd filename the name of the ramdisk filesystem image to use during boot. The kernel image file and the ramdisk image file are typically produced as a result of building the Linux kernel.

The legacy OS type may be used for all hardware assisted virtual machines. The name value pairs are not interpreted they are passed on to the HVM emulator directly. Examples of parameters supported by the qemu emulator used in XEN include acpi 0 1 apic 0 1 pae 0 1 etc.

The assembly descriptor includes one assembly entity defining a new component that comprises several components which can be either simple components or other assemblies. An assembly that may be made up entirely of instantiable components all residing in a catalog may be itself considered instantiable. If a singleton component appears anywhere in an assembly the assembly itself may be a singleton and cannot be moved into a catalog.

The following attributes are defined for an assembly they have the same meaning as their counterparts for a simple component 

The order of entities in the assembly may not be important and all of the sub entities are optional except that an assembly may preferably have at least one subordinate entity.

Here may be a summary of the sub entities of the assembly entity followed by sub sections defining each one in detail 

The terminal entities support a single attribute mandatory. Specifying this attribute means that the terminal may preferably be connected mandatory terminals may trigger a compilation error in an assembly that includes a component with such a terminal left unconnected. Note that specifying the mandatory attribute for an assembly may not be necessary if the subordinate component s terminal to which it may be connected may be already mandatory.

An assembly can have any number of terminals except for the top level assembly of an application which may preferably have no terminals.

The property entity defines a property of the assembly. Each property may preferably be connected to at least one property of a subordinate component see the subordinate entities below. A property may have a default value identified by the dflt attribute. The default if specified overrides the default value in the subordinate components to which the property may be connected. Alternatively mandatory may be specified requiring that the property be set from outside e.g. in an outer assembly even if the subordinate components to which it may be connected have a default value for the property.

This entity efines a property of the assembly similar to the property entity. The property defined with the volume entity may preferably be connected to at least one volume property on a subordinate component see the subordinate entities below. The property defined by a volume entity may have the mandatory attribute specified requiring it to be set even if the components volumes to which it may be connected do not have the mandatory attribute set. Unlike regular properties default cannot be specified for a volume.

The subordinate entity defines a subordinate component in the assembly. Each subordinate can have any number of attributes each corresponding to a property including volume properties of the component that may be overridden with the specified value. In addition the following pre defined attributes with a special meaning exist for each subordinate all having a name that begins with a . to distinguish them from regular properties 

All attribute names other than the pre defined ones are considered to be property names of the subordinate component that need to be set to the specified value this includes the predefined attributes of the subordinate component .boot tout .migrateable .server .standby as well as the component specific properties defined in it by the property or the volume entities see the component descriptor syntax .

A special type of value may be defined indicating that the property may be connected to the assembly s boundary .name where name may be the name of one of the property or volume entities in the assembly. If a property has to be set to a literal value that begins with the . characters the value may preferably be quoted to ensure that it may not be interpreted as a property connection. More than one subordinate property can be connected to the same boundary property and all such properties get the default value from the boundary property definition if none may be provided in an outer scope assembly. The .name can be used for the pre defined attributes of the subordinate as well making them regular properties on the assembly boundary.

The subordinate entity in an assembly also accepts the resource sub entities mem cpu and bw with the same attributes as defined in the Component Descriptor Syntax section. When applied to a subordinate that may be a simple component they override the resource settings in that component. The override may preferably remain within the limits of the range defined in the component e.g. the new range may preferably no wider than the old one and may preferably fit entirely into the old one . When applied to a subordinate that may be an assembly the specified resources are distributed pro rata according to the relative weight of the resource requirements in each of that assembly s subordinates. If a resource setting for a subordinate assembly causes a component to receive a resource setting that may be outside of the min max range defined for it an error may be reported by the ADL linker.

This defines the assembly s connection table. The connections entity may be an array entity and each array element may be an association in the form x y where x and y identify two terminals to be connected each terminal identifier comprises a subordinate name and a terminal name separated by a . character. Terminals that are to be exposed as terminals of the assembly itself exterior connections are also defined in in the same table with the following syntax 

Both syntax variants are equivalent and mean that the terminal strm name of subordinate sub name may be to be visible as atrm name on the assembly atrm name may preferably correspond to an input or output entity defined in the assembly . Since an input terminal may be a network server and an output terminal may be a client the following rules apply 

The package descriptor may be a table of contents file that defines the contents of an application or of a component library a catalog . The package descriptor also includes references to volume images that are outside the application s root directory the application may be installed on the grid controller while the volumes may reside on any of the grid s servers . For applications it also includes the configuration settingscomponent of the application.

An application package descriptor may also contain an entity of type assembly with the same structure as the one found in an assembly descriptor except that it cannot have terminals and properties on the boundary. It may be used as the topmost component of the application containing the property settings for the application itself with a single subordinate that may be the application s main assembly.

The package sub entity in a package descriptor may be a reference to another package. In at least one embodiment only application packages can have references to other packages. The references are to catalog packages that are part of the application itself no references to global catalogs are added to an application s package descriptor.

The volume sub entity may be a reference to a volume image that may be directly assigned for use by a component of the application. No attributes are defined for this entity. Volumes defined in this manner are stored with the application itself e.g. when it may be archived moved or copied . These application volumes are assigned to placeholder volumes of component instances using the regular property setting syntax in an assembly.

Note that the volume entities in a package descriptor are the only explicit reference to volumes that belong to the application. However each component class defined in the application scope or in an application specific catalog also implicitly refers to one or more volumes that belong to the same application each volume listed in such components descriptors that has the class attribute has a corresponding template volume considered an integral part of the application.

This sub entity may be used to define protocol filters. It can appear either in a catalog s package descriptor or in an application package descriptor. If any catalog may be used in an application all filters defined in it are available for use in the application whether by components coming from that catalog or by components defined in the application itself .

If the same protocol filter may be defined in more than one package descriptor all definitions may preferably match exactly otherwise an error may be reported by the ADL compiler. The well known protocols filter definitions are defined in the global catalog that may be part of any AppLogic installation these include http ftp smtp ssh etc.

The name of each protocol entity may be a name that can be used in the protocol xxx attribute of a terminal see the component descriptor syntax .

The protocol subentity has a single attribute filter with a string value that defines the protocol constraints e.g. 

Note the syntax of the protocol filter string may not be part of this specification it may not be interpreted by the ADL compiler.

The resources sub entity defines what may be available for the application to use on the grid of servers on which it may be installed. It includes the following sub entities 

The property markup syntax may be used to identify text in ASCII configuration files of a component as being configurable properties which are modified automatically to match the component s configuration within the application before the component may be started. All files identified in the cfgfiles array in a component are scanned for property markup and updated as needed each time the application may be being prepared to start.

Note that the property markup may be only supported for appliances that use the volfix configuration mode.

A configuration file may be eligible for inserting property markup into it if the file s syntax meets the following conditions 

The following file formats are known to comply with the above requirements and may be preferable in one or more embodiments 

To handle non instrumental files the recommended approach may be to write a bash or Perl script that updates the config file on boot and instrument the script itself.

The presence of a prop string on a line of text in the configuration file means that this line includes one or more property values. Usually the prop string and the rest of the line of text are made invisible to the application that uses this configuration file by making it appear as a comment e.g. if the configuration file may be a Perl script this might look like 

val1 name1 indicates that the first occurrence of the string val1 on this line may be to be treated as the value of the property name1 and replaced whenever that property needs to be changed.

val2 name2 indicates that the first occurrence of the string val2 following the first occurrence of val1 may be the value of the property name2 etc.

If the name in a val name pair may be the string the string val may be simply ignored. This may be used to skip parts of the configuration data that might otherwise match a property value e.g. a markup like this 

may cause the 1 in x1 to be considered the value of the property val . To make the string 1 that follows the sign be the property value the markup has to be 

The special property name may be also used in case the property value may be the empty string e.g. in the following markup the property may be the empty string that follows the x1 string 

If a value includes punctuation characters that are part of the markup syntax colon comma space the value may preferably be quoted using the double quote syntax that may be defined for the ADL descriptor files.

This markup may be used for configuration files that do not allow comment text to appear on the same line as the value that needs to be exposed as a modifiable property. It may be similar to the inline syntax but it indicates that the text on the line that follows the one on which the markup appears may be to be searched for matching strings not the current line.

This markup may be used for configuration files in which the newline character may not be considered different from other whitespace and updates of the file may cause newlines to be added or removed at any place where un quoted whitespace occurs. For this type of markup a closing sequence may be required to indicate the end of the list of val name pairs. Newlines are allowed between the val name pairs. All text following the closing mark regardless of newlines may be searched for strings matching the values until all values are found or until 1K of text may be read for each val name pair if the latter occurs without finding all values an error may be reported . Note that each property value may be still expected to reside on a single line.

Some configuration files allow characters that have a special meaning meta characters to be quoted in a way that they lose their special meaning and become part of normal data. The ADL property update code in the Volume Fixup utility may be aware of quoting and may maintain it when property values are updated.

Whenever a property value includes such escaped characters they may preferably appear in the same exact way both in the markup which may be inside a comment section in the file and in the actual text even if these characters need to be escaped only in the normal config file text or only in the comment . For example the character doesn t have a special meaning in HTML comments but it has to be escaped in HTML data e.g. 

may not be valid even though may be OK to appear in the comment and may preferably be re done this way 

The quoting of the data values may be in different formats depending on the file type as specified by the quoting attribute see the component descriptor syntax . This quoting may be independent of the C style double quotes used by the markup syntax itself to enclose a property value the latter may be always done with the C style double quotes and may be superimposed on top of the former e.g. the string abc def which may be quoted as abc def for a C file may appear as follows in the markup 

The component descriptor syntax allows specifying a single quoting style for a config file which applies to the entire file. This may not be sufficient to cover for cases when a single file has two or more meta character quoting methods depending on context e.g. in an HTML style regularly the . . . sequence may be used to quote special characters but in URLs the xx hex coded quoting may be used.

To provide for cases like this a per property override can be defined as an extension of the markup syntax e.g. 

Additional meta character quoting styles can be added such as for example one or more of the following or combinations thereof 

The Application Configuration property sheet allows one to configure the settings of the application as a whole. If one may look at the entire application as a single appliance these are its instance settings.

For a well built application these settings are the only configuration that one may need to change when starting a new instance of the application e.g. one may need to do that if one may have made a copy of the application or one may have moved the application from another AppLogic system .

In addition to the application settings this property sheet includes some additional elements such as the application management panel and the protocols settings.

This property sheet may be very similar to the Instance Settings property sheet except it affects the settings of the application as a whole.

A icon may be shown to the right of the application name designating that the application may be locked. When an application may be locked it may not be edited or viewed within the Editor. See Application and Class Locking Reference for more information.

Unique numeric identifier of the application used internally by AppLogic . It may be assigned automatically when the application may be created.

URL where the documentation for the application can be found. The URL may be opened by clicking on the Open URL text to the right of the field.

Although one may cannot change the application name here one may rename the application from the Installed Applications screen.

The Resources tab allows one to control how much resources the application requires and may be allowed to take.

By default AppLogic calculates the resource range of the application based on the resource ranges of all appliances used in the application.

If one may don t want to constrain the application further or simply don t know yet what constraints one may want leave the default settings uncheck all constraints .

AppLogic provides two ways to constrain further the amount of resources to be allocated to the application by number of servers or by resource range.

In addition one may select a subset of servers in the system on which the application can be scheduled. Such constraints allow one to specialize this particular instance of the application for production and sandbox testing environments.

AppLogic determines the actual amount of resources to be given to an application when one may start the application. Whatever resources are available and or specified when starting the application may preferably fit within the range defined here. See Starting Applications for more details.

one may fix the exact amount of resources to be used when starting the application by specifying the maximum values equal to the minimum. This may ensure that a no freedom may be given to the AppLogic scheduler b the application may not start unless at least that much resources are available and c the application may take no more than that much resources.

On this screen one may only reduce the resource range specify a higher minimum and or lower maximum for resources.

Portion of CPU or number of CPUs to be allocated for the application. Fractional amounts can be specified as a decimal number e.g. 0.5 or 3.5 . Whole CPUs are specified simply as an integer e.g. 12 .

Amount of memory to be allocated for the application. The amount can be specified as an integer value in Megabytes e.g. 512 M or in Gigabytes e.g. 9 G .

Amount of network bandwidth to be allocated for this application total for all terminals interfaces including the internal communication inside the application . The amount can be specified as an integer value in Megabits sec e.g. 10 M or in Gigabits sec e.g. 1 G .

A range can be specified for each resource type. The range defines the normal operating parameters desired for the application in production environment.

The minimum amount of a resource that the application needs to work at all. This may be useful to allow running the application in functional testing environments where the application may not be expected to run under production load and therefore can run with much less resources. Contrast this with the Default below which may be amount of resources needed for production use.

The maximum amount of a resource that the application may be allowed to take. Typically this may be the maximum that the application can use e.g. giving it more resources may not increase performance . The application may not be allocated more than the specified maximum amount ensuring that it may not be able to take resources away from other applications think of it as a quota.

The minimum amount of a resource that the application may be provided with for normal operation in production environments. The application may not be started unless at least that much can be allocated for it. Specifying a default ensures that the application may work within certain guaranteed resource amount think of it as a service level agreement SLA for that resource.

One may easily see which values override the defaults they are displayed in bold. If one wants to restore the default value for a given resource use the restore button next to the value.

One may also select on which particular servers of the system one may would like the application to run.

This may be an advanced option that may be useful when one may want to run several applications on the same system and the results produced by the AppLogic scheduler are not satisfactory. In most cases one may preferably leave this constraint disabled.

Many applications don t have any configurable volumes all application volumes are assigned internally in the application so there would be nothing to configure.

Being able to configure volumes on the application may be useful in the cases when the application has more than one actual volume for a given volume need. For example an e commerce application may have a test database and a production database volumes. In this case the User Volumes tab allow one to specify which actual volume one may want to configure as the database volume.

If one wants to add or remove actual application volumes or access one of the application volumes in order to upload and or download files to from it press the Manage Volumes button.

If one wants to add or remove placeholder application volumes volume roles close this property sheet and edit the application boundary by right clicking on the editor canvas and selecting Edit Application Boundary from the menu. See Class Editor for details.

The info button next to the volume if present gives one may information about the volume requirements e.g. read only shared etc. .

The Properties tab allows one to set values for properties of the application allowing one to specialize this instance of the application. This may be useful for configuring location specific parameters such as IP addresses and for configuring tuning parameters such as cache sizes.

The default values of the properties are shown in normal font weight. Property values explicitly configured for this application are in bold.

For information on the property its type and allowed values select the info button . To restore the default value of a property press the restore button use the Reset All button to reset the values of all properties to their defaults .

If one wants to add or remove application properties close this property sheet and edit the application boundary by right clicking on the editor canvas and selecting Edit Class from the menu. See Class Editor for details.

The Protocols tab shows the full set of protocols available for defining appliance terminal types. This may not be a configurable application settings e.g. it may not be something that one may want to change from one instance of the application to another but rather an advanced option for configuring appliances in the application scope Protocols are on a separate tab for convenience although they belong to the application configuration and may be part of the application boundary property sheet .

This may be useful when one may are defining new appliances and want to know what protocol types are available or want to add new protocols.

This list shows the protocols defined in all catalogs accessible to the application union of all protocols defined in all catalogs with the duplicates eliminated .

The name of the protocol. This name may be used when selecting a protocol for each terminal of an appliance inside the application.

A network filter specification for the protocol describing what are the legal interactions. The descriptions are similar to setting up port filters. This list may be read only. To add a new protocol use the Application Protocols list below.

The name of the protocol. This name may be used when selecting a protocol for each terminal of an appliance inside the application it may preferably be unique may be a duplicate of a catalog defined protocol . The name may be a single word case sensitive alphanumeric A Za z0 9  .

A network filter specification for the protocol describing what are legal interactions in that protocol. Currently the filter specification for AppLogic may not be fully defined. Please use the following format for the filter value protocol identification or comment. The comment may be sufficient to identify the application level protocol such as an RFC number or simply a description TCP port 80 .

The any protocol allows connections to be established in any direction within a connection a bi directional connection . The any protocol may preferably be set on both terminals of the connection.

Even though this version of AppLogic does not enforce the protocols on inter appliance connections it may be a good idea to set those correctly both for documenting the required protocol and for making use of the protocol enforcement feature when it becomes available.

one may add new protocols only for singleton appliances if one may add the appliance using the new protocol s to a catalog the protocol settings may not be propagated properly. If one may need to add new protocols contact Technical Support for more details and or review the protocol definitions in catalog packages described in the ADL Language Reference.

The notes tab shows free form notes that are set on the application. One may edit the notes by double clicking on the text window.

According to different embodiments the Note editor viewer may be based upon TinyMCE a platform independent web based Javascript HTML WYSIWYG editor control released as Open Source under LGPL by Moxiecode Systems AB.

Insert or modify a hyper link. To insert a hyper link type and highlight the text that may be to comprise the hyper link and then click on the Insert edit Link button. A dialog may be displayed where one may enter the URL to which the link may be to refer as well as optional text This option may be also available from the right click menu.

The Application Migration wizard allows one to migrate an application from a remote grid or a URL or migrate an application to a remote grid.

Before the Application Import Wizard can be run trust between the two grids may preferably be set up. To setup trust between the two grids perform the following steps 

In addition either the user s and or the grid s public SSH key may preferably also be installed on the remote grid in order to set up a trust between the two grids. When importing an application from a remote grid 

When importing an application from a remote grid the Application Import Wizard walks the user through the steps necessary to import and configure an application that resides on a remote grid. In at least one embodiment the wizard walks the user through at least one or more of the following steps 

When the Import from Grid radial button may be selected the wizard allows the following fields to be specified 

DNS name or IP address of remote grid from which the application may be to be imported e.g. mygrid.3tera.net .

Optional new name for imported application. If a new name may not be specified the imported application may have the same name as the Remote Application Name specified above.

The Import from Grid option may be similar to executing the application migrate command from the grid shell.

The Configuration Properties dialog of the wizard allows one to set values for properties of the application allowing one to specialize this instance of the application. This may be useful for configuring location specific parameters such as IP addresses and for configuring tuning parameters such as cache sizes.

The default values of the properties are shown in normal font weight. Property values explicitly configured for this application are in bold. Mandatory property values that have not yet been configured are highlighted in red.

To restore the default value of a property press the restore button use the Reset All button to reset the values of all properties to their defaults .

Do not compress volumes when migrating application Select this option to disable compression when transferring volumes for the application. This option may speed up the operation if the application includes very large volumes.

When the Import from URL radial button may be selected the wizard allows the following fields to be specified 

The Import from URL option may be similar to executing the application import command from the grid shell and specifying a URL for the exchange directory.

When the application has been successfully imported it may be configured using the Application Configurator.

When exporting an application to a remote grid the Application Export Wizard walks the user through the steps necessary to export and configure the application to reside on a remote grid. The wizard walks the user through the following steps 

DNS name or IP address of remote grid to which the application may be to be exported e.g. mygrid.3tera.net .

Optional new name for exported application. If a new name may not be specified the exported application may have the same name as the local application being exported.

The Configuration Properties dialog of the wizard allows one to set values for properties of the application allowing one to specialize this instance of the application. This may be useful for configuring location specific parameters such as IP addresses and for configuring tuning parameters such as cache sizes.

The default values of the properties are shown in normal font weight. Property values explicitly configured for this application are in bold. Mandatory property values that have not yet been configured are highlighted in red.

For information on the property its type and allowed values select the info button . To restore the default value of a property press the restore button use the Reset All button to reset the values of all properties to their defaults .

Select this option to disable compression when transferring volumes for the application. This option may speed up the operation if the application includes very large volumes.

The Class Editor property sheet allows one to define the boundary of an appliance class and set the bindings between the class boundary and the appliance internals.

To reach the Class Editor property sheet in the editor select an appliance shape on the canvas open the right click menu and select Modify Boundary or View Boundary. The Class

Editor property sheet can also be reached by selecting an appliance shape on the canvas opening the Appliance menu and selecting the Modify Boundary or View Boundary option.

Class name. Defines the name of the appliance class. This name may be shown in the bottom left side of each appliance shape on the canvas. If the appliance may be placed in a catalog the class name may be also shown in the catalog. The name may be a single word case sensitive alphanumeric A Za z0 9  .

Template from which appliance instance names are generated. When a template may be specified the first instance may have the same name as the template and subsequent instances may have names comprised of the template followed by a number. If no template may be specified the name of the class may be used as the template.

Category of the appliance. The category may be a short alphanumeric phrase describing the group category of appliances within a catalog that the appliance belongs to. If the appliance may be placed in a catalog all appliances from the same category are grouped together in a section.

Free text description of the appliance. Typically the description includes definition of the appliance s function some distinguishing details separating an appliance from other similar appliances as well as the key software package s used inside the appliance.

It may be useful to keep color choices consistent by appliance category this makes completed applications look better.

It may be recommended to use shape size proportional to the importance and complexity of the appliance.

Specifies the type of virtualization to be used for the appliance. AppLogic supports the following virtualization modes Paravirtualized and Hardware Emulation.

The default value of the boot timeout for the appliance the time in seconds that AppLogic allows the appliance between the start of boot and the moment the appliance needs to indicate to AppLogic that it has completed boot and may be operational. See Appliance Creation Guide for details. One recommend that one may leave this setting empty so that AppLogic may use the system wide default timeout.

The default value of the shutdown timeout for the appliance the time in seconds that AppLogic allows the appliance between the start of shutdown and the moment the appliance needs to indicate to AppLogic that may be has shutdown. One recommend that one may leave this setting empty so that AppLogic may use the system wide default timeout.

This may be a numeric value that enables diagnostic or other special features of AppLogic for the appliance class this setting affects all instances of the appliance. For a list of available codes and precautions when using them see Field Engineering Codes. In short do not enable this option unless directed by a support engineer.

The following advanced settings are available by clicking on the Options button when the virtualization mode may be set to paravirtualized 

Path to the file containing the OS kernel on the appliance boot volume. The path may be relative to the boot volume root directory. If a kernel path may not be specified the appliance uses pygrub in order to start. See Appliance Creation Guide for more details on choosing the correct kernel.

Path to the file containing the boot initrd image on the appliance boot volume. This path may be relative to the boot volume root directory. If an initrd path may not be specified the appliance uses pygrub in order to start. See Appliance Creation Guide for more details on choosing the correct initrd image.

Specifies the types of consoles that are supported by the appliance. The value of this setting may be a comma separated list of one or more of the following 

Additional parameters to be specified on the kernel command line when the appliance boots. This setting can be used to pass parameters to high level drivers running in the appliance such as file systems and network stacks. For Linux appliances the kernel command line syntax may be space separated param value pairs. This setting may be optional and may be usually empty.

Specifies the schema by which the appliance operating system recognizes disk devices. For example Linux recognizes disk devices as dev hda1 dev hda2 dev hdaX. The device schema may be used by AppLogic to auto assign devices to new volumes that are added to the appliance class. The devices are stored in the class descriptor and can be used by the appliance to access its volumes. The following device schema are supported 

Specifies the mechanism by which the appliance retrieves its configuration. The following mechanisms are supported 

The following advanced settings are available by clicking on the Options button when the virtualization mode may be set to hardware Emulation 

Specifies the types of consoles that are supported by the appliance. The value of this setting may be a comma separated list of one or more of the following 

This setting may be only available when the virtualization mode may be set to Hardware Emulation and comprises a space separated list of options in the format of option val that affect how the appliance may be started. The following options are supported 

Specifies the schema by which the appliance operating system recognizes disk devices. For Hardware Emulated appliances this setting may preferably be set to hda hdb hdc hdd. The device schema may be used by AppLogic to auto assign devices to new volumes that are added to the appliance class. The devices are stored in the class descriptor and can be used by the appliance to access the volumes.

Specifies the mechanism by which the appliance retrieves its configuration. For Hardware Emulated appliances this setting may preferably be set to dhcp and the appliance may preferably have the AppLogic Appliance Productization Kit APK installed. See the APK User Manual for more information.

The Interfaces tab defines the network interfaces for the appliance. There are two types of network interfaces 

Most appliances may preferably use only terminals for their interactions see the AppLogic Overview if this may not be obvious .

The appliance terminals are named network interfaces through which the appliance interacts with other appliances in the same application. The terminals have direction input or output. The terminal direction determines whether the appliance originates connections or accepts connections.

Looking from inside an appliance the terminal may be a host name visible only to that appliance instance. The terminal name of an input terminal can be used inside the appliance to set up a listening socket for accepting connections. The terminal name of an output terminal resolves to whatever appliance may be connected to the output and can be used to establish connections to that appliance.

Each input terminal can have many appliances connected to it. Each output terminal can be connected only to a single appliance. For more details see AppLogic Overview and Appliance Creation Guide.

Name of the terminal representing the role of the interface within the appliance. It may be a single word case sensitive alphanumeric A Za z0 9  . Terminal names are usually lowercase and short 3 to 4 characters so that they fit in the appliance terminal shape.

Direction of the terminal input or output. The direction determines whether the appliance originates connections client side of most protocols or accepts connections server side of most protocols . The direction determines only where the connection originates from the appliance can pass data in and out of any terminal.

Selecting the correct protocol allows AppLogic to enforce certain aspects of the communication and more importantly to provide protocol specific statistics such as response time for the traffic passing through the terminal. In case the appliance may be protocol agnostic select Any. The Any protocol also allows connections to be established from an output terminal to an input terminal bi directional terminals . To define new protocols see the Protocols tab on the Application Configuration property sheet.

In this release this setting may be ignored however if one may configure it correctly one may be able to use the advanced connection features when they become available.

Alias of the terminal name that can be used inside the appliance to refer to the terminal. The alias can be any valid DNS name RFC 1035 . That DNS name may be available inside the appliance as an alias to the terminal name. Aliases are useful when some application inside the appliance may be hard coded to access an external service via fixed host name e.g. server1.mycompany.com . The alias attribute may be available only for output terminals.

The order of the terminals in the list as well as in the appliance shape can be modified by selecting a terminal entry in the list and using the up and down arrow buttons on the right side of the list. This may be especially useful for appliances that have more than one terminal on one of the sides.

If a mandatory terminal may not be connected the application may not start. This ensures that configuration constraints are met and prevents many configuration errors from happening. AppLogic may report the name of the appliance and the terminal that failed the check so that one may easily locate and fix it.

This option enables the appliance to interact with other applications and with any host accessible on the network external interactions . In hosted AppLogic environments the external interface has access to the Internet so make sure the appliance may be properly firewalled and otherwise protected if one may enable the external interface. The appliance may be responsible to fully configure the external interface including its IP address gateway etc. See the Appliance Creation Guide for more details. Typically only gateway appliances need to have the external interface enabled.

This option allows the appliance to interface with the AppLogic system specifically permitting authorized secure shell ssh connections to the appliance.

In this release the default interface cannot be disabled since it may be used by appliances to report that they have started. Even if one may uncheck this option the default interface may be enabled.

The Volumes tab allows one to create and destroy the set of volumes required for the operation of the appliance.

Logical name of the volume within the appliance. This name represents the role of the volume for the appliance class. It may be a single word case sensitive alphanumeric A Za z0 9  .

Path where the volume may be automatically mounted inside of the appliance e.g. nmt data . If left empty it may be up to the appliance to mount the volume.

For Windows appliances boot volumes may only be mounted as c or c . The mount path for non boot volumes can be only one of the following letter letter or c path where letter may be any valid drive letter except for c and path may not be empty.

The mount path for the boot volume does not need to be set to c or c as this may be done automatically by AppLogic .

Name of a device on which AppLogic makes the volume available to the appliance. For Linux appliances this may be typically in the form of dev hdaN where N may be a digit between 1 and 9. The appliance itself determines in its etc fstab configuration file how and where in the filesystem hierarchy the volume may be mounted unless Mount on path may be specified.

Determines the boot volume for the appliance. Each appliance may preferably have a boot volume otherwise it may not start. See the Appliance Creation Guide for more information on how to create an appliance boot volume.

Volume size for blank volumes. This field defines the size of the volume that AppLogic may create. The size may be specified as integer with optional M or G suffix e.g. 256 M . This field may be shown and needed only for volumes of type blank. For all other volumes AppLogic gets the volume size from the volumes themselves.

Performance constraints for the volume. AppLogic supports three volume constraints none high bandwidth and local only. For volumes requiring high bandwitdh access AppLogic tries to schedule the appliance on the same server where the volume resides. If this may not be possible AppLogic logs a warning but it nevertheless runs the application. For volumes set here as requiring local only access AppLogic may not start the application unless it can ensure that the appliance can run on the same server where the volume may be.

When there may be no Mount on path specified it may be the responsibility of the appliance to mount a volume itself whenever it needs it in the file system and needs to select the r o or r w option on the mount within etc fstab to specify the type of access to the file system. The R O vs. R W setting in the editor does not affect how the appliance mounts the volume but only how it can mount it. For example if a volume may be specified as R O in the editor then the appliance can only mount the volume as R O. However if the volume may be specified as R W in the editor the appliance may mount the volume as R O or R W.

Delete the selected volume. This operation permanently removes the volume from the class and from the grid. All volume content may be lost. There may be no undelete.

Manage the selected volume. This operation provides access to the volume contents via a web browser. Files may be uploaded downloaded edited deleted etc. See the Volume Browser Reference for more information.

One may arrange the order of the volumes in the list using the up and down arrows. The order affects only how the volumes may be shown to one may in the property sheets it has no runtime impact.

The Properties tab defines the properties that may be available on the appliances of this class. Properties are named configuration parameters for the appliance.

AppLogic supports three property types string integer and IP address. One may make a property mandatory requiring that its value be explicitly set on each instance. Alternatively one may define a default value for the property and that value may be used if no special value may be configured on an appliance instance.

The set of properties on an appliance class reflects the specific needs of the class. AppLogic passes the property values to the appliance without interpretation. One may are free to define whatever properties one may like.

Name for the property. The property name uniquely identifies a property within the appliance. The property names are used to set property values in the Instance Settings property sheet. The property names are also used inside the appliance to match the property values to configuration parameters see Appliance Creation Guide for details .

Type of the property. AppLogic supports three property types string integer and IP address. The type constraints the possible property values for other constraints options see below .

Default value for the property. This value may be used if no value may be specifically defined for the property in an appliance instance. Most properties may preferably have defaults. One may leave the default value empty in which case the default may be an empty string. One may also disable the default value by making the property mandatory see below .

In addition pressing the info button provides a summary of the property attributes. This may be a quick way to see any constraints without opening the constraints window.

One may arrange the property order in the list by using the up and down buttons on the right side of the list. One recommend using the property order to make configuration more intuitive group the more important properties at the top arrange the properties in the order in which it may make sense to configure them e.g. IP address netmask and then gateway .

If one wants to define value constraints for a property press the constraints button . This may open the constraints setup window 

The min max range constraint allows setting a minimum and a maximum value for integer properties. To limit only on one side of the range leave the other side empty e.g. specify only the minimum or only the maximum .

The filter constraint allows setting a regular expression for validating the property value. Regular expressions are fickle very error prone so use this constraint with care or simply use the values constraint instead. The syntax of the filter may be the same as the Perl regular expression pattern matching http perldoc.perl.org perlre.html . AppLogic performs the match on the entire property value that may be as if filter was used in a Perl statement to check for a match where filter may be the value of the filter attribute . One may use the filter constraint with any property type.

The values constraint allows one to define an enumerated set of values for the property limiting the possible property values. The syntax may be regular expression like literal values separated with vertical bar . For example any tcp udp allows only any tcp or udp as values for the property. One may use the filter constraint with any property type. For string properties one may use the values constraint together with the lowercase property attribute to make the value set not case sensitive.

If a mandatory property may not be set or a property value constraints are not met the application may not start. This ensures that configuration constraints are met and prevents many configuration errors from happening. AppLogic may report the name of the appliance and the property that failed the constraint check so that one may easily locate and fix it.

The Configuration Files property sheet lets one may define a set of files on the appliance volumes that one may want AppLogic to modify. All property values set on the appliance instance may propagate to these files. Such files for example would be httpd.conf for Apache web server appliance my.cnf for MySQL database appliance etc.

Note The Configuration Files property sheet may be only supported if the configuration mode for the appliance may be set to volfix. If the configuration mode for the appliance may be set to dhcp configuration settings may preferably be handled internally by the appliance.

The appliance volume where the configuration file resides. Typically this may be the boot volume but in some cases one may want to have the a configuration file on a data volume. AppLogic can modify config files on instantiable and placeholder volumes that are not read only.

The path to the configuration file that needs to be modified relative to the root of the volume. For example this may be etc my.cnf for MySQL s config file.

The method that AppLogic may use to quote meta characters in the value. A meta character may be any character that has a special meaning in the config file and may preferably be quoted or escaped in some manner in order to appear as a data character and not in its special function role. Based on the type of configuration file one may have the quoting method can be set to one of the following values 

One may change the order in the list by selecting an entry and using the up and down buttons on the right side of the list.

In order for AppLogic to properly modify the configuration files and know where to apply the instance property values one may need to have those configuration files instrumented using the Property Markup Syntax. See the Appliance Creation Guide for more details.

In addition to configuration files one may add here AppLogic also puts all property values in a small shell script file called etc AppLogic .sh. One may use that file from shell scripts via the source etc AppLogic .sh command. See the Appliance Creation Guide for more details.

The Resources tab allows one to specify the amount of hardware resources that are needed for each instance of this appliance. One may select amount of CPU percentage of a full CPU memory and bandwidth needed by the appliance.

Portion of a CPU to be allocated for each instance. Portions can be specified as percentage e.g. 10 or as a decimal number 0.10 .

Amount of memory to be allocated for each instance. The amount can be specified as an integer value in Megabytes e.g. 128 M or in Gigabytes e.g. 2 G . For 32 bit Linux appliances the memory may be at least 32 M and no more than 3 G.

Amount of network bandwidth to be allocated for each instance total for all terminals interfaces . The amount can be specified as an integer value in Megabits sec e.g. 10 M or in Gigabits sec e.g. 1 G . The maximum amount of bandwidth for a simple appliance may be 2 G a full duplex Gigabit Ethernet port .

One may specify a range for each resource type. The range defines the normal operating parameters desired for the appliance as well as minimum resource requirements for sandbox use.

The absolute minimum amount of a resource that the appliance needs to work at all. This may be useful to allow running the appliance in functional testing environments where the appliance may not be expected to run under production load and can run with much less resources. Contrast this with the Default below which may be amount of resources needed for production use.

Typically this may be the maximum that an appliance can use e.g. giving it more resoucres may not increase performance . The appliance may not be allocated more than the specified maximum amount ensuring that the appliance may not be able to take resources away from other appliances think of it as a quota.

The minimum amount of a resource that the appliance requires for normal operation in production environments. The appliance may not be started unless at least that much can be allocated for it likely failing the start of the application as a whole . Specifying a minimum ensures that the appliance may work within certain guaranteed resource amount think of it as a service level agreement SLA for that resource.

Leave the broadest reasonable range for all resources. The amount of resources actually allocated for an instance of the appliance can be further constrained by the instance settings of the appliance. In at least one embodiment the degree to which the resource ranges are enforced varies may be based on the underlying virtualization technology used by AppLogic .

In at least one embodiment the CPU minimum may be guaranteed and the maximum may be enforced only if other appliances need the CPU the memory minimum and maximum are strictly enforced the bandwidth minimum and maximum are not enforced at all they are used only in order to make scheduling decisions. As a result it may be guaranteed that an appliance may get its minimum CPU and memory. It may not get its full bandwidth if another appliance may be scheduled on the same server and hogs the bandwidth. In other embodiments bandwidth guarantee may be provided.

The notes tab shows free form notes that are set on the class. One may edit the notes by double clicking on the text window.

The Note editor viewer may be based upon TinyMCE a platform independent web based Javascript HTML WYSIWYG editor control released as Open Source under LGPL by Moxiecode Systems AB.

Insert or modify a hyper link. To insert a hyper link type and highlight the text that may be to comprise the hyper link and then click on the Insert edit Link button. A dialog may be displayed where one may enter the URL to which the link may be to refer as well as optional text This option may be also available from the right click menu.

In some browsers the cut copy and paste operations from the right click menu are not available. Text may be cut copied and pasted using CTRL X CTRL C and CTRL V respectively.

In at least one embodiment the instance settings may apply to a currently selected appliance instance. They override any defaults specified in the class of the appliance.

Most instance settings have their default values defined in the appliance class. When one may change these values they are shown in the property sheet in bold.

For certain settings instead of defining an explicit value one may redirect a setting so that its value may be obtained from the settings of the containing assembly. By way of example at least a portion of the redirected settings are shown herein in underlined format. One may find more information on redirected settings in Redirected Properties.

To reach the Instance Settings property sheet in the application editor double click on an appliance shape on the canvas or right click on the appliance shape and choose Attributes Resources User Volumes Property Values or Notes from the menu.

When the appliance instance may be contained in an assembly that may not be the main application assembly the instance settings specialize the instance for its role in that assembly. The assembly itself may be further specialized for its role in its containing assembly recursively going up to the whole application.

The Instance Settings property sheet may be read only if one may opened it on an instance within a catalog assembly. To learn how to modify catalog classes see Branching Classes.

If some settings need to be applied to all instances of an appliance one may use the mechanism described in Redirecting Properties. If the settings in the appliance class needs to be changed see Branching Classes and Class Editor Simple. Attributes 

This tab includes the instance attributes starting from the instance name and class name through start order to a number of advanced settings.

Instance name of the appliance. This name typically reflects the role of the appliance in the application more precisely in its containing assembly . The name may be a single word case sensitive consisting of alphanumeric characters and underscore A Za z0 9  the name may preferably be unique within the containing assembly. The instance name may be shown in the center of the appliance shape on the editor canvas.

A icon may be shown to the right of the instance name designating that the appliance may be locked. When an appliance may be locked it may not be edited nor its interior viewed within the Editor. See Application and Class Locking Reference for more information.

Class name of the appliance. This name may be read only and indicates the name of the appliance class to which this instance belongs. Typically this field also shows the catalog where the class comes from catalog class uniquely identifying the class.

If the standby option may be checked the appliance may not start automatically when the application starts the appliance can be started manually later . The standby option may be convenient for appliances that are used in development diagnostics or for appliances that are planned in reserve . This attribute may be valid only for simple appliances it may be ignored on assemblies. The Standby attribute can be redirected by selecting the button. See Using Standby for more information on the various uses of the standby attribute.

Defines the order of starting this instance relative to the other instances in the containing assembly. Lower numbers are started first. Appliances with a higher number are not started until all those with lower numbers have started successfully. Appliances with the same start order number can be started in any order and may have their startups overlap in time. The start order may be local to the containing assembly and the same start order numbers can be reused in different assemblies. The relative order of starting subordinates in different assemblies depends on the start order numbers assigned to those assemblies. Appliance instances with the start order attribute not set are started last.

If the ignore failed start option may be checked and the appliance fails to start this may not result in the application failing to start as a whole. This option may be convenient for appliances that are under development and have not been fully tested.

If one may check migrateable attribute one may allow the appliance to be moved from one server to another at runtime. When not checked the appliance may run only on the server where it was initially started. By default all appliances are migrateable. Disabling the migration for an appliance may be particularly useful to pin an appliance to a particular server see Pinning Appliances for more details . This attribute may be valid only for simple appliances it may be ignored on assemblies. This attribute can be redirected by selecting the button.

This may be an advanced capabilities section all fields here have reasonable defaults. Unless one may need to do something special make sure all advanced attributes are unchecked and one may skip this section completely.

The following attributes modify the scheduling and other behavior of AppLogic with respect to this appliance.

When specified it defines the name of the server where the appliance may start normally the servers are automatically assigned by the AppLogic scheduler . Typically the server override may be used together with unchecked Migrateable attribute to pin an appliance to a particular server.

Note that selecting a server limits the portability of the application to another grid which may not have the same server. This attribute can be redirected and it may be recommended to always redirect it all the way up to the application properties. A portable way to separate appliances on different servers may be to use the Failover Group Member attribute described below.

If the server override includes the name of a server that may not be in the system the appliance may fail to start. To see the set of server names on a given system use the server list shell command.

This field when enabled defines a failover group name for the appliance. Appliances belonging to the same group may not be scheduled to run on the same server providing an easy way to ensure that if a server fails at least one of several appliances in the group may remain running. The group name may be user defined global for an application it may be a single word case sensitive alphanumeric A Za z0 9  . This attribute can be redirected and it may be recommended that it may be redirected all the way up to the application properties.

Time in seconds given to the appliance to complete its startup. If not set AppLogic uses a default value specified in AppLogic s configuration files usually 2 5 minutes . One use of this attribute may be to help diagnose why an appliance may not be starting see Debugging Appliance Start on how to do that .

The time specified here may be how long the appliance has from start of OS boot to running the VM agent vmad that tells AppLogic that the appliance has started successfully. For more details see the Appliance Creation Guide.

Time in seconds given to the appliance to complete its shutdown. If not set AppLogic uses a default value specified in AppLogic s configuration files usually 2 5 minutes .

This may be a numeric value that enables diagnostic or other special features of AppLogic for this appliance instance. For a list of available codes and precautions when using them see Field Engineering Codes. In short do not enable this option unless directed by a support engineer.

On the Resources tab one may specify the amount of hardware resources that may be provided to the appliance instance. Unless one may override some of the values here this tab shows the defaults provided by the appliance class. The ability to override resources per instance allows one to further specialize the instance for its role.

For example a database appliance can work with as little as 128 MB RAM or take as much as 3 GB RAM. To allow this wide range the database appliance class would set these as its resource requirements minimum 128 MB maximum 3 GB . An instance of the database appliance responsible for keeping a small and rarely used database e.g. maintenance account passwords can be further constrained through this tab to 256 MB RAM maximum as there may be no need to reserve more memory for such a small and rarely used database. In contrast a database appliance that may be responsible for a core application database which may be likely to be large and heavily loaded can be constrained to run with at least 512 MB RAM ensuring that the application may operate well.

If one may don t know what resource constraints to use one recommend that one may leave the class defaults.

One may easily see which values override the defaults they are displayed in bold. If one wants to restore the default value for a given resource use the restore button next to the value. To restore all values to defaults use the Reset All button.

Portion of CPU or number of CPUs to be allocated for this instance. Portions can be specified as percentage e.g. 10 or as a decimal number 0.10 . Whole CPUs are specified as integer e.g. 2 .

Amount of memory to be allocated for this instance. The amount can be specified as an integer value in Megabytes e.g. 128 M or in Gigabytes e.g. 2 G .

Amount of network bandwidth to be allocated for this instance total for all terminals interfaces . The amount can be specified as an integer value in Megabits sec e.g. 10 M or in Gigabits sec e.g. 1 G .

A range can be specified for each resource type. The range defines the normal operating parameters desired for the appliance as well as minimum resource requirements for sandbox use.

The absolute minimum amount of a resource that the appliance needs to work at all. This may be useful to allow running the appliance in functional testing environments where the appliance may not be expected to run under production load and can run with much less resources. Contrast this with the Default below which may be amount of resources needed for production use.

The maximum amount of a resource that the appliance may be allowed to take. Typically this may be the maximum that an appliance can use e.g. giving it more resoucres may not increase performance . The appliance may not be allocated more than the specified maximum amount ensuring that the appliance may not be able to take resources away from other appliances think of it as a quota.

The minimum amount of a resource that the appliance requires for normal operation in production environments. The appliance may not be started unless at least that much can be allocated for it likely failing the start of the application as a whole . Specifying a minimum ensures that the appliance may work within certain guaranteed resource amount think of it as a service level agreement SLA for that resource.

To use the appliance with less than the default resources the crunch scheduling option may preferably be specified when starting the application see application start options.

In at least one embodiment the resource range that can be specified for the instance may preferably be a subset of the class resource range. For example in one embodiment the following may preferably be true the instance minimum may preferably be no less than the class minimum the instance maximum may preferably be no more than the class maximum the instance default may preferably be no less than the class minimum value. Other common sense constraints apply e.g. that the minimum may preferably be not greater than the maximum .

When propagating resource constraints through multiple levels of assemblies the same rules apply the new resource range may preferably be a subset of the lower level resource range.

The degree to which the resource ranges are enforced varies based on the underlying virtualization technology used by AppLogic . In one embodiment the CPU minimum may be guaranteed and the maximum may be enforced only if other appliances need the CPU the memory minimum and maximum are strictly enforced the bandwidth minimum and maximum are not enforced at all they are used only in order to make scheduling decisions. As a result it may be guaranteed that an appliance may get its minimum CPU and memory it may not get its full bandwidth if another appliance may be scheduled on the same server and hogs the bandwidth. In other embodiments the bandwidth guarantee may be provided.

The User Volumes tab allows one to configure volumes for the appliance instance. Not all appliances need volumes to be configured for them typically only appliances that work with application specific persistent data have such volumes. If the volume list on this tab may be empty the appliance instance does not need volumes.

Note that only placeholder volumes need to be configured through the instance settings see the volumes tab in Simple Class Editor property sheet . Other volumes needed by the appliance such as its boot volume are provided automatically by the appliance class and don t need to be configured explicitly.

For each placeholder volume in the appliance one may configure an application volume that may be used for this appliance.

To add or remove application volumes go to the Application Configuration property sheet select the User Volumes tab and press the Manage Volumes button.

Instead of picking a specific application volume one may also redirect the volume selection to the containing assembly. To do this select the button and choose a volume defined on the assembly boundary see Assembly Class Editor for details on how to manage those .

The info button next to the volume gives one may information about the volume requirements e.g. read only shared etc.

See the appliance class data sheet for details what are the requirements to the volume s and whether they can be shared between appliances also there may be some properties that can be set to configure directory names on the volume for this appliance. The data sheets for the global catalog appliances are in the RefCatalog.

The Property Values tab allows one to set values for properties of the appliance instance. The existing properties for an instance and their defaults are determined by the appliance class see Simple Class Editor or Assembly Class Editor for how properties are defined .

The default values of the properties are shown in normal font weight. Property values explicitly configured for this appliance are in bold. Property values that are redirected to the values of the containing assembly s properties are shown in blue.

For information on the property its type and allowed values select the info button . To restore the default value of a property press the restore button use the Reset All button to reset the values of all properties to their defaults .

To redirect a property press the redirect button and choose the name of the assembly property to which one may would like to redirect its value. For details on property redirection see Redirected Properties.

Note that some properties may not have defaults and require explicit or redirected values. Those properties are described as Mandatory in the info. Not setting a value or redirection for a mandatory property may prevent the appliance from starting. See the appliance class data sheet for details on what properties mean and what their values may be. The data sheets for the global catalog appliances are in the Catalog Reference.

The notes tab shows free form notes that are set on the instance. One may edit the notes by double clicking on the text window.

The Note editor viewer may be based upon TinyMCE a platform independent web based Javascript HTML WYSIWYG editor control released as Open Source under LGPL by Moxiecode Systems AB.

Insert or modify a hyper link. To insert a hyper link type and highlight the text that may be to comprise the hyper link and then click on the Insert edit Link button. A dialog may be displayed where one may enter the URL to which the link may be to refer as well as optional text This option may be also available from the right click menu.

In some browsers the cut copy and paste operations from the right click menu are not available. Text may be cut copied and pasted using CTRL X CTRL C and CTRL V respectively.

The editor main layout includes a palette with appliance catalogs on the left and a drawing canvas on the right.

One may reach the Infrastructure editor by first logging in and then selecting an application to edit.

The application as a whole may be an assembly a composite appliance with a well defined boundary built as a structure of connected appliance instances subordinates . In addition to the application assembly main which may be created automatically by AppLogic one may create additional assemblies that one may use to build up one s application.

So to restate the infrastructure editor allows one to visually edit the interior structure of an assembly to define the subordinate instances their configurations and connections.

The editor provides a drawing canvas where one may build structures of connected appliances. The editor further provides a number of property sheets for configuring various aspects of the application and its appliances.

The editor may be configured or designed to be intuitive and to enable users to use the palette and canvas layout familiar from a number of drawing applications.

The editor menu may include but are not limited to one or more of the following or combinations thereof 

Next to the buttons the editor shows the name of the application and the hierarchical path to the assembly being edited. The path also doubles as breadcrumb navigation one may step up to parent assemblies all the way up to main.

The following operations are available by right clicking on the canvas via the right click context menu 

The following operations are available by right clicking on an appliance within the application via the right click context menu 

In AppLogic each application has access to a two or more catalogs. At a minimum the application has access to the global system catalog and to its local catalog.

The global system catalog includes appliance classes that are common for AppLogic and are accessible to all applications. Changing an appliance in the global catalog affects all applications.

The local catalog includes appliance classes specific to the application one may are editing. Each application has its own local catalog. Changing an appliance in the local catalog affects only this application. Many applications don t actually have any appliances in the local catalog and use only appliances from the global catalog.

The appliance classes in a catalog are grouped by category. One may visually collapse or expand a category by clicking on the category name. If the catalog has a lot of appliances one may be able to scroll the catalog up and down as well.

The editor shows the catalog appliances with smaller shapes using the same color and terminals as the appliance may have when dropped on the canvas. The class name of each appliance may be shown under the shape.

One may move a singleton appliance to the catalog and make it a catalog class by dragging the singleton into the catalog make sure one may have selected the correct catalog first . See Branching Classes for more information on singletons and on customizing classes.

One may access the following operations over appliance classes by opening the right click menu on a class in the catalog 

The canvas may be the drawing area where one may assemble one s application by dragging elements from the catalog pallete and connecting them.

In addition to dragging instances around selecting instances and re routing connections one may right click on the canvas and access the following operations 

Also it shows a progress indicator for some of the longer operations such as loading or saving an application .

One may create an instance of an appliance a subordinate within the assembly by simply dragging an appliance shape from a catalog palette onto the canvas. Once one may creates the instance one may move its shape freely anywhere on the canvas.

One may configure the instance settings of the new appliance by double clicking on it the editor opens the Instance Settings property sheet for the instance. One may change the class name of a subordinate by SHIFT dragging the new class form the catalog onto the existing subordinate. This may be useful if one may wish to replace a WEB5 with WEB64 replace an IN gateway with INSSL etc. However the following limitations apply 

If the existing subordinate may not be connected to any other instance the class name of the subordinate may be changed regardless of the number and names of its terminals.

Once one may has a few instances one may also connect them. Appliances can be connected by connecting their terminals the named arrows that stick out of the appliance shape . One may connect two appliances by clicking on the terminals one may wants to connect click the output first then the input one may want it connected to.

The mouse cursor may provide clues as to what connections are allowed. Many outputs can be connected to a single input. Each output however can be connected to exactly one input. It may be even possible to connect the output of an appliance to an input of the same appliance.

For more information on what the connections mean at runtime and the benefits of using connections please see the AppLogic Overview.

When multiple outputs are connected to a single input the editor reduces visual clutter by joining the connections with as few lines as possible. Whenever a connection joins an existing connection the editor places a small dot indicating the joining of connections.

One may route the connections manually by dragging their corners up down or left right. Once one may position the mouse cursor on a connection corner it may give one may visual clue as to what directions are allowed. One may also add a segment to the connection route which may allow one to make a route that passes around another appliance.

One may perform the following operations over a connection by right clicking on the connection and selecting from the menu 

Clicking on an appliance makes it the selected appliance. Clicking on an appliance while holding the Ctrl key adds the appliance to the currently selected appliance group. Drawing a rectangle on the canvas around several appliances selects all the appliances within that rectangle.

The editor shows the current selection with dashed line. Once one may select a few appliances one may do the following with them 

One may add one or more notes or annotations to the application such as describing usage of various appliances in its architecture.

An annotation can be created by clicking on the Annotation button on the tool bar. One may edit the annotation by clicking on the created text box. In addition one may change the color of the background by clicking on the icons in the bottom left corner of the annotation text box. Clicking on the lower right corner of the annotation text box and then dragging the mouse may resize the annotation text box. The color of the text background may be changed by clicking on the icons in the lower left corner of the text box.

This section describes elements and editing capabilities that are available only when editing assemblies that are not the application top level assembly main .

The editing of an assembly may be very much like editing and configuring application main. The following may be a description of how to create and edit an assembly class.

In AppLogic assemblies can be used in any place one may would use a simple appliance. This makes it possible to reuse infrastructure without increasing the complexity of the application. For example a specialist in database clustering can create a stock assembly for clustered database deployment like the one shown above and publish it in a catalog.

Application integrators can then use this assembly in multiple applications whenever they need database scalability and or high availability and without having to know how exactly the cluster may be set up and operates.

The editor tracks unconfigured mandatory properties volumes and unconnected mandatory terminals for all appliances in an application. Such appliances that need configuration and or are missing connections are visually flagged with a warning icon e.g. on the canvas. When the mouse cursor may be dragged over the flagged appliance the editor displays the list of properties volumes terminals that need attention. The editor also displays on the status bar the number of entities that need attention. This feature also includes highlighting unconfigured mandatory properties volumes that are not configured on appliances applications.

URL where the documentation for the application can be found. The URL may be opened by clicking on the Open URL text to the right of the field.

Specify the amount of resource for each hardware resource separately CPU memory and bandwidth by moving the slide bar or entering the value manually to the right of the resource range.

Portion of CPU or number of CPUs to be allocated for the application. Fractional amounts can be specified as a decimal number e.g. 0.5 or 3.5 . Whole CPUs are specified simply as an integer e.g. 12 .

Amount of memory to be allocated for the application. The amount can be specified as an integer value in Megabytes e.g. 512 M or in Gigabytes e.g. 9 G .

Amount of network bandwidth to be allocated for this application total for all terminals interfaces including the internal communication inside the application . The amount can be specified as an integer value in Megabits sec e.g. 10 M or in Gigabits sec e.g. 1 G .

Specify the new size for the application user and singleton class volumes. The volume size can be specified as an integer value in Megabytes e.g. 512 M or in Gigabytes e.g. 2 G . The default size of the volumes are shown in normal font weight. Volume sizes explicitly configured for this application are in bold.

The Configuration Properties dialog of the wizard allows one to set values for properties of the application allowing one to specialize this instance of the application. This may be useful for configuring location specific parameters such as IP addresses and for configuring tuning parameters such as cache sizes.

The default values of the properties are shown in normal font weight. Property values explicitly configured for this application are in bold. Mandatory property volumes that have not yet been configured are highlighted in red.

For information on the property its type and allowed values select the info button . To restore the default value of a property press the restore button use the Reset All button to reset the values of all properties to their defaults .

Select this if one wants the application to be started after the provisioning. If left unselected the provisioned application may not be started.

Select this if one wants the application volumes copied using filesystem level copy rather than block level copy. This may be useful if the application has very large volumes that have little data on them.

Select this if one wants the volumes prefilled e.g. all blocks allocated . Note this may greatly increase the amount of time it takes to provision the application depending on the size of the application volumes being created.

The Provisioning dialog of the wizard shows the overall progress for the application provisioning operation.

Utility computing has gained considerable popularity over the past eighteen months as businesses big and small seek to take advantage of the flexibility the new computing model offers. This hasn t always been the case though. For a time utility computing seemed a lackluster space that hadn t been able to deliver on its early promise. The renewed interest comes on the heels of rapid market acceptance of server virtualization solutions like VMware and Xen.

Virtualization may be commonly used for server consolidation carving physical servers into smaller virtual machines VM that can be used as if they were real servers. However to accomplish this virtualization creates a separation of hardware and software decoupling virtual machine images from physical assets. Users of virtualization have come to accept that virtual machine images can be moved among servers in their data center.

Virtualization by itself however may not be a complete utility computing solution. While virtualization systems deal exceptionally well with partitioning CPU and memory within a server they lack abstractions for network and storage interactions image management lifecycle control and other services critical to utility computing. However as explained herein various aspects and virtualization techniques provided herein provide features and or services which may be advantageously used to build a fully functional utility computing system.

Storage may be one hurdle to utility computing and if poorly architected can affect cost performance scalability and portability of the system.

Virtualized storage systems such as those provided by Xen provide a basic redirection of block devices to the virtual machines. The block devices may be partitions of a physical hard disk attached to the server a large file from the server s hard disk loopback or a SAN logical disk. How the disk is associated with the VM and how it becomes available on the server prior to being redirected to the VM may not be something virtualization systems deal with.

Utility computing systems have to deal with this they cannot leave to the customer to partition physical hard disks or deal with hard disk and server failures that may make the local disk unavailable. Some systems provide near line storage outside of the VM others use IP SANs with an associative namespace. In at least some cases what may be preferred is a self managed storage system that fully mimics physical server behavior inside a VM so that regular existing software code can be used databases web servers etc.

In at least one embodiment various aspects of the provided herein relate to various techniques for implementing some form of quota or throttling of disk I O which prevents one virtual machine from monopolizing a storage device and starving others. Another aspect provided herein relates to the ability to improve detection of hardware failures in order for example to allow utility computing systems to take corrective actions automatically. In at least one embodiment such detection tools may be suitably integrated with the virtualization system in order to minimize manual intervention.

When installing software on a physical server or virtual machine it s normal practice for each system to be configured with the name or IP addresses of numerous other resources within the data center. For instance a web server may have the name of a database or NAS. In a utility system however configuration isn t quite so simple.

For example Xen s network configuration provides two mechanisms 1 flat L2 network in which domain 0 acts also as a network switch forwarding packets between the physical network and the VMs and 2 routed solution in which domain 0 acts as an IP router creating a subnet for all VMs on the same server. Both approaches create their own set of problems when used in utility computing systems from exceeding the MAC address limits on L2 switches to complicating the IP address space and preventing live migration of VMs.

Most existing utility systems implement either point to point connection virtualization or security groups similar to VLANs. In at least one embodiment various aspects of the provided herein relate to various techniques for implementing some form of quota or throttling of network in order for example to prevent one VM from monopolizing the network interface and from starving other VMs. Another aspect provided herein relates to the implementation of network virtualization services such as for example improved VLAN systems DHCP and DNS variants which may be able to account for various VM and utility needs.

As users start their applications the utility system needs a scheduling mechanism that determines where virtual machines will run on available hardware resources. In one embodiment the scheduler must deal not only with CPU and memory but also with storage and network capacity across the entire system.

In one embodiment it may be preferable for utility computing systems take the responsibility of scheduling VMs among the pool of physical servers automatically. However different utility computing systems may differ in their VM sizing from single size fixed CPU memory to a few standard sizes to the full flexibility. In at least one embodiment it may be preferable for at least some systems to also have provisions for scheduling multiple related VMs in a way to provide a deterministic and fast network between related VMs. Further it may be preferable to provide the ability to ensure the placement of VMs on different physical servers so that VMs that serve as backup for each other will not all go down together in case of a server hardware failure.

In at least one embodiment various aspects of the provided herein relate to various techniques for avoiding fragmentation without losing flexibility in the size of each virtual machine. This may be an important economic factor as fragmentation leads to wasted resources and therefore higher costs. Another aspect provided herein relates to the ability for utility computing systems to implement global scheduling and or the ability to place VMs and or whole services in specific geographic locations to optimize cost and quality of service.

It may be observed how the number of images in virtualized systems can seemingly explode. Accordingly one aspect provided herein relates to the ability for utility systems to provide image management that allows users to organize their images and easily deal with version control across the system.

Another aspect provided herein relates to the development improved techniques for creating instances of images throughout geographically distributed systems providing global access to images providing access control to licensed images and or providing improved version control. Additionally in at least one embodiment may be directed to various types of licensing mechanisms that allow for the most popular software to be purchased directly through the utility.

The tremendous increase in the number of images also exacerbates the manual configuration of virtual machines. Unlike physical servers which are usually configured carefully once and then ideally left alone for a long time in utility computing systems VMs are frequently moved around and reconfigured restarted or shut down. Conventional virtualization systems offer little to help the configuration process as they re supposed to emulate physical machines and often leave the configuration to the VMs themselves.

Existing utility computing systems provide a variety of ways to provide configuration to the VMs. However as more operating systems are offered on utility systems these parameterization methods may need to expand. Accordingly at least one aspect is directed to various techniques for implementing an OS independent configuration method e.g. being able to configure a Solaris VM from Linux domain 0 . Another aspect is directed to various techniques for improving configuration abstraction facilities.

IP address assignment can create bindings between virtual machines yet applications often require static IP addresses for public facing interfaces.

Xen simply provides to VMs what is available to physical servers essentially either a static IP or DHCP configuration per VM. Utility computing systems extend this by automatically constructing private VLANs for related VMs or automatically assigning IP addresses without the need for global DHCP service. Systems differ in the way they provide access to fully routable IP addresses from disallowing routable addresses and using NAT to fully allowing VMs to use IP addresses and configuration with the same flexibility that is available to physical servers.

Accordingly one aspect is directed to various techniques for establishing external IP addresses in a way that allows automatic allocation yet is still flexible enough to maintain static addresses for service end points and interaction with DNS. For example in one embodiment at least one mechanism may be provided for allowing IP address assignment to be enforced so that one VM cannot interfere with the operation of another. Additionally in at least one embodiment it is preferable to provide services that provide the ability to move IP addresses between geographic locations for disaster recovery for example as larger users begin moving mission critical applications onto the services.

With applications running on a utility computing service system administrators still may need to be able to monitor operations and create systems that offer high availability.

Virtualization breaks the one box one function relationship and makes it very hard to manually track down hardware failures and map them to logical servers VMs and services services built from multiple VMs . At the same time virtualization allows one to provide near transparent failover.

Accordingly one aspect is directed to techniques for handling the isolation of VMs belonging to different customers as well as with providing performance data of multiple related VMs in context of a bigger service. Another aspect relates to various techniques for collecting correlating and analyzing the performance data of large services built of multiple VMs as well as the ability to take actions based on performance data.

High availability is typically beyond the single server scope of standard server virtualization. Some utility computing systems attempt to leverage the array of physical resources they control to automatically restart VMs from a failed server to another ready server. However to improve this capability at least one mechanism may be provided for providing more reliable failure detection and for handling various the issues which may arise from a server disk or network. In at least one embodiment various mechanisms may be provided to offer improved integration with existing data center monitoring systems will also improve response and reporting.

According to different embodiments other services and or features may be provided by one or more of the various techniques described herein such as for example one or more of the following or combinations thereof 

This application incorporates by reference in its entirety and for all purposes U.S. patent application Ser. No. 11 024 641 by Miloushev et al. entitled APPARATUS METHOD AND SYSTEM FOR AGGREGATING COMPUTING RESOURCES filed Dec. 29 2004.

Although several preferred embodiments of this invention may be described in detail herein with reference to the accompanying drawings it is understood that the invention may not be limited to these precise embodiments and that various changes and modifications may be effected therein by one skilled in the art without departing from the scope of spirit of the invention as defined in the appended claims.

