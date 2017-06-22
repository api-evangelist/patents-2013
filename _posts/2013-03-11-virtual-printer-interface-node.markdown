---

title: Virtual printer interface node
abstract: A virtual printer interface node enables a non-cloud-ready printer to communicate with a cloud-based service, residing on an internet. The virtual printer interface node includes a housing; a communication interface to provide communication directly to the network router; and a microcontroller operatively connected to the communication interface. The microcontroller converts commands, received through the communication interface, from the cloud-based service, residing on the internet, to native protocols of the non-cloud-ready networked printer and communicates the converted native protocols to the non-cloud-ready networked printer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09122436&OS=09122436&RS=09122436
owner: Xerox International Partners
number: 09122436
owner_city: Palo Alto
owner_country: US
publication_date: 20130311
---
Cloud computing is the use of computing resources hardware and software that are delivered as a service over a network typically the Internet . Traditionally cloud computing has been focused on web cloud based applications and web connected mobile devices. However as these web cloud based applications and mobile devices have become more capable users expect the same capabilities from these web cloud based applications and mobile devices that the users receive from the users personal computers. One such capability is printing.

Printing architectures and protocols print drivers of conventional personal computer operating systems can be complex and many times are proprietary to the manufacturers of the printing device.

In contrast a cloud based system is based upon achieving coherence and economies of scale thereby relying upon converged infrastructure and shared services. Thus the complexity and proprietary nature of the conventional printing architectures and protocols negatively impact the feasibility of implementing a cloud based printing service.

One solution has been the development of cloud ready printers. These printers have built in systems native support for connecting to cloud print services. A cloud ready printer has no need for a personal computer connection of any kind or for a print driver. The printer can be simply connected directly to a network and then registered with a cloud print service to enable such a printer render print jobs.

However this solution is not readily backward compatible with the vast number of existing conventional network printers that rely upon the conventional printing architectures and protocols. A network ready printer is a printer that includes a network interface wired or wireless that allows the printer to be directly connected to a network.

One conventional approach as illustrated in to enable a conventional network printer to be cloud ready includes running software connector on a personal computer associated with the conventional network printer wherein the software connector registers the network printer through a network with the cloud based service residing on the internet .

When a print job is submitted from the cloud based service residing on the internet to the registered printer the print job is actually routed by the network to the associated personal computer .

The communication channel between the network and the associated personal computer may be wired or wireless.

The software connector running on the personal computer submits the print job to the printer through the network using the personal computer operating system s native printer software.

The software connector running on the personal computer also communicates through the network with the cloud based print service residing on the internet regarding any status information associated with the printer.

Although this approach provides the printer with a connection to a cloud based service residing on the internet the solution requires that the personal computer remain powered ON be executing the software connector and be connected to the network .

In other words the conventional approach for enabling a non cloud ready network printer to be a cloud ready printer is not a standalone solution but requires a personal computer in combination with the conventional non cloud ready network printer.

Thus it is desirable to provide a device for a non cloud ready printer which enables the printer to be cloud ready.

Moreover it is desirable to provide a device for a non cloud ready printer which enables the printer to be cloud ready and does not require a personal computer to be running.

Furthermore it is desirable to provide a plug n play inline device for a non cloud ready printer which enables the printer to be a cloud ready printer.

In addition it is desirable to provide a plug n play network device which enables a non cloud ready printer to be a cloud ready printer and does not require a personal computer to be running.

For a general understanding reference is made to the drawings. In the drawings like references have been used throughout to designate identical or equivalent elements. It is also noted that the drawings may not have been drawn to scale and that certain regions may have been purposely drawn disproportionately so that the features and concepts could be properly illustrated.

A cloud environment uses of computing resources hardware and software that are delivered as a service over a network typically the Internet . For example in a cloud environment a user can rent application software and or databases wherein the cloud providers manage the infrastructure and platforms on which the applications run and the databases are stored.

In another example end users may access cloud based applications through a web browser or a light weight desktop or mobile app while the software and user s data are stored on servers at a remote location.

As mentioned above a user may desire to have a conventional non cloud ready printer be fully functional with cloud based services. To have a conventional non cloud ready printer be fully functional with cloud based services the issues with the native protocols and architecture of the conventional non cloud ready printer not being readily compatible with the protocols of the cloud based service.

As illustrated in an inline virtual printer interface node is provided to enable communication between a conventional non cloud ready printer and a cloud based print service residing on the internet . The inline virtual printer interface node is connected between the network router and the conventional non cloud ready printer .

The communication channel connection between the inline virtual printer interface node and the network router may be wired or wireless.

It is further noted that the inline virtual printer interface node if the communication channel connection between the inline virtual printer interface node and the network router is wired may include a cable jack port RJ45 for receiving a cable coming from the network router .

On the other hand it is noted that the inline virtual printer interface node if the communication channel connection between the inline virtual printer interface node and the network router is wired may include a cable jack for plugging in directly to a port of the network router .

Moreover the communication channel connection between the inline virtual printer interface node and the conventional non cloud ready printer may be wired or wireless.

It is further noted that the inline virtual printer interface node if the communication channel connection between the inline virtual printer interface node and the conventional non cloud ready printer is wired may include a cable jack port RJ45 for receiving a cable coming from the conventional non cloud ready printer .

On the other hand it is noted that the inline virtual printer interface node if the communication channel connection between the inline virtual printer interface node and the conventional non cloud ready printer is wired may include a cable jack for plugging in directly to a port network interface of the conventional non cloud ready printer .

The inline virtual printer interface node converts the native protocols of the conventional non cloud ready printer to a unified protocol that can be used by a cloud based service residing on the internet . In addition the inline virtual printer interface node converts the protocols used by the cloud based service residing on the internet to the native protocols of the conventional non cloud ready printer .

Since the inline virtual printer interface node is a physical device that is inline between the conventional non cloud ready printer and the network router the system does not require a personal computer to be running to enable the conventional non cloud ready printer to be cloud ready. 

In another embodiment as illustrated in a network virtual printer interface node is provided to enable communication between a conventional non cloud ready printer and a cloud based print service residing on the internet . The network virtual printer interface node is connected to the network router and communicates with the conventional non cloud ready printer through the network router .

The communication channel connection between the network virtual printer interface node and the network router may be wired or wireless.

It is further noted that the network virtual printer interface node if the communication channel connection between the network virtual printer interface node and the network router is wired may include a cable jack port RJ45 for receiving a cable coming from the network router .

On the other hand it is noted that the network virtual printer interface node if the communication channel connection between the network virtual printer interface node and the network router is wired may include a cable jack for plugging in directly to a port of the network router .

Moreover the communication channel connection between the network router and the conventional non cloud ready printer may be wired or wireless.

The network virtual printer interface node converts the native protocols of the conventional non cloud ready printer to a unified protocol that can be used by a cloud based service residing on the internet . In addition the network virtual printer interface node converts the protocols used by the cloud based service residing on the internet to the native protocols of the conventional non cloud ready printer .

In this embodiment the network virtual printer interface node receives commands from the cloud based service residing on the internet through the network router and converts these commands to the native protocols of the conventional non cloud ready printer . The network virtual printer interface node then communicates the converted native protocols to the conventional non cloud ready printer through the network router .

In addition the network virtual printer interface node may receive information from the conventional non cloud ready printer through the network router and convert this information into a form that can be readily processed by the cloud based service residing on the internet . The network virtual printer interface node then communicates the converted information to the cloud based service residing on the internet through the network router .

Since the network virtual printer interface node is a physical device that is in communication with the conventional non cloud ready printer and the network router the system does not require a personal computer to be running to enable the conventional non cloud ready printer to be cloud ready. 

The communication interfaces and enable a communication channel to be established between the inline virtual printer interface node and a conventional non cloud ready printer or a network router .

For example communication interface may enable a communication channel to be established between the inline virtual printer interface node and a conventional non cloud ready printer and communication interface may enable a communication channel to be established between the inline virtual printer interface node and a network router .

If the communication channel enabled by the communication interface is wireless the communication interface would include a transmitter and receiver capable of providing wireless communication.

If the communication channel enabled by the communication interface is wireless the communication interface would include a transmitter and receiver capable of providing wireless communication.

If the communication channel enabled by the communication interface is wired the communication interface may include a cable jack port RJ45 for receiving a cable.

For example if the communication channel enabled by the communication interface is a wired communication channel between the conventional non cloud ready printer and the inline virtual printer interface node the communication interface would include a cable jack port RJ45 for receiving a cable coming from the conventional non cloud ready printer.

If the communication channel enabled by the communication interface is wired the communication interface may include a cable jack port RJ45 for receiving a cable.

For example if the communication channel enabled by the communication interface is a wired communication channel between the conventional non cloud ready printer and the inline virtual printer interface node the communication interface would include a cable jack port RJ45 for receiving a cable coming from the conventional non cloud ready printer.

If the communication channel enabled by the communication interface is wired the communication interface may include a cable jack for plugging in directly to a port of a network interface.

For example if the communication channel enabled by the communication interface is a wired communication channel between the conventional non cloud ready printer and the inline virtual printer interface node the communication interface would include an integral cable jack that would plug directly into the cable jack port RJ45 on the conventional non cloud ready printer.

If the communication channel enabled by the communication interface is wired the communication interface may include a cable jack for plugging in directly to a port of a network interface.

For example if the communication channel enabled by the communication interface is a wired communication channel between the conventional non cloud ready printer and the inline virtual printer interface node the communication interface would include an integral cable jack that would plug directly into the cable jack port RJ45 on the conventional non cloud ready printer.

The microcontroller or processor in conjunction with memory converts commands from a cloud based service residing on the internet received through one of the communication interfaces or to the native protocols of a conventional non cloud ready printer. The microcontroller or processor then causes the converted native protocols to be communicated to the conventional non cloud ready printer through the other communication interfaces or .

The microcontroller or processor in conjunction with memory also converts information from a conventional non cloud ready printer received through one of the communication interfaces or into a form that can be readily processed by the cloud based service residing on the internet. The microcontroller or processor then causes the converted information to be communicated to the cloud based service residing on the internet through the other communication interfaces or .

It is noted that the microcontroller or processor and memory may be realized by an application specific integrated circuit ASIC .

It is also noted that the memory may have pre stored the information and commands necessary to convert the commands from a cloud based service residing on the internet to the native protocols of a specific conventional non cloud ready printer.

Moreover it is noted that the inline virtual printer interface node may include functionality to identify the make and model of the conventional non cloud ready printer connected thereto. Based upon the identity the make and model of the conventional non cloud ready printer connected to the inline virtual printer interface node the inline virtual printer interface node could download from the internet the information and commands necessary to convert the commands from a cloud based service residing on the internet to the native protocols of the identified conventional non cloud ready printer.

The network virtual printer interface node includes a housing a communication interface a microcontroller or processor and a memory .

The communication interface enables a communication channel to be established between the network virtual printer interface node and a conventional non cloud ready printer or a network router .

For example communication interface may enable a communication channel to be established between the network virtual printer interface node and a conventional non cloud ready printer and communication interface may enable a communication channel to be established between the network virtual printer interface node and a network router .

If the communication channel enabled by the communication interface is wireless the communication interface would include a transmitter and receiver capable of providing wireless communication.

If the communication channel enabled by the communication interface is wired the communication interface may include a cable jack port RJ45 for receiving a cable.

For example if the communication channel enabled by the communication interface is a wired communication channel between the conventional non cloud ready printer and the network virtual printer interface node the communication interface would include a cable jack port RJ45 for receiving a cable coming from the conventional non cloud ready printer.

If the communication channel enabled by the communication interface is wired the communication interface may include a cable jack for plugging in directly to a port of a network interface.

For example if the communication channel enabled by the communication interface is a wired communication channel between the conventional non cloud ready printer and the network virtual printer interface node the communication interface would include an integral cable jack that would plug directly into the cable jack port RJ45 on the conventional non cloud ready printer.

The microcontroller or processor in conjunction with memory converts commands from a cloud based service residing on the internet received through the communication interface to the native protocols of a conventional non cloud ready printer. The microcontroller or processor then causes the converted native protocols to be communicated to the conventional non cloud ready printer through the communication interface .

The microcontroller or processor in conjunction with memory also converts information from a conventional non cloud ready printer received through the communication interface into a form that can be readily processed by the cloud based service residing on the internet. The microcontroller or processor then causes the converted information to be communicated to the cloud based service residing on the internet through the communication interface .

It is noted that the microcontroller or processor and memory may be realized by an application specific integrated circuit ASIC .

It is also noted that the memory may have pre stored the information and commands necessary to convert the commands from a cloud based service residing on the internet to the native protocols of a specific conventional non cloud ready printer.

Moreover it is noted that the network virtual printer interface node may include functionality to identify the make and model of the conventional non cloud ready printer connected thereto. Based upon the identity the make and model of the conventional non cloud ready printer connected to the network virtual printer interface node the network virtual printer interface node could download from the internet the information and commands necessary to convert the commands from a cloud based service residing on the internet to the native protocols of the identified conventional non cloud ready printer.

It is noted that since the network virtual printer interface node is not inline with the conventional non cloud ready printer the network virtual printer interface node may be located connected to anywhere on the local area network.

It is noted that the virtual printer interface node can receive power over the cables connected to the communication interfaces. If the communication interfaces are wireless the virtual printer interface node would receive power from a power source.

It is noted that although the virtual printer interface node has been described with respect to a conventional non cloud ready printer the virtual printer interface node can be utilized with a conventional non cloud ready multifunction printer i.e. a device having at least scanning printing and copying functionality.

It is further noted that although the virtual printer interface node has been described with respect to a conventional non cloud ready printer the virtual printer interface node can be utilized with a network stand alone scanner. In this situation the virtual printer interface node converts the commands from a cloud based service residing on the internet to the native protocols of scanner.

The virtual printer interface node enables a conventional non cloud ready printer to be availed of cloud based control based services. These services that are based on acquiring data from the conventional non cloud ready printer as well as sending commands to the conventional non cloud ready printer.

For example these services may include break fix service contracts supplies contracts remote monitoring services and other related print services.

To enable these services the microcontroller of the virtual printer interface node provides the mechanism to translate between various local area network LAN side protocols such as simple network management protocol SNMP hypertext transfer protocol HTTP hypertext transfer protocol secure HTTPs exchange web service EWS screen scraping and wide area network WAN or cloud side protocols such as customer premise equipment wan management protocol CWMP being used as a transport protocol with command set being a derivative of the Technical Report 069 TR 069 specification set.

The microcontroller of the virtual printer interface node may also provide the mechanism to translate between the native application programming interface of the conventional non cloud ready printer and the application programming interface of the cloud based service. In this situation the virtual printer interface node acts a proxy between the conventional non cloud ready printer and an application that communicates using a different interface platform by providing either a universal application programming interface on the WAN side or cloud side of the virtual printer interface node or enabling the communication with various interface platforms wherein the memory would store the necessary information and instructions to recognize the interface being used by the application attempting to access the conventional non cloud ready printer and provide the proper translation to the native application programming interface of the conventional non cloud ready printer.

The microcontroller of the virtual printer interface node would also provide the translation of the native application programming interface of the conventional non cloud ready printer to the application programming interface of the cloud based application that the conventional non cloud ready printer is attempting to access.

For example a third party provider may offer an application which communicates via the interface platform of the third party interface platform. The virtual printer interface node would act as a proxy to allow the third party application to communicate with a non enabled third party interface platform device conventional non cloud ready printer having a different application programming interface.

The microcontroller of the virtual printer interface node may also provide the mechanism to translate between local area network based protocols for the conventional non cloud ready printer to firewall friendly wide area network based protocols so as to allow the conventional non cloud ready printer to be able to connect to external services cloud based services .

In the various situations described above the virtual printer interface node would need the appropriate translation application translation program and or translation driver to enable communication therebetween.

As illustrated in the virtual printer interface node at step S determines the identity of the device to which it will act as a translator proxy and the cloud based service being utilized.

With respect to the determination the identity of a printing device to which it will act as a translator proxy the virtual printer interface node may identify the print driver for the printing device or the virtual printer interface node may identify the application programming interface utilized by the printing device.

If the device was a scanner the virtual printer interface node may identify the driver for the scanner or the virtual printer interface node may identify the application programming interface utilized by the scanner.

With respect to the determination the identity of the cloud based service being utilized the virtual printer interface node may identify the application programming interface utilized by the cloud based service.

This identification process enables the virtual printer interface node to identify the translation couplet.

The virtual printer interface node at step S determines if the appropriate translation application for the identified translation couplet is stored on the virtual printer interface node.

If the appropriate translation application for the identified translation couplet is stored on the virtual printer interface node at step S the appropriate stored translation application is retrieved from a memory in the virtual printer interface node.

If the appropriate translation application for the identified translation couplet is not stored on the virtual printer interface node at step S the appropriate translation application is downloaded from the internet i.e. downloaded from a website server associated with the manufacture of the virtual printer interface node.

The microcontroller of the virtual printer interface node can execute a web server application to provide administration interaction reporting and control from a user s browser which is connected through the local area network or proxied through the cloud connection for remote device interaction. In the later situation the virtual printer interface node as noted above would provide the necessary translations between the native protocols and native application programming interface of the conventional non cloud ready printer and the cloud based service.

The virtual printer interface node also enables a conventional non cloud ready multifunction printer to be availed of cloud based content based services. These services are based on moving documents to and from conventional non cloud ready multifunction printer to the cloud services such as a cloud service bridge

The cloud service bridge is a universal gateway to cloud based third party services. The virtual printer interface node implements a special cloud service bridge client that facilitates the document interchange processes between the conventional non cloud ready multifunction printer and the cloud service bridge which in turn may pass some or all the document to a third party service for additional processing. Such content based services may include workflow automation content conversion such as print ready conversion optical character recognition etc.

The content based services could also include consumer services such as brokering and optimization of content that may be available on the broadcast TV or other internet based news channels feeds images or other content.

Various examples of content based cloud services are described in co pending U.S. patent application Ser. No. 13 673 733 filed on Nov. 9 2012 and entitled NETWORKED PRINTING SYSTEMS. The entire content of co pending U.S. patent application Ser. No. 13 673 733 is hereby incorporated by reference.

The virtual printer interface node further enables a conventional non cloud ready printer to be availed of device networking services. These services enable conventional non cloud ready printer through the virtual printer interface node to join a network of other devices that can be exposed to various communities. These communities can be part of a social network for example and once exposed to the conventional non cloud ready printer can utilize the services from the conventional non cloud ready printer.

For example the virtual printer interface node can enable the conventional non cloud ready printer to be connected to a social network such that when content is uploaded to the community the content can be readily or automatically printed by the virtual printer interface node.

These communities can also exist for the purpose of enabling an ecommerce model to charge for the service of using the conventional non cloud ready printer once the conventional non cloud ready printer is exposed to the community.

As noted above conventional non cloud ready printers utilize different versions of an application programming interface making it difficult for a third party system provider to invest adequately in learning a programming system that has a limited applicability thereby limiting the benefits the third party system provider can provided for the conventional non cloud ready printer. The virtual printer interface node implements a universal application programming interface protocol converter such that the third party only needs to invest in a single programming language and interface.

As noted above since the virtual printer interface node enables the conventional non cloud ready printer to be availed of cloud based services the virtual printer interface node can be used to gate services for the conventional non cloud ready printer.

For example if the conventional non cloud ready printer is a multifunction printer having printing copying and or scanning functionality the virtual printer interface node could be used to gate services in the MFP based on a subscription model.

In this scenario the virtual printer interface node acts to block usage of the multifunction printer through content intercept or passing of settings to the multifunction printer to enable or disable certain features. If a valid active subscription is confirmed the virtual printer interface node would enable those features.

For security purposes the virtual printer interface node can utilize authentication protocols to prevent a misuse of remote services.

An authentication process is illustrated in . As illustrated in the virtual printer interface node at step S determines the identity of the device to which it is connected.

If the virtual printer interface node is an inline virtual printer interface node for a printing device the virtual printer interface node would identify the printing device.

On the other hand if the virtual printer interface node is a network virtual printer interface node the virtual printer interface node would identify the router for the local area network.

At step S the virtual printer interface node creates an authentication code based upon the identity of the device to which it is connected and its identity. This would enable the authentication code to be linked or tied to the device virtual printer interface node pair.

It is also noted that the authentication code could be generated using a password or other mechanism that uniquely identifies the authorized user of the virtual printer interface node. In this instance the virtual printer interface node can be utilized with various devices by the authorized user.

It is noted that the generated authentication code may be registered with a cloud based service associated with the virtual printer interface node so that if the proper authentication code is not received by the cloud based service associated with the virtual printer interface node the virtual printer interface node is blocked from being utilized.

If the virtual printer interface node is blocked from being utilized this state of operation would not prevent the connected device from being used under normal conditions. In other words the communications would pass through the virtual printer interface node without processing or translation.

As illustrated in when the virtual printer interface node is invoked at step S the cloud based service associated with the virtual printer interface node requests an authentication code at step S. The virtual printer interface node at step S generates an authentication code in a similar manner as described above with respect to .

The authentication code at step S is transmitted to the cloud based service associated with the virtual printer interface node and the cloud based service associated with the virtual printer interface node validates at step S the received authentication code.

If the received authentication code is valid the cloud based service associated with the virtual printer interface node may transmit an activation code to the virtual printer interface node to allow the virtual printer interface node to be utilized. The activation code could be time based in that the activation period of the virtual printer interface node may be defined in the activation code i.e. activation for thirty minutes.

If the received authentication code is not valid the cloud based service associated with the virtual printer interface node may transmit a deactivation code to the virtual printer interface node to block the virtual printer interface node from being utilized.

In the alternative if the received authentication code is not valid the cloud based service associated with the virtual printer interface node would not transmit an activation code. In this situation the virtual printer interface node would be designed not to be activated functional without the proper activation code.

For example the virtual printer interface node may when the virtual printer interface node is connected to a conventional non cloud ready printer poll the conventional non cloud ready printer to obtain unique identification of the conventional non cloud ready printer such as the media access control MAC address of the conventional non cloud ready printer.

The virtual printer interface node may combine this identification information with the identification information such the media access control MAC address of the virtual printer interface node to create a unique authentication code.

This unique identification code may be registered with the cloud based service associated with the virtual printer interface node such that whenever a cloud based service is accessed that requires the functionality of the virtual printer interface node the cloud based service associated with the virtual printer interface node would request the authentication code.

If the virtual printer interface node is connected to a different printer than when the authentication code was registered with the cloud based service associated with the virtual printer interface node and the authentication code is based upon the device virtual printer interface node pair the authentication code generated by the virtual printer interface node would be different from the registered code because the code would be a combination of the identification of the new printer and the identification of the virtual printer interface node. In such a situation the cloud based service would block utilization of the virtual printer interface node.

More specifically each time the virtual printer interface node needs to communicate with a cloud based service the virtual printer interface node would create an authentication code based on current conventional non cloud ready printer connected thereto. This tying of the authentication code to the identification of both the virtual printer interface node and the conventional non cloud ready printer prevents the virtual printer interface node from being improperly used with another unauthorized printer.

On the other hand if the authentication code is a user virtual printer interface node pair whenever the cloud based service associated with the virtual printer interface node requests the authentication code the virtual printer interface node would have to acquire the user identification mechanism and generate the authentication code therefrom. The user identification mechanism may be acquired through a user interface on the connected device or other input mechanism.

In summary the virtual printer interface node intercepts communications between the cloud based service and the conventional non cloud ready printer and provides the appropriate conversion so that the cloud based service and the conventional non cloud ready printer can effectively communicated therebetween.

An inline virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface. The microcontroller converts commands received through the first communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer. The microcontroller communicates through the second communication interface the converted native protocols to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and an inline virtual printer interface node. The inline virtual printer interface node includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface. The microcontroller converts commands received through the first communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer. The microcontroller communicates through the second communication interface the converted native protocols to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

A network virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller converts commands received through the communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer.

The microcontroller communicates through the communication interface the converted native protocols to the non cloud ready networked printer.

The communication interface m a transmitter receiver to create a wireless communication channel with the network router.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and a network virtual printer interface node. The network virtual printer interface node includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface. The microcontroller converts commands received through the communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer. The microcontroller communicates through the communication interface the converted native protocols to the non cloud ready networked printer.

The communication interface m a transmitter receiver to create a wireless communication channel with the network router.

An inline virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between said first communication interface and said second communication interface.

The microcontroller converts commands received through the first communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer.

The microcontroller communicates through the second communication interface the converted native protocols to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and an inline virtual printer interface node. The inline virtual printer interface node includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface.

The microcontroller converts commands received through the first communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer.

The microcontroller communicates through the second communication interface the converted native protocols to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

A network virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller converts commands received through the communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer.

The microcontroller communicates through the communication interface the converted native protocols to the non cloud ready networked printer.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and a network virtual printer interface node.

The network virtual printer interface node includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller converts commands received through the communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer.

The microcontroller communicates through the communication interface the converted native protocols to the non cloud ready networked printer.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

An inline virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface.

The microcontroller converts commands associated with a first application programming interface language received through the first communication interface from the cloud based service residing on the internet to commands associated with a native application programming interface language of the non cloud ready networked printer the first application programming interface language being different from the native application programming interface language of the non cloud ready networked printer.

The microcontroller communicates through the second communication interface the converted commands associated with the native application programming interface language of the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and an inline virtual printer interface node.

The inline virtual printer interface node includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface.

The microcontroller converts commands associated with a first application programming interface language received through the first communication interface from the cloud based service residing on the internet to commands associated with a native application programming interface language of the non cloud ready networked printer the first application programming interface language being different from the native application programming interface language of the non cloud ready networked printer.

The microcontroller communicates through the second communication interface the converted commands associated with the native application programming interface language of the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

A network virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller converts commands associated with a first application programming interface language received through the communication interface from the cloud based service residing on the internet to commands associated with a native application programming interface language of the non cloud ready networked printer the first application programming interface language being different from the native application programming interface language of the non cloud ready networked printer.

The microcontroller communicates through the communication interface the converted commands associated with the native application programming interface language of the non cloud ready networked printer.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and a network virtual printer interface node.

The network virtual printer interface node includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller converts commands associated with a first application programming interface language received through the communication interface from the cloud based service residing on the internet to commands associated with a native application programming interface language of the non cloud ready networked printer the first application programming interface language being different from the native application programming interface language of the non cloud ready networked printer.

The microcontroller communicates through the communication interface the converted commands associated with the native application programming interface language of the non cloud ready networked printer.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

An inline virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface.

The microcontroller converts local area network based protocols received from the conventional non cloud ready printer to firewall friendly wide area network based protocols the firewall friendly wide area network based protocols enabling the conventional non cloud ready printer to be able to connect to the cloud based service.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and an inline virtual printer interface node.

The inline virtual printer interface node includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface.

The microcontroller converts local area network based protocols received from the conventional non cloud ready printer to firewall friendly wide area network based protocols the firewall friendly wide area network based protocols enabling the conventional non cloud ready printer to be able to connect to the cloud based service.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

A network virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller converts local area network based protocols received from the conventional non cloud ready printer to firewall friendly wide area network based protocols the firewall friendly wide area network based protocols enabling the conventional non cloud ready printer to be able to connect to the cloud based service.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes anon cloud ready networked printer a network router and a network virtual printer interface node.

The network virtual printer interface node includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller converts local area network based protocols received from the conventional non cloud ready printer to firewall friendly wide area network based protocols the firewall friendly wide area network based protocols enabling the conventional non cloud ready printer to be able to connect to the cloud based service.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

An inline virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface.

The microcontroller polls the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller creates an authentication code based on the identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

The identification information associated with the non cloud ready networked printer may be a media access control address.

The identification information associated with the inline virtual printer interface node may be a media access control address.

The microcontroller may poll in response to an authentication request form the cloud based service the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller may create an authentication code based on the authentication request triggered identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and an inline virtual printer interface node.

The inline virtual printer interface node includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface.

The microcontroller polls the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller creates an authentication code based on the identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

The identification information associated with the non cloud ready networked printer may be a media access control address.

The identification information associated with the inline virtual printer interface node may be a media access control address.

The microcontroller may poll in response to an authentication request form the cloud based service the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller may create an authentication code based on the authentication request triggered identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

A network virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller polls the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller creates an authentication code based on the identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

The identification information associated with the non cloud ready networked printer may be a media access control address.

The identification information associated with the inline virtual printer interface node may be a media access control address.

The microcontroller may poll in response to an authentication request form the cloud based service the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller may create an authentication code based on the authentication request triggered identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and a network virtual printer interface node.

The network virtual printer interface node includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller polls the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller creates an authentication code based on the identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

The identification information associated with the non cloud ready networked printer may be a media access control address.

The identification information associated with the inline virtual printer interface node may be a media access control address.

The microcontroller may poll in response to an authentication request form the cloud based service the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller may create an authentication code based on the authentication request triggered identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

An inline virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface.

The microcontroller converts commands received through the first communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer.

The microcontroller communicates through the second communication interface the converted native protocols to the non cloud ready networked printer.

The microcontroller converts commands associated with a first application programming interface language received through the first communication interface from the cloud based service residing on the internet to commands associated with a native application programming interface language of the non cloud ready networked printer the first application programming interface language being different from the native application programming interface language of the non cloud ready networked printer.

The microcontroller communicates through the second communication interface the converted commands associated with the native application programming interface language of the non cloud ready networked printer. The microcontroller polls the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller creates an authentication code based on the identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

The identification information associated with the non cloud ready networked printer may be a media access control address.

The identification information associated with the inline virtual printer interface node may be a media access control address.

The microcontroller may poll in response to an authentication request form the cloud based service the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller may create an authentication code based on the authentication request triggered identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and an inline virtual printer interface node.

The inline virtual printer interface node includes a housing a first communication interface to provide communication directly to the network router a second communication interface to provide communication directly to the non cloud ready networked printer and a microcontroller operatively connected between the first communication interface and the second communication interface.

The microcontroller converts commands received through the first communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer.

The microcontroller communicates through the second communication interface the converted native protocols to the non cloud ready networked printer.

The microcontroller converts commands associated with a first application programming interface language received through the first communication interface from the cloud based service residing on the internet to commands associated with a native application programming interface language of the non cloud ready networked printer the first application programming interface language being different from the native application programming interface language of the non cloud ready networked printer.

The microcontroller communicates through the second communication interface the converted commands associated with the native application programming interface language of the non cloud ready networked printer. The microcontroller polls the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller creates an authentication code based on the identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a port to receive a first cable connected to the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router and the second communication interface may be a jack for plugging into a network port of the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a port to receive a second cable connected to the non cloud ready networked printer.

The first communication interface may be a jack for plugging into a network port of the network router and the second communication interface may be a transmitter receiver to create a wireless communication channel with the non cloud ready networked printer.

The first communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

The identification information associated with the non cloud ready networked printer may be a media access control address.

The identification information associated with the inline virtual printer interface node may be a media access control address.

The microcontroller may poll in response to an authentication request form the cloud based service the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller may create an authentication code based on the authentication request triggered identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

A network virtual printer interface node for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer through to a network router includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller converts commands received through the communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer.

The microcontroller communicates through the communication interface the converted native protocols to the non cloud ready networked printer.

The microcontroller polls the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller creates an authentication code based on the identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

The identification information associated with the non cloud ready networked printer may be a media access control address.

The identification information associated with the inline virtual printer interface node may be a media access control address.

The microcontroller may poll in response to an authentication request form the cloud based service the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller may create an authentication code based on the authentication request triggered identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

A system for providing communication between a cloud based service residing on an internet and a non cloud ready networked printer includes a non cloud ready networked printer a network router and a network virtual printer interface node.

The network virtual printer interface node includes a housing a communication interface to provide communication directly to the network router and a microcontroller operatively connected to the communication interface.

The microcontroller converts commands received through the communication interface from the cloud based service residing on the internet to native protocols of the non cloud ready networked printer.

The microcontroller communicates through the communication interface the converted native protocols to the non cloud ready networked printer.

The microcontroller polls the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller creates an authentication code based on the identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

The communication interface may be a transmitter receiver to create a wireless communication channel with the network router.

The microcontroller may execute a web server application to provide administration interaction reporting and control from a browser which is proxied through the cloud based service for remote device interaction.

The microcontroller may gate services provided by the non cloud ready networked printer in response to restrictions communicated from the cloud based service to the non cloud ready networked printer.

The identification information associated with the non cloud ready networked printer may be a media access control address.

The identification information associated with the inline virtual printer interface node may be a media access control address.

The microcontroller may poll in response to an authentication request form the cloud based service the non cloud ready networked printer to retrieve identification information associated with the non cloud ready networked printer.

The microcontroller may create an authentication code based on the authentication request triggered identification information retrieved from the non cloud ready networked printer and identification information associated with the non cloud ready networked printer associated with the inline virtual printer interface node.

It will be appreciated that various of the above disclosed and other features and functions or alternatives thereof may be desirably combined into many other different systems or applications. Also that various presently unforeseen or unanticipated alternatives modifications variations or improvements therein may be subsequently made by those skilled in the art which are also intended to be encompassed by the following claims.

