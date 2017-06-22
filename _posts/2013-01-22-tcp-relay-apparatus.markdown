---

title: TCP relay apparatus
abstract: An apparatus for terminating and replaying transmission control protocol (TCP) communication between a server and cellular phone is disclosed. The TCP relay apparatus performs precise control for each TCP connection in the process of executing default TCP transmission control for the server and performing wireless-optimized TCP transmission control for the cell phone while facilitating setup for determination of the type of a network to which a communication destination terminal belongs. The TCP relay apparatus includes a unit capable of setting TCP control information suitable for the characteristics of a network linked to the destination device on a per-TCP connection basis, a unit which enables an application program to instruct the TCP control information setting, and a unit which determines the network type by judging whether the connection is a passive connection to a listen port or a TCP connection to the server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09001650&OS=09001650&RS=09001650
owner: Hitachi, Ltd.
number: 09001650
owner_city: Tokyo
owner_country: JP
publication_date: 20130122
---
This application claims priority based on Japanese patent application No. 2012 102038 filed on Apr. 27 2012 the entire contents of which are incorporated herein by reference.

The subject matter as disclosed herein relates to a transmission control protocol TCP relay apparatus for relaying TCP communication performed between communication devices that are connected to respective networks having different characteristics.

In recent years cellular or mobile telecommunications systems are rapidly increasing year by year in the Internet related traffic flowing therein. This results from advances in high speed wireless communication technologies such as radio communication networks compliant with the long term evolution LTE or like standards. In mobile communications systems major characteristics of communications over wireless networks are such that these are broad in frequency band unlike wired networks and on the other hand are large in transfer delay thereby posing a risk that instantaneous communication interruption occurs due to hand over between base stations. It has been revealed that in networks of the type having such characteristics various kinds of application programs using a default transmission control protocol internet protocol TCP IP suffer from performance deterioration such as being unable to obtain sufficient throughputs.

Prior known performance improving schemes for suitably using the TCP in such network environments include a method for installing a TCP terminating and relaying apparatus between a mobile phone and server and for performing default TCP transmission control between the relay apparatus and the server while performing between the relay apparatus and the mobile phone TCP transmission control optimized for wireless networks.

United States Patent Application Publication US 2011 0125915 A1 referred to hereinafter as Literature 1 discloses therein a TCP transmission control device having a unit which sets up TCP transmission control information for use in a TCP connection to be established between a transmission side terminal and its chosen reception side terminal in compliance with the type of a network to which the reception terminal belongs. The TCP transmission control device disclosed in Literature 1 is specifically arranged to set up TCP transmission control information based on the kind of communication services and IP address routing information of the reception terminal.

By employing such an arrangement the transmission side device sets appropriate TCP transmission control information in accordance with a packet data communication network to which its associated opponent party s terminal belongs whereby it is possible to perform efficient TCP communication thus making it possible to appreciably shorten a retransmission time in packet loss events. In addition it becomes possible to set adequate TCP parameters in units of TCP connections with the use of existing architectures without having to modify the current TCP stack protocols. By arranging the TCP relay apparatus to have its ability to perform the TCP transmission control method disclosed in Literature 1 it becomes possible to make the efficiency of TCP communications between a cell phone and server improved.

The technique disclosed in Literature 1 assumes that the setting of TCP transmission control information is uniquely determinable on a per service basis. However it does not disclose a technique for providing precise control in units of TCP connections or the like.

Additionally the determination of a network to which the reception side terminal belongs is based on the routing information of IP address of such terminal. Unfortunately in ordinary mobile communications systems the reception side terminal is granted to have a wide variety of IP address domains. For this reason it is a must to set a large number of IP addresses in the transmission side terminal causing inconveniences as to system operations.

As one of the TCP transmission control information a minimal value of a retransmission timeout RTO period of TCP is disclosed. However it is unlikely that packet losses inducing the TCP retransmission always occur due to network congestions. For example when putting packets in an output queue existing in the IP layer of an operating system OS a queue overflow can take place resulting in packets being discarded from time to time. In such case when the minimum value of RTO period is set to a relatively large value the retransmission from TCP layer becomes longer in interval. This poses a problem which follows packets are hardly retransmitted regardless of the fact that the network is free from any congestion which in turn leads to delay or traffic jam of a TCP connection.

To solve the above stated problem the disclosures herein provides a TCP relay apparatus a first feature of which lies in having a unit capable of setting in units of TCP connections TCP control information adapted for the characteristics of a network to which is connected a communication destination device.

A second feature of the TCP relay apparatus disclosed herein is that it further includes a unit for enabling an application program running on an OS to instruct the setting of the TCP control information suitable for the characteristics of a network to which is connected a communication destination device without relying upon the OS s decision.

A third feature of the TCP relay apparatus disclosed herein is that it further includes a unit for determining or judging the type of the communication destination device s linked network depending upon whether a passive connection to a listen port or a TCP connection to a server device.

A fourth feature of the TCP relay apparatus is that it further includes a unit for distinguishing between packet discard due to a network congestion and packet discard due to an overflow of internal transmission queue of the OS for setting a minimum value of TCP RTO suitable for the network type in the case of the former and for setting a minimum value of default TCP RTO in the case of the latter.

Owing to the features installing the TCP terminating relaying apparatus between a mobile phone and server device makes it possible to provide precise control per TCP connection in the event of performing default TCP transmission control with respect to the server and performing for the mobile phone TCP transmission control suitable for wireless networks.

Another advantage is that it becomes easier to determine the type of a network to which the reception side terminal belongs.

A further advantage lies in an ability to suppress a phenomenon which follows in case the minimum TCP RTO value is set to a relatively large value a longer time is consumed before packet retransmission actually gets started resulting in deceleration of a TCP connection even when the network is free from congestions.

According to disclosures herein it becomes possible to sustain high communication quality without regard to the type of a network being connected.

The details of one or more implementations of the subject matter described in the specification are set forth in the accompanying drawings and the description below. Other features aspects and advantages of the subject matter will become apparent from the description the drawings and the claims.

The TCP relay apparatus also called the TCP repeater in some cases is operatively associated with a plurality of networks having different characteristics for relaying TCP communication between communication devices that are connected to networks respectively.

The TCP relay apparatus is presently in a state capable of communicating with a client device through a local area network LAN and a wireless network A .

The client device uses a protocol on transmission control protocol internet protocol TCP IP such as hypertext transfer protocol HTTP to establish a connection to a server device thereby performing service request.

The TCP relay apparatus is also in a state capable of communicating with the server device via the LAN and a wired communication network A .

The server device is a device on which a server process operates for providing Web services or else to the client device .

A hardware configuration example of each of the client device TCP relay apparatus and server device is shown in .

Each of these devices is implementable by a general purpose computer which is made up of a central processing unit CPU a main storage unit typically a semiconductor memory an external storage device such as hard disk drive HDD a data readout device which reads data out of a removable and carriageable record media such as compact disc read only memory CD ROM digital versatile disc DVD or else an input output device such as a display monitor keyboard with or without a pointing device called the mouse a communication device used for connection with a network such as network interface card NIC or else and a bundle of internal data transfer lines such as buses for interconnection between respective devices.

For example a TCP information management region or domain to be later described is realized by use of a partial storage space of the main memory . Each device loads one of various kinds of software programs being stored in its associated external storage device into main storage device for execution of the loaded program by CPU and makes a connection with network using communication device to perform network communication with client device and server device thereby achieving various functions of respective processing units in this embodiment along with processing to be executed thereby.

As shown in the TCP relay apparatus includes a TCP relay processing unit subordinate communication processing unit socket API processing unit TCP processing unit IP processing unit network interface processing unit and TCP information management domain .

The TCP processor unit performs main processing of termination and relay interexchange of TCP communication between the client device and server device . The sub communication processor unit performs communication related processing other than the TCP relaying operation including middleware processing such as monitoring or surveillance of an operating state of TCP relay apparatus as an example. Note that the sub communication processor does not communicate directly with the device and server device .

The socket API processor unit provides the TCP processor and sub communication processor with an application programming interface API for connection establishment and data transmission reception in the form of a socket which is an abstractly created concept of TCP communication.

The socket API processor has a custom setup API . This API is for performing registration referencing alteration and deletion of a custom TCP setup as will be discussed later in the description.

The TCP relay processor performs communication data transmission reception with the client device and server device by calling the API of socket API processor .

The TCP processor performs TCP connection and data transfer reception control. The IP processor performs processing of the IP layer of TCP IP.

The IP processor internally has an output queue and performs upon transmission of a stream of IP packets to a network interface processing unit to be later described the queuing of IP packets until such transmission is completed.

The network interface processor is for control of a network interface device that sends and receives data to and from the LAN .

The TCP information management domain is a storage region for storing therein data or information used for TCP management and control. TCP information management domain has therein a default TCP setup storing therein default TCP setup information.

The TCP information management domain also has a socket parameter management table and custom TCP setup .

A detailed explanation will here be given of the socket parameter management table with reference to .

The socket parameter management table has as socket setup data a socket descriptor field classification field minimum retransmission timeout RTO value field maximum RTO value field and initial window size field .

The socket descriptor field is a region for storage of identifiers of sockets created by the TCP relay processor unit .

The classification field is a region for storage of network types such as wireless network wired network etc.

The minimum RTO value field is a region for storage of a minimum value synonymous with a lower limit value of RTO period.

The maximum RTO value field is a region for storage of a maximum i.e. upper limit value of RTO period.

The initial window size field is a region for storage of a value indicative of an initial size of TCP congestion window.

The information of socket parameter management table is subjected to registration alteration or deletion by the socket API processor and TCP processor .

The custom TCP setup has a classification field minimum RTO value field maximum RTO value field and initial window size field .

The classification field is a region for storage of network types such as wireless network wired network etc.

The minimum RTO value field is a region for storage of a minimum value i.e. lower limit value of RTO period.

The information of custom TCP setup undergoes registration alteration or deletion to be performed by the custom setup API and a custom TCP control unit .

An operation say TCP packet relaying process of the TCP relay apparatus of the embodiment 1 will be described with reference to below.

Firstly the TCP relay processor awaits a TCP connection from the client device at a listen port in step S .

A decision is made as to whether or not this TCP connection is a custom target object at step S . If Yes call the custom setup API and then pass thereto a socket descriptor and network type information step S .

The determination as to whether the accepted connection is a custom object may be carried out for example based on judging the inbound TCP connection is which one of a connection to a specific listen port number in the TCP relay apparatus from the client device and a connection to a specific listen port number from the TCP relay apparatus to server device . A practical example of such process is as follows. The TCP relay apparatus reads upon its start up a setup file which was prestored by a system administrator in TCP relay apparatus and which has a description indicating TCP listen port No. 8080 is assigned to wireless network A and port 8081 is allocated to wired network A and operates in conformity with the following judgment conditions TCP connection to the listen port 8080 is a wireless network A and TCP connection to listen port 8081 is a wired network A. 

If No at step S then the process proceeds to step S which receives data from the client device step S .

In accordance with the content of the data received TCP connection is established with respect to the server device at step S .

A decision is made to specify whether this TCP connection is a custom object at step S . If Yes call the custom setup API then pass a socket descriptor and network type information step S . A determination method of the custom object is the same as that in step S.

If No at step S the process goes to step S which relays TCP data between the client device and server device .

Upon completion of the relaying operation the process goes next to step S which breaks the TCP connection with the client device and server device followed by exiting the TCP relay processing.

See which is a flowchart of exemplary custom setup API processing to be performed using the custom setup API .

The custom setup API is responsive to receipt of a call from the TCP relay processor for starting its operation to confirm whether the socket descriptor passed thereto is a valid socket descriptor at step S .

If Yes then a search is conducted to find a custom TCP setup with the network type being as a search key resulting in acquisition of information on the minimum RTO value from an entry searched step S .

Further the classification information indicative of the network type and minimum RTO value are registered into an entry of the socket descriptor of the socket parameter management table .

The processing at step S may be modified to perform a process which includes conducting a search for custom TCP setup with the network type being as a search key to thereby acquire the information of maximum RTO value from an entry searched and registering the type data and maximum RTO value in an entry of the socket descriptor of socket parameter management table .

Alternatively the processing of step S may be modified to perform a process including conducting a search for custom TCP setup with the type as a search key to thereby obtain the information of initial window size from an entry searched and registering the type data and the value of such initial window size in an entry of the socket descriptor of socket parameter management table .

Still alternatively the processing of step S may be modified so that the information to be acquired from the custom TCP setup and the information to be registered in the entry of the socket descriptor of socket parameter management table may be any possible combinations of the minimum RTO value maximum RTO value and initial window size or all of them.

If the registration reason is packet discard at output queue in the IP processor traditional processing is performed which references the default TCP setup and acquires a default minimum RTO value at step S .

Then checking is done to determine whether an RTO value that was calculated from a round trip time RTT of the TCP is less than or equal to the default minimum RTO value step S . Note here that in a request for comments RFC one example of a method for calculating RTO value from RTT is shown.

If Yes at step S then the procedure goes to step S which registers the default minimum RTO value in the retransmission timer as RTO value. If No then the currently executed processing is ended instantly.

In case the examination at step S reveals that the registration reason is packet discard occurring over the network access is given to the socket setup information from socket parameter management table with the socket descriptor as a search key step S .

Then an RTO value that was computed from the TCP s RTT is compared with the minimum RTO value obtained from the socket setup information to thereby check whether the former is less than or equal to the latter step S .

If Yes at step S then register the minimum RTO value of socket setup information in the retransmission timer as RTO value step S . If No then quit the processing promptly.

The processing at any one of the steps S S and S S may be modified to use the maximum RTO value rather than the minimum RTO value or alternatively use both of these minimum and maximum RTO values.

An example is that in the case of using the maximum RTO value the step S may be arranged to obtain default minimum RTO value by reference to the default TCP setup .

Additionally the step S may be altered to check whether an RTO value computed from the TCP s RTT is greater than or equal to the default maximum RTO value. If Yes then register such default maximum RTO value in the retransmission timer as RTO value step S . If No then quit the processing instantly.

Optionally the step S may be modified to check whether an RTO value computed from the TCP s RTT is larger than or equal to the maximum RTO value obtained from the socket setup information if Yes then register the maximum RTO value of socket setup information in the retransmission timer as RTO value step S if No then exit the processing.

As the TCP connection to listen port is qualified as a custom object a need arises to perform additional processing i.e. calling of the custom setup API at step S .

A TCP connection to the server device is established in accordance with the content of such received data step S .

Processing is performed to relay TCP packet data between the client device and server device step S .

Upon completion of such relay processing the TCP connection with the client device and server device is closed i.e. cut off step S then quit the TCP relay processing.

As apparent from the foregoing in the illustrative embodiment it is possible by installing the TCP terminating relaying apparatus between a mobile phone and server to provide precise control on a per TCP connection basis in the process of performing default TCP transmission control with respect to the server and performing for the mobile phone TCP transmission control suitable for wireless networks. It is also possible to make easier the determination or judgment of a network to which the reception side terminal belongs. Furthermore it is possible to suppress or minimize a phenomenon which follows in case the minimum TCP RTO value is set to a relatively large value a long time is undesirably consumed before packet retransmission actually gets started resulting in deceleration of a TCP connection even when the network is free from any congestion.

Each of the embodiments shown above has been described as one example. Various modifications and applications may occur without being limited to disclosures herein.

Although the present disclosure has been described with reference to example embodiments those skilled in the art will recognize that various changes and modifications may be made in form and detail without departing from the spirit and scope of the claimed subject matter.

