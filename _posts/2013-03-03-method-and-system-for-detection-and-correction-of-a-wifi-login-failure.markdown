---

title: Method and system for detection and correction of a WiFi login failure
abstract: A method and system for detection and correction of a WiFi login failure for a mobile application is disclosed herein. The present invention provides a set of diagnostic steps that are undertaken automatically on a mobile communication device to identify this condition within an application and generate a browser window inside the application so that the condition can be fixed and the application can continue without having to time-out and exit an application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08693403&OS=08693403&RS=08693403
owner: Joingo, LLC
number: 08693403
owner_city: San Jose
owner_country: US
publication_date: 20130303
---
The Present Application claims priority to U.S. Provisional Patent Application No. 61 671 409 filed on Jul. 13 2012 which is hereby incorporated by reference in its entirety.

The present invention generally relates to WiFi connections for mobile communication devices. More specifically the present invention relates to a method and system for detection and correction of a WiFI login failure for a mobile application.

Mobile communication device end users constantly face a particular problem when using a local WiFi connection with a mobile communication device. Many times whether on an airplane in a hotel room or in another facility with a local WiFi connection a user attempts to run an application on a mobile communication device and the application times out. Upon inspection the end user determines that the signal strength is good and there is a connection to a local WiFi connection. Some end users will try to start a browser of the mobile communication device to determine if there is something that needs to be agreed to or a login. Other end users will be bewildered and frustrated that they cannot access an application on the mobile communication device.

Application Programming Interface API is a collection of computer software code usually a set of class definitions that can perform a set of related complex tasks but has a limited set of controls that may be manipulated by other software code entities. The set of controls is deliberately limited for the sake of clarity and ease of use so that programmers do not have to work with the detail contained within the given API itself.

BLUETOOTH technology is a standard short range radio link that operates in the unlicensed 2.4 gigaHertz band.

Code Division Multiple Access CDMA is a spread spectrum communication system used in second generation and third generation cellular networks and is described in U.S. Pat. No. 4 901 307.

CRM Customer Relationship Management is a widely implemented strategy for managing a company s interactions with customers clients and sales prospects. CRM involves using technology to organize automate and synchronize business processes and the like principally sales activities but also business processes and the like for marketing customer service and technical support.

Direct Inward Dialing DID involves a carrier providing one or more trunk lines to a customer for connection to the customer s private branch exchange PBX and a range of telephone lines are allocated to this line.

FTP or File Transfer Protocol is a protocol for moving files over the Internet from one computer to another.

Hypertext Transfer Protocol HTTP is a set of conventions for controlling the transfer of information via the Internet from a web server computer to a client computer and also from a client computer to a web server.

Hypertext Transfer Protocol Secure HTTPS is a communications protocol for secure communication via a network from a web server computer to a client computer and also from a client computer to a web server by at a minimum verifying the authenticity of a web site.

Internet is the worldwide decentralized totality of server computers and data transmission paths which can supply information to a connected and browser equipped client computer and can receive and forward information entered from the client computer.

Interactive voice response IVR is a telephone technology in which a user uses a phone to interact with a database to acquire information.

Multimedia messaging service MMS communication is a communication transmitted to and from a mobile phone that includes a multimedia content such as a digital photograph JPEG videos and the like.

Public Switch Telephone Network PSTN is a telecommunication system in which networks are inter connected to allow telephones to communicate with each other throughout the world.

Short Message Service SMS is text messaging communication using a mobile phone or other device to send messages up to 160 characters in length.

Short message peer to peer SMPP is a telecommunications protocol for exchanging SMS messages between SMS peer entities.

A SMS aggregator is an entity that provides connectivity with a mobile phone carrier by offering a SMS gateway to send and receive messages and other digital content.

A SMS Gateway is used to send text messages with or without a mobile phone and is used by aggregators to forward text messages to mobile phones.

Telephone Consumer Protection Act TCPA of 1991 restricts the use of SMS text messages received by mobile phones and SMS messages sent without a consumer s consent can violate the TCPA.

Voice over Internet Protocol VoIP relates to communications transmitted over the Internet such as SKYPE.

User Interface or UI is the junction between a user and a computer program. An interface is a set of commands or menus through which a user communicates with a program. A command driven interface is one in which the user enter commands. A menu driven interface is one in which the user selects command choices from various menus displayed on the screen.

Web Browser is a complex software program resident in a client computer that is capable of loading and displaying text and images and exhibiting behaviors as encoded in HTML HyperText Markup Language from the Internet and also from the client computer s memory. Major browsers include MICROSOFT INTERNET EXPLORER NETSCAPE APPLE SAFARI MOZILLA FIREFOX and OPERA.

Web Server is a computer able to simultaneously manage many Internet information exchange processes at the same time. Normally server computers are more powerful than client computers and are administratively and or geographically centralized. An interactive form information collection process generally is controlled from a server computer to which the sponsor of the process has access.

Wireless Application Protocol WAP is an open global specification that empowers users with mobile wireless communication devices such as mobile phones to easily access data and to interact with Websites over the Internet through such mobile wireless communication device. WAP works with most wireless communication networks such as CDPD CDMA GSM PDC PHS TDMA FLEX reflex iDEN TETRA DECT DataTAC Mobitex and GRPS. WAP can be built on most operating systems including PalmOS WINDOWS CE FLEXOS OS 9 JavaOS and others.

WAP Push is defined as an encoded WAP content message delivered pushed to a mobile communication device which includes a link to a WAP address.

The prior art has failed to provide a means for automatically determining and correcting a WiFi login failure.

The present invention is provides a solution to the problem. The present invention provides for automatic detection and correction of a WiFI login failure for a mobile application. The present invention provides a set of diagnostic steps that are undertaken automatically on a mobile communication device to identify this condition within an application and generate a browser window inside the application so that the condition can be fixed and the application can continue without having to time out and exit.

One aspect of the present invention is a method for detection and correction of a WiFi login failure for a mobile application. The method includes launching a mobile application on a mobile communication device. The method also includes accessing a network through a WiFi connection of a facility for an action on the mobile application. The method also includes determining that access to the WiFi connection of the facility on the mobile application has failed. The method also includes displaying a login for the WiFi connection of the facility on the mobile application to login to gain access to the WiFi connection.

Another aspect of the present invention is a mobile communication device comprising a mobile application resident on the mobile communication device. The mobile application is configured to access a network through a WiFi connection of a facility for an action determine that access to the WiFi connection of the facility on the mobile application has failed display a login for the WiFi connection of the facility on the mobile application to login to gain access to the WiFi connection. The mobile communication device is preferably a mobile phone or tablet computer.

Yet another aspect of the present invention is a system for detection and correction of a WiFi login failure for a mobile application. The system includes a facility having WiFi access to the Internet available through a WiFi connection with a login and at least one mobile communication device. The mobile communication comprises a mobile application configured to access a network through a WiFi connection of a facility for an action determine that access to the WiFi connection of the facility on the mobile application has failed display a login for the WiFi connection of the facility on the mobile application to login to gain access to the WiFi connection.

Yet another aspect of the present invention is a method for detection and automatic correction of a WiFi login failure for a mobile application. The method includes launching a mobile application on a mobile communication device. The method also includes accessing a network through a WiFi connection of a facility for an action on the mobile application. The method also includes determining that access to the WiFi connection of the facility on the mobile application has failed. The method also includes automatically transmitting a login for the WiFi connection of the facility for the mobile communication device to login to gain access to the WiFi connection.

Yet another aspect of the present invention is a method for detection and correction of a WiFi login failure for a mobile application. The method includes launching a mobile application on a mobile communication device. The method also includes accessing a network through a WiFi connection of a facility for an action on the mobile application. The method also includes determining that a link to a web address over the WiFi connection is inaccessible. The method also includes determining that the mobile communication device is connected to the WiFi connection of the facility. The method also includes determining that a login must be completed. The method also includes displaying a login for the WiFi connection of the facility on the mobile application to login to gain access to the WiFi connection.

Yet another aspect of the present invention is a system for detection and correction of a WiFi login failure for a mobile application. The system includes a facility having WiFi access to the Internet available through a WiFi connection with a login and a mobile communication device. The mobile communication device comprises a mobile application configured to access a network through a WiFi connection of a facility for an action determine that a link to a web address over the WiFi connection is inaccessible determine that the mobile communication device is connected to the WiFi connection of the facility determine that a login must be completed and display a login for the WiFi connection of the facility on the mobile application to login to gain access to the WiFi connection.

Having briefly described the present invention the above and further objects features and advantages thereof will be recognized by those skilled in the pertinent art from the following detailed description of the invention when taken in conjunction with the accompanying drawings.

A method for detection and correction of a WiFi login failure for a mobile application is shown in . At block a mobile application is launched on a mobile communication device. At block a network is accessed through a WiFi connection of a facility for an action on the mobile application. At block the mobile application determines that access to the WiFi connection of the facility on the mobile application has failed. At block a login for the WiFi connection of the facility is displayed on the mobile application to login to gain access to the WiFi connection.

A method for detection and automatic correction of a WiFi login failure for a mobile application is shown in . At block a mobile application is launched on a mobile communication device. At block a network is accessed through a WiFi connection of a facility for an action on the mobile application. At block the mobile application determines that access to the WiFi connection of the facility on the mobile application has failed. At block the mobile application automatically transmits a login for the WiFi connection of the facility for the mobile communication device to login to gain access to the WiFi connection.

A system for detection and correction of a WiFi login failure for a mobile application is shown in . The system includes a network such as the Internet a third party server a mobile communication service provider a mobile communication device wireless access points and a facility server and a firewall of a facility network. A mobile application is launched on the mobile communication device . The mobile communication device accesses the facility network through a wireless access point for a WiFi connection of the facility network for an action on the mobile application. The mobile application determines that a link to a web address over the WiFi connection is inaccessible. The mobile application determines that the mobile communication device is connected to the WiFi connection of the facility network. The mobile application also determines that a login must be completed. The mobile application displays a login for the WiFi connection of the facility on the mobile application to login to gain access to the WiFi connection of the facility network.

A system for detection and correction of a WiFi login failure for a mobile application is shown in . The system includes a network such as the Internet a third party server a mobile communication service provider a mobile communication device wireless access points and a facility server and a firewall of a facility network. A mobile application is launched on the mobile communication device . The mobile communication device accesses the facility network through a WAP for a WiFi connection of the facility network for an action on the mobile application. The mobile application determines that a link to a web address over the WiFi connection is inaccessible. The mobile application determines that the mobile communication device is connected to the WiFi connection of the facility network. The mobile application also determines that a login must be completed. The mobile application displays a login for the WiFi connection of the facility on the mobile application to login to gain access to the WiFi connection of the facility network.

As shown in a typical mobile communication device includes an accelerometer a head phone a microphone a speak a GPS chipset a Bluetooth component a WiFi component a 3G 4G component a BaseBand Processor for radio control an applications processor a JTAG debugger a SDRAM memory a Flash memory SIM card LCD display a camera a power management circuit and a battery or power source

The mobile communication devices utilized with the present invention preferably include mobile phones smartphones tablet computers PDAs and the like. Examples of smartphones include the IPHONE smartphone from Apple Inc. BLACKBERRY smartphones from Research In Motion the DROID smartphone from Motorola Mobility Inc. and many more. Examples of tablet computing devices include the IPAD tablet from Apple Inc. and the XOOM tablet from Motorola Mobility Inc.

Most of the interface descriptions preferably disclose use of at least one communication protocol to establish handshaking or bi directional communications. These protocols preferably include but are not limited to XML HTTP TCP IP Serial UDP FTP Web Services WAP SMTP SMPP DTS Stored Procedures Import Export Global Positioning Triangulation IM SMS MMS GPRS and Flash. The databases used with the system preferably include but are not limited to MSSQL Access MySQL Progress Oracle DB2 Open Source DBs and others. Operating system used with the system preferably include Microsoft 2010 XP Vista 200o Server 2003 Server 2008 Server Windows Mobile Linux Android Unix I series AS 400 and Apple OS.

The underlying protocol at a server is preferably Internet Protocol Suite Transfer Control Protocol Internet Protocol TCP IP and the transmission protocol to receive a file is preferably a file transfer protocol FTP Hypertext Transfer Protocol Secure HTTPS or other similar protocols. The transmission protocol ranges from SIP to MGCP to FTP and beyond. The protocol at a server is preferably HTTPS.

A mobile communication service provider aka phone carrier of the customer such as VERIZON AT T SPRINT T MOBILE and the like mobile communication service providers provide the communication network for communication to the mobile communication device of the end user.

From the foregoing it is believed that those skilled in the pertinent art will recognize the meritorious advancement of this invention and will readily understand that while the present invention has been described in association with a preferred embodiment thereof and other embodiments illustrated in the accompanying drawings numerous changes modification and substitutions of equivalents may be made therein without departing from the spirit and scope of this invention which is intended to be unlimited by the foregoing except as may appear in the following appended claim. Therefore the embodiments of the invention in which an exclusive property or privilege is claimed are defined in the following appended claims.

