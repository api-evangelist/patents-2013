---

title: Service compliance enforcement using user activity monitoring and work request verification
abstract: A computer implemented method, data processing system, and computer program product control point in time access to a remote client device and auditing system logs of the remote client device by an auditing server device to determine whether monitored user activity on the remote client device associated with a work request was in compliance with one or more regulations.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09608881&OS=09608881&RS=09608881
owner: International Business Machines Corporation
number: 09608881
owner_city: Armonk
owner_country: US
publication_date: 20130410
---
This application claims the benefit of U.S. Provisional Application No. 61 623 990 filed Apr. 13 2012 the entirety of which is incorporated by reference herein.

The disclosure relates to a computer implemented method data processing system and computer program product for realtime capturing and monitoring of remote activities using a client side identification management agent.

Network security is becoming more and more important as businesses governmental agencies medical institutions financial institutions and educational institutions spend more and more time connected online to provide services to individuals. Network security consists of provisions policies regulations and laws designed to prevent and monitor unauthorized access misuse or modification of network accessible resources. Network security is the authorization of access to resources within a network. Typically users are assigned an identification identifiers such as a user name and a password that allows the users access to the network accessible resources on a network within their security level clearance. In other words network security secures the network by protecting and monitoring operations being performed on network accessible resources.

The illustrative embodiments herein provide a system for user activity capturing and monitoring services. The invention has a server client architecture. The client side consists of an agent which performs single sign on actions for corresponding applications and a few monitoring modules which captures user activity and transfer activity data to the server component. Each application workflow determines the right interface and right step to perform single sign on and calls individual monitoring modules to perform monitoring actions based on the nature of the application. Activities such as user login logout all keystroke mouse click and server response are captured and monitored. Each activity monitored by the modules is also logged in the database with each session differentiated by a session identifiers.

For console access such as Secure Shell multiple Secure Shell sessions or nested Secure Shell sessions can be differentiated.

For graphical user interface applications such as Tool for Oracle Application Developers TOAD for database access Remote Desktop Protocol for remote Windows server access activity logs are linked with window title keystrokes mouse clicks and critical screenshots. This is achieved via an event driven snapshot taking mechanism which ensures high performance and low storage size. The resulted log is also searchable via title or command text.

As will be appreciated by one skilled in the art aspects of the present invention may be embodied as a system method or computer program product. Accordingly aspects of the present invention may take the form of an entirely hardware embodiment an entirely software embodiment including firmware resident software micro code etc. or an embodiment combining software and hardware aspects that may all generally be referred to herein as a circuit module or system. Furthermore aspects of the present invention may take the form of a computer program product embodied in one or more computer readable medium s having computer readable program code embodied thereon.

Any combination of one or more computer readable medium s may be utilized. The computer readable medium may be a computer readable signal medium or a computer readable storage medium. A computer readable storage medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus or device or any suitable combination of the foregoing. More specific examples a non exhaustive list of the computer readable storage medium would include the following an electrical connection having one or more wires a portable computer diskette a hard disk a random access memory RAM a read only memory ROM an erasable programmable read only memory EPROM or Flash memory an optical fiber a portable compact disc read only memory CD ROM an optical storage device a magnetic storage device or any suitable combination of the foregoing. In the context of this document a computer readable storage medium may be any tangible medium that can contain or store a program for use by or in connection with an instruction execution system apparatus or device.

A computer readable signal medium may include a propagated data signal with computer readable program code embodied therein for example in baseband or as part of a carrier wave. Such a propagated signal may take any of a variety of forms including but not limited to electro magnetic optical or any suitable combination thereof. A computer readable signal medium may be any computer readable medium that is not a computer readable storage medium and that can communicate propagate or transport a program for use by or in connection with an instruction execution system apparatus or device.

Program code embodied on a computer readable medium may be transmitted using any appropriate medium including but not limited to wireless wireline optical fiber cable RF etc. or any suitable combination of the foregoing.

Computer program code for carrying out operations for aspects of the present invention may be written in any combination of one or more programming languages including an object oriented programming language such as Java Smalltalk C or the like and conventional procedural programming languages such as the C programming language or similar programming languages. The program code may execute entirely on the user s computer partly on the user s computer as a stand alone software package partly on the user s computer and partly on a remote computer or entirely on the remote computer or server. In the latter scenario the remote computer may be connected to the user s computer through any type of network including a local area network LAN or a wide area network WAN or the connection may be made to an external computer for example through the Internet using an Internet Service Provider .

Aspects of the present invention are described below with reference to flowchart illustrations and or block diagrams of methods apparatus systems and computer program products according to embodiments of the invention. It will be understood that each block of the flowchart illustrations and or block diagrams and combinations of blocks in the flowchart illustrations and or block diagrams can be implemented by computer program instructions. These computer program instructions may be provided to a processor of a general purpose computer special purpose computer or other programmable data processing apparatus to produce a machine such that the instructions which execute via the processor of the computer or other programmable data processing apparatus create means for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

These computer program instructions may also be stored in a computer readable medium that can direct a computer other programmable data processing apparatus or other devices to function in a particular manner such that the instructions stored in the computer readable medium produce an article of manufacture including instructions which implement the function act specified in the flowchart and or block diagram block or blocks.

The computer program instructions may also be loaded onto a computer other programmable data processing apparatus or other devices to cause a series of operational steps to be performed on the computer other programmable apparatus or other devices to produce a computer implemented process such that the instructions which execute on the computer or other programmable apparatus provide processes for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

With reference now to the figures and in particular with reference to diagrams of data processing environments are provided in which illustrative embodiments may be implemented. It should be appreciated that the Figures are only meant as examples and are not intended to assert or imply any limitation with regard to the environments in which different embodiments may be implemented. Many modifications to the depicted environments may be made.

In the depicted example server and server connect to network along with storage unit . Server may be for example an auditing server device that illustrative embodiments use to audit system audit logs of remote client devices to determine whether monitored user activity on the remote client device associated with a work request was in compliance with one or more regulations. A work request is a work order or work instruction that typically is or includes incident problem or change ticket information regarding the remote client device. The work request may either be automatically generated by the remote client device itself or may be manually generated by a user of the remote client device. The work request is used to have an identified problem corrected on the remote client device by an end user on an end user workstation device via network . A regulation may be for example a federal regulation provided by FFIEC HIPAA or RTIA. FFIEC is the Federal Financial Institutions Examination Council. FFIEC is a formal interagency body of the United States government empowered to prescribe uniform principles standards and report forms for the federal examination of financial institutions. HIPAA is the Health Insurance Portability and Accountability Act enacted by the United States which addresses the security and privacy of healthcare data. RTIA is the Right to Information Act enacted by the Parliament of India which allows access to access to government documents and information.

Server may be for example a system log management server device that receives audit logs from a plurality of remote client devices. The audit logs of the remote client devices include the end user workstation device activities performed on the remote client devices to correct the problems associated with the work requests. In addition the system log management server device may store the audit logs in the form of audit log reports for each of the plurality of remote client devices. Further server and server may each represent a plurality of server devices.

Storage unit is a network storage device capable of storing data in a structured or unstructured format. The data stored in storage unit may be data of any type. Storage unit may be for example an activity logging database system that stores work request information received from a plurality of remote client devices.

Clients and also connect to network . Client computers and may be for example network server devices that provide IT services such as financial services or medical services to individuals connected to network . The financial service may be regulated by FFIEC regulations and the medical service may be regulated by HIPAA regulations for example. However it should be noted that client computers and may provide other types of IT services that may be regulated by other types of regulations. A regulated IT service is a service that is not available for unrestricted network access. For example a medical services application may provide online access to confidential medical history data that is protected under HIPAA regulations. Thus access to and activities performed on a remote client device that stores this confidential medical data must be monitored and audited to determine whether HIPAA regulations are complied with. An activity or task associated with a work request performed on a remote client device that stores confidential data may be for example resetting a password applying a new security patch configuring a software application or testing a hardware component.

In the depicted example server computer provides information such as boot files operating system images and applications to client computers and . Client computers and are clients to server computer and server computer . Also network data processing system may include additional server computers client computers and other devices not shown.

Program code located in network data processing system may be stored on a computer recordable storage medium and downloaded to a computer or other device for use. For example program code may be stored on a computer recordable storage medium on server and downloaded to client over network for use on client .

In the depicted example network data processing system is the Internet with network representing a worldwide collection of networks and gateways that use the Transmission Control Protocol Internet Protocol TCP IP suite of protocols to communicate with one another. At the heart of the Internet is a backbone of high speed data communication lines between major nodes or host computers consisting of thousands of commercial governmental educational and other computer systems that route data and messages. Of course network data processing system also may be implemented as a number of different types of networks such as for example an intranet a local area network LAN or a wide area network WAN . is intended as an example and not as an architectural limitation for the different illustrative embodiments.

With reference now to a diagram of a data processing system is depicted in accordance with an illustrative embodiment. Data processing system is an example of a computer such as server or client in in which computer usable program code or instructions implementing processes of illustrative embodiments may be located. In this illustrative example data processing system includes communications fabric which provides communications between processor unit memory persistent storage communications unit input output I O unit and display .

Processor unit serves to execute instructions for software applications or programs that may be loaded into memory . Processor unit may be a set of one or more processors or may be a multi processor core depending on the particular implementation. Further processor unit may be implemented using one or more heterogeneous processor systems in which a main processor is present with secondary processors on a single chip. As another illustrative example processor unit may be a symmetric multi processor system containing multiple processors of the same type.

Memory and persistent storage are examples of storage devices . A storage device is any piece of hardware that is capable of storing information such as for example without limitation data program code in functional form and or other suitable information either on a transient basis and or a persistent basis. Memory in these examples may be for example a random access memory or any other suitable volatile or non volatile storage device. Persistent storage may take various forms depending on the particular implementation. For example persistent storage may contain one or more devices. For example persistent storage may be a hard drive a flash memory a rewritable optical disk a rewritable magnetic tape or some combination of the above. The media used by persistent storage may be removable. For example a removable hard drive may be used for persistent storage .

Communications unit in this example provides for communication with other data processing systems or devices. In this example communications unit is a network interface card. Communications unit may provide communications through the use of either or both physical and wireless communications links.

Input output unit allows for the input and output of data with other devices that may be connected to data processing system . For example input output unit may provide a connection for user input through a keyboard a mouse and or some other suitable input device. Further input output unit may send output to a printer. Display provides a mechanism to display information to a user.

Instructions for the operating system applications and or programs may be located in storage devices which are in communication with processor unit through communications fabric . In this illustrative example the instructions are in a functional form on persistent storage . These instructions may be loaded into memory for running by processor unit . The processes of the different embodiments may be performed by processor unit using computer implemented instructions which may be located in a memory such as memory . These instructions are referred to as program code computer usable program code or computer readable program code that may be read and run by a processor in processor unit . The program code in the different embodiments may be embodied on different physical or computer readable storage media such as memory or persistent storage .

Program code is located in a functional form on computer readable media that is selectively removable and may be loaded onto or transferred to data processing system for running by processor unit . Program code and computer readable media form computer program product . In one example computer readable media may be computer readable storage media or computer readable signal media . Computer readable storage media may include for example an optical or magnetic disc that is inserted or placed into a drive or other device that is part of persistent storage for transfer onto a storage device such as a hard drive that is part of persistent storage . Computer readable storage media also may take the form of a persistent storage such as a hard drive a thumb drive or a flash memory that is connected to data processing system . In some instances computer readable storage media may not be removable from data processing system .

Alternatively program code may be transferred to data processing system using computer readable signal media . Computer readable signal media may be for example a propagated data signal containing program code . For example computer readable signal media may be an electro magnetic signal an optical signal and or any other suitable type of signal. These signals may be transmitted over communication links such as wireless communication links an optical fiber cable a coaxial cable a wire and or any other suitable type of communications link. In other words the communications link and or the connection may be physical or wireless in the illustrative examples. The computer readable media also may take the form of non tangible media such as communication links or wireless transmissions containing the program code.

In some illustrative embodiments program code may be downloaded over a network to persistent storage from another device or data processing system through computer readable signal media for use within data processing system . For instance program code stored in a computer readable storage media in a server data processing system may be downloaded over a network from the server to data processing system . The data processing system providing program code may be a server computer a client computer or some other device capable of storing and transmitting program code .

The different components illustrated for data processing system are not meant to provide architectural limitations to the manner in which different embodiments may be implemented. The different illustrative embodiments may be implemented in a data processing system including components in addition to or in place of those illustrated for data processing system . Other components shown in can be varied from the illustrative examples shown. The different embodiments may be implemented using any hardware device or system capable of executing program code. As one example data processing system may include organic components integrated with inorganic components and or may be comprised entirely of organic components excluding a human being. For example a storage device may be comprised of an organic semiconductor.

As another example a storage device in data processing system is any hardware apparatus that may store data. Memory persistent storage and computer readable media are examples of storage devices in a tangible form.

In another example a bus system may be used to implement communications fabric and may be comprised of one or more buses such as a system bus or an input output bus. Of course the bus system may be implemented using any suitable type of architecture that provides for a transfer of data between different components or devices attached to the bus system. Additionally a communications unit may include one or more devices used to transmit and receive data such as a modem or a network adapter. Further a memory may be for example memory or a cache such as found in an interface and memory controller hub that may be present in communications fabric .

The illustrative embodiments herein provide a system for user activity capturing and monitoring services. The invention has a server client architecture. The client side consists of an agent which performs single sign on actions for corresponding applications and a few monitoring modules which are exported as dynamic link library application program interfaces. Each application workflow determines the right interface and right step to perform single sign on and calls individual monitoring modules to perform monitoring actions based on the nature of the application. Activities such as user login logout are logged on server audit log database by default. Each activity monitored by the modules is also logged in the database with each session differentiated by a session identifiers.

Activities such as Secure Shell are captured when the command is entered. A separate session identifiers is assigned to the Secure Shell session to differentiate it from the parent session. So that multiple Secure Shell sessions or nested Secure Shell sessions can be differentiated.

For graphical user interface applications such as Tool for Oracle Application Developers TOAD for database access Remote Desktop Protocol for remote Windows server access activity logs are linked with window title keystrokes mouse clicks and critical screenshots. This is achieved via an event driven snapshot taking mechanism which ensures high performance and low storage size. The resulted log is also searchable via title or command text.

Referring now to an information technology delivery system is shown according to an illustrative embodiment. System is a network data processing system such as network data processing system of .

System includes integrated management system server . Integrated management system server is a server such as one of servers or server of . Integrated management system server is a central repository for user data user access profiles identity wallets and machine profiles. Integrated management system server provides a Web based interface to administrate users and policies.

Integrated management system server provides a central point of administration and control. Integrated management system server enables centralized management of user identities application specific workflows and authentication policies. Integrated management system server also provides loss management of authentication tokens certificate management and audit management Administrator desktop gateway includes base agent . Base agent is a software component that can identify and notify common problems with applications on endpoint systems that are monitored by base agent .

Administrator desktop gateway includes application workflow profile . Application workflow profile is a set of instructions that handles workflow automation for supported desktop applications on endpoint systems . In one illustrative embodiment application workflow profile is constructed as a state engine consisting of states triggers and actions. Application workflow profile can contain instructions for performing automatic operations for user logon user logoff user change or reset password and other customized activities the application might present. Application workflow profile might consist of any combination of these activities and more depending on business requirements and users needs.

In one illustrative embodiment application workflow profile is associated with and uniquely mapped to only one application. An application can be an executable file .EXE or a web page each of which is a unique process on endpoint system . Application workflow profile is loaded in runtime and begins its automation workflow when application workflow profile detects that the relative application is initiated on endpoint system .

Administrator desktop gateway includes monitoring module . Monitoring module is one or more software modules that log event messages to audit log server . The event messages can be for example but not limited to state changes detected by application specific workflow or monitoring workflow . Events are provided to server audit log server in audit logs .

Audit log server includes application user policies and monitoring policies . Application user policies and monitoring policies may define for example which user commands are blocked and which user commands are allowed which user activities are recorded in a system audit log and which user activities are not and which user activities require immediate action.

Audit log server includes audit logs provided by monitoring module . Audit logs are records of user and administration activity as determined by application specific workflows and monitoring workflow.

Referring now to an in depth information technology delivery system is shown according to an illustrative embodiment. System is system of .

Agent is a client side software system that communicates with and performs tasks for the integrated management system server . Communication and tasks can be performed to synchronize data changes with integrated management system server . In one illustrative embodiment agent can cache data locally on disk based on policies such as application policy and monitoring policy . Application policy is one or more of application user policies of . Monitoring policy is one or more of monitoring policies of . As such agent is able to perform most of its functions even if it is not connected to integrated management system server at any point in time.

Agent is responsible for authenticating a user. Because of its local cache agent can automate single sign on into operating system and to a set of applications that are defined in application specific workflow . Agent can extend the Windows Graphical Identification and Authentication GINA dynamic link library chain to provide additional functions for self service or strong authentication.

Integrated management system server is integrated management system server of . Integrated management system server is a central repository for user data user access profiles identity wallets and machine profiles. Integrated management system server provides a Web based interface to administrate users and policies.

Integrated management system server provides a central point of administration and control. Integrated management system server enables centralized management of user identities application specific workflow and authentication policies. Integrated management system server also provides loss management of authentication tokens certificate management and audit management.

Wallet holds the user credentials that are required for single sign on. Wallet is loaded from the integrated management system server into the agent after successful authentication of the user so that wallet is available even when the endpoint is disconnected from the computer network. To protect the credentials against tampering or stealing wallet is encrypted with a strong encryption mechanism.

Agent includes plug ins . Plug ins are blocks of code that perform some custom action needed as part of a workflow trigger or workflow action inside application specific workflow . In one illustrative embodiment can be for example but not limited to VBScript or JavaScript. Using the user s access privileges plug ins can make calls into operating system as well as into other ones of plug ins .

Agent typically uses plug ins to implement customized authentication access control or workflow automation for a specific application. This customized authentication access control or workflow automation can include but is not limited to retrieving application credential from wallet retrieving a user policy setting from wallet looking up a user s group membership or attribute from a user directory reading or storing data from a central fileshare looking up the time from the host system clock performing an additional checksum or check the installation path on a target application prior to single sign on calling an external application or process and making an HTTPS call to a third party service.

Agent includes observer layer . Observer layer is a software component that performs necessary logon logoff and automation actions into various applications run by system . When an application presents a request for credentials observer layer is responsible for the appropriate action.

In one illustrative embodiment observer layer is composed of a core module and a number of agent instances that are hooked into various applications. The applications can include for example but not limited to for example IBM Lotus Notes application Microsoft Outlook and Microsoft Internet Explorer . The behavior of the number of agent instances within each application is driven by application specific workflow .

Automated trigger layer and automated trigger layer cause transitions between states in application specific workflow . Automated trigger layer and automated trigger layer define when a condition is true. For example automated trigger layer and automated trigger layer can define when a Windows executable window is created when a Web document completes loading when an HTML element is clicked and when an operating system executable button within a graphical user interface is clicked.

Application specific workflow is application workflow profile of . Application specific workflow is a set of instructions that handles workflow automation for supported applications in operating system . In one illustrative embodiment application specific workflow is constructed as a state engine consisting of states triggers and actions. Application specific workflow can contain instructions for performing automatic operations for user logon user logoff user change or reset password and other customized activities the application might present. Application specific workflow might consist of any combination of these activities and more depending on business requirements and users needs. In one illustrative embodiment application specific workflow is an XML structured file that provides a declarative set of pre conditions that can be detected by automated trigger layer and automated trigger layer to cause transitions between states in application specific workflow .

In one illustrative embodiment application specific workflow is associated with and uniquely mapped to only one application. An application can be an executable file .EXE or a web page each of which is a unique process on an endpoint system or administrator desktop gateway. The endpoint system can be for example endpoint system of . The administrator desktop gateway can be for example administrator desktop gateway of .

Application specific workflow is loaded in runtime and begins its automation workflow when application specific workflow detects that the relative application is initiated on an endpoint system or administrator desktop gateway. The endpoint system can be for example endpoint system of . The administrator desktop gateway can be for example administrator desktop gateway of .

Monitoring workflow is a set of instructions that provide workflow automation applications. Monitoring workflow detects changes to the position or title of the current active window or a mouse or keyboard event. When such event is detected monitoring workflow gives a callback to one of set of triggers .

Set of triggers can include for example command capturing for console access trigger . Set of triggers can include for example activity logging for bitmapped console trigger . Set of triggers can include for example activity logging for GUI applications trigger .

Monitoring components are software modules such as for example but not limited to application programming interface applications that log event messages to integrated management system server . The event messages can be for example but not limited to state changes detected by application specific workflow or monitoring workflow . Events are provided to server in audit logs .

Monitoring component can include for example bitmap recognition module . In one illustrative embodiment the bitmap recognition module comprises an optical character recognition module to capture bit mapped application processes.

Monitoring component can include for example screen capturing module . In one illustrative embodiment screen capturing module dynamically captures application screenshots based on user input that causes a state change within either application specific workflow or monitoring workflow .

Monitoring component can include for example graphical user interface module . In one illustrative embodiment graphical user interface module dynamically captures a window title of a current active application as well as any button name that is interacted with in the graphical user interface as an activity signature. In one illustrative embodiment graphical user interface module can include a trigged when though a window monitoring process to trigger a log on process.

Monitoring component can include for example command and response module . In one illustrative embodiment command and response module captures user input such as but not limited to key strokes and mouse clicks.

Audit logs are records of user and administration activity as determined by application specific workflow and monitoring workflow that are stored in integrated management system server .

Audit logs can provide logs of different activity. For example audit logs may provide a logged record of user system and administrator activities. User and administrator logs track user administrator and help desk activity. The user and administrator logs are considered the audit logs and are written to integrated management system server . The system logs are message and error logs for integrated management system server itself primarily used for troubleshooting server issues and monitoring the system health.

Triggers are software mechanisms that detect an occurrence of an event defined by one of application specific workflow or monitoring workflow . In response to detecting the event triggers then cause the creation of audit log .

In one illustrative embodiment trigger is a command capturing for console access. When a user attempts a log on process trigger invokes one or more of monitoring components .

In one illustrative embodiment trigger is an activity logger for bitmapped console applications. In response to determining a change by a bitmapped recognition module trigger invokes one or more of monitoring components .

In one illustrative embodiment trigger is an activity logger for applications graphical user interfaces. In response to detecting an interaction with an icon or other graphical user interface element trigger invokes one or more of monitoring components .

Referring now to a flow chart for command capturing within a profile is shown according to an illustrative embodiment. Process is a software process executing on a software component such as application specific workflow of .

Process begins when an application is opened on an endpoint system or administrator desktop gateway step . The application can be for example one of applications of . The endpoint system can be for example endpoint system of . The administrator desktop gateway can be for example administrator desktop gateway of .

Process then performs identification injection capturing and checkout step . Identification injection capturing and checkout is a process that retrieves any necessary user credentials that are required for access of an application and applies those credentials to a checkout procedure. The credentials can be stored in a wallet such as wallet of . Process then generates a session identifier step . The session identifier is a unique identifier that is sent with each request made by the logged on user.

Process then makes a call to a monitoring module transferring the captured information step . The monitoring module can be for example monitoring components of .

Responsive to making the call to the monitoring module process continues with any regular workflow step with the process terminating thereafter.

Referring now to a data flow chart for command capturing within a monitoring module is shown according to an illustrative embodiment. Monitoring module is one of monitoring components of .

Monitoring module logs session identifier user identifier hostname internet protocol address application name calls a privilege identification manager .

Monitoring module receives user input and then captures any server response . The server response can be sequentially captured into a same buffer as the user input.

Monitoring module then logs the session identifiers along with the sequential user input and server response.

In one illustrative embodiment the buffer is split into 500 byte chunks. The size is chosen due to a 512 byte of the description field in a user activity log table.

Monitoring module logs session id and log data chunk . If the privilege identification dies monitoring module terminates monitoring.

Referring now to a flowchart for activity capturing in a bitmapped console is shown according to an illustrative embodiment. Process is a software process executing on a software component such as in a command policy of an integrated management server system such as integrated management server system of . The command policy can be for example one of application specific workflow or monitoring workflow of .

Process triggers a screenshot upon the occurrence of a trigger. The trigger can be for example one of triggers of .

Responsive to the trigger determining a keystroke a screenshot of the bitmapped console is triggered step . The keystroke can be for example a depress of the enter return key.

Responsive to the trigger determining a mouse click a screenshot of the bitmapped console is triggered step . Process then returns to step in an iterative manner log additional activities.

Referring now to a flowchart for activity capturing in a bitmapped console is shown according to an illustrative embodiment. Process is a software process executing on a software component such as in a profile of an integrated management server system such as integrated management server system of . The profile can be for example one of application specific workflow or monitoring workflow of . The profile can be a profile for a bitmapped console such as a remote desktop profile.

Process begins when an application is opened on an endpoint system or administrator desktop gateway step . The application can be for example one of applications of . The endpoint system can be for example endpoint system of . The administrator desktop gateway can be for example administrator desktop gateway of .

Process then performs identification injection capturing and checkout step . Identification injection capturing and checkout is a process that retrieves any necessary user credentials that are required for access of an application and applies those credentials to a checkout procedure. The credentials can be stored in a wallet such as wallet of .

Process then generates a session identifier step . The session identifier is a unique identifier that is sent with each request made by the logged on user.

Process then makes a log entry logging the captured information step . The logging information can be transferred as audit logs of .

Process then retrieves a screenshot trigger policy from the integrated management server step . The screenshot trigger policy can be one of application policy of or monitoring policy of .

While refers to calling the screenshot module it is understood that the screenshot module can be incorporated into or combined with other modules. For example the screenshot may be taken the detection module such as the detection module described in . Furthermore it is understood that the capture may be constrained by some conditions such as for example but not limited to that a screenshot of should be taken only if only if certain windows are visible on a user s desktop.

Referring now to a flowchart of a process for capturing activity in a bitmapped console is shown according to an illustrative embodiment. Process is a software process executing on a software component such as monitoring module of .

Process begins when a session identifier is received step . The session identifier can be received in response to the name of the Remote Desktop s address.

Process determines the active window step . An active window is the currently focused window in the current window manager or explorer. The active window can be the window that is currently being used by the user.

Process extracts the active window title step . The window title for the active window is text that appears within a title bar at the top of the active window.

Process determines any change to the window title step . Changes to the window title can be determined by performing optical character recognition to the title bar of the active window and comparing detected text to previous recognized window.

Process then records user input step . User input can be for example but not limited to key strokes and mouse clicks.

Process then logs the screenshot along with the session identifier as well as all captured text and extracted text step with the process terminating thereafter.

Referring now to a flowchart of a process for capturing activity in a bitmapped console for a screenshot module is shown according to an illustrative embodiment. Process is a software process executing on a software component such as monitoring module of .

Process begins by receiving a call from another monitoring module step . The call can be for example a call such as the call of step of . The call can include a session identifier for the triggered application.

Process takes a screenshot of the desired window step . The desired window is the graphical user interface into which a user action was entered and detected. The desired can be for example the active window. For example the screenshot can include the entire remote desktop profile.

Process converts and compresses the screenshot into a storage format step . In one illustrative embodiment the storage format can be for example but not limited to a binary format.

Process then applies a data encoding compression to the screenshot step . According to one illustrative embodiment a lossy compression can be applied to a background of the screenshot while a lossless compression is applied to the foreground. The foreground of the screenshot can include for example but not limited to the active window. The background of the screenshot can include for example but not limited to other windows or icons visible within the screenshot not including the active window. Lossless compression use data compression algorithms that allows for exact reconstruction of the foreground from compressed data. However lossy compression does not produce an exact reconstruction of the background from the compressed data.

Process then performs an XOR operation with a preview screenshot to extract a delta between the two screenshot step .

Process then log the session identifier and image fits step with the process terminating thereafter. The image fits include at least the delta file.

Referring now to a flowchart for is an event driven screenshot is shown according to an illustrative embodiment.

Process begins by receiving an initial workflow step . The initial workflow is application specific workflow or monitoring workflow of .

Responsive to receiving the initial workflow process forwards the initial workflow to an optical character recognition module step and begins monitoring by following the visual activity of the screen image and or the user s use of mouse and keyboard. In one illustrative embodiment the detection of mouse clicks and keyboard events is performed externally from VOP such as for example but not limited to by an application such as IBM Tivoli Access Manager for Enterprise Single Sign On TAMESSO .

Process then detects an event step . The event can be detected by the triggering of a trigger such as one of triggers of .

In response to the event being a change to a change of caption step process captures a screenshot step . The screenshot can be captured according to process of .

Responsive to capturing the screenshot process logs the session id and any recorded keystroke or mouse events step with the process terminating thereafter. The session id and the recorded keystroke or mouse events can be logged as audit logs of .

Returning now to step responsive to the event being a mouse click step process captures the event step . By capturing the mouse click event process stores the metadata associated with the event such as for example but not limited to a kind of the mouse click a position of the pointer and a button identification that is utilized for the click.

Process forwards the event to the monitored application step . In one illustrative embodiment the mouse monitoring adds a set of hooks to mouse handling chain of the operating system. When a mouse event is triggered the hook captures or does something with the event for example reads metadata associated with the mouse event. The hook then releases the event back to the event chain. In this manner the monitoring will not interfere the processing just delay it marginally.

Process waits for image stabilization step as described above. Waiting for Image stabilization means waiting for certain processes to complete. When a screen image is updated the image does not usually refresh instantly but rather refreshes in a sweeping manner. Furthermore sometimes a graphical user interface might take some time to load it graphics. Some content is shown immediately for example but not limited to menus while other content takes some time to be retrieved. By waiting for Image stabilization process waits for the whole screen image or part of the screen image not to change any more.

Returning now to step responsive to the event being a change to the keyboard state machine step process determines if the change to the state machine was due to a keystroke of a target key step . The keystroke of a target key can be for example a depress of the enter return key. Responsive to determining that change to the state machine was due to a keystroke of a target key yes at step process proceeds to step to capture the event.

Responsive to determining that change to the state machine was not due to a keystroke of a target key no at step process then determines whether a predetermined time has passed since the last key press step . Responsive to determining that the time passed since the last key press is less than some predetermined less than threshold at step process iterates back to step .

Responsive to determining that the time passed since the last key press is larger than some predetermined larger than threshold at step process proceeds to proceeds to step to capture the event.

Referring now to an illustration of a series of audit logs is shown according to an illustrative embodiment. Audit logs are audit logs such as audit logs of .

Audit logs are audit logs of graphical user interface and bitmapped applications. The console applications can be applications such as applications of .

Audit log is an audit log taken at time indicated by timestamp T. Audit log includes a session identifier a user identifier a system identifier an application identifier and a server identifier. This information can be captured by monitoring components such as Monitoring components of . Additionally audit log includes an indication of the action triggering the audit log. Here a login action by user U triggers audit log .

Audit log is an audit log taken at time indicated by timestamp T. Audit log includes a session identifier. This information can be captured by monitoring components such as monitoring components of . Additionally audit log includes an indication of the action triggering the audit log. Here a command input into window title of xyz by user U triggers audit log .

Audit log also includes a screenshot of window title at time indicated by timestamp T. The screenshot can be determined for example by process of .

Audit log is an audit log taken at time indicated by timestamp T. Audit log includes a session identifier. This information can be captured by monitoring components such as Monitoring components of . Additionally audit log includes an indication of the action triggering the audit log. Here a left mouse click of button name within window title by user U triggers audit log .

Audit log also includes a screenshot of window title at time indicated by timestamp T. The screenshot can be determined for example by process of .

Audit log is an audit log taken at time indicated by timestamp T. Audit log includes a session identifier. This information can be captured by monitoring components such as Monitoring components of . Additionally audit log includes an indication of the action triggering the audit log. Here a close of window of the monitored application triggers audit log .

Audit logs are audit logs of console applications. The console applications can be applications such as applications of .

Audit log is an audit log taken at time indicated by timestamp T. Audit log includes a session identifier a user identifier a system identifier an application identifier and a server identifier. This information can be captured by monitoring components such as monitoring components of . Additionally audit log includes an indication of the action triggering the audit log. Here a login action by user U triggers audit log .

Audit log is an audit log taken at time indicated by timestamp T. Audit log includes a session identifier. This information can be captured by monitoring components such as monitoring components of . Additionally audit log includes an indication of the action triggering the audit log and any server response. Here a command of xyz by user U and a server response of abc triggers audit log .

Audit log is an audit log taken at time indicated by timestamp T. Audit log includes a session identifier. This information can be captured by monitoring components such as monitoring components of . Additionally audit log includes an indication of the action triggering the audit log and any server response. Here a command of xyz by user U and a server response of abc triggers audit log .

Audit log is an audit log taken at time indicated by timestamp T. Audit log includes a session identifier. This information can be captured by monitoring components such as monitoring components of . Additionally audit log includes an indication of the action triggering the audit log. Here a close of window of the monitored application triggers audit log .

Referring now to a flow chart for applying a policy to recorded event is shown according to an illustrative embodiment. Process is a software process executing on a software component such as application specific workflow of .

Process begins by receiving data from a client step . The data can include for example a screenshot along with any associated mouse event or keyboard event.

Process then retrieves a security policy step . The security policy can be for example a policy such as application policy and monitoring policy .

Process then determines applies a pattern matching algorithm to the data received from the client according to security policy step . Based on results from the pattern matching algorithm process can record the data step record the data and raise alert to security team step or record the data and terminate the client step . Process terminates thereafter.

Thus the illustrative embodiments herein provide a system for user activity capturing and monitoring services. The invention has a server client architecture. The client side consists of an agent which performs single sign on actions for corresponding applications and a few monitoring modules which are exported as dynamic link library application program interfaces. Each application workflow determines the right interface and right step to perform single sign on and calls individual monitoring modules to perform monitoring actions based on the nature of the application. Activities such as user login logout are logged on server audit log database by default. Each activity monitored by the modules is also logged in the database with each session differentiated by a session identifiers.

Activities such as Secure Shell are captured when the command is entered. A separate session identifiers is assigned to the Secure Shell session to differentiate it from the parent session. Multiple Secure Shell sessions or nested Secure Shell sessions can be differentiated.

For graphical user interface applications such as Tool for Oracle Application Developers TOAD for database access Remote Desktop Protocol for remote Windows server access activity logs are linked with window title keystrokes mouse clicks and critical screenshots. This is achieved via an event driven snapshot taking mechanism which ensures high performance and low storage size. The resulted log is also searchable via title or command text.

Thus illustrative embodiments of the present invention provide a computer implemented method data processing system and computer program product for controlling point in time access to a remote client device and auditing system logs of the remote client device by an auditing server device to determine whether monitored user activity on the remote client device associated with a work request was in compliance with one or more regulations. The flowchart and block diagrams in the Figures illustrate the architecture functionality and operation of possible implementations of systems methods and computer program products according to various embodiments of the present invention. In this regard each block in the flowchart or block diagrams may represent a module segment or portion of code which comprises one or more executable instructions for implementing the specified logical function s . It should also be noted that in some alternative implementations the functions noted in the block might occur out of the order noted in the figures. For example two blocks shown in succession may in fact be executed substantially concurrently or the blocks may sometimes be executed in the reverse order depending upon the functionality involved. It will also be noted that each block of the block diagrams and or flowchart illustration and combinations of blocks in the block diagrams and or flowchart illustration can be implemented by special purpose hardware based systems that perform the specified functions or acts or combinations of special purpose hardware and computer instructions.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises and or comprising when used in this specification specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

The corresponding structures materials acts and equivalents of all means or step plus function elements in the claims below are intended to include any structure material or act for performing the function in combination with other claimed elements as specifically claimed. The description of the present invention has been presented for purposes of illustration and description but is not intended to be exhaustive or limited to the invention in the form disclosed. Many modifications and variations will be apparent to those of ordinary skill in the art without departing from the scope and spirit of the invention. The embodiment was chosen and described in order to explain best the principles of the invention and the practical application and to enable others of ordinary skill in the art to understand the invention for various embodiments with various modifications as are suited to the particular use contemplated.

