---

title: Cluster system based on parallel computing framework, and host node, computing node and method for executing application therein
abstract: A cluster system based on a parallel computing framework is provided, and the cluster system includes a host node configured to execute a host program for a parallel computing framework and a computing node configured to be connected to the host node and execute a kernel program for the parallel computing frame work.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09485303&OS=09485303&RS=09485303
owner: Seoul National University R&DB Foundation
number: 09485303
owner_city: Seoul
owner_country: KR
publication_date: 20130104
---
This application claims the benefit under 35 U.S.C. 119 a of Korean Patent Application No. 10 2012 0001690 filed on Jan. 5 2012 the entire disclosure of which is incorporated herein by reference for all purposes.

Parallel computing refers to a form of computation in which many calculations are carried out simultaneously operating on the principle that large problems can often be divided into smaller ones which are then solved concurrently. There are several different forms of parallel computing bit level instruction level data and task parallelism. Parallelism has been employed for many years mainly in high performance computing but interest in it has grown lately due to the physical constraints preventing frequency scaling. As power consumption by computers has become a concern in recent years parallel computing has become the dominant paradigm in computer architecture mainly in the form of multicore processors.

A typical framework for parallel computers is OpenCL. OpenCL is a framework for writing programs that execute across heterogeneous platforms consisting of Central Processing Units CPUs Graphics Processing Units GPUs and other processors. OpenCL includes a language base on C99 for wiring kernels and Application Programming Interfaces APIs that are used to define and then control the platforms. OpenCL provides parallel computing using task based and data based parallelism.

Generally OpenCL operates in a single node system not in a cluster system which is nowadays widely used. Hence if a user wants to write an application for OpenCL the user has to use a message programming library to access a network. Such inconvenience makes it difficult to write an application. On top of that even though the user adds a code for OpenCL on his own OpenCL may not operate in a single node system.

The following descriptions relate to a cluster system a host node a computing node and a method for executing an application all of which help a parallel computing framework to be executed efficiently.

In one general aspect of the present invention a cluster system based on a parallel computing framework is provided and the cluster system includes a host node configured to execute a host program for a parallel computing framework and a computing node configured to be connected to the host node via a network and execute a kernel program for the parallel computing framework. The host node may generate a request message to request execution of a command related to the kernel program and transmit the generated request message to the computing node via the network. The host node and the computing node may generate a network message and execute an application consisting of a host program and a kernel program while exchanging the generated network message.

In another general aspect of the present invention a host node in a cluster system based on a parallel computing framework is provided and the host node includes a host thread configured to execute a host program for a parallel computing framework and insert a command related to a kernel program in a command queue which corresponds to a remote computing module capable of executing the kernel program for the parallel computing framework and a command scheduler configured to select a command to be executed by scheduling the command queue generate a request message to request execution of the selected command and transmit the request message to a computing node via a network.

In another general aspect of the present invention a computing node in a cluster system based on a parallel computing framework is provided and the computing node includes one or more computing module a command handler configured to receive a request message indicating a request for execution of a command related to a kernel program for a parallel computing framework from a remote host node which executes a host program in response to the request message generate a command object and insert the generated command object in a ready queue corresponding to the one or more computing modules and a module thread configured to execute the command using the command object inserted in the ready queue and the computing modules.

In another general aspect of the present invention a method for executing an application in a cluster system based on a parallel computing network is provided and the method includes in a host node inserting a command related to a kernel program for a parallel computing framework in a command queue corresponding to a remote computing module which executes the kernel program in the host node selecting a command to be executed by scheduling the command queue generating a request message to request execution of the selected command and transmitting the request message to a computing node in a computing node receiving the request message via a network in response to the request message generating a command object and inserting the generated command object in a ready queue corresponding to the one or more computing modules in the computing node executing the command using the command object inserted in the ready queues and the computing module and in the computing node generating a completion message to notify that execution of the command has been completed and transmitting the generated completion message to the host node via the network.

Other features and aspects will be apparent from the following detailed description the drawings and the claims.

Throughout the drawings and the detailed description unless otherwise described the same drawing reference numerals will be understood to refer to the same elements features and structures. The relative size and depiction of these elements may be exaggerated for clarity illustration and convenience.

The following description is provided to assist the reader in gaining a comprehensive understanding of the methods apparatuses and or systems described herein. Accordingly various changes modifications and equivalents of the methods apparatuses and or systems described herein will suggest themselves to those of ordinary skill in the art. Also descriptions of well known functions and constructions may be omitted for increased clarity and conciseness.

Referring to a cluster system according to an exemplary embodiment of the present invention includes a host node and a plurality of computing nodes . . . . The host node is connected to each of the computing nodes . . . via a network . The network may be wired or wireless. The host node and each of the computing nodes . . . are able to exchange information with each other using a network message. The network message may a LAN packet an IPv4 packet an IPv6 packet and the like.

The cluster system consists of parallel computing frameworks. That is a parallel computing framework according to an exemplary embodiment of the present invention is able to operate in the cluster system . The parallel computing framework for the cluster system is may be OpenCL OpenMP and CUDA.

An application for the parallel computing framework in the cluster system may consist of a host program and a kernel program. The host program may manage the kernel program to be executed and data computing may be processed in the kernel program. According to an exemplary embodiment of the present invention the host program may be executed in the host node and the kernel program may be executed in the computing nodes . . . 

The host node executes a host program. The host node may manage execution of the kernel program by executing a host program of an application written using a parallel computing programming tool. For example the host node is able to generate a request message to request execution of a command related to the kernel program and transmit the generated request message to the computing nodes . . . via the network .

The computing nodes . . . execute the kernel program. In response to receiving the request message indicating a request for execution of the command a computing node for example the computing node executes the command generates a completion message to notify that execution of the command has been completed and transmits the generated completion message to the host node .

Referring to a host node may include a host thread a command scheduler command queues an issue queue and a completion queue .

The host thread inserts a command in the command queue . The command queues may respectively correspond to computing modules and of the computing node . For example the first command queue included in the first command queue group is able to be mapped to the first computing module included in the first computing node . A command may be one of various calculations related to a kernel program which is executed in the computing node . That is the host thread may determine the computing node and a computing module for example the computing module to execute a command and insert the command in the determined computing node and a command queue for example the command queue corresponding to the determined computing module

The command scheduler schedules the command queues . A scheduling algorithm may be round robin and others according to an application purpose. For example the command scheduler is able to select a command to be executed according to a predetermined schedule algorithm and take out the selected command from the command queues 

The command scheduler generates a request message using the selected command. A request message may be a message in the form of packet which is transmitted via a network and used to request execution of the selected command. For example the command scheduler may generate packet data with an address field and a command description using the computing node which is mapped to a command queue for example the command queue of the selected command and a computing module for example the computing module .

According to an exemplary embodiment of the present invention the command scheduler may store a command corresponding to the transmitted request message in the issue queue and wait for a response from the computing node . If the computing node notifies that execution of the command has been completed the command scheduler may takes out the command stored in the issue queue and transfer the command to the completion queue .

In addition referring to the computing node may include a plurality of computing nodes and a command handler a plurality of ready queues and and a plurality of module threads and

Each of the computing modules and may be a device to calculate and process data including a CPU and a GPU.

In response to receiving the request message the command handler generates a command object and inserts the generated command object in the ready queues and . The ready queues and respectively correspond to the computing nodes and . Hence if a command is determined to be executed in the first computing module according to the request message a command object may be inserted in the ready queue corresponding to the first computing module

The module threads and executes the command using the command object which is inserted in the ready queues and and the computing modules and . For example in the above example the module thread of the first computing module may take out the command object and help the command to be processed in the first computing module based on the command object.

According to an exemplary embodiment of the present invention if a command has been completely executed the module threads and may insert the completed command in the completion queue .

According to another exemplary embodiment of the present invention using a command stored in the completion queue the command handler may generate a completion message to notify that execution of the command has been completed and then transmit the generated completion message to the host node via the network .

Each element illustrated in may be an electric circuit hardware or an application program which is able to be executed in a predetermined processor. In addition the elements are merely examples logically divided according to functions and the functions of the elements may be divided by a different criteria used in . That is two or more functional units may be integrated or one or more functional units may take over a function of another functional unit

The method of is able to be applied to execute an application which is for a parallel computing framework in a cluster system of .

Referring to in the method for executing an application according to an exemplary embodiment of the present invention a host node inserts a command related to a kernel program for a parallel computing framework in a command queue corresponding to a remote computing module which executes the kernel program in .

Next the host node selects a command to be executed by scheduling the command queue and generates a request message to request execution of the selected command in .

In response to receiving the request message the computing node generates a command object and inserts the generated command object in a ready queue corresponding to one or more computing modules in .

In addition the computing node executes the command using the command object inserted in the ready queue and the computing module .

When execution of the command has been completed the computing node generates a completion message to notify execution of the command has been completed in and transmits the generated completion message to the host node via the network in .

In response to receiving the completion message the host node deletes the command stored in the issue queue in . For example the host node is able to transfer the command from the issue queue to a completion queue.

As described in the above exemplary embodiments of the present invention an application of a parallel computing programming model is executed while a host node and a computing node in a cluster system execute are exchanging messages with each other. Due to this feature a user does not need to add a code such as Message Passing Interface MPI to an application on his own so that the number of application bugs may reduce the productivity of a programmer may improve and the portability of a parallel computing framework may be enhanced.

Meanwhile the exemplary embodiments of the present invention may be realized using computer readable codes in a computer readable recording medium. The computer readable recording medium includes all types of recording devices which stores computer system readable data.

Examples of the computer readable recording medium includes a Read Only Memory ROM a Random Access Memory RAM a CD ROM a magnetic tape a floppy disk and an optical data storage device and the computer readable recording medium may be realized in a carrier wave form for example transition via the Internet . In addition the computer readable recording medium is distributed in a computer system connected via a network so that computer readable codes are stored and executed in an distributed manner. In addition functional programs codes and code segments used to embody the present invention may be easily anticipated by programmers in the technical field of the present invention.

A number of examples have been described above. Nevertheless it should be understood that various modifications may be made. For example suitable results may be achieved if the described techniques are performed in a different order and or if components in a described system architecture device or circuit are combined in a different manner and or replaced or supplemented by other components or their equivalents. Accordingly other implementations are within the scope of the following claims.

