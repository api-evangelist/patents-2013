---

title: Techniques enabling use of a Wi-Fi direct services (WFDS) application services platform (ASP) for layer 2 services
abstract: Techniques are disclosed for using a WI-FI Direct Services (WFDS) Application Services Platform (ASP) for Layer 2 services, by extending a definition of a session in WFDS to include non-IP sessions as well. Techniques are further disclosed for operating an application services platform coordination protocol (ASP-CP) directly over a media access control (MAC) layer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09237591&OS=09237591&RS=09237591
owner: INTEL CORPORATION
number: 09237591
owner_city: Santa Clara
owner_country: US
publication_date: 20130722
---
61 812 846 filed on 17 Apr. 2013 entitled TECHNIQUES ENABLING USE OF A WI FI DIRECT SERVICES WFDS APPLICATION SERVICES PLATFORM ASP FOR LAYER 2 SERVICES 

61 819 078 filed on 3 May 2013 entitled TECHNIQUES ENABLING USE OF A WI FI DIRECT SERVICES WFDS APPLICATION SERVICES PLATFORM ASP FOR LAYER 2 SERVICES and

61 823 980 filed on 16 May 2013 entitled METHODS TO PORT THE WI FI DIRECT SERVICES ASP FOR OPERATION DIRECTLY OVER THE MAC.

With the increased popularity of Wi Fi networks for wireless connectivity there are new services being developed that use the underlying Wi Fi links for peripheral connectivity for example Wi Fi Serial Bus WSB which enables support of USB traffic over Wi Fi links and allows a WSB host to connect to Wi Fi enabled USB devices functions WSB peripherals wirelessly and to legacy USB devices functions via a Wi Fi enabled USB hub WSB Hub .

Wi Fi Direct provides peer to peer connectivity to allow users to connect their devices in an easy and convenient manner to share show print and synchronize content. However Wi Fi Direct only provides link layer connectivity. Wi Fi Direct is not enough to enable interoperability between services applications from multiple vendors. Users have inconsistent experiences due to lack of services interoperability and complexity of P2P topology.

Thus there are general needs for improved techniques using Wi Fi links for peripheral connectivity and general needs for improved techniques to improve service interoperability and decrease P2P topology complexity for Wi Fi Direct.

In the following description numerous specific details are set forth. However it is understood that embodiments of the invention may be practiced without these specific details. In other instances well known methods structures and techniques have not been shown in detail in order not to obscure an understanding of this description.

References to one embodiment an embodiment example embodiment various embodiments etc. indicate that the embodiment s of the invention so described may include a particular feature structure or characteristic but not every embodiment necessarily includes the particular feature structure or characteristic. Further repeated use of the phrase in one embodiment does not necessarily refer to the same embodiment although it may.

As used herein unless otherwise specified the use of the ordinal adjectives first second third etc. to describe a common object merely indicate that different instances of like objects are being referred to and are not intended to imply that the objects so described must be in a given sequence either temporally spatially in ranking or in any other manner.

Some embodiments may be used in conjunction with devices and or networks operating in accordance with existing Wireless Gigabit Alliance WGA specifications Wireless Gigabit Alliance Inc WiGig MAC and PHY Specification Version 1.1 April 2011 Final specification and or future versions and or derivatives thereof devices and or networks operating in accordance with existing IEEE 802.11 standards IEEE 802.11 2012 IEEE Standard for Information technology Telecommunications and information exchange between systems Local and metropolitan area networks Specific requirements Part 11 Wireless LAN Medium Access Control MAC and Physical Layer PHY Specifications Mar. 29 2012 IEEE802.11 task group ac TGac IEEE802.11 09 0308r12 TGac Channel Model Addendum Document IEEE 802.11 task group ad TGad IEEE P802.11ad Standard for Information Technology Telecommunications and Information Exchange Between Systems Local and Metropolitan Area Networks Specific Requirements Part 11 Wireless LAN Medium Access Control MAC and Physical Layer PHY Specifications Amendment 3 Enhancements for Very High Throughput in the 60 GHz Band and or future versions and or derivatives thereof devices and or networks operating in accordance with existing WirelessHD specifications and or future versions and or derivatives thereof units and or devices which are part of the above networks and the like.

To address the problems set forth above WFA formed the Wi Fi Direct Services WFDS task group TG . WFDS is tasked with defining a common set of application programming interfaces APIs and protocols enabling service interoperability. shown generally as depicts the architecture of the WFDS specification. The ASP coordination protocol ASP CP is assumed to run over IP

The core component of the WFDS specification is the definition of the Application Service Platform ASP . ASP is a logical entity that implements the common functions needed by application services such as play send display and print. Within the ASP different protocol elements are defined to realize device discovery service discovery P2P connection management and session management. Among those the ASP coordination protocol ASP CP is the name given to the protocol that allows two peer ASP entities to manage ASP sessions. describes where the ASP CP lies in the WFDS architecture.

Presently the WFDS specification defines the use of the ASP CP over IP only. Essentially this requirement imposes that all devices compliant with the WFDS specification must be capable of supporting an IP stack and associated management functions. While this might not be considered a difficult requirement to meet for devices such as phones laptops TV sets to name a few it does pose a challenge for a range of new device categories characterized by 

High date rates for interfaces that operate at very high bit rates e.g. 3 Gbps in 60 GHz generation and processing of IP packets could become a bottleneck in terms of efficiency and latency.

Lower complexity devices requiring IP support from very low complexity devices such as wireless keyboards wireless mouse to name a few is often an overkill and can lead to higher cost and power consumption.

Type of services certain services do not inherently need or use IP for their operation with cables. Examples include USB HDMI and DisplayPort DP . Therefore as these protocols become wireless reusing the same architecture which does not rely on IP is a suitable approach.

As a result of the above there has been an increasing demand in the industry to extend WFDS particularly ASP CP to operate directly over the MAC. In the process of doing that this should enable services such as shown in to also operate directly over the MAC.

Examples herein provide apparatus systems and methods that would allow the ASP CP and services to operate directly over the MAC i.e. without using IP . In these examples there are some key aspects that need to be taken into account given that IP is no longer present namely 

Traffic identification each service and WFDS messages need to be uniquely identified so that packets can be routed to the proper process. Therefore packets transferred between the MAC and upper layers need to identify the traffic type.

Scalability the methods should be scalable so that they can be used not only for services presently defined but also for future services.

Service isolation due to aspects such as security service isolation should be an important goal to be achieved. This refers to the capability to isolate one service from another so that security risks can be minimized.

Example method 1 is shown in shown generally as . In this approach the ASP is responsible for mux demux of ASP traffic as well as traffic belonging to any service and operating using the ASP. One Ethertype is shared across ASP and services and may support service isolation.

This implies that the ASP is responsible for tagging e.g. through service identifiers packets belonging to each service and and ASP in a uniquely identified manner. As a result packets can be routed to the appropriate end point whether that is a specific service or the ASP protocol itself.

To use this method the ASP needs to be allocated a new EtherType. EtherType is a two octet field in an Ethernet frame. It is used to indicate which protocol is encapsulated in the payload of an Ethernet Frame. Every service and using the ASP and the ASP protocol itself see would use the same Ethertype for transmitting to and receiving from the MAC.

This architecture can provide for service isolation and scalability. Service isolation is supported given that the ASP can manage the identification of the various services and in a dynamic manner. Such dynamicity would increase the level of security. Moreover new services can be added over time without changes to the architecture which makes it scalable.

Finally since the ASP can dynamically change the identification associated with services and this method requires that a service seeker and a service advertiser exchange service identifiers before transmitting or receiving service data. This is needed so that packets are routed to the correct end point upon reception.

The downside of method 1 is that it increases the complexity of the ASP and makes the delivery of a service dependent on the ASP . Method 2 proposes a decentralized architecture whereby each service interacts directly with the bottom MAC layer. This is depicted in . In an ASP and each service have a well known Ethertype. In an example herein the number of Ethertypes may be proportional to the number of services and in an example herein does not support service isolation.

In this method not only the ASP traffic is identified by an Ethertype like in method 1 but also each service has its own Ethertype. Therefore the number of Ethertypes implied by this method is proportional to the number of services.

Method 2 provides stronger support for scalability since service delivery does not rely solely on the ASP. Each service can be independently enabled over the MAC. With respect to service isolation method 2 does not provide the same level of isolation as method 1 since the Ethertypes are well known identifications which allows devices to attempt to access use a service before obtaining the proper authorization from the ASP.

Method 3 shown in generally as improves the service isolation of method 2 by having the ASP dynamically assign the Ethertype used by each service. This may support service isolation. Specifically the ASP manages a pool of Ethertypes. Once a service becomes in use the ASP assigns an Ethertype to that particular service and . Over the lifetime of a service it can use different Ethertypes assigned by the ASP.

Moreover due to the dynamic allocation of Ethertypes this requires that a service seeker and a service advertiser exchange Ethertypes before transmitting or receiving service data. This is needed so that packets are routed to the correct end point upon reception. Method 3 relies on the fact that the ASP manages a pool of Ethertypes and dynamically assigns them to services and .

Method 4 is an alternative approach shown in at that does not require formal allocation of Ethertypes which is done through the IEEE is by defining a frame structure that allows the ASP to configure a Service ID for each service and within the frame itself.

In method 4 one Ethertype is allocated for the ASP . The services can either use the same Ethertype as ASP or use a separate Ethertype that can be used by all services and . In either case means are necessary to uniquely identify the service so that packets can be routed to the appropriate service. For that examples herein define a new Service type field that is part of the payload of the frame as shown in . In this Packet structure the Payload Header field signals the specific service. LLC field and SNAP field are shown as and respectively. The payload carries data associated with the service. As opposed to method 3 where the ASP would configure Ethertypes in the case of the ASP would dynamically configure values of Service types to be used by the various services. Once a Service type value is assigned all the packets belonging to that service use the assigned Service type value.

The ASP can dynamically change the Service type value used by a service. This provides for enhanced security and service isolation. The length of the Service type field depends on how many services are supported but can be as short as one octet. Finally similar to method 3 due to the dynamic allocation of Service type values this requires that a service seeker and a service advertiser exchange Service type values before transmitting or receiving service data. This is needed so that packets are routed to the correct end point upon reception.

It is important to highlight the difference between method 1 and method 4. In method 4 a packet using the Services Ethertype can be delivered either to all services and each service would then drop the packet if it does not match the intended Service type or to a mux demux function that would do the forwarding to the correct service. In method 1 on the other hand ASP becomes a layer that sits above the MAC and below the Service on the data path.

With increased popularity of Wi Fi networks for wireless connectivity there are new services being developed that use the underlying Wi Fi links for peripheral connectivity for example Wi Fi Serial Bus WSB which enables support of USB traffic over Wi Fi links and allows a WSB host to connect to Wi Fi enabled USB devices functions WSB peripherals wirelessly and to legacy USB devices functions via a Wi Fi enabled USB hub WSB Hub . WSB defines two modes of operation Native mode in which the WSB directly interfaces with the MAC and the IP mode in which the WSB traffic is encapsulated as IP traffic before being sent to the MAC. WSB relies on Wi Fi Direct P2P technology as an enabling technology for discovery of devices that are WSB capable.

Wi Fi Direct Services WFDS is a technology that defines an interoperability framework for service discovery and session management for services that use Wi Fi Direct. However WFDS as defined is not applicable to WSB for two main reasons 

Embodiments herein address the connection and service sessions that are limited to IP sessions by extending the definition of session in WFDS to include non IP sessions as well.

Embodiments herein extend the definition of connection and session in WFDS framework to include non IP sessions. WFDS defines Application Services Platform ASP as a logical entity which is among other things responsible for session management for different services. However the ASP session itself and the application services sessions are established over TCP IP connections.

1 Extend the definition of an ASP session to be a logical session established over either a Layer 2 or an IP connection between a seeker and an advertiser . An ASP session would be established over an IP connection if both devices A and B support IP and established over layer 2 otherwise for example if the advertiser is a non IP Wi Fi device like a Wi Fi mouse which does not support an IP stack.

3 For IP services for example WSB IP mode embodiments define ASP Service session as either a TCP or a UDP connection. Whether the TCP or UDP is used is identified by the proto parameter in the ALLOWED PORT message defined in WFDS.

4 For non IP Services like native mode WSB embodiments define ASP Service session exclusively as a logical channel over a Layer 2 connection. The characteristics parameters associated with this Layer 2 channel can be negotiated using the ASP Coordination Protocol which itself can be running either as an IP or non IP session i.e. Layer 2 session . If the ASP Coordination Protocol runs over an IP session then the mechanism for establishing a non IP service session is as follows 

A new field is defined to be added in the REQUEST SESSION message defined in WFDS to identify the session type. This new field is called session type field and can take at least two values indicating whether the requested session is to be established over IP or over Layer 2. For example the definition of REQUEST SESSION in WFDS can be modified as below to accommodate the new subfield. It is noted that the field can be located differently with a different length and the mapping of the values to the session types may be different from the example below.

b. Service Seeker ASP requests a new ASP Session for the advertised advertisement id to Service Advertiser ASP .

c. The Service Advertiser which is recipient of this command shall send ADDED SESSION or REJECTED SESSION message within seconds after receiving a REQUEST SESSION message. Failure to receive a response shall trigger a SessionStatus with Closed status Event at the requestor Service Seeker end.

The ASP coordination protocol defined in WFDS consists of commands and responses either ACK or NACK that are sent in form of a single UDP datagram. In Layer 2 ASP coordination protocol each of these commands are sent as ASP Session Action frame an IEEE 802.11 Action Frame. The retry mechanisms associated with 802.11 Action Frame apply to ASP coordination protocol.

Table 2 below provides an embodiment of a general format of ASP Session Action Frame. The format of ASP Session Action frame is defined as 

A Layer 2 session is established as a logical channel carrying the data related to the specific service between the seeker and the advertiser . This logical channel may be identified by different parameters specifically related to Layer 2 one example may be the parameters in the TSPEC element defined in IEEE 802.11 standard .

In order to enable the devices to establish the layer 2 logical channel we define the ASP coordination protocol message below which is used to communicate the information regarding the logical channel between the seeker and the advertiser SESSION PARAMETERS 

Additionally an embodiment defines two new ASP Methods and an ASP Event to bind and release the Level 2 logical channel to the layer 2 service and to carry the information regarding the status of the logical channel 

Antenna module provides for the exchange of wireless signals with remote devices. Moreover antenna module may transmit wireless signals through one or more directional radiation patterns. Thus antenna module may include multiple antennas and or multiple radiating elements e.g. phased array radiating elements .

Transceiver module provides an interface between antenna module and host module . For instance transmitter portion within transceiver module receives symbols from host module and generates corresponding signals for wireless transmission by antenna module . This may involve operations such as modulation amplification and or filtering. However other operations may be employed.

Conversely receiver portion within transceiver module obtains signals received by antenna module and generates corresponding symbols. In turn receiver portion provides symbols to host module . This generation of symbols may involve operations including but not limited to demodulation amplification and or filtering.

The symbols exchanged between host module and transceiver module may form messages or information associated with one or more protocols and or one or more user applications. Thus host module may perform operations corresponding to such protocol s and or user application s . Further exemplary protocols include various media access network transport and or session layer protocols. Exemplary user applications include telephony messaging e mail web browsing content e.g. video and audio distribution reception and so forth.

In addition host module may exchange control information with transceiver module . This control information may pertain to the operation and status of transceiver module . For instance this control information may include directives that host module sends to transceiver module . Such directives may establish operating parameters characteristics for transceiver module . Also this control information may include data e.g. operational status information that host module receives from transceiver module . It may further incorporate commands and messages that as enable the application services platform coordination protocol ASP CP and services to operate directly over the MAC and enable using a WI FI Direct Services WFDS Application Services Platform ASP for Layer 2 services by extending a definition of a session in WFDS to include non IP sessions as well.

As described above transmitter portion generates signals from symbols and receiver portion generates symbols from received signals. To provide such features transmitter portion and receiver portion may each include various components such as modulators demodulators amplifiers filters buffers upconverters and or downconverters. Such components may be implemented in hardware e.g. electronics software or any combination thereof.

The techniques described herein may be embodied in a computer readable medium for configuring a computing system to execute the method. The computer readable media may include for example and without limitation any number of the following magnetic storage media including disk and tape storage media optical storage media such as compact disk media e.g. CD ROM CD R etc. and digital video disk storage media holographic memory nonvolatile memory storage media including semiconductor based memory units such as FLASH memory EEPROM EPROM ROM ferromagnetic digital memories volatile storage media including registers buffers or caches main memory RAM etc. and data transmission media including permanent and intermittent computer networks point to point telecommunication equipment carrier wave transmission media the Internet just to name a few. Other new and various types of computer readable media may be used to store and or transmit the software modules discussed herein. Computing systems may be found in many forms including but not limited to mainframes minicomputers servers workstations personal computers notepads personal digital assistants various wireless devices and embedded systems just to name a few. A typical computing system includes at least one processing unit associated memory and a number of input output I O devices. A computing system processes information according to a program and produces resultant output information via I O devices.

Realizations in accordance with the present invention have been described in the context of particular embodiments. These embodiments are meant to be illustrative and not limiting. Many variations modifications additions and improvements are possible. Accordingly plural instances may be provided for components described herein as a single instance. Boundaries between various components operations and data stores are somewhat arbitrary and particular operations are illustrated in the context of specific illustrative configurations. Other allocations of functionality are envisioned and may fall within the scope of claims that follow. Finally structures and functionality presented as discrete components in the various configurations may be implemented as a combined structure or component. These and other variations modifications additions and improvements may fall within the scope of the invention as defined in the claims that follow.

