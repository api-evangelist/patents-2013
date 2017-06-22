---

title: Distributed system, server computer, distributed management server, and failure prevention method
abstract: A distributed system according to an exemplary embodiment includes first and second servers capable of executing the same application, wherein when a failure occurs in the application in the first server, the first server generates failure information identifying a cause of the failure in the application, and the second server performs failure prevention processing which is determined based on the failure information and intended to prevent a failure in the application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09342426&OS=09342426&RS=09342426
owner: NEC CORPORATION
number: 09342426
owner_city: Tokyo
owner_country: JP
publication_date: 20130924
---
This application is based upon and claims the benefit of priority from Japanese patent application No. 2012 209911 filed on Sep. 24 2012 the disclosure of which is incorporated herein in its entirety by reference.

The present application relates to a distributed system server computer distributed management server and failure prevention method.

A failure often occurs in a business system due to a defect in a business application program implemented on an application server causing the entire business system to fail. Examples of a failure in a business application include the following.

A first example is a deadlock. A deadlock refers to a state in which multiple threads which are executing application logic exert exclusive control acquisition of lock etc. over each other and thus the execution of each thread remains blocked. In this case there occur problems such as one in which a client application serving as the caller of an application such as a browser cannot obtain a response to a request failing to update the screen.

A second example is excessive memory consumption. Excessive memory consumption refers to a state in which the memory area available to an application server is reduced due to one time execution of application logic which handles a great amount of data in query processing related to business for example. In this state a delay may occur in processing of a thread which is executing another application logic which is running on the same process in parallel or an error may occur due to a memory shortage during processing. At worst the process of the application server aborts.

A third example is excessive central processing unit CPU consumption excessively high CPU usage . Excessive CPU consumption refers to a state in which the CPU is being used more than necessary due to occurrence of an infinite loop or redundant application logic. In this case there arises for example a problem that the caller of the application cannot obtain a response to a request failing to update the screen. There also arises a problem that a delay occurs in processing of a thread which is executing another application logic which is running on the same process in parallel.

When such an event occurs it usually can be eliminated by restarting the failed application server. In any case however a fundamental solution requires modification of the application program in question. For this reason the system operator may have to take temporary measures such as periodical restart of the application server or tuning of the parameters with respect to the application server so as to prevent recurrence of a failure as described above until the application is modified.

Japanese Unexamined Patent Application Publication No. 2010 9127 discloses as a technology for handling a failure a management apparatus that identifies a component acting as the cause of a failure. Specifically when an abnormality occurs in a system in which a computer including an application server and a computer including a management system are connected together via a network the management apparatus can determine in which of the application server and the management system the failure has occurred.

Japanese Unexamined Patent Application Publication No. 2006 338069 discloses a component software operation infrastructure that prevents an error from occurring in response to a sign or occurrence of a failure as well as prevents a reduction in performance. Specifically during execution of component software including multiple components software components the component software operation infrastructure replaces a component with another.

Japanese Unexamined Patent Application Publication No. 2005 209029 discloses an application management system including multiple application server computers and a management server computer. Each application server computer refers to an application operation definition storage file stored in the management server computer to control and manage the execution of an application whose execution has been requested. When a failure occurs in an application being executed by an application server computer the application server computer notifies the other application server computers or external computers of that fact.

Currently systematization using cloud computing technology is becoming widespread. Such systematization refers to constructing a system using a great number of application servers distributed on many networks. In such an environment the load is distributed. Accordingly an abnormality occurring in a single server due for example to occurrence of a failure is less likely to cause the entire system to fail.

However if the failure is caused by a problem associated with the application program itself all the application servers have a potential risk of experiencing the same failure in future. For this reason the system operator must inevitably take a temporary measure as described above unless he or she takes a measure such as downgrading of the failed application to a previous version. Further as the number of servers increases such a failure is more likely to occur in the system. This results in an increase in the operating cost for taking temporary measures.

Any of Japanese Unexamined Patent Application Publication Nos. 2010 9127 and 2006 338069 does not consider a situation in which multiple servers such as application servers are disposed as in cloud computing.

For an application management system according to Japanese Unexamined Patent Application Publication No. 2005 209029 when an abnormality occurs in an application which is being executed by an application server computer it cannot prevent a similar abnormality from occurring in another application server computer.

An example of the object of the present invention is to provide a distributed system server computer distributed management server and failure prevention method that prevent a failure in a server without imposing a load on the system operator.

In a first exemplary aspect of the invention a distributed system includes first and second servers capable of executing the same application wherein

when a failure occurs in the application in the first server the first server generates failure information identifying a cause of the failure in the application and

the second server performs failure prevention processing which is determined based on the failure information and intended to prevent a failure in the application.

In a second exemplary aspect a server computer disposed in a distributed system and connected to another server computer capable of executing the same application wherein

when a failure occurs in the application the server computer generates failure information identifying a cause of the failure in the application and

when the other server generates failure information identifying a cause of a failure in the application the server computer performs failure prevention processing which is determined based on the failure information and intended to prevent a failure in the application.

In a third exemplary aspect a distributed management server disposed in a distributed system including first and second servers capable of executing the same application wherein

when the distributed management server receives from the first server failure information identifying a cause of a failure in the application in the first server the distributed management server transmits to the second server the failure information serving as information that the second server uses to perform failure prevention processing for preventing a failure in the application.

In a fourth exemplary aspect in a distributed system including first and second servers capable of executing the same application a failure prevention method for preventing a failure in the application includes 

when a failure occurs in the application in the first server generating by the first server failure information identifying a cause of the failure in the application and

performing by the second server failure prevention processing which is determined based on the failure information and intended to prevent a failure in the application.

In light of the foregoing it is possible to provide a distributed system server computer distributed management server and failure prevention method that prevent a failure in a server without imposing a load on the system operator.

Now a first embodiment of the present invention will be described with reference to the drawings. is a block diagram showing an example configuration of a distributed system according to the first embodiment.

The distributed system includes a server computer first server and a server computer second server both capable of executing the same application. The distributed system is for example a distributed system using cloud computing. The number of server computers included in the distributed system is not limited to two and may be three or more. The server computers and are storing the same applications applications and in such a manner that the applications and are executable.

When a failure occurs in the application being executed by the server computer the server computer generates failure information identifying the cause of the failure in the application . As used herein the failure information refers to for example a component which has caused the failure to the application or an interface associated with the component. Specifically the failure information may be data of the interface or the component name of the interface or the component or the like.

The server computer performs failure prevention processing which is determined based on the failure information generated by the server computer and intended to prevent a failure in the application .

For example assume that a failure occurs in the server computer due to a request from a client thereof and then the server computer generates failure information related to the failure. In this case the server computer monitors a request from a client thereof on the basis of the failure information that is performs failure prevention processing. As an example of monitoring the server computer determines whether the same function as the function of the application requested by the request from the client which has caused the failure to the server computer is being requested by a client of the server computer . If the same function is being requested by a client of the server computer the server computer prevents the same failure as that in the server computer for example by stopping performing that function.

By performing processing as described above the distributed system can prevent a failure in a server without the system operator having to perform some processing without imposing a load on the system operator .

The server computer described above may further perform processing performed by the server computer . Specifically when a failure occurs in the application the server computer generates failure information identifying the cause of the failure in the application . When the server computer generates failure information identifying the cause of a failure in the application the server computer performs failure prevention processing which is determined on the basis of that failure information and intended to prevent a failure in the application . Similarly the server computer may perform processing performed by the server computer . That is each server computer can generate when a failure occurs therein failure information which is necessary for another server computer to perform failure prevention processing as well as can perform when another server computer generates failure information failure prevention processing on the basis of that failure information. By including such server computers in the distributed system it is possible to prevent failures in the distributed system more efficiently.

The distributed system may include a distributed management server that manages the distributed system in addition to the server computers and . is a block diagram showing an example configuration of the distributed system as described above. In the distributed system the distributed management server is connected to the server computers and . The server computers and are similar to those described with reference to .

The distributed management server receives from the server computer failure information identifying the cause of a failure in the application installed in the server computer . The distributed management server transmits to the server computer the failure information serving as information which the server computer uses to perform failure prevention processing for preventing a failure in the application . By performing the above processing the distributed management server can prevent a failure in the server computer .

Details of the failure prevention processing performed by the server computer may be determined by any of the server computer and the distributed management server on the basis of the failure information.

Now a second embodiment of the present invention will be described with reference to the drawings. is a block diagram showing an example configuration of a distributed management system according to the second embodiment.

The distributed management system includes application servers A B and C a distributed management server and client applications A B and C. Hereafter the application servers A B and C will be collectively referred to as the application server the client applications A B and C collectively as the client application .

The application server functions as a business application execution infrastructure in the distributed management system . The application server includes for example software executed by a server computer including resources such as a CPU and memory and hardware of the server computer used in the processing of the software. The application server includes a request receiving unit a request analysis unit an operational request receiving unit a failure information receiving unit a failure information storage unit a storage device a failure event issuing unit and an application execution control unit . The application servers A B and C are distributed on a network of the distributed management system and each have the same configuration. The application servers A B and C are executed by different computers.

The request receiving unit receives a request which a system user transmits using the client application .

The request analysis unit analyzes detailed information of the request received by the request receiving unit .

The operational request receiving unit receives a request for operation management made to the application server by the distributed management server .

The failure information receiving unit receives from the distributed management server information about a failure that has occurred in another application server.

The failure information storage unit stores in an internal memory thereof the failure information received by the failure information receiving unit . The storage device is a storage device which stores failure information data in a non transitory manner and the failure information storage unit stores the failure information in the storage device as necessary.

The failure event issuing unit transmits information about a failure that has occurred in an application installed in the application server to other application servers which are connected to the application server via the distributed management server .

The application execution control unit controls the execution of applications installed in the application server . The application execution control unit includes an execution management unit a failure monitoring unit a failure identifying unit a failure analysis unit a potential failure storage unit a failure information search unit and components application components A B and C. Hereafter components A B and C will be collectively referred to as the component .

The execution management unit manages the execution state of the component that operates in the application execution control unit . Specifically the execution management unit manages information indicating that an application is being called or information about a request being executed currently and about a thread which is executing the request.

The failure monitoring unit monitors a failure in applications installed in the application server . For example the failure monitoring unit acquires a list of information about threads of a process thread dump or various types of resource information such as memory usage and CPU usage.

The failure identifying unit identifies details of a failure detected by the failure monitoring unit . Specifically the failure identifying unit extracts the identifier of a component component name and the name of an interface of the component from the various types of resource information acquired by the failure monitoring unit .

The failure analysis unit analyses an occurring failure in detail or performs computation related to the prediction of a failure on the basis of the information extracted by the failure identifying unit through the identification.

The potential failure storage unit stores information about a failure predicted by the failure analysis unit . This information is updated by the failure analysis unit .

The failure information search unit searches the failure information storage unit for failure information with respect to the application.

The component forms an application which is actually installed in the application server an application stored in a manner to be executable by the computer of the application server . The component has business logic implemented thereon. The component runs on the application execution control unit . The application servers A to C have the same applications installed thereon and therefore include the same components A to C. Note that the components A to C do not need to form the same application.

The distributed management server is a dedicated server that centrally manages application servers distributed on the network configuration of the distributed management system . The system administrator can manage the distributed management system by using the distributed management server . The distributed management server includes an application storage unit an application information management unit a failure event receiving unit an operational action issuing unit and a failure information issuing unit .

The application storage unit is storing the same applications as the applications installed in the application server .

The application information management unit manages detailed information version information etc. about the applications installed in the application server .

The failure event receiving unit receives an event issued by the failure event issuing unit of each application server and including failure information. The failure event receiving unit includes an event analysis unit . The event analysis unit analyzes on the basis of the received event details of a failure that has occurred in the application server .

The operational action issuing unit transmits any operational action request to the application servers under the management thereof.

The failure information issuing unit transmits failure information extracted by the failure identifying unit of a particular application server to the application servers under the management thereof.

The client application is an application for client that a system user client uses to call business logic of the applications installed in the application servers.

The elements of the application server and distributed management server shown in as function blocks that perform various types of processing can be formed by a CPU a memory and other circuits in terms of hardware these elements are achieved by a program loaded into the memory in terms of software for example. Accordingly it will be appreciated by those skilled in the art that these function blocks can be achieved using hardware alone software alone or combinations thereof in various forms but are not limited to one of these.

Hereafter an example operation of the distributed management system according to the second embodiment will be described in detail with reference to the drawings.

The application server receives a request from the client application such as a Web browser via the request receiving unit .

The request analysis unit analyzes the request received by the request receiving unit to extract information about the component to be called by the request and about an interface method of the component. The request analysis unit transmits the extraction result serving as a parameter to the application execution control unit .

The application execution control unit stores in the execution management unit information indicating that the application is being called and then executes business logic using the interface of the component requested.

When the execution of the business logic is complete the application execution control unit deletes the information stored in the execution management unit . This series of processing is performed by a thread of a process that runs the application server on a request basis.

Further the distributed management server properly manages basic information host name or the like about the distributed application servers or information about the configuration of the applications installed in the application servers application name version name or the like . The application servers are previously distributed on the basis of operational work of the system operator. Furthermore the distributed management server can instruct all the application servers under the management thereof to perform installation or update of an application a change in the setting of the application server or the like.

The following items with respect to failure detection are set in the application server according to the second embodiment.

A recovery action taken on the application server when a deadlock is detected while the application is called is specified in this item. In the second embodiment options of the recovery action at least include restart of the application server and downgrading of the application to a previous version. 

A memory usage for determining that the memory of the application server is being consumed excessively is set in this item. When the actual memory usage of the application server becomes greater than or equal to the value set in this item the application server determines that the memory is being consumed excessively.

The entry frequency of component name and interface name for determining the cause when the memory is being consumed excessively failure frequency is specified in this item. When a component name and interface name are entered at a frequency greater than or equal to the specified frequency the application server determines the entered component name and interface name as the cause of the excessive memory consumption.

This item includes options of a recovery action taken on the application server when detecting excessive memory consumption. The recovery action options at least include forced execution of garbage collection GC and downgrading of the application of a previous version. 

A CPU usage for determining that the CPU of the application server is being consumed excessively is set in this item. When the actual CPU usage of the application server becomes greater than or equal to the set value the application server determines that the CPU is being consumed excessively.

The entry frequency of application component name and interface name for determining the cause when detecting that the CPU is being consumed excessively is specified in this item. When an application component name and interface name are entered at a frequency greater than or equal to the specified frequency the application server determines the application component name and interface name are the cause of the excessive CPU consumption.

A recovery action taken on the application server when detecting excessive CPU consumption is selected in this item. The recovery action options at least include change of processing priority and downgrading of the application to a previous version. 

The above items are previously set to appropriate values criteria either by the system operator or according to the specification of the application server . The application server detects a failure in an application using the following method. For example the application server itself periodically monitors the consumption state of the resources or the occurrence state of a failure using an application programming interface API provided by the operating system OS or the execution environment of the program. Alternatively in an execution environment in which occurrence of a failure is issued as an internal event the application execution control unit of the application server detects a failure by receiving such an event.

When a failure is detected in the application server using a method as shown above the failure monitoring unit of the application server acquires a list of information about the threads of the process or information about resources such as memory usage or CPU usage failure information step S .

Using the failure identifying unit the application execution control unit identifies the type of the occurring failure the cause of the failure from various types of resource information acquired by the failure monitoring unit step S .

The application execution control unit determines whether the type the failure identified by the failure identifying unit is a deadlock or whether the number of requests being processed is 1 step S . The application execution control unit refers to information about a request s currently being executed which is stored in the execution management unit to determine whether the number of requests being processed is 1.

When the type of the failure identified by the failure identifying unit is deadlock or when the number of requests being processed is 1 Yes in step S the application execution control unit extracts the identifier of the component in question component name whose business logic has been called and the name of an interface thereof from information about the stack of the thread. Based on the information extracted the application execution control unit issues a failure event including the following information to the distributed management server via the failure event issuing unit step S .

The related component name and related interface name represent a component and an interface thereof which are believed to cause a failure in relation to the component in question whose business logic has been called and the interface thereof. When the number of requests being processed is 1 only the component in question whose business logic has been called and the interface thereof are described as the component name and the interface name and nothing is described as the related component name or related interface name.

When the failure type identified by the failure identifying unit is not deadlock and when the number of requests being processed is more than one No in step S the failure identifying unit sequentially analyzes the acquired thread stack information. In the analysis the failure identifying unit extracts the identifier of the component the name of the failed component and the name of the interface thereof from the thread stack information step S . The failure analysis unit analyzes the failure on the basis of the information extracted by the failure identifying unit through the above identification step S . The information extraction by the failure identifying unit step S and the failure analysis by the failure analysis unit step S are performed by generating a loop corresponding to the number of requests being processed.

Referring to the failure analysis performed by the failure analysis unit step S will be described in detail. In the analysis of a failure the failure analysis unit checks whether data composed of a pair of the component name and interface name extracted by the failure identifying unit has been entered exists as potential data in the potential failure storage unit step S .

If such data has been entered as potential data in the potential failure storage unit Yes in step S the failure analysis unit acquires the data from the potential failure storage unit step S .

If such data has not been entered as potential data in the potential failure storage unit No in step S the failure analysis unit generates an entry potential data as a new cause of the failure by using the identifier of a component and an interface name as keys step S . At this time the failure analysis unit stores in the entry a parameter such as the threshold or recovery action specified in the items for failure detection in accordance with the failure type detected.

In any of steps S and S the failure analysis unit increments by 1 the failure frequency of the component name and interface name extracted by the failure identifying unit step S . Note that the processing of step S may be performed concurrently with step S or step S or prior thereto.

As described above a threshold in refers to a criterion for determining that a failure corresponding to that threshold is occurring. For example if the type of a failure in the application is excessive memory consumption CPU load or the like the failure analysis unit has difficulty in determining which of multiple application threads which are running in parallel is a direct cause. In this case a statistical value and criterion need to be used to determine the source location of the failure. The threshold is used as information for determining the source location.

The failure analysis unit refers to the data stored in the potential failure storage unit to make a comparison among the failure frequencies and corresponding thresholds of the component names and interface names. The failure analysis unit then determines whether there is a failure frequency which is greater than or equal to the threshold step S .

If the frequency serving as a criterion for determining that a failure has occurred reaches or exceeds the threshold Yes in step S the failure analysis unit determines identifies a call of the interface of the corresponding component as the cause of the failure. Using this information the failure analysis unit starts processing for issuing a failure event to the distributed management server . Details of the event are as described above. The component name and interface name included in the failure event to be issued are the names of the component first component and interface first interface determined as the cause of the failure by the failure analysis unit .

At this time in addition to the entry determined as the cause of the failure which has reached or exceeded the threshold the failure analysis unit extracts a component second component and interface second interface related to an entry which has not reached the threshold at that time but has the highest frequency an entry having the second highest failure frequency step S . The thread processing of this potential failure is to be controlled.

The reason for extracting the entry having the highest frequency as a potential failure in addition to the entry determined as the cause of the failure is to obtain the relationship among the components of the application that may cause a failure. In the case of excessive CPU consumption the cause thereof may be not a call of an interface of a particular component but an overlap between calls of interfaces of multiple components. Even in the case of logic which requires execution of complicated processing when called and significantly consumes the CPU excessive CPU consumption does not occur if an interface whose load falls within when the interface is called alone the allowable range in which the business system runs normally though may increase temporarily is called alone. However when calls of multiple such interfaces overlap each other excessive CPU consumption would occur.

Note that even when calls of multiple interfaces overlap each other whether a failure occurs depends on the configuration of the application the machine specification of the application server or the like. For this reason by obtaining a relationship as described above when the business system is running it is possible to detect a potential failure more accurately and prevent a failure from occurring. This applies not only to excessive CPU consumption but also excessive memory consumption.

There may be multiple components each having a failure frequency reaching or exceeding the threshold. If an interface of a component has already reached or exceeded the threshold when the failure analysis unit determines that the failure frequency of an another component has reached or exceeded the threshold as described above the failure analysis unit also may extract the other component second component and an interface thereof second interface as a potential failure in step S. As seen above the number of potential failures extracted by the failure analysis unit is not limited to one and may be two or more.

Further when the failure frequency with respect to excessive CPU consumption of a particular component and an interface thereof reaches or exceeds the threshold the failure frequency with respect to excessive memory consumption of another component and an interface thereof may reach or exceed the threshold. In such a case the other component second component and the interface thereof second interface in which excessive memory consumption has occurred are extracted as a potential failure in step S. In contrast when the failure frequency with respect to excessive memory consumption of a component and an interface thereof reaches or exceeds the threshold the failure frequency with respect to excessive CPU consumption of another component and an interface thereof may reach or exceed the threshold. In this case also the other component second component and the interface thereof second interface in which excessive CPU consumption has occurred are extracted as a potential failure in step S.

Note that the component second component extracted as a potential failure in step S may be different from or the same as the component first component determined as the cause of the failure by the failure analysis unit . Note that the interface first interface determined as the cause of the failure by the failure analysis unit differs from the interface second interface extracted as a potential failure thereby.

The failure information event issuing unit includes in a failure event the potential failure extracted in step S as information about the related component name and related interface name related information and then issues the failure event step S . After the failure event is issued the failure analysis unit deletes the data about the entry potential data from the potential failure storage unit step S .

If the frequency of an entry falls below the threshold No in step S the failure analysis unit determines that the data is not adequate to determine that the entry is the cause of the failure and avoids starting processing for issuing a failure event. The failure analysis unit updates the entry data potential data in the potential failure storage unit step S . The updated information is stored in the storage device via the failure information storage unit .

Due to the above processing the entry information accumulated in the potential failure storage unit is continuously held by each application server until the component in question is updated or deleted. Accordingly when the application server is started the data about the potential failures stored in the storage device in a non transitory manner is read and again stored in the potential failure storage unit .

First the distributed management server receives a failure event from the application server via the failure event receiving unit and then analyzes it using the event analysis unit step S . The event analysis unit determines whether a recovery action to be taken on the failure is included defined in the failure event received step S .

If a recovery action to be taken on the failure is included in the failure event Yes in step S the operational action issuing unit issues a recovery action request to the failed application server A on the basis of details of the recovery action included in the failure event. In accordance with the recovery action request issued the application server A takes the recovery action recovery processing step S . Thus the application server A can recover from the failure.

The distributed management server determines whether the recovery action to be taken on the failure is downgrading of the application to a previous version step S .

If the recovery action is downgrading of the application to a previous version Yes in step S the distributed management server updates information about the version of the installed applications stored in the application information management unit step S . Thus the distributed management server matches the information about the version of the applications therein with the information about the version of the applications in the application server .

If the recovery action is not downgrading No in step S the distributed management server transmits new failure information based on the component identifier and interface name of the application extracted by the event analysis unit to all the application servers under the management thereof via the failure information issuing unit step S . The Information transmitted by the distributed management server is as follows.

Note that the failure information issuance processing step S is performed by generating a loop corresponding to the number of the application servers to be managed.

The failure information receiving unit of each application server receives the failure information issued by the failure information issuing unit . The application server stores the failure information received in the failure information storage unit and then in the storage device . The application server also immediately starts monitoring requests transmitted from system users.

Note that the processing of step S may be performed concurrently with or after step S. Further the processing of step S may be performed concurrently with or after step S or concurrently with or after step S.

After starting monitoring the application execution control unit of the application server receives a request with respect to a request request to request from a system user via the request receiving unit step S .

Using the failure information search unit the application execution control unit determines whether failure information about an interface of a component requested by the system user is stored in the failure information storage unit in the form of a component name and interface name step S .

If the failure information is stored Yes in step S the application execution control unit refers to information about an interface of an application related to the interface of the component requested in the failure information step S . The application execution control unit then determines whether the failure information includes information about an interface of a related application step S . As used herein the related application refers to an application including the related component included in the failure information.

If the failure information includes information about the interface of the related application that is information about the related interface in the failure information Yes in step S the application execution control unit determines whether a request corresponding to this interface information related request is being executed by a thread other than the thread which is processing the request to request step S . The application execution control unit makes this determination on the basis of information held by the execution management unit .

If the application execution control unit can confirm that the related request is being executed by another thread Yes in step S it puts execution of a subsequent request request to request on hold until the execution by the other thread is complete step S . After predetermined time elapses the application execution control unit again determines whether the related request is being executed by another thread step S .

If the related request is not being executed by another thread No in step S the application execution control unit causes a thread to process a subsequent request step S . That is the application execution control unit executes the request. If the application execution control unit puts execution of a subsequent request on hold in previous step S it causes a thread to resume processing the request put on hold.

If the failure information does not include information about the interface of the related component in step S No in step S the application execution control unit performs the following processing. The application execution control unit determines whether the request to the interface of the failed component same request is being executed by a thread other than the thread which is processing the request to request on the basis of information held by the execution management unit step S .

If the same request is being executed by another thread Yes in step S the application execution control unit puts execution of a subsequent request on hold until the execution of the other thread is complete step S . After predetermined time elapses the application execution control unit again determines whether the same request is being executed by another thread step S .

If the same request is not being executed by another thread No in step S the application execution control unit causes a thread to process the same request step S . That is the application execution control unit executes the request. If the application execution control unit puts execution of a subsequent request on hold in step S it causes a thread to resume processing the request put on hold.

Note that in the on hold processing in steps S and S the application execution control unit may determine after predetermined time elapses that the processing has timed out and return an appropriate error to the caller ending the processing of . The application execution control unit performs this processing for example on the basis of a parameter specified by the system operator or application server .

If the failure occurring in the application server A is a deadlock the application server B does not need to perform the processing of any of steps S and S. A deadlock failure occurs when an interface of a component related to a request and an interface of another component exert exclusive control over each other simultaneously. Accordingly if the interface of the component related to the request has already been executed a deadlock failure is believed not to occur.

Note that if the related request is not being executed by another thread No in step S the application execution control unit may perform the processing of step S. Bifurcation based on the determination in step S is as described above.

The above monitoring is continuously performed by each application server until the application in question is updated. Accordingly if the application server is restarted before such update is made the failure information on the memory of the failure information storage unit would be lost. For this reason when the application server is started the failure information stored in a non transitory manner is read from the storage device . The failure information read is again stored in the failure information storage unit by the application execution control unit .

Imagine a case in which when a business system is running in a particular application server A a deadlock occurs between threads which are processing multiple requests in parallel due to a defect in an application. The components of the application that has caused the deadlock in the application server are represented by A and B and call interfaces thereof by Am and Bm. Restart of the application server is predefined as a recovery action taken when a deadlock occurs.

When the deadlock occurs in the application server A the failure monitoring unit in the application server A acquires stack information with respect to the threads processing the requests which have caused the deadlock information including the flow of the call of the threads . Based on the information acquired the application server issues a failure event to the distributed management server . This failure event includes information including the component name A and interface name Am of the application identified as the source of the deadlock the cause of the failure by the failure identifying unit a related component name B and related interface name Bm corresponding to the component name A and interface name Am and the failure type deadlock and information including the component name B and interface name Bm of the application identified as the source of the deadlock the related component name A and related interface name Am corresponding to the component name B and interface name Bm and the failure type deadlock. A recovery action identified here is restart of the server. 

The distributed management server receives the failure event and extracts through analysis by the event analysis unit failure information indicating that the deadlock has occurred between the interfaces Am and Bm of the components A and B and in which restart of the server is predefined as a recovery action. The distributed management server restarts the failed application server A and then transmits the failure information to all the application servers under the management thereof. This failure information includes the component names the components A and B and the interface names the interfaces Am and Bm.

An application server B receives the failure information and stores it in the failure information storage unit thereof as well as immediately starts monitoring requests. The application server B then processes a request which is outputted from the client application and is intended to call the interface Am of the component A of the application using the request receiving unit .

The request receiving unit transfers the request to the application execution control unit . At this time the failure information search unit of the application execution control unit confirms that the interface information Am of the component A is present in the failure information storage unit . After the confirmation the application execution control unit inquires of the execution management unit as to whether a call of the related interface Bm of the related component B is already managed as being executed by another thread.

If a call of the interface Bm is being executed by another thread the application execution control unit puts processing for calling the interface Am of the component A on hold until the processing by the other thread is complete. After the call of the interface Bm of the component B is complete the application execution control unit releases the call of the interface Am of the component A put on hold to resume the processing.

When the processing thread of the request to the interface Am of the component A is executed a request is made to the interface Cm of a component C. On the other hand when the processing thread of the request to the interface Bm of the component B is executed a request is made to the interface Cm of the component C. At this time both interfaces methods may exert exclusive control. Depending on the timing at which the processing is executed a deadlock may occur between the interfaces Cm and Cm.

In the above processing the execution of the request to the interface Am of component A is put on hold until the request to the interface Bm of the component B is complete. This prevents both interfaces from exerting exclusive control allowing the interface Cm to be executed after the interface Cm is executed. In other words the interfaces Cm and Cm are executed at different timings. As a result a deadlock can be avoided.

Not only the application server B but also the application server C receives the failure information and performs similar processing.

While the case in which a deadlock occurs between the interfaces of the different components A and B has been described above a deadlock may occur between different interfaces of the same component. For example there can be a case in which when a processing thread of a request to an interface Am of the component A is executed a request is made to the interface Cm of the common component C when a processing thread of a request to an interface Am of the component A is executed a request is made to the interface Cm of the common component C. At this time both interfaces Am and Am exert exclusive control. Depending on the timing of the processing the processing may proceed in such a manner that exclusive control is exerted in an overlapping manner simultaneously causing a deadlock according to a principle similar to that in . As seen above while the threads are processing the different interfaces Am and Am of the same component A different exclusive control may be exerted over the common component C.

When the deadlock occurs in the application server A the application server issues a failure event to the distributed management server on the basis of the information acquired by the failure monitoring unit . This failure event includes information including the component name A and the interface name Am of the application identified as the source of the deadlock the cause of the failure by the failure identifying unit a related component name A and the related interface name Am corresponding to the component name A and the interface name Am and the failure type deadlock and information including the component name A and the interface name Am of the application identified as the source of the deadlock the related component name A and related interface name Am corresponding to the component name A and interface name Am and the failure type deadlock. 

In accordance with the failure event issued the distributed management server transmits failure information to the application server B. The application server B performs request processing control for preventing a deadlock failure similar to that described with reference to . For example when a request for calling the interface Am is made by the client application and when a call of the interface Am is already being executed by another thread the application execution control unit puts processing for calling the interface Am on hold until the processing by the other thread is complete. After the processing of calling the interface Am is complete the application execution control unit releases the call of the interface Am put on hold to resume the processing.

Hereafter using another specific example the processing of will be further described. Image a case in which during operation of the system the memory is being consumed excessively due to a defect in the application in the particular application server A. In the description below in the application server a component of an application which is consuming the memory excessively is represented by A an interface thereof by Am the other components by B to E and interfaces thereof by Bm to Em. Assume that in the data stored in the failure information storage unit the frequency threshold for determining the component as the cause of a failure is 3 and the set recovery action is forced GC. 

When the memory is consumed excessively in the application server A at time t the failure monitoring unit acquires stack information with respect to a thread which is processing a request. Using the failure identifying unit the application execution control unit identifies a component name and interface name of the failed application from the information acquired. Assume that the following information is acquired.

 Component Name Interface Name A Am C Cm E Em hereafter components and interfaces corresponding thereto will be represented similarly. 

At this time the failure analysis unit newly stores the entry information in the failure information storage unit . The frequency of each entry is regarded as 1.

Subsequently the memory is again excessively consumed in the application server A at time t. Assume that the failure identifying unit acquires the following information.

At this time the failure analysis unit performs processing similar to that described above and adds the entries to the data stored in the failure information storage unit to update the data.

Subsequently the memory is again excessively consumed in the application server A at time t. Assume that the failure identifying unit acquires the following information.

At this time the failure analysis unit performs processing similar to that described above and adds the entries to the data stored in the failure information storage unit to update the data.

At this time the failure frequency of A Am reaches 3 that is the threshold. For this reason the failure analysis unit determines that A Am is the cause of the failure associated with excessive memory consumption. The failure analysis unit regards C Cm and E Em having the highest frequency next to A Am as related components and related interfaces related information with respect to A Am acting as the cause of the failure. The failure event issuing unit issues to the distributed management server a failure event indicating the component name and interface name acting as the cause of the failure A Am and the related component names and related interface names C Cm and E Em .

The subsequent processing that is execution of a recovery action and issuance of failure information to the application server by the distributed management server and processing and request processing thread execution control that each application server performs after receiving the failure information are as described above.

If the interface Am of the component A is an interface that consumes the memory excessively calls of the interface Am by multiple requests would cause a memory shortage.

For this reason the application server B puts execution of the request later made to the interface Am of the component A on hold until the preceding request earlier made to the interface Am of the component A is complete. This prevents calls based on multiple requests from being made in the application server B allowing avoidance of a memory shortage. In other words the application server B performs control so that the interface Am of the component A is not simultaneously executed by multiple threads.

Note that failure information may indicate that the interface Cm of the component C is a potential failure having the second highest frequency next to the interface Am of the component A and in the application server B the interface Cm is being executed by a thread other than the thread which is executing the interface Am. In this case the application server B puts execution of the interface Am of the component A on hold until the execution of the interface Cm is complete. In addition the application server B may put execution of the interface Cm of the component C on hold until the execution of the interface Am is complete. Since the application server B performs control in this way it is possible to prevent calls of interfaces of multiple components and causing a failure. Even when an interface of a component which has already reached or exceeded the threshold is recorded as a potential failure or even when an interface of a component whose failure frequency with respect to CPU excessive consumption has reached or exceeded the threshold is recorded as a potential failure the application server B can perform similar control.

Note that the different interface Am of the same component A may be described as a potential failure having the highest frequency next to the interface Am of the component A. In this case if the interface Am is being executed by a thread other than the thread which is executing the interface Am the application server B puts execution of the interface Am on hold until execution of the interface Am is complete.

Hereafter using yet another specific example the processing of will be further described. Image a case in which during operation of the system the CPU is consumed excessively due to a defect in an application in the particular application server A. In the description below in the application server a component of an application which consumes the CPU excessively is represented by A an interface thereof by Am the other components by B to E and interfaces thereof as Bm to Em. Assume that in the data stored in the failure information storage unit the frequency threshold for determining that the component is the cause of the failure is to 3 and the set recovery action is forced GC. 

When the CPU is consumed excessively in the application server A at time t the failure monitoring unit acquires stack information with respect to a thread which is executing a request. From the information obtained the application execution control unit identifies the component name and the interface name of the failed application by using the failure identifying unit . Assume that the following information is acquired.

 Component Name Interface Name A Am C Cm E Em Hereafter Components and Interfaces Corresponding Thereto Will be Represented Similarly. 

At this time the failure analysis unit stores each entry information in the failure information storage unit . The frequency of each entry is regarded as 1.

Subsequently the CPU is again excessively consumed in the application server A at time t. Assume that the failure identifying unit acquires the following information.

At this time the failure analysis unit performs processing similar to that described above and then adds the entries to the data stored in the failure information storage unit to update the data.

Subsequently the CPU is again excessively consumed in the application server A at time t. Assume that the failure identifying unit acquires the following information.

At this time the failure analysis unit performs processing similar to that described above and adds the entries to the data stored in the failure information storage unit to update the data.

The failure frequency of A Am has reached 3 that is the threshold. For this reason the failure analysis unit determines that A Am is the cause of the failure associated with the excessive CPU consumption. The failure analysis unit also regards C Cm and E Em having the second highest frequency as related components and related interfaces with respect to A Am acting as the cause of the failure. The failure event issuing unit issues to the distributed management server a failure event indicating the component name and interface name acting as the cause of the failure A Am and the request component names and related interface names C Cm and E Em .

The subsequent processing that is execution of a recovery action and issuance of failure information to the application server by the distributed management server and processing and request processing thread execution control that each application server performs after receiving the failure information are as described above.

If the interface Am of the component A is an interface that consumes the CPU excessively calls of the interface Am based on the multiple requests would cause a delay in the processing of another request or the like.

The application server B puts execution of the request made later to the interface Am of the component A on hold until the request made earlier to the interface Am of the component A is complete. This prevents calls based on multiple requests from being made in the application server B allowing avoidance of a delay in the processing of another request or the like. In other words the application server B performs control so that the interface Am of the component A is not simultaneously executed by multiple threads.

Note that failure information may indicate that the interface Cm of the component C is a potential failure having the second highest frequency next to the interface Am of the component A and in the application server B the interface Cm is being executed by a thread other than the thread which is executing the interface Am. In this case the application server B puts execution of the interface Am of the component A on hold until the execution of the interface Cm is complete. Since the application server B performs control in this way it is possible to prevent calls of interfaces of multiple components and causing a failure. Even when an interface of a component which has already reached or exceeded the threshold is recorded as a potential failure or even when an interface of a component whose failure frequency with respect to excessive memory consumption has reached or exceeded the threshold is recorded as a potential failure the application server B can perform similar control.

Note that the different interface Am of the same component A may be described as a potential failure having the highest frequency next to the interface Am of the component A. In this case if the interface Am is being executed by a thread other than the thread which is executing the interface Am the application server B puts execution of the interface Am on hold until the execution of the interface Am is complete. In addition the application server B may put execution of the interface Am of the component A on hold until the execution of the interface Am is complete.

The processing in the distributed management system according to the second embodiment described above is summarized. The application server in which a failure has occurred analyzes information about resources such as the memory threads or CPU and identifies or predicts the cause of the application failure on a component or interface basis. Thus in coping with the application failure which may affect the entire system the system operator does not need to identify the cause of the failure or make a statistical prediction allowing the load on the system operator to be reduced.

The failed application server then transmits the analysis result to the other application servers having the same configuration so as to share the failure information with the other application servers. The other application servers receive the failure information transmitted by the failed application server and accumulate the failure information so as to prevent a failure similar to the failure which has occurred in the failed application server. In accordance with the failure information accumulated the application server monitors requests to the application as well as controls the order or timing of execution of the requests.

Effects of the distributed management system according to the second embodiment are as follows. First the system including distributed multiple application servers can prevent a failure which is caused by a defect in an application and which may affect the entire system. The reason is that since failure information about the defect in the application is transmitted to the other application servers an application server which has received the failure information transmitted can control execution of the application so that the same failure does not occur in the application server.

An application failure such as a deadlock or memory failure often occurs based on a particular processing pattern. For this reason if an application server analyzes the pattern and previously controls a call of the application so that the processing pattern does not occur it is possible to stably run the entire distributed management system. In other words the application server can perform monitoring and procedure specialized in the location of a failure similar to the failure which has occurred in another application server and which may occur in the future. In performing the monitoring and procedure the application server controls the order or timing of execution of requests to the application.

A second effect is that the load on the system operator can be reduced. The reason is that the distributed management system can automatically take a e.g. temporary countermeasure against the failure without involving an operation by the system operator.

Typically a fundamental solution to a failure which is caused by a defect in an application requires modification of the application program. That is a failure can recur until components running on all application servers are updated. Modification of the application program testing of the modified program and an update of components on the application server require a certain period of time.

For this reason when a similar failure occurs in a situation in which the system must continue running unavoidably before the components are updated some temporary measure must be taken including restart of the application server by the system operator. In this case as the number of application servers increases a failure is more likely to occur in the application. Accordingly the system operator is more likely to have to bear an excessive workload.

However the distributed management system according to the second embodiment instead of the system operator controls the execution of the application so that the application server itself prevents recurrence of a failure. As a result the system operator does not need to take such a measure whatever the number of application servers may be.

System models using cloud computing technology have been increasingly constructed in recent years. Most of such systems include a great number of server machines which are distributed on many networks. Application servers serving as server machines often have the same configuration. Since most of such systems have a load distribution configuration an abnormality in a single server which is caused by a failure or the like is less likely to affect the entire system that is less likely to cause the entire system to fail .

However if the business application itself which is running on each application server contains a defect a failure caused by this error in a single application server may result in successive occurrence of similar failures in other application servers in the near future. As a result this failure may reduce the performance of the entire system or affect the non working time thereof. Further the failure may result in a quality problem with respect to the service level agreement SLA of the system or the like. In this case the system operator must unavoidably take a temporary measure unless there is taken a measure such as downgrading of the failed application to a previous version. Further as the number of servers increases such a failure is more likely to occur resulting in an increase in the operating cost for taking temporary measures.

As described above however a defect in the application often occurs based on a particular processing pattern. For this reason if the application server analyzes this pattern and previously controls a call of the application so that the failure pattern does not occur the system can more likely be run stably. On the other hand recovery of the application from the error mostly requires a sufficient evaluation period and sufficient operating cost so as not to cause similar problems.

In view of the foregoing it seems necessary to construct a mechanism which performs control so that the system can be run as stably as possible without imposing a load on the system operator if possible while using the application containing the failure. In this case it seems important that the system be capable of being run as stably as possible even if the processing performance degrades to some extent. This is because it is possible to achieve an important object of preventing an economic loss associated with an increase in operating cost and the non operation of the system which occur before the failure is fundamentally solved.

As described above Japanese Unexamined Patent Application Publication Nos. 2010 9127 and 2006 338069 do not consider a situation in which multiple servers such as application servers are disposed as in cloud computing.

Specifically a system according to Japanese Unexamined Patent Application Publication No. 2010 9127 accumulates failure information on the basis of a unique determination criterion and transmits failure information detected based on the determination criterion to a dedicated administrator terminal. However Japanese Unexamined Patent Application Publication No. 2010 9127 does not consider an environment in which application servers and the like are distributed. On the other hand the distributed management system according to the second embodiment has a mechanism which transmits failure information to a distributed environment and prevents a failure on the basis of the failure information.

For a system according to Japanese Unexamined Patent Application Publication No. 2006 338069 when the system predicts or detects failure information on the basis of a unique determination criterion it replaces components to prevent the entire system from failing. However this processing assumes that there are running alternative components. In other words unless there are such components it is not possible to obtain the effect of preventing the entire system from failing. On the other hand the distributed management system according to the second embodiment does not need to consider replacement of components. Even if a component of the application contains a defect the distributed management system can control the operation of the application by identifying the defect as well as can make most use of the component in such a manner that a system failure does not occur.

The distributed management system according to the second embodiment also produces the following effects. When a failure occurs in the application the application server A generates a failure event failure information including information identifying a recovery action recovery processing necessary for the application server A to recover from the failure. The distributed management server extracts the information identifying a recovery action from the failure event issued by the application server A and transmits the information to the application server A. Based on the information identifying a recovery action transmitted by the distributed management server the application server A executes the failure recovery action. Thus even if when a failure occurs the application server A itself cannot execute a failure recovery action it can execute a failure recovery action by performing processing based on a request from the distributed management server . Further even when a failure occurs the system operator does not need to perform the control of a recovery action in each application server and the distributed management server can control a recovery action. Thus the load on the system operator can be reduced.

A failure in the application of the application server A occurs on the basis of a request from a client thereof. The application server B monitors requests from a client thereof on the basis of a failure event generated by the application server A. Thus the distributed management system can prevent failures from being caused by requests from clients.

When a failure greater than or equal to the threshold occurs in an interface of a component first interface in the application server A the application server A identifies the first interface as the cause of the failure. Further the application server A outputs a failure event including as information related the failure another interface second interface in which a failure has occurred at the highest frequency next to that of the first interface. When the first interface is requested by a client the application server B determines whether the second interface is being executed by a thread on the basis of the failure event. If the second interface is being executed the application server B puts execution of the request on hold. This prevents execution of processing which is estimated to be related to the cause of the failure. As a result the distributed management system can prevent a failure more accurately.

When a failure greater than or equal to the threshold occurs in an interface of a component first interface in the application server A the application server A identifies the first interface as the cause of the failure. Further the application server A outputs a failure event including as information related the failure another interface third interface in which a failure greater than or equal to the threshold has occurred. When the first interface is requested by a client the application server B determines whether the third interface is being executed by a thread on the basis of the failure event. If the third interface is being executed the application server B puts execution of the request on hold. This prevents execution of processing which is estimated to be related to the cause of the failure. As a result the distributed management system can prevent a failure more accurately.

When a failure greater than or equal to the threshold occurs in an interface of a component first interface in the application server A the application server A identifies the first interface as the cause of the failure. Further the application server A outputs a failure event including as information related the failure another interface second interface in which a failure has occurred. When the first interface is requested by a client the application server B determines whether the second interface is being executed by a thread on the basis of the failure event. If the second interface is being executed the application server B puts execution of the request on hold. This prevents execution of processing which is estimated to be related to the cause of the failure. As a result the distributed management system can prevent a failure more accurately.

In the above case when the first interface is requested by a client the application server B determines whether the first interface is being executed by a thread on the basis of the failure event. If the first interface is being executed the application server B puts execution of the request on hold. Thus it is possible to further reduce the number of threads which simultaneously execute the processing identified as the cause of the failure. As a result the distributed management system can prevent a failure more accurately.

A failure in the first interface and a failure in the second interface are each for memory usage to reach or exceed the criterion or for CPU usage to reach or exceed the criterion. Thus the distributed management system can accurately prevent a failure caused by the application from occurring frequently. A failure in the first interface may be for memory usage to reach or exceed the criterion and a failure in the second interface may be for CPU usage to reach or exceed the criterion. As seen above with respect to failures which are of different types but have a common character of taking time in being handled the application server includes in a failure event information about components and interfaces which have caused the failures as information identifying the failures and information related to the failures and transmits the failure event. Thus it is possible to further reduce the number of threads which simultaneously perform processing which causes failures having similar characters. As a result the distributed management system can prevent a failure more accurately.

When a deadlock occurs as a failure between an interface of a component first interface and another interface second interface in the application server A the application server A outputs a failure event identifying the first and second interfaces as the cause of the failure. When the first interface is requested by a client the application server B determines whether the second interface is being executed by a thread on the basis of the failure event. When the second interface is being executed the application server B puts processing of the request on hold. As a result the application server of the distributed management system can reliably prevent a deadlock.

The distributed management system according to the second embodiment is applicable to middleware such as Web application servers or computer management applications. Thus it is possible to suppress a system stop or the period thereof associated with a defect in the application. It is also possible to reduce the load imposed on the system operator in coping with a failure.

The present invention is not limited to the above embodiments and changes can be made to the embodiments as appropriate without departing from the spirit and scope of the invention.

For example the application components in the distributed management system according to the second embodiment may be replaced with modules or system components forming a Web application server or the like and subsequently the configuration and processing of a distributed management system thus formed may be configured as in . Even in this case it is possible to prevent a failure such as a deadlock or memory shortage when operating a distributed application server.

While deadlock and excessive CPU or memory consumption are used as examples in the second embodiment the type of a failure is not limited thereto. Similar processing may be performed with respect to the consumption of other resources of the computer.

According to an aspect of the present invention it is possible to provide a distributed system server computer distributed management server and failure prevention method that prevent a failure in a server without imposing a load on the system operator.

The whole or part of the exemplary embodiments disclosed above can be described as but not limited to the following supplementary notes.

A distributed system comprising first and second servers capable of executing the same application wherein

when a failure occurs in the application in the first server the first server generates failure information identifying a cause of the failure in the application and

the second server performs failure prevention processing which is determined based on the failure information and intended to prevent a failure in the application.

The distributed system according to supplementary note 1 further comprising a distributed management server configured to manage the first and second servers wherein

when a failure occurs in the application the first server generates the failure information including information identifying recovery processing necessary for the first server to recover from the failure 

the distributed management server extracts the information identifying the recovery processing from the failure information and transmits the information extracted to the first server and

the first server performs the recovery processing from the failure on the basis of the information identifying the recovery processing transmitted from the distributed management server.

the failure in the application in the first server occurs based on a request from a client of the first server and

the second server monitors a request from a client of the second server on the basis of the failure information.

when a failure greater than or equal to a threshold occurs in a first interface of a first component in the first server the first server identifies the first interface as a cause of the failure and outputs the failure information including a second interface of a second component as information related to the failure the second interface being an interface which has had the most failures next to the first interface among interfaces of the components and

when the first interface is requested by a client of the second server the second server determines whether the second interface is being executed by a thread on the basis of the failure information and if the second interface is being executed prevents processing of the request.

when a failure greater than or equal to a threshold occurs in a first interface of a first component in the first server and when a failure greater than or equal to the threshold occurs in a second interface of a second component in addition to the first interface the first server identifies the first interface as a cause of the failure and outputs the failure information including the second interface as information related to the failure and

when the first interface is requested by a client of the second server the second server determines whether the second interface is being executed by a thread on the basis of the failure information and if the second interface is being executed prevents processing of the request.

when the first interface is requested by a client of the second server the second server determines whether the first interface is already being executed by a thread on the basis of the failure information and if the first interface is being executed prevents processing of the request.

when a deadlock occurs as the failure between a first interface of a first component and a second interface of the second component in the first server the first server outputs the failure information identifying the first and second interfaces as a cause of the failure and

when the first interface is requested by a client of the second server the second server determines whether the second interface is being executed by a thread on the basis of the failure information and if the second interface is being executed prevents processing of the request.

A server computer disposed in a distributed system and connected to another server computer capable of executing the same application wherein

when a failure occurs in the application the server computer generates failure information identifying a cause of the failure in the application and

when the other server generates failure information identifying a cause of a failure in the application the server computer performs failure prevention processing which is determined based on the failure information and intended to prevent a failure in the application.

A distributed management server disposed in a distributed system including first and second servers capable of executing the same application wherein

when the distributed management server receives from the first server failure information identifying a cause of a failure in the application in the first server the distributed management server transmits to the second server the failure information serving as information that the second server uses to perform failure prevention processing for preventing a failure in the application.

In a distributed system including first and second servers capable of executing the same application a failure prevention method for preventing a failure in the application comprising 

when a failure occurs in the application in the first server generating by the first server failure information identifying a cause of the failure in the application and

performing by the second server failure prevention processing which is determined based on the failure information and intended to prevent a failure in the application.

The distributed system according to supplementary note 4 5 or 6 wherein the failure in the first interface and the failure in the second interface are each for memory usage to exceed a criterion or for CPU usage to exceed a criterion.

The distribution according to supplementary note 11 wherein the failure in the first interface is one of for memory usage to exceed the criterion and for CPU usage to exceed the criterion and the failure in the second interface is the other of for memory usage to exceed the criterion and for CPU usage to exceed the criterion.

While the invention has been particularly shown and described with reference to exemplary embodiments thereof the invention is not limited to these embodiments. It will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the claims.

