---

title: System and method for supporting messaging in a fully distributed system
abstract: A system and method can support messaging in a fully distributed system. The fully distributed system includes a plurality of agents. An agent in the plurality of agents operates to determine an address for a message, wherein said address is determined at least partially according to a content of the message. Then, said agent can select a path to transmit the message according to said address, and send the message according to said path directly to said address.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09369382&OS=09369382&RS=09369382
owner: ORACLE INTERNATIONAL CORPORATION
number: 09369382
owner_city: Redwood Shores
owner_country: US
publication_date: 20130930
---
This application is a continuation of U.S. patent application Ser. No. 11 949 166 entitled SYSTEM AND METHOD FOR COMMUNICATION AGENT WITHIN A FULLY DISTRIBUTED NETWORK filed Dec. 3 2007 now as U.S. Pat. No. 8 549 122 which claims the benefit of priority under 35 U.S.C. to U.S. Provisional Patent Application 60 868 359 entitled DISTRIBUTED NETWORK by Sharon Azulai filed on Dec. 4 2006.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

The present invention is of a system and method for an ESB Enterprise Service Bus for a distributed network and in particular for an ESB having a fully distributed architecture.

Organizations including corporations and other typically large entities need scalable efficient solutions for network architecture which enables even remote distributed components and or legacy systems to communicate. Small businesses and other small organizations also have such needs but design paradigms which may be sufficient for smaller entities often fail to work on the significantly larger scale required by large corporations.

One example of such a network architecture is Enterprise Service Buses ESBs . As described in a white paper by Steve Craggs Best of Breed ESBs EAI Industry Consortium Saint Consulting Limited 2003 ESBs help to support the latest technologies such as Service Oriented Architectures SOAs which provide components and even legacy systems to the network in the form of services. These services should be structured so that they can cooperate and interact without requiring highly specialized human skills and or specially designed and constructed software. ESBs assist with these interactions effectively acting as an enterprise nervous system Craggs white paper quoting the Gartner Group p. 5 by providing an IT backbone Craggs white paper p. 6 . ESBs are prepackaged and are preferably usable off the shelf however as described in greater detail below not all ESBs meet this goal.

According to the above white paper in order to perform these tasks effectively and return the maximum value to the organization enterprise ESBs should have the following features messaging transformation and intelligent routing services particularly by using XML extensible mark up language described in greater detail below support for Web services and other types of services including having a SOA structure support for distributed components and such features as manageability scalability robustness to failure and so forth p. 9 of the above white paper .

Messaging may be transmitted through a message architecture concept called MOM messaging oriented middleware which is used to support message distribution without a strict orientation to the destination of the message or connection required to send that message. For example MOM architectures support content based routing for messages in which a message is distributed by topic rather than by an address. It should be noted that such routing currently does not involve actual analysis of the content of the message itself. MOM architectures also support asynchronous message delivery and the ability of applications components in a network to subscribe to messages and to publish messages. All of these facilities should be extended by the ESB architecture through the use of message brokers. Unfortunately such message brokers are centralized and may cause single point of failure and or bottleneck problems.

MOM is currently being superseded by next generation messaging which also uses message brokers but which provides additional functionality to further avoid connection specific addressing for messages. Unfortunately this type of technology does not solve the problem of message brokers.

These different architectures typically use or alternatively may use XML for messages. XML is a highly standardized language which is easy to parse transform analyze and otherwise manipulate. It has a number of disadvantages however particularly with regard to the size of the XML messages. Because these messages are comprehensible by humans and are not binary machine readable messages they tend to be very large. Such large messages in turn place additional stress on currently message system architectures which rely on one or more centralized brokers. Furthermore previously designed tools such as firewalls cannot always understand or properly handle XML for example some known firewalls fail to properly parse and or block XML messages even those which are machine to machine communication because XML messages are different from regular messages.

New tools are therefore required which can handle XML well and which also provide ESB functionality while avoiding current ESB problems such as potential single point of failure problems and bottleneck problems caused by the requirement for centralized broker s . Even the use of more than one such broker simply distributes the problem across more than one point but does not solve the underlying weakness of a centralized system.

Described herein are systems and methods that can support messaging in a fully distributed system. The fully distributed system includes a plurality of agents. An agent in the plurality of agents operates to determine an address for a message wherein said address is determined at least partially according to a content of the message. Then said agent can select a path to transmit the message according to said address and send the message according to said path directly to said address.

The invention is illustrated by way of example and not by way of limitation in the figures of the accompanying drawings in which like references indicate similar elements. It should be noted that references to an or one or some embodiment s in this disclosure are not necessarily to the same embodiment and such references mean at least one.

The background art does not teach or suggest a system or method for a messaging mechanism which does not require one or more message brokers. The background art also does not teach such a system or method for an ESB which does not have some type of centralized routing component.

The present invention overcomes these disadvantages of the background art by providing a system and method for handling communication in a network without any centralized component s . The present invention is useful for those networks being implemented according to a service oriented architecture such as for an ESB enterprise service bus for example. The present invention features a fully distributed service bus unlike background art networks which rely upon some type of centralization function for messages such that a plurality of components in the network rely upon communication through a centralized message broker. Such centralized message brokers represent a potential single or at least concentrated point of failure and also a potential bottleneck even if a plurality of such brokers is available in the network. By contrast the completely distributed nature of the present invention prevents such single or concentrated point of failures as well as preventing potential bottlenecks for message transmission. Furthermore such architecture provides potentially unlimited scalability.

Optionally and preferably messages are in XML extensible mark up language for preferred embodiments of the present invention. Also optionally and preferably different types of message protocols may optionally be used including but not limited to JMS HTTP TCP messages RMI remote method invocation which is a Java technology and is used for one object on a JVM Java virtual machine to call a method on another object on another JVM . Any other suitable type of message protocol may also optionally be used.

According to another optional embodiment of the present invention there is provided a smart publish subscribe function which more easily enables agents to provide information related to published information and or to information to which the agent wishes to subscribe. As described in greater detail below optionally and preferably fully distributed queues may be provided in order to assist in publication of information and rapid distribution to subscribers. The distributed queue is preferably distributed between a plurality of agents for example if there are several agents publishing the same topic or queued material such as the same XML message and or portions of the same XML message. The distributed queue may also optionally occur if the same information is included in a plurality of different messages in which case the recurring information is preferably available from any queue of agent publishing a message containing that recurring information. Optionally and preferably the agents may communicate between themselves to avoid replicating information between queues.

According to other preferred embodiments of the present invention there is preferably provided discovery of agents and their capabilities by an agent which is more preferably automatic. Such automatic discovery may optionally and preferably occur upon initialization of agent and or re initialization after failure of the agent. The agent preferably provides information to other agent s in the domain s of that agent for example optionally through reliable multicast concerning the agent s capabilities information to be published by the agent and or information to which the agent wishes to subscribe. In addition the agent preferably receives a map concerning such information about the other agent s in the domain more preferably from the central management console. This map enables the agent to discover such information about the other agent s in the domain in an automated manner thereby preferably updating the world model of the agent s .

The present invention preferably provides automatic discovery and easy installation for adding a new agent which is more preferably performed as an on the fly operation. Such an on the fly operation is also preferably provided for installing new clients etc. According to preferred embodiments of the present invention it is not necessary to shut down the network and or to have no down time for the network for such installation.

According to still another embodiment of the present invention there is provided the capability of flexible connections between agents such that an agent may optionally and preferably choose the type of connection to another agent or agents for transmitting information. More preferably such a connection is selected according to at least one of a cost function availability of the connection or scale of the connection and or transmission s . Examples of such connections include but are not limited to connections such as TCP UDP RUDP reliable UDP broadcast multicast reliable multicast tunneling and unicast and others. The connection may optionally be permanent or non permanent.

According to another preferred embodiment of the present invention there is provided a fully distributed network for providing a passive service as an active service by adding push capabilities to the service. For example the use of a fully distributed network enables Web services which are usually passive and which usually do not use push capabilities to be provided as active services with push capabilities. As a non limiting example an agent may optionally communicate with the Web service on a regular and or periodic basis to receive information and may then optionally publish the received information thereby pushing the received information. Preferably the agent communicates with the Web service frequently for example on the order of seconds.

According to preferred embodiments of the present invention the fully distributed network is also able to perform synchronization of tasks across the distributed components without requiring a central message broker or any type of centralized functionality. Instead synchronization is preferably performed by communication between agents for example with regard to a distributed queue of messages as described in greater detail below.

The present invention optionally and preferably features a plurality of different types of agents. Non limiting examples of these agents include an agent as described below with regard to the Figures also referred to as a peer agent or normal agent a proxy agent and a relay agent. A proxy agent carries some of the processing load of a peer agent. The processing load may optionally include such tasks as validation parsing transformation template matching etc.

A relay agent preferably acts as a kind of a bridge between two agents. A relay agent is used in cases where a direct connection between the two agents is not possible. For example one agent may be located inside the MZ militarized or secure zone and while another agent may be located on the Internet. The relay agent is then preferably located in the DMZ de militarized zone and facilitates bridging between both agents.

According to preferred embodiments the present invention enables an agent to perform true content based switching. Such switching which also includes the functionality of routing has a number of advantages for example it enables other agents to request data according to its content such as a topic for some messaging protocols such as XML or JMS for example. It also supports publication of data by content and avoids the pitfalls of mismatched and or incomplete categories when data is published.

XML is an example of a useful language for such a message because it allows data to be separated into a plurality of elements for example according to a template. However any other language may optionally be used alone or in combination if the data can be parsed for determining subscription to the data.

The switching process according to the present invention also preferably enables the determination of the transport mechanism according to which the message should be sent including but not limited to unicast multicast or broadcast for example and or such persistent connections as TCP and or RUDP reliable UDP for example. Preferably the present invention is able to select which transport mechanism is used and more preferably also to drop reconnect and or swap connections most preferably according to a cost function. These features have not yet been included in an agent based switching system which does not use a central message broker of any type instead currently available background systems use such a central message broker. The present invention therefore provides truly distributed switching.

The principles and operation of the present invention may be better understood with reference to the drawings and the accompanying description.

Referring now to the drawings shows an exemplary agent architecture according to the present invention. As shown an agent preferably features an agent core shown in more detail with regard to with an agent fa ade . Agent fa ade preferably features an open API application programming interface which exposes methods and information to clients and or to other applications in the system shown as a client communicating with agent through agent fa ade . Agent fa ade enables agent to communicate with these other applications in the system without predetermined programming for each such application.

Agent core preferably features the internal functions and processes which enable a plurality of agents to operate without any type of message broker for communication across a network.

Agent preferably also features a protocol layer and a network layer . Network layer handles communication with one or more other agents with which agent is in communication not shown the presence of network layer preferably enables agent to communicate with the other agents regardless of network architecture and or the type of network or network protocols being used. Network layer also preferably supports switching and routing functions and other functions for transmitting and or receiving messages by agent through the network. Protocol layer preferably handles objects used for the operation of the present invention including performing marshalling and unmarshalling of messages related to the present invention through network layer . Messages are analyzed according to content such as a topic for example in order to determine where the message should be transmitted while network layer preferably handles the actual transport but is not concerned with the content of the message.

General services are preferably provided by an infrastructure layer which as shown may optionally provide one or more services to each component of agent . Infrastructure layer is described in greater detail below with regard to .

Agent core also preferably features a core logic including those components required for the internal functioning and logic of the agent. Core logic preferably features an outgoing message logic for messages to be sent from the agent and a message consumer for incoming messages to the agent. Each of outgoing message logic and message consumer preferably features a SLA service level assurance manager which handles the determination and maintenance of service levels

Outgoing message logic is the entry point for messages which are to be sent from the agent. SLA manager preferably prioritizes message handling according to a priority model for determining which messages should be sent first. The message model is preferably based on the actual message priority and the sending service priority more preferably through the use of a priority function for example the message and sending service priorities could optionally be multiplied . Message handling may optionally include validation template matching message transformation etc.

A flow manager preferably manages the flow of message handling itself. Flow manager preferably features a plurality of processing modules termed herein processors each of which is responsible for an atomic action. Optionally each core function has a separate associated processor such as a validation processor a template matching processor and a transformation processor not shown each of which may optionally be located at the respective manager but which are preferably called by flow manager more preferably sequentially to handle a particular message. Each such processor is preferably registered at flow manager . A processing flow may optionally include the following stages 

Therefore the message is preferably first validated after which the message is run through the transformation processor followed by the template matcher.

Messages are preferably received and processed by message consumer . Message consumer receives client messages from protocol layer and preferably acts upon them by invoking core logic . As previously described message consumer also contains a preferably separate SLA manager also for prioritizing message handling for example message acceptance according to some priority model as previously described. A similar priority function may also optionally be used.

A distributed queue manager is optionally and preferably provided for managing messages and or information optionally including portions of messages that are distributed between a plurality of agents . Distributed queue manager preferably assists with such issues as the order in which a plurality of messages is sent. Background art publish subscribe message systems rely upon a central message broker which can therefore perform the necessary synchronization tasks between messages sent from different parts of the system at different types. By contrast the present invention is fully distributed such that no central mechanism such as a broker exists to perform such synchronization. Instead preferably distributed queue manager performs such synchronization for example by enabling higher priority messages to move forward in the queue before lower priority messages. Queue management may also optionally include managing the order of persistent vs. non persistent messages and also preferably ensuring that the order in which messages are sent is not the only controlling factor for the queue order.

Distributed queue manager preferably also handles the queue to maintain order of messages sent by a particular agent such that for example a plurality of messages sent by a particular agent is preferably read in the order of being sent.

Distributed queue manager at each receiving agent optionally manages a separate queue in the name of each sending agent each such local queue then preferably maintains an internal order of outgoing messages. Receiving agent R then preferably retrieves messages in the order sent within a local queue. A simple de queuing algorithm may therefore optionally be implemented as a round robin algorithm in which each queue is traversed in turn.

Optionally and more preferably there is a plurality of different messages including but not limited to client messages management messages and control messages. Client messages preferably pass through the agent to the client . These messages are handled through agent for example for translation between different protocols TCP vs. HTTP for example in order for inter operability to be present between the clients. Management messages are messages which originate from a human administrator and are preferably used to remotely manipulate the agent. These messages are preferably forwarded to the Coridan Management Component CMC see for handling.

Control messages originate from an application such as another agent in the network not shown the control messages are then preferably passed to a control signal message consumer which preferably receives control messages from the protocol layer and acts upon them by invoking core logic .

Message handling is optionally and preferably further assisted by a timeout monitor which determines when a message is too old to be relevant. When sending a message with an acknowledgment policy the message is preferably stored in a message mapper module . Messages which are stored in message mapper module are preferably either removed from it when a related ACK acknowledgment message is received by the agent normal removal or alternatively when a certain amount of time has passed in which case the message can be thought of as an expired message .

Message mapper module is preferably a persistent map although persistency is optionally configurable. Message mapper module preferably maintains a mapping between a message ID and the actual message. Message mapper module preferably participates in various messages sending processes. For example during the message sending process the agent adds the message to the map. At a later stage when an ACK message arrives the agent uses the correlation ID to remove the persistent message from the map.

The first stage of the sending message flow preferably stores the messages which are about to be processed in the message mapper. Only after the messages are added to message mapper module the agent s flow commences.

Optionally adding a message to message mapper module does not automatically make it persistent. More preferably only messages requiring an acknowledgement ACK are included in message mapper module .

Timeout monitor preferably contains a separate thread which examines the collection of sent messages which have not received any acknowledgment. When timeout monitor locates a message which has not received any acknowledgment it checks the message valid until value. Timeout monitor preferably resends messages which are still valid timeout monitor tries to resend the message as long as the message is valid. When timeout monitor determines that a message is no longer valid the message is removed from message mapper module . The client which created the message is preferably informed of the message expiration.

A message sending listener is optionally and more preferably responsible for handling message sending callbacks which originate from either protocol layer or network layer . Both layers preferably call back message sending listener upon sending the message. Events can optionally range from a successful sending event to an error event . It is the responsibility of message sending listener to inspect the event and act based on the information stored in the event. Successfully sending preferably causes message sending listener to remove the sent message from message mapper module .

Unsuccessfully sending the message may optionally cause message sending listener to resend the message. The decision to resend the message is preferably delegated to a resending manager .

Resending manager preferably decides whether a message should be resent based on one or more criteria including but not limited to 

If a message is to be sent resending manager preferably delays the resending of the message by a configurable amount of time. If the message was sent as a blocking send such that the message is not expected to return until an ACK is received for this message resending manager optionally returns the message. Otherwise preferably an error message is returned.

A world modeler is preferably featured for enabling core logic to be able to determine how to address messages for example in order to determine which agent s should receive a message. World modeler preferably includes information about other agents which are part of the agent s world or domain and to which data needs to be transmitted in the form of messages. A domain is a group of agents with which a particular agent may communicate. As described in greater detail below such information may optionally include the identity of one or more agents which have requested particular information through subscribing to data and or to an event as well as those agent s which are visible to a particular agent for example for sending a multi cast message.

Briefly publishing data and subscribing to such publications are well known for MOM architectures in general as they enable data to be passed without connection specific addressing. For example according to the background art which requires a central message broker unlike the present invention a first component would publish data about a particular topic by sending it to a queue on the central message broker one or more other components in the network would inform the central message broker that they wish to subscribe to such a topic such that the broker would send the subscribing component s the data when received from the publishing component.

The present invention also preferably supplies such publication subscription functionality but without the central message broker. Instead a list of all agents subscribing to particular data which are also within the domain or world of the agent is preferably contained in the map in world modeler . A non limiting example of such a map is as in .

World modeler also enables a central console not shown see to more easily control message transmission between agents without requiring all or even any messages to pass through such a console instead a human administrator is preferably able to determine how groups of agents interact by sending updates of the map for each agent from the central console. World modeler receives this map and uses it to determine interactions with other agents. Optionally and more preferably world modeler may receive information about other agents through a discovery mechanism such that the map is more preferably capable of also being updated through this mechanism and not only through a central console. Most preferably the discovery mechanism features automatic discovery. Discovery preferably includes determining information about other agents that are available for communication with the particular agent more preferably by being in the same domain as well as the characteristics and or capabilities of these other agents. Most preferably discovery also involves determining information published by these agents.

The map contained in world modeler may also optionally include information about one or more applications services connected to each agent as previously described the present invention may optionally be implemented with a service oriented architecture in which application functionality is provided through services such as Web services for example the networking capabilities of each agent and also the identity of one or more adaptors which may also optionally be connected to the agent.

The discovery mechanism which may optionally be used to update this map preferably includes one or more functions which are performed in order for the agent to be able to request information. For example preferably the agent is able to transmit a message which requests the identity of a publisher of particular data. More preferably the data does not need to necessarily be organized by category instead the agent may optionally and more preferably request particular data and or notification of an event more generally without being limited to specific categories. Each such publisher agent which receives the request preferably then responds with a notification message. The requesting agent then preferably adds the information to the map in world modeler .

An alias resolution manager is a mapping module that preferably maps a name to another name. It may optionally be present at more than one component of agent core .

An XML management module preferably handles the tasks related to XML itself. XML management module is for an optional but preferred embodiment of the present invention in which messages are prepared in XML. XML management module preferably features validation manager and template matcher as previously described XML management module more preferably also features a XML parser and a transformation manager .

Validation manager preferably validates any messages the client wishes to send according to a predefined DTD document type definition which supports automatic validation to determine whether a document follows the DTD. In cases of validation failure validation manager preferably acts according to one or more of the following illustrative non limiting rules 

The agent s configuration preferably determines whether validation manager is active for example for always checking messages. The validation information is preferably stored in memory and is more preferably not persistent such that if the agent fails all validation information would need to be rebuilt by the client.

Validation manager is preferably a pluggable module allowing it to be replaced at a later date. The validation process is optionally and preferably determined at least partially according to information and or instructions received from the central control.

Template matcher preferably features at least one template and more preferably a plurality of templates according to which a message may be parsed. The message is optionally and preferably in XML such that the template is optionally and preferably constructed for parsing XML. These XML templates may range from full XML DTDs to specific XPath filters. XPath is an XML parser which is able to understand and parse XML for example optionally according to the hierarchy of the XML document as well as optionally according to a search key. A message may come from a particular client which may have subscribed to the message data or content as described in greater detail below. Xpath is optionally and preferably used in order to match messages to clients.

Xpath is a non XML language that may optionally be used to identify particular parts of XML documents. Xpath permits expressions to be written that refer to the document s first person element as a non limiting example of an element the seventh child element of the third person element the ID attribute as a non limiting example of an attribute of the first person element whose contents are the string Fred Jones as a non limiting example all xml stylesheet processing instructions in the document s prolog and so forth. Xpath indicates nodes by position relative position type content and several other criteria. Xpath expressions can also represent numbers strings or Booleans.

Template matcher is preferably used to map templates such as XML templates to clients. When a client publishes a XML message or other type of message XML parser parses the message and uses template matcher to locate any clients which were subscribed to a message having the particular template. The sending agent then sends the message only to these clients.

The receiving agent preferably performs the following process for message filtering. For example if an agent was subscribed to receive all documents having a particular key value e.g. a particular element or elements having particular value s the filtering process may optionally be performed to determine whether a message has an element with a particular value.

According to preferred embodiments of the present invention if a failure occurs when sending a message to an agent template matcher preferably removes dead non responding agents from the map stored in world modeler according to the topic and or agent durability. Subscribers subscribing agents to durable topics are preferably not removed from template matcher even if the sending agent knows that the receiving agent is dead. If on the other hand the subscriber of the topic is not a durable subscriber the sending agent preferably removes the dead receiving agent from template matcher . Optionally and preferably template matcher is not persistent.

The template matcher entries are preferably removed from the map according to their TTL time to live .

According to other preferred embodiments of the present invention during the agent initialization stage the agent preferably sends control messages to other agents in the agent s domain. These control messages preferably contain one or more templates more preferably XML templates for which the agent expects to receive message s . This information is then stored in template matcher of each receiving agent. Template matcher is optionally only used for publication subscription processes.

Transformation manager is preferably able to transform one type of XML message into another type optionally and more preferably according to XSLT. The central console optionally allows the human administrator to add new XML transformations which enable the XSLT to perform different types of transformations.

A performance housekeeper optionally and preferably monitors various metrics with regard to agent functions. Performance housekeeper also preferably maintains a performance policy which is responsible for calculating the agent s overall metric. These metrics may optionally be used to affect decisions taken by the agent itself or the administrator of the system while using the configuration manager to view these metrics .

Metric measurement is preferably performed by adding new objects which implement the measure interface.

Performance housekeeper is able to detect new measurement objects and activate them. The human administrator is preferably able to use the central console in order to load unload measurement objects. Some illustrative examples of such measurements may include but are not limited to the list in Appendix A.

Message sending listener optionally and preferably informs performance housekeeper about various statistics such as number of failed successful sending attempts.

Other optional components of agent core include but are not limited to a cache and a security manager .

Security is preferably handled also by the infrastructure layer see . Security manager preferably features a security mechanism that may optionally include XACML SSL or other alternatives. One or more different types of key encryption and or authentication mechanisms may also optionally be used.

According to another optional but preferred embodiment of the present invention fa ade features a number of different functions some non limiting illustrative examples of which are listed in Appendix B.

During initialization the agent preferably sends a message telling the world agents belonging to its group that it is the publisher of some message template s . Some of the templates may optionally be predefined these templates are preferably persistent. The agent preferably loads these templates from the persistent store and sends resends if the initialization process is performed after a failure for example them upon initialization.

At initialization the agent preferably sends a subscribe message to other agent s in the world thereby requesting that the publishing agent subscribe the requesting agent to the messages being published by the publisher.

At least during the initialization process and preferably after as well as described in greater detail above the agent is preferably able to subscribe to topics. Subscribing to topics is done by sending a who is the publisher of the topic X message using domain multicast and or broadcast to all the agents in the network. A relevant publisher agent may reply to the agent with a confirmation thus the requesting agent will be able to subscribe to the new topic with the publisher.

This topic discovery flow preferably enables the agent as a side effect to rediscover publishers agents because publishers responses to who is the publisher of the topic X message every publisher agent which the requesting agent does not know will be added to the requesting agent s world map.

If initialization occurs after a failure once the agent recovers from the failure it preferably sends a subscribe message to the world as known to the agent this message preferably causes other agents to update their world map with the new agent if they don t know it already.

The agent can also optionally send a message telling the world that it is the publisher of some message templates.

According to other preferred embodiments of the present invention initialization manager is called from the agent core not shown see which passes two parameters a init file location and a loader object.

The initialization process preferably has a plurality of parts initialization from a init file step and the loader step. Given an init file property file the system preferably loads all the classes listed in the property file keys by invoking the given initialization method values .

A non limiting illustrative example of an init file entry is as follows Remark regarding this entry com.coridan.core.cm.ConfigurationManager initInstanse .

In this example initialization manager calls the initInstanse method of the ConfigurationManager singleton located at configuration center described in greater detail below .

The loader process is preferably performed as follows given a Loader object initialization manager then delegates the next stages of the load to this loader. A simple loader will perform the init process for all the relevant infrastructure elements specific components according to the present invention clients servers . . . will preferably have their own loader that will either inherit from this simple loader or implement a loader interface in order to disable some infrastructure components .

Configuration center preferably is a repository of key and values. Configuration files are preferably held in property files. All common properties are preferably held in the repository file as repository parameters. Configuration center is preferably called upon initialization by the agent core see above for a description and given a component specific configuration file name as parameter e.g. client.param . The component specific configuration file is preferably able to over write and or append to the common configuration.

Configuration center preferably then merges the two files into one property map and a set of methods which are more preferably accessible to a client that needs the configuration data.

Properties can optionally be changed at runtime by the Management Component MC not shown see . Persistency is preferably controlled by configuration center . Objects may optionally be notified of changed properties optionally and preferably by performing the following two processes 

When changes accrue configuration center invokes the refresh method in the objects and they refresh themselves with the new data.

According to preferred embodiments of the present invention each component of the system of the present invention has a management component as for configuration center above. The management center enables the component such as an agent for example to be controlled and or managed from a remote location.

The management center receives the management XML commands passed from the network layer described in greater detail below and invokes the relevant command in its command repository with the XML parameters. The management center replies with an XML response which may be an ACK or a relevant data for that request for example.

The management center preferably examines each added object and if the object implements a well defined naming structure the management center is preferably able to link a XML management command to a method.

According to other preferred embodiments of the present invention the management center has a security mechanism which may optionally be implemented as follows. Each client connecting to the management center has a role. The management center preferably holds the commands in the repository in a way that will enable a client to see and invoke only the methods relevant to that client or to sub roles on the client s role.

Network layer preferably handles low level network operations i.e. creating and accepting sockets and reading and writing message buffers from sockets. It also includes a decision process for finding the least expensive way to send a message to one or more destinations.

Network layer interfaces with protocol layer . When data is available on one of the sockets that network layer manages it reads the incoming message into a message buffer and passes it to protocol layer .

For outgoing messages network layer expects to receive a list of destinations agents for which the message is intended and a message buffer. This buffer is a byte array containing an already serialized message.

One important role of network layer is the transport decision process. A transport is the combination of a network socket and a transport protocol. The protocol provides services such as reliability message integrity etc. Transports can be unicast meaning a message sent will be received by one agent only example a TCP socket although this may optionally be performed multiple times for multiple agents or multicast meaning a message will be received by more than one agent and possibly all agents example a multicast socket with LRMP lightweight reliable multicast protocol as a transport protocol .

Each transport has two costs associated with it a setup cost and a message cost. The former quantifies how expensive it is to setup this transport creating a socket initializing the protocol stack sending any initialization messages defined by the transport protocol. The latter describes the cost of sending a message via the transport. A message cost can be a constant or a function. For example when sending a message through a multicast transport each recipient which is not a destination would add to the total message cost. A cost function describing this desired behavior can be defined.

An outgoing message includes one or more destinations. It possible for an agent to have several transports leading to it. The responsibility of network layer is to find for each outgoing message the optimal destination s to be used cost wise. This defines the transport decision process.

Another aspect of the transport process is to determine the cost at least partially according to the route for the message for example according to routing tables. Also one aspect of the transport process is to determine whether a particular connection that is open to another agent should be closed although this decision preferably also considers the cost of reopening the connection should this be necessary and more preferably also considers the likelihood of reopening such a connection.

Another parameter of a transport is whether or not it is encrypted. Protocol layer can request that a message be sent using encrypted transports if available. In this case the encryption capabilities of a transport preferably take precedence over its cost in the transport decision process.

Timer preferably is responsible for keeping the current time updated. Different modules in the agent are preferably able to query the system s current time by querying timer .

Timer preferably is created to alleviate system resources consumed by each call to System.getCurrentTimemills . The time resolution of timer preferably is 1 second meaning that the internal time of the timer is updated every second.

Infrastructure layer preferably also includes a management component for handling communication between the console not shown see and the agent.

Network layer is preferably able to handle message transmission and reception from a network such that the agent does not need to be aware of the type of network and or network protocols being used. Network layer also preferably determines how to send a message and also preferably determines and or selects a mechanism for sending a particular message such as by uni cast multi cast or reliable multi cast broadcast TCP UDP and or reliable UDP. The mechanism is more preferably selected according to at least one of a cost function availability of the mechanism and scale of the mechanism relative to the data to be transmitted optionally the cost mechanism could include the latter two factors in its function .

Network layer preferably includes a number of data structures. For example one such network structure is preferably a cost policy . This is a global object specifying the cost of using the various transports available in the system. The policy specifies the setup cost and the message cost for each transport type available. The setup cost describes how expensive it is to setup a connection and the message cost describes the cost of sending a message using a connection.

Network layer also preferably has one or more Inputs and Outputs . For example inputs may optionally include but are not limited to one or more of the following Incoming message through a network connection Outgoing message through the protocol layer.

Inputs are also preferably subject to configuration as previously described for example according to a cost policy max number of connections connection age timeout and so forth.

Outputs may optionally include but are not limited to one or more of the following for example Incoming message to the protocol layer Outgoing message to the network connections Error Callback when an outgoing message sending fails this is used to report the problem to the protocol layer.

Network layer also preferably includes a connection manager which is responsible for creating new connections and sending messages through these connections. Connection manager receives a buffer containing the message and a list of addresses to which to send the message. If an address does not have a connection associated with it yet this connection is created at this stage.

The layer can optionally be configured to maintain a maximum number of connections. It also preferably removes connections sockets if they were not used for a period of time which is more preferably determinable. If the decision is based on the number of connections the unused connection s are preferably removed using the LRU Least Recently Used algorithm such that the connection or connections being least recently used or accessed by network layer are removed.

If the manager encounters a problem when sending a message it optionally and preferably uses a callback supplied by protocol layer see to report the problem.

The network message handler preferably listens to all available connections. When a message arrives it is read into a buffer and passed to protocol layer see .

Transport director is preferably activated by protocol layer . It receives a buffer and a list of addresses. The responsibility of transport director is determining the cheapest way to send this message to the requested destinations according to the costs defined for each transport.

Transport director preferably locates the cheapest route to send the message. The decisions taken by transport director are preferably managed by a pluggable dispatching policy .

Transport director preferably has knowledge of the transmission channels that are available to the agent according to the dispatching policy including but not limited to multicast broadcast reliable multicast UDP RUDP TCP HTTP Tunnel or SSL. Transport director is preferably able to understand the message recipients and their respective capabilities optionally also according to security considerations and to make an informed decision on how to send the message to them.

For example transport director looks at the targets and sees if all of them can receive multicast. If n 2 can receive multicast then transport director sends the message using multicast to the n 2 receivers and sends the message by using TCP or some other protocol to the receiver s which could not handle the multicast message.

The agent s capabilities include which services are connected to the agent and which adaptors are attached to it. The agent s information about other agents includes other agents networking capabilities transport capabilities . During the connection establishment process between two agents the connecting agents will make sure their respective information about the other agents transport capabilities is complete. They will do so by swapping UPDATE TRANSPORT CAPABILITES messages.

Central management console preferably forms the central point of management in the network according to the present invention which preferably enables human administrator s to view the network and invoke commands on each component thereof.

Central management console is preferably operated by a Web server in order to be able to provide a user interface in the form of Web pages more preferably central management console also additionally or alternatively supports other interfaces like JMX .

Central management console is preferably able to connect to each management component as shown for example with regard to .

Central management console preferably features a security mechanism. Users human administrators are preferably assigned a role upon first interacting with central management console . Some users may optionally have the same role but each user preferably has only one role.

Some roles can optionally be permitted to create other user identities and attach a role to them for example as console administrators. The user identities and their roles are preferably saved to a persistent storage preferably LDAP lightweight directory access protocol server or database or file . Central management console preferably does not permit a user to access commands that are not related to the user s role.

Central management console preferably also features a central management component for communicating with management component at each agent see .

One embodiment of the present invention is a method for distributing a message among a plurality of agents in a fully distributed system. Such a method can comprise determining an address for the message by an agent selecting a path for transmitting the message according to the address by the agent and sending the message according to said path directly by said agent .

In one embodiment of the present invention the address for distributing a message is determined at least partially according to a content of the message wherein the agent is capable of parsing the message to determine the content of the message. In one example the message comprises XML such that the message can be parsed according to an analysis of at least one XML element. In another case the message comprises at least one portion component or element for being parsed by the agent. In yet another example the message has a protocol comprising at least one of JMS HTTP TCP messages RMI remote method invocation or any other suitable type of message protocol.

In one embodiment of the present invention a second agent subscribes to said content such that the address is determined according to subscribing to the content by the second agent .

In another embodiment of the present invention the selecting of the path further comprises selecting a transport mechanism. In one example the transport mechanism can be selected from the group consisting of a persistent connection and a temporary transmission. In another example the connection is selected from the group consisting of reliable UDP RUDP UDP and TCP. In yet another example the transmission is selected from the group consisting of unicast broadcast multicast tunneling and reliable multicast.

In another embodiment of the present invention the transport mechanism is at least partially selected according to at least one of a cost function availability of the connection or scale of the connection and or transmission s .

In another embodiment of the present invention the method for distributing a message among a plurality of agents can also includes providing a smart publish subscribe function for the message by said agent providing a distributed queue and queuing messages from a plurality of agents in said distributed queue .

In another embodiment of the present invention each agent contributes to the distributed queue while each agent also features a local queue corresponding to the distributed queue.

In another embodiment of the present invention the method for distributing a message among a plurality of agents can also includes performing automatic discovery by the agent for determining at least one characteristic of at least one other agent. In one example the at least one other characteristic comprises at least one of a capability information being published and information being subscribed. In another example the automatic discovery comprises receiving a map by the agent.

Next the flow manager performs message handling such as calling the validation manager to validate the message. The flow manager then calls the XML parser which parses the message in an exchange with the outgoing message logic. Next the flow manager calls the transformation manager. The transformation manager transforms the message after which the flow manager instructs the protocol network layer to send the message. This layer sends an ACK when the message is sent after which the message mapper is instructed to remove the message from the map.

The message mapper then receives an un map command to remove the message from the map. The core logic is instructed to manage the message for example for analysis parsing and so forth. The message is then passed through the fa ade to Client B which returns an ACK message. The message consumer then returns an ACK message to the protocol network layer.

In each agent has an associated client clients and agents are differentiated by a letter for the purpose of clarity only. Agent B is associated with client B and sends a message to Agent D and Agent E . This message may optionally be transmitted by unicast if this method is the most cost effective for example if the message is only to be sent to one or two agents . Alternatively if this message is one of many messages to be sent to either or both of Agent D and Agent E there may be a TCP or reliable UDP connection between Agent B and Agent D and or Agent E . The connection between Agent B and each of Agent D and Agent E may optionally be the same or different depending upon the communication requirements.

Another possibility is that if Agent B needs to send the message to a plurality of agents preferably over a threshold number then Agent B may optionally use a multicast method such as a reliable multicast protocol LRMP . These multicast methods may optionally enable messages to be sent across subnets for example according to domains or associations of agents rather than according to network structure.

Both the proxy agent and the relay agent do not act as normal agents rather they serve other agents. Both the proxy agent and the relay agent pass keep or process messages for other agents in the network agents that for some reason can not perform or choose not to perform these tasks.

The agent s world perspective its ability to maintain a different view of the world is one of the main concepts which allow agents to have capabilities such as relying and proxying.

Achieving both perspectives is preferably done by manipulating the mapping each agent maintains thereby making agents believe that other agents resides in different locations in the network.

Agents C and D located on the Internet are unable to reach agents A and B as both agents are located in the MZ Militarized Zone in this scenario the Relay agent is able to bypass the firewall as it is located in the DMZ De Militarized Zone .

As stated above there are two kinds of perspectives a world perspective and an agent perspective. When thinking about the relay agent and the sample presented above one can see that Agents C and D are not able to establish connection with agents A and B as a firewall separates them both .

In order to solve this problem the network administrator optionally maps agents A and B to the relay Agent.

Both agents C D maintain the same view of agents sees agents A and B as they are accessing the internet from inside the MZ .

The relay agent s perspective perceives the world exactly the way is really is it knows where agent A B C and D are located and how to access them.

The proxy agent acts as the delegate agent for some service s . The proxy may be responsible for the parsing of messages or any other activities which the administrator has chosen to assign to the agent.

As shown in Agent W exposes two services Service and service . The network administrator may decide to allow agent W to continue exposing service and assign service to the proxy agent thereby sharing the load of agent W.

Thus agents are able to see some of the services agent W originally exposed as mapped to agent W and some as mapped to the proxy agent.

The proxy agent perspective will reflect the knowledge that if a request is made to service is should handle to work by itself although it may need to consult with agent W .

Although the invention has been described in conjunction with specific embodiments thereof it is evident that many alternatives modifications and variations will be apparent to those skilled in the art. Accordingly it is intended to embrace all such alternatives modifications and variations that fall within the spirit and broad scope of the appended claims. All publications patents and patent applications mentioned in this specification are herein incorporated in their entirety by reference into the specification to the same extent as if each individual publication patent and patent application was specifically and individually indicated to be incorporated herein by reference. In addition citation or identification of any reference in this application shall not be construed as an admission that such reference is available as prior art to the present invention.

One embodiment includes a computer program product which is a storage medium media having instructions stored thereon in which can be used to program a computer to perform any of the features present herein. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs micro drive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs flash memory of media or device suitable for storing instructions and or data stored on any one of the computer readable medium media the present invention can include software for controlling both the hardware of the general purpose specialized computer or microprocessor and for enabling the computer or microprocessor to interact with a human user or other mechanism utilizing the results of the present invention. Such software may include but is not limited to device drivers operating systems execution environments containers and user applications.

Embodiments of the present invention can include providing code for implementing processes of the present invention. The providing can include providing code to a user in any manner. For example the providing can include transmitting digital signals containing the code to a user providing the code on a physical media to a user or any other method of making the code available.

Embodiments of the present invention can include a computer implemented method for transmitting code which can be executed at a computer to perform any of the processes of embodiments of the present invention. The transmitting can include transfer through any portion of a network such as the Internet through wires the atmosphere or space or any other type of transmission. The transmitting can include initiating a transmission of code or causing the code to pass into any region or country from another region or country. For example transmitting includes causing the transfer of code through a portion of a network as a result of previously addressing and sending data including the code to a user. A transmission to a user can include any transmission received by the user in any region or country regardless of the location from which the transmission is sent.

Embodiments of the present invention can include a signal containing code which can be executed at a computer to perform any of the processes of embodiments of the present invention. The signal can be transmitted through a network such as the Internet through wires the atmosphere or space or any other type of transmission. The entire signal need not be in transit at the same time. The signal can extend in time over the period of its transfer. The signal is not to be considered as a snapshot of what is currently in transit.

The forgoing description of preferred embodiments of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Many modifications and variations will be apparent to one of ordinary skill in the relevant arts. For example steps preformed in the embodiments of the invention disclosed can be performed in alternate orders certain steps can be omitted and additional steps can be added. The embodiments where chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular used contemplated. It is intended that the scope of the invention be defined by the claims and their equivalents.

Gets the default length of time in milliseconds from its dispatch time that a message should be retained by the message system

Sets the default length of time in milliseconds from its dispatch time that a produced message should be retained by the message system

Receives the next message produced for this agent. The client is blocked for the duration of the method call

Sets a Message Listener message listeners are called back by the agent s logic upon receiving a message

Removes a Message Listener from the agent logic. This can be thought of as a unsubscribing to some Template topic 

