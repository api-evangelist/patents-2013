---

title: Networked security system with translating router
abstract: A system and method for protocol translation between security devices in a security network using a transforming router. The router utilizes protocol templates to identify the protocols that encapsulate messages sent by the devices, and to determine the format of the messages. Using the protocol templates, the router translates the messages from protocols of source security devices to an intermediate protocol, translates the messages in the intermediate protocol into destination protocols for destination security devices, and forwards the messages to the destination security devices.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09191383&OS=09191383&RS=09191383
owner: Sensormatic Electronics, LLC
number: 09191383
owner_city: Boca Raton
owner_country: US
publication_date: 20130319
---
Manufacturers of security systems provide security devices for public and private institutions commercial businesses schools hospitals and government institutions. The security devices are connected to security networks installed in the customer premises. Security systems that were once separate such as systems for fire detection and suppression video monitoring and intrusion detection are increasingly converging to form integrated or converged security systems connected to a common security network. This provides operators of security networks with improved management reporting problem isolation and fault tolerance capabilities for the security devices in the security network.

Within a security network security devices send messages to one another in communications protocols. Security devices typically include a combination of software protocol stacks and custom software that implement the communications protocols. The software protocol stacks are typically modeled after the OSI 7 layer model.

Converged security systems integrate many different security devices or components that communicate over the security network using standard and proprietary communications protocols. The components range in sophistication from simple sensor devices such as door sensors and access card readers that send one way unsolicited messages in response to detected events to more advanced devices such as fire alarm panels video cameras and network video recorders. The latter devices typically support two way communications and more flexible communications protocols such as Internet Protocol IP .

Moreover security networks for converged security systems often include mixed installations of modern and legacy based security devices. Security devices in modern security systems typically connect to shared bus network segments such as Ethernet and utilize standard two way IP protocols. Legacy based systems on the other hand typically utilize a mix of standard and proprietary communications protocols on serial links or network segments.

A major challenge for manufacturers and system integrators of converged security systems is providing interoperability between security devices that support different communications protocols. The interoperability also has to take into account the fact that communicating security devices can reside on separate network segments with different physical layers such as bus based Ethernet and serial based RS 232 links.

Additionally security devices and the security network itself operate in a high security environment. The security network is typically isolated from a company s data network. Operators and managers often have access only to those network segments within the security network that are within their immediate control and job function. This creates logistical and operational problems when coordinating and implementing software upgrades for security devices.

Current approaches to solving the problem of interoperability between security devices supporting different communications protocols include the use of custom software drivers and a unifying protocol super set. The custom driver approach requires that each security device provide a custom application programming interface API or server driver for each communications protocol that the security device does not currently support. The unifying protocol approach creates a single new protocol that provides interoperability between all security devices in the security network.

The current approaches to solving the problem of achieving interoperability between security devices supporting different communications protocols in a security network have problems.

The custom driver approach requires that manufacturers implement custom APIs on each security device as part of each device s software executable image. This adds research development and testing costs. Operators must then download the new version of the software for each security device in their security network that requires the changes. This creates logistical problems as the number of security devices increases combined with the aforementioned problems associated with performing device software upgrades in a high security environment.

The unifying protocol solution has the same logistical problems as the custom driver approach and introduces protocol performance uncertainties. Many communications protocols used in security devices have existed for 10 years or more and have possibly evolved to their optimal form. A single one size fits all unifying protocol could likely degrade critical message timing for certain protocols for example and thus operation of the security device itself.

The present invention takes a different approach to solving the problem of achieving interoperability between security devices supporting different communications protocols in a security network. The invention utilizes a universal protocol converter or translator typically operating within a separate device or network appliance that the operator connects to their existing security network. Such as device can also be referred to as a router or a layer 4 router.

In one example the solution approaches the problem of unified data aggregation and cross product interfacing from the perspective of protocol transformation at the byte level of the message data OSI layer 4 rather than at the application level OSI layers 6 and 7 of the network interface.

OSI layer 4 also known as the transport layer is a true source to destination or end to end layer and as such is not concerned with the details of the underlying communications facility. It is typically only used by router or firewall firmware and not by protocol management software. The transport layer typically handles functions such as flow control reliable message delivery and multiplexing of multiple simultaneous data streams or sessions onto the same logical communications link.

Like a router in a data network the layer 4 router forwards messages from source security devices to destination security devices that potentially reside on different network segments. Unlike traditional routers which make forwarding decisions based on OSI layer 3 data of the messages however the layer 4 router processes OSI layer 3 data of the messages at OSI layer 4.

In this way the layer 4 router essentially repurposes the transport layer for protocol translation and management purposes. The layer 4 router then utilizes a router state engine software module to set up and maintain the communications sessions between source security devices and destination security devices from applications and to perform the activities usually associated with the transport layer.

The present invention combines the functionality of firewall router firmware with protocol translation software to create a protocol translation system for security devices in a security network that can accommodate both byte packed and string protocols.

Moreover the solution creates a template transform structure to address protocol translation issues rather than fixed protocol translation objects. This creates a unique extensible environment for addressing intra product communications requirements.

In general according to one aspect the invention features a protocol translation system for a security system comprising a security network and security devices connected to the security network that communicate messages over the security network using communications protocols. A router receives messages from source security devices translates the messages to new protocols and sends the translated messages to destination security devices. A protocol server provides protocol templates to the router defining the translation of the messages.

In one example the protocol templates of the protocol server comprise a protocol identification template PIT that includes a PIT entry that defines the name and format of each protocol supported by the router which the router uses to identify the communications protocol of the message and one or more data transform templates DTTs associated with each PIT entry which the router uses to interpret the message.

Each DTT specifies the format of data within the message and bitmasks for manipulating the data. Each PIT entry in the PIT identifies type of protocol that includes the message and the name of the associated DTT.

The router preferably performs the message translation by first determining the PIT entry associated with the communications protocol of the source security device and downloading the associated DTT. Using the DTT to determine the format of the messages the router then transforms the messages from the source security device into translated messages for the destination security device.

In one aspect the router forwards the messages from the source security device directly to the destination security device in response to a determination that the communications protocol of the source security device and the communications protocol of the destination security device are the same communications protocol.

In the preferred embodiment the router determines that the communications protocol of the source security device and the communications protocol of the destination security device are not the same communications protocol and in response to the determination translates the messages from the source security devices to the new protocols and sends the translated messages to destination security devices.

In general according to another aspect the invention features a method of operation of a protocol translation system for a security system comprising a security network security devices connected to the security network that communicate messages over the security network using communications protocols a router and a protocol server. The method comprises receiving messages from source security devices translating the messages to new protocols sending the translated messages to destination security devices and providing protocol templates to the router defining the translation of the messages.

In general according to another aspect the invention features a protocol translation system for a security system comprising a security network including multiple network segments security devices connected to the security network on the network segments that communicate information over the security network using communications protocols and a router that receives messages from source security devices in source protocols translates the messages into an intermediate protocol and then translates the messages into destination protocols of the destination security devices.

In the preferred embodiment the router utilizes protocol templates to translate the messages from the source security devices in the source protocols into the intermediate protocol and to translate the messages from the intermediate protocol into destination protocols of the destination security devices. Preferably the router implements the intermediate protocol as an object in JSON format.

In another example the protocol translation system includes an application server that includes applications for defining communications sessions between the source security devices and the destination security devices. The applications specify the source security device and the destination security device and a requested communications protocol for communicating with the destination security device.

In yet another example the router includes an event subscription service that provides event subscription services to the applications.

The router further comprises a router state engine for maintaining connection state information and for handling data flows between the source security device and the destination security device of the subscribing applications and the router.

According to another aspect the router the source security devices and the destination security devices connect to network segments with different physical layers that support one or more interface types.

Within the security network the security devices include one or more network video recorders camera controllers video cameras security panels connected to one or more alarm sensors and door controllers connected to one or more access card readers.

In another example the security network includes a client system for user interaction with the applications and a communications head end. The communications head end comprises one or more network video recorders one or more door controllers that control access card readers one or more camera controllers that control video cameras an access control and event management server and a database connected to the access control and event management server.

In general according to yet another aspect the invention features a method of operation of a protocol translation system for a security system comprising a security network including multiple network segments security devices connected to the security network on the network segments that communicate information over the security network using communications protocols and a router. The method comprises receiving messages from source security devices in source protocols translating the messages into an intermediate protocol and translating the messages into destination protocols of the destination security devices.

The above and other features of the invention including various novel details of construction and combinations of parts and other advantages will now be more particularly described with reference to the accompanying drawings and pointed out in the claims. It will be understood that the particular method and device embodying the invention are shown by way of illustration and not as a limitation of the invention. The principles and features of this invention may be employed in various and numerous embodiments without departing from the scope of the invention.

Sophisticated security devices typically support two way communications have network interfaces and support one or more standard or proprietary communications protocols. One of the standard communications protocols supported by many sophisticated security devices is Internet Protocol IP . Sophisticated security devices include control panels also known as field panels video cameras one or more network video recorders and one or more door controllers .

Unsophisticated security devices such as fire alarm sensors and access card readers typically support one way communications. They are also known as sensor devices. Sensor devices connect to a receiving device and send unsolicited messages to the receiving device in response to state changes in the sensor devices. The fire alarm sensors connect to the field panels and the access card readers connect to the door controller .

A router also known as a layer 4 transforming router typically connects to each network segment in the security network . The router provides the potential for a security device connected to a network segment to communicate with any other security device connected to a network segment in the security network even despite protocol mismatches.

An applications server connects to at least one of the network segments as the router does. The applications server includes one or more applications . A camera controller controls the video cameras . The door controller controls one or more access card readers . An access control and event management server monitors system events.

A database connected to the access control and event management server saves event data. The network video recorder the door controller the camera controller and the access control and event management server are included in a communications head end .

A client workstation connects to a network segment that is also connected to the applications server such as network segment . Using the client workstation the operator defines parameters for the applications . The applications specify communications sessions between source security devices and destination security devices.

For the applications operators define parameters such as the source security device the destination security device and a requested communications protocol to use for communications with the destination security device. Example communications sessions between source and destination security devices are illustrated in and and will be described in more detail in the description for those figures.

The security network includes network segments that support different physical layers such as shared LAN segments and serial links. Devices utilize interfaces or ports for connecting to the network segments . In the example network segments and are shared LAN segments and the devices that connect to the network segments and utilize Ethernet interfaces . Network segment is a serial link and the devices that connect to network segment utilize USB interfaces .

The application server the client workstation field panels and the video cameras the camera controller the network video controller and the access control and event management server connect to network segment via Ethernet interfaces . Field panel connects to network segment via an Ethernet interface . The door controller connects to network segment via a USB interface .

The router connects to network segment and via an Ethernet interface and to network segment via a USB interface . The router also has a connection to a network cloud . As part of its protocol translation services the router downloads protocol templates from a protocol server within the network cloud .

The protocol templates include a Protocol Identification Template PIT and one or more Data Transform Templates DTT . For this reason the protocol server is also referred to as a DTT PIT server in other figures.

The PIT has one or more entries also known as PIT entries . Each PIT entry defines the format of a specific communications protocol. The router uses the PIT to identify the communications protocols utilized by the security devices specified in the applications . An example PIT entry is displayed in .

The router includes an event subscription service that provides event subscription services. The event subscription service provides network discovery services based on zeroconf and subscription services based on the General Event Notification Architecture GENA . The router also includes a router state engine RSE .

The operator defines parameters for the session in an application running on the application server . The parameters include the source security device the destination security device and a requested communications protocol for communicating with the destination security device.

Using the parameters in the subscribing application the router state engine sets up a control session between field panel and field panel . Once the control session is established the router state engine begins the data session and awaits messages from field panel .

Buffer contains the message from the source security device field panel . In response to receiving messages from the source security device the router state engine must then determine the communications protocol of the message. For this purpose the router state engine creates an inbound transformer software module. The router state engine then downloads the PIT from the protocol server and initializes the inbound transformer with the contents of the PIT .

The PIT contains the full set of all communications protocols supported by the router . The PIT has a PIT entry for each communications protocol that the router supports. Preferably the PIT is in JSON format.

In the preferred embodiment the router performs the message translation by first utilizing the inbound transformer to determine the PIT entry associated with the communications protocol of the source security device. The inbound transformer performs the parsing of the messages at OSI layer 4 comparing OSI layer 3 data of the messages from the source security device with the data fields of each PIT entry in the PIT .

Each PIT entry includes information such as the length and protocol name associated with a message. This allows the router state engine through its transformers to match the message contents to a unique PIT entry to identify the communications protocol associated with the message. The format of a typical PIT entry and more detail associated with PIT entries is provided in the description of .

The PIT entry identifies the overall envelope of the message the communications protocol that contains the message. However the inbound transformer requires more information to interpret the format and contents of the payload the data within the message. At this point the inbound transformer sees the message data only an opaque sequence of bits arranged in octets. This is also known as byte array format.

For interpreting the format and content of the message data each PIT entry also contains a DTT name field that points to the name of a Data Transform Template DTT . Preferably each DTT is in JSON format. The inbound transformer downloads the associated DTT from the protocol server . The format of a typical DTT and more detail associated with DTTs is provided in the description of .

The router performs the next step in the message translation by creating a new protocol or intermediate representation of the message within the router state engine . Using the DTT the inbound transformer creates an Intermediate Data Language IDL object from the message data.

The router performs the next step in the message translation by creating an IDL cache entry associated with the IDL object . The router then serializes the IDL cache entry to non volatile memory to provide persistence of the IDL object associated with the IDL cache entry through router restarts.

The router performs the next step in the message translation by determining if the communications protocol of the source security device and the requested communications protocol for the destination security device are the same communications protocol. If the protocols are the same the router then forwards the received message in buffer directly to the destination security device field panel .

In the example however the communications protocol for the source security device field panel and the requested communications protocol for the destination security device are different communications protocols. As a result the router must transform the message from the format of the source communications protocol to the format of the requested communications protocol before forwarding the message to field panel .

The router performs the next step in the message translation by preferably creating an outbound transformer initialized with contents of the PIT . The outbound transformer selects the PIT entry associated with the requested communications protocol and then downloads the associated DTT pointed to by the DTT name field of the PIT entry from the protocol server .

The outbound transformer then that translates the IDL object to translated messages using the DTTs associated with the requested communications protocol. Then the router buffers the translated messages into buffer and sends the translated messages in buffer to the destination security device field panel .

Session which includes a control session and a data session takes place between a source security device field panel and a destination security device field panel . The router state engine RSE of the router sets up and maintains the control session between the devices. Once the control session is established the router state engine waits to receive messages from the field panel to begin the data session .

The control session begins when the field panel in step sends a connection request to the router state engine to connect to field panel . In response the RSE in step sends a session connection request including the requested communications protocol type for the destination security device. Field panel in step sends a session connection response to the RSE which then sends a connection response in step to the field panel . If the connection is successful the RSE saves the established session parameters in step and waits to receive data from the field panel .

The data session begins when field panel sends message data using the established control session in step . In response the RSE in step creates an inbound transformer initialized with the PIT from the protocol server . In step the RSE through its inbound transformer then determines the PIT entry for the communications protocol of source security device field panel .

In step the inbound transformer determines if message can be forwarded directly to the destination security device. The RSE forwards the message to destination security device without translation. This is because the security devices utilize the same communications protocol in step .

The RSE downloads the DTT associated with the PIT entry for communications protocol of source security device from protocol server in step . In step the RSE transforms the message to the IDL object using the DTT . The RSE creates an IDL cache entry from the IDL object for data mining purposes in step .

Session which includes a control session and a data session takes place between a source security device field panel and a destination security device field panel . The router state engine RSE of the router sets up and maintains the control session between the devices. Once the control session is established the router state engine waits to receive messages from the field panel to begin the data session .

The control session begins when the field panel in step sends a connection request to the router state engine to connect to field panel . In response the RSE in step sends a session connection request including the requested communications protocol for the destination security device. Field panel in step sends a session connection response to the RSE which then sends a connection response in step to the field panel . If the connection is successful the RSE saves the established session parameters in step and waits to receive data from the field panel .

The data session begins when field panel sends message data using the established control session in step . In response the RSE in step creates an inbound transformer initialized with the PIT from the protocol server . In step the RSE through its inbound transformer then determines the PIT entry for the communications protocol of source security device field panel .

In step the inbound transformer determines if message can be forwarded directly to the destination security device. Because the example specified different communications protocols between the source and destination security devices the router must first transform the message into the requested protocol for the destination security device before the router can forward the message to the destination security device.

To start the transformation in step the RSE downloads the DTT associated with the PIT entry for the communications protocol of the source security device from protocol server . In step the RSE transforms the message to the IDL object using the DTT .

In step the RSE creates an outbound transformer initialized with the PIT from the protocol server . In step the RSE downloads the DTT associated with the PIT entry for the requested communications protocol of the destination security device from the protocol server .

In step the RSE transforms the IDL object into a translated message for requested communications protocol of destination security device using the DTT . In step the RSE forwards the translated message to the destination security device field panel . In step the RSE creates an IDL cache entry from the IDL object for data mining purposes.

In step the inbound transformer determines if there is a PIT entry match. If no match occurs the inbound transformer proceeds to step where the inbound transformer sends an error for unknown source communications protocol to the application server . If a match occurs the inbound transformer proceeds to step to use protocol type of matched PIT entry to identify the communications protocol of the source security device.

In step the inbound transformer of the RSE compares the communications protocol of the source security device and the requested protocol for the destination security device. In step the inbound transformer determines if the communications protocols are the same. If the protocols are the same the inbound transformer proceeds to step and saves information indicating that source and destination security devices use the same communications protocol. If the protocols are not the same the inbound transformer proceeds to step and saves information indicating that source and destination security devices do not use the same communications protocol.

Each PIT entry in the PIT includes the following fields protocol type protocol name byte array offset length a content array and a DTT name that points to the protocol name of the associated DTT .

In the preferred embodiment the inbound transformer determines the PIT entry associated with the communications protocol of the source security device at OSI layer 4 by comparing OSI layer 3 data of the messages from the source security device with the byte array offset length and content array of each PIT entry in the PIT .

DTTs typically define the message and data format for communications protocols. In other examples DTTs define individual actions or instruction within a protocol.

Each DTT includes the following fields protocol type protocol name protocol type mask byte array offset and length .

The transformers map each field within the DTT to the byte array of the message data using the byte array offset and length fields. The protocol type field is an enumeration of supported types defined in the DTT framework. The protocol type also supports bit references within a byte using the protocol type mask field. This allows the protocol associated with the DTT to take advantage of bit level Boolean values.

In one example the IDL cache entry includes the following fields a name a value a data ID and a timestamp ID . The value field contains the data from the associated IDL object . The data ID field utilizes a globally unique identifier GUID to act as a primary key for the data in the value field. The same GUID used in the data ID field is also included as part of the contents of the timestamp ID field.

While this invention has been particularly shown and described with references to preferred embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the scope of the invention encompassed by the appended claims.

