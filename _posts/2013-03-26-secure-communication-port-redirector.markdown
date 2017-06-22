---

title: Secure communication port redirector
abstract: A method and system that allows a host system application to securely communicate with a legacy device is provided. A redirector software module receives data that is destined for a host system serial COM port. Data is secured and re-directed to a legacy device via a network port instead of the serial COM port. Conversely, data destined for the host system is provided to a device server via a server COM port by the legacy serial device. The data can be encrypted and sent to the host system via the network. The redirector software module decrypts the encrypted data and presents it to the consumer application as if the data had arrived via the local COM port.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08560734&OS=08560734&RS=08560734
owner: Lantronix, Inc.
number: 08560734
owner_city: Irvine
owner_country: US
publication_date: 20130326
---
This application is a continuation of U.S. patent application Ser. No. 12 639 855 filed on Dec. 16 2009 which is a continuation of U.S. patent application Ser. No. 10 929 858 filed on Aug. 30 2004 now issued U.S. Pat. No. 7 660 910. This and all other extrinsic materials discussed herein are incorporated by reference in their entirety.

The present invention relates to computing systems and more particularly to secured communication between a host system and a legacy device.

Users of serial devices often have the need to remotely communicate with host computing systems for example a personal computer a set top box laptop computer notebook computer or any other computing device collectively referred to as a PC throughout this specification to extend the distance between the devices and their hosts beyond that provided using for example an RS232 cable. The desired remote distance may span the length of an office building or even a continent.

Access to remote serial devices has been limited since it was often necessary to physically connect a computer or PC to the serial device to download data. Fortunately the advent of the Internet network computing provided a method for providing remote communications. A demand arose to Internet enable older serial devices may also be referred to as legacy devices by creating products that have a serial port and an Ethernet port and which can accept data from the legacy devices and send the data over the Internet. Legacy devices may include a stand alone vending machine a microwave a dishwasher or any other device that lacks basic computing ability. Alternatively legacy devices can include devices that require significant computing capabilities such as a FAX machine a copier a printer and the like.

Today the creation of device server technology in embedded systems allows users to place legacy serial devices on to Ethernet networks and thus the Internet with minimal effort and with limited knowledge of networking on the part of the user.

Unfortunately the Internet has proved to be a risky place to operate especially when transferring sensitive data. Security has become a necessity for legacy serial devices operating over the Internet.

Many consumer applications and legacy serial devices are designed to communicate via a local serial communication port a COM port on a PC and are therefore network incompatible without extensively rewriting or otherwise replacing the communications applications to make the legacy serial devices network intelligent. These applications also do not have the means to secure data.

Therefore there is a need for an efficient low cost system and method for providing secured communication with a legacy device without altering legacy device drivers or the applications that are designed to communicate with legacy devices.

The present invention provides a method and associated system that receives data from an application and re directs the data to a legacy device via a network port. Data may be encrypted before it is sent out via the network port. The application is not aware of the redirection of data. This allows consumer applications on a user s PC to securely communicate with legacy devices without requiring the consumer applications to be rewritten upgraded.

In one aspect of the present invention a communication port redirector software module resides on a PC. The redirector software module can redirect the consumer application data otherwise destined for a local serial communication port hereinafter local COM port or serial COM port on the user s PC to a network port. Beneficially the redirector software module can include the capability to encrypt or decrypt using an encryption algorithm.

Instead of traversing through the local COM port the consumer application data is transmitted across the Ethernet network using for example TCP IP. Advantageously the redirection is transparent to the consumer application which continues to perform as if it were communicating to the PC local COM port.

The redirected data is directed to the device server on the network. The device server is capable of decrypting the data and presenting to the legacy device via a local server serial COM port hereinafter server COM port .

Conversely data provided to the device server via the server COM port from the attached legacy serial device can be encrypted and directed back to the consumer application on the remote PC via the network to the redirector software module. The redirector software module decrypts the data and presents to the consumer application as if the data had arrived via the local COM port.

The redirector software module of the present invention eliminates the need for consumers to modify or redesign their communication applications in order to obtain secure data transmission over inherently unsecured data flow paths such as the Internet. The present invention does not require a knowledge or understanding of how to develop networks or how to implement encryption software.

Additional advantages objects and features of the invention will be set forth in part in the detailed description which follows. It is to be understood that both the foregoing general description and the following detailed description are merely exemplary of the invention and are intended to provide an overview or framework for understanding the nature and character of the invention as it is claimed.

A method and system are provided for securing and re directing data from an application that is designed to communicate via a local COM port. Data is secured and transmitted via a network port instead of the local COM port. Accordingly the present description of the embodiments is not to be taken in a limiting sense but is made merely for the purpose of describing the general principles of the invention.

In accordance with an embodiment of the present invention the systems and methods described incorporate all essential networking features including but not limited to an Ethernet connection an operating system a server a full TCP IP protocol stack and encryption capability for secure communications.

To facilitate an understanding of the preferred embodiment the general architecture and operation of a host system or PC will be described. The specific architecture and operation of the preferred embodiment will then be described with reference to the general architecture of the host system and host controller.

Computer includes a computer readable memory medium such as a rotating disk for storing readable data. Besides other programs disk can store application programs including web browsers by which computer connects to the Internet and the systems described below.

According to one aspect of the present invention computer can also access computer readable floppy disks storing data files application program files and computer executable process steps embodying the present invention or the like via a floppy disk drive . A CD ROM or CD R W read write interface not shown may also be provided with computer to access application program files audio files and data files stored on a CD ROM.

A modem an integrated services digital network ISDN connection or the like also provides computer with an Internet connection to the World Wide Web WWW .

It is noteworthy that the present invention is not limited to the architecture. For example notebook or laptop computers handheld devices set top boxes or any other system capable of running computer executable process steps as described below may be used to implement the various aspects of the present invention.

As described above disk stores operating system program files application program files web browsers and other files. Some of these files are stored on disk using an installation program. For example CPU executes computer executable process steps of an installation program so that CPU can properly execute the application program.

Random access memory RAM also interfaces to computer bus to provide CPU with access to memory storage. When executing stored computer executable process steps from disk or other storage media such as floppy disk or WWW connection CPU stores and executes the process steps out of RAM .

Read only memory ROM is provided to store invariant instruction sequences such as start up instruction sequences or basic input output operating system BIOS sequences for operation of keyboard .

The following provides a brief description of the Internet that may be used to receive and send data using the redirector software module of the present invention.

The Internet connects thousands of computers world wide through well known protocols for example Transmission Control Protocol TCP Internet Protocol IP into a vast network. Information on the Internet is stored world wide as computer files mostly written in the Hypertext Mark Up Language HTML . Other mark up languages for example Extensible Markup Language as published by W3C Consortium Version 1 Second Edition October 2000 W3C may also be used. The collection of all such publicly available computer files is known as the World Wide Web WWW . The WWW is a multimedia enabled hypertext system used for navigating the Internet and is made up of hundreds of thousands of web pages with images and text and video files which can be displayed on a computer monitor. Each web page can have connections to other pages which may be located on any computer connected to the Internet.

A typical Internet user uses a client program called a Web Browser to connect to the Internet. A user can connect to the Internet via a proprietary network such as America Online or CompuServe or via an Internet Service Provider for example Earthlink. The web browser may run on any computer connected to the Internet. Currently various browsers are available of which two prominent browsers are Netscape Navigator and Microsoft Internet Explorer. The Web Browser receives and sends requests to a web server and acquires information from the WWW. A web server is a program that upon receipt of a request sends the requested data to the requesting user.

A standard naming convention known as Uniform Resource Locator URL has been adopted to represent hypermedia links and links to network services. Most files or services can be represented with a URL. The URLs enable Web Browsers to go directly to any file held on any WWW server. Information from the WWW is accessed using well known protocols including the Hypertext Transport Protocol HTTP the Wide Area Information Service WAIS and the File Transport Protocol FTP over TCP IP. The transfer format for standard WWW pages is Hypertext Transfer Protocol HTTP .

As shown in consumer application module is designed to initiate communication through application driver to legacy device via a serial COM port . This system configuration is used to provide direct communication capability for transferring data between host system and legacy device without regard to networking capability or the security of the data being transferred.

In this embodiment redirector module is used to intercept a data signal destined for serial COM port from consumer application module secure the data and redirect it through a network interface card NIC to a legacy device via network for example local area network wireless network Internet or any other network. Legacy device is coupled to a device server embedded system that has a local serial port and a network port as discussed below in detail.

In one embodiment consumer application module generates data that is destined for serial COM port local to host system . The generated data is re directed to App Rx Tx module instead.

Configuration module is launched by a host system user when a user desires to map COM port to a network via user interface A to cause application data to be redirected from the serial COM port to the network port that maps to an Ethernet address and port number pair. Configuration module maps serial COM port to the network port for NIC .

App RX TX module accepts application data and determines the particular COM port option. App RX TX module accepts the input data in any format binary or ASCII data.

App RX TX module determines whether the input data needs to be encrypted or decrypted depending on the direction of data flow and if the user has enabled this feature.

After the COM port is properly mapped every time consumer application reads writes or sets options on serial COM port it is directed to the specified network port with a given Ethernet address.

In one embodiment encrypt decrypt module encrypts application data using an encryption algorithm. Alternatively encrypt decrypt module decrypts the encrypted data that is received from device server . Various techniques may be used to secure data for example the Secured Sockets Layer SSL protocol Secure Shell SSH or the Advanced Encryption Standard AES which are incorporated herein by reference in their entirety or any other encryption standard or protocol.

NIC RX TX module moves the encrypted decrypted data depending on the direction of data flow. NIC RX TX module delivers or receives the encrypted decrypted data to or from the Ethernet via NIC .

Application is a communication application that is used to communicate with legacy device . In accordance with an embodiment of the present invention application initiates standard operations such as open close read write and input out control IOCTL operations. In one embodiment application includes communicates with a Win 32 Sub system Win32 Com API an application programming interface and an input output I O manager . The operation of modules and is well known to those of ordinary skill in the art. In one embodiment when application is ready to send data it calls COM API to communicate with the application driver which drives serial COM port . Redirector module intercepts the packet data and then processes it accordingly.

Redirector module is an auxiliary module to application driver and provides an additional interface for redirecting data from serial COM port to the NIC .

In one embodiment redirector module may be a Windows 9X driver which uses Virtual Device Driver VDD with the driver being designated with the extension .vxd. In other embodiments redirector module can be used with Windows NT Windows 2000 Windows XP and Windows 2003 using the Win32 driver model or a close approximation thereof. This type of driver application has the signature extension of .sys. In one embodiment redirector module is a Windows Socket application.

In one embodiment data from application is redirected from in band and out band control data from Ring 0 kernel layer to Ring 3 user mode layer using for example event based processing.

In one embodiment redirector module provides two functions. The first function includes opening a new process thread to setup and wait for a data packet send event. The second function includes communicating with a Windows Socket API for example WS32.dll.

Redirector module launches a Delayed Procedure Call DPC to wake up after a certain time for example every 100 nano seconds to check if the data packet is available. Redirector module returns an IRP with the status of pending. This causes the I O manager to wait until the data packet has been received before returning to the user.

Redirector service module includes an event handler which is called by a signaled event to copy data from the Ring 0 layer to the Ring 3 layer.

After the data is copied the Windows socket Winsock interface takes over the data and passes it down to a Socket Emulator . The Winsock function completes the data transmission. Data is passed through a transport driver interface to a TCP IP stack and then via NIC to network . Modules through are standard components well known to those skilled in the art.

Alternatively when the data packet comes in from legacy device on the network redirector module performs a back channel write IOCTL with the data. This operation wakes the DPC which copies the data into a buffer not shown and signals the I O manager that the data packet is available.

Referring again to device server receives and sends data to and from legacy device . Data that is received from legacy device via COM Port is secured by device server and transmitted to host system . Device server includes two modular connectors and . Connector provides physical connectivity with host system and includes a network port. Connector operationally couples device server with legacy device and includes an RJ 45 jack and a serial COM port.

In one embodiment dual port random access memory is provided to both connectors and to execute process steps according to one aspect of the present invention. Data is received from redirector module and is moved to connector . Thereafter data exchange takes place between connector and . In one aspect data is secured in connector and then transmitted as secure data.

The adaptive aspects of device server are not limited to any particular encryption decryption technique protocol or standard. Device server may be configured to use any encryption techniques such as from SSL to SSH to AES.

In an exemplary operational embodiment encrypt decrypt module of redirector module and device server are setup to use AES. Encrypt decrypt module is implemented as an AES client while secure device server is implemented as an AES server. In this embodiment the user turns on AES selects the size of the key and types the same encryption key for encrypt decrypt module and device server . AES on the encrypt decrypt module is set up on a per port basis. Only the ports connected to AES device server can use AES.

When a connection on the AES redirected port is opened a random initialization string is sent to device server . The length of the string depends upon the size of the key. Device server swallows the initialization string and does not forward it to legacy device . Thereafter all of the data that is now exchanged between host system and device server is encrypted. Encrypt decrypt module of redirector encrypts all data bound to device server and decrypts all data received from device server .

It is noteworthy that if device server does not need to provide a secure data channel it merely passes TCP IP packets from redirector module to legacy device .

An example of a secure device server is the XPort commercially available through Lantronix Inc. and is disclosed in U.S. patent application Ser. No. 10 896 088 entitled Secure Data Transfer Using an Embedded System filed Jul. 21 2004 which is herein incorporated by reference in its entirety.

In step s redirector module determines if the intercepted data must be encrypted. If so in step s redirector software module encrypts the data using an encryption algorithm.

In step s data is transmitted across the Ethernet network using for example TCP IP. Advantageously the redirection is transparent to consumer application which continues to perform as if it were communicating to serial COM port .

In step s the redirected data is directed to device server out on the network. Device server is capable of decrypting the data.

In step s the data is directed back to redirector module via the network. Redirector module receives the data and if necessary in step s decrypts the data.

In step S the decrypted data is presented to consumer application on host system as if the data had arrived via serial COM port .

It is noteworthy that although the foregoing description has used Ethernet to illustrate the adaptive aspects of the present invention an Ethernet to Wireless implementation may also be used to transmit data.

It will be apparent to those skilled in the art that various modifications and variations can be made to the present invention without departing from the spirit and scope of the invention. Thus it is intended that the present invention cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

