---

title: Smart card service method and apparatus for performing the same
abstract: Provided are a smart card service method and an apparatus for performing the same. The smart card service method includes receiving a certificate generation request from a terminal, transmitting the certificate generation request to an authentication processing device, and storing credential information with respect to the generated certificate in a virtual machine associated with the terminal in response to a certificate generation success message provided from the authentication processing device. Thus, it is possible to reduce costs in accordance with manufacturing smart card hardware, and support smart card services in a more enhanced security environment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09503454&OS=09503454&RS=09503454
owner: ELECTRONICS & TELECOMMUNICATIONS RESEARCH INSTITUTE
number: 09503454
owner_city: Daejeon
owner_country: KR
publication_date: 20131017
---
This application claims priority to Korean Patent Application No. 10 2012 0115855 filed on Oct. 18 2012 and No. 10 2013 0122300 filed on Oct. 15 2013 in the Korean Intellectual Property Office KIPO the entire contents of which are hereby incorporated by reference.

Example embodiments of the present invention relate in general to smart card service technology and more particularly to a smart card service method which virtualizes a smart card to provide the virtualized smart card in a cloud computing environment and an apparatus for performing the same.

In a smart terminal including a radio communication function or a mobile communication function such as a cellular phone a smartphone a pad type terminal and the like a smart card is mounted in the form of hardware for the purpose of security and or authentication of a subscriber and an authentication manager performs authentication of a user or a subscriber based on credential information obtained from the smart card.

The smart card may include personal information a phonebook message download data applications personal setting information of a user and the like as well as provisioning or subscription information for a cellular phone of the user.

Information of a user or a subscriber is stored in the above described smart card and therefore personal information of the user may be easily stored even when the user purchases or exchanges a new smart terminal thereby easily replacing the smart terminal.

Meanwhile as the number of smart terminals used by individuals is gradually increased the number of smart cards which should be mounted in the smart terminal is also increased costs for manufacturing the smart card are increased due to the increase in the number of smart cards in the form of hardware and credential information of individuals becomes more difficult to be managed due to its dispersion.

In addition since operating systems or applications installed in the smart terminals are able to easily access credential information stored in the smart card important credential information of individuals may be leaked when the smart terminal is exposed to malicious attacks such as hacking or malicious codes.

Accordingly example embodiments of the present invention are provided to substantially obviate one or more problems due to limitations and disadvantages of the related art.

Example embodiments of the present invention provide a smart card service method which may reduce manufacturing costs of a smart card and integrally manage credential information of individuals in a cloud computing environment in which security is enhanced.

Example embodiments of the present invention also provide a smart card service apparatus which may reduce manufacturing costs of the smart card and integrally manage credential information of individuals in a cloud computing environment in which security is enhanced.

In some example embodiments a smart card service method which is performed in an apparatus enabling processing of digital data includes receiving a certificate generation request from a terminal transmitting the certificate generation request to an authentication processing device and storing credential information with respect to the generated certificate in a virtual machine associated with the terminal in response to a certificate generation success message provided from the authentication processing device.

Here before the storing of the credential information the smart card service method may further include verifying whether the virtual machine associated with the terminal exists and generating the virtual machine associated with the terminal when the virtual machine associated with the terminal does not exist.

Also after the storing of the credential information the smart card service method may further include receiving an authentication request from the terminal acquiring the to credential information from the virtual machine associated with the terminal transmitting the authentication request to the authentication processing device using the acquired credential information and transmitting to the terminal an authentication result received from the authentication processing device.

Also after the storing of the credential information the smart card service method may further include receiving a certificate deletion request from the terminal acquiring the credential information from the virtual machine associated with the terminal transmitting the certificate deletion request to the authentication processing device using the acquired credential information and receiving a certificate deletion result from the authentication processing device.

Also after the receiving of the certificate deletion result the smart card service method may further include verifying whether the credential information exists in the virtual machine associated with the terminal and deleting the virtual machine associated with the terminal when the credential information does not exist in the virtual machine associated with the terminal.

In other example embodiments a smart card service apparatus includes a cloud server configured to include credential information of each of a plurality of user terminals and a plurality of virtual machines for executing a smart card function of each of the user terminals and an interface unit configured to communicate with an authentication management device so as to receive a request for a process associated with authentication from an arbitrary user terminal and perform the received request for the process using credential information included in a virtual machine associated with the arbitrary user terminal.

Here the smart card service apparatus may further include a cloud user management unit configured to allow access to the smart card service apparatus only with respect to an authorized user.

Also the smart card service apparatus may further include a cloud channel management unit configured to manage a communication channel for security of communication between the smart card service apparatus and the plurality of user terminals and communication between the smart card service apparatus and the authentication management device.

Also the interface unit may receive a certificate generation request from the arbitrary user terminal transmit the certificate generation request to the authentication management device and store credential information with respect to the generated certificate in the virtual machine associated with the arbitrary user terminal based on a certificate generation success message provided from the authentication management device.

Also the interface unit may receive an authentication request from the arbitrary user terminal acquire the credential information from the virtual machine associated with the arbitrary user terminal transmit the authentication request to the authentication management device using the acquired credential information and transmit an authentication result provided from the authentication management device to the arbitrary user terminal.

Also the interface unit may receive a certificate deletion request from the arbitrary user terminal acquire the credential information from the virtual machine associated with the arbitrary user terminal and transmit the certificate deletion request to the authentication management device using the acquired credential information.

Also the interface unit may receive a message indicating that certificate deletion is successfully performed from the authentication management device verify whether the credential information exists in the virtual machine associated with the arbitrary user terminal and delete the virtual machine associated with the arbitrary user terminal when the credential information does not exist in the virtual machine associated with the arbitrary user terminal.

Example embodiments of the present invention are described below in sufficient detail to enable those of ordinary skill in the art to embody and practice the present invention. It is important to understand that the present invention may be embodied in many alternative forms and should not be construed as limited to the example embodiments set forth herein.

Accordingly while the invention can be modified in various ways and take on various alternative forms specific embodiments thereof are shown in the drawings and described in detail below as examples. There is no intent to limit the invention to the particular forms disclosed. On the contrary the invention is to cover all modifications equivalents and alternatives falling within the spirit and scope of the appended claims. Elements of the example embodiments are consistently denoted by the same reference numerals throughout the drawings and detailed description.

The terminology used herein to describe embodiments of the invention is not intended to limit the scope of the invention. The articles a an and the are singular in that they have a single referent however the use of the singular form in the present document should not preclude the presence of more than one referent. In other words elements of the invention referred to in the singular may number one or more unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features numbers steps operations elements and or components but do not preclude the presence or addition of one or more other features numbers steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this invention belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

Hereinafter preferred embodiments of the present invention will be described in detail with reference to the accompanying drawings. In the drawings and description elements that appear in more than one drawing and or elements that are mentioned in more than one place in the description are always denoted by the same respective reference numerals and are not described in detail more than once.

A smart card used in the present specification may be used as a meaning including credential information for performing security and or authentication of a user and may be referred to as other terms such as existing subscriber identity module SIM removable user identity module RUIM universal subscriber identity module USIM universal integrated circuit card UICC embedded UICC eUICC and the like.

In addition a smart terminal used in the present specification may be used as a term that defines all terminals or devices required for security and or authentication in order to use a specific function.

Hereinafter virtualization technologies and cloud computing technologies which are utilized as technologies for smart card services in the present invention will be briefly described.

In order to well respond to business environments which have been recently rapidly changed as importance of flexibility to respond well to the changes and a speed to respond quickly to occurrence of the changes has been emerged virtualization technologies have attracted attention as next generation computing technologies.

The virtualization technologies applied to a server of an existing data center are approaching closer to general users in various areas while showing new virtualization technologies which have rapidly evolved utilizing existing virtualization technologies such as application virtualization presentation virtualization and the like.

The virtualization technologies have been generally used in a main frame starting from a virtual memory in the late 1960s but have been used limitedly in some places for usage due to high introduction costs and a limited use environment. Thereafter in many areas ranging up to a hypervisor that supports dynamic resource partitioning propelled by several decades of continuous innovation new technologies of virtualization have been introduced in a stepwise manner.

In addition as there arise needs for receiving services anytime and anywhere in a distributed computing environment based on the Internet the virtualization technologies have been developed as actual implementation technologies which constitute an efficient computing infrastructure ranging up to cloud computing and utility computing.

As an existing concept of the virtualization resource partitioning technology which partitions and utilizes a single resource has been mainly developed starting from server virtualization technology but virtualization in the advanced form henceforth can be seen to be extended in such a manner that various resources are expanded to an overall group rather than at the level of a single resource so that the expanded resources are managed. Through such development integrated virtualization of a plurality of servers may be possible and partitioned resources may freely move in a computing environment and therefore stability of an overall work load may be ensured.

Meanwhile the cloud computing includes a server a storage an application program and the like in a data center as components and in the cloud computing the data center is connected to a terminal through a network to provide services to the terminal.

The server is equipment for performing an actual operation and includes a server computer an operating system and the like and the storage is equipment for storing results and includes a disk a database and the like. The application program refers to a program for performing a desired operation using the server and the storage and the network is responsible for connection between a terminal and a cloud and between the clouds. The terminal is equipment for requesting services or displaying the result and includes a personal computer a laptop computer a cellular phone and the like.

In a smart card service method according to an embodiment of the present invention a conventional smart card mounted in the form of hardware is virtualized using the above described virtualization technologies and the cloud computing technologies to thereby constitute a virtual machine VM and then smart card VMs that provides smart card services are located in a cloud server of a cloud computing environment.

When a user requests security and or authentication services using a smart terminal the smart terminal may be connected to a corresponding smart card VM by accessing a cloud environment through a communication channel in which security is supported.

The smart card VM that provides the smart card services transmits credential information of the user stored in advance to an authentication management device for executing authentication enables the authentication management device to execute an authentication procedure using the transmitted credential information of the user receives an authentication result from the authentication management device and then transmits the received authentication result to the smart terminal of the user through a communication channel with enhanced security.

In addition according to an embodiment of the present invention when an application installed in the smart terminal of the user requests security and or authentication an interface that allows the same interface as the existing one to be used may be provided.

In addition a smart card VM that exists in the cloud computing environment may be configured to be operated using an existing interface supported by an existing authentication management device and therefore an existing application and authentication management device which are operated in an environment using the smart card in the form of hardware are used as is without separately reconfiguring or changing the existing application and authentication management device.

Referring to in a smart card service system according to an embodiment of the present invention a smart terminal a smart card service apparatus and a security authentication management device may be operated in an environment in which the smart terminal the smart card service apparatus and the security authentication management device are connected to each other through a wired or wireless network or .

The smart terminal may include at least one application that requests security and or authentication and a terminal interface unit that is responsible for an interface function for transmitting and receiving requests for security and or authentication and authentication results between the application and the smart card service apparatus .

The at least one application installed in the smart terminal may request security and or an authentication operation using an application programming interface API provided from the terminal interface unit and receive the security and or authentication results through the terminal interface unit to determine the results. Here the API provided by the terminal interface may be the same as an API provided by the terminal interface unit of the existing smart terminal in which a smart card in the form of hardware is mounted.

The smart card service apparatus may be located in a cloud computing environment and configured in the form of a virtualization server that supports a virtualization function.

The smart card service apparatus may include a plurality of smart card VMs that support smart card functions and a security authentication interface unit and integrally manage credential information of a plurality of users. Here each of the plurality of smart card VMs may support the smart card function and for this include credential information of a designated user.

The security authentication interface unit performs an interface function corresponding to the terminal interface unit provided in the smart terminal . In addition the security authentication interface unit performs an interface function for security and or authentication with the security authentication management device .

Specifically the security authentication interface unit receives requests for certificate generation authentication request certificate deletion and the like through the network from the terminal interface unit provided in the smart terminal and cooperates with the security authentication management device in order to perform operations corresponding to the received requests.

The security authentication management device is connected to the smart card service apparatus through the network performs the corresponding function in response to the security and or authentication requests provided through the security authentication interface unit provided in the smart card service apparatus and then provides the result to the smart card service apparatus . Here the security authentication management device may perform functions such as certificate generation authentication certificate deletion and the like and provide to the smart card service apparatus the results with respect to whether the certificate is successfully generated whether the authentication is successfully performed whether the certificate is successfully deleted.

Referring to the smart card service apparatus may include at least one cloud server a cloud user management unit a cloud channel management unit and a security authentication interface unit .

Each cloud server may include a plurality of smart card VMs that support smart card services a VM monitor and hardware .

Each of the plurality of smart card VMs executes a smart card service operation and for this includes credential information associated with each smart card.

The VM monitor performs a function of a virtual platform or a hypervisor for simultaneously performing the plurality of smart card VMs which exist above the VM monitor . That is the VM monitor supports each of the smart card VMs to execute the same operations as operations of the smart terminal in which conventional smart card hardware is provided.

The hardware may include a memory an input output interface a processor and the like which configure hardware of the cloud server .

The cloud user management unit manages information about cloud user accounts managed within a cloud. That is when an arbitrary user attempts to access the cloud or the smart card service apparatus the cloud user management unit determines whether the arbitrary user is an authorized user based on login information input by the user grants the access to the cloud when the arbitrary user is the authorized user and denies the access when the arbitrary user is not the authorized user. In addition the cloud user management unit may grant access only to the smart card VM designated in advance to the arbitrary user when the arbitrary user is the authorized user.

The cloud channel management unit manages a communication channel for security communication between the smart terminal and the cloud server and security communication between the cloud server and the security authentication management device . For the above described security communication the cloud channel management unit may support communication encrypted between the cloud server and the smart terminal or between the cloud server and the security authentication management device or support the communication to be performed using a security communication protocol set in advance.

The security authentication interface unit receives requests for certificate generation authentication request certificate deletion and the like from the terminal interface unit of the smart terminal through the network and cooperates with the security authentication management device in order to perform operations corresponding to the received requests.

Specifically in case of the certificate generation the security authentication interface unit provides a certificate generation request to the security authentication management device to enable a new certificate to be generated and creates credential information with respect to the generated certificate to the corresponding smart card VM. Here when the smart card VM associated with a user or the smart terminal that has requested the certificate generation does not exist the security authentication interface unit may newly generate a smart card VM associated with the user that has requested the certificate generation.

Here in case of the authentication request the security authentication interface unit acquires credential information from the corresponding smart card VM whose authentication is requested transmits the acquired credential information to the security authentication management device to perform an authentication procedure and transmits the authentication result provided from the security authentication management device to the smart terminal.

In addition in case of the certificate deletion the security authentication interface unit provides a deletion request of the corresponding certificate to the security authentication management device and deletes credential information corresponding to the deleted certificate from the corresponding smart card VM. In addition when the credential information does not exist anymore in the smart card VM associated with the user or the smart terminal that has requested the certificate deletion the security authentication interface unit may delete the corresponding smart card VM.

Referring to in operation the smart card service apparatus acquires cloud login information used for accessing a cloud or the smart card service apparatus from a smart terminal.

Next in operation S the smart card service apparatus determines whether a user of the smart terminal is an authorized user capable of accessing the cloud based on the acquired login information. Here the smart card service apparatus may verify whether the login information acquired from the smart terminal exists in a list of users allowed to access the cloud and then determine that the user of the smart terminal is the authorized user capable of accessing the cloud when the login information exists in the list of users allowed to access the cloud.

The smart card service apparatus blocks the access to the cloud with respect to a user which is not authorized in accordance with the determination result of operation S and terminates the certificate generation process. Here the smart card service apparatus may transmit to the smart terminal of the user that has attempted to access the cloud a message indicating that the user of the smart terminal is not an authorized user.

Meanwhile in operation S when the user that attempts to access the cloud is determined to be the authorized user in operation S the smart card service apparatus allows the access of the user to the cloud and receives a message indicating a certificate generation request from the smart terminal of the user.

Next in operation S the smart card service apparatus determines whether a smart card VM allocated to the user or the smart terminal of the user that has requested the certificate generation exists.

In operation S when the smart card VM allocated to the user that has requested the certificate generation does not exist in accordance with the determination result of operation S the smart card service apparatus generates a new smart card VM that can support smart card services to the user or the smart terminal .

Next in operation S the smart card service apparatus transmits a message indicating generation of a new certificate to the security authentication management device. Here the security authentication management device may newly generate the certificate of the user in response to the certificate generation request received from the smart card service apparatus and transmit to the smart card service apparatus a message indicating that the certificate generation is successfully completed. Here the smart card service apparatus may recognize that the certificate generation is completed through a certificate generation completion message provided from the security authentication management device.

In operation S when the certificate generation is completed the smart card service apparatus stores credential information with respect to the generated certificate in the corresponding smart card VM.

Referring to in operation S the smart card service apparatus acquires cloud login information used for accessing a cloud or the smart card service apparatus from a smart terminal.

Next in operation S the smart card service apparatus determines whether a user of the smart terminal is an authorized user capable of accessing the cloud based on the acquired login information. Here the smart card service apparatus may verify whether the login information acquired from the smart terminal exists in a list of users allowed to access the cloud and then determine that the user of the smart terminal is the authorized user capable of accessing the cloud when the login information exists in the list of users allowed to access the cloud.

The smart card service apparatus blocks the access to the cloud with respect to a user which is not authorized in accordance with the determination result of operation and terminates the authentication processing process.

Meanwhile in operation S when the user that attempts to access the cloud is determined to be the authorized user in operation S the smart card service apparatus allows the access of the user to the cloud and receives a message indicating the authentication request from the smart terminal of the user.

Next in operation S the smart card service apparatus acquires credential information of the user from the smart card VM allocated to the user or the smart terminal of the user that has requested the authentication.

In operation S the smart card service apparatus transmits a message for requesting authentication of a corresponding user to the security authentication management device using the acquired credential information of the user. Here the security authentication management device performs a user authentication procedure based on the credential information of the user received from the smart card service apparatus and provides the authentication result to the smart card service apparatus.

In operation S the smart card service apparatus transmits to the smart terminal authentication result information received from the security authentication management device. Here the smart card service apparatus may transmit an authentication success message or an authentication failure message to the smart terminal of the user that has requested the authentication based on the authentication result information received from the security authentication management device.

Referring to in operation S the smart card service apparatus acquires cloud login information used for accessing a cloud or the smart card service apparatus from the smart terminal.

Next in operation S the smart card service apparatus determines whether a user of the smart terminal is an authorized user capable of accessing the cloud based on the acquired login information. Here the smart card service apparatus verifies whether the login information acquired from the smart terminal exists in a list of users allowed to access the cloud and then determines that the user of the smart terminal is the authorized user capable of accessing the cloud when the login information acquired from the smart terminal exists in the list of users allowed to access the cloud.

The smart card service apparatus blocks the access to the cloud with respect to a user which is not authorized in accordance with the determination result of operation S and terminates the certificate deletion process.

Meanwhile in operation S when the user that attempts to access the cloud is determined to be the authorized user in operation S the smart card service apparatus allows the access of the user to the cloud and receives a message indicating the certificate deletion request from the smart terminal of the user.

Next in operation S the smart card service apparatus acquires credential information of the user from the smart card VM allocated to the user or the smart terminal of the user that has requested the certificate deletion.

Next in operation S the smart card service apparatus transmits a message indicating deletion of a corresponding certificate to the security authentication management device. Here the security authentication management device may delete a certificate of the user in response to the certificate deletion request received from the smart card service apparatus and then transmit to the smart card service apparatus a message indicating that the certificate deletion is successfully completed. Here the smart card service apparatus may recognize that the certificate deletion is completed through a certificate deletion completion message provided from the security authentication management device.

In operation S when the certificate deletion is completed the smart card service apparatus determines whether remaining credential information of the user exists in the smart card VM allocated to the user that has requested the certificate deletion.

When the credential information of the user exists in the smart card VM allocated to the user that has requested the certificate deletion in accordance with the determination result of operation S the smart card service apparatus completes the certificate deletion process.

However in operation S when the credential information of the user does not exist in the smart card VM anymore in accordance with the determination result of operation S the smart card service apparatus deletes the corresponding smart card VM.

As described above in the smart card service method and the apparatus for performing the same according to the embodiments of the present invention a smart card configured in the form of existing hardware may be virtualized and the virtualized smart card may be serviced in a cloud computing environment thereby reducing manufacturing costs of smart card hardware and supporting the smart card services in a more enhanced security environment.

In addition the smart card services may be provided so as not to change an existing user interface thereby easily switching a use environment from an existing use environment to a new cloud computing environment.

While example embodiments of the present invention and their advantages have been described in detail it should be understood that various changes substitutions and alterations may be made herein without departing from the scope of the invention.

