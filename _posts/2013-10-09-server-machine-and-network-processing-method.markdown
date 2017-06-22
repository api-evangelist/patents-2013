---

title: Server machine and network processing method
abstract: A server machine comprises a packet dispatching processor for retrieving a destination application group of a communication packet based on first identification information included in a communication packet received by any of a plurality of ports and first management information; for retrieving a plurality of endpoints based on second identification information included in the communication packet and second management information; and for dispatching the communication packet to a server application corresponding to any of the plurality of the retrieved endpoints and belonging to the retrieved application group.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09077718&OS=09077718&RS=09077718
owner: HITACHI, LTD.
number: 09077718
owner_city: Tokyo
owner_country: JP
publication_date: 20131009
---
This application is a continuation application of U.S. application Ser. No. 12 050 282 filed Mar. 18 2008 and which application relates to and claims priority from Japanese Patent Application No. 2008 18205 filed on Jan. 29 2008 the entire disclosures of which are incorporated herein by reference.

The invention relates generally to network processing in an operating system hereinafter referred to as OS and is a technique applicable to server applications such as a WEB server and file server and to consolidation of NAS Network Attached Storage .

In order to consolidate the operation management of a server machine and to reduce management costs consolidation is suggested in which the same kinds of services provided by each server application in a plurality of server machines are consolidated in a single server machine. The service indicates for example a WEB service or NFS service and enables to utilize software features via a network.

Usually a server application in each server machine uses a particular address called an ANY address as an address for expecting a request issued by a client. The ANY address is a technique capable of expecting all requests sent to IP addresses held in the server machine for example see W. Richard Stevens UNIX Network Programming p.p. 278 289 Prentice Hall PTR 1990 .

When each server machine consolidates server applications hereinafter referred to as same server applications providing the same kinds of services a plurality of the same server applications cannot be simply run on a single server machine.

If a plurality of the same server applications simply runs on a single server machine it means that the server machine has a plurality of server applications with ANY addresses for expecting requests and the server machine cannot determine which server application the requests should be received at.

For example the following method for consolidation is suggested. First a method using virtual machine software is suggested. The virtual machine software is capable of providing a plurality of virtual machines on a single server machine. An independent OS can run in each virtual machine. Consolidation can be achieved by providing one virtual machine for each consolidation source sever machine and running the same kinds of server application on each virtual machine see a http www.vmware.com pdf virtualization.pdf b http www.vmware.com files pdf VMware paravirtualization.pdf and c http www.vmware.com pdf virtualization considerations.pdf .

In another method consolidation is achieved in a single server application on a single server machine by integrating configuration information on the service provided in a plurality of server machines. For example when each server machine individually manages user information on services user information is integrated beforehand.

Accordingly in order to achieve consolidation a plurality of the same applications cannot be simply run on a single server machine so there is no choice but to employ either a method using a virtual machine as described above or a method of integrating configuration information on the service into a single application.

It is an object of the present invention to provide a server machine and network processing method capable of running a plurality of same server applications at a time on a single OS in a single sever machine without employing a method using a virtual machine in which memory usage in the server machine and the CPU load are large or a method of integrating configuration information on the service into a single application.

According to an aspect of the invention a server machine connected to one or more client computers via a network comprises a plurality of ports a plurality of application groups to which a plurality of server applications providing services belong first management information associating the application group with first identification information used by a server application belonging to the application group second management information associating second identification information identifying the plurality of ports with a plurality of endpoints consisting of a set of the first identification information and the second identification information and a packet dispatching processor for retrieving a destination application group of a communication packet based on first identification information included in the communication packet received by any of the plurality of ports and the first management information for retrieving a plurality of endpoints based on second identification information included in the communication packet and the second management information and for dispatching the communication packet to a server application corresponding to any of the plurality of the retrieved endpoints and belonging to the retrieved application group.

Accordingly a communication packet can be dispatched to a designated server application even when a server machine has a plurality of same server applications. Thus the server machine in the invention can run a plurality of same server applications at a time on a single OS.

According to another aspect of the invention a network processing method for a server machine connected to one or more client computers via a network comprises a first association step for associating a plurality of application groups to which a plurality of server applications providing services belong with first identification information that can be used by a server application belonging to the application group as first management information a second association step for associating second identification information identifying the plurality of ports with a plurality of endpoints consisting of a set of the first identification information and the second identification information as second management information and a packet dispatching processing step for retrieving a destination application group of a communication packet based on first identification information included in the communication packet received by any of the plurality of ports and the first management information for retrieving a plurality of endpoints based on second identification information included in the communication packet and the second management information and for dispatching the communication packet to a server application corresponding to any of the plurality of the retrieved endpoints and belonging to the retrieved application group.

Consequently a communication packet can be dispatched to a designated server application even when a server machine has a plurality of same server applications. Thus the server machine in the invention can run a plurality of the same server applications at a time on a single OS.

According to the present invention it is possible to run a plurality of same server applications which expect requests by using an ANY address on a single OS in a single server machine at a time.

Also a single server machine is capable of dispatching requests from a client and dispatching the requests without fail even when there is a plurality of same server applications.

The same services operated on a plurality of server machines can be consolidated onto a single server machine without modifying an existing server application and the single server machine can be used as a server consolidation.

Other aspects and advantages of the invention will be apparent from the following description and the appended claims.

An embodiment of the present invention will be described below with reference to the attached drawings.

 1 shown in represents a computer system according to a first embodiment. The computer system is configured so that a server machine is connected via LAN to a plurality of client computers hereinafter simply referred to as clients .

The network interface is connected to the LAN and is an interface for communicating with the client by using a network protocol such as TCP Transmission Control Protocol or UDP User Datagram Protocol .

The memory is for example semiconductor memory and stores data to which the CPU and the program executed by the CPU refers. More specifically the memory stores server applications A C in an operating system mentioned as an OS in drawings a network processing unit which is a program a process management table an ANY address management table a socket management table a routing table and a network interface setting program which makes requests to the OS to set and delete network interface IP addresses.

The CPU is a processor for controlling the actions of the server machine . The CPU executes programs such as the server applications A C on the OS or the network processing unit that are stored in the memory .

The server applications A C are applications for providing the client with services related to files web email and ftp. The server applications A C may be applications in a user space within the OS or may be applications in a kernel space within the OS. Furthermore the number of applications is not limited.

In the first embodiment plural server applications of three server applications including A B and C which provide the services run.

The OS groups a process family by adding identification numbers called VNAS Virtual NAS IDs to all processes including the server application . Here a process means programs including the server application that are being executed by the server machine . In three VNAS sets A B and C are formed where one VNAS set consists of three server applications A B and C that provide different types of services. The VNAS groups different type sever applications into one group and more than one VNAS exists in the single OS . Also the VNASA B and C are process families that are supposed to be provided by each of three server machines. Incidentally the process configurations of each group do not necessarily match one another. Furthermore they are respectively described as the server application and VNAS unless expressly indicated otherwise.

A request from the client is included in a communication packet hereinafter simply referred to as the packet and sent to the server machine . When the request arrives at the network interface in the server machine via the LAN the network processing unit in the OS determines which of destination server applications A C in a plurality of the VNAS the request is addressed to based on information in various management tables .

The network processing unit is a program for sending and receiving a packet and for managing the network interface . The network processing unit includes a packet receiving processor a packet sending processor and a network interface manager .

The packet receiving processor executes processing for delivering the packet of the request received from the client via the network interface to server applications A C. The packet receiving processor includes a packet dispatching processor .

The packet dispatching processor determines which type of server application A C the packet should be delivered to and when there is more than one same type server application the packet dispatching processor determines which of the same server applications in the VNASA C the packet should be delivered to. The packet dispatching processor will be explained in a flowchart described later below.

The packet sending processor executes processing for sending the packet to the client via the network interface based on a packet sending request from the server application . The packet sending processor includes a source address setting processor .

The source address setting processor executes processing for setting an IP address a first identification available to the server application that issued the packet sending request as a source address of the packet. The source address setting processor will be explained in a flowchart described later below.

The network interface manager executes processing for assigning IP addresses and enabling the network interface hereinafter referred to as validation and executes processing for deleting the IP address and disabling the network interface hereinafter referred to as invalidation .

Also the network interface manager executes processing for registering and deleting values in the ANY address management table as well as the validation and invalidation of the network interface . The network interface manager includes an interface validation processor and interface invalidation processor . The interface validation processor and interface invalidation processor will be explained in a flowchart described later below.

The process management table is a table for managing all process information on the OS including the process of the server application .

The process management table mainly includes a PID column for a process identification number uniquely added to each process in the order it runs and a VNAS ID column for the identification number of the VNAS to which the process belongs. Management information such as that concerning resources used by processes is stored in another column .

The VNAS identification number is used for distinguishing the IP addresses available for each process. When the server machine runs more than one same server application expecting a request by using an ANY address a process is generated beforehand with a different VNAS identification number so that each server application can expect a request with a different IP address.

Here an example of grouping a process family into a VNAS group will be described. A pattern diagram of a process tree a tree structure showing the parentage between processes according to the first embodiment is shown in .

The following will be described in the situation where the ID for example VNAS is assigned to the process . The copy source process of the new process can be generated by calling a fork system call . In that case the copy source process is called a parent process and the newly generated process is called a child process. When continuing to generate the new processes the copy source process calls the fork system call . In that case the copy source process is called a parent process and the newly generated processes are called child processes. Thus when generating the child process from the parent process by using the fork system call the OS adds the assigned VNAS ID to the parent process.

Meanwhile when generating the child process from the parent process by using a vnas start system call provided in the first embodiment it is possible to designate the VNAS identification number assigned to the child process. For example if the process to which the ID VNAS assigned is called the vnas start system call and one of the VNAS IDs is designated then a new process to which the designated ID VNAS is assigned is generated. In that case the copy source process is called a parent process and the newly generated process is called a child process. 

Following the above the process generates the process by using the fork system call and the process generates the processes by using the fork system call in the same manner as that in the above described process generation.

The process families are grouped into a process family having the same VNAS ID. The process groups grouped in that manner are groups A C. For example the process belonging to the VNAS and the process belonging to the VNAS correspond to the same server application A and the process belonging to the VNAS and the process belonging to the VNAS correspond to the same server application B.

In the first embodiment the fork system call was explained with example as a process generating method for the OS however any API Application Programming Interface may be used if it is intended for use in generating a process. Also in the present embodiment the vnas start system call was used when adding an ID different from the ID of the VNAS to which the parent process belongs however the system call which is different from the vnas start system call may be used as long as the child process can be generated by adding an ID different from the ID of the VNAS to which the parent process belongs.

The ANY address management table is a table for managing the correspondence relationship of the VNAS and IP addresses. The ANY address management table includes an IP address column a VNAS ID column and a network interface column .

For example shows that IP and IP are available in the VNAS and IP is available in the VNAS. It also shows that IP is set for eth IP is set for eth and IP is set for eth.

Incidentally the interface recorded on the network interface is not limited to a physical interface. The interface recorded on the network interface may be a virtual interface created in the OS . Specifically it may be an interface bonding more than one physical interface an interface duplicated using a VLAN Virtual LAN identification number or an interface duplicated as software in order to assign a different IP address alias to the same physical virtual interface.

Furthermore in the first embodiment ANY address management information is held in the ANY address management table format however the format may be a list structure instead of a table structure. Specifically when ANY address management information INFO is considered as one data structure the list structure may be connected to a plurality of data structures. Also more than one table structure or list structure may be created for each VLAN identification number.

The socket management table is a table for managing a send receive channel where the server application expects a packet and is a table for managing the correspondence relationship of a socket a destination port number a second identification and the VNAS. Here the socket is an endpoint consisting of a pair of an IP address and a destination port number is arranged in each server application and indicates the end point sending receiving channel of a network communication path between the server application and the client .

Moreover the socket management table consists of a port table and a socket table associated with the destination port numbers entered in the port table .

The port table is a table for managing destination port numbers assigned in order to identify the kind of services provided by the server application and includes a destination port number column . For example among a plurality of server applications server applications assigned the same port numbers are the same server applications providing the same services.

Specifically the port number No. 80 is assigned to a server application providing a web service the port number No. 3020 is assigned to a server application providing a CIFS service and the port number No. 2049 is assigned to a server application providing an NFS service.

Thus the port number to be assigned is determined in correspondence with the kinds of services with which the server applications provide. Therefore the client sends a request in which a destination port number is designated the kind of services is designated to the server machine .

The socket table is provided for each port number and it is a table for managing sockets with the same port numbers.

The socket table mainly includes a recipient address column indicating an IP address available to receive a packet a PID column for recording the identification number for a process generating a socket and a VNAS ID column for recording the VNAS identification number.

The same identification number as that registered in the VNAS ID column in the process management table is registered in the VNAS ID column .

Incidentally management information such as that concerning resources used by a socket is stored in another column. Also the socket table shown in is created for each port number and they are subdivided into A B and C respectively. However if it is not necessary to subdivide them when describing the embodiment they will simply be described with the reference number . The same applies for the columns and .

Each socket can receive only a packet directed to the IP address registered in the recipient address column . However as an exception an ANY address indicates that it is possible to receive a packet directed to any address. A normal server application is implemented so that it can receive requests packets directed to all IP addresses in the server machine by setting an ANY address as a socket.

Existing server machines cannot hold more than one socket to which an ANY address is assigned in socket tables associated with one and the same port number so a plurality of the same server applications server applications using the same port numbers cannot be executed at one time.

In the server machine in the first embodiment it is allowed to hold more than one socket for which an ANY address is designated so it is possible to execute a plurality of the same server applications belonging to different VNASs.

Therefore more than one socket for which an ANY address is designated is registered in a socket table provided for each of the same port numbers.

The socket table is used for determining from among a plurality of sockets for which an ANY address is set as a recipient address which socket of the server application the packet from the client should be delivered to.

The routing table is a table for managing the network interface which is available when the server machine sends a packet to the client . The routing table includes a network address column indicating a LAN identification number and a network interface column . For example as shown in when the server machine sends a packet to the client on the LAN with the network address 192.168.10.0 the network interface corresponding to the eth1 is provided to be used. Incidentally if there is no relevant network address in the table the interface corresponding to the default and eth0 is used.

A header is always added at the head of a packet and paths can be chosen in accordance with the header. In the first embodiment when sending a packet from the client to the server machine the IP address of the client is stored in a source address area among the specific areas of the packet . The IP address of the server machine is stored in a destination address area . On the other hand when returning a packet from the server machine to the client the stored location of the IP addresses of the server machine and client machine will be replaced one another. If the server machine is a source destination the IP address of the server machine is stored in a source and destination address area and then data communicated by IP is stored in a data area . Packet s of upper level protocols such as TCP or UDP is are stored in the data area in the first embodiment.

In the first embodiment an IPv4 packet is used as a protocol for a network communication. However it does not have to be the IPv4 packet and an IPv6 or similar protocol specification packet may be used. Furthermore TCP is used as an upper level protocol of IPv4 in the embodiment. However UDP or other protocols may be used as long as it includes information for determining the kind of destination service destination port number .

The packet dispatch processing in which the server machine dispatches packets from the client to each socket will be described with reference to the above described various tables. The packet dispatch processing is executed by the CPU in accordance with a packet dispatching processor in a packet receiving processor .

Specifically as shown in the CPU starts the packet dispatch processing when a packet from the client arrives at the server machine S .

First the CPU checks whether or not the destination IP address of the packet is a loopback address S . A loopback address is a special IP address designated in order for a process in the server machine to communicate with a process server application in the same server machine .

If the destination IP address of the packet is a loopback address S YES the CPU retrieves the identification number of the VNAS to which the source process of the packet belongs as the dispatch destination VNAS identification number S . In that case the CPU cannot identify which VNAS the communication was directed to by using the destination IP address of the packet as a key because the destination IP address is a loopback address. Therefore the CPU dispatches packets to sockets with the same VNAS identification number as that of the packet source process.

Meanwhile if the destination IP address of the packet is not a loopback address S NO the CPU refers to the ANY address management table by using the destination IP address of the packet as a key and retrieves the VNAS identification number associated with the destination IP address as a dispatch destination VNAS identification number S .

When the dispatch destination VNAS identification number is determined the CPU looks for the destination port number by using the destination port number of a packet as a key and with reference to the port table . And after the CPU looks for the destination port number it retrieves a socket table associated with the aforementioned port number S .

The CPU retrieves socket information in the order of being registered in the socket table S and then the CPU judges whether or not the recipient address of the socket is registered as an ANY address S .

If the CPU judges that the socket is registered as an ANY address S YES it goes on to judge whether or not the VNAS identification number in the socket table and the dispatch destination VNAS identification number for the packet are equivalent to one another S .

If the CPU judges that they are not equivalent to one another S NO the CPU retrieves the next piece of socket information registered in the socket table S and then executes the processing in step S.

If the CPU judges that they are equivalent to one another S YES the CPU delivers the packet to the socket judged as being equivalent S and then terminates the packet dispatch processing S .

Meanwhile in step S if the CPU judges that the recipient address of the socket is not registered as an ANY address S NO it judges whether or not the recipient address of the socket and the destination IP address of the packet are equivalent to one another S .

If the CPU judges that they are not equivalent to one another S NO the CPU retrieves the next piece of socket information registered in the socket table S and then executes the processing in step S.

If the CPU judges that they are equivalent to one another S YES the CPU delivers the packet to the socket judged as being equivalent S and then terminates the packet dispatch processing S .

According to the above described flow chart a packet received from a process in the client or the server machine is dispatched to a server application with particular VNAS identification number based on the destination IP address and the VNAS identification number.

Next the source address setting processing for setting source addresses when a process server application receives a request from the client or the server machine replies will be described. The source address setting processing is executed by the CPU in accordance with a source address setting processor .

As shown in the CPU starts the source address setting processing when a dispatched process server application replies to a request from the client or the server machine S .

The CPU retrieves the VNAS identification number for the source process server application of a packet from the process management table S .

Next the CPU refers to a routing table and retrieves information on the network interface used for returning a packet in response to a request from the client or the server machine S .

The CPU then judges whether or not the VNAS identification number retrieved in step S and the network interface retrieved in step S are respectively equivalent to the VNAS identification number and the network interface in ANY address management information INFO S .

If the CPU judges that they are not equivalent S NO it returns to step S retrieves a next ANY address management information INFO and executes the processing in step S.

Meanwhile if the CPU judges that they are equivalent S YES the CPU sets the IP address of the ANY address management information INFO to the source address of the packet to be sent S and then terminates the source address setting processing S .

According to the above described flow chart the CPU can set the source IP address of a packet based on the identification number of the VNAS to which the source server application belongs.

Next the interface validation processing for enabling the network interface by adding an IP address will be described. The interface validation processing is executed by the CPU in accordance with the interface validation processor .

As shown in the CPU starts the interface validation processing when the process in the network interface setting program is generated and an IP address setting is requested S .

The CPU judges whether or not an IP address to be added to the network interface has been registered in the ANY address management table S .

If the IP address is not yet registered S NO the CPU enables the network interface by adding an IP address to the network interface S .

Next the CPU retrieves the identification number of a VNAS to which a process requesting the interface validation processing belongs from the process management table S . Here the process requesting the interface validation processing indicates a process in the interface setting program .

After the CPU registers the pair of the set IP address the identification number of the VNAS to which the process requesting the interface validation processing belongs and the network interface to which the IP address is added as ANY address management information INFO in the ANY address management table S the CPU then terminates the interface validation processing S .

Incidentally in step S if the IP address has been registered S YES the CPU terminates the interface validation processing S .

According to the above described flow chart the network interface is validated and enabled. At the same time the IP address set for the network interface becomes available for a process family belonging to the same VNAS as that to which the process requesting the interface validation processing belongs.

Next the interface invalidation processing for disabling a network interface by deleting the IP address added to the network interface when stopping all process families belonging to the same VNAS will be described. The interface invalidation processing is executed by the CPU in accordance with the interface invalidation processor .

As shown in the CPU starts the interface invalidation processing when the process in the network interface setting program is generated and an IP address deletion is requested S .

First the CPU retrieves the identification number of the VNAS to which a process requesting the interface invalidation processing belongs from the process management table S . The CPU judges whether or not a pair of an IP address added to the network interface to be invalidated and a VNAS identification number has been registered in the ANY address management table S .

If a pair has been registered S YES the CPU disables the network interface by detaching the IP address added to the network interface S .

The CPU deletes the set of the IP address of the invalidated network interface a VNAS identification number and the network interface to which an IP address is added from the ANY address management table S and then terminates the interface invalidation processing S .

Incidentally in step S if the pair is not yet registered S NO the CPU terminates the interface invalidation processing S .

According to the above described flow chart the network interface is invalidated and disabled. At the same time the IP address set for the network interface becomes unavailable for a process family belonging to the same VNAS as that to which the process requesting the interface invalidation processing belongs.

In that case the ANY address management tables A C include an IP address column A C and a network interface column A C. The respective columns have features similar to those of the respective columns described with reference to .

Furthermore item columns in a socket management table created for each port mainly include a recipient address column and a PID column . Thus a IP address available to receive a packet may be held in other ANY address management table as a table and the IP address may be associated with a VNAS.

According to the embodiment it is possible to run a plurality of same server applications expecting requests by using an ANY address on a single OS in one server machine.

Also one server machine can recognize requests from a client and dispatch the requests without fail even when there is more than one same server application.

The same services operated on a plurality of server machines can be consolidated onto a single server machine without modifying an existing server application and the one server machine can be used as a server consolidation.

The present invention can be broadly applied in a computer system including one or more server machines or other types of computer systems.

While the invention has been described with respect to a limited number of embodiments those skilled in the art having benefit of this disclosure will appreciate that other embodiments can be devised that do not depart from the scope of the invention as disclosed herein. Accordingly the scope of the invention should be limited only by the attached claims.

