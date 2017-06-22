---

title: Communication system with transport link mechanism and method of operation thereof
abstract: A method of operation of a communication system includes: adapting an application programming interface (API) for communicating with an application using a control unit; identifying a detection signal for identifying a physical transport for communication with the application through the application programming interface (API); arbitrating a physical transport protocol for the physical transport with the application programming interface (API); and connecting a transport wrapper for the transport protocol with the application programming interface (API) for communicating with the physical transport.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09584601&OS=09584601&RS=09584601
owner: Telenav, Inc.
number: 09584601
owner_city: Santa Clara
owner_country: US
publication_date: 20130829
---
An embodiment of the present invention relates generally to a communication system and more particularly to a system for linking

Modern consumer and industrial electronics especially devices such as graphical display systems televisions projectors cellular phones portable digital assistants and combination devices are providing increasing levels of functionality to support modern life including three dimensional display services. Research and development in the existing technologies can take a myriad of different directions.

With the many continued advancements in communications technology more and more devices are being introduced in both the consumer and commercial sectors with advanced communications capabilities. Additionally advances in processing power and low power consumption technologies as well as advances in data coding techniques have led to the proliferation of wired and wireless communications capabilities on a widespread basis in a variety of different platforms.

For example communication networks both wired and wireless are now commonplace in many homes offices and other environments. Such communication networks allow various heretofore independent devices to share data and other information to enhance productivity or simply to improve their convenience to the user.

Many and varied technologies and protocols for this communication can now be made available. Typically only some of the many modes of communication technologies and protocols are available at a given time in a given location but the particular technologies and protocols can change as in the case of moving mobile devices.

Thus a need still remains for communication systems with link mechanisms. In view of the ever increasing commercial competitive pressures along with growing consumer expectations and the diminishing opportunities for meaningful product differentiation in the marketplace it is increasingly critical that answers be found to these problems. Additionally the need to reduce costs improve efficiencies and performance and meet competitive pressures adds an even greater urgency to the critical necessity for finding answers to these problems.

Solutions to these problems have been long sought but prior developments have not taught or suggested any solutions and thus solutions to these problems have long eluded those skilled in the art.

An embodiment of the present invention provides a method of operation of a communication system including adapting an application programming interface API for communicating with an application using a control unit detecting a detection signal for identifying a physical transport for communication with the application through the application programming interface API arbitrating a physical transport protocol for the physical transport with the application programming interface API and connecting a transport wrapper for the transport protocol with the application programming interface API for communicating with the physical transport.

An embodiment of the present invention provides a method of operation of a communication system including adapting an application programming interface API for communicating with an application using a control unit detecting a detection signal for identifying a physical transport for communication with the application through the application programming interface API arbitrating a physical transport protocol for the physical transport with the application programming interface API connecting a transport wrapper for the transport protocol with the application programming interface API for communicating with the physical transport and transmitting data for communication between the application and the physical transport.

An embodiment of the present invention provides a communication system including an application adaptation module configured to adapt an application programming interface API for communicating with an application a transport arbitration module coupled to the application adaptation module configured to detect a detection signal for identifying a physical transport for communication with the application through the application programming interface API a unified transport interface module coupled to the transport arbitration module configured to arbitrate a physical transport protocol for the physical transport with the application programming interface API and a transport abstraction module coupled to the unified transport interface module configured to connect a transport wrapper for the transport protocol with the application programming interface API for communicating with the physical transport.

Certain embodiments of the invention have other steps or elements in addition to or in place of those mentioned above. The steps or elements will become apparent to those skilled in the art from a reading of the following detailed description when taken with reference to the accompanying drawings.

The following embodiments are described in sufficient detail to enable those skilled in the art to make and use the invention. It is to be understood that other embodiments would be evident based on the present disclosure and that system process or mechanical changes may be made without departing from the scope of an embodiment of the present invention.

In the following description numerous specific details are given to provide a thorough understanding of the invention. However it will be apparent that the invention may be practiced without these specific details. In order to avoid obscuring an embodiment of the present invention some well known circuits system configurations and process steps are not disclosed in detail.

The drawings showing embodiments of the system are semi diagrammatic and not to scale and particularly some of the dimensions are for the clarity of presentation and are shown exaggerated in the drawing figures. Similarly although the views in the drawings for ease of description generally show similar order this depiction in the figures is arbitrary for the most part. Generally the invention can be operated in any order. The embodiments have been numbered first embodiment second embodiment etc. as a matter of descriptive convenience and are not intended to have any other significance or provide limitations for an embodiment of the present invention.

One skilled in the art would appreciate that the format with which image information is expressed is not critical to some embodiments of the invention. For example in some embodiments image information is presented in the format of X Y where X and Y are two coordinates that define the location of a pixel in an image.

In an alternative embodiment three dimensional image information is presented by a format of X Y Z with related information for color of the pixel. In a further embodiment of the present invention the three dimensional image information also includes an intensity or brightness element.

The term image referred to herein can include a two dimensional image three dimensional image video frame a computer file representation an image from a camera a video frame or a combination thereof. For example the image can be a machine readable digital file a physical photograph a digital photograph a motion picture frame a video frame an x ray image a scanned image or a combination thereof.

The term module referred to herein can include software hardware or a combination thereof in an embodiment of the present invention in accordance with the context in which the term is used. For example the software can be machine code firmware embedded code and application software. Also for example the hardware can be circuitry processor computer integrated circuit integrated circuit cores a pressure sensor an inertial sensor a microelectromechanical system MEMS passive devices or a combination thereof.

With the enormous growth in the smart phone applications area there is an increasing desire to bring in the smart phone applications into the infotainment head unit systems in automobiles. A key technology that can enable such an in dash user experience is the connectivity between smart phones and automotive systems such as automotive head units. Various technologies for communication such as WiFi Bluetooth or USB cables are enabled in both smart phones and auto head units. However there is no application that enables seamless connection between the phone and the car without any human interaction on one hand and development of applications without worrying about which mode of communication is available on the other hand.

Thus an Application Programming Interface API such as Telenav Link or TnLink provides an application developer concurrent use of multiple physical communication media without knowing what media exist or without worrying about the different communication protocol for each medium.

Referring now to therein is shown a communication system with transport link mechanism in an embodiment of the present invention. The communication system includes a first device such as a client or a server connected to a second device such as a client or server. The first device can communicate with the second device with a communication path such as a wireless or wired network.

For example the first device can be of any of a variety of communicating devices such as a cellular phone personal digital assistant a notebook computer a liquid crystal display LCD system a light emitting diode LED system an in dash device an in dash system or other multi functional display or entertainment device. The first device can couple either directly or indirectly to the communication path to communicate with the second device or can be a stand alone device.

For illustrative purposes the communication system is described with the first device as a communicating device although it is understood that the first device can be different types of devices. For example the first device can also be a device for presenting images or a multi media presentation. A multi media presentation can be a presentation including sound a sequence of streaming images or a video feed or a combination thereof. As an example the first device can be a high definition television a three dimensional television a computer monitor a personal digital assistant a cellular phone or a multi media set.

The second device can be any of a variety of centralized or decentralized computing devices or video transmission devices. For example the second device can be a multimedia computer a laptop computer a desktop computer a video game console grid computing resources a virtualized computer resource cloud computing resource routers switches peer to peer distributed computing devices a media playback device a Digital Video Disk DVD player a three dimension enabled DVD player a recording device such as a camera or video camera or a combination thereof. In another example the second device can be a signal receiver for receiving broadcast or live stream signals such as a television receiver a cable box a satellite dish receiver or a web enabled device.

The second device can be centralized in a single room distributed across different rooms distributed across different geographical locations embedded within a telecommunications network. The second device can couple with the communication path to communicate with the first device .

For illustrative purposes the communication system is described with the second device as a computing device although it is understood that the second device can be different types of devices. Also for illustrative purposes the communication system is shown with the second device and the first device as end points of the communication path although it is understood that the communication system can have a different partition between the first device the second device and the communication path . For example the first device the second device or a combination thereof can also function as part of the communication path .

The communication path can span and represent a variety of networks. For example the communication path can include wireless communication wired communication optical ultrasonic or the combination thereof. Satellite communication cellular communication Bluetooth Infrared Data Association standard IrDA wireless fidelity WiFi and worldwide interoperability for microwave access WiMAX are examples of wireless communication that can be included in the communication path . Ethernet digital subscriber line DSL fiber to the home FTTH and plain old telephone service POTS are examples of wired communication that can be included in the communication path . Further the communication path can traverse a number of network topologies and distances. For example the communication path can include direct connection personal area network PAN local area network LAN metropolitan area network MAN wide area network WAN or a combination thereof.

Referring now to therein is shown an example of a display interface of the communication system . The first device can optionally include a handheld device including a smart phone or an infotainment device including an in dash system or an automotive system such as an automotive head unit.

Similarly the display interface can also be optionally included in the second device of . The display interface of the second device can also include a handheld device including a smart phone or an infotainment device including an in dash device or an automotive head unit.

The display interface can provide a visual image of locations and objects in the physical world transformed for display. The visual image preferably updates or changes as the first device or the second device moves in the physical world. The display interface can also provide status confirmation selection control or combination thereof of communication with the first device the second device or combination thereof.

Referring now to therein is shown an exemplary block diagram of the communication system . The communication system can include the first device the communication path and the second device . The first device can send information in a first device transmission over the communication path to the second device . The second device can send information in a second device transmission over the communication path to the first device .

For illustrative purposes the communication system is shown with the first device as a client device although it is understood that the communication system can have the first device as a different type of device. For example the first device can be a server having a display interface.

Also for illustrative purposes the communication system is shown with the second device as a server although it is understood that the communication system can have the second device as a different type of device. For example the second device can be a client device.

For brevity of description in this embodiment of the present invention the first device will be described as a client device and the second device will be described as a server device. The embodiment of the present invention is not limited to this selection for the type of devices. The selection is an example of an embodiment of the present invention.

The first device can include a first control unit a first storage unit a first communication unit and a first user interface . The first control unit can include a first control interface . The first control unit can execute a first software to provide the intelligence of the communication system .

The first control unit can be implemented in a number of different manners. For example the first control unit can be a processor an application specific integrated circuit ASIC an embedded processor a microprocessor a hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof. The first control interface can be used for communication between the first control unit and other functional units in the first device . The first control interface can also be used for communication that is external to the first device .

The first control interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first control interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the first control interface . For example the first control interface can be implemented with a pressure sensor an inertial sensor a microelectromechanical system MEMS optical circuitry waveguides wireless circuitry wireline circuitry or a combination thereof.

The first storage unit can store the first software . The first storage unit can also store the relevant information such as data representing incoming images data representing previously presented image sound files or a combination thereof.

The first storage unit can be a volatile memory a nonvolatile memory an internal memory an external memory or a combination thereof. For example the first storage unit can be a nonvolatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The first storage unit can include a first storage interface . The first storage interface can be used for communication between and other functional units in the first device . The first storage interface can also be used for communication that is external to the first device .

The first storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first storage interface can include different implementations depending on which functional units or external units are being interfaced with the first storage unit . The first storage interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first communication unit can enable external communication to and from the first device . For example the first communication unit can permit the first device to communicate with the second device of an attachment such as a peripheral device or a computer desktop and the communication path .

The first communication unit can also function as a communication hub allowing the first device to function as part of the communication path and not limited to be an end point or terminal unit to the communication path . The first communication unit can include active and passive components such as microelectronics or an antenna for interaction with the communication path .

The first communication unit can include a first communication interface . The first communication interface can be used for communication between the first communication unit and other functional units in the first device . The first communication interface can receive information from the other functional units or can transmit information to the other functional units.

The first communication interface can include different implementations depending on which functional units are being interfaced with the first communication unit . The first communication interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first user interface allows a user not shown to interface and interact with the first device . The first user interface can include an input device and an output device. Examples of the input device of the first user interface can include a keypad a touchpad soft keys a keyboard a microphone an infrared sensor for receiving remote signals or any combination thereof to provide data and communication inputs.

The first user interface can include a first display interface . The first display interface can include a display a projector a video screen a speaker or any combination thereof.

The first control unit can operate the first user interface to display information generated by the communication system . The first control unit can also execute the first software for the other functions of the communication system . The first control unit can further execute the first software for interaction with the communication path via the first communication unit .

The second device can be optimized for implementing an embodiment of the present invention in a multiple device embodiment with the first device . The second device can provide the additional or higher performance processing power compared to the first device . The second device can include a second control unit a second communication unit and a second user interface .

The second user interface allows a user not shown to interface and interact with the second device . The second user interface can include an input device and an output device. Examples of the input device of the second user interface can include a keypad a touchpad soft keys a keyboard a microphone or any combination thereof to provide data and communication inputs. Examples of the output device of the second user interface can include a second display interface . The second display interface can include a display a projector a video screen a speaker or any combination thereof.

The second control unit can execute a second software to provide the intelligence of the second device of the communication system . The second software can operate in conjunction with the first software . The second control unit can provide additional performance compared to the first control unit .

The second control unit can operate the second user interface to display information. The second control unit can also execute the second software for the other functions of the communication system including operating the second communication unit to communicate with the first device over the communication path .

The second control unit can be implemented in a number of different manners. For example the second control unit can be a processor an embedded processor a microprocessor hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof.

The second control unit can include a second controller interface . The second controller interface can be used for communication between the second control unit and other functional units in the second device . The second controller interface can also be used for communication that is external to the second device .

The second controller interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second controller interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the second controller interface . For example the second controller interface can be implemented with a pressure sensor an inertial sensor a microelectromechanical system MEMS optical circuitry waveguides wireless circuitry wireline circuitry or a combination thereof.

A second storage unit can store the second software . The second storage unit can also store the such as data representing incoming images data representing previously presented image sound files or a combination thereof. The second storage unit can be sized to provide the additional storage capacity to supplement the first storage unit .

For illustrative purposes the second storage unit is shown as a single element although it is understood that the second storage unit can be a distribution of storage elements. Also for illustrative purposes the communication system is shown with the second storage unit as a single hierarchy storage system although it is understood that the communication system can have the second storage unit in a different configuration. For example the second storage unit can be formed with different storage technologies forming a memory hierarchal system including different levels of caching main memory rotating media or off line storage.

The second storage unit can be a volatile memory a nonvolatile memory an internal memory an external memory or a combination thereof. For example the second storage unit can be a nonvolatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The second storage unit can include a second storage interface . The second storage interface can be used for communication between other functional units in the second device . The second storage interface can also be used for communication that is external to the second device .

The second storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second storage interface can include different implementations depending on which functional units or external units are being interfaced with the second storage unit . The second storage interface can be implemented with technologies and techniques similar to the implementation of the second controller interface .

The second communication unit can enable external communication to and from the second device . For example the second communication unit can permit the second device to communicate with the first device over the communication path .

The second communication unit can also function as a communication hub allowing the second device to function as part of the communication path and not limited to be an end point or terminal unit to the communication path . The second communication unit can include active and passive components such as microelectronics or an antenna for interaction with the communication path .

The second communication unit can include a second communication interface . The second communication interface can be used for communication between the second communication unit and other functional units in the second device . The second communication interface can receive information from the other functional units or can transmit information to the other functional units.

The second communication interface can include different implementations depending on which functional units are being interfaced with the second communication unit . The second communication interface can be implemented with technologies and techniques similar to the implementation of the second controller interface .

The first communication unit can couple with the communication path to send information to the second device in the first device transmission . The second device can receive information in the second communication unit from the first device transmission of the communication path .

The second communication unit can couple with the communication path to send information to the first device in the second device transmission . The first device can receive information in the first communication unit from the second device transmission of the communication path . The communication system can be executed by the first control unit the second control unit or a combination thereof. For illustrative purposes the second device is shown with the partition having the second user interface the second storage unit the second control unit and the second communication unit although it is understood that the second device can have a different partition. For example the second software can be partitioned differently such that some or all of its function can be in the second control unit and the second communication unit . Also the second device can include other functional units not shown in for clarity.

The functional units in the first device can work individually and independently of the other functional units. The first device can work individually and independently from the second device and the communication path .

The functional units in the second device can work individually and independently of the other functional units. The second device can work individually and independently from the first device and the communication path .

For illustrative purposes the communication system is described by operation of the first device and the second device . It is understood that the first device and the second device can operate any of the modules and functions of the communication system .

Referring now to therein is shown a control flow for an application programming interface system of the communication system in an embodiment of the present invention. An application programming interface API such as an API including Telenav Link preferably includes an application adaptation module a transport arbitration module a unified transport interface module and a transport abstraction module .

The unified transport interface module can preferably enable application or application logic communications through multiple communication protocols including physical transports. The interface can provide asynchronous network operations to allow maximum resource utilization.

The API including a Telenav Link can be organized into multiple layers such as a Transport Abstraction Layer and a Transport Arbitration Layer. The transport abstraction module can include the Transport Abstraction Layer of the transport abstraction module which can include each transport medium or interconnect available in the system wrapped by a transport wrapper .

The transport wrapper preferably adapts the communication protocol including physical transports such as an underlying medium access API provided by an operating system device drivers or combination thereof into a Unified Transport API of the unified transport interface module . Thus a Transport Arbitration Layer of the transport arbitration module can use the access transports based on the Unified Transport API of the unified transport interface module .

As an example the API including the Telenav Link can be implemented in C programming language. For application use an additional Application Adaptation Layer of the application adaptation module can be coupled to or interface with the Transport Arbitration Layer of the transport arbitration module for binding application programming interfaces into other languages applications or combination thereof.

Further for example to load the API including the Telenav Link an application preferably calls an initialization API. The initialization API could be implemented in C language as follows 

For C and other object oriented languages this initialization API can be bound as an object construction. Note that the API including the Telenav Link can connect to another of the API including another Telenav Link. Thus for two applications or two modules of one application to couple interface or talk to each other each application or module preferably initializes the API including the Telenav Link object.

The API including the Telenav Link preferably includes a plug in mechanism for adding transport wrappers for new kinds of transport wrappers on the fly. The Telenav Link can expose different types sets or combination thereof of APIs to an application that uses the Telenav Link through different implementations of the application adaptation module .

An add transport module can preferably integrate other communication protocol including physical transports such WiFi Bluetooth USB a proprietary Bluetooth stack other communication transports or combination thereof. The API including the Telenav Link can provide integration of other communication protocols including proprietary physical protocol stacks utilizing a plug in format or plug in model for transport wrappers . The plugin architecture of the transport application can allows additional transport abstraction modules to be added at run time.

For example an event based function or application programming interface API can connect other components or function to the Telenav Link using an event bus connector such as a Telenav Link object constructed or initialized to plugs in relevant transport wrappers using an addTransport API. The transport arbitration module arbitrates communication transports and initiates a connection procedure automatically. Once a connection is established the Telenav Link is notified using a Connected event. If the connection is broken the application is notified using a Disconnected event. The Telenav Link publishes a SendPacket event to send data and a PacketReceived event when data is received from another device such as a remote peer.

As another example each of the transport wrappers can connect be integrated in or be plugged into the API using the add transport module including the addTransport API. Other of the transport wrappers including new transport wrappers or custom transport wrappers can be provided for any transport medium interconnect or physical protocol stack of an operating system interface module or a system interface module including a proprietary physical transport protocol medium or interconnect with an appropriate protocol stack or proprietary protocol stack .

Further for example the transport wrapper such as the custom transport wrapper can then be connected integrated or plugged in with the transport wrappers including default wrappers that can be packaged with the API including the Telenav Link. The addTransport API can be implemented as follows 

The add transport module including the addTransport API can define a wrapper plugin object as well as two other parameters related to the transport wrapper . The API including the Telenav Link preferably provides point to point communication including one end of the transport medium can act as a connection initiator the other end can act as a connection acceptor. This initiator acceptor mode can be defined in an endpointType parameter. The priority endpointType parameter can define priority of a transport medium particularly in arbitrating among multiple transport mediums.

In the Transport Arbitration Layer of the transport arbitration module a multi transport arbitrator module tries the available transports to establish a connection. For example by default all available transports are attempted in parallel and whichever responds first is accessed for further data communication. This default arbitration policy can be overridden by a setTranpsortArbitrationPolicy API. At least three policies can be parallel round robin or priority order.

Further for example by default the API including the Telenav Link would not attempt other transports while one connected session is ongoing. A new connection is attempted only when an existing connection is terminated disconnected or otherwise broken. Allowing or preventing concurrent connections can be set by a flag or preference for multiple connections. The preferred default for this setting can be overridden and multiple concurrent connections over different or same medium can be allowed by invoking an allowMultipleConnection API.

Depending on preference settings switching to other transport can be allowed. There would be little value or sense to add two or more USB cables between one pair of devices. However multiple physical wireless channels could be used such as in case of Bluetooth or WiFi for redundancy additional bandwidth or combination thereof

Multiple connected data channels can be established between the smart phone and head unit if needed. All data channels can be full duplex and can carry arbitrary binary data. For portable serialization of data over the wire a protocol buffer serialization application can be leveraged.

The transport wrappers provide access to the unified transport interface module including the Unified Transport API a discovery module a data channel module or combination thereof. Each of the transport wrappers provides an interface makes available or exposes one or more of the wrappers or Transport APIs that the Transport Arbitration Layer of the transport arbitration module can interface with access or use. There can be one or more functions defined in the Unified Transport API of the unified transport interface module . Following are six examples 

The first four Unified Transport APIs can be asynchronous function calls. The last two are preferably for management of prior asynchronous calls. Each of the asynchronous functions can have the following pattern 

Each of the Unified Transport APIs can return a success failure Boolean flag. Also each function can take a callback function pointer as a parameter that is called on at the completion of an asynchronous operation. As asynchronous functions these functions preferably return results such as a return value immediately.

For example if the return value indicates a failure the implication is that initiation of the asynchronous operation failed thus a completion callback function may not be called afterwards. On the other hand if the return value indicates a success the implication is that the asynchronous operation was initiated successfully. In this case the completion callback function may be called exactly once.

Completion of a function call such as the Unified Transport APIs may be a success or failure. This can be denoted using an error code parameter in a completion function such as the completion callback function. In the event of a successful function call the discovery module can function as a session manager module coupled to the connected data channel module .

Of the functions preferably defined in the discovery module or the connected data channel module of the Unified Transport API two examples can establish a connection. The first two functions discoverAndConnect and advertiseAndAccept can be used for establishing a connection.

Each transport can be configured either as acceptor or as initiator of a connection when being plugged into the application programming interface API such as an API including the Telenav Link using the addTransport API. The acceptor side can use the advertiseAndAccept API and the initiator side can use the discoverAndConnect API. Those are specified as properties of the transport. Examples of these two functions are as follows 

In both cases the ConnectionHandle parameter represents a connection such as an established bi directional channel for sending and receiving data. The error code parameter denotes the type of error if the process failed.

In addition there can be a caller reference parameter in all four examples of asynchronous APIs. The caller reference parameter can provide support for object oriented users of the asynchronous APIs. The caller reference parameter preferably contains a reference to the object that invoked the asynchronous API. When a corresponding callback is invoked the same reference to the object is passed back so that the object that was called can be tracked.

For example the endpoint for connection such as port number service ID or combination thereof might not be specified in the discoverAndConnect or the advertiseAndAccept function calls. This would abstract the actual or exact discovery mechanism used by the underlying transport.

Further to the example if the transport is Bluetooth the API can use a Bluetooth Service Discover Protocol to look for the API including a Telenav Link running in any of the Bluetooth paired devices. If the transport is WiFi the API can use a User Datagram Protocol UDP broadcast to identify any device running the API including a Telenav Link in the same network to respond to a query message. For USB it looks for the API including a Telenav Link running in the USB connected device and so on.

If the API finds a service such as Bluetooth WiFi or USB it connects to the remote device. The API including the Telenav Link can be configured to establish a communication protocol channel automatically unconditionally or combination thereof if an API capable remote device is present. If authentication or establishment of a secure communication protocol channel is required authentication such as a handshaking protocol can be provided or implemented on the connection such as an established raw data pipe. If authentication fails the data pipe can be closed by the closeConnection API.

Thus the API can optionally automatically connect to a device it detects having supported active and unused transport service such as Bluetooth WiFi USB other communication protocol or other transport protocols. Optionally the API can automatically connect if an application in a device requests a connection that is connections only if there is a purpose for the connection.

Sending and receiving data once a connection is established can include a send a receive or combination thereof for arbitrary binary data. For example the following two APIs are configured to provide the aforementioned send receive or combination thereof.

These two APIs include return value caller tracking completion callback in a manner similar to other asynchronous APIs previously described. The ConnectionHandle parameter is used to designate a connection over which data is being sent or received. As such multiple logical channels communication protocol channels or communication protocol connections are supported over a single physical medium. An arbitrary number of new logical connections can be established using the discoverandConnect API and advertiseAndAccept API.

For both the asyncSend API and the asyncRecv API a reference to a pre allocated byte buffer is passed along with a buffer size. In the case of a send the buffer is filled with data to send. In the case of a receive the buffer is filled with received data preferably at the end of an asynchronous receive operation.

The asynchronous send or receive process initiated by the asyncSend API and asyncRecv API preferably completes when transfer of all bytes intended to send or receive is completed or an error occurred. In either case the number of actual bytes transferred can be mentioned as a parameter in the callback function.

Further regarding asynchronous calls and based on previous descriptions of the asynchronous API including return values completion callback and caller tracking these APIs do not need to be reentrant. Preferably only one function will be called at a time. The API is not meant to have any concurrency control built into it.

The implementations for initiation of connections with the discoverAndConnect API and the advertiseAndAccept API can preferably be called one at time for any given time. It is also preferable that only one of the initiations of the connections is ongoing.

Similarly for data send receive APIs such as asyncSend API and the asyncRecv API preferably only one send or receive operation is ongoing on a given connection at any given time. Optionally one send and one receive can be ongoing concurrently on the same connection. A further option can include two different connections having one connection with a send or a receive concurrent to the other connection with a send or receive.

When the previously established connection is closed all pending asynchronous send receive operations or APIs initiated on or associated with that connection are preferably closed or cancelled. This would preferably invoke completion callback functions with an error. The closeConnection function preferably returns a result or completes only after all pending operations are closed or cancelled and all corresponding completion callback functions are called and returned.

A previously attempted initiation of a connection can be cancelled using a cancel API such as the following 

When the cancel API is called the previously invoked discoverAndconnect API or advertiseAndAccept API functions or operations close cancel or terminate and the corresponding completion callback functions are preferably invoked or called and can return a failure notification. The cancel API function preferably returns a result or completes after all pending operations are closed or canceled and all corresponding completion callback functions are called and returned.

Note that the closeConnection function or API and cancel function or API are preferably synchronous APIs. They can return a result or complete after completion of the closeConnection function or cancel function operations and preferably do not have any completion callback function.

An event notification module or event notification system can provide communication between the frame work API having the Telenav Link and other functions including the rest of the application. The Telenav Link can communicate with the event notification module by publishing events of the Telenav Link including connection disconnection and data arrival. For sharing or sending data for other functions or parts of the application of the Telenav Link the data simply needs to be published on the event notification system . Telenav Link takes the data for the events from the event notification system and communicates transmits or carries the data through the communication protocol channel.

The communication system has been described with module functions or order as an example. The communication system can partition the modules differently or order the modules differently. For illustrative purposes the transport arbitration module is shown with the multi transport arbitrator module the discovery module and the connected data channel module in a row it is understood that the modules can operate in any order including independently from the other modules.

The API can be implemented in part or wholly as a hardware component such as a Printed Circuit Board a Multi Chip Module a Thick Film Hybrid a System in Package an Application Specific Standard Part an Application Specific Integrated Circuit or combination thereof including Standard Cell Programmable Gate Array Structured Design Custom Design or combination thereof.

The modules described in this application can be hardware implementation or hardware accelerators in the first control unit of or in the second control unit of . The modules can also be hardware implementation or hardware accelerators within the first device or the second device but outside of the first control unit or the second control unit respectively.

The physical transformation from the application programming interface results in the movement in the physical world such as images audio captured multimedia or combination thereof. Movement in the physical world results in changes to the images audio captured multimedia or combination thereof representing the application data by the application programming interface including the application adaptation module the transport arbitration module the unified transport interface module or the transport abstraction module .

The modules described in this application can be part of the first software of the second software of or a combination thereof. These modules can be stored in the first storage unit of the second storage unit of or a combination thereof. The first control unit of the second control unit of or combination thereof can execute these modules for operating the communication system .

The communication system has been described with module functions or order as an example. The communication system can partition the modules differently or order the modules differently. For example the transport arbitration module can include the multi transport arbitrator module the discovery module or the connected data channel module as separate modules although these modules can be combined into one. Also the transport arbitration module can be split into separate modules for implementing in the separate modules.

The modules described in this application can be hardware implementation hardware circuitry or hardware accelerators in the first control unit or in the second control unit . The modules can also be hardware implementation hardware circuitry or hardware accelerators within the first device or the second device but outside of the first control unit or the second control unit respectively.

It has been discovered that the application adaptation module the transport arbitration module the unified transport interface module the transport abstraction module the system interface module and the add transport module of the API including the Telenav Link provides a seamless way to connect automotive head units to handheld smart phones over different communication protocols or media.

Further it has been discovered that the application adaptation module the transport arbitration module the unified transport interface module the transport abstraction module the system interface module and the add transport module identify the physical protocol stacks such as wireless fidelity WiFi Bluetooth universal serial bus USB other communication protocols or combination thereof for concurrent use and to provide connectivity through whichever communication protocol or transport protocol is available at any given time. The physical protocol stack can preferably be detected or identified by a transmission or a signal based on a particular or a specific of the physical protocol stack .

Yet further it has been discovered that the application adaptation module the transport arbitration module the transport arbitration module the transport abstraction module the system interface module and the add transport module provide a uniform automatic discovery mechanism that can include a peer node. The uniform automatic discovery mechanism is preferably based on the Telenav Link including a Telenav Link or Tnlink service leveraging underlying transport protocols or transport specific service discovery protocols such as Bluetooth WiFi USB Bluetooth SDP WiFi direct Bonjour USB device discovery etc.

Referring now to therein is shown a control flow of the application programming interface API of the application programming interface system in an embodiment of the present invention. The application programming interface API such as an API includes the application adaptation module the transport arbitration module the unified transport interface module and the transport abstraction module .

The application adaptation module can include an application communication or application data including a communication or data of the application logic of . The application adaptation module preferably includes the application data for sending or receiving with the application logic and the system interface module of of the first device of or the second device of .

The discovery module of the transport arbitration module preferably identifies or detects a detection transmission or a detection signal based on the protocol stacks of that are available in the system interface module of the first device or the second device . The physical protocol stack of can preferably be detected or identified by the detection transmission or the detection signal including a physical transport protocol detection signal such as carrier signals identification signals acknowledgment signals or combination thereof.

The application data can be transmitted or communicated through the physical transport communication protocol with the transport wrapper based on identification of the detection signal .

It has been discovered that the communication system having the application adaptation module with the application data provides interoperability both in smart phones and in automotive applications. The interface with the application programming interface API such as an API including the Telenav Link to both the smart phone and automotive application are the same and can communicate in a peer to peer fashion.

Further it has been discovered that the communication system having the transport arbitration module with the detection signal provides an interface to makes available or exposes different communication transport protocol APIs to the application that uses the through different implementations of the Application Adaptation Layer.

Referring now to therein is shown an exemplary network of the communication system in an embodiment of the present invention. The exemplary network preferably includes a handheld device such as the first device of or the second device of and an automotive system such an as in dash device or an automotive head unit.

The handheld device preferably includes the API with the transport abstraction module coupled to an operating system such as a smart phone operating system OS . The operating system can communicate with the automotive system with a network such as a physical transport such as an underlying medium access API provided by an operating system device drivers or combination thereof. The handheld device can optionally communicate with a wireless network such as a data network cellular network other handheld networks or combination thereof

The automotive system can preferably include the API with an automotive application coupled to the operating system interface module for communication with the network . The API can connect the transportation module of the handheld device and the system interface module of the automotive system with multiple communication protocols.

It has been discovered that the API including the Telenav Link including the Unified Transport Interface of the unified transport interface module enables communication of the application logic of independent of a particular of the physical protocol stack . The Unified Transport Interface is defined in terms of asynchronous functions for network send or receive operations to allow maximum resource utilization.

Referring now to therein is shown an exemplary network of the communication system in an embodiment of the present invention. The exemplary network preferably includes a handheld device such as the first device of or the second device of and an automotive system such an as in dash device or an automotive head unit.

The handheld device preferably includes two of the API . One of the API can be coupled to a first application such as a navigation application a Telenav Navigator application or other handheld device application. The first application can communicate with the automotive system with a first network such as a physical transport such as an underlying medium access API provided by an operating system device drivers or combination thereof.

Another of the API of the handheld device can be coupled to a second application such as a messaging application an instant messaging application or other handheld device application. The second application can communicate with the automotive system with a second network such as a physical transport such as an underlying medium access API provided by an operating system device drivers or combination thereof.

Multiple instances of the API of the handheld device include identifiers parameterizing the Telenav Link to multiplex underlying protocols. The API coupled to the first application can be parameterized for the first network . Similarly the API coupled to the second application can be parameterized for the second network .

For the example each of the Telenav Links of the handheld device can be parameterized with different universal unique identifiers UUID for a physical transport such as a service UUID for multiplexing with the physical protocol stack over a common network such as Bluetooth .

Similarly the automotive system also includes two of the API . One of the API can be coupled to the first application such as a navigation application a Telenav Navigator application or other handheld device application. The first application can communicate with the automotive system with the first network such as a physical transport such as an underlying medium access API provided by an operating system device drivers or combination thereof.

Another of the API of automotive system can be coupled to the second application such as a messaging application an instant messaging application or other handheld device application. The second application can communicate with the automotive system with a second network such as a physical transport such as an underlying medium access API provided by an operating system device drivers or combination thereof.

Multiple instances of the API of the automotive system can include identifiers parameterizing the Telenav Link to multiplex underlying protocols. The API coupled to the first application can be parameterized for the first network . Similarly the API coupled to the second application can be parameterized for the second network .

For the example each of the Telenav Links of the automotive system can be parameterized with different universal unique identifiers UUID for a physical transport such as a service UUID for multiplexing with the physical protocol stack over a common network such as Bluetooth .

It has been discovered that the API can multiplex underlying protocols with different universal unique identifiers UUID for a physical transport. The different UUIDs can be service UUIDs for a common physical transport.

Referring now to therein is shown a flow chart of a method of operation of a communication system in an embodiment of the present invention. The method includes adapting an application programming interface API for communicating with an application using a control unit in a block identifying a detection signal for identifying a physical transport for communication with the application through the application programming interface API in a block arbitrating a physical transport protocol for the physical transport with the application programming interface API in a block and connecting a transport wrapper for the transport protocol with the application programming interface API for communicating with the physical transport for displaying on a device in a block .

The resulting method process apparatus device product and or system is straightforward cost effective uncomplicated highly versatile accurate sensitive and effective and can be implemented by adapting known components for ready efficient and economical manufacturing application and utilization. Another important aspect of an embodiment of the present invention is that it valuably supports and services the historical trend of reducing costs simplifying systems and increasing performance.

These and other valuable aspects of an embodiment of the present invention consequently further the state of the technology to at least the next level.

While the invention has been described in conjunction with a specific best mode it is to be understood that many alternatives modifications and variations will be apparent to those skilled in the art in light of the aforegoing description. Accordingly it is intended to embrace all such alternatives modifications and variations that fall within the scope of the included claims. All matters set forth herein or shown in the accompanying drawings are to be interpreted in an illustrative and non limiting sense.

