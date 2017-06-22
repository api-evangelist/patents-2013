---

title: Method and apparatus for providing network applications monitoring
abstract: A method for providing network performance monitoring using a performance database manager (PDM) is disclosed. A PDM has a PDM state manager, a communications server (COM server), a communications client (COM client), and an application database (AppDB). The PDM is configured to communicate with a network controller and a switch running a service monitoring (SERMON) client. A list of one or more switches, one or more hosted services, and one or more applications is determined. A request for service monitoring (SERMON) data is received from one or more applications running on a network controller. The request is sent to a SERMON client. A response is received from the SERMON client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09519563&OS=09519563&RS=09519563
owner: Telefonaktiebolaget LM Ericsson (publ)
number: 09519563
owner_city: Stockholm
owner_country: SE
publication_date: 20130509
---
The present disclosure relates to frameworks for virtualized and non virtualized environments. More particularly the present disclosure relates to frameworks for providing performance monitoring.

Many telecom oriented services are being considered for deployment within the confines of data centers. These services have a large compute bias and lax latency requirements. Current data centric deployments involve a large number of machines on the order of hundreds of thousands in both virtual as well as non virtual environments.

A Distributed Resource Scheduler DRS is a technology that is used to optimize computing resources to align with business needs and priorities. The DRS can operate in a manual mode or an automatic mode. In an automatic mode the DRS determines the best possible distribution of virtual machines taking into account the business policies and relocates the virtual machines to the appropriate physical servers. In a manual mode the DRS makes recommendations that align with business policies. The DRS runs in the context of a virtual center vCenter and assists the resource allocation function.

A Vscheduler is another framework for managing processor resources. Its local and global resource configuration framework allows virtual machines VMs to be balanced for processing resources locally and globally across a cluster. The Vscheduler uses a centralized manager node that receives input from VMAgents in VMs and PMAgents in physical nodes.

The Memory Balancer MEMB dynamically monitors the memory usage of each VM in a virtual environment predicts the memory needs of each VM based on swap space usage and a least recently used LRU histogram to track physical addresses and periodically reallocates host memory to the VMs needing more memory resources.

Frameworks such as the ones mentioned above provide a centralized mechanism to optimize the cluster host resources like CPU Memory Storage and Power across a plurality of machines.

These aforementioned frameworks provide tools to optimize the host and cluster wide resources like CPU and memory. Given the importance of connectivity in a data center there is a dearth of frameworks that optimize the performance of a network or a connection fabric.

Application performance metrics like the number of open sockets and the working set size for example require the cooperation of the Guest Operating System OS running in the guest domain Domain U on top of which the application is running.

What is needed therefore is a framework for exporting application configuration and performance information for performance monitoring in virtualized and non virtualized environments.

A method for providing network performance monitoring using a performance database manager PDM is disclosed. In one embodiment a list of one or more switches one or more hosted services and one or more applications is determined. A request for service monitoring SERMON data is received from one or more applications running on a network controller. The request is sent to a SERMON client. A response is received from the SERMON client.

In one embodiment the one or more switches can be Layer2 switches. The PDM can receive the list on boot up. The PDM can also periodically query the network controller to update the list.

The request can be a snapshot request. When the snapshot request is a first time request an application identifier is flagged for retrieval of SERMON information. The response received in response to the snapshot request is sent to the application upon receipt from the SERMON client. When the snapshot request is not a first time request a PDM state manager stores in a database SERMON data related to the application identifier from the response.

A PDM state manager formulates the request message and sends the message to the one or more switches hosting the one or more hosted services. The PDM sends the response to the one or more applications on the controller.

An apparatus for providing network performance monitoring is disclosed. In one embodiment the apparatus includes a performance database manager PDM . The PDM has a PDM state manager a communications server COM server a communications client COM client and an application database AppDB .

The PDM is configured to communicate with a network controller and a switch running a service monitoring SERMON client. The PDM is further configured to determine a list of one or more switches one or more hosted services and one or more applications receive a request for SERMON data from the one or more applications running on the network controller send the request to the SERMON client and receive a response from the SERMON client.

In one embodiment the one or more switches can be layer2 switches. In one embodiment the COM server parses the request and sends the list to the PDM state manager.

In one embodiment the request can be a snapshot request. When the snapshot request is a first time request an application identifier is flagged for retrieval of SERMON information. The response received in response to the snapshot request is sent to the application upon receipt from the SERMON client. When the snapshot request is not a first time request the PDM state manager stores in the AppDB SERMON data related to the application identifier from the response.

The PDM state manager formulates the request message and sends the message to the one or more switches hosting the one or more hosted services. The PDM sends the response to the one or more applications on the controller.

In the following description numerous specific details are set forth. However it is understood that embodiments of the invention may be practiced without these specific details. In other instances well known circuits structures and techniques have not been shown in detail in order not to obscure the understanding of this description. It will be appreciated however by one skilled in the art that the invention may be practiced without such specific details. Those of ordinary skill in the art with the included descriptions will be able to implement appropriate functionality without undue experimentation.

References in the specification to one embodiment an embodiment an example embodiment etc. indicate that the embodiment described may include a particular feature structure or characteristic but every embodiment may not necessarily include the particular feature structure or characteristic. Moreover such phrases are not necessarily referring to the same embodiment. Further when a particular feature structure or characteristic is described in connection with an embodiment it is submitted that it is within the knowledge of one skilled in the art to effect such feature structure or characteristic in connection with other embodiments whether or not explicitly described.

In the following description and claims the terms coupled and connected along with their derivatives may be used. It should be understood that these terms are not intended as synonyms for each other. Coupled is used to indicate that two or more elements which may or may not be in direct physical or electrical contact with each other co operate or interact with each other. Connected is used to indicate the establishment of communication between two or more elements that are coupled with each other.

As used herein a network element e.g. a router switch bridge is a piece of networking equipment including hardware and software that communicatively interconnects other equipment on the network e.g. other network elements end stations . Some network elements are multiple services network elements that provide support for multiple networking functions e.g. routing bridging switching Layer 2 aggregation session border control Quality of Service and or subscriber management and or provide support for multiple application services e.g. data voice and video . Subscriber end stations e.g. servers workstations laptops netbooks palm tops mobile phones smartphones multimedia phones Voice Over Internet Protocol VOIP phones user equipment terminals portable media players tablets GPS units gaming systems set top boxes access content services provided over the Internet and or content services provided on virtual private networks VPNs overlaid on e.g. tunneled through the Internet. The content and or services are typically provided by one or more end stations e.g. server end stations belonging to a service or content provider or end stations participating in a peer to peer service and may include for example public webpages e.g. free content store fronts search services private webpages e.g. username password accessed webpages providing email services and or corporate networks over VPNs. Typically subscriber end stations are coupled e.g. through customer premise equipment coupled to an access network wired or wirelessly to edge network elements which are coupled e.g. through one or more core network elements to other edge network elements which are coupled to other end stations e.g. server end stations .

Different embodiments of the invention may be implemented using different combinations of software firmware and or hardware. Thus the techniques shown in the figures can be implemented using code and data stored and executed on one or more electronic devices e.g. an end station a network element . Such electronic devices store and communicate internally and or with other electronic devices over a network code and data using computer readable media such as non transitory computer readable storage media e.g. magnetic disks optical disks random access memory read only memory flash memory devices phase change memory and transitory computer readable transmission media e.g. electrical optical acoustical or other form of propagated signals such as carrier waves infrared signals digital signals . In addition such electronic devices typically include a set of one or more processors coupled to one or more other components such as one or more storage devices non transitory machine readable storage media user input output devices e.g. a keyboard a touchscreen and or a display and network connections. The coupling of the set of processors and other components is typically through one or more busses and bridges also termed as bus controllers . Thus the storage device of a given electronic device typically stores code and or data for execution on the set of one or more processors of that electronic device.

A seamless non intrusive scalable framework that retrieves the network application performance metrics from a collection of applications running on machines is disclosed. The network application performance metrics can be easily exported to the centralized controller component in Software Defined Networks SDNs .

The framework includes components and messaging that work coherently together to achieve the objective of presenting the network application running in the centralized controller with the performance data needed to make an intelligent decision for loading balancing network flows across several instances of a network appliance.

The use of such a framework can lead to supporting the deployment of cloud services with stringent service level agreements for network performance in even more dynamic service environments while making cost effective use of network infrastructures without gross over provisioning.

SDNs offer scope for a global view of the network including the topology and the metrics. It is possible to perform automatic load balancing and placement features based on metrics that can be obtained from the services in the network. In a services network there may be multiple instances of a particular service like Deep Packet Insertion DPI or a content filter running in a network. The present disclosure defines a framework for providing useful performance data of a hosted application.

The PDM state manager is responsible for managing all of the states for metrics that are periodically collected from one or more entities running in the context of the hosted service environment. The PDM state manager stores these states in AppDB . The PDM state manager is also responsible for formulating messages e.g. from requests received from a network controller through COM server and funneling these messages to the COM client .

As stated above network controller sends requests to PDM . Network controller also runs network application programming interfaces API s and network middleware . In one embodiment the request may include a datapath identifier DPID a host identifier HostID and application identifier AppID and other data X X . . . X . This other data can be the request for actual data items e.g. number of open sockets average load etc.

Communications COM server module services requests from applications running on network controller . A COM client module assists the PDM with populating the database by maintaining connections to each entity e.g. the Service Monitoring SERMON client that services the requests. The SERMON client services the requests made by the COM client module . A SERMON server module retrieves the requested information for an application using an AppID.

The database and its manager can be co located within the controller or outside of it depending on the specific configuration for communication between the controller and the database manager . In the SDN controller and the PDM are shown as different entities. The communication between them is shown to be generic and is not restricted to any message type. In one embodiment a RESTful interface i.e. corresponding to Representational State Transfer REST constraints or any proprietary interface can be used as part of the implementation. Although some of the messages of the present disclosure are described as using a RESTful interface as stated above the present disclosure is not limited to RESTful interfaces.

The centralized PDM is responsible for populating the information in the database which depends on a schema that is given to the PDM by the SDN application . The SDN application is decoupled from the database and is also not responsible for maintaining connections with each application agent. The application agent is a component that runs on top of the network controller and acts on behalf of an application. The application agent forms the actual requests to be sent and is also responsible for handling the responses for the requests. Further the COM client in the PDM module connects with each SERMON client that handles the database requests. SERMON client is running on a Layer 2 Switch .

The Layer 2 Switch can be a virtual switch running in a hypervisor a physical Ethernet switch or an Openflow switch. The SERMON module running on the switch runs as a functional block that is responsible for encapsulating decapsulating requests responses to service hosts. The SERMON module can choose any of the following to make a request to the service hosts dedicated management Virtual Local Area Network VLAN Physical Ethernet Multi Protocol Label Switching MPLS tagged Openflow and or a higher level Transmission Control Protocol TCP connection to the server. The switch datapath is programmed to forward these packets to the correct ports in order to reach the service hosts.

The SERMON client module then translates the database requests into the appropriate messages that are encapsulated in a specific VLAN tag MPLS tag or a TCP session at a specific TCP port . The SERMON server module that runs in the context of the network application environment handles the SERMON client requests data and returns the requested data e.g. in a response to PDM .

The present disclosure identifies the SERMON server running in the network application environment e.g. on a service host by a SERMON server ID ServID . The SERMON client is identified with a specific SERMON client ID CliID . The SERMON client sends a list of known SERMON Servers identified by the ServID to enable the PDM to specify the exact entity that should be contacted for performance information which is identified by SERMON CHID SERMON ServID AppID. The SERMON client is also responsible for encapsulation and decapsulation of the messages between the SERMON client and the SERMON server .

The SERMON server itself can be located inside a Virtual machine running on top of Hypervisor SERMON server running on a Linux Host without a Hypervisor SERMON server or on a physical middle box that hosts the server SERMON server . Each SERMON server includes a SDCU and a Platform Dependent Collection Unit PDCU . The tagging mechanism should be chosen so as to mate the client with the server.

The SDCU is implemented as a thread e.g. a kernel same page merging KSM thread ksmThread . The SDCU receives notifications from the SERMON module. The SDCU is responsible for encapsulation decapsulation of requests responses. The SDCU fetches the network monitoring parameters from the PDCU and returns the reply e.g. response.

Network applications running on the centralized controller periodically request the PDM for SERMON metrics. The applications specify which layer2 switch and service host ID on which services are hosted. The applications specify the metrics in which they are interested. In one embodiment the applications can determine metrics for current values or a snapshot of aggregated values over time. The network application s receive a reply from the PDM with the requested data.

In one embodiment the data values are applied on application specific heuristics. In one embodiment changes can be made to data plane switches. In this embodiment the controller sends a new set of flow messages to the switches to alter the traffic going through the services hosted on for example one or more of the virtual machines.

The database contains the information that is used by the controller applications . The PDM should be implemented in a highly available reliable and scalable manner.

Each physical server e.g. a physical service host or physical switch notifies the controller when the following events happen 

When the PDM is launched the PDM queries the centralized controller for a list of SERMON CliID SERMON ServIDs and application ID s. The PDM also periodically queries the centralized controller for the latest snapshot of the SERMON CliIDs SERMON ServIDs and App IDs.

There are multiple controller applications that require performance data from each of the hosted services and each controller application can generate a schema file that can be sent to the data base manager which in turn populates the data base based on the schema. It is important to note that there is no change to the hosted service . The database manager has a per application state that maintains a copy of the schema. Based on the schema the database manager queries the appropriate entity e.g. the hosted service for data with a specific SERMON CliID SERMON ServID and AppID combination.

The SERMON client module identified by a SERMON CliID is resident in the switch and responds to the queries sent by the database manager .

The SERMON client handles requests from the COM client . The SERMON client checks whether the inquiry is related to a particular instance or all instances of a hosted service . The SERMON client then parses the request and stores this request as requested information. The SERMON client sends an internal message to the Service Data Collector Unit SDCU . The SDCU contacts the appropriate SERMON ServID AppID entity for information.

The SERMON client sends a request message e.g. a retrieve command to the SERMON server s in order to request performance data. The SDCU formats a retrieve command encapsulates the retrieve command into an appropriate tagged frame VLAN MPLS TCP connection and forwards the encapsulated retrieve command toward its destination. This tagging mechanism depends on the configuration.

The SERMON client handles response messages from SERMON Servers. The SERMON client waits for a response from the SERMON server. The SERMON client checks for any errors in the received response s . When errors are detected the error information is accumulated in a buffer along with the SerVID AppID. When no errors are detected the response is stored in a buffer associated with the SERMON client along with the ServID AppID and the received counter e.g. SERMON data category value.

Buffering in this context is the process of receiving requests and storing them. Later the responses are received by the COM client when the responses are returned from the SERMON servers. The COM client makes a note of the request and matches the request up with the received response.

The SERMON client sends the buffered response s to the PDM COM client . The SERMON CliID is filled at the beginning of the buffer. The response message is sent back to the PDM that requested this information.

The SERMON server handles the request e.g. the request generated by SDCU from the SERMON Client . The datapath decapsulates the request and strips the tagged header. Datapath passes the packet to the SDCU block which parses the packet to look for an AppID. The SDCU parses the packet for example using a packet buffer .

The SDCU sends a request to PDCU unit . The PDCU unit implements the platform dependent way of collecting performance data. In one embodiment the performance data is collected using a kernel thread that searches the requested information in the kernel data structure s and returns the data e.g. to the SDCU from PDCU . If the PDCU cannot identify the data to be retrieved the PDCU returns an error. The kernel thread can be used to construct a buffer in shared memory .

The SERMON server sends a response to the SERMON Client. The response message includes the data returned from the PDCU. The response message is encapsulated e.g. by datapath and returned to the requestor to be put into the database. The request from the client is satisfied by querying the database.

In order to improve the performance and security of their networks network operators today deploy a wide range of specialized appliances or middle boxes. An architecture based on SDN principles is used to explicitly steer different types of traffic through the desired set of middle boxes. Using an architecture of this type provides an architecture that is easier to manage and provides greater scale even at the granularity levels of per subscriber and per application defined policies.

SDN inline services and forwarding architecture uses two different types of switches. The Perimeter Open Flow OF Switches are placed on the perimeter of the service delivery network. These switches classify the incoming traffic and steer this traffic towards the next service in the chain. OF switches are the switches to which services or gateway nodes are connected. The Inner Switches forward the traffic using efficient Layer 2 L2 switching. Inner switches are only connected to other switches. Inner switches may or may not be OF switches.

Traffic steering is a two step process. The first step classifies incoming packets and assigns them a service path based on predefined subscriber application and ordering policies. The second step forwards packets to a next service based on its current position along its assigned service path. This two step traffic steering process only needs to be performed once between any two border routers regardless of the number of switches that connects them.

For the different types of middle box functionality the set of parameters that could be used to construct efficient heuristics for the sole purpose of steering the traffic to the correct chosen instance of the service is identified.

A controller application driving the distribution of flows to the different instances of DPI for example could use the CPU data e.g. CPU 1 min load packet data e.g. the packet rate statistics and sockstat data e.g. the number of open sockets. The DPI inspects each and every packet beyond the TCP headers scanning for recognizable content to apply rules and therefore the DPI instance processing the least amount of packets can be chosen to accept the flow. If there is more than an instance processing an equal number of packets CPU load could be used for example as a tie breaker. Similarly the number of open sockets could be used as a tiebreaker as well.

Table 1 shows the different applications and the categories of performance data used by each of them according to one embodiment. Each cell in the table shows the exact file name from for each category which contains appropriate data to be used by the applications themselves. Instances of service names can be shown in the table to give an overall view of the performance data of a specific application.

In one embodiment an application queries the database for all existing SERMON client SERMON Server entities and App ID s that are returned by the PDM. The application pushes the schema e.g. sends a request to the PDM in order to retrieve performance information pertinent to the application. This performance information can be collected for one or more instances of the application running on one or more entities e.g. one or more service hosts. The application receives a response from the PDM and if performance data for a plurality of instances of the application is desired an algorithm is run to choose the next application instance to which a performance data flow is to be scheduled.

The Performance Database manager receives the request and validates the request against the schema it has for the application instance. The PDM then returns the values for the requested data items from its database. It is the responsibility of the PDM to query the specified data items from the SERMON Severs via the SERMON Clients on a periodic basis driven by the timing requirements specified by the application.

The SERMON Client receives independent requests for performance data. The server converts these requests into a retrieve command and forwards the retrieve command to the appropriate SERMON Server s .

The SERMON Server receives the message de capsulates it and sends it to the kernel thread that searches and retrieves the requested information which is then returned to the requesting SERMON client.

a. The DPI application queries the database for all existing SERMON client SERMON Server entities and DPI App ID s which are returned by the database manager

b. Push the schema to retrieve the 1 min CPU loadavg the number of input and output packets on the virtual interface that the virtual service is connected to and the number of TCP sockets.

c. The application then requests the database for the information from all Service VM s that are interesting to this application e.g. DPI typically all DPI instances or specific DPI instances

d. The application receives the response from the database and runs an algorithm to choose the next DPI instance to which to schedule a flow.

The Performance Database manager receives the request and validates the request against the schema that the PDM has for DPI. The PDM then returns the values for the requested data items from its database. It is the responsibility of the PDM to query the specified data items from the SERMON Severs via the SERMON Clients on a periodic basis driven by the timing requirements specified by DPI.

The SERMON Client receives independent requests for CPU load average the total packet count and the number of open sockets. The server converts these requests into a retrieve command and forwards the retrieve command to the appropriate SERMON Server s .

The SERMON Server receives the message de capsulates it and sends it to the kernel thread that searches and retrieves the requested information e.g. DPI performance data which is then returned to the requesting SERMON client.

Table 2 shows per interface packet statistics according to one embodiment. Each row in the table represents a specific kind of metric. This table can be used to monitor the network as a whole. The number of broadcast packets and packet rates can be used to determine the health of the interface s which could eventually be correlated to a service.

Various terminating services such as transparent content cache video transcoders web proxy engines can benefit from measurements of the number of sockets in connected state cpu load and percentage of available memory to name a few.

The utilization of an intrusion prevention system IPS an intrusion detection system IDS and or firewalls can be modeled from the input output packet byte counters and central processing unit CPU load. Network address translation NAT steering on the other hand uses an added parameter of the percent of available memory. Persistent memory parameters like available storage capacity take an important role for mail filtering or spam prevention networks. Other counters for sockets in a non connected state or rate of in coming packets become a guiding light to trigger alarms for denial of service attacks in steering service networks. This framework offers an opportunity to design an appropriate heuristic to optimize the appropriate application objective.

The message formats between the applications and the components of the framework are shown in . illustrates a message format according to one embodiment. All messages carry the SERMON CliID followed by the SERMON ServID type and the counter type which could signify all or specific . Depending on the values of the ServID type and Counter Request type the objects can be of different types. The shaded part of message format represents the required part of any message between the applications and components of the framework.

Messages can be made asynchronous by adding a transaction identifier. Each response can then embed this transaction identifier so that the transaction identifier can be correlated with a request. This mechanism can be used for multiple purposes like bulking or making the server responses asynchronous to the context of a request.

A performance data request includes an application name e.g. in the form of a UUID string to identify the application. This UUID string may take the form of an AppID. All instances of a particular service can be identified by this application name string. The counter name object is included when a specific counter is being requested. A particular SERMON server instance is identified by the ServID. shows all the requests that can be sent by the application to the PDM. Each request is denoted as such and each reply can be correlated with each request by using the request number.

Req1 includes an AppID . All instances of a particular service can be identified using the AppID. Using this request allows for performance data associated with the application across all SERMON servers to be requested using all pertinent counters.

Req2 includes an AppID and a counter name . Using this request allows a specific counter to be requested across all SERMON servers.

Req3 includes an AppID and a ServID . Using this request allows for application performance data using all pertinent counters to be requested for a particular SERMON server instance.

Req4 includes an AppID a ServID and a counter name . Using this request allows for performance data to be requested for a specific counter for a particular SERMON server instance.

The integer part of the value in the counter objects in the responses of and can have up to 128 digits and the fractional part of the number can be up to nine digits. The application name itself can be described with a 128 byte string. The ServID is a UUID which in one embodiment is a sixteen byte hexadecimal string.

Each one of the responses in can have an error object that replaces the counter value field in the counter object. The error string can be one of the following 

In one embodiment the database manager and the SERMON Client is capable of exchanging request messages.

A request e.g. Req1 for all counters from all service instances of a particular application can be implemented using the following command 

A request e.g. Req3 for all counters from a specific service instance of an application can be implemented using the following command 

A request e.g. Req2 for all application instances Service VMs for a specific counter can be implemented using the following command 

A request e.g. Req4 of a specific instance of an application for a specific counter can be implemented using the following command 

The responses to these queries are returned in standard XML JSON or any other chosen format. The data in the replies is organized as shown in .

This messaging happens via a configured tagging mechanism such as VLAN tags or MPLS tags. The particular tagging mechanism or format should be one that can be recognized by all incarnations of the hosted services. The message is encapsulated in a tagged frame and forwarded to its destination.

These requests are sent to the appropriate SERMON Servers located in the different hosted environments identified by ServID and the application identifier AppID in the request uniform resource identifier URI . The SERMON server iterates through all the counters for all AppIDs and for each counter the SERMON server parses the name looks up the name and returns the value or an error corresponding to the request. The SERMON server should set the number of counter objects field appropriately to enable the hosted service instance to iterate through every requested object.

The second step in the process of collecting the data is to notify the service VM instance that a request has been sent.

For each of the counters specified in the shared memory the service VM instance parses the counter name looks through its resources typically the proc file system for the specified counter and returns the value in the counter value field described above.

Appropriate error codes are returned in the error codes field. These error codes may include the following 

At block a request for performance data information e.g. SERMON data metrics is sent to a PDM. The request includes the application name which can be a UUID such as an AppID. In one embodiment all instances of a particular service can be identified by the application name.

Network applications running on the centralized controller periodically request the PDM for SERMON metrics. The applications specify which layer2 switch and service host ID on which services are hosted. The applications specify the metrics in which they are interested. In one embodiment the applications can determine metrics for current values or a snapshot of aggregated values over time.

In one embodiment the performance data associated with the at least one application can be requested across all service monitoring SERMON servers using all pertinent counters. In one embodiment the performance data associated with the at least one application is requested across all service monitoring SERMON servers using a specific counter. In one embodiment the performance data associated with the at least one application is requested across a specific service monitoring SERMON server using all pertinent counters. In one embodiment the performance data associated with the at least one application is requested across a specific service monitoring SERMON server using a specific counter.

At block a response to the request for performance data information is received. The network application s receive a reply from the PDM with the requested data.

At block a service path is assigned by steering traffic to a particular instance of each of the one or more applications using the performance data. In one embodiment the performance data is applied to application specific heuristics. In one embodiment changes can be made to data plane switches. In this embodiment the controller sends a new set of flow messages to the switches to alter the traffic going through the services hosted on for example one or more of the virtual machines. At block the steered traffic is forwarded to a next application based on a current position along a service path.

At block a request for SERMON data is received from one or more applications running on a network controller. A COM server of the PDM parses the request and sends the request to a PDM state manager.

At block the request is sent to a SERMON client e.g. running on a switch. At block a response is received from the SERMON client.

In one embodiment the request is a snapshot request. If the snapshot request is made for the first time the AppID of the application is flagged for information retrieval. Otherwise the PDM state manager fetches the values related to the snapshot request previously stored in the AppDB.

In one embodiment the PDM state manager formulates request messages for every pertinent metric. Request messages are sent to each switch hosting the services using a COM client. A response is sent to the application on the network controller that requested the SERMON data once a reply e.g. response message has been received from the switch.

In one embodiment when a flag has been set for an AppID the PDM makes a request for SERMON metrics through the COM client. The PDM stores an application specific aggregated SERMON metric in the AppDB. When a retrieval flag is set for an AppID a response is sent to the application on the controller once a reply is received from the switch.

At block the request is sent to the SERMON server designated in the request. The SERMON server runs in a service host. In one embodiment the SDCU retrieves the service host to which the request needs to be sent. For each host the SDCU formulates a command and an expected data type encapsulates the request in a designated tag sends the encapsulated request e.g. frame to a switch datapath and waits for a reply e.g. response from the service host.

At block a reply is received from the SERMON server. In one embodiment the SDCU reads the reply. The SDCU parses the buffer and formulates a message for the COM server of the SERMON client by decapsulating the tagged frame. The SDCU sends a reply message to COM server of the SERMON client. At block the COM server send a reply to the PDM.

At block the SERMON data is collected using a kernel thread. The ksmthread fetches SERMON data from local kernel data structures. The ksmthread constructs a buffer in the shared memory and sends the notification e.g. reply response to the SERMON server by encapsulating the notification as a tagged frame. In one embodiment the ksmthread is implemented in a Platform dependent Data Collection Unit PDCU . At block the collected data is sent in the notification to the SERMON client.

The computer system includes a bus es that is coupled with a processing system a power supply volatile memory e.g. double data rate random access memory DDR RAM single data rate SDR RAM nonvolatile memory e.g. hard drive flash memory Phase Change Memory PCM . The processing system may be further coupled to a processing system cache . The processing system may retrieve instruction s from the volatile memory and or the nonvolatile memory and execute the instruction to perform operations described above. The bus es couples the above components together and further couples a display controller one or more input output devices e.g. a network interface card a cursor control e.g. a mouse trackball touchscreen touchpad etc. a keyboard etc. . In one embodiment the display controller is further coupled to a display device .

As described herein instructions may refer to specific configurations of hardware such as application specific integrated circuits ASICs configured to perform certain operations or having a predetermined functionality or software instructions stored in memory embodied in a non transitory computer readable medium. Thus the techniques shown in the figures can be implemented using code and data stored and executed on one or more electronic devices e.g. an end station a network element . Such electronic devices store and communicate internally and or with other electronic devices over a network code and data using computer readable media such as non transitory computer readable storage media e.g. magnetic disks optical disks random access memory read only memory flash memory devices phase change memory and transitory computer readable communication media e.g. electrical optical acoustical or other form of propagated signals such as carrier waves infrared signals digital signals . In addition such electronic devices typically include a set of one or more processors coupled to one or more other components such as one or more storage devices non transitory machine readable storage media user input output devices e.g. a keyboard a touchscreen and or a display and network connections. The coupling of the set of processors and other components is typically through one or more buses and bridges also termed as bus controllers . Thus the storage device of a given electronic device typically stores code and or data for execution on the set of one or more processors of that electronic device. Of course one or more parts of an embodiment of the invention may be implemented using different combinations of software firmware and or hardware.

While the flow diagrams in the figures show a particular order of operations performed by certain embodiments of the invention it should be understood that such order is exemplary e.g. alternative embodiments may perform the operations in a different order combine certain operations overlap certain operations etc. .

The present invention allows advanced heuristics to be applied based on the performance and configuration information which is made available to the application. This framework has the following characteristics 

While the invention has been described in terms of several embodiments those skilled in the art will recognize that the invention is not limited to the embodiments described. The description is thus to be regarded as illustrative instead of limiting.

