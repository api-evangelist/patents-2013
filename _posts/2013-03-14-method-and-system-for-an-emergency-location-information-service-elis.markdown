---

title: Method and system for an emergency location information service (E-LIS)
abstract: A method and system for determining and verifying a location of mobile and non-mobile devices in emergency situations. The method and system provide a current physical geographic location for a mobile device (e.g., building address, a building floor, a room on a building floor, campus, enterprise, city, state, region, country, continent, etc.), in an emergency situation such as an accident, fire, terrorist attack, military incident, etc. and forward the physical geographic location to a legacy 911 network or a Emergency Services IP networks (ESInet).
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08755767&OS=08755767&RS=08755767
owner: Redsky Technologies, Inc.
number: 08755767
owner_city: Chicago
owner_country: US
publication_date: 20130314
---
This is a Continuation In Part CIP of U.S. utility patent application Ser. No. 13 098 981 filed May 2 2011 which is a CIP of U.S. utility patent application Ser. No. 11 803 671 filed May 15 2007 which is an application claims priority to U.S. Provisional patent applications 60 800 774 60 800 775 60 800 776 and 60 800 777 all filed May 16 2006 Ser. No. 11 803 671 which issued as U.S. Pat. No. 7 937 067 on May 3 2011 AND is also a CIP of U.S. utility application Ser. No. 12 844 972 filed Jul. 28 2010 which is an application claiming priority to U.S. Provisional patent applications Nos. 61 229 414 filed Jul. 29 2009 and 61 230 154 filed Jul. 31 2009 the contents of all of these cited applications and issued patents are incorporated herein by reference.

This application relates to automatic processing of location information. More specifically it relates to a method and system for an emergency location information service.

In many emergency situations it is of great importance to be able to quickly and accurately locate individuals within a large building. For example in the event of a fire public safety personnel may need to operate within an unfamiliar building on short notice in conditions of poor visibility due to smoke or flame. Accurate location information is vital to coordinate rescue operations and ensure the safety of firefighters. Police or military personnel may be faced with similar circumstances in which accurate and timely location information can help avoid friendly fire incidents and coordinate action against a criminal or enemy force.

Individuals faced with an emergency involving immediate danger to life or health of themselves or a colleague need to be able to accurately provide their location to emergency rescue personnel preferably without human intervention to enable rescue in the case where the individual in need is incapacitated or all attention must be devoted to his her protection. In all these circumstances rapid and automated acquisition of the location of an individual to within a few meters within a large building can be critical in saving lives.

Prior art methods of accomplishing such location do not simultaneously meet the requirements of rapid location determination automation and accuracy. Navigation employing conventional maps and visual observation or dead reckoning are not readily automated and thus require time and attention by a human observer. Manual navigation may be vitiated in the case where visibility is impacted by flame or smoke or where personnel are under hostile fire and unable to establish their location by patient observation.

Enhanced 911 E911 is a location technology that enables mobile or cellular phones and other mobile device such personal digital data assistants PDAs to process 911 emergency calls and enable emergency services to locate a physical geographic position of the device and thus the caller. When a person makes a 911 call using a traditional phone with wires the call is routed to the nearest public safety answering point PSAP that then distributes the emergency call to the proper emergency services. The PSAP receives the caller s phone number and the exact location of the phone from which the call was made. Prior to 1996 911 callers using a mobile phone would have to access their service providers in order to get verification of subscription service before the call was routed to a PSAP. In 1996 the Federal Communications Commission FCC ruled that a 911 call must go directly to the PSAP without receiving verification of service from a specific cellular service provider. The call must be handled by any available service carrier even if it is not the cellular phone customer s specific carrier.

The FCC has rolled out E911 in two phases. In 1998 Phase I required that mobile phone carriers identify the originating call s phone number and the location of the signal tower or cell accurate to within a mile. In 2001 Phase II required that each mobile phone company doing business in the United States must offer either handset or network based location detection capability so that the caller s location is determined by the geographic location of the cellular phone within 100 meter accuracy and not the location of the tower that is transmitting its signal. The FCC refers to this as Automatic Location Identification ALI .

There are many problems associated with determining a location of device and a caller who needs to place an E911 call in an emergency. On problem is that many E911 calls a misrouted to the wrong PSAP. This can delay the dispatch of emergencies services to the caller. Another problem is that existing mobile technology makes its difficult to accurately locate mobile devices.

Another problem is that triangulation based on time of arrival at multiple mobile communications base stations TDOA has inadequate coverage and is insufficiently accurate unless supplemented by signals provided by local radios placed outside the facility by public safety personnel.

Another problem is that conventional radio frequency based location methods do a poor job of providing topological location within a building that is location relative to walls doors partitions stairways and other features whose spatial extent is small but whose significance to a person s ability to move is great.

Another problem is that many mobile devices are not location aware. Location aware devices are aware of their current geographic location. Mobile telephones and Global Positioning System GPS devices may be aware of their current geographic location. GPS devices typically determine their current geographic location by communicating with satellites. However mobile telephones may only determine their current geographic location by communicating with a particular mobile phone interface or telephony switch that provides coverage to a geographic location such as a telephony cell but not an exact current geographic location within the cell.

Thus there exists a critical need for a method of locating individuals making an E911 call that is rapid automated accurate simple and inexpensive to employ and does not require manual intervention from the person to be located.

In accordance with preferred embodiments of the invention some of the problems associated with locating E911 and other callers are overcome.

A method and system for determining and verifying a location of mobile devices in emergency situations is presented. The method and system provide a current physical geographic location for a mobile device e.g. building address a building floor a room on a building floor campus enterprise city state region country continent etc. in an emergency situation such as an accident fire terrorist attack military incident etc. and forward the physical geographic location to a legacy 911 network or a Emergency Services IP networks ESInet .

The foregoing and other features and advantages of preferred embodiments of the present invention will be more readily apparent from the following detailed description. The detailed description proceeds with references to the accompanying drawings.

In one embodiment the target network devices are smart devices. A smart device is aware of its location in X Y Z space or X Y Z geo space. In another embodiment the target network device are dumb device. A dumb device is not aware of its location in geo space. A dumb device is typically in contact with proxy server device that is aware of the dumb device s location in geo space.

In one specific exemplary embodiment the one or more target network devices also include smart phones such as the iPhone by Apple Inc. Blackberry Storm and other Blackberry models by Research In Motion Inc. RIM Droid by Motorola Inc. HTC Inc. other types of smart phones other types of mobile and non mobile phones etc. However the present invention is not limited to such devices and more fewer or other types of smart phones can be used to practice the invention.

A smart phone is a mobile phone that offers more advanced computing ability and connectivity than a contemporary basic feature phone. Smart phones and feature phones may be thought of as handheld computers integrated with a mobile telephone but while most feature phones are able to run applications based on platforms such as Java ME a smart phone usually allows the user to install and run more advanced applications. Smart phones and or tablet computers run complete operating system software providing a platform for application developers assessable trough a specialized Application Programming Interface API .

The operating systems include the iPhone OS Android Windows etc. iPhone OS is a proprietary operating system for the Apple iPhone. Android is an open source operating system platform backed by Google along with major hardware and software developers such as Intel HTC ARM Motorola and Samsung etc. that form the Open Handset Alliance.

The one or more target network devices also include tablet computers such as the iPad by Apple Inc. the HP Tablet by Hewlett Packard Inc. the Playbook by RIM Inc. the Tablet by Sony Inc.

In one embodiment the one or more target network devices include an internal accelerometer. An accelerometer is a device that measures an acceleration of the device and a change of velocity of the target network devices. Many smart phones digital audio players and personal digital assistants contain accelerometers for user interface control often the accelerometer is used to present landscape or portrait views of the device s screen based on the way the device is being held. The accelerometer can be used to detect crash strength G forces and automatically translate and provide location 3D X Y Z geo space into a current physical location fir emergency response personal.

In one embodiment the one or more target network devices include an internal hardware temperature sensor that indicates when the device has exceeded a certain pre determined temperature. This internal temperature sensor is used with a corresponding to detect emergency events such as fires weather events etc. that include a dramatic change in temperature. In one embodiment the temperature sensor include and Infrared temperature sensor. However the present invention is not limited to such embodiments and other types of internal and external temperature sensors can also be used to practice the invention.

In another embodiment the one or more target network devices include an external device that is plugged into a target network device that include an integration of a variety of motion magnetic pressure and temperature sensors with a processing unit and dedicated smart device application software to provide location information when an emergency event is detected via the motion magnetic pressure and or temperature sensors.

The network devices include an application . In one embodiment the application is a software application. However the present invention is not limited to this embodiment and the application can be firmware hardware or a combination thereof. In one embodiment the application exists only on the target network devices . In another embodiment application exists only on server network devices. In another embodiment a portion of the application exists on the target network devices and another portion exists one or more server network devices . However the present invention is not limited to these embodiments and other embodiments and other combinations can also be used to practice the invention.

In one embodiment of the invention the application is a smart application for a smart phone. A smart network device application includes interactions with an operating system on a smart phone. In another embodiment the application is a smart application for the tablet computer. The interactions for the application are typically completed through an Application Programming Interface API .

The mobile network devices are in communications with a communications network . The communications network includes but is not limited to the Internet an intranet a wired Local Area Network LAN a wireless LAN WiLAN a Wide Area Network WAN a Metropolitan Area Network MAN Public Switched Telephone Network PSTN mesh networks and other types of wired and wireless communications networks providing voice video and data communications with wired or wireless communication protocols.

Plural server network devices only four of which are illustrated each with one or more processors and include one or more associated databases . The plural server network devices are in communications with the one or more target network devices via the communications network . The plural server network devices include but are not limited to wireless or wired or data communications servers wireless access points proxy servers and other types of server devices. Selected ones of the server network devices e.g. etc. include Public Safety Answering Point PSAP servers legacy 911 servers E911 servers etc.

The communications network may include one or more gateways routers bridges switches. As is known in the art a gateway connects computer networks using different network protocols and or operating at different transmission capacities. A router receives transmitted messages and forwards them to their correct destinations over the most efficient available route. A bridge is a device that connects networks using the same communications protocols so that information can be passed from one network device to another. A switch is a device that filters and forwards packets between network segments. Switches typically operate at the data link layer and sometimes the network layer and therefore support virtually any packet protocol.

In one embodiment the target network devices and the server network devices include a location application with plural software modules. The multiple software modules may be implemented in firmware hardware or any combination thereof. In one embodiment the target network devices may include a plug in for a browser with plural software modules. In another embodiment the plural target network devices and plural server devices do not include a location application or browser plug in.

The one or more target network devices and one or more server network devices may communicate with each other and other network devices with near field communications NFC and or machine to machine M2M communications.

 Near field communication NFC is a set of standards for smartphones and similar devices to establish radio communication with each other by touching them together or bringing them into close proximity usually no more than a few centimeters. Present and anticipated applications include contactless transactions data exchange and simplified setup of more complex communications such as Wi Fi. Communication is also possible between an NFC device and an unpowered NFC chip called a tag including radio frequency identifier RFID tags.

NFC standards cover communications protocols and data exchange formats and are based on existing radio frequency identification RFID standards including ISO IEC 14443 and FeliCa. These standards include ISO IEC 1809 and those defined by the NFC Forum all of which are incorporated by reference.

 Machine to machine M2M refers to technologies that allow both wireless and wired systems to communicate with other devices of the same ability. M2M uses a device to capture an event such as option purchase etc. which is relayed through a network wireless wired cloud etc. to an application software program that translates the captured event into meaningful information. Such communication was originally accomplished by having a remote network of machines relay information back to a central hub for analysis which would then be rerouted into a system like a personal computer.

However modern M2M communication has expanded beyond a one to one connection and changed into a system of networks that transmits data many to one and many to many to plural different types of devices and appliances. The expansion of IP networks across the world has made it far easier for M2M communication to take place and has lessened the amount of power and time necessary for information to be communicated between machines.

The communications network may also include one or more servers or access points AP including wired and wireless access points WiAP e.g. .

The communications network includes data networks using the Transmission Control Protocol TCP User Datagram Protocol UDP Internet Protocol IP and other data protocols.

The communications network may also include wired interfaces connecting portions of a PSTN or cable television network that connect the target network devices via the Public Switched Telephone Network PSTN or a cable television network CATV including high definition television HDTV that connect the target network devices via one or more twisted pairs of copper wires digital subscriber lines e.g. DSL ADSL VDSL etc. coaxial cable fiber optic cable other connection media or other connection interfaces. The PSTN is any public switched telephone network provided by AT T GTE Sprint MCI SBC Verizon and others.

The communications network may also include digital and analog cellular services Commercial Mobile Radio Services CMRS including mobile radio paging and other wireless services. The communications network includes a cellular telephone network Personal Communications Services network PCS Packet Cellular Network PCN Global System for Mobile Communications GSM Generic Packet Radio Services GPRS Cellular Digital Packet Data CDPD . The communications network includes a Wireless Application Protocol WAP or Digital Audio Broadcasting DAB 802.xx.xx Global Positioning System UPS and GPS map Digital GPS DGPS or other type of wireless network.

The wireless network includes but is not limited to Code Division Multiple Access CDMA Time Division Multiple Access TDMA or other switched wireless technologies.

As is known in the art PCS networks include network that cover a range of wireless digital communications technologies and services including cordless phones mobile phones voice mail paging faxing mobile personal PDAs etc. PCS devices are typically divided into narrowband and broadband categories.

Narrowband devices which operate in the 900 MHz band of frequencies typically provide paging data messaging faxing and one and two way electronic messaging capabilities. Broadband devices which operate in the 1850 MHz to 11990 MHz range typically provide two way voice data and video communications. Other wireless technologies such as GSM CDMA and TDMA are typically included in the PCS category.

As is known in the art GSM is another type of digital wireless technology widely used throughout Europe in Australia India Africa Asia and the Middle East. GSM use is growing in the U.S. GSM is a wireless platform based on TDMA to digitize data. GSM includes not only telephony and Short Message Services SMS but also voice mail call forwarding fax caller ID Internet access and e mail. As is known in the art SMS is type of communications service that enables a user to allow private message communications with another user. GSM typically operates at three frequency ranges 900 MHz GSM 900 in Europe Asia and most of the rest of the world 1800 MHz GSM 1800 or DCS 1800 or DCS in a few European countries and 1900 MHz GSM 1900 also called PCS 1900 or PCS in the United States. GSM also operates in a dual band mode including 900 1800 Mhz and a tri band mode include 900 1800 1900 Mhz.

As is known in the art GPRS is a standard for wireless communications which runs at speeds up to 150 kilo bits per second kbit s GPRS which supports a wide range of bandwidths is an efficient use of limited bandwidth and is particularly suited for sending and receiving small bursts of data such as e mail and Web browsing as well as large volumes of data.

As is known in the art CDPD is a wireless standard providing two way 19.2 Kbps or higher packet data transmission over existing cellular telephone channels. As is known in the art a Packet Cellular Network PCN includes various types of packetized cellular data.

The communications network may also include a mesh network or a mesh sensor network. A mesh network is a self organizing networks built from plural nodes that may spontaneously create an impromptu network assemble the network themselves dynamically adapt to device failure and degradation manage movement of nodes and react to changes in task and network requirements. The plural nodes are reconfigurable smart sensor nodes that are self aware self reconfigurable and autonomous.

A mesh network is a network that employs one of two connection arrangements full mesh topology or partial mesh topology. In the full mesh topology each node is connected directly to each of the others. In the partial mesh topology nodes are connected to only some not all of the other nodes. A mesh network is a network where the nodes are in close proximity e.g. about few feet to about 100 feet or about 1 meter to about 30 meters etc. .

Preferred embodiments of the present invention include network devices and interfaces that are compliant with all or part of standards proposed by the Institute of Electrical and Electronic Engineers IEEE International Telecommunications Union Telecommunication Standardization Sector ITU European Telecommunications Standards Institute ETSI Internet Engineering Task Force IETF U.S. National Institute of Security Technology NIST American National Standard Institute ANSI Wireless Application Protocol WAP Forum Data Over Cable Service Interface Specification DOCSIS Forum Bluetooth Forum the ADSL Forum the Federal Communications Commission FCC the 3rd Generation Partnership Project 3GPP and 3GPP Project 2 3GPP2 and Open Mobile Alliance OMA . However network devices based on other standards could also be used.

An operating environment for network devices and interfaces of the present invention include a processing system with one or more high speed Central Processing Unit s CPU or other types of processors and a memory. In accordance with the practices of persons skilled in the art of computer programming the present invention is described below with reference to acts and symbolic representations of operations or instructions that are performed by the processing system unless indicated otherwise. Such acts and operations or instructions are referred to as being computer executed CPU executed or processor executed. 

It will be appreciated that acts and symbolically represented operations or instructions include the manipulation of electrical signals by the CPU. An electrical system represents data bits which cause a resulting transformation or reduction of the electrical signals and the maintenance of data bits at memory locations in a memory system to thereby reconfigure or otherwise alter the CPU s operation as well as other processing of signals. The memory locations where data bits are maintained are physical locations that have particular electrical magnetic optical or organic properties corresponding to the data bits.

The data bits may also be maintained on a computer readable medium including magnetic disks optical disks organic memory and any other volatile e.g. Random Access Memory RAM or non volatile e.g. Read Only Memory ROM mass storage system readable by the CPU. The computer readable medium includes cooperating or interconnected computer readable medium which exist exclusively on the processing system or be distributed among multiple interconnected processing systems that may be local or remote to the processing system.

As is known in the art the Open Systems Interconnection OSI reference model is a layered architecture that standardizes levels of service and types of interaction for network devices exchanging information through a communications network. The OSI reference model separates network device to network device communications into seven protocol layers or levels each building and relying upon the standards contained in the levels below it. The OSI reference model includes from lowest to highest a physical data link network transport session presentation and application layer. The lowest of the seven layers deals solely with hardware links the highest deals with software interactions at the application program level.

As is known in the art the Internet Protocol reference model is a layered architecture that standardizes levels of service for the Internet Protocol suite of protocols. The Internet Protocol reference model comprises in general from lowest to highest a link network transport and application layer.

In one embodiment of the present invention the wireless interfaces used for the plural target network devices include but are not limited to an IEEE 802.11a 802.11b 802.11g 802.11n Wireless Fidelity Wi Fi Worldwide interoperability for Microwave Access WiMAX ETSI High Performance Radio Metropolitan Area Network HIPERMAN RF Home Zigbee Bluetooth Infrared Industrial Scientific and Medical ISM a Radio Frequency Identifier RFID or other tong range or short range wireless interfaces may be used to practice the invention.

As is known in the art 802.11b defines a short range wireless network interface. The IEEE 802.11b standard defines wireless interfaces that provide up to 11. Mbps wireless data transmission to and from wireless devices over short ranges. 802.11a is an extension of the 802.11b and can deliver speeds up to 54M bps. 802.11g deliver speeds on par with 802.11a. However other 802.11xx interfaces can also be used and the present invention is not limited to the 802.11 protocols defined. The IEEE 802.11a 802.11b and 802.11g standards are incorporated herein by reference.

As is known in the art Wi Fi is another type of 802.11xx interface whether 802.11b 802.11a dual band etc. Wi Fi devices include an RF interfaces such as 2.4 GHz for 802.11b or 802.11g and 5 GHz for 802.11a. More information on Wi Fi can be found at the URL www.weca.net. 

As is known in the art WiMAX is an industry trade organization formed by communications component and equipment companies to promote and certify compatibility and interoperability of broadband wireless access equipment that conforms to the IEEE 802.16xx and ETSI HIPERMAN. HIPERMAN is the European standard for MANs.

The IEEE The 802.16a 802.16c 802.16d 802.16e and 802.16g standards are wireless MAN technology standard that provides a wireless alternative to cable DSL and T1 E1 for last mile broadband access. It is also used as complimentary technology to connect IEEE 802.11xx hot spots to the Internet.

The IEEE 802.16a standard for 2 11 GHz is a wireless MAN technology that provides broadband wireless connectivity to fixed portable and nomadic devices. It provides up to 50 kilometers of service area range allows users to get broadband connectivity without needing direct line of sight with the base station and provides total data rates of up to 280 Mbps per base station which is enough bandwidth to simultaneously support hundreds of businesses with T1 E1 type connectivity and thousands of homes with DSL type connectivity with a single base station. The IEEE 802.16g provides up to 100 Mbps.

The IEEE 802.16e standard is an extension to the approved. IEEE 802.16 16a 16g standard. The purpose of 802.16e is to add limited mobility to the current standard which is designed for fixed operation.

The ESTI HIPERMAN standard is an interoperable broadband fixed wireless access standard for systems operating at radio frequencies between 2 GHz and 11 GHz.

The IEEE 802.16a 802.16d 802.16e and 802.16g standards are incorporated herein by reference. More information on WiMAX can be found at the URL www.wimaxforum.org. WiMAX can be used to provide a wireless local loop WLP .

The ETSI HIPERMAN standards TR 101 031 TR 101 475 TR 101 493 1 through TR 101 493 3 TR 101 761 1 through TR 101 761 4 TR 101 762 TR 101 763 1 through TR 101 763 3 and TR 101 957 are incorporated herein by reference. More information on ETSI standards can be found at the URL www.etsi.org. 

As is known in the art IEEE 802.15.4 Zigbee is low data rate network standard used for mesh network devices such as sensors interactive toys smart badges remote controls and home automation. The 802.15.4 standard provides data rates of 250 kbps 40 kbps and 20 kbps. two addressing modes 116 bit short and 64 bit IEEE addressing support for critical latency devices such as joysticks Carrier Sense Multiple Access Collision Avoidance CSMA CA channel access automatic network establishment by a coordinator fully handshaked protocol for transfer reliability power management to ensure low power consumption for multi month to multi year battery usage and up to 16 channels in the 2.4 GHz ISM band Worldwide 10 channels in the 915MHz US and one channel in the 868 MHz band Europe . The IEEE 802.15.4 2003 standard is incorporated herein by reference. More information on 802.15.4 and ZigBee can be found at the URL www.ieee802.org and www.zigbee.org respectively.

As is known in the art Bluetooth IEEE 802.15.1a is a short range radio frequency technology aimed at simplifying communications among network devices and between network devices. Bluetooth wireless technology supports both short range point to point and point to multipoint connections. The Bluetooth. Specification GL 11r02 March 2005 prepared by the Bluetooth SIG Inc. and the IEEE 802.15.1a standard are incorporated herein by reference.

As is known in the art Infra data association RDA is a short range radio wireless Bluetooth or wireless infrared communications. As is known in the art Industrial Scientific and Medical ISM are short range radio wireless communications interfaces operating at 400 MHz 800 MHz and 900 Mhz. ISM sensors may be used to provide wireless information to practice the invention.

As is known in the art an RFID is an automatic identification method relying on storing and remotely retrieving data using devices called RFID tags or transponders. An RFID tag is a small object that can be attached to or incorporated into a product animal or person. RFID tags contain antennas to enable them to receive and respond to radio frequency queries from an RFID transceiver. Passive tags require no internal power source whereas active tags require a power source. RFID sensors and or RFID tags are used to provide wireless information to practice the invention.

Passive tags are powered by received radiation from a reading device and require no internal source of power thus they can be manufactured at very low cost and require no ongoing maintenance as long as they are not removed or physically damaged. Passive tags can only be read by a reader device in close proximity to the tag which is an advantage in RFID based in building location services.

RFID Passive tags can be manufactured in a sticker like form factor and held in place by adhesive providing very low installation cost however such an arrangement is not heat resistant and conventional mechanical mounting employing screws or cover plates is advisable for at least a minimal subset of all installed tags.

RFID Passive tags are typically capable of providing a 96 bit number to a to reader 96 bits allow 2 10 100 billion possible codes ample to allow unique identification of every significant location within a building.

RFID Active tags may also be employed for location awareness. Active tags have longer range and can include more sophisticated functionality. In the context of this invention active tags may be programmed to validate their location from time to time either by reference to Global Positioning System GPS signals using very long integration times or by interrogation of other RFID tags in their vicinity.

A RFID tag which finds itself in an incorrect or unverified location is programmed to turn itself off thus avoiding spurious location data being provided to a user responses to incorrect location may also include emitting a distress signal which can be detected by a reader during building maintenance or contacting a central location by direct wireless communications or mesh networking employing the multiplicity of companion ID tags in order to induce maintenance personnel to diagnose and repair the problem with the subject tag.

RFID Active tags are also deployed in a mesh network that would allow information to pass from tag to tag. This type of network would allow tag and reader information to be passed from location to location and possibly from floor to floor to move the information to a central location or to the building wall ultimately making it easier to access. Active tag networks have significant functional advantages but are relatively expensive and maintenance intensive compared to passive tags.

In one embodiment the physical location information includes Global Positioning System GPS information street address information two dimensional 2D geo space e.g. X Y e.g. building floor three dimensional 3D X Y Z e.g. building floor floor location e.g. room office desk etc. or other physical location information e.g. longitude latitude street address etc. .

The Global Positioning System GPS is a space based global navigation satellite system GNSS that provides reliable location and time information in all weather and at all times and anywhere on or near the Earth. A GPS receiver calculates its position by precisely timing signals sent by GPS satellites. A GPS receiver uses the messages it receives to determine a transit time of each message and computes a distance to each GPS satellite . These distances along with the satellites locations are used with the possible aid of triangulation depending on which algorithm is used to compute a current physical position of the GPS receiver. This position is then displayed perhaps with a moving map display e.g. at a street level etc. and or latitude and longitude and or elevation and or speed and or acceleration information may also be included. Many GPS units also show derived information such as travel direction and speed calculated from position changes. The GPS coordinates include standard GPS GPS map Digital GPS DGPS and or other types of GPS information.

The target network devices include a protocol stack with multiple layers based on the Internet Protocol or OSI reference model. The protocol stack is used for but not limited to data networking. The protocol stack includes but is not limited to TCP UDP IP Hypertext Transfer Protocol HTTP Simple Mail Transfer Protocol SMTP Post Office Protocol version 3 POP3 Internet Mail Access Protocol IMAP Voice Over IP VoIP Session Initiation Protocol SIP Service Location Protocol SLP Session Description Protocol SDP Real time Protocol RTP H.323 H.324 Domain Name System DNS Authentication Authorization and Accounting AAA instant messaging IM and other protocols.

TCP provides a connection oriented end to end reliable protocol designed to fit into a layered hierarchy of protocols that support multi network applications. For more information on TCP see RFC 793 incorporated herein by reference.

UDP provides a connectionless mode of communications with datagrams in an interconnected set of networks. For more information on UDP see ITEF RFC 768 incorporated herein by reference.

IP is an addressing protocol designed to route traffic within a network or between networks. For more information on IP see ITEF RFC 791 incorporated herein by reference. An IP address includes four sets of numbers divided by period e.g. x.x.x.x in the range of zero to 255. An IP address is a unique string of numbers that identifies a device on an IP based network.

HTTP is a standard protocol for communications on the World Wide Web. For more information on HTTP see IETF RFC 2616 incorporated herein by reference.

SMTP is a protocol for sending e mail messages between devices including e mail servers. For more information on SMTP see IETF RFC 821 and RFC 2821 incorporated herein by reference.

POP3 is a protocol for a protocol used to retrieve e mail from a mail server. For more information on POP3 see IETF RFC 1939 incorporated herein by reference.

IMAP is a protocol for retrieving e mail messages from a server. For more information on IMAP see IETF RFC 1730 incorporated herein by reference.

Media Access Control MAC is a data link layer protocol. A MAC address is a physical address of a device connected to a communications network expressed as a 48 bit hexadecimal number. A MAC address is permanently assigned to each unit of most types of networking hardware such as network interface cards NICs e.g. Ethernet cards etc. by manufacturers at the factory.

VoIP is a set of facilities for managing the delivery of voice information using IP packets. In general VoIP is used to send voice information in digital form in discrete data packets i.e. IP packets over data networks rather than using traditional circuit switched protocols used on the PSTN. VoIP is used on both wireless and wired data networks.

VoIP typically comprises several applications e.g. SIP SLP SDP H.323 H.324 DNS AAA etc. that convert a voice signal into a stream of packets e.g. IP packets on a packet network and back again. VoIP allows voice signals to travel over a stream of data packets over a communications network .

As is known in the art SIP supports user mobility by proxying and re directing requests to a mobile node s current location. Mobile nodes can register their current location. SIP is not tied to any particular conference control protocol. SIP is designed to be independent of a lower layer transport protocol and can be extended. For more information on SIP see IETF RFC 2543 and IETF 3261 the contents of both of which are incorporated herein by reference.

As is known in the art SLP provides a scalable framework for the discovery and selection of network services. Using SIT network devices using the Internet need little or no static configuration of network services for network based applications. For more information on SLP see IETF RFC 2608 incorporated herein by reference.

As is known in the art SDP is a protocol for describing multimedia sessions for the purposes of session announcement session invitation and other forms of multimedia session initiation. For more information on SDP see IETF RFC 2327 incorporated herein by reference

As is known in the art RTP is a protocol for end to end network transport functions suitable for applications transmitting real time data such as audio video or simulation data over multicast or unicast network services. For more information on RIP see IETF RFC 1889 incorporated herein by reference.

As is known in the art H.323 is one of main family of video conferencing recommendations for IP networks. The ITU T 11323 standards entitled Packet based multimedia communications systems dated 02 98 09 99 11 00 and 07 03 are incorporated herein by reference.

As is known in the art H.324 is a video conferencing recommendation using Plain Old Telephone Service POTS lines. The ITU T H.324 standards entitled Terminal for low bit rate multimedia communication dated 02 98 and 03 02 are incorporated herein by reference.

As is known in the art a Domain Name System DNS provides replicated distributed secure hierarchical databases that hierarchically store resource records under domain names. For more information on the DNS see IETF RFC 1034 RFC 1035 RFC 1591 RFC 2606 and RFC 2929 the contents of all of which are incorporated herein by reference.

As is known in the art Authentication Authorization and Accounting AAA includes a Classification scheme and exchange format for accounting data records e.g. for call billing etc. For more information on AAA applications see IETF RFC 2924 the contents of which are incorporated herein by reference.

VoIP services typically need to be able to connect to traditional circuit switched voice networks such as those provided by the PSTN. Thus VoIP is typically used with the H.323 protocol and other multimedia protocols. H.323 and H.324 terminals such as multimedia computers handheld devices PDAs or other devices such as non mobile and mobile phones connect to existing wired and wireless communications networks as well as private wired and wireless networks.

H.323 and H.324 terminals implement voice transmission functions and typically include at least one voice codec ITU T CODECS G.711 G.723 G.726 G.728 G.729 GSM etc. that sends and receives packetized voice data and typically at least one video codec e.g. MPEG etc. that sends and receives packetized video data .

An Instant Message IM is a short real time or near real time message that is sent between two or more end user devices such computers personal digital data assistants PDAs mobile phones etc. running IM client applications. An IM is typically a short textual message. Examples of IM messages include America Online s Instant AIM messaging service Microsoft Network MSN Messenger Yahoo Messenger and Lycos ICQ instant Messenger IM services provided by telecom providers such as T Mobile Verizon Sprint and others that provide IM services via the Internet and other wired and wireless communications networks. In one embodiment of the present invention the IM protocols used meet the requirements of Internet Engineering Task Force IETF Request For Comments RFC entitled Instant Messaging Presence Protocol Requirements. However the present invention is not limited to such an embodiment and other IM protocols not compliant with IETF RFC 2779 may also be used.

Devices and interfaces of the present invention may include security and encryption for secure communications. Wireless Encryption Protocol WEP also called Wired Equivalent Privacy is a security protocol for WiLANs defined in the IEEE 802.11b standard. WEP is cryptographic privacy algorithm based on the Rivest Cipher RCA encryption engine used to provide confidentiality for 802.11b wireless data.

As is known in the art RC4 is cipher designed by RSA Data Security Inc. of Bedford Mass. which can accept encryption keys of arbitrary length and is essentially a pseudo random number generator with an output of the generator being XORed with a data stream to produce encrypted data.

One problem with WEP is that it is used at the two lowest layers of the OSI model the physical layer and the data link layer therefore it does not offer end to end security. One another problem with WEP is that its encryption keys are static rather than dynamic. To update WEP encryption keys an individual has to manually update a WEP key. WEP also typically uses 40 bit static keys for encryption and thus provides weak encryption making a WEP device a target of hackers.

The IEEE 802.11 Working Group is working on a security upgrade for the 802.11 standard called 802.11i. This supplemental draft standard is intended to improve WiLAN security. It describes the encrypted transmission of data between systems 802.11x WiLANs. It also defines new encryption key protocols including the Temporal Key Integrity Protocol TKIP . The IEEE 802.11i draft standard version 4 completed Jun. 6 2003 is incorporated herein by reference.

The 802.11i is based on 802.1x port based authentication for user and device authentication. The 802.11i standard includes two main developments Wi Fi Protected Access WPA and Robust Security Network RSN .

WPA uses the same RC4 underlying encryption algorithm as WEP. However WPA uses TKIP to improve security of keys used with WEP. WPA keys are derived and rotated more often than WEP keys and thus provide additional security. WPA also adds a message integrity check function to prevent packet forgeries.

RSN uses dynamic negotiation of authentication and selectable encryption algorithms between wireless access points and wireless devices. The authentication schemes proposed in the draft standard include Extensible Authentication Protocol EAP . One proposed encryption algorithm is an Advanced Encryption Standard AES encryption algorithm.

Dynamic negotiation of authentication and encryption algorithms lets RSN evolve with the state of the art in security adding algorithms to address new threats and continuing to provide the security necessary to protect information that WiLANs carry.

The NIST developed a new encryption standard the Advanced Encryption Standard AES to keep government information secure. AES is intended to be a stronger more efficient successor to Triple Data Encryption Standard 3DES . More information on NIST AES can be found at the URL www.nist.gov aes. 

As is known in the art DES is a popular symmetric key encryption method developed in 1975 and standardized by ANSI in 1981 as ANSI X.3.92 the contents of which are incorporated herein by reference. As is known in the art 3DES is the encrypt decrypt encrypt EDE mode of the DES cipher algorithm. 3DES is defined in the ANSI standard ANSI X9.52 1998 the contents of which are incorporated herein by reference. DES modes of operation are used in conjunction with the NIST Federal Information Processing Standard FIPS for data encryption FIPS 46 3 October 1999 the contents of which are incorporated herein by reference.

The NIST approved a FIPS for the AES FIPS 197. This standard specified Rijndael encryption as a FIPS approved symmetric encryption algorithm that may be used by U.S. Government organizations and others to protect sensitive information. The NIST FIPS 197 standard AES FIPS PUB 197 November 2001 is incorporated herein by reference.

The NIST approved a FIPS for U.S. Federal Government requirements for information technology products for sensitive but unclassified SBU communications. The NIST FIPS Security Requirements for Cryptographic Modules FIPS PUB 140 2 May 2001 is incorporated herein by reference.

As is known in the art RSA is a public key encryption system which can be used both for encrypting messages and making digital signatures. The letters RSA stand for the names of the inventors Rivest Shamir and Adleman. For more information on RSA see U.S. Pat. No. 4 405 829 now expired incorporated herein by reference.

As is known in the art hashing is the transformation of a string of characters into a usually shorter fixed length value or key that represents the original string. Hashing is used to index and retrieve items in a database because it is faster to find the item using the shorter hashed key than to find it using the original value. It is also used in many encryption algorithms.

Secure Hash Algorithm SHA is used for computing a secure condensed representation of a data message or a data file. When a message of any length 

Message Digest 5 MD 5 takes as input a message of arbitrary length and produces as output a 128 bit message digest of the input. The MD5 algorithm is intended for digital signature applications where a large file must be compressed in a secure manner before being encrypted with a private secret key under a public key cryptosystem such as RSA. The IETF RFC 1321 entitled The MD5 Message Digest Algorithm is incorporated here by reference.

As is known in the art providing a way to check the integrity of information transmitted over or stored in an unreliable medium such as a wireless network is a prime necessity in the world of open computing and communications. Mechanisms that provide such integrity check based on a secret key are called message authentication codes MAC . Typically message authentication codes are used between two parties that share a secret key in order to validate information transmitted between these parties.

Keyed Hashing for Message Authentication Codes HMAC is a mechanism for message authentication using cryptographic hash functions HMAC is used with any iterative cryptographic hash function e.g. MD5 SHA 1 SHA 512 etc. in combination with a secret shared key. The cryptographic strength of HMAC depends on the properties of the underlying hash function. The IETF RFC 2101 entitled HMAC Keyed Hashing for Message Authentication is incorporated here by reference.

As is known in the art an Electronic Code Book ECB is a mode of operation for a block cipher with the characteristic that each possible block of plaintext has a defined corresponding cipher text value and vice versa. In other words the same plaintext value will always result in the same cipher text value. Electronic Code Book is used when a volume of plaintext is separated into several blocks of data each of which is then encrypted independently of other blocks. The Electronic Code Book has the ability to support a separate encryption key for each block type.

As is known in the art Diffie and Hellman DH describe several different group methods for two parties to agree upon a shared secret in such a way that the secret will be unavailable to eavesdroppers. This secret is then converted into various types of cryptographic keys. A large number of the variants of the DH method exist including ANSI X9.42. The IETF RFC 2631 entitled Diffie Hellman Key Agreement Method is incorporated here by reference.

However the present invention is not limited to the security or encryption techniques described and other security or encryption techniques can also be used.

As is known in the art the HyperText Transport Protocol HTTP Secure HTTPs is a standard for encrypted communications on the World Wide Web. HTTPs is actually just HTTP over a Secure Sockets Layer SSL . For more information on HTTP see IETF RFC 2616 incorporated herein by reference.

As is known in the art the SSL protocol is a protocol layer which may be placed between a reliable connection oriented network layer protocol e.g. TCP IP and the application protocol layer e.g. HTTP . SSL provides for secure communication between a source and destination by allowing mutual authentication the use of digital signatures for integrity and encryption for privacy.

The SSL protocol is designed to support a range of choices for specific security methods used tier cryptography message digests and digital signatures. The security method are negotiated between the source and destination at the start of establishing a protocol session. The SSL 2.0 protocol specification by Kipp E. B. Hickman 1995 is incorporated herein by reference. More information on SSL is available at the URL See netscape.com eng security SSL2.html. 

As is known in the art Transport Layer Security TLS provides communications privacy over the Internet. The protocol allows client server applications to communicate over a transport layer e.g. TCP in a way that is designed to prevent eavesdropping tampering or message forgery. For more information on TLS see IETF RFC 2246 incorporated herein by reference.

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step plural outbound signals are sent from a first mobile network device to a plural other network devices via a communications network . In one embodiment the plural outbound signals are plural outbound wireless signals. In one embodiment the plural outbound signals include SIP messages with geo location headers and or message bodies which may include SDP messages.

At Step the first mobile network device receives plural inbound wireless signals from the plurality of other network devices . In one embodiment the plural inbound wireless signals include SIP or SDP protocol messages with a geo location information.

The plural inbound wireless signals include a location thr the first mobile network device in a set of pre determined coordinates. In one embodiment the set of pre determined coordinates are X Y Z space coordinates which are also called geo coordinates 

At Step the pre determined coordinates are translated into a physical geographic location for the first mobile network device including but not limited to a desk and or cubicle in a room on a building floor a building floor in a building a building on a street enterprise campus village town city state country or continent or other global region etc. As described herein the physical geographic address is not a physical or data link layer address but instead a location based address.

in one embodiment the location information is constantly updated in real time e.g. milliseconds seconds etc. In another embodiment the location information is updated in non real time time frames e.g. hours days etc. . If the first mobile network device moves a notification is sent to the other network devices via the communications network.

Thus the target device always knows it s geo location. If the target device is a dumb device a location server acts a proxy for the dumb device and the location server always know the geo location of the dumb device even though the dumb device may not know its own location.

In one embodiment the first mobile network device includes application as software on a Universal Serial Bus USB device that is plugged into the device. In one embodiment the USB device includes a wireless radio transceiver chip. In another embodiment the first mobile network device may already include a wireless radio transceiver. In such an embodiment the USB device may only include application .

In one embodiment The USB port provides the power to the transceiver chip. The transceiver chip uses low power heartbeat communications with wireless transceivers that are strategic located throughout an enterprise building campus village town city state country or continent or other global region. Software application in the USB device processes the return signals from the other wireless transceivers in such way as to determine the location of the first mobile network device in geo space 

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a set of coordinates in geo space received from plural other network devices are translated into a current physical geographic location for a first mobile network device .

In one embodiment the current physical geographic location for the first mobile network device includes but not limited to a room on a building floor a building floor in a building a building on a street enterprise campus village town city state country or continent or other global region etc.

At Step the current physical geographical location is added to a SIP geo location header and or message body used to initiate an E911 emergency communication.

As is known in the art E911 stands for Enhanced 911 which is an emergency event that provides a data event i.e. including location information along with the voice event i.e. an emergency voice call .

At Step the E911 emergency communication is initiated from the first mobile network device using the SIP geo location header and or message body including the physical geographic location of the first mobile network device .

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a first mobile network device periodically sends a set of coordinates geo space received from plural other network devices to a network server via the communications network .

For example the first mobile network device periodically updates either on a scheduled basis or on an event basis e.g. physical movement of the device its r geo coordinates to a centralized location tracing management system using HTTP IP cellular RFID 802.xx.xx or other wireless or other data transmission protocols.

At Step the network server translates the set of geo space coordinates into a current physical geographic location for a first mobile network device .

The centralized management tracing system translates the geo space coordinates into a current physical geographic location that can be responded to by emergency responders such a police fire military etc. The centralized management tracing system also provides access to current physical geographic location information via the communications network with a web interface or other interface useable by emergency personnel.

At Step the network server receives an emergency message from the first mobile network device indicating an emergency event has occurred.

In one embodiment at Step the network server returns the current physical geographic location for the first mobile network device in a SIP geo location header and or message body that can be used to initiate an E911 emergency call from the first mobile network device .

In another embodiment upon an emergency call the centralized management tracing system provides the current physical geographic location of the first network device back to the first mobile network device in a message other than a SIP geolocation header and or message body e.g. IP IM cellular 802.xx.xx RFD etc. .

in another embodiment the centralized management tracing system also provides the current physical geographic location of the first mobile network device to emergency personnel using a variety of methods including but not limited to those illustrated in Table 1.

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a first mobile network device periodically sends plural outbound wireless signals to plural other network devices on one or more wireless communications networks

At Step the first mobile network device periodically receives plural inbound wireless signals from the plural other network devices on the one or more wireless communications networks .

At Step the plural inbound wireless signals are used to determine a set of coordinates in geo space for the first mobile network device .

In one embodiment a transceiver chip in the first mobile network device is used to poll existing WiFi WiMax 802.xx.xx cellular RPM mesh and other wireless networks to determine its geo space. The application uses a variety of methods to determine location in geo space including triangulation signal strength orthogonal etc. The location is constantly updated and the first mobile network device always knows its geo location.

In one embodiment the plural inbound wireless signals are used for Peer to Peer location determination of other network devices on the communications network.

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a set of coordinates in geo space is determined from plural received inbound wireless signals are translated into a current physical geographic location for a first mobile network device .

At Step the physical geographical location is added to a SIP geolocation header and or message body used to initiate an emergency E911 communication.

At Step the E911 emergency communication is initiated from the first mobile network device using the SIP geo location header and or message body including the physical geographic location of the first mobile network device .

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a first mobile network device periodically sends a set of coordinates in geo space derived from one or more other wireless communications networks .

For example the first mobile network device periodically updates either on a scheduled basis or on an event basis e.g. physical movement of the device its geo coordinates to a centralized location tracing management system using HTTP IP SIP SDP or other wireless or other data transmission protocols.

At Step the network server translates the set of geo space coordinates into a current physical geographic location for a first mobile network device .

The centralized management tracing system translates the X Y and Z coordinates into a current physical geographic location that can be responded to by emergency responders such a police fire military etc. The centralized management tracing system also provides access to current physical geographic location information via the communications network with a web interface or other interface useable by emergency personnel.

At Step the network server receives an emergency message from the first mobile network device indicating an emergency has occurred.

In one embodiment at Step the network server returns the current physical geographic location for the first mobile network device in a SIP geo location header and or message body that can be used to initiate an E911 emergency call from the first mobile network device .

In another embodiment upon an emergency call the centralized management tracing system provides the current physical geographic location of the first network device back to the first mobile network device in a message other than a SIP message e.g. IP etc. .

In another embodiment the centralized management tracing system also provides the current physical geographic location of the first mobile network device to emergency personnel using a variety of methods including but not limited to those illustrated in Table 2.

In one embodiment Method further includes Step . At Step the wireless access point sends the set plural physical locations for the plural network networks to a server device to allow a physical geographic location to be determined for the plural network devices. However Method can be practice with or without Step .

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

in such an exemplary embodiment at Step a wireless access point sends plural outbound signals to plural wireless network devices connected to a wireless communications network .

In one embodiment the plural outbound signals include plural SIP geo location header and or message bodies or other protocol messages.

In one embodiment the wireless access point includes a server device. In another embodiment the wireless access point does not include a server device. In such an embodiment the wireless access point comprises a proxy for dumb devices.

In one embodiment the plural wireless network devices include unique identifiers. e.g. IP and MAC address MAC address URI etc. . At Step the wireless access points sends out the plural outbound signals to ping the plural network devices device and then measures a return signal strength a return time delay a return orthogonal to determine the geo coordinates of the plural wire network devices. In such an embodiment the plural wireless network devices periodically send out an electronic heartbeat with a timestamp to the wireless access point via the communications network . However the present invention is not limited to this embodiment and other embodiments can also be used to practice the invention.

At Step the wireless access point receives plural inbound signals from the plural wireless network devices .

In one embodiment the plural inbound signals and plural outbound signals include but are not limited to SIP SDP IP MAC CMRS cellular telephone PCS PCN GSM GMS CDPD WAP DAB Wi Fi WiMAX IEEE 802.11xx GPS GPS map DGPS IM SMS RFID or Zigbee signals. However the present invention is not limited to this embodiment and other inbound and outbound signals can be used to practice the invention.

However the present invention is not limited to this embodiment and other inbound and outbound signals can be used to practice the invention.

In one embodiment at Step the wireless access point determines a set of geo coordinates and an identifier including an IP address and a MAC address for the plural wireless network devices .

In another embodiment at Step the wireless access point determines a set of geo coordinates using a unique identifier pre assigned to the plural wireless network devices . This unique identifier does not include an IP address or a MAC address. In one embodiment the unique identifier is included in an E Location Object.

In one embodiment the E Location Object includes an Extensible Markup Language XML object extension to a Presence Information Data Format e.g. PIDF LO as defined in RFC 4119 the information used in current presence based systems like IM or SMS . For more information see IETF RFC 4119 incorporated by reference.

In another embodiment the unique identifier includes a Uniform Resource Identifier URI . As is known in the art a URI is a unique address of a network resource that is unique across the whole network it is used on. A URI is the unique identifier used to access the resource on a network.

In one embodiment a URI used herein for a network device is unique across all wired and wireless communication networks the network device is used on.

In another embodiment the unique identifier includes a specialized E911 based unique identifier. However the present invention is not limited to these unique identifier and other identifiers can also be used to practice the invention.

At Step the wireless access point determines a set of physical geographic locations for the plural wireless network devices . The plural physical geographic locations are used to locate the plural wireless network devices when an emergency event occurs such as an E911 call. In another embodiment the plural physical geographic locations are used to locate the plural wireless network devices during non emergency situations.

In one embodiment at Step the wireless access point sends a set of geo coordinates and an identifier including an IP address and a MAC address for the plural network devices to a server device to allow a physical geographic location to be determined for the plural network devices on the server device .

In another embodiment at Step the wireless access point sends the unique identifier for the plural network devices to a server device to allow a physical geographic location to be determined for the plural network devices on the server device .

In such embodiments both the wireless access point and the server device have physical geographic location of the plural network devices .

In another embodiment Method is practiced with wired devices a wired access point and a wired communications network . In another embodiment Method is practiced with a combination of wireless and wired devices and wired and wireless communications networks.

In another embodiment a geo coordinates in X Y and or Z space is used in place of the physical geographic location. In such an embodiment the geo coordinates may be further translated or used by other devices to determine a device location.

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a network server receives an emergency message from a first mobile network device e.g. via the communications network indicating an emergency event e.g. fire accident injury criminal event etc. has occurred.

In one embodiment the emergency message is an E911 communication event. In another embodiment the emergency message is an non emergency message.

In one embodiment the emergency message includes a SIP geo location header and or message body with a geo location header. The geo location header includes a PIDF LO extension i.e. RFC 4119 for the device. When a PIDF LO is present the header will indicate to SIP proxies along the call path where in the message body the PIDF LO can be found otherwise the geo location header will have the SIP URI i.e. address of the E LIS where the device s location is stored.

In another embodiment the emergency message includes a SIP geo location header and or message body without a PIDF LO extension. In another embodiment the emergency message includes an E911 message.

At Step the network server translates information from the emergency message into a current physical geographic location for a first mobile network device .

In one embodiment the network server translates a set of coordinates in geo space in the emergency message or retrieves from database a set of previously stored coordinates for the first mobile network device and the unique identifier includes an IP address and MAC address into a current physical geographic location for the first mobile network device and writes this information back to the first mobile network device in a management data message or management data stream over the wireless communications network .

In another embodiment the network server translates the unique identifier for the first mobile network device into a current physical geographic location for the first mobile network device . The unique identifier includes a URI for the first mobile network device .

In another embodiment the network server translates a unique identifier for the first mobile network device into a current physical geographic location for the first mobile network device and the unique identifier is used for a look up of a ten digit emergency location identification number ELM number that will be sent out in the event of a E911 call for the first mobile network device .

In another embodiment the network server translates a set of coordinates in geo space in the emergency message or retrieves from database a set of previously stored current physical geographical location for the first mobile network device and writes this information back to the first mobile network device in a management data stream over the wireless communications network .

In one embodiment the emergency message is an emergency message sent over a wireless interface in one embodiment the wireless interfaces include but are not limited to CARS cellular telephone PCS PCN GSM GPRS CDPD WAP DAB Wi Fi WiMAX IEEE 802.11xx GPS GPS map DGPS IM SMS RFD or Zigbee wireless interfaces. However the present invention is not limited to this embodiment and other wireless interfaces can be used to practice the invention.

In another embodiment the emergency message is an emergency message sent over a wired interface. In another embodiment the emergency message is an non emergency message.

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In one embodiment the plural inbound and outbound signals include but are not limited to SIP geo location header and or message bodies.

In one embodiment the plural outbound and plural inbound signals are sent securely to and received securely from the communications network .

In one embodiment plural inbound and outbound signals comprise wireless signals include but are not limited to CMRS cellular telephone PCS PCN GSM GPRS CDPD WAP DAB Wi Fi WiMAX IEEE 802.11.xx GPS GPS map DGPS IM SMS RFID or Zigbee wireless signals.

In one embodiment the plural inbound and outbound signals comprise wired signals include but are not limited to CATV HDTV DSL ADSL VDSL etc. coaxial or fiber optic signals.

In such an exemplary embodiment at Step a network server device sends plural outbound signals to plural wired or wireless target network devices connected to a wired or wireless communications network .

At Step the network server device receives plural inbound signals from the plural target network devices .

In one embodiment at Step the network server device determines a device type for the plural wireless or wired target network devices to allow a current physical geographic location to be determined for the plural wireless or wired target network devices in an emergency event situation.

In one embodiment at Step the network server device determines a device type using at least the items illustrated in Table 3.

In on embodiment the device type includes a smart network device that stores its own location information or a dumb target network device that does not store its own location information. If the device type is a dumb target network device then the server network device includes a proxy server device to store location information for the dumb target network device.

In one embodiment the emergency event is an E911 communication event. In another embodiment the emergency message is an non emergency event.

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at S the network server device determines IP based network devices and SIP based network devices for the plural wireless or wired target network devices to allow a current physical geographic location to be determined for the plural wireless or wired target network devices in an emergency situation. However the present invention is not limited to IP and SIP based network devices and the network server device can be used to determine other types of target network devices.

At Step the network server device sends the plural device types to plural other server network devices to allow a physical geographic location to be determined for the plural target network devices when an emergency event occurs. In one embodiment the emergency event is a E911 communication event.

In another embodiment the network server device sends the plural device types to plural other server network devices to allow a physical geographic location to be determined for the plural target network devices when non emergency event occurs.

In one embodiment at Step the network server device sends physical geographic location data to ancillary network infrastructure devices that may store manage or forward physical location data including but not limited to those listed in Table 4.

The server network device also includes an application with software to convert geo coded location data to physical location or physical maps.

The server network device also includes an application for reading and writing data to external databases applications systems including but not limited to those illustrated in Table 5 

In one embodiment the server network device also includes an application for notification of events scheduling of tasks issuing reports on system logs and system performance and activity and a graphical user interface GUIs for softphone and device location identification by the end user.

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a wireless emergency message is received on a network server device with one or more processors from an application on a first mobile network device with one or more processors via a wireless communications network indicating an emergency event has occurred with the first mobile network device .

At Step the network server device determines from the emergency message a current physical geographic location for the first mobile network device . The emergency message includes a unique identifier e.g. URI XML object etc. for the first mobile network device on the wireless communications network and the unique identifier is used to access and verify location information about the first mobile network device in current three dimensional 3D X Y Z geo space coordinates at the current physical geographic location.

At Step the network server device returns to a desired emergency response server with one or more processors the current physical geographic location for the first mobile network device .

In one embodiment the first mobile network device includes a smart network device comprising a smart phone or a tablet computer. In one embodiment the application includes a smart application for a smart phone or a tablet computer.

In one embodiment the emergency event includes an accident event fire event terrorist attack event military event or crime event.

In one embodiment the emergency event is detected by an accelerometer and or a temperature sensor integral and or internal to the first mobile network device . In another embodiment the emergency event is detected by an accelerometer and or a temperature sensor external e.g. connected via USB port not connected directly but receiving communications e.g. RFID sensor ISM sensor etc. and in communications with to the first mobile network device . For example the accelerometer may detect an impact and or the temperature sensor may detect a fire etc.

However the present invention is not limited to these emergency events and or sensors and more fewer and or other types of emergency events and or sensors can be used to practice the invention.

In one embodiment the emergency event further includes other types of emergencies including locating children or medical patients based on a triggering event causing communications to an intermediate service provider e.g. hospital private nurse company etc. and or an intruder in a school locating inanimate objects based on a triggering event causing communications to an intermediate information receiver e.g. material e.g. via MD tag etc. truck trailer tools etc. locating sensors based on a triggering event causing communications to an intermediate information receiver e.g. weather service private security office government security office etc. for a kidnapping robbery assault missing person a criminal subject to court ordering electronic monitoring e.g. a registered sex offender not allowed to be near a school etc. . In such an embodiment sensors such as RFD sensors and or ISM sensors and or other types of sensors and or other types of target network devices and or other types server network devices may also be used to provide information to the target network devices and or server network devices and or emergency server network devices.

However the present invention is not limited to these exemplary emergency events and more fewer and or other types of emergency events can be used to practice the invention.

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a location request message is received on the server network device to determine a current physical location for a first mobile network device .

At Step the first mobile network device retrieves via one or more other server network devices on the wireless communications network the current physical location of the first mobile network device .

In one embodiment Step includes determining a current physical location of the first mobile network device . The current physical location is determined by pulling current physical location coordinates from the infrastructure of the wireless communications network rather than the first mobile network device periodically pushing its current physical location into the wireless communication network . For example 1 In a Public Branch Exchange PBX environment the E LIS performs a data link Layer 2 discovery on an IP network that serves the enterprise. This would correlate extensions with the coordinates for an actual physical location or area from where the emergency or non emergency call was placed for downstream processing e.g. by emergency response servers other network servers etc 2 In a cellular traditional micro cell data to cell etc. environment the E LIS queries cell site and its neighbors serving the first mobile network device for presence information of the first mobile network device to request original or updated location coordinates for the current physical location.

In one embodiment no translation of location coordinates are completed. In another embodiment location information is translated in 3D X Y Z geo space coordinates to obtain a current physical location as was described above.

In another embodiment the automatic location request message is generated on the first mobile network device when the first mobile network device is physically shaken in a pre determined pattern. For example if a person was being kidnapped and still had the first mobile network device the device could be turned upside and shaken to automatically generate the location request message. In such an embodiment the accelerometer in the device is used and automatically generates automatic location request message when it is activated.

In another embodiment the automatic location request message is generated on the first mobile network device when a pre determined selection input is received e.g. typing in a numeric code on the virtual keypad from a manual button from a virtual button etc. .

However the present invention is not limited to the pre determine pattern described and other pre determined patterns can be used to practice the invention.

However the present invention is not limited to the embodiments described for Step and other embodiments can also be used to practice the invention.

At Step the current physical location of the first mobile network device is verified by comparing the retrieved current physical location information to stored current physical location information for the first mobile network device on the server network device .

At Step the current physical location information for the first mobile network device is sent to the desired emergency response server.

In one embodiment first mobile network device periodically determines and sends the current physical location for the first mobile network device to the server network device via the wireless communications network .

Method and the other methods described herein can be applied to emergency situations where a user of the first mobile network device does not have the capability to initiate a call e.g. partially incapacitated person kidnapped person etc. The E LIS could be used to initiate the tracking or locating of the first mobile network device . It follows that this same technology could be applied to non emergency events including stolen property location and subsequent retrieval.

However the present invention is not limited to the embodiments described and other embodiments can also be used to practice the invention.

The methods and system described herein provide but are not limited to at least 1 location determine services for any network device in any wired and or wireless access network e.g. Ethernet cable DSL WiFi WiMAX CATV PSTN mesh ISM RFID 802.xx.xx etc. 2 Determines a physical geographical location if necessary and interface with any and all existing location systems e.g. GPS network triangulation 3D X Y Z geo space other WiFi WiMAX and other wireless tracking systems etc. and stores manipulates secures and serves up location in a data form or XML data objects or other accepted and necessary data formats to devices capable of accepting it to location recipients where the service servers stores location on behalf of users devices 3 provides current physical location service for any and applications requiring it including and especially emergency calling service i.e. called E911 and 911 in North America and other geographic regions and 4 and provides stores manipulates and secure locations in either room building postal address physical geographic location format or geo coordinates e.g. X Y Z etc. referent to any generally accepted reference datum like WGS 84 GPS etc. .

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a server application on server network device with one or more processors receives a wireless emergency message from a mobile application on a first mobile network device with one or more processors via a wireless communications network indicating an emergency event has occurred with the first mobile network device . The wireless emergency message includes a unique identifier comprising a specialized E911 based unique identifier for the first mobile network device unique across all wireless and wired communications network and an indication a current set of 3D X Y Z geo space coordinates for the first mobile network device is stored on one or more other server network devices and not on the first mobile network device.

At Step one or more request messages are sent from the server application on the server network device to one or more other network server devices via a second communications network to request the 3D X Y Z geo space coordinates of the first mobile network device .

In one embodiment a Network Attachment Sub System NASS application in the server application maintains on the server network device information about IP connectivity access sessions associated with mobile network devices connected to a communications network . This information is stored in the Connectivity Session Location and Repository Function CLF and made accessible to other subsystems and applications through an interface called an E2 interface. The E2 interface enables Application Functions AF to retrieve IP connectivity related session data. The IP connectivity related session data helps determine a current location of a network device.

In such an embodiment the server application on the server network device uses an E2 interface to send message to and receive messages from the one or more other network server devices . However the present invention is not limited to such an embodiment and other types of message interfaces can be used to practice the invention.

In one embodiment the second communications network is the same communications network as the wireless communications network . In another embodiment the second communications network is a different communications network e.g. a wired communications network a data network e.g. IP network etc. etc.

In another embodiment location information other than the 3D X Y Z geo space coordinates of the first mobile network device can be used to practice the invention and the present invention is not limited the location information described.

At Step one or more response messages are received on the server application on the server network device from the one or more other server network devices via the second communications network including the 3D X Y Z geo space coordinates of the first mobile network device .

In one embodiment all the 3D X Y Z coordinates of the first mobile network device are included in one message. In another embodiment selected portions of the 3D X Y Z geo space coordinate data fir the first mobile network device are included in plural different responses messages. In another embodiment all the 3D X Y Z geo space coordinates of the first mobile network device are included in plural different response messages to allow for verification of a location of a first mobile network device .

However the present invention is not limited to such embodiments and other types of location information and message sequences can be used to practice the invention.

At Step the server application on the server network device consolidates location information for the first mobile network device from the one or more response messages.

At Step the server application on the server network device determines with the E911 based unique identifier and the current set of 3D X Y Z geo space coordinates a current physical geographic location for the first mobile network device .

At Step the server application on the server network device verifies via the wireless communications network the first mobile network device is actually located at the determined current physical geographic location.

In one embodiment the verification step includes comparing location information from the one or more response messages received on the server application on the server network device. In another embodiment the verification step includes sending a message to the first mobile network device asking it to verify its location. In another embodiment the verification step includes comparing a current location of the first mobile network device to previous location.

However the present invention is not limited to such embodiments and other types of verifications can be used to practice the invention.

At Step the server application on the server network device sends a emergency message via the second communications network to a desired emergency response server with one or more processors with the determined and verified current physical geographic location for the first mobile network device .

The emergency response server includes but is not limited to Public Safety Answering Point PSAP servers legacy 911 servers E911 servers Emergency Services IP networks ESInet and other types of emergency response servers.

However the present invention is not limited to such embodiments and other types of emergency response servers can be used to practice the invention.

Method is illustrated with one exemplary embodiment. However the present invention is not limited to such an embodiment and other embodiments can also be used to practice the invention.

In such an exemplary embodiment at Step a server application on a server network device determines whether a desired emergency response server can receive 911 messages from legacy 911 networks or from Emergency Services IP networks ESInet . At Step the server application on the server network device determines whether the emergency response message is being sent to a legacy 911 network.

If the emergency response message is being sent to a legacy 911 network at Step the server application on the server network device creates a new legacy 911 message with the determined physical location information for the first mobile network device in a format usable on the legacy 911 network e.g. physical location information determined with Method etc. 

At Step the new legacy 9111 message is forwarded from the server application on the server network device for transport and dissemination by the legacy 911 network .

If the emergency response message is not being sent to a legacy 911 network at Step from the server application on the server network device creates a new ESInet 911 message with the determined physical location information for the first mobile network device in a in format usable on the ESInet.

At Step the server application on the server network device forwards the new ESInet 911 message for transport and dissemination by the ESInet .

The server application on the server network provides transformation of 911 messages in both inbound and outbound directions including transformation of emergency messages without physical location information included into new 911 messages with determined physical location information and from a format usable on legacy 911 networks into to a format usable on ESInets and from a format usable on ESI nets into a format usable on legacy 911 networks.

It should be understood that the architecture programs processes methods and systems described herein are not related or limited to any particular type of computer or network system hardware or software unless indicated otherwise. Various types of general purpose or specialized computer systems may be used with or perform operations in accordance with the teachings described herein.

In view of the wide variety of embodiments to which the principles of the present invention can be applied it should be understood that the illustrated embodiments are exemplary only and should not be taken as limiting the scope of the present invention. For example the steps of the flow diagrams may be taken in sequences other than those described and more or fewer elements may be used in the block diagrams.

While various elements of the preferred embodiments have been described as being implemented in software in other embodiments hardware or firmware implementations may alternatively be used and vice versa.

The claims should not be read as limited to the described order or elements unless stated to that effect. In addition use of the term means in any claim is intended to invoke 35 U.S.C. 112 paragraph 6 and any claim without the word means is not so intended.

Therefore all embodiments that come within the scope and spirit of the following claims and equivalents thereto are claimed as the invention.

