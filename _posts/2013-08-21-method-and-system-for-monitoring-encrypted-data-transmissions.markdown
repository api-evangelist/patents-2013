---

title: Method and system for monitoring encrypted data transmissions
abstract: A method for efficiently decrypting asymmetric SSL pre-master keys is divided into a key agent component that runs in user mode, and an SSL driver running in kernel mode. The key agent can take advantage of multiple threads for decoding keys in a multi-processor environment, while the SSL driver handles the task of symmetric decryption of the SSL encrypted data stream. The method is of advantage in applications such as firewalls with deep packet inspection in which all encrypted data traffic passing through the firewall must be decrypted for inspection.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08898451&OS=08898451&RS=08898451
owner: Trend Micro Incorporated
number: 08898451
owner_city: Tokyo
owner_country: JP
publication_date: 20130821
---
The present application is a Continuation application of U.S. application Ser. No. 11 766 976 filed on Jun. 22 2007 entitled METHOD AND SYSTEM FOR MONITORING ENCRYPTED DATA TRANSMISSION the entire contents of all applications and issued patent being incorporated herein by reference.

The present invention relates to the decryption of encrypted data packets specifically for the purpose of monitoring the packet payload contents.

The encryption of data that is transmitted through the Internet has become common place. Data messages may be encoded by a protocol known as SSL Secure Socket Layer which is intended to render the encoded data unintelligible to any recipient or eavesdropper unless they are in possession of the key decryption key necessary for decoding the data. SSL was developed by Netscape Communications Corporation for securing data transmission in commercial transactions on the Internet. Using public key cryptography SSL provides server authentication data encryption and data integrity for client server communications.

The SSL protocol has evolved over the years and has become standardized the term SSL being generally used to refer to any version of the protocol. The specification of a recent version of SSL may be found in the IETF Internet Engineering Task Force document RFC Request For Comment 4346 entitled The Transport Layer Security TLS Protocol Version 1.1 . The TLS protocol is thus a recent specification of the SSL protocol.

Briefly the SSL includes a handshake protocol for setting up an encrypted session methods for the authentication of messages and methods for encrypting decrypting the data.

The Internet also has become a place over which unwanted potentially harmful and otherwise unsolicited data traffic is transmitted. This phenomenon has given rise to an industry providing various tools for defending networks servers and computer work stations against such traffic while allowing legitimate traffic to pass unhindered. A firewall is typically software that is installed in a network node traffic passing through a firewall is inspected by inspecting each packet and applying a set of rules to determine whether the packet should pass or be stopped. A firewall may be implemented in a networked computer such as a server or a work station as well as in dedicated nodes such as network access nodes and routers.

The functionality of a firewall may range from simple address filtering in which packets with predetermined source addresses or ranges of addresses are discarded to more complex processes which include discriminating traffic on the basis of the protocol for example ICMP Internet Control Message Protocol UDP User Datagram Protocol TCP Transmission Control Protocol etc filtering based on source and destination ports of each packet tracking the connection state to determine protocol violations and the like. Even more sophisticated filtering may be done on the basis of the message content itself so called deep packet inspection.

An added complication arises when the firewall is also required to guard against and identify for discarding unwanted messages that are encrypted. In the case of a network node that is flooded with a large amount of unwanted messages that are encrypted it is very important to ensure that the filtering of such messages is performed efficiently and expeditiously. When deep packet inspection is required each session comprising a stream of ultimately perhaps unwanted packets must first be set up according to the specified protocol and packets decrypted correctly before a decision regarding the session s validity can be made.

While the specification as well as much of the necessary software to handle SSL are publicly available the existing software is designed to deal with the traditional case of server to client communication but is inadequate to process unwanted traffic efficiently enough to be used in a firewall that includes deep packet inspection.

Consequently there is a need for the development of improved techniques to efficiently enable monitoring the packet payload contents of encrypted data traffic for example for the purpose of monitoring and filtering of unwanted data traffic.

It is therefore an objective of the invention to develop a method and system that can be used to enable the decryption of encrypted data packets specifically for the purpose of monitoring the packet payload contents.

According to one aspect of the invention there is provided a method for decrypting a Secure Socket Layer SSL pre master key in a computing environment having a user mode and a kernel mode comprising steps of 

In the embodiment of the invention the steps ii and iii of the method comprise selecting one of a plurality of key decryption threads for decrypting different decryption request records.

Conveniently the step c of the method comprises sending an error response to the driver indicating that the agent request queue is full sending an error response to the driver indicating that the private key is not available and sending an error response to the driver indicating that the decryption did not succeed.

According to another aspect of the present invention there is provided a method of inspecting an encrypted packet in a computing environment having a user mode and a kernel mode the method comprising the steps of

The method further comprises the step 5 repeating the steps 3 and 4 until the encrypted session is terminated.

The method further comprises terminating the encrypted session based on the content of the decrypted packets.

According to yet another aspect of the invention there is provided a method of initiating a Secure Socket Layer SSL session using a handshake protocol in a computing environment having a user mode and a kernel mode the method comprising steps of 

In the method described above the step of decrypting is performed in one of a plurality of decryption threads of the key agent.

According to one more aspect of the invention there is provided a system for decrypting a Secure Socket Layer SSL pre master key in a computing environment having a user mode and a kernel mode comprising a memory comprising the following components 

According to one more aspect of the invention there is provided a system for inspecting an encrypted packet in a computing environment having a user mode and a kernel mode the system comprising a memory including 

The passive SSL engine further comprises means for continuing to decrypt packets and to inspect the decrypted packets until the encrypted session is terminated.

The system further comprises means for terminating the encrypted session based on the content of the decrypted packets.

According to yet one more aspect of the present invention there is provided a system for initiating a Secure Socket Layer SSL session using a handshake protocol in a computing environment having a user mode and a kernel mode the system comprising a memory including 

The progress of a typical SSL session may be divided into two phases a handshake phase for setting up the session and a stream decryption phase. In the handshake phase public key technology is used to derive secret session keys to be used in the decryption of the encrypted SSL data streams.

The cryptographic operations that deal with the public keys will be referred to collectively as asymmetric cryptographic operations because their efficacy is based on the public key premise under which it is easy to encrypt data using the public key but for all practical purposes impossible to decrypt unless one has the private key. The computational effort to perform the asymmetrical cryptographic operations is high due to the use of very large keys which are typically 128 of bytes or larger. Because the asymmetrical cryptographic operations are only used in setting up a cryptographic SSL session the computational expense is normally accepted but even so hardware accelerators and key stores are sometimes used to offload the central processor.

A purpose of the SSL handshake phase is for the two ends of the connection that is a client and a server to negotiate a secret pre master key. From the pre master a master key a master secret in the terminology of 1 is derived with which the subsequent SSL data stream is encoded at one end of the connection and decoded at the other. The same key is used in both operations which are referred as symmetric cryptographic operations . The pre master key and the master key are typically much shorter than the public keys and the symmetric cryptographic operations are very efficiently performed by modern processors.

Network protocol operations are commonly performed by the kernel of modern operating systems that follow the UNIX model such as Linux Mac OSX Object Linking and Embedding Control Extension and Windows . The kernel is generally reliable and handles hardware software interactions such as network interfaces. It communicates with application software that normally runs in user space through software interfaces or APIs Application Process Interface . Some kernel modules are also referred to as drivers with a simple API or an Input Output Control Interface IOCTL . Relevant to the present discussion is the fact that context switching between user processes and kernel processes is time consuming and to allow responsive multi process operation of the computer system no process can be allowed to run uninterruptedly for long periods of time.

All much or only some of the data to be processed by the Deep Packet Inspection Engine may be in the form of encrypted SSL data streams but only encrypted packets are of interest here. Packets arriving from a network interface are passed into the SSL Handshake which performs the standard SSL handshake protocol to initiate an encrypted session. The SSL Driver participates in the SSL handshake by receiving key requests and passing asymmetric encrypted pre master keys to the Key Agent . The Key Agent performs the compute intensive operations that are required to decrypt each asymmetric encrypted pre master key and sends a corresponding decrypted pre master key back to the SSL Driver . The SSL Driver then generates a secret master key from the decrypted pre master key according to the standard specification and sends the secret master key to the Deep Packet Inspection Engine . Details of the SSL handshake including key exchanges are described in the RFC 4346 cited above only a cursory description being offered here for convenience.

Encrypted SSL data streams are then passed to the Deep Packet Inspection Engine where they may be decrypted using the secret master key in a standard manner for analysis including deep packet inspection in the same way as other non SSL data streams would be analyzed.

With the Deep Packet Inspection Engine and other functionality not shown the software package provides firewall functions such as intrusion detection including the capability that encrypted data streams be decrypted for inspection before either suppressing or passing the encrypted data stream on to the intended recipient for example an HTML server or client application on the same host or to a local network.

The embodiment of the invention provides offloading the kernel mode from the asymmetric cryptographic operations that are required for deriving secret SSL master keys to be used in the decryption and subsequent inspection of encrypted SSL data streams as well as the design of the kernel mode driver.

The passive SSL decryption of data streams requires symmetric cryptographic keys i.e. the master keys that are derived using pre master keys which in turn are generated with asymmetric cryptographic methods. For reasons such as code size lengthy decryption times possible support of third party hardware acceleration and key stores in the embodiment of the present invention the asymmetric part of the process is implemented as a user mode software process in the form of the Key Agent coupled to the SSL Driver that is implemented as a kernel mode software process.

Asymmetric decryption is a computationally heavy process that is not well suited for implementation within an operating system kernel mode driver for the following reasons 

Thus in the present the invention the asymmetric decryption operations are implemented as a user mode software component the Key Agent and the symmetric decryption operations are implemented in an operating system kernel mode driver the SSL Driver .

This requires that the asymmetrically encrypted key information i.e. the asymmetric encrypted pre master key is communicated from the kernel mode driver to the user mode software component and the decrypted key information i.e. the decrypted pre master key is communicated back from the user mode component i.e. the Key Agent to the kernel mode driver i.e. the SSL Driver .

In this way it is possible to take advantage of facilities such as threading concurrency and preemptive symmetric multi processing SMP processing that are available in the user mode of operating systems.

Although the software package the Third Brigade Deep Security Agent software package includes of a number of components only the kernel mode driver the SSL Driver and the user mode agent the Key Agent and the interaction therebetween are directly of interest with respect to the present invention.

Roles of the SSL Driver include intercepting network traffic at the network transport layer modifying inserting and deleting packets at its discretion based upon well defined rules thus implementing a network security device.

As indicated earlier a common method of protecting network data transmitted between hosts is to encrypt the data via the SSL protocol RFC 4346 at the application layer. In contrast in order to secure a host against unwanted network intrusion the Driver component must be able to analyze the raw or unencrypted form of the data.

The SSL Driver implements a Passive SSL Engine which besides ensuring the validity of the SSL protocol is also used to decrypt the SSL traffic stream for analysis by the Payload Engine in the Deep Packet Inspection Engine . The deep packet inspection is the reason why SSL decryption is required.

The SSL request device is a virtual device that is dynamically created to be used by the Key Agent for acquiring the asymmetric encrypted SSL pre master key s the SSL Response Device is a virtual device by which the Key Agent communicates the results of the decryption s i.e. the decrypted pre master key back to the SSL Driver . Virtual devices are commonly known software structures used as a convenience to provide a simple interface between the Key Agent and the SSL Driver .

The Key Agent opens and executes a blocking read on the SSL request device unblocking only when the SSL Driver inserts one or more encrypted keys into the Decryption Request Queue associated with the SSL request device .

The SSL State Machine monitors the traffic stream implied not shown in for SSL protocol messages. When triggered by the ClientKeyExchange handshake message of the SSL protocol see 1 for protocol details the SSL State Machine adds encrypted keys into the Decryption Request Queue .

The Key Agent when unblocked will read one or more encrypted keys from the Decryption Request Queue through the SSL Request Device i.e. the asymmetric encrypted pre master key .

The Key Agent will then attempt to decrypt asymmetric encoded pre master key using a provided asymmetric private key as described in 1 . In both instances of a successful or an unsuccessful decryption of the asymmetric encrypted pre master key the Key Agent will send a response that is either the decrypted pre master key or an error indicator respectively into the SSL Driver via the SSL Response Device which makes the decrypted key available to the SSL State Machine .

The Key Agent obtains asymmetric encrypted pre master keys from the SSL Driver . The asymmetric encrypted pre master keys are contained in data records known as decryption requests or decryption request records . The methods for passing the decryption requests from the SSL Driver to the Key Agent are described in more detail in the following and .

The SSL State Machine further includes a Passive SSL Engine that includes common SSL protocol and decryption functions that are outside the scope of the invention.

The Passive SSL Engine of the SSL State Machine monitors the traffic stream for SSL protocol messages and passes such messages to the step Analyze SSL handshake protocol . Each SSL protocol message is compared with the ClientKeyExchange message type. If it is not a ClientKeyExchange message as indicated by the decision step SSL ClientKeyExchange determination No the analysis of the SSL Handshake protocol continues and loops back to the step Analyze SSL handshake protocol otherwise the step Add Encrypted Pre master key to Request Queue is executed which adds the encrypted keys of the ClientKeyExchange message into the Decryption Request Queue . The encrypted keys i.e. the asymmetric encrypted pre master keys that are queued in the Decryption Request Queue are then available to be passed through the SSL Request Device to the Key Agent as described above. After a successful decryption of the encrypted pre master keys the decrypted pre master key is forwarded from the Key Agent to the SSL State Machine via the SSL Response Device and to the Passive SSL Engine in the step Pass the decrypted pre master key . Subsequent processing of the decrypted pre master key in the Passive SSL Engine is beyond the scope of the present invention.

Key decryption requests i.e. the asymmetric encrypted pre master keys are passed from the SSL Driver to the Decryption Request Reader Thread of the Key Agent . The received encrypted pre master keys are stored in the Agent Request Queue by the Decryption Request Reader Thread . Concurrently Key Decryption Threads service the Agent Request Queue decrypt the pre master keys and forward the decrypted pre master key back to the SSL Driver . It may be noted that the Agent Request Queue has a finite capacity and it is possible that the queue becomes full because the Key Agent may have been preempted by other tasks and not been able to service the queue in time before additional decryption requests arrive. In this case an Error Response is transmitted from the Decryption Request Reader Thread to the SSL Driver to indicate that a request could not be stored. In the preferred embodiment of the invention the SSL Driver then cancels the corresponding attempt to set up an SSL session.

Flow charts of the Decryption Request Reader Thread and the Key Decryption Threads are shown in the following respectively. The Key Agent may operate in a multi thread environment in order to take advantage of multi CPU machines and so achieve higher performance than a single thread design.

The decryption request records which include the asymmetric encrypted pre master keys are received from the SSL Request Device of the SSL Driver in the step Read decryption request records from driver . The next step is Is Queue full in which the state of the Agent Request Queue is determined. If the queue is full Yes from the step Is Queue full the step Send error response to driver is executed in which the Error Response is sent to the SSL Response Device of the SSL Driver and execution flow returns to the step Read decryption request records from driver . As long as the queue is full additional decryption requests continue to be denied until such time as room becomes available in the queue i.e. until the Key Decryption Threads have serviced the queue and removed at least one decryption request record see below .

If the queue is not full No from the step Is Queue full the step Add decryption request record to queue is executed in which the decryption request record obtained in the step Read decryption request records from driver is put into the Agent Request Queue .

Execution of the step Remove one decryption request record from queue is performed whenever a decryption request is available in the Agent Request Queue otherwise the thread sleeps until it is awakened by the operating system in a standard manner. The methods by which different computer operating systems handle threads vary and are outside the scope of the present invention. It may be recalled that decryption requests which include encrypted pre master keys were put into this queue in the step Add decryption request record to queue of the Decryption Request Reader Thread .

According to the SSL standard decryption can only be performed when the appropriate private key is available see the RFC 4346 cited above. Following removal of the decryption request from the queue in the step a search and determination is made in the following step Is private key available . If the required private key is not available exit No from the step Is private key available execution is directed to the step Send error response to driver in which the error response is sent to the SSL Response Device in the SSL Driver . After the step Send error response to driver execution returns to the step Remove one decryption request record from queue in which the thread fetches the next decryption request if one is available.

The determination of Is private key available may be handled as a configuration issue. In the preferred embodiment of the invention the agent and driver are configured via user supplied configuration data which specifies which SSL key to use for a particular TCP port on the local machine.

If the required private key is available exit Yes from the step Is private key available execution continues with the step Decrypt SSL pre master key using standard APIs in which the pre master key is computed according to standard practice i.e. by calling routines in a decryption library using standard APIs Application Programming Interfaces . At this stage decryption may fail due to any of a number of reasons. In the next step Did decryption succeed such a determination is made. If decryption did not succeed exit No from the step Did decryption succeed execution is directed to the step Send error response to driver in which the error response is sent to the SSL Response Device . If decryption did succeed exit Yes from the step Did decryption succeed execution continues with the step Send pre master key to driver in which the pre master key is sent to the SSL Response Device of the SSL Driver . After the step Send pre master key to driver execution returns to the step Remove one decryption request record from queue in which the thread fetches the next decryption request if one is available.

Multiple instances of Key Decryption Threads may be active simultaneously to advantage for example in a multiprocessor host each thread to take a decryption record off the shared Agent Request Queue to decrypt the included asymmetric encrypted pre master key into the decrypted pre master key to be sent to the SSL Response Device using the steps outlined in the . An advantage of the present invention with multiple instances of Key Decryption Threads is due to the fact that the high computational effort to decrypt a pre master key an effort that is considerably higher than the comparatively trivial computational effort required to receive and queue the key can be performed efficiently by threads potentially running in parallel in multiple processors or multiple processor cores.

The system for decrypting a Secure Socket Layer SSL pre master key in a computing environment having a user mode and a kernel mode of the embodiment of the present invention comprises a computer having a computer readable means in the form for example of a memory for storing instructions to cause the computer to perform the steps of the methods of the present invention as described above.

The system and methods of the invention have been devised to efficiently handle the computationally expensive decryption of the pre master keys that are used in the SSL session initiation thus enabling the subsequent decryption and monitoring of the payload contents of the SSL packet streams.

Although the embodiment of the invention has been described in detail it will be apparent to one skilled in the art that variations and modifications to the embodiment may be made within the scope of the following claims.

