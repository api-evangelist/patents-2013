---

title: Message handling multiplexer
abstract: A method and apparatus for processing message is described. In one embodiment, an application programming interface is configured for receiving and sending messages. A multiplexer receives messages from different servers. A service name is coupled to each message with the corresponding destination service. A single shared channel is formed. The messages are processed over the single shared channel.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09548949&OS=09548949&RS=09548949
owner: Red Hat, Inc.
number: 09548949
owner_city: Raleigh
owner_country: US
publication_date: 20131217
---
This application is a continuation of U.S. patent application Ser. No. 11 807 624 filed May 29 2007 which is incorporated by reference in its entirety.

Embodiments of the present invention relate to group communication and more specifically to parallel processing of messages.

Group communication protocol designed for multicast communication may be used to communicate messages between endpoints forming a group. Communication endpoints can be processes or objects or any entity that can send and receive messages to from a group.

However messages from different senders are conventionally processed in a First In First Out FIFO order in a single queue for incoming messages by one thread. The messages are processed sequentially in the order they are received. A bottleneck may thus be formed since every message has to wait for its turn to be processed accordingly.

Described herein is a method and apparatus for processing messages using a multiplexer. The multiplexer may receive messages or services from several senders. A service name is coupled to each message with the corresponding destination service. A single shared channel is formed to process the messages.

In the following description numerous details are set forth. It will be apparent however to one skilled in the art that the present invention may be practiced without these specific details. In some instances well known structures and devices are shown in block diagram form rather than in detail in order to avoid obscuring the present invention.

Some portions of the detailed descriptions which follow are presented in terms of algorithms and symbolic representations of operations on data bits within a computer memory. These algorithmic descriptions and representations are the means used by those skilled in the data processing arts to most effectively convey the substance of their work to others skilled in the art. An algorithm is here and generally conceived to be a self consistent sequence of steps leading to a desired result. The steps are those requiring physical manipulations of physical quantities. Usually though not necessarily these quantities take the form of electrical or magnetic signals capable of being stored transferred combined compared and otherwise manipulated. It has proven convenient at times principally for reasons of common usage to refer to these signals as bits values elements symbols characters terms numbers or the like.

It should be borne in mind however that all of these and similar terms are to be associated with the appropriate physical quantities and are merely convenient labels applied to these quantities. Unless specifically stated otherwise as apparent from the following discussion it is appreciated that throughout the description discussions utilizing terms such as processing or computing or calculating or determining or displaying or the like refer to the action and processes of a computer system or similar electronic computing device that manipulates and transforms data represented as physical electronic quantities within the computer system s registers and memories into other data similarly represented as physical quantities within the computer system memories or registers or other such information storage transmission or display devices.

The present invention also relates to apparatus for performing the operations herein. This apparatus may be specially constructed for the required purposes or it may comprise a general purpose computer selectively activated or reconfigured by a computer program stored in the computer. Such a computer program may be stored in a computer readable storage medium such as but is not limited to any type of disk including floppy disks optical disks CD ROMs and magnetic optical disks read only memories ROMs random access memories RAMs EPROMs EEPROMs magnetic or optical cards or any type of media suitable for storing electronic instructions and each coupled to a computer system bus.

The algorithms and displays presented herein are not inherently related to any particular computer or other apparatus. Various general purpose systems may be used with programs in accordance with the teachings herein or it may prove convenient to construct more specialized apparatus to perform the required method steps. The required structure for a variety of these systems will appear from the description below. In addition the present invention is not described with reference to any particular programming language. It will be appreciated that a variety of programming languages may be used to implement the teachings of the invention as described herein.

A machine accessible storage medium includes any mechanism for storing or transmitting information in a form readable by a machine e.g. a computer . For example a machine accessible storage medium includes read only memory ROM random access memory RAM magnetic disk storage media optical storage media flash memory devices electrical optical acoustical or other form of propagated signals e.g. carrier waves infrared signals digital signals etc. etc.

JGroups is toolkit for reliable group communication. Processes can join a group send messages to all members or single members and receive messages from members in the group. The system keeps track of the members in every group and notifies group members when a new member joins or an existing member leaves or crashes. A group is identified by its name. Groups do not have to be created explicitly when a process joins a non existing group that group will be created automatically. Member processes of a group can be located on the same host within the same LAN or across a WAN. A member can be part of multiple groups.

The group communication architecture may comprise three parts 1 a channel API used by application programmers to build reliable group communication applications 2 building blocks which are layered on top of channel and provide a higher abstraction level and 3 a protocol stack which implements the properties specified for a given channel.

Channel is connected to protocol stack . Whenever an application sends a message channel passes it on to protocol stack comprising several protocols . The topmost protocol processes the message and the passes it on to the protocol below it. Thus the message is handed from protocol to protocol until the bottom protocol puts it on the network . The same happens in the reverse direction the bottom transport protocol listens for messages on network . When a message is received it will be handed up protocol stack until it reaches channel . Channel stores the message in a queue until application consumes it.

When an application connects to a channel protocol stack will be started and when it disconnects protocol stack will be stopped. When the channel is closed the stack will be destroyed releasing its resources.

To join a group and send messages a process has to create a channel and connect to it using the group name all channels with the same name form a group . The channel is the handle to the group. While connected a member may send and receive messages to from all other group members. The client leaves a group by disconnecting from the channel. A channel can be reused clients can connect to it again after having disconnected. However a channel may allow only one client to be connected at a time. If multiple groups are to be joined multiple channels can be created and connected to. A client signals that it no longer wants to use a channel by closing it. After this operation the channel may not be used any longer.

Each channel has a unique address. Channels always know who the other members are in the same group a list of member addresses can be retrieved from any channel. This list is called a view. A process can select an address from this list and send a unicast message to it also to itself or it may send a multicast message to all members of the current view. Whenever a process joins or leaves a group or when a crashed process has been detected a new view is sent to all remaining group members. When a member process is suspected of having crashed a suspicion message is received by all non faulty members. Thus channels receive regular messages view messages and suspicion messages. A client may choose to turn reception of views and suspicions on off on a channel basis.

Channels may be similar to BSD sockets messages are stored in a channel until a client removes the next one pull principle . When no message is currently available a client is blocked until the next available message has been received.

A channel may be implemented over a number of alternatives for group transport. Therefore a channel is an abstract class and concrete implementations are derived from it e.g. a channel implementation using its own protocol stack or others using existing group transports such as Jchannel and EnsChannel. Applications only deal with the abstract channel class and the actual implementation can be chosen at startup time.

The properties for a channel may be specified in a colon delimited string format. When creating a channel JChannel a protocol stack will be created according to these properties. All messages will pass through this stack ensuring the quality of service specified by the properties string for a given channel.

Channels are simple and primitive. They offer the bare functionality of group communication and have on purpose been designed after the simple model of BSD sockets which are widely used and well understood. The reason is that an application can make use of just this small subset of JGroups without having to include a whole set of sophisticated classes that it may not even need. Also a somewhat minimalistic interface is simple to understand a client needs to know about 12 methods to be able to create and use a channel and oftentimes will only use 3 4 methods frequently .

Channels provide asynchronous message sending reception somewhat similar to UDP. A message sent is essentially put on the network and the send method will return immediately. Conceptual requests or responses to previous requests are received in undefined order and the application has to take care of matching responses with requests.

Also an application has to actively retrieve messages from a channel pull style it is not notified when a message has been received. Note that pull style message reception often needs another thread of execution or some form of event loop in which a channel is periodically polled for messages.

JGroups offers building blocks that provide more sophisticated APIs on top of a Channel. Building blocks either create and use channels internally or require an existing channel to be specified when creating a building block. Applications communicate directly with the building block rather than the channel. Building blocks are intended to save the application programmer from having to write tedious and recurring code e.g. request response correlation.

As discussed above JGroups provides two channel implementations an Ensemble based channel and its own channel based on a Java protocol stack. The latter is a protocol stack containing a number of protocol layers in a bidirectional list. illustrates protocol stack with the following procotols CAUSAL GMS MERGE FRAG UDP .

All messages sent and received over the channel have to pass through the protocol stack. Every layer may modify reorder pass or drop a message or add a header to a message. A fragmentation layer might break up a message into several smaller messages adding a header with an id to each fragment and re assemble the fragments on the receiver s side.

The composition of the protocol stack i.e. its layers is determined by the creator of the channel a property string defines the layers to be used and the parameters for each layer . This string might be interpreted differently by each channel implementation in JChannel it is used to create the stack depending on the protocol names given in the property.

Knowledge about the protocol stack is not necessary when only using channels in an application. However when an application wishes to ignore the default properties for a protocol stack and configure their own stack then knowledge about what the individual layers are supposed to do is needed. Although it is syntactically possible to stack any layer on top of each other they all have the same interface this wouldn t make sense semantically in most cases.

Data is sent between members in the form of messages. A message can be sent by a member to a single member or to all members of the group of which the channel is an endpoint. An example of a structure of a message is illustrated in .

A list of headers can be attached to a message. Anything that should not be in the payload can be attached to message as a header. Methods putHeader getHeader and removeHeader of message can be used to manipulate headers .

The destination address may include the address of the receiver. If null the message will be sent to all current group members.

The source address may include the address of a sender. It can be left null and will be filled in by the transport protocol e.g. UDP before the message is put on the network .

The payload may include the actual data as a byte buffer . The message class contains convenience methods to set a serializable object and to retrieve it again using serialization to convert the object to from a byte buffer.

The message may be similar to an IP packet and consists of the payload a byte buffer and the addresses of the sender and receiver as addresses . Any message put on the network can be routed to its destination receiver address and replies can be returned to the sender s address.

A message usually does not need to fill in the sender s address when sending a message this is done automatically by the protocol stack before a message is put on the network. However there may be cases when the sender of a message wants to give an address different from its own so that for example a response should be returned to some other member.

The destination address receiver can be an Address denoting the address of a member determined e.g. from a message received previously or it can be null which means that the message will be sent to all members of the group. A typical multicast message sending string Hello to all members would look like this 

A state transition diagram for the major states a channel can assume are shown in . In order to join a group and send messages a process has to create a channel. A channel is like a socket. When a client connects to a channel it gives the name of the group it would like to join. Thus a channel is in its connected state always associated with a particular group. The protocol stack takes care that channels with the same group name find each other whenever a client connects to a channel given group name G then it tries to find existing channels with the same name and joins them resulting in a new view being installed which contains the new member . If no members exist a new group will be created.

When a channel is first created at it is in the unconnected state . An attempt to perform certain operations which are only valid in the connected state e.g. send receive messages will result in an exception. After a successful connection by a client it moves to the connected state . Now channels will receive messages views and suspicions from other members and may send messages to other members or to the group. Getting the local address of a channel is guaranteed to be a valid operation in this state see below . When the channel is disconnected it moves back to the unconnected state . Both a connected and unconnected channel may be closed which makes the channel unusable for further operations. Any attempt to do so will result in an exception. When a channel is closed directly from a connected state it will first be disconnected and then closed.

The architecture of one embodiment of a concurrent stack is shown in . As previously discussed channel communicate with transport protocol to a network . However transport protocol may include the following protocols TP with subclasses UDP TCP and TCP NIO. Therefore to configure the concurrent stack the user has to modify the config for e.g. UDP in the XML file.

Concurrent stack consists of two thread pools an out of band OOB thread pool and a regular thread pool . Packets are received from Multicast receiver Unicast receiver or a Connection Table TCP TCP NIO . Packets marked as OOB with Message.setFlag Message.OOB are dispatched to the OOB thread pool and all other packets are dispatched to the regular thread pool .

When a thread pool is disabled then the thread of the caller e.g. multicast or unicast receiver threads or the ConnectionTable is used to send the message up the stack and into the application. Otherwise the packet will be processed by a thread from the thread pool which sends the message up the stack. When all current threads are busy another thread might be created up to the maximum number of threads defined. Alternatively the packet might get queued up until a thread becomes available.

The point of using a thread pool is that the receiver threads should only receive the packets and forward them to the thread pools for processing because unmarshalling and processing is slower than simply receiving the message and can benefit from parallelization.

Previously all messages received were processed by a single thread even if the messages were sent by different senders. For instance if sender A sent messages 1 2 and 3 and B sent message 34 and 45 and if A s messages were all received first then B s messages 34 and 35 could only be processed after messages 1 3 from A were processed.

Now messages from different senders can be processed in parallel e.g. messages 1 2 and 3 from A can be processed by one thread from the thread pool and messages 34 and 35 from B can be processed on a different thread.

As a result a speedup of almost N for a cluster of N if every node is sending messages may be obtained. The thread pool may be configured to have at least N threads.

The exemplary computer system includes a processing device a main memory e.g. read only memory ROM flash memory dynamic random access memory DRAM such as synchronous DRAM SDRAM or Rambus DRAM RDRAM etc. a static memory e.g. flash memory static random access memory SRAM etc. and a data storage device which communicate with each other via a bus .

Processing device represents one or more general purpose processing devices such as a microprocessor central processing unit or the like. More particularly the processing device may be complex instruction set computing CISC microprocessor reduced instruction set computing RISC microprocessor very long instruction word VLIW microprocessor or processor implementing other instruction sets or processors implementing a combination of instruction sets. Processing device may also be one or more special purpose processing devices such as an application specific integrated circuit ASIC a field programmable gate array FPGA a digital signal processor DSP network processor or the like. The processing device is configured to execute the processing logic for performing the operations and steps discussed herein.

The computer system may further include a network interface device . The computer system also may include a video display unit e.g. a liquid crystal display LCD or a cathode ray tube CRT an alphanumeric input device e.g. a keyboard a cursor control device e.g. a mouse and a signal generation device e.g. a speaker .

The data storage device may include a machine accessible storage medium on which is stored one or more sets of instructions e.g. software embodying any one or more of the methodologies or functions described herein. The software may also reside completely or at least partially within the main memory and or within the processing device during execution thereof by the computer system the main memory and the processing device also constituting machine accessible storage media. The software may further be transmitted or received over a network via the network interface device .

The machine accessible storage medium may also be used to JGroup and concurrent stack configurations . JGroup and concurrent stack configurations may also be stored in other sections of computer system such as static memory .

While the machine accessible storage medium is shown in an exemplary embodiment to be a single medium the term machine accessible storage medium should be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term machine accessible storage medium shall also be taken to include any medium that is capable of storing encoding or carrying a set of instructions for execution by the machine and that cause the machine to perform any one or more of the methodologies of the present invention. The term machine accessible storage medium shall accordingly be taken to include but not be limited to solid state memories optical and magnetic media and carrier wave signals.

Several JGroups channels may be formed one for each application e.g. JBossCache ClusterPartition etc . A multiplexer may combine all stacks with the same configuration into one and have multiple services on top of that same channel.

To do this the multiplexer may include multiplexing and demultiplexing functionality ie. each service will have to have a unique service ID a string and when sending a message the message has to be tagged with that ID. When receiving a message it will be dispatched to the right destination service based on the ID attached to the message. Special handling for VIEW and SUSPECT messages may be required those need to be dispatched to all services. State transfer also needs to be handled specially here we probably have to use thread locals or change the API TBD .

When deployed into JBoss the Multiplexer will be exposed as an MBean and all services that depend on it will be deployed with dependency injection on the Multiplexer. The old configuration will still be supported.

The config of the Multiplexer is done via a config file which lists a number of stacks each keyed by a name e.g. udp tcp tcp nio etc. An app is configured with the name of a stack e.g. udp and a reference to the Multiplexer MBean. It will get a proxy channel through which all of its communication will take place. The proxy channel MuxChannel will mux demux messages to the real JGroups channel.

The Multiplexer is actually a JChannelFactory which is configured with a reference to an XML configuration file and has a few additional methods to get a Channel. The channel returned is actually an instance of MuxChannel which transparently forwards all invocations to the underlying JChannel and performs multiplexing and demultiplexing. Multiple MuxChannels can share the same underlying JChannel and each message sent by a service over the MuxChannel will add the services s ID to the message as a header . That ID is then used to demultiplex the message to the correct MuxChannel when received.

public Channel createMultiplexerChannel String stack name String id boolean register for state transfer String substate id throws Exception 

The id parameter is the service ID and has to be unique for all services sitting on the same channel. If an ID is used more than once when trying to call createMultiplexerChannel an exception will be thrown.

The stack name parameter is a reference to a stack for example defined in stacks.xml. A shortened version of stacks.xml is shown below 

This file defines 4 configurations fc fast minimalthreads sequencer tcp and discovery. The first service to call JChannelFactory.createMultiplexerChannel with a stack name of tcp will create the JChannel with the tcp configuration all subsequent method calls for the same stack name tcp will simply get a MuxChannel which has a reference to the same underlying JChannel. When a service closes a MuxChannel the underlying JChannel will only be closed when there are no more MuxChannels referring to it.

The call sequence is indeterministic unless all dependent beans are defined in the same XML file which is unrealistic. We re looking into using a barrier service to provide the guarantee that all create methods are called before all start methods.

When multiple services are sharing a JChannel and each of the services requires state transfer at a different time then we need FLUSH. FLUSH is also called the stop the world model and essentially stops everyone in a group from sending messages until the state has been transferred and then everyone can resume again.

The 2.3 release of JGroups will not have the FLUSH protocol integrated so state transfer for the Multiplexer might be incorrect. 2.4 will have FLUSH so that situation will be corrected. The main reason for putting Multiplexing into 2.3 is that people can start programming against the API and then use it when FLUSH is available.

When multiple services share one JChannel then we have to run the FLUSH protocol for every service which requires state so if we have services A B C D and E running on top of a JChannel J and B C and E require state then the FLUSH protocol has to be run 3 times which slows down startup e.g. of JBoss.

To remedy this we can batch state transfers so that we suspend everyone from sending messages then fetch the states for B C and E at once and then resume everyone. Thus the FLUSH protocol has to be run only once.

To do this a service has to register with the JChannelFactory when creating the MuxChannel and know that getState will be a no op until the last registered application has called getState . This works as follows 

The example above shows that 2 services c1 and c2 share a common JChannel because they use the same stack name STACK NAME . It also shows that only the second getState invocation will actually transfer the 2 states for c1 and c2 .

When we have multiple service running on the same channel then some services might get redeployed or stopped independently from the other services. So we might have a situation where we have services S1 S2 and S3 running on host H1 but on host H2 only services S2 and S3 are running.

So here we host H1 running services S1 S2 and S3 whereas H2 is only running S2 and S3. S1 might be in the process of being redeployed on H2 or is simply not running.

A service view is essentially a list of nodes of a cluster on which a given service S is currently running. Service views are always subsets of cluster views. Here s a reason we need service views consider the example above. Let s say service S1 on H1 wants to make a cluster wide method invocation on all instances of S1 running on any host. Now S1 is only running on H1 therefore we have to make the invocation only on S1. However if we took the cluster view rather than the service view the invocation would be across H1 and H2 and we d be waiting for a response from the non existent service S1 on H2 forever.

So by default calling MuxChannel.getView will return the service view rather than the cluster view. The cluster view can be retrieved calling MuxChannel.getClusterView .

One could deal with this at the MessageDispatcher RequestCorrelator level but a simpler solution is to add asynchronous message handling in Multiplexer. A set of bounded queues is maintained in the Multiplexer one per service. When messages arrive in Multiplexer.up the message is added to the queue and the JGroups up thread returns. Multiplexer maintains a thread pool that reads messages off the queues and passes them up to the mux channel. The use of queues ensures the messages are received in FIFO order at the application level.

It is still possible that one service could block others if it s queue is full. We need to determine exactly how to size the queues i.e. based on number of bytes of queued messages or based on number of messages. An application could then configure the size of its queue such that the queue shouldn t fill under expected load during any normal events e.g. a JBC queue should be configured not to fill during the normal lock acquisition timeout. 

Thus a method and apparatus for processing messages has been described. It is to be understood that the above description is intended to be illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reading and understanding the above description. The scope of the invention should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

