---

title: Mobile application utilizing accelerometer-based control
abstract: A resident mobile application for application and mobile web navigation on a mobile communication device is disclosed herein. The resident mobile application interfaces with a motion sensor of a mobile communication device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09280526&OS=09280526&RS=09280526
owner: Joingo, LLC
number: 09280526
owner_city: San Jose
owner_country: US
publication_date: 20130308
---
The present application claims priority to U.S. Provisional Patent Application No. 61 624 245 filed on Apr. 13 2012 which is hereby incorporated by reference in its entirety.

The present invention generally relates to mobile applications. More specifically the present invention relates to a mobile application that utilizes an accelerometer based control.

Many mobile communication devices that utilize touch screen technology only have one control button to activate a command. This creates difficulties sending a command if a person is holding an item in one hand and the mobile communication device in the other hand. Further a more physical action is warranted at times to send a command on a mobile communication device.

Application Programming Interface API is a collection of computer software code usually a set of class definitions that can perform a set of related complex tasks but has a limited set of controls that may be manipulated by other software code entities. The set of controls is deliberately limited for the sake of clarity and ease of use so that programmers do not have to work with the detail contained within the given API itself.

BLUETOOTH technology is a standard short range radio link that operates in the unlicensed 2.4 gigaHertz band.

Code Division Multiple Access CDMA is a spread spectrum communication system used in second generation and third generation cellular networks and is described in U.S. Pat. No. 4 901 307.

CRM Customer Relationship Management is a widely implemented strategy for managing a company s interactions with customers clients and sales prospects. CRM involves using technology to organize automate and synchronize business processes and the like principally sales activities but also business processes and the like for marketing customer service and technical support.

Direct Inward Dialing DID involves a carrier providing one or more trunk lines to a customer for connection to the customer s private branch exchange PBX and a range of telephone lines are allocated to this line.

FTP or File Transfer Protocol is a protocol for moving files over the Internet from one computer to another.

Hypertext Transfer Protocol HTTP is a set of conventions for controlling the transfer of information via the Internet from a web server computer to a client computer and also from a client computer to a web server and Hypertext Transfer Protocol Secure HTTPS is a communications protocol for secure communication via a network from a web server computer to a client computer and also from a client computer to a web server by at a minimum verifying the authenticity of a web site.

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

The present invention provides a mobile application that utilizes accelerometer based activation to command a request.

One aspect of the present invention is a method for application and mobile web navigation on a mobile communication device. The method includes accessing a mobile application resident on a mobile communication device of an end user. The mobile application interfaces with an accelerometer of the mobile communication device. The method also includes displaying a request page for the mobile application. The request page comprises action instructions for retrieving a request. The method also includes shaking the mobile communication device to activate the accelerometer of the mobile communication device to transmit an accelerometer signal to request page of the mobile application. The method also includes performing an action upon receiving the accelerometer signal to retrieve the request on the mobile communication device. The method also includes displaying the request on the mobile communication device.

Another aspect of the present invention is a system for application and mobile web navigation on a mobile communication device. The system includes mobile communication devices a network request sites and a request server. Each of the plurality of mobile communication devices is associated with an end user and each mobile communication device comprises a resident mobile application configured to interface with an accelerometer of the mobile communication device display a request page comprising action instructions for retrieving a request perform an action upon receiving an accelerometer signal to retrieve the request on the mobile communication device the accelerometer signal sent to the mobile application upon shaking of the mobile communication device and configured to display the request on the mobile communication device. Each of the request sites is in communication with the network and each has a request. The request server is in communication with each of the request sites and each of the mobile communication devices. The request server receives a request transmission from each of the mobile communication devices and retrieves the request from a corresponding request site.

Yet another aspect of the present invention is a mobile communication device comprising an accelerometer which transmits a signal upon shaking of the mobile communication device and a resident mobile application. The mobile application is configured to interface with the accelerometer of the mobile communication device display a request page comprising action instructions for retrieving a request perform an action upon receiving the accelerometer signal to retrieve the request on the mobile communication device the accelerometer signal sent to the mobile application upon shaking of the mobile communication device and configured to display the request on the mobile communication device.

Having briefly described the present invention the above and further objects features and advantages thereof will be recognized by those skilled in the pertinent art from the following detailed description of the invention when taken in conjunction with the accompanying drawings.

As shown in A and B a resident mobile application on a mobile communication device interfaces with an accelerometer shown in of the mobile communication device in order to activate a request upon shaking the mobile communication device which results in an action performed by the resident mobile application . In one embodiment the request is a new page in a HTML based application and the action is navigating to the new page in the HTML based application. In another embodiment the request is a new page in a downloaded application and the action is navigating to the new page in the downloaded application. In yet another embodiment the request is a form and the action is posting the form. In yet another embodiment the request is a website and the action is fetching a link to the website. In yet another embodiment the instruction is a hypertext link. In yet another embodiment the instruction is a navigation button.

For example in an end user launches a resident mobile application on a mobile communication device . The resident mobile application displays a request page with tickets comprising action instructions for retrieving a request. In the end user shakes the mobile communication device to activate an accelerometer of the mobile communication device. The accelerometer transmits an accelerometer signal to the resident mobile application . Upon receiving the accelerometer signal the resident mobile application performs an action to retrieve the request on the mobile communication device . As shown in the request VIP passes is shown on a display page of the resident mobile application on the mobile communication device .

Another example of the present invention in use is shown in A and B. A scene at a nightclub has a patron is waiting in line with other patrons and while a doorman verifies access to the nightclub. The end user has items in both hands and thus navigating through pages on a mobile browser would be difficult. The resident mobile application displays a request page with action instructions for retrieving a request. The end user shakes the mobile communication device to activate an accelerometer of the mobile communication device. The accelerometer transmits an accelerometer signal to the resident mobile application . Upon receiving the accelerometer signal the resident mobile application performs an action to retrieve the request on the mobile communication device . The present invention allows the end user to shake the mobile communication device to show an access pass on her mobile communication device that is confirmed on a list by the doorman .

The mobile communication devices host devices utilized with the present invention preferably include mobile phones smartphones tablet computers PDAs and the like. Examples of smartphones include the IPHONE smartphone from Apple Inc. BLACKBERRY smartphones from Research In Motion the DROID smartphone from Motorola Mobility Inc. and many more. Examples of tablet computing devices include the IPAD tablet from Apple Inc. and the XOOM tablet from Motorola Mobility Inc.

As shown in a system includes an end user that shakes a mobile communication device . The shaking activates a motion sensor such as an accelerometer which sends a signal to a resident mobile application to perform an action. The resident mobile application transmits a request over a network to a request server which transmits the request over the Internet to a request site having a database . The request is retrieved and sent from the request site over the Internet to the request server over the communications network to the mobile communication device . For example if the end user wanted to request tickets for an event as a reward for reaching a goal in a rewards program the end user would shake the mobile communication device and an electronic ticket would be retrieved from rewards program site and transferred to the mobile communication device .

Each of the interface descriptions preferably discloses use of at least one communication protocol to establish handshaking or bi directional communications. These protocols preferably include but are not limited to XML HTTP TCP IP Serial UDP FTP Web Services WAP SMTP SMPP DTS Stored Procedures Import Export Global Positioning Triangulation IM SMS MMS GPRS and Flash. The databases used with the system preferably include but are not limited to MSSQL Access MySQL Progress Oracle DB2 Open Source DBs and others. Operating system used with the system preferably include Microsoft 2010 XP Vista 200o Server 2003 Server 2008 Server Windows Mobile Linux Android Unix I series AS 400 and Apple OS.

The underlying protocol at a server is preferably Internet Protocol Suite Transfer Control Protocol Internet Protocol TCP IP and the transmission protocol to receive a file is preferably a file transfer protocol FTP Hypertext Transfer Protocol HTTP Secure Hypertext Transfer Protocol HTTPS or other similar protocols. The transmission protocol ranges from SIP to MGCP to FTP and beyond. The protocol at the server is preferably HTTPS.

A mobile communication service provider aka phone carrier of the customer such as VERIZON AT T SPRINT T MOBILE and the like mobile communication service providers provide the communication network for communication to the mobile communication device of the end user.

A flow chart of a method for application and mobile web navigation on a mobile communication device is shown in . At block an end user accesses a mobile application resident on a mobile communication device of an end user. The mobile application interfaces with an accelerometer of the mobile communication device. At block a request page for the mobile application is displayed on the mobile communication device. The request page comprises action instructions for retrieving a request. At block the mobile communication device is shaken to activate the accelerometer of the mobile communication device to transmit an accelerometer signal to the request page of the mobile application. At block an action is performed upon receiving the accelerometer signal to retrieve the request on the mobile communication device. At block the request is displayed on the mobile communication device.

Another embodiment of the present invention is utilized for gaming. An end user shakes a mobile communication device that displays dice for a gaming application. Shaking activates the accelerometer to send a signal to the gaming application which retrieves a reward for a loyalty program. Various embodiment of the present invention can be used with Boyle U.S. patent application Ser. No. 13 769 376 filed on Feb. 16 2013 for a System And Method For Managing Games In A Mobile Virtual Casino which is hereby incorporated by reference in its entirety. Various embodiment of the present invention can be used with Boyle U.S. patent application Ser. No. 13 789 686 filed on Mar. 8 2013 for a System And Method For Secure Play In A Mobile Virtual Casino which is hereby incorporated by reference in its entirety. Various embodiment of the present invention can be used with Boyle et al. U.S. patent application Ser. No. 13 310 741 filed on Dec. 3 2011 for a System And Method For Dynamic Binding Of Prizes To Multi Outcome Games which is hereby incorporated by reference in its entirety.

From the foregoing it is believed that those skilled in the pertinent art will recognize the meritorious advancement of this invention and will readily understand that while the present invention has been described in association with a preferred embodiment thereof and other embodiments illustrated in the accompanying drawings numerous changes modification and substitutions of equivalents may be made therein without departing from the spirit and scope of this invention which is intended to be unlimited by the foregoing except as may appear in the following appended claim. Therefore the embodiments of the invention in which an exclusive property or privilege is claimed are defined in the following appended claims.

