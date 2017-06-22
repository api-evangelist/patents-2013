---

title: Device and method for supporting internet-based sensor data transmission
abstract: Provided is a method of supporting CoAP-based sensor data transmission between a sensor data collector in a sensor node relay and one or more 6LoWPAN-unsupported sensor nodes. The method includes receiving a CoAP sensor data request message from the sensor data collector, transmitting a CoAP sensor data request message to a corresponding 6LoWPAN-unsupported sensor node by analyzing the received CoAP sensor data request message, and responding to the sensor data collector by creating a CoAP sensor data response message including sensor data received from one or more of the 6LoWPAN-unsupported sensor nodes.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09154544&OS=09154544&RS=09154544
owner: Electronics and Telecommunications Research Institute
number: 09154544
owner_city: Daejeon
owner_country: KR
publication_date: 20130624
---
This application claims the benefit under 35 U.S.C. 119 a of Korean Patent Application No. 10 2013 0003541 filed on Jan. 11 2013 the entire disclosure of which is incorporated herein by reference for all purposes.

The following description relates to a device and method for supporting sensor node data transmission and more particularly to a device and method for supporting sensor data transmission using a CoAP protocol in a sensor node which does not use a TCP IP based 6LoWPAN.

An IPv6 over low power wireless personal area networks 6LoWPAN is a communication technology for building a TCP IP based sensor network and it is being standardized by the Internet Engineering Task Force IETF organization.

When this 6LoWPAN technology is incorporated into a sensor network it is possible to develop a variety of applications with ease according to convergence with existing Internet based technologies. A CoAP a type of the 6LoWPAN technology has an advantage in that RESTful services can be extensively applied by integration with the Internet web.

However a plurality of sensor nodes installed in the field have a minimum specification required to acquire and transmit sensor data and interfaces having a high probability of delay and loss for example a serial communication RS485 CAN and ZigBee which have a relatively low speed other than the Ethernet or WiFi which can easily apply the 6LoWPAN technology are used. Therefore it is currently difficult to apply the 6LoWPAN technology to all sensor nodes.

The following description relates to applying a RESTful based application service in an integrated manner between a 6LoWPAN supported sensor network and a 6LoWPAN unsupported sensor network by enabling communication using a CoAP protocol in common in a sensor network.

In one general aspect there is provided a device which includes a connecting unit that can access the Internet through a sensor node relay and transmits and receives an Internet based message to and from a sensor data collector an interface to connect one or more Internet unsupported sensor nodes a request processing unit that transmits a sensor data request message to one or more of the Internet unsupported sensor nodes through the interface by analyzing the CoAP sensor data request message received from the sensor data collector through the connecting unit and a response processing unit that creates a sensor data response message including sensor data received from one or more of the Internet unsupported sensor nodes through the interface and transmits it to the sensor data collector through the connecting unit.

In another aspect there is provided a method of supporting Internet based sensor data transmission between a sensor data collector in a sensor node relay and one or more Internet unsupported sensor nodes the method including receiving a sensor data request message from the sensor data collector transmitting a sensor data request message to a corresponding Internet unsupported sensor node by analyzing the received sensor data request message and responding to the sensor data collector by creating a sensor data response message including sensor data received from one or more of the Internet unsupported sensor nodes.

Other features and aspects will be apparent from the following detailed description the drawings and the claims.

Throughout the drawings and the detailed description unless otherwise described the same drawing reference numerals will be understood to refer to the same elements features and structures. The relative size and depiction of these elements may be exaggerated for clarity illustration and convenience.

The following description is provided to assist the reader in gaining a comprehensive understanding of the methods apparatuses and or systems described herein. Accordingly various changes modifications and equivalents of the methods apparatuses and or systems described herein will suggest themselves to those of ordinary skill in the art. Also descriptions of well known functions and constructions may be omitted for increased clarity and conciseness.

Hereinafter exemplary embodiments of the invention will be described in detail with reference to the accompanying drawings. The exemplary embodiments described below should be considered in a descriptive sense only in order to facilitate understanding of the invention and the scope of the invention is not limited by the exemplary embodiments.

As illustrated in sensor nodes may be classified into a 6LoWPAN sensor node and 6LoWPAN unsupported sensor nodes . . . and 

The 6LoWPAN sensor node may transmit and receive sensor data using a CoAP protocol in a TCP IP based network. The 6LoWPAN unsupported sensor nodes . . . and may not transmit and receive sensor data using the CoAP protocol in the TCP IP based network but may transmit and receive sensor data using a serial a RS485 and a ZigBee communication method.

The sensor data collector and the 6LoWPAN sensor node exchange sensor data over the Internet using the CoAP protocol of the 6LoWPAN.

The sensor data collector and 6LoWPAN unsupported sensor nodes . . . and may not exchange sensor data over the Internet using the CoAP protocol of the 6LoWPAN.

However the 6LoWPAN unsupported sensor node which is directly connected to the sensor data collector using the serial RS485 or ZigBee may transmit and receive sensor data using the serial RS485 or ZigBee method for sensor data transmission.

However the 6LoWPAN unsupported sensor nodes . . . and which are connected to the sensor data collector over the Internet may not independently transmit sensor data to the sensor data collector . Accordingly a sensor node relay is provided in order to transform and transmit the sensor data between the sensor data collector and the 6LoWPAN unsupported sensor nodes . . . and 

A specific configuration for relaying transmission and reception of the sensor data between the sensor data collector and the 6LoWPAN unsupported sensor nodes . . . and will be described.

The sensor node relay may have two embodiments based on a CoAP URL configuration of a CoAP sensor data request message. That is in order to clearly identify each sensor node when the sensor data collector requests data on an individual sensor node it is necessary to add information on the sensor node in the CoAP URL which represents header content of the CoAP sensor data request message as general text.

In one general aspect only path information is included in the CoAP URL. In this case the sensor node relay determines an interface to connect the sensor node and a sensor node ID corresponding to the path information of the CoAP URL and transmits a sensor data request message to the corresponding sensor node through a determined interface. A detailed description of this procedure will be provided below with reference to .

In another aspect a corresponding sensor node ID and an interface are explicitly represented in the CoAP URL. In this case the sensor node relay transmits a sensor data request message to the corresponding sensor node through the interface which is explicitly indicated in the CoAP URL. A detailed description of this procedure will be given below with reference to .

As illustrated in a sensor node relay specifically includes a connecting unit a request processing unit an interface a sensor node management unit and a response processing unit .

The connecting unit can access the TCP IP based Internet and transmits and receives a CoAP based message to and from the sensor data collector .

The request processing unit analyzes the CoAP sensor data request message received from the sensor data collector through the connecting unit . For example the URL of the CoAP sensor data request message may include only path information temp for example coap temp. Then the request processing unit inputs this path information temp to the sensor node management unit .

However in order to reduce its size the header of the CoAP protocol message does not use the same information contained in headers of its upper layers. Therefore information on size of the CoAP message is obtained in a TCP or UDP header and ID information of both nodes that transmit and receive the CoAP message is obtained in an IP header. However since the 6LoWPAN unsupported sensor node which does not use the TCP IP stack may not obtain the TCP or UDP header and the IP header the request processing unit needs to define a shim header including associated information and transmits the shim header attached above the CoAP header. A detailed description of the shim header will be given below with reference to .

Since the sensor node management unit includes sensor node ID information matching information on each path it detects a sensor node ID based on input path information and transmits the CoAP sensor data request message through the interface in order to connect to the sensor node corresponding to the ID.

As illustrated in a case in which a noise sensor and a temperature sensor which are the 6LoWPAN unsupported sensor nodes and satisfy specifications in Table 1 are connected to the sensor node relay will be taken as an example.

When URL coap temp is included in the CoAP sensor data request message the sensor node management unit recognizes that sensor data of the temperature sensor having a sensor node ID 0002 is requested from the temp value connects to the temperature sensor through a serial interface and transmits the CoAP sensor data request message.

The response processing unit allows the CoAP sensor data response message including sensor data received from the sensor nodes and to be transmitted to the sensor data collector through the connecting unit . At this time the response processing unit removes the shim header from the CoAP sensor data response message.

As illustrated in the sensor node relay specifically includes a connecting unit a request processing unit an interface and a response processing unit .

The connecting unit can access the TCP IP based Internet and transmits and receives a CoAP based message to and from the sensor data collector .

The request processing unit analyzes the CoAP sensor data request message received from the sensor data collector through the connecting unit . The URL of the CoAP sensor data request message may include a sensor node ID 0001 an interface serial and path information temp for example coap 0001.serial temp. 

Then the request processing unit transmits the CoAP sensor data request message through the interface in order to connect to the sensor node corresponding to the sensor node ID included in the URL. However in order to reduce its size the header of the CoAP protocol message does not use the same information contained in headers of its upper layers. Therefore information on the size of the CoAP message is obtained from the TCP or UDP header and ID information of both nodes that transmit and receive the CoAP message is obtained from the IP header. However since the 6LoWPAN unsupported sensor node which does not use the TCP IP stack may not obtain the TCP or UDP header and the IP header the response processing unit needs to define a shim header including associated information and transmits the shim header attached above the CoAP header. A detailed description of the shim header will be provided below with reference to .

The response processing unit allows the CoAP sensor data response message including sensor data received from the sensor nodes and to be transmitted to the sensor data collector through the connecting unit . At this time the response processing unit removes the shim header from the CoAP sensor data response message.

One aspect of a sensor node relay configured according to the present invention has been described but the sensor node relay configured according to the present invention may also be applied to the sensor data collector.

As an embodiment as illustrated in the format may be defined and used as for example a preamble indicating start of the shim header version information on the shim header length information on the CoAP message and sender and receiver IDs of the CoAP message.

As another embodiment as illustrated in when the size of the CoAP message is too large to be represented in the CoAP message length field of the shim header the field may be filled with 0 values and information on the size of the CoAP message may be inserted into the CoAP message extension length field which is larger than the CoAP message length field.

As still another embodiment as illustrated in when a sender or a receiver address of the CoAP message is known in advance for example a one to one connection interface it is possible to define and use a format representing only the other node address and not the known address.

As illustrated in the sensor node relay receives the CoAP sensor data request message from the sensor data collector in operation . However in order to clearly identify each sensor node when the sensor data collector requests data on an individual sensor node it is necessary to add information on the sensor node into the CoAP URL representing header content of the CoAP sensor data request message as general text.

Then the sensor node relay analyzes the CoAP sensor data request message in operation and requests sensor data from a corresponding sensor node in operation . However in order to reduce its size the header of the CoAP protocol message does not use the same information contained in headers of its upper layers. Therefore information on size of the CoAP message is obtained from the TCP or UDP header and ID information of both nodes that transmit and receive the CoAP message is obtained from the IP header. However since the 6LoWPAN unsupported sensor node which does not use the TCP IP stack may not obtain the TCP or UDP header and the IP header it needs to define a shim header including associated information and transmits the shim header attached above the CoAP header. A detailed description of the shim header has been given above with reference to and will not be repeated.

Two examples of operations and based on a CoAP URL configuration of a CoAP sensor data request message will now be described.

In one example only path information is included in the CoAP URL. In this case the sensor node relay determines a sensor node ID corresponding to the path information of the CoAP URL and an interface to connect the sensor node and transmits a sensor data request message to the corresponding sensor node through a determined interface. For example the URL of the CoAP sensor data request message may include only path information temp for example coap temp. Then since the sensor node relay detects the path information temp and has sensor node ID information on matching each path information it detects a sensor node ID based on input path information and transmits the CoAP sensor data request message through the interface in order to connect to the sensor node corresponding to the ID.

In another example a corresponding sensor node ID and an interface are explicitly represented in the CoAP URL. In this case the sensor node relay transmits a sensor data request message to a corresponding sensor node through the interface which is explicitly represented in the CoAP URL. For example the URL of the CoAP sensor data request message may include a sensor node ID 0001 an interface serial and path information temp for example coap 0001.serial temp. Then the sensor node relay transmits the CoAP sensor data request message through the interface in order to connect to the sensor node corresponding to the sensor node ID included in the URL.

The sensor node relay receives sensor data from the sensor node in operation and then transmits the CoAP sensor data response message to the sensor data collector in operation . At this time the sensor node relay removes the shim header from the CoAP sensor data response message.

The exemplary embodiments should be considered in a descriptive sense only. It will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the invention. Therefore the invention is not limited to the above mentioned embodiments and encompasses all modifications and equivalents that fall within the scope of the appended claims and their equivalents.

The present invention can be implemented as computer readable code in a computer readable recording medium. The computer readable recording medium includes all types of recording media in which computer readable data are stored. Examples of the computer readable recording medium include a ROM a RAM a CD ROM a magnetic tape a floppy disk and an optical data storage. Further the recording medium may be implemented in the form of carrier waves such as those used in Internet transmission. In addition the computer readable recording medium may be distributed among computer systems over a network such that computer readable codes may be stored and executed in a distributed manner.

A number of examples have been described above. Nevertheless it will be understood that various modifications may be made. For example suitable results may be achieved if the described techniques are performed in a different order and or if components in a described system architecture device or circuit are combined in a different manner and or replaced or supplemented by other components or their equivalents. Accordingly other implementations are within the scope of the following claims.

