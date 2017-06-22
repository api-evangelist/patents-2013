---

title: Server abstracted messaging system
abstract: A server abstracted messaging system interfaces to networking services such as SMS, UDP and IP, using internally implemented protocols or third-party tools. All connections, disconnections, errors or intricacies in service decoding are abstracted by the messaging system. To interface to an LBS device, the messaging system uses a special language to communicate with that device, leaving the actual translation of the command to the device until the very end, thereby abstracting the communication to the device by any application. All new commands for the LBS device are implemented in the abstracted language.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09332404&OS=09332404&RS=09332404
owner: Spireon, Inc.
number: 09332404
owner_city: Knoxville
owner_country: US
publication_date: 20130315
---
This invention relates to the field of electronic communication of messages across communication networks. More particularly this invention relates to a system for communicating messages over multiple communication networks to and from mobile devices that communicate using various different communication protocols.

Mobile communication devices use various services and protocols for communicating information across wireless communication networks. For example Short Messaging Service SMS is used for text messaging and General Packet Radio Service GPRS is used for data transmission. Computer applications communicate over Internet Protocol IP networks using protocols such as User Datagram Protocol UDP . Web services use Extensible Markup Language XML to represent data structures for communication over the Internet and other IP networks.

Such networking services and protocols are constantly evolving to meet the growing demand for efficient and fast data communications between mobile devices. Location Based Service LBS devices such as automotive tracking and communication devices cargo container monitoring devices and fleet vehicle tracking devices are being introduced that use various different protocols for transmitting status information and receiving commands. Efficiently communicating messages to and from these various LBS devices over wireless communication networks and the Internet has become increasingly challenging.

What is needed therefore is a messaging system that can efficiently interface any LBS device to any networking service using current and yet to be developed protocols.

The above and other needs are met by a server abstracted messaging system. To interface to networking services such as SMS UDP and IP the system uses internally implemented protocols or third party tools. All connections disconnections errors or intricacies in service decoding are abstracted by the messaging system. To interface to an LBS device the messaging system uses a special language to communicate to that device leaving the actual translation of the command to the device until the very end thereby abstracting the communication to the device by any application. All new commands for the LBS device are implemented in the abstracted language.

In preferred embodiments the messaging system is designed to be failsafe by using a separate thread for each messaging event. A thread is an individual process that does not affect the operation of the main messaging system process. As implemented in the abstracted messaging system a thread may fail but the main process remains alive and no other transactions are affected by the failed thread. Thread safe queues store messages until they are ready to be processed.

In a preferred embodiment messages are received by a fast non blocking message receiver that places the messages into the main queue. Message handling is done either by dedicated threads also referred to as processors or by code invoked only upon the receipt of a message also referred to as handlers. A queue manager dispatches messages to the appropriate handlers or processors. Each processor preferably has its own queue of messages awaiting processing so it may asynchronously work its way through the messages in the queue. Message handlers are placed in another queue to await execution by handler runner threads.

The messaging system consists of several instances that are each designed for a specific protocol and a specific LBS device. Each instance is preferably optimized using conditional compilation thereby disabling sections of code and routines that are not needed for proper execution of the current instance.

Preferred embodiments of the messaging system use a Structured Query Language SQL database to capture all messaging system transactions and to communicate between the messaging system and applications.

As shown in Location Based Service LBS devices are in communication with a wireless communication network that is connected to a wide area communication network such as the Internet. LBS devices generally include any wireless device having means to determine its location and report its location or perform some function based on its location. Examples of LBS devices include automotive tracking devices personal tracking devices pet tracking devices cargo container tracking devices fleet vehicle tracking devices emergency locator beacons and security fire alarm monitoring devices. Such devices may determine location coordinates using signals transmitted by Global Positioning System GPS satellites.

Mobile wireless communication devices such as cell phones smart phones and tablet computers are also in communication with the network . These devices may also be capable of determining location and providing services based on location and thus are also considered to be LBS devices.

Multiple service provider computer systems are also connected to the network . These systems which may also be referred to herein as servers provide location based services to end users or consumers. For example one of the service provider computer systems may provide tracking information for mapping the location of fleet vehicles or cargo containers. Another of the service provider computer systems may monitor the location of people or pets or personal automobiles and provide such information on a subscription basis to end users via websites. Yet another of the service provider computer systems may monitor emergency signals transmitted by emergency locator beacon devices via the COSPAS SARSAT emergency rescue satellite system and provide location information to search and rescue authorities. The location based services provided by the service provider computer systems are accessed by consumers using consumer computer systems connected to the communication network .

As shown in various LBS devices communicate over communication networks using various communication protocols such as Short Messaging Service SMS General Packet Radio Service GPRS and Code Division Multiple Access CDMA . Other devices such as security systems and fire alarm systems may communicate using RS 232. Information from the LBS devices may be used by various software applications running on the service provider computer systems such as call center applications i.e. OnStar corporate extranet and intranet web applications and consumer websites. These service provider applications may communicate over the Internet and other wide area networks using protocols such as User Datagram Protocol UDP and Extensible Markup Language XML . As described herein preferred embodiments of a server abstracted messaging system SAMS efficiently communicate messages between the LBS devices and the applications using the various communication protocols .

The queue manager thread pulls messages out of the message queue and determines what to do with them by determining which message handlers and message processors are interested in each message. As shown in singleton classes MessageHandlerManager and MessageProcessorManager hold information indicating which message handlers are available and which messages they should receive. These classes and maintain a list of message handlers and message processors that are registered. Registration is done either by calling a registerHandler or registerProcessor method or by scanning a directory for the relevant classes and registering them all.

The queue manager thread invokes the abstract method preProcessMessage prior to invoking any message handlers or message processors. This method can be used for example to unpack a CORBA representation in the message.

As shown in a message filter is defined to determine which messages that a message handler or message processor should receive. The message filter is an abstract class having one method filterMessage that returns true if the message handler is interested in the message.

So as not to burden the main message queue message handlers run in their own message handler runner threads . A pool of these threads is started by the queue manager thread . These threads monitor the message handler queue taking message handlers from the queue one at a time and running them. The message handlers were inserted into the queue by the queue manager thread after being looked up in the message handler manager . As shown in the message handler invokes the abstract method handleMessage to do the work. Each message handler may be assigned an integer priority value. The handlers having the highest priority will be given to the runner thread first.

As shown in message processor threads receive the messages next. The queue manager thread passes each message to the message processor manager which in turn passes it to all relevant processors by calling passMessageToProcessors. The message then stays in the processor queue until the message processor thread calls the abstract method processMessage. When processMessage terminates the message processor thread sleeps until a new message is ready to be processed. Message processor threads are started as they are registered.

In preferred embodiments if the order of execution of message related code is important then the order should be specified in the preProcessMessage method in the queue manager thread . Message processors run completely asynchronously. Thus even if they are given messages in a particular order one message processor may take longer than another to get around to processing a message so that the order in which they actually begin processing is undefined.

As discussed above message handlers are inserted into a priority queue . Thus even if higher priority message handlers are started before lower priority ones they are not guaranteed to finish first unless there is only one active handler runner thread . Thus any code that depends critically on other code being completed first must all be in one handler. Alternatively the first part of the code should be in the preProcessMessage method of the queue manager thread or there must be only one handler runner thread.

In the monitoring service events are passed to the processEvent method of the EventMessageReceiver remote interface as shown in . This class is a subclass of the MessageReceiver server class. The processEvent method wraps the event description in a message object and puts it in the message queue .

As shown in the QueueManagerThread is subclassed to provide a preProcessMessage method that can unwrap the CORBA representation of the event and provide a version for use by message handlers and message processors.

As shown in the MessageProcessor thread is subclassed to provide services that are applied to all events the DatabaseEventProcessor and the HalfDomeEventProcessor which will pass the message to other monitoring systems if necessary. The ForwardingEventProcessor forwards events to upstream messaging servers so as to provide scalability to run the messaging system across several machines. For example one server could provide database logging and another server could provide real time monitoring.

As shown in forwarding to real time monitoring is handled by a RealtimeMonitorHandler having a filter so that only relevant events are given to the message handler . DatabaseEnquiryHandler handles requests for event histories and AlarmHandler sends out alarms.

As shown in database connections are handled by a connection pooling database class . Threads may request connections from and to the database and connections are returned after use.

As shown in the database class also provides for schema management. A schema object has abstract methods to check whether a schema is present and create it if necessary. The compound schema checks for and creates any missing schemas in its schema list. The schema is made from a combination of the base schema which provides a version management table and the events schema which provides the necessary tables below for storing events.

To communicate a messages between a client computer and an LBS device a preferred embodiment of the server abstracted messaging system inserts a command into the SQL database using a yQueue Command. The command has a state selected from one of those listed in the Queue State Table below.

In the preferred embodiment yQueue Command is an SQL database procedure that is defined according to CREATE PROCEDURE dbo . yQueue Command .

In an example wherein the LBS device is a vehicle tracking unit the Command field may be one of the commands listed in the Command Table below as implemented in the firmware of the LBS device.

Shown in is one embodiment of a method for communicating between the wireless communication device and the LBS device using a text messaging protocol such as SMS. To begin a communication session a user of the wireless communication device enters a text message such as in the following format which is transmitted via the wireless communication network step 

The text message in the above format is communicated through the wireless communication network and the wide area communication network to the service provider computer system step . In a preferred embodiment the service provider computer system receives and parses the command text message transmitted from the wireless communication device and validates that the serial number is in a valid serial number format and properly registered to a customer of the service provider step as indicated by records stored in the service provider s database. Although the user does not necessarily have to be the user to which the serial number of the LBS device has been registered once the user is authenticated the user is deemed to be authorized to use the service.

If the serial number is not in the expected format or is not properly registered to a customer then a report text message is returned to the wireless communication device via the communication networks and in the following format 

If the serial number is valid the service provider computer system authenticates the submitted PIN Password against the customer s account to which the serial number of the LBS device has been registered step . If the PIN Password cannot be authenticated to the customer s account then the following report text message is returned to the wireless communication device via the communication networks and 

Once the serial number has been validated and the PIN Password authenticated the service provider computer system sends the LBS command to the LBS device identified by the serial number step . The LBS device receives the LBS command and processes the command to determine what function is to be performed. The LBS device then performs the function such as determining and transmitting location information disabling enabling the starter or unlocking the doors step . The LBS device also transmits a response based on the function performed step .

The service provider computer system continuously looks for the response transmitted from the LBS device . Once a response is received the service provider computer system parses and interprets the response step and constructs a report text message to be sent to the wireless communication device step . The report text message is forwarded via the communication network to the wireless network step and is transmitted via the wireless network to the wireless communication device step .

If the LBS device has responded properly the wireless communication device will receive a report text message in the following format which is displayed on the display screen of the wireless communication device step 

If the LBS device has responded with an improper response or the service provider computer system did not receive a proper response from the LBS device the wireless communication device will receive a report text message in the following format which is displayed on the display screen of the wireless communication device step 

In step the SAMS validates the serial number of the LBS device that was provided by the calling application. The serial number is embedded into the command to be sent by the SAMS to the LBS device and exists in the database of the service provider .

In step the SAMS validates the PIN password of the customer account. The PIN password is provided by the calling application to the SAMS . In preferred embodiments it is generally not necessary to forward this information to the LBS device .

In step an instance of the SAMS parses commands to be sent as a message to the LBS device by the service provider . Each instance of the SAMS is specifically designed to parse a message from one or more specific types of LBS devices .

In step the service provider receives a message transmitted by the SAMS and sends the command message to the corresponding LBS device . The information regarding how to send the command message to the specific LBS device is derived from the database of the service provider and is passed by the calling application to the SAMS .

The LBS device receives the command message step performs a function specified by the command message step and transmits a response message based on the function performed step .

In step the service provider transmits a message to the SAMS based on the response message received from the LBS device .

In step an instance of the SAMS parses the message as received by the service provider . The information regarding how to parse the message is derived from the instance of the SAMS that receives the message from the LBS device through the service provider .

In step the SAMS inserts a row into a database for use by the calling application including a success failure code and geographic data as previously described.

In step the SAMS notifies the calling application that the LBS device command is now complete and the results are available in the database of the service provider . This is preferably done via a result code that the calling application checks periodically until the transaction is successful or has failed.

The foregoing description of preferred embodiments for this invention have been presented for purposes of illustration and description. They are not intended to be exhaustive or to limit the invention to the precise form disclosed. Obvious modifications or variations are possible in light of the above teachings. The embodiments are chosen and described in an effort to provide the best illustrations of the principles of the invention and its practical application and to thereby enable one of ordinary skill in the art to utilize the invention in various embodiments and with various modifications as are suited to the particular use contemplated. All such modifications and variations are within the scope of the invention as determined by the appended claims when interpreted in accordance with the breadth to which they are fairly legally and equitably entitled.

