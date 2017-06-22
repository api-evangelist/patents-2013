---

title: Creating and using a specific user unique id for security login authentication
abstract: A method of monitoring all network login activity, which includes a real-time analysis of intercepting all network login activity, analyzing network login activity, authenticating network login activity and closing (i.e., terminating) those network login connections that are not authenticated to proceed and access the network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08954729&OS=08954729&RS=08954729
owner: CW International, LLC
number: 08954729
owner_city: Ellwood City
owner_country: US
publication_date: 20130307
---
This application claims benefit of priority to U.S. Provisional Patent Application No. 60 824 835 filed Sep. 7 2006 which is herein incorporated in its entirety by reference. This application is a continuation of U.S. patent application Ser. No. 12 440 312 filed Mar. 5 2010 which is a National Stage filing of Patent International Application Number PCT US2007 077914 filed on Sep. 7 2007 and amended on Mar. 9 2009 both of which are hereby incorporated in their entireties by reference.

This method of invention relates generally to the field of network utility programming and more particularly but not exclusively to monitoring attempted network login connections methods of intercepting network login activity authenticating the network login and closing terminating those network login connections that are not authenticated to proceed and access a network.

As networking and automation expands in business and organizations one of the most important new technical capabilities in today s modern network computing is the ability for organizations to establish access to host networks via the Internet and other network service providers. In essence organizations are allowing connectivity from their Local Area Network LAN from the Internet and any other public network which can be accessed from the Internet. Many public corporations private corporations state and federal government including the Department Of Defense have established and made available a host LAN connection login access for employees from almost any place in the world. As an example it would be very common for an employee working at home to access the Internet and use the Internet to login to the host LAN made available by their employer. Once the individual user is granted login access to the host LAN then it may be very possible for that user to have complete i.e. 100 access to that organization s Wide Area Network WAN or to probe the LAN in an attempt to gain access to the remaining WAN.

Another important issue in today s modern computing environment is that individuals employees associates are provided mobile lap top personal computers PCs which are just as powerful if not more powerful than many standard desktop office computers. These lap top PCs may be used by individuals employees associates while they are physically inside a facility accessing a host LAN and also while they are outside a facility to remotely access the host LAN via the Internet.

Because lap top PCs are becoming smaller and more powerful along with many other computing devices the theft of these lap top PCs and other computing devices is becoming much more common.

Another very important issue problem is that the cracking of network system names and passwords to host LANs has now become a daily problem. Network system names and passwords can be determined using network tools that probe a network while the network is continuously broadcasting information throughout the network domain. When the broadcast information is obtained additional programs i.e. tools can be used to obtain an actual password to a networked computer. System names and passwords can also be obtained by social engineering such as an individual observing another individual user while they actually login and access the host LAN. Alternatively an individual user may be provided an authorized system name and password to accomplish a certain task but then that system name and password are not changed or deleted after the task is completed so the individual user still has access using this system name and password.

Because of the problems described in the previous paragraphs a new technology i.e. utility is needed that has the ability to perform a network user login authentication in order to insure the security of the host LAN during the time the user attempts to login and gain access to the host LAN.

In accordance with an embodiment of the present invention a method includes i.e. comprises executing and performing an analysis of a computer s internal hardware configuration e.g. a 32 64 bit Microsoft computer s internal hardware configuration reading the internal device hardware physically installed within the 32 64 bit Microsoft computer and generating a Unique ID based on the internal hardware configuration and the system name and password of the individual user.

In the description herein general details are provided in flow diagrams to provide a general understanding of the programming methods that will assist in an understanding of embodiments of the inventive methods. One skilled in the relevant art of programming will recognize however that the inventive method can be practiced without one or more specific details or in other programming methods. Referenced throughout this specification to one embodiment or an embodiment means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the present inventive method. Thus the appearance of the phrases in one embodiment or in an embodiment in places throughout this specification are not necessarily all referring to the same embodiment. Furthermore the particular features structures or characteristics may be combined in any suitable manner in one or more embodiments.

In accordance with one or more embodiments of the present invention the O S utility may be developed or implemented in a variety of programming languages ranging from low level programming languages e.g. but not limited to assembler to high level programming languages e.g. but not limited to C Visual Basic Java Java Beans etc. . The O S utility may be stored or encoded as an executable file on a machine readable and or a computer readable medium e.g. but not limited to a floppy disk a hard drive a flash drive a bubble memory a Read Only Memory ROM a Random Access Memory RAM or the like and or hardwired into one or more integrated circuits e.g. an Electrically Erasable Programmable Read Only Memory EEPROM an Erasable Programmable Read Only Memory EPROM etc. .

This STRING ALL COMBINED Media Access Codes is combined with the hard drive serial number which is also converted to a character string prior to being combined and that may be retrieved by calling the GetVolumeInformation function to create an Unique ID using the following equation Unique ID STRING ALL COMBINED Media Access Codes Hard Drive Serial Number

In those instances where more than one hard drive is present in the computer some embodiments of the present invention may only use the primary i.e. root hard drive for example this is frequently the C drive. However in other embodiments of the present invention when more than one hard drive is present serial numbers from two or more of the hard drives present may be used by converting them to strings and then appending them to the end of the STRING of MAC codes. In general the root drive for example C will be used in each embodiment to calculate the Unique ID but embodiments are contemplated in which the root drive may not be used.

The Unique ID may be encrypted by initiating the operating system Crypto API and a DES or an AES Encrypted string that is stored to a data file.

In accordance with and embodiment of the present invention when the user attempts to log into the host if the Unique ID matches the Unique ID stored on the host the user is granted access to the host LAN. If the Unique ID identified by the user i.e. client does not exist because the user does not have an Unique ID stored on the host or the Unique ID stored on the host for the user does not match the user Unique ID the login session is terminated and the IP Address of the attempted login is recorded and an alert is sent to network administration. For example if a user attempts to login on to the host LAN from a different computer from which his her Unique ID was created they will not be able to login into the host LAN.

It is contemplated that embodiments of the present invention may also be used with computer server systems that include additional elements not included in computer system in . For example these addition elements may include but are not limited to additional processing units e.g. parallel processing units graphics processing units etc. bridges and or interfaces to a variety of peripherals e.g. monitor keyboard mouse printer joystick biometric devices speakers external communications devices e.g. a LAN a WAN a modem a router etc. .

Additionally any configuration of the computer system in may be used with the various embodiments of the present invention. The executable instructions i.e. computer program implementing the present invention may be stored in any memory or storage device accessible to processing unit for example but not limited to volatile memory mass storage device or any other local or remotely connected memory or storage device.

An embodiment of the present invention provides one or more means for implementing a programming design capable of being applied to Microsoft C C programs that can initiate parallel threads to monitor almost an unlimited amount of events reported by the operating system in a real time environment without any noticeable performance degradation by the user and an extremely small impact to the overall computer usage regarding CPU cycles percentage and memory utilization.

In accordance with one or more embodiments each of the features of the present invention may be separately and independently claimed. Likewise in accordance with one or more embodiments each utility program program and or code segment module may be substituted for an equivalent means capable of substantially performing the same function s .

In accordance with one or more embodiments each of the features of the present invention may be separately and independently claimed. Likewise in accordance with one or more embodiments each utility program program and or code segment module may be substituted for an equivalent means capable of substantially performing the same function s .

An embodiment of the present invention provides one or more means for executing and performing an analysis of a 32 64 bit Microsoft computer s internal hardware configuration reading the internal device hardware physically installed within the 32 64 bit Microsoft computer and generating a Unique ID based on the internal hardware configuration and the system name and password of the individual user .

In accordance with an embodiment of the present invention a method of retrieving all Media Access Codes MAC includes retrieving a hard drive serial number and a combined all Media Access Codes with the hard drive serial number and creating a Unique ID.

In accordance with an embodiment of the present invention a method includes implementing a Unique ID as part of a user login authentication to a network and verifying that a physical computer logging into the network is a correct computer.

In accordance with an embodiment of the present invention a method as substantially shown and described herein.

In accordance with another embodiment of the present invention a system and method as substantially shown and described herein.

In accordance with yet another embodiment of the present invention a computer and method as substantially shown and described herein.

In accordance with still another embodiment of the present invention a computer network and method as substantially shown and described herein.

Although the present invention has been disclosed in detail it should be understood that various changes substitutions and alterations can be made herein. Moreover although software and hardware are described to control certain functions such functions can be performed using either software hardware or a combination of software and hardware as is well known in the art. Other examples are readily ascertainable by one skilled in the art and can be made without departing from the spirit and scope of the present invention as defined by the following claims.

