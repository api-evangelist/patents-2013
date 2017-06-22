---

title: Multicast transmission using a unicast protocol
abstract: Method for multicast transmission between a server and at least one of a plurality of clients using a unicast protocol, said method comprising a step of providing by the server to the client information permitting to said client to communicate with the server over a multicast path, in order to enable a joint operation of multicast and unicast paths between the server and the client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09425975&OS=09425975&RS=09425975
owner: Thomson Licensing
number: 09425975
owner_city: Issy-les-Moulineaux
owner_country: FR
publication_date: 20130710
---
This application claims the benefit under 35 U.S.C. 119 of European Application 12305835.6 filed 12 Jul. 2012.

The present invention generally relates to the field of transport layer protocols used for transporting information within a network.

More particularly the invention deals with the Stream Control Transport Protocol known as SCTP which is standardized by the Internet Engineering Task Force IETF in IETF RFC 4960.

Thus the invention concerns a method a client and a server for multicast transmission using a unicast protocol. It also concerns a computer program implementing the method of the invention.

The approaches described in this section could be pursued but are not necessarily approaches that have been previously conceived or pursued. Therefore unless otherwise indicated herein the approaches described in this section are not prior art to the claims in this application and are not admitted to be prior art by inclusion in this section.

The Stream Control Transmission Protocol SCTP is a general purpose transport layer protocol providing a service similar to TCP Transmission Control Protocol plus a set of advanced features to use the enhanced capabilities of modern IP Internet Protocol networks and to support increased application requirements. Nowadays there are SCTP implementations for all major operating systems.

The SCTP protocol as specified by the IETF is used in 3GPP 3rd Generation Partnership Project for transporting signalling information within a cellular core network. SCTP was designed to address certain limitations inherent to TCP for the transport of signalling for telephony over IP. One of the main design goals of SCTP was the efficient transport of small messages in a network fault tolerant way important for transporting signalling messages. Thus SCTP provides a reliable data transmission service for the transport of service messages to applications users.

SCTP is a connection oriented general purpose transport protocol that preserves message boundaries. An SCTP connection called an SCTP association can be used on top of IPv4 and IPv6.

The messages are encapsulated in data structures called chunks. The chunks are themselves encapsulated in SCTP packets. Moreover SCTP incorporates several new features that are not available in TCP.

One of the most important enhancements provided by SCTP over traditional transport layer protocols is multihoming. This multihoming feature allows an SCTP association to use several source and destination addresses. Then each node can be accessed by several addresses set at the establishment of the association. The addresses of transport are exchanged during the initialization of an SCTP association.

The multihoming feature was used up to now as a way to provide reliability. Whenever a primary path between a source and a destination fails the SCTP association remains as traffic can continue to flow over one of the secondary paths.

Recently it has been proposed to use concurrently the different available connection paths allowed by SCTP in such a way that the overall bandwidth is increased inherently enhancing mobility management.

Besides the above described default TCP like behaviour SCTP supports also non acknowledged traffic UDP User Datagram Protocol like in an extension named SCTP PR SCTP Partial reliability specified in RFC 3758.

In an article by F. Yong W. Chee and S. Ramadass entitled M SCTP transport layer multicasting protocol in National Computer Science Postgraduate Colloquium NaCSPC 2005 a scheme that utilizes multicast SCTP M SCTP is described. The scheme adds an M SCTP server stack between an SCTP server and its SCTP clients. The server stack manages the resources of a multicast service and controls multicast membership. However the scheme achieves multicast capability by using recursive unicast protocol message transmissions. In other words multicast is realized by the server stack by duplicating data packets and sending them to each client individually using multiple unicast protocol message transmissions. Thus the scheme does not solve problems stemming from low bandwidth efficiency or poor system scalability.

The document WO2011 071474 evokes the advantages of a scheme allowing the adding of a multicast support to SCTP.

The idea is to operate the SCTP transport protocol in a multicast environment whereas as explained in the previous paragraphs SCTP has been primarily designed for unicast TCP UDP like connections.

There are numerous cases and in particular when considering video distribution where it is interesting to beneficiate from multicasting and or broadcasting. However it is common to associate with a broadcast medium a bi directional medium for robustness service continuity etc. Today it is up to the application to deal with different media and their characteristics such as unicast or multicast.

The prior art consisting only in multicast over UDP addresses the case of a source as a streaming server for example distributing a stream to multiple destinations over a shared communication link but does not permit concurrent use of multiple links to achieve distribution of such multicast content.

The above cited document WO2011 071474 does not provide the changes to the SCTP protocol to achieve such a multicast transmission.

Accordingly the present invention provides a method for multicast transmission between a server and at least one of a plurality of clients using a unicast protocol said method comprising a step of providing by the server to the client information permitting to said client to communicate with the server over a multicast path in order to enable a joint operation of multicast and unicast paths between the server and the client.

By providing from the server to the client information permitting to said client to communicate with the server over a multicast path the method of the present invention enables to use both unicast and multicast paths jointly or alternatively.

Preferably the multihoming protocol is the Stream Control Transmission Protocol SCTP or an extension of SCTP.

Advantageously in the case of SCTP the information permitting to the client to communicate with the server over the multicast path comprise initialization information permitting to initialize an SCTP association.

With the present invention it is then possible to design a multicast SCTP service where concurrent IP multicast bearers associated with IP unicast bearers are used.

According to a first embodiment the initialization information is carried in an initialization chunk broadcast over the multicast path regularly.

Advantageously the initialization chunk comprises a field advertising a number of outbound streams carried by the SCTP association.

More particularly the broadcast initialization chunk comprises a set of IPv4 IPv6 addresses by which the server may be contacted. These addresses may include other possible multicast bearers.

According to a second embodiment the initialization information are described in a file made available to the client.

For example such a file may be a SDP file made available to the client by any possible means for example as part of a service guide or may be pre loaded by a network operator.

Advantageously the method comprises a step carried by the client of initialization of an SCTP association.

The invention further provides a server able to communicate with at least one of a plurality of clients using a unicast protocol said server comprising a management module for providing to the client information permitting to said client to communicate with the server over a multicast path in order to enable a joint operation of multicast and unicast paths between the server and the client.

The present invention also provides a client able to communicate with a server using a unicast protocol said client comprising a receiver module for receiving information permitting to said client to communicate with the server over a multicast path in order to enable a joint operation of multicast and unicast paths between the server and the client.

The method for multicast transmission according to the invention may be implemented in software on a programmable apparatus. It may be implemented solely in hardware or in software or in a combination thereof.

Since the present invention can be implemented in software the present invention can be embodied as computer readable code for provision to a programmable apparatus on any suitable carrier medium. A carrier medium may comprise a storage medium such as a floppy disk a CD ROM a hard disk drive a magnetic tape device or a solid state memory device and the like.

The invention thus provides a computer readable program comprising computer executable instructions to enable a computer to perform the steps of the method of the invention. The diagram of illustrates an example of the general algorithm for such computer program.

Referring to there is shown therein a schematic view of a transmission system using a multihoming unicast protocol more particularly SCTP according to an embodiment of the invention.

The transmission system comprises a server containing an SCTP management module a first client and a second client containing receiver modules respectively. Although depicts two clients the system is not limited to operation with two clients and may support from one to a plurality of clients.

The server includes a storage medium comprising content to be delivered to the client . Advantageously the server maintains client state or profile information allowing it to track client devices characteristics such as for instance playback capability screen resolution and whether the client has established a unicast connection in addition to the multicast connection. Accordingly this state information can be used to selectively add targeted content for some of the clients as for example a different sound track or an enhanced quality.

Each individual client may include several IP addresses used for exchanging data packets with the server . The IP addresses of an individual client are used to create communication paths with IP addresses of the server to facilitate the exchange of data packets between an individual client and the server . The server may also form communication paths with the individual clients through multiple access networks.

For example as shown in the server can communicate with the clients through unicast access paths respectively which correspond for instance to a 3generation partnership project 3GPP Unicast network.

According to the present invention the server can also communicate with the clients through multicast access paths which correspond for instance to a 3GPP Multimedia Broadcast and Multicast Services MBMS network and a Digital Video Broadcasting Handheld DVB H network respectively.

An SCTP protocol stack residing in the server handles the multicast association between the server and the clients registering new client addresses whenever the clients add their unicast addresses to the association. It sends data chunks to the clients over the multicast connection and uses unicast connections towards individual clients to deliver data selectively or retransmit data when explicitly requested by the clients .

Although depicts three access networks the system is not limited to operation with three access networks and may support connection paths between the server and one to a plurality of access networks supporting either unicast or multicast data transmission.

The unicast paths provide unicast communication support capability with bi directional uplinks and downlinks between server and each respective client .

The multicast paths only support uni directional downlinks. As a result no feedback channels from a respective client to the server are available through multicast paths .

The clients may also have multiple network interfaces and be able to connect with a remote system via different types of communication networks. Specifically the clients may connect to a remote system through all three of the aforementioned access networks and thus have both unicast bi directional and multicast uni directional links.

Each client may be a hardware device for example a computer or a mobile device capable of processing data files running applications and communicating with the server for instructions on transmitting receiving and processing of data.

The clients may require content from the server in order to be able to perform a specific function. For example the client may be an audio video device that must receive specific data from the server in order to properly process and display the data for a user. Thus associations between the clients and the server are required in order to facilitate transmission of data.

According to the present invention a hybrid multicast unicast transmission is handled by the SCTP layer i.e. the SCTP protocol stack .

Interfaces consisting for instance in slightly enhanced socket Application Programming Interfaces API are used on the server the client and the client sides respectively to read out and modify the association parameters. The enhanced socket API allow reading a list of clients having established a unicast connection.

The association between the server and the client is either initiated by the server through its multilink side or by the client through the uplink path .

A SCTP association is initiated through a conventional four ways handshake. Of course this connection set up can only be used by a client when an uplink path as paths is available.

According to a first embodiment of the present invention this association uses an initialization chunk called BINIT different from the INIT chunk defined in RFC 4960. This chunk is broadcast over the multicast path regularly and advertises the number of outbound streams carried by the SCTP association.

The BINIT chunk comprises the following conventional fields of the INIT chunk of an SCTP association 

Besides the BINIT chunk contains a new field according to the first embodiment of the invention. The new field contains the number of outbound streams carried by the association and is coded identically to the Number or Outbound Streams field found in the INIT chunk. Its value allows the client joining the association to know how many streams are part of the association as this information is normally not advertised any further once the association has been established.

In case of uplink possibility as here with the unicast paths the client shall wait for the BINIT chunk and uses at step the Initiate tag value as the Verification tag value in an INIT chunk starting the subsequent four ways handshake. The server processing the incoming INIT chunk detects the non null Verification tag which indicates that the client is not attempting to setup a new legacy SCTP association. Instead the received Verification Tag value allows the server to identify the multicast SCTP association that the client wishes to join using his bidirectional path. After having processed the remainder of the four way handshake with the client the server s SCTP protocol stack will have integrated the client s IP address into the existing multicast association.

The server indicates in its BINIT chunk and possible subsequent INIT ACK chunk s at step through the optional field the set of IPv4 IPv6 addresses it supports and the list of multicast addresses used on multicast paths . The addresses are encoded as for INIT chunks as per RFC 4960.

According to a second embodiment of the invention the characteristics of the association are described in a SDP file. This file is made available to the client by any possible means for example as part of a service guide or pre loaded by a network operator.

A different mechanism is used in case the client wishes to initiate an uplink connection. Indeed the server sets the Verification Tag of all chunks sent over the multicast link to a fixed value which is chosen here upon initialization of the association by the server. The client sends an INIT chunk with the Verification Tag set to the value of the Verification Tag found in the chunks received over the multicast link . This indicates to the server that the client wishes to add this unicast link to the existing association and not to initiate a new association. The Initiate Tag is set to a value chosen by the client as in the conventional SCTP handshake. The server replies with an INIT ACK chunk with the Verification Tag set to the value of the Initiate Tag provided by the client .

From the server viewpoint the application opens a one to many SCTP socket. However when creating the socket the SOCK DGRAM type is used instead of the conventional SOCK SEQPACKET. This indicates the de facto non connected nature of the underlying connection. This indicates also to the SCTP protocol stack that potential point to point associations might be set up.

It is then up to the SCTP protocol stack to generate the BINIT chunks and start distributing traffic over the multicast paths .

From the client viewpoint the application creates a one to many SCTP socket as well with the SOCK DGRAM type. The client programming model looks like a conventional multicast receiver. It calls the standard setsockopt function from the socket API with IP ADD MEMBERSHIP option for handling IGMP. Then the client binds the socket with a particular multicast capable interface and waits incoming packets.

It is then up to the SCTP protocol stack to listen the corresponding multicast traffic and to create a new unicast association with the source SCTP end point if possible.

From the client viewpoint the traffic is read from the SCTP socket as with a normal socket. Having an additional uplink gives the possibility to the SCTP socket to request the retransmission of missing packets transparently for the client .

In the specific use case of where more than one multicast distribution mechanism exist as for example DVB H and MBMS it is possible to add a multicast path a posteriori through the socket API.

Remarkably the invention integrates downstream multicast distribution and optional bi directional unicast links at the transport layer. Legacy applications leveraging multicast UDP can be reused with almost no modifications. Large numbers of clients can receive a multicast stream without flooding the distribution network because replication of the data is avoided when multicast is supported by the network. Additional bi directional unicast links can be established by the clients transparently for the applications that can be used to enhance user experience due to additional bandwidth or to guarantee service continuity in areas where multicast is not available due to the network coverage.

While there has been illustrated and described what are presently considered to be the preferred embodiments of the present invention it will be understood by those skilled in the art that various other modifications may be made and equivalents may be substituted without departing from the true scope of the present invention. Additionally many modifications may be made to adapt a particular situation to the teachings of the present invention without departing from the central inventive concept described herein. Furthermore an embodiment of the present invention may not include all of the features described above. Therefore it is intended that the present invention not be limited to the particular embodiments disclosed but that the invention includes all embodiments falling within the scope of the appended claims.

Expressions such as comprise include incorporate contain is and have are to be construed in a non exclusive manner when interpreting the description and its associated claims namely construed to allow for other items or components which are not explicitly defined also to be present. Reference to the singular is also to be construed to be a reference to the plural and vice versa.

A person skilled in the art will readily appreciate that various parameters disclosed in the description may be modified and that various embodiments disclosed and or claimed may be combined without departing from the scope of the invention.

