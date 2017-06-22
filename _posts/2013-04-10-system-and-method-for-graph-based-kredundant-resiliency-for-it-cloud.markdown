---

title: System and method for graph based K-redundant resiliency for IT cloud
abstract: A method for enabling resiliency for cloud computing systems is described. The method includes modifying a topology graph of a network architecture by mapping processes flows onto the topology graph. A resiliency graph is created based on the modified topology graph. The method includes modifying the resiliency graph by translating at least one SLA into the resiliency graph. Overlaps and dependencies in the modified resiliency graph are identified. Apparatus and computer readable instructions are also described.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09077613&OS=09077613&RS=09077613
owner: International Business Machines Corporation
number: 09077613
owner_city: Armonk
owner_country: US
publication_date: 20130410
---
The exemplary and non limiting embodiments relate generally to cloud computing systems methods devices and computer programs and more specifically relate to providing resiliency for cloud computing systems.

This section is intended to provide a background or context. The description herein may include concepts that could be pursued but are not necessarily ones that have been previously conceived or pursued. Therefore unless otherwise indicated herein what is described in this section is not prior art to the description and claims in this application and is not admitted to be prior art by inclusion in this section.

Cloud computing allows the use of computing resources such as hardware and software over a network such as the Internet for example . Using cloud computing remote devices are allowed to access a user s data as well as to use software applications.

Information technology IT clouds may be implemented as virtualized data centers and enabled the creation deployment management and usability of new services. Distributed users both individuals and businesses can take advantage of the cloud services in order to provide automation and scalability. Additionally many implementations may suffer from points of failure that could impact larger number of users.

What is needed is a technique to evaluate a cloud architecture and determine ways to provide improved resiliency.

In an exemplary aspect a method for enabling resiliency for cloud computing systems is provided. The method includes modifying a topology graph of a network architecture by mapping processes flows onto the topology graph. A resiliency graph is created based on the modified topology graph. The method includes modifying the resiliency graph by translating at least one SLA into the resiliency graph. Overlaps and dependencies in the modified resiliency graph are identified.

In another exemplary aspect an apparatus for enabling resiliency for cloud computing systems is provided. An apparatus includes a processor and a memory storing computer program code. The memory and the computer program code are configured to with the processor cause the apparatus to perform actions. The actions include modifying a topology graph of a network architecture by mapping processes flows onto the topology graph and creating a resiliency graph based on the modified topology graph. The actions also include modifying the resiliency graph by translating at least one SLA into the resiliency graph and identifying overlaps and dependencies in the modified resiliency graph.

In a further exemplary aspect an article of manufacture such as a computer readable memory for enabling resiliency for cloud computing systems is provided. The article of manufacture tangibly embodies computer readable instructions which when implemented cause a computer to carry out the steps of a method. The method includes modifying a topology graph of a network architecture by mapping processes flows onto the topology graph and creating a resiliency graph based on the modified topology graph. The method also includes modifying the resiliency graph by translating at least one SLA into the resiliency graph and identifying overlaps and dependencies in the modified resiliency graph.

In another exemplary aspect an apparatus for enabling resiliency for cloud computing systems is provided. The apparatus includes means for modifying a topology graph of a network architecture by mapping processes flows onto the topology graph and means for creating a resiliency graph based on the modified topology graph. The apparatus also includes means for modifying the resiliency graph by translating at least one SLA into the resiliency graph and means for identifying overlaps and dependencies in the modified resiliency graph.

The on demand aspects of cloud computing such as the scalability and flexibility to enable more and more systems to support provide automation make it difficult to apply traditional high availability HA architectures and delivery methods.

Various exemplary embodiments provide techniques for discovering and creating a network topology graph including a resiliency graph. The method includes classifying flows and processes based on resilience requirements and mapping them on top of the topology graph. An initial resiliency graph is created and subsequent service level agreement SLA constraints are translated into the resiliency graph. System overlaps and dependencies are identified along with points of failure. Resiliency is calculated in view of an optimally sharing backup infrastructure. Additionally planning is included for virtual environment capacity high availability and migration. A unified resiliency graph is created with 1 K replication for critical system and K 1 sharing of primary and backup capacity for independent sub processes.

Shared virtual machines VM can manage different service level agreements SLA . Thus VMs should not share k redundant system but can share back up with independent systems. Shared application cannot manage different SLA so it is recommended to split the application functionality such as between client UI and business support UI for example .

A service topology representation can be used to identify the service composition by mapping the infrastructure and resource allocation based on scalability requirements. This service topology representation can then be altered to satisfy HA requirements. The resulting representation can be provided as an output. In such as way a particular topology graph can be modified and output as a new graph optimized for HA.

The server provides cloud computing services to the computers . Services may be provided by independent processes or shared processes where one or more process subsystems for multiple processes are performed by a single process . While an independent process is relatively secure from issues facing other processes an independent process may use additional system resources such as processor time memory etc. . Conversely shared processes may provide more efficient use of system resources but a single failure may result in multiple processes being adversely impacted.

In a first non limiting example the third subsystem the third subsystem and the third subsystem are shared by all three processes. For example a single module thread on a processing unit may perform the actions of the third subsystems . In such cases the processes may be split duplicated for operation by different processing units or different modules in the same processing unit. Alternatively HA requirements may be applied to the most critical aspects of the processes.

In another non limiting example the high critical process and the mid critical process share subsystems C and subsystems D . For critical HA these subsystems as well as their backup do not share the same hypervisor virtual machine manager. For low HA these subsystems as well as their backup can share the same infrastructure.

In a further non limiting example subsystems B are replicated for workload management. In the cloud computing system if all VMs are on the same hypervisor the HA may be compromised and a primary and backup split is considered in order to ensure satisfactory HA performance. Such a split may be referred to as application replication.

Application replication provides an application based model centric replication model. This replication is focused on keeping consistent database DB content when data replicates. Checkpoints are selected to communicate logically complete sets of information in order to reduce bandwidth use by avoiding intermediate DB updates and focuses on complete function. Replica sites are kept in a consistent state that is a delayed view of the whole.

Implementation options can vary for data transmission. For example data transmission may be queue based when transaction packets can be contained the transaction packets are for file replication etc.

A peer to peer replication model may be used in order to sync two or more application environments. Each server is an equal peer with equal ownership of the data. Thus no server is sole master owner of the data.

The first Portal Front Office BBS includes an application receive send process for messages received at the first Portal Front Office BBS from third Portal Front Office BBS and sent to the third Portal Front Office BBS from first Portal Front Office BBS via the first queuing service and an application receive send process for messages received at the first Portal Front Office BBS from second Portal Front Office BBS and sent to the second Portal Front Office BBS from first Portal Front Office BBS via the second queuing service .

The second Portal Front Office BBS includes an application receive send process for messages received at the second Portal Front Office BBS from first Portal Front Office BBS and sent to the first Portal Front Office BBS from second Portal Front Office BBS via the second queuing service and an application receive send process for messages received at the second Portal Front Office BBS from third Portal Front Office BBS and sent to the third Portal Front Office BBS from second Portal Front Office BBS via the third queuing service .

The third Portal Front Office BBS includes an application receive send process for messages received at the third Portal Front Office BBS from second Portal Front Office BBS and sent to the second Portal Front Office BBS from third Portal Front Office BBS via the third queuing service and an application receive send process for messages received at the third Portal Front Office BBS from first Portal Front Office BBS and sent to the first Portal Front Office BBS from third Portal Front Office BBS via the first queuing service .

In order to ensure that particular subsystems do not share the same hypervisor virtual machine manager Q Replication may be used. Q replication is a high volume low latency replication solution that uses queuing such as WebSphere MQ for example to transmit transactions between source and target databases or subsystems. For Q replication a peer to peer replication model may be used in order to add two or more database instances or clusters. All servers are equal peers with equal ownership of the data. Thus no server is the master or owner of the data.

Application replication enables systems to target changes that need replication to peers and avoids replicating transitional data. Network bandwidth usage is more controlled and contained and latency is related to the granularity design of application replication. Furthermore collision management can be more intelligent and robust in order to manage collisions such as deletes updates etc. . Using broad based code changes application replication can communicate data updates to peers and incorporate remote changes into operational data in the peers. Care should be taken to re asses flows for new features to ensure every release replicates properly such as during development activities and or testing for example.

Replication is managed by the database such as DB2 for example and provides transparent replication from a development activity point of view . This replication is low latency and asynchronous. Collisions are mitigated through a policy which determines which data should supersede the other.

Data configuration may be used when a new table or column is introduced or removed. This can cause high bandwidth consumption. Furthermore data model consistency is not ensured at any given point in time. Rather caching mechanisms can be used to be aware of important changes in order to maintain adequate caches in peer systems. This can lead to possible replication of transitional data but that can be avoided by not synchronizing targeted columns tables or adapting code to transition data to specific tables.

In one non limiting example of a cloud computing system a business support service BSS system may be provided. A BSSmay be used to provide customers with various services. The BSScan provide the UI. API and minimal BSS capabilities needed for steady state use by customers. A BSSmay be used to provide business users access to other services. The BSScan provide BSS capabilities like catalog management customer on boarding reporting metering rating and interaction with Back Office systems.

A web processing engine provides modules for authentication a load balancer and lightweight directory access protocol LDAP . The web processing engine communicates with the Portal Front Office BBS through a portal and API and an abstraction layer .

Various exemplary embodiments processes input describing a system such as a topology process and as is resiliency graph for example and determine modifications to the system in order to optimize the system for various HA purposes. The system description may describe serial and parallel paths dependencies and other system aspects such as hardware HW and software SW failure distributions for example. Additional information may also be provided in order to describe any desired HA service level agreement SLA environment temperature distribution and or synchronization requirements when not provided at the process level and or technical level through validations .

Upon completion various exemplary embodiments supply information for parallel redundancy and K redundancy for example with a modified topology graph or other description of the processes and changes. Parallel redundancy may be provided such as for a application server farm or data center replication. K redundancy includes shared infrastructure for independent network links and or independent processes. Independent processes such as edges in a topology graph do not have overlapping systems such as vertices in a topology graph . Serial redundancy may also include notifications for manual processes.

An exemplary embodiment is a method to provide K redundant resiliency for cloud computer. The method discovers or creates the system and network topology graph. The processes clients flows are mapped on top of the topology graph. Next the method identifies system overlaps and dependencies among processes systems and site deployment single points of failure. Customer and business support processes may overlap due to common application to provide web front end and underlying services. Software packaging may include various dependencies such as data repository RO for customer processes while WR for business support processes for example . An example of a single point of failure is a common web front deployed in one data center.

Based on the data in the topology graph and the mapped flows the component model representation can be transformed from the current state into a graph representation. Processes and their systems components may be detailed and classified based on their individual resiliency requirements. For example customer processes and business support processes may have different HA requirements.

A business support processes may desire less strong resiliency than a customer processes and can be hosted on less hardware while a customer processes may request high availability data replication HADR and operational scaling which may involve more hardware usage. In one example customer processes do not allow rollover to standby delay instead preferring an active active operational environment. Additionally customer processes may use distributed locations allowing for reduced latency for web based customers. Customer processes may also wish to enable rolling upgrade of customers. In contrast batch environment failures may only impact the business support and catalog update activities.

Next the method translates the SLA constraints such as performance management etc. into IT features in the resiliency graph. Some cloud systems may not carry specific SLAs in such case other types of constraints may be translated.

The method also generates a unified resiliency graph documentation describing how the system is to be through 1 K replication for critical systems and setup of backup capacity for independent sub processes. Front office critical systems may be provided as parallel systems and set up with active active operational environment and replication. Independent processes such as business support processes and customer facing processes may be split into different systems and are deployed with different HA solutions 

If the UI API BSS a common web front in is identified as a potential point of failure the business office user is moved to use the first mid office BSS instance while the first customer the second customer and third customer are each provided a separate instance of a UI API BSS .

The individual instances of a UI API BSS are parallel systems and have an active active operational environment. In this case K is three for the three instances of the UI API BSS providing a 3 redundant resiliency system.

The first mid office BSS instance is a critical systems and may be setup with a backup capacity for independent sub processes.

Another potential point of failure is identified as the first mid office BSS instance . Thus a second mid office BSS instance is created for datacenter B . This second mid office BSS instance is initially set up in a standby mode.

In order to complete the replication of the UI API BSS data replication is setup to ensure reasonably synched data for the first instance of a UI API BSS the second instance of a UI API BSS and the third instance of a UI API BSS . Likewise data replication is setup for the active first mid office BSS instance and the second mid office BSS instance on standby .

A point of failure may be the first instance of a UI API BSS for example the first instance of a UI API BSS may lock up or otherwise become non responsive. This prevents the first customer from accessing cloud computing services via datacenter A .

In order to resolve the failure the first customer is allowed to share the second instance of a UI API BSS with a second customer . Due to the data replication the transfer can occur with minimal impact on services provided to the first customer or even occur transparently . The third customer should experience little to no impact on the third instance of a UI API BSS .

A second point of failure is the first mid office BSS instance . This would prevent the business office user accessing cloud computing services via datacenter A .

In order to resolve this second point of failure the business office user may be moved from the failed first mid office BSS instance to the second mid office BSS instance in datacenter B . Accordingly the second mid office BSS instance is now made active.

Based on the foregoing it should be apparent that various exemplary embodiments provide a method apparatus and computer program s to provide resiliency in cloud computer systems. Resiliency is provided by considering processes dependency in view of optimally sharing of the replicated infrastructure. Capacity planning HA and migration concerns are combined in virtual environment.

The various blocks shown in may be viewed as method steps and or as operations that result from operation of computer program code and or as a plurality of coupled logic circuit elements constructed to carry out the associated function s .

Reference is made to for illustrating a simplified block diagram of an electronic device and apparatus that is suitable for use in practicing various exemplary embodiments.

In an apparatus such as a computer is depicted which is suitable for use as any one of computers or server . The computer includes a controller such as a computer or a data processor DP and a computer readable memory medium embodied as a memory MEM that stores a program of computer instructions PROG .

The PROGs is assumed to include program instructions that when executed by the DP enables the device to operate in accordance with exemplary embodiments.

That is various exemplary embodiments may be implemented at least in part by computer software executable by the DP of the computer by hardware HW or by a combination of software SW and hardware and firmware .

The computer readable MEM may be of any type suitable to the local technical environment and may be implemented using any suitable data storage technology such as semiconductor based memory devices flash memory magnetic memory devices and systems optical memory devices and systems fixed memory and removable memory. The DP may be of any type suitable to the local technical environment and may include one or more of general purpose computers special purpose computers microprocessors digital signal processors DSPs and processors based on a multicore processor architecture as non limiting examples.

In general the various exemplary embodiments may be implemented in hardware or special purpose circuits software logic or any combination thereof. For example some aspects may be implemented in hardware while other aspects may be implemented in firmware or software which may be executed by a controller microprocessor or other computing device although not limited thereto. While various aspects of the exemplary embodiments may be illustrated and described as block diagrams flow charts or using some other pictorial representation it is well understood that these blocks apparatus systems techniques or methods described herein may be implemented in as nonlimiting examples hardware software firmware special purpose circuits or logic general purpose hardware or controller or other computing devices or some combination thereof.

It should thus be appreciated that at least some aspects of the exemplary embodiments may be practiced in various components such as integrated circuit chips and that the exemplary embodiments may be realized in an apparatus that is embodied as an integrated circuit. The integrated circuit or circuits may comprise circuitry as well as possibly firmware for embodying at least one or more of a data processor or data processors and memories that are configurable so as to operate in accordance with the exemplary embodiments.

An exemplary embodiment provides a method for enabling resiliency for cloud computing systems. The method includes modifying such as by a processor a topology graph of a network architecture by mapping processes flows onto the topology graph. The method includes creating such as by a processor a resiliency graph based on the modified topology graph. The method includes modifying such as by a processor the resiliency graph by translating at least one SLA into the resiliency graph. The method also includes identifying such as by a processor overlaps and dependencies in the modified resiliency graph.

In another exemplary embodiment of the method above the method also includes determining at least one potential point of failure based on the overlaps and dependencies 

In a further exemplary embodiment of any one of the methods above the method also includes classifying the potential point of failure.

In another exemplary embodiment of any one of the methods above the method also includes in response to determining that the potential point of failure is a subsystem shared by multiple processes splitting the subsystem into a plurality of instances of the subsystem.

In a further exemplary embodiment of any one of the methods above the method also includes in response to determining that the potential point of failure is a plurality of critical subsystems shared by multiple processes ensuring the plurality of critical subsystems does not share a hypervisor.

In another exemplary embodiment of any one of the methods above the method also includes in response to determining that the potential point of failure is a plurality of non critical subsystem shared by multiple processes allowing the plurality of non critical subsystem to share infrastructure resources.

In a further exemplary embodiment of any one of the methods above the method also includes in response to determining that the potential point of failure is a replicated subsystem determining a primary and backup split for the replicated subsystem.

In another exemplary embodiment of any one of the methods above the method also includes calculating resiliency based on an infrastructure of the network architecture.

In a further exemplary embodiment of any one of the methods above the method also includes classifying processes based on resiliency requirements.

Another exemplary embodiment provides an apparatus for enabling resiliency for cloud computing systems. An apparatus includes a processor such as DP and a memory such as MEM storing computer program code such as PROG . The memory and the computer program code are configured to with the processor cause the apparatus to perform actions. The actions include modifying a topology graph of a network architecture by mapping processes flows onto the topology graph. The actions include creating a resiliency graph based on the modified topology graph. The actions include modifying the resiliency graph by translating at least one SLA into the resiliency graph. The actions also include identifying overlaps and dependencies in the modified resiliency graph.

In a further exemplary embodiment of the apparatus above the actions also include determining at least one potential point of failure based on the overlaps and dependencies.

In another exemplary embodiment of any one of the apparatus above the actions also include classifying the potential point of failure.

In a further exemplary embodiment of any one of the apparatus above the actions also include in response to determining that the potential point of failure is a subsystem shared by multiple processes splitting the subsystem into a plurality of instances of the subsystem.

In another exemplary embodiment of any one of the apparatus above the actions also include in response to determining that the potential point of failure is a plurality of critical subsystems shared by multiple processes ensuring the plurality of critical subsystems does not share a hypervisor.

In a further exemplary embodiment of any one of the apparatus above the actions also include in response to determining that the potential point of failure is a plurality of non critical subsystem shared by multiple processes allowing the plurality of non critical subsystem to share infrastructure resources.

In another exemplary embodiment of any one of the apparatus above the actions also include in response to determining that the potential point of failure is a replicated subsystem determining a primary and backup split for the replicated subsystem.

In a further exemplary embodiment of any one of the apparatus above the actions also include calculating resiliency based on an infrastructure of the network architecture.

In another exemplary embodiment of any one of the apparatus above the actions also include classifying processes based on resiliency requirements.

A further exemplary embodiment provides an article of manufacture for enabling resiliency for cloud computing systems. The article of manufacture tangibly embodies computer readable instructions which when implemented cause a computer to carry out the steps of a method. The method includes modifying a topology graph of a network architecture by mapping processes flows onto the topology graph. The method includes creating a resiliency graph based on the modified topology graph. The method includes modifying the resiliency graph by translating at least one SLA into the resiliency graph. The method also includes identifying overlaps and dependencies in the modified resiliency graph.

In another exemplary embodiment of the article of manufacture above the method also includes determining at least one potential point of failure based on the overlaps and dependencies.

In a further exemplary embodiment of any one of the articles of manufacture above the method also includes classifying the potential point of failure.

In another exemplary embodiment of any one of the articles of manufacture above the method also includes in response to determining that the potential point of failure is a subsystem shared by multiple processes splitting the subsystem into a plurality of instances of the subsystem.

In a further exemplary embodiment of any one of the articles of manufacture above the method also includes in response to determining that the potential point of failure is a plurality of critical subsystems shared by multiple processes ensuring the plurality of critical subsystems does not share a hypervisor.

In another exemplary embodiment of any one of the articles of manufacture above the method also includes in response to determining that the potential point of failure is a plurality of non critical subsystem shared by multiple processes allowing the plurality of non critical subsystem to share infrastructure resources.

In a further exemplary embodiment of any one of the articles of manufacture above the method also includes in response to determining that the potential point of failure is a replicated subsystem determining a primary and backup split for the replicated subsystem.

In another exemplary embodiment of any one of the articles of manufacture above the method also includes calculating resiliency based on an infrastructure of the network architecture.

In a further exemplary embodiment of any one of the articles of manufacture above the method also includes classifying processes based on resiliency requirements.

In another exemplary embodiment of any one of the articles of manufacture above the articles of manufacture is a non transitory computer readable medium e.g. CD ROM RAM flash memory etc. .

In a further exemplary embodiment of any one of the articles of manufacture above the articles of manufacture is a storage medium.

Another exemplary embodiment provides an apparatus for enabling resiliency for cloud computing systems. The apparatus includes means for modifying such as a processor a topology graph of a network architecture by mapping processes flows onto the topology graph. The apparatus includes means for creating such as a processor a resiliency graph based on the modified topology graph. The apparatus includes means for modifying such as a processor the resiliency graph by translating at least one SLA into the resiliency graph. The apparatus also includes means for identifying such as a processor overlaps and dependencies in the modified resiliency graph.

In a further exemplary embodiment of the apparatus above the apparatus also includes means for determining at least one potential point of failure based on the overlaps and dependencies.

In another exemplary embodiment of any one of the apparatus above the apparatus also includes means for classifying the potential point of failure.

In a further exemplary embodiment of any one of the apparatus above the apparatus also includes means for splitting the subsystem into a plurality of instances of the subsystem in response to determining that the potential point of failure is a subsystem shared by multiple processes.

In another exemplary embodiment of any one of the apparatus above the apparatus also includes means for ensuring the plurality of critical subsystems does not share a hypervisor in response to determining that the potential point of failure is a plurality of critical subsystems shared by multiple processes.

In a further exemplary embodiment of any one of the apparatus above the apparatus also includes means for allowing the plurality of non critical subsystem to share infrastructure resources in response to determining that the potential point of failure is a plurality of non critical subsystem shared by multiple processes.

In another exemplary embodiment of any one of the apparatus above the apparatus also includes means for determining a primary and backup split for the replicated subsystem in response to determining that the potential point of failure is a replicated subsystem.

In a further exemplary embodiment of any one of the apparatus above the apparatus also includes means for calculating resiliency based on an infrastructure of the network architecture.

In another exemplary embodiment of any one of the apparatus above the apparatus also includes means for classifying processes based on resiliency requirements.

Various modifications and adaptations to the foregoing exemplary embodiments may become apparent to those skilled in the relevant arts in view of the foregoing description when read in conjunction with the accompanying drawings. However any and all modifications will still fall within the scope of the non limiting and exemplary embodiments.

It should be noted that the terms connected coupled or any variant thereof mean any connection or coupling either direct or indirect between two or more elements and may encompass the presence of one or more intermediate elements between two elements that are connected or coupled together. The coupling or connection between the elements can be physical logical or a combination thereof. As employed herein two elements may be considered to be connected or coupled together by the use of one or more wires cables and or printed electrical connections as well as by the use of electromagnetic energy such as electromagnetic energy having wavelengths in the radio frequency region the microwave region and the optical both visible and invisible region as several non limiting and non exhaustive examples.

Furthermore some of the features of the various non limiting and exemplary embodiments may be used to advantage without the corresponding use of other features. As such the foregoing description should be considered as merely illustrative of the principles teachings and exemplary embodiments and not in limitation thereof.

The following abbreviations that may be found in the specification and or the drawing figures are defined as follows 

