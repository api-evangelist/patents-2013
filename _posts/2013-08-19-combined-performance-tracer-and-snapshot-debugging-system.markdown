---

title: Combined performance tracer and snapshot debugging system
abstract: A tracing and debugging system may collect both performance related tracer data and snapshot data. The tracer data may contain aggregated performance and operational data, while the snapshot data may contain call stack, source code, and other information that may be useful for debugging and detailed understanding of an application. The snapshot data may be stored in a separate database from the tracer data, as the snapshot data may contain data that may be private or sensitive, while the tracer data may be aggregated information that may be less sensitive. A debugging user interface may be used to access, display, and browse the stored snapshot data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09021444&OS=09021444&RS=09021444
owner: Concurix Corporation
number: 09021444
owner_city: Kirkland
owner_country: US
publication_date: 20130819
---
Crash dumps are datasets that may be collected when a computer program encounters an error for which the computer can no longer function. Operating systems and other software management products may collect data at a catastrophic failure so that a programmer may be able to detect the cause of the failure. The programmer may then be able to recreate the error or make changes that may prevent the error from occurring again.

A tracing and debugging system may take a snapshot of an application in response to an event and may continue executing the program after the snapshot is captured. The snapshot may be stored and retrieved later in a debugging tool where a programmer may browse the snapshot or the snapshot may have some other analysis performed. The snapshot may contain a subset of the state of the application such as call stacks portions of source code the values of local and global variables and various metadata. The snapshot may be defined in a snapshot configuration that may include an event description and data to be collected.

A tracing and debugging system may collect both performance related tracer data and snapshot data. The tracer data may contain aggregated performance and operational data while the snapshot data may contain call stack source code and other information that may be useful for debugging and detailed understanding of an application. The snapshot data may be stored in a separate database from the tracer data as the snapshot data may contain data that may be private or sensitive while the tracer data may be aggregated information that may be less sensitive. A debugging user interface may be used to access display and browse the stored snapshot data.

A debugging system may display snapshot information that may be collected in response to an event identified while an application executes. The debugging system may allow a user to browse the various data elements in the snapshot and may allow the user to modify a snapshot configuration by including or excluding various data elements within the snapshot data. The user interface may have a mechanism for including or excluding data elements that may be presented during browsing as well as options to change the events that may trigger a snapshot. The updated snapshot configuration may be saved for future execution when the event conditions are satisfied.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

A snapshot debugging system may take snapshots of an application in response to an event and store the snapshots for later viewing. The snapshots may occur as an application executes and may collect various program state at the designated events. The program state may include local and global variable values call stacks source code related to the executing code and other information.

A debugging interface may be used to view browse or otherwise inspect the contents of each snapshot. In some cases the snapshots may be relatively lightweight glimpses of the program as each event is detected. A programmer may define snapshots for conditions where problems may have occurred in the past and the snapshots may allow the programmer the ability to look back to the program state at the time of the event to determine the causes and effects of the monitored event.

The snapshot mechanism may be deployed in several manners. In a simple implementation a programmer may manually insert snapshot code into an application. The snapshot code may include conditions that when satisfied cause a snapshot to be taken.

In a more complex implementation the snapshot code may be deployed by monitoring the application code at runtime. In such an implementation a monitoring agent may check for the snapshot conditions. When the conditions are satisfied the monitoring agent may cause the application to pause then collect the snapshot data and cause the application to resume execution. Such an implementation may be deployed in conjunction with a monitoring system that may wrap function calls or provide some other performance monitoring.

The snapshots may be edited and modified. The snapshot may include a definition of the event that may trigger a snapshot to be taken as well as a definition of the data to be collected. The triggering event definition may be defined using any type of expression event or other information and may be evaluated at runtime. The data collection definition may define the type of data to collect as well as values from local and global variables metadata external events or other information. In some embodiments the snapshots may include executable code that may be executed as part of the data collection process.

The snapshots may be viewed using a viewing or browsing user interface. In many cases the snapshots may be viewed in a debugging user interface which may also serve as part of a real time debugger. Such embodiments may view the stored snapshots as instances of the real time debugger that are recalled from the point the snapshots were taken. The user interaction with the snapshots may be similar to the user interaction with a real time debugger but may lack the ability to step forward or backwards through the code like a real time debugger.

The snapshot debugging system may be a lightweight data collection system that may gather program state at various events. The data collection may be lightweight in the sense that an application may be paused for a short period of time then continue execution. Such data collection may give a programmer some insight into what occurs around specific events so that the programmer may be better able to improve or modify the application.

A tracing and snapshot debugging may integrate continuous performance measurements and snapshots to better understand a computer application s behavior. The performance measurement system may monitor an application on a periodic basis and may be a platform on which snapshots of the program state may be taken.

The performance measurement system may monitor an application by different mechanisms such as instrumenting the application monitoring an execution environment in which an application runs or other mechanisms. While the monitoring is ongoing a snapshot manager may detect conditions for snapshots and may cause a snapshot to be taken and stored.

The performance measurements may be aggregations of performance metrics such as counters or other summary metrics while the snapshots may contain actual data that may be handled or processed by an application. In such embodiments the snapshots may contain sensitive data and the snapshots may be stored in a separate storage repository than performance metrics which may contain less sensitive information. In some embodiments some or all of the snapshot data may be encrypted.

A debugging user interface may be used for viewing and browsing snapshot instances. When viewing a snapshot instance the debugging user interface may have a similar user experience as when the same interface may be used for real time debugging however the data being displayed may be retrieved from a storage repository for the snapshots as opposed to retrieving data from a live execution environment in the case of real time debugging.

A user may be able to create or modify a snapshot definition for deploying future snapshots. In many cases a snapshot may contain a subset of an application s state at the time a snapshot is taken. When a user identifies a variable or other data object that is not contained in a snapshot the user may be able to add the object to future snapshots. In a typical user interface the user may be able to drag and drop right click or perform some other interaction in the user interface to select the object for inclusion or exclusion from the snapshot.

After a snapshot is defined the snapshot may be deployed to collect data while an application executes.

Throughout this specification and claims the terms profiler tracer and instrumentation are used interchangeably. These terms refer to any mechanism that may collect data when an application is executed. In a classic definition instrumentation may refer to stubs hooks or other data collection mechanisms that may be inserted into executable code and thereby change the executable code whereas profiler or tracer may classically refer to data collection mechanisms that may not change the executable code. The use of any of these terms and their derivatives may implicate or imply the other. For example data collection using a tracer may be performed using non contact data collection in the classic sense of a tracer as well as data collection using the classic definition of instrumentation where the executable code may be changed. Similarly data collected through instrumentation may include data collection using non contact data collection mechanisms.

Further data collected through profiling tracing and instrumentation may include any type of data that may be collected including performance related data such as processing times throughput performance counters and the like. The collected data may include function names parameters passed memory object names and contents messages passed message contents registry settings register contents error flags interrupts or any other parameter or other collectable data regarding an application being traced.

Throughout this specification and claims the term execution environment may be used to refer to any type of supporting software used to execute an application. An example of an execution environment is an operating system. In some illustrations an execution environment may be shown separately from an operating system. This may be to illustrate a virtual machine such as a process virtual machine that provides various support functions for an application. In other embodiments a virtual machine may be a system virtual machine that may include its own internal operating system and may simulate an entire computer system. Throughout this specification and claims the term execution environment includes operating systems and other systems that may or may not have readily identifiable virtual machines or other supporting software.

Throughout this specification and claims the term application is used to refer to any combination of software and hardware products that may perform a desired function. In some cases an application may be a single software program that operates with a hardware platform. Some applications may use multiple software components each of which may be written in a different language or may execute within different hardware or software execution environments. In some cases such applications may be dispersed across multiple devices and may use software and hardware components that may be connected by a network or other communications system.

Throughout this specification like reference numbers signify the same elements throughout the description of the figures.

In the specification and claims references to a processor include multiple processors. In some cases a process that may be performed by a processor may be actually performed by multiple processors on the same device or on different devices. For the purposes of this specification and claims any reference to a processor shall include multiple processors which may be on the same device or different devices unless expressly specified otherwise.

When elements are referred to as being connected or coupled the elements can be directly connected or coupled together or one or more intervening elements may also be present. In contrast when elements are referred to as being directly connected or directly coupled there are no intervening elements present.

The subject matter may be embodied as devices systems methods and or computer program products. Accordingly some or all of the subject matter may be embodied in hardware and or in software including firmware resident software micro code state machines gate arrays etc. Furthermore the subject matter may take the form of a computer program product on a computer usable or computer readable storage medium having computer usable or computer readable program code embodied in the medium for use by or in connection with an instruction execution system. In the context of this document a computer usable or computer readable medium may be any medium that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The computer usable or computer readable medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus device or propagation medium. By way of example and not limitation computer readable media may comprise computer storage media and communication media.

Computer storage media includes volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can accessed by an instruction execution system. Note that the computer usable or computer readable medium could be paper or another suitable medium upon which the program is printed as the program can be electronically captured via for instance optical scanning of the paper or other medium then compiled interpreted of otherwise processed in a suitable manner if necessary and then stored in a computer memory.

When the subject matter is embodied in the general context of computer executable instructions the embodiment may comprise program modules executed by one or more systems computers or other devices. Generally program modules include routines programs objects components data structures etc. that perform particular tasks or implement particular abstract data types. Typically the functionality of the program modules may be combined or distributed as desired in various embodiments.

The snapshot system may collect application state such as call stack information and values for selected variables. The snapshot may capture a glimpse of the application at a specific event or condition and may help a programmer understand an application s behavior.

The snapshot system may collect snapshots that may be viewed and browsed later. Such a system may be used to collect data over time. In one use case a programmer may have a bug or other anomaly that may be difficult to reproduce. The programmer may create one or several snapshots that may be taken under conditions similar to the anomaly. The programmer may launch the snapshots and let the application run so that the snapshots collect program state when the anomaly occurs. The programmer may come back after a period of time and view the snapshot datasets to help understand the application s state at the time of the anomaly.

The user interface for viewing browsing and exploring the snapshots may be similar to a debugging user interface. In a debugging user interface an application s source code may be displayed along with local and global variable values. The programmer may explore a snapshot using the same user interface as the programmer would use to explore a running application in debugging mode.

A snapshot definition may contain an event description and a data definition . The event description may be a condition under which the snapshot may be taken and the data definition may define the data to be collected.

The event description may include any type of expression for defining an event. The expression may use an internal value such as when local variable X 1. The expression may use external information such as a specific time of day or when a hardware interrupt may be raised. In some cases the expression may include complex expressions that may be evaluated at runtime to determine whether or not to take a snapshot.

Throughout this specification and claims the term take a snapshot is used to denote a process of collecting state information in response to an event. The state information may be collected while an application is paused. In some embodiments snapshot data collection code may be inserted into an application which may effectively pause the application while the snapshot data collection code executes and collects various application state. In other embodiments the processing of an application may be paused within and operating system or other execution environment and a separate process may collect the application state during the pause.

The data definition may define the data to collect. Some embodiments may have a default data collection setting that may be varied by including or excluding elements from the default setting. In many cases the data definition may include a call stack which may include application code currently being executed plus each call frame of higher level functions back to an outer loop or main level of an application.

A call stack may be a data structure that stores information about active subroutines of an application. The call stack may be known as an execution stack control stack run time stack machine stack or other nomenclature. In many cases the call stack may define a point to which a subroutine may return when it has finished execution. Some call stacks may store data for local variables at each call frame of the stack as well as parameters that may be passed to and from subroutines.

The data definition may include complex memory objects that may be defined in a hierarchical structure. In some embodiments such memory objects may be collected by unpacking the structure at different levels. For example a default setting may unpack and collect complex memory objects at a first level such that the first level values of the data structure may be captured and saved in the snapshot definition. Some data definition settings may cause such complex memory objects to be collected in their entirety or at various levels within the data structure s hierarchy. In some cases a specific sub object value or set of values may be defined for collection.

The data definition may include various metadata relating to the snapshot. Such metadata may include external information about the computer system on which the application is executing such as the processor type and speed memory and storage capacities and availabilities hardware and software configurations and other information. Such metadata may also include timestamps performance information or other metadata.

The snapshot definitions may be consumed by a snapshot monitoring agent which may cause snapshot data to be collected when the event described in an event description may occur. The snapshot monitoring agent may be deployed in several different forms.

In a simple deployment a programmer may manually insert snapshot code into an application. In such a deployment the snapshot code may be executable code that may collect data and transmit the data to a snapshot repository. The executable code may be include a call to a debugging application programming interface to collect call stack information metadata variable values and other information. The executable code may also include a call to a collection application programming interface which may receive the data perform some processing and packaging of the data and cause the snapshot instance to be stored.

In a more complex deployment snapshot code may be inserted into an application automatically. In some such deployments the snapshot code may be inserted prior to runtime by automatically traversing the application code to identify conditions for which a snapshot may be taken. Such insertion may occur prior to runtime by analyzing source code or intermediate code determining an appropriate location and adding snapshot code that may evaluate the event description and when the event conditions are satisfied cause a snapshot to be taken.

Some embodiments may insert snapshot code into an application at runtime. In one runtime insertion system a monitoring system may wrap various functions for performance monitoring. The monitoring system may be detect that a condition for a snapshot may be present and may cause the snapshot code to be inserted.

In another runtime insertion system a monitoring agent may monitor a running application detect that the event conditions are satisfied and cause the application to pause. Some such systems may deploy the monitoring agent as a separate thread or process than the application which is being monitored. Some such systems may use monitoring mechanisms that may be part of an operating system or execution environment to monitor the application as it executes.

The execution environment may execute an application from which snapshots may be taken. The execution environment may be an operating system process virtual machine system virtual machine or other construct that may manage the execution of the application .

The application may be any type of computer program. The application may be written in any computer language from high level languages with complex frameworks to binary executable code. In some cases the application may be compiled prior to execution while in other cases the application may be interpreted at runtime.

Snapshot instances may be generated at each event. The snapshot instances may include call stack local variables global or shared variables and source code as well as other data and metadata. In systems where the source code may be readily available by a debugging application programming interface such as when the application is interpreted the snapshot monitoring agent may be able to collect source code for each call frame.

A snapshot instance may include pointers to locations in source code in some embodiments. Such pointers may reference source code which may be stored in a source code repository . When the source code may be displayed while viewing a snapshot instance the source code may be retrieved from the source code repository

A debug viewer may display snapshot instances. The debug viewer may be a full fledged debugging system that may be able to execute code in a user interface and have functions for pausing execution examining variables setting breakpoints stepping through executable code and other functions. Such systems may also include editors compilers and other components.

When displaying a snapshot instance the debug viewer may present the snapshot information using the same user interface as the debugging system but may retrieve the underlying data from a stored snapshot rather from an execution environment in which the application may be executing.

The debug viewer may be any type of interface through which a snapshot instance may be viewed. In many cases the user interface may present a subset of the snapshot instance and a user may explore or browse different portions of the user interface to uncover and view various data.

The debug viewer may have capabilities to create and edit snapshot definitions. A user may be able to identify conditions or breakpoints for snapshot collection as well as include or exclude various data elements for collection. The updated or newly created snapshots may be deployed for execution when the application is executed in the future.

The architecture of embodiment includes a device on which the snapshots may be collected as well as several other devices for storing different elements of the snapshot. A last device may view the snapshot instances. In other embodiments some or all of the functions illustrated may be combined into one or more devices.

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be execution environment level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the functions described.

Embodiment illustrates a device that may have a hardware platform and various software components. The device as illustrated represents a conventional computing device although other embodiments may have different configurations architectures or components.

In many embodiments the device may be a server computer. In some embodiments the device may still also be a desktop computer laptop computer netbook computer tablet or slate computer wireless handset cellular telephone game console or any other type of computing device.

The hardware platform may include a processor random access memory and nonvolatile storage . The hardware platform may also include a user interface and network interface .

The random access memory may be storage that contains data objects and executable code that can be quickly accessed by the processors . In many embodiments the random access memory may have a high speed bus connecting the memory to the processors .

The nonvolatile storage may be storage that persists after the device is shut down. The nonvolatile storage may be any type of storage device including hard disk solid state memory devices magnetic tape optical storage or other type of storage. The nonvolatile storage may be read only or read write capable. In some embodiments the nonvolatile storage may be cloud based network storage or other storage that may be accessed over a network connection.

The user interface may be any type of hardware capable of displaying output and receiving input from a user. In many cases the output display may be a graphical display monitor although output devices may include lights and other visual output audio output kinetic actuator output as well as other output devices. Conventional input devices may include keyboards and pointing devices such as a mouse stylus trackball or other pointing device. Other input devices may include various sensors including biometric input devices audio and video input devices and other sensors.

The network interface may be any type of connection to another computer. In many embodiments the network interface may be a wired Ethernet connection. Other embodiments may include wired or wireless connections over various communication protocols.

The software components may include an operating system on which various software components and services may operate. Depending on the embodiment the application may be executed in an operating system or in an execution environment . The operating system and execution environments may have debugging application programming interfaces and respectively.

A set of snapshot definitions may define conditions for taking snapshots. A snapshot and monitoring agent may perform dual roles of monitoring and managing snapshot collection. During execution of the application the snapshot and monitoring agent may detect that a condition for a snapshot has been satisfied then collect various data elements as defined in the snapshot definition .

The snapshots may be taken by calling debugging application programming interfaces or . The debugging application programming interfaces may respond to requests to collect various program state such as the call stack local and global variables and other information. In some cases the executing source code may also be retrieved in this manner.

The snapshots may be encrypted prior to being stored. An encryption module may encrypt some or all of the snapshot prior to transmitting the snapshot over a network to a snapshot storage system .

Some snapshots may contain sensitive or other information that may have an obligation for control and security. For example an application that may process credit card numbers personally identifiable information or other sensitive information may have such information gathered in a snapshot. To prevent such data from being viewed or accessed the snapshot be encrypted at the point of creation. The snapshot may be decrypted by an authorized user when using a debug viewer.

The encryption module may use any type of encryption or obfuscation mechanism to protect the contents of a snapshot instance. In some cases a public private key system may be used while in other cases some type of substitution cypher dictionary or other mechanism may be used to remove or obfuscate any sensitive information.

Some embodiments may selectively apply encryption or obfuscation mechanisms. For example a snapshot instance may encrypt of obfuscate all data values for variables but may leave other data in the snapshot instance in plain text. A snapshot definition may include indicators for selectively encrypting or obfuscating different data elements within the snapshot instance.

The network may connect various devices together. The network may be a local area network wide area network or any other communications network.

A performance storage system may collect and store performance data collected during execution of the application . The performance storage system may include a hardware platform which may be similar to the hardware platform . A performance database may store the various performance information datasets collected by the snapshot and monitoring agent .

A snapshot storage system may collect and store snapshot instance data. The snapshot storage system may have a hardware platform which may be similar to the hardware platform . A snapshot instance database may store the individual snapshot instances.

In some embodiments different security policies may be applied to the performance data and snapshot data collected from an application. In many cases the performance data may be aggregated data that may include function names but may not include underlying data handled by the application. In contrast the snapshot data may include sensitive data that may have a more restrictive security policy applied.

The security policies may be applied by having different storage systems for performance and snapshot data where the snapshot data may be stored and managed with a more restrictive security policy. A restrictive security policy may dictate physical security encryption settings network configuration access restrictions or other configurations in order to limit access and protect data from unauthorized access.

A source code storage system may store and retrieve application source code. The source code storage system may have a hardware platform which may be similar to the hardware platform . Some such systems may include version management systems that may save different versions of source code. When a version management system is available a snapshot may be created with a link or descriptor to the specific version of the application that may be executing. Such systems may retrieve the specified version of the application source code when displaying the snapshot instance in a debugging viewer.

A debugging system may be a system on which a programmer may view the snapshot instances among other functions. The debugging system may operate on a hardware platform which may be similar to the hardware platform .

A debug viewer may be an application that may display snapshot instances. In many cases the debug viewer may be an interactive application that may allow a programmer to interact with the snapshot instances in a similar manner as a debugger. The debug viewer may be a standalone application may be an interactive page rendered in a browser or may have some other architecture.

The debugging system may have a decryption module which may decrypt the data encrypted by the encryption module when the snapshot instance was created.

Embodiment may illustrate one example of a system that may wrap various functions for performance monitoring or tracing. The wrappers may gather and store performance information for each wrapped function and the performance information may be stored for analysis or potentially displayed in real time.

The wrapping function may be one mechanism whereby the conditions for a snapshot may be evaluated with each function call. When the conditions may be present the wrapping system may insert snapshot code into the wrapped function or into the wrapper to cause a snapshot to be taken.

In some cases a determination may be made at wrapping time that some of the conditions for a snapshot may be present but that other conditions may be unknown. In such a case the snapshot code may include code that may evaluate the additional conditions which when met may cause the snapshot to be evaluated. In some cases the snapshot code may be inserted into a function and one or more additional conditions may not be met causing the snapshot to not be taken.

The structure of the executable code representing a snapshot may include a set of conditions and a mechanism for gathering and storing snapshot data. Such an embodiment may be inserted into an application such that the application halts other processing and executes the snapshot code.

The conditions may be expressed as executable code that contains a full set or subset of conditions and the executable code may be evaluated at the point of taking a snapshot. When all of the conditions are met the snapshot executable code that gathers snapshot information may then be executed.

Such a mechanism may be deployed in both dynamic and static languages. Dynamic languages may be a loose classification of programming languages that refer to those computer languages that may have mechanisms for modifying the application after compile time. Such actions may include adding new code extending objects and definitions modifying the type system and other changes. Static languages may be able to perform such operations in some cases but may typically not contain explicit features for doing so. Examples of dynamic programming languages are ActionScript Clojure Common Lisp JavaScript Perl PHP Python R Ruby Smalltalk and others.

A system may receive application code . The application code may contain several functions with a current function identified by an execution pointer . As each function is identified for execution a performance monitor with snapshot manager may process the function.

The incoming function may be wrapped using a wrapper function . The wrapper function may contain monitoring mechanisms that collect performance and operational data which may be used to monitor or display performance or operational characteristics of the application.

When a function may be considered for wrapping a snapshot evaluator may scan through one or more snapshot definitions to determine whether or not a condition for a snapshot may be met by the function or within the function.

When a snapshot has the potential to be executed within a function or as part of a wrapper the snapshot evaluator may insert snapshot code into the function or wrapper. The snapshot code may include additional conditions that may be evaluated during execution.

When no snapshot code is to be inserted a function may be created with a performance monitoring wrapper . The wrapped function may be executed by an execution engine and the wrapper may output performance data for analysis.

When a snapshot may be taken as part of the function a wrapper may be created around the function and snapshot code may be inserted into the function . In some cases the snapshot code may be part of the wrapper and may be executed before or after the function .

The wrapped function may be executed by the execution engine with the wrapper generating performance data and the snapshot code generating snapshot instances .

Embodiment is merely one mechanism for deploying snapshots that may be useful with dynamic languages. Other embodiments may have different logic or may deploy snapshots in different manners using dynamic or static programming languages.

The user interface may allow a programmer to browse source code and the state of an application at the point a snapshot was taken. The programmer may be able to view the call stack the source code at each level of the call stack and values of variables. The programmer may be able to modify existing snapshots or create new snapshots for later execution.

A timeline may present both performance data and snapshot instances. The top portion of the timeline may contain various performance indicators while the bottom portion of the timeline may include snapshot indicators . Each of the snapshot indicators may represent a single snapshot.

The timeline may be an interactive mechanism for viewing performance information that may have been collected over a period of time along with the presence of snapshots that may have been taken during the same time period. When the timeline is an interactive interface a user may be able to select various elements of the timeline to view underlying data. For example a user may click on one of the performance indicators to view performance data collected during the representative time period.

A selected snapshot may cause the user interface to be populated as illustrated. The selected snapshot may represent a specific snapshot that a user wishes to view and the selection may cause the snapshot to be retrieved from storage and displayed in the user interface .

A code window may display the source code of the application at the point of a snapshot. The source code may initially be displayed at the location that the snapshot was taken and the user may be able to traverse up the call stack to view source code at locations where the various functions in the call stack were called.

In some embodiments the source code may be contained in the snapshot definition while in other embodiments a snapshot may contain pointers or other links to the source code. Snapshots that store source code may be useful in systems where the source code may be changing rapidly such as in development environments. In such systems the entire source code of an application may not be available for browsing as the snapshot may only contain source code in the vicinity of the functions in the call stack.

A breakpoint indicator may signify the location in the source code where a snapshot was taken. The code in the code window may be the code in the vicinity of the breakpoint and the user may be able to scroll up or down in the code window to view more.

The variables in the code window may be interactive elements. In the example of embodiment a selected variable may be highlighted. A user may select such a variable by clicking right clicking or perform some other action to indicate and select the variable. While the variable is selected the user may be able to view the current value of the variable as well as use the variable to define a breakpoint add or remove the breakpoint from data collection and other uses.

In some cases the selected variable may be highlighted by the user interface when the value for the selected variable is known.

A call stack view may serve as both a tool to view variable values as well as a code navigation tool. The call stack view may show each function called as a subroutine to a top level function. When the call stack view is interactive a user may be able to select and expand a particular frame in the call stack.

An expansion of a call stack frame may present the local variables for the expanded level of the call stack. In the example of embodiment the frame main is shown in a collapsed view while the frame initialize server is shown in an expanded view . In the expanded view local variables are shown.

The call stack view may be used to navigate the source code. In some embodiments the selection of a specific call stack frame may cause the code window to be updated with the source code in the vicinity of the subroutine call represented by the call stack frame.

Other data may be displayed as part of a snapshot view. The other data may be metadata external data or other information that may be collected along with the snapshot.

A breakpoint definition may define the conditions under which the snapshot was collected. In the example of embodiment the snapshot was taken when the incoming data object was ping the day of the week was not Monday and the value of memory was greater or equal to 900 MB. The breakpoint definition may be an interactive window where a programmer may be able to add remove or modify the conditions for the snapshot.

Similarly the data collection definition may define the data to be collected. In many cases a snapshot system may have a default set of data that may be collected. In such cases the data collection definition may define changes to the default settings by adding or removing values to be collected. In many cases the data collection definition may include metadata or other information that may be outside the normal scope of a snapshot.

If the breakpoint definition or data collection definition are updated the programmer may launch the snapshot for future data collection by using the launch button . By launching the snapshot future execution of the application may be done with the new snapshot definition.

A set of navigation buttons may be used to navigate through the various snapshots. A previous button and next button may be actuated to select the previous and next snapshots respectively. When selected the snapshot may be displayed in the user interface . An identifier may display the date and time of the current snapshot for the user s reference.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment illustrates a general method that shows snapshot deployment and data collection. A user may create snapshot definitions using a user interface then the snapshot definitions may be deployed to a snapshot monitor . The snapshot monitor may cause the snapshots to be deployed and collect snapshot instances by working in conjunction with an execution environment .

The method of embodiment is a general method that may be deployed using several different types of mechanisms. In one mechanism a programmer may manually insert snapshot code in an application. In other mechanisms the snapshot code may be inserted in an application before or during execution. In still other mechanisms a snapshot monitor may be a separate process that may interact with an execution environment but may not change the application code.

In a user interface snapshot conditions may be defined in block and stored in block . The snapshot conditions may include both conditions for executing the snapshot and the data to be collected. The snapshot definition may be transmitted in block to the snapshot monitor which may receive the snapshot definition in block .

The execution environment may receive an application in block and begin execution in block . While the application executes in block the snapshot monitor may monitor the execution in block .

During the monitoring the snapshot monitor may check to determine whether or not the conditions for the snapshot have been met in block . When the conditions have not been met the process may return to block .

When the conditions for a snapshot have been met in block the snapshot monitor may cause the application to pause execution in block which may be transmitted to the execution environment where the execution may be paused in block .

The snapshot monitor may gather data defined in the snapshot definition in block . Part of the data gathering may include transmitting a request to the execution environment which may be received in block . The execution environment may gather the requested data in block and transmit the data to the snapshot monitor in block .

Many execution environments may have a debugging application programming interface or other mechanisms by which various data may be collected. A typical debugging application programming interface may be able to retrieve a call stack as well as local global and other variables.

The data may be received by the snapshot monitor in block . Additional state and metadata may be collected in block while the application may be paused after which the snapshot monitor may cause the application to resume in block . The execution environment may receive the resume request in block and resume execution in block . The process of the execution environment may return to block to continue execution.

The snapshot monitor may optionally encrypt the snapshot data in block before storing the snapshot instance in block . In some embodiments certain portions or subsets of the snapshot data may be encrypted.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Snapshot code may consist of a set of conditions for collecting a snapshot along with code for collecting and storing snapshot data as snapshot instances. When the snapshot code is executed the application in effect stops execution until the snapshot code has completed then the application may resume processing.

The source code may be received in block . Each location within the source code for a snapshot may be identified in block .

Each of the locations may be processed in block . For each location a condition for the snapshot may be defined in block . An expression defining the condition may be created in block . The expression may be executable code in the same language as the application.

In some embodiments the snapshot code may be defined in a high level programming language that may have been used for the application. In other embodiments the snapshot code may be defined using intermediate code machine language or in a different language than the main application.

The snapshot code may be inserted into the application in block . In some embodiments a snapshot may call various application programming interfaces that may gather process and store snapshot instances.

After processing each of the locations and inserting snapshot code in each location in block the updated source code may be stored in block and executed in block .

Embodiment may be implemented in a manual method by a programmer. In such a case the programmer may manually identify the locations for snapshots and insert code for each snapshot.

In other cases the method may be implemented in an automated fashion. Some embodiments may process source code for an application to automatically scan for locations in the source code for snapshots then automatically insert snapshot code. Such automated systems may insert snapshot code in source code which may be subsequently compiled or interpreted. In some cases the automated systems may insert snapshot code in intermediate code form which may be subsequently compiled in a just in time compiler prior to execution or may be interpreted in intermediate form.

The method of embodiment places snapshot code at predefined locations within the application. Such an embodiment may infer that one of the conditions for a snapshot may be execution of the application to the location of the snapshot code.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment may illustrate the data collection performed by for a snapshot instance. In some cases the operations of embodiment may be embodied in executable code that may be inserted in an application.

The call stack may be retrieved in block . The call stack may have multiple frames each of which may define a calling function that calls a subroutine. Many computer languages may have a notion of a call stack although some languages may use different nomenclature and some programming environments may have more or fewer data elements stored in the call frames.

Each frame of the call stack may be processed in block . For each frame local variables for the frame may be retrieved in block . Values of parameters passed to the called function may be retrieved in block .

In some embodiments a snapshot may include source code for the application. When the source code may be included in a snapshot in block the source code in the vicinity of the breakpoint or calling routine may be captured in block . When the source code may not be included in block pointers to locations in the source code may be identified in block .

Some embodiments unpack various memory objects which may be defined in various complex structures an example of which may be hierarchical structure. Such memory objects may be identified in block and processed in block .

For each memory object the first level of data values may be retrieved in block . If another level is to be retrieved in block the additional level may be retrieved in block . When all of the levels have been retrieved that were requested in block the process may return to block to process another memory object.

In some snapshot definitions a user may be able to select the amount of data to collect. Part of such a definition may include defining a portion or all of a complex data object to collect. Some data objects may be very large and cause a large amount of data to be collected in a snapshot. When all of such data may not be useful a subset may be collected.

Metadata may be collected in block . The metadata may be various data that may not be retrievable from the call stack and various memory objects. For example metadata may include timestamps external events hardware interrupt states hardware and software configurations performance metrics or other information.

The snapshot data may be formatted in block and encryption may be applied in block . The snapshot may be transmitted to storage in block and the snapshot code may end in block .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment may illustrate a mechanism that may integrate performance monitoring and snapshot gathering in a single system. The performance monitoring may operate by wrapping all or selected functions with a performance monitoring function that may gather operational data about an application. As each function may be evaluated for monitoring an additional analysis may determine whether or not the conditions for a snapshot may be met by the function. If so the system may add snapshot code to the function or the wrapper to collect snapshot data.

An application may begin execution in block . The application may have multiple functions that may be executed as part of the application. The functions may be subroutines or other blocks of executable code.

A function may be received in block . An analysis may begin in block to evaluate each of the snapshot definitions to the current state of the application. For each snapshot definition an analysis may determine if a snapshot condition may apply to the function in block . If not the snapshot is skipped and the process may return to block . If so a snapshot condition expression may be created in block and snapshot code may be inserted into the function or wrapper in block .

The analysis of block may attempt to identify whether or not any snapshot definition may apply to the function about to be executed. The analysis may be an initial determination that a snapshot may be performed in a function then additional conditions may be added to the snapshot code so that the snapshot may be executed only when the full set of conditions may be satisfied.

A performance monitoring wrapper may be created in block and the function to be executed may be wrapped in the performance monitoring wrapper in block .

In some cases the snapshot code may be inserted into the executable code of the function. In other cases the snapshot code may be inserted into the wrapper. When the snapshot code is part of the wrapper the snapshot code may be configured to execute prior to executing the function or after the function has completed.

The wrapped function may be executed in block and performance data may be collected in block . Snapshot instances may be collected in block .

When another function is to be executed in block the process may return to block . When all the functions have been executed in block the application may end in block .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment shows a simplified method for snapshot instance collection and viewing. In one use case for the method a programmer may create one or more snapshot definitions which may be run against an application. While the application executes snapshots may be collected. At a later time the programmer may use a debug viewer to browse each snapshot instance to determine what may have been happening with the application at the time of each snapshot instance.

In block snapshot definitions may be identified. As an application executes in block and a snapshot condition is met in block the program state or a subset of program state may be collected in block . The snapshot instance may be stored in block . If execution is ongoing in block the process may return to block . When execution ends in block the application may end in block .

The steps from through may reflect the data gathering phase where snapshot instances may be collected during application execution. The following steps may reflect the activities that may be performed to view and browse the information contained in the snapshot instance.

A debugging interface may be launched in block . One example of such an interface may be found in embodiment although other configurations may also be used.

A snapshot instance may be selected in block . The snapshot data may be viewed and browsed in block . In embodiments where performance data are also available performance data may be viewed and browsed in block .

The debug interface may include a code viewer and code editor. When an editor is present the programmer may update or modify the source code using the editor in block .

If another snapshot is selected to be viewed in block the process may loop back to block . When the user has completed viewing snapshots in block and the user made changes to the application the application may be compiled in block and the process may loop back to block .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment is a simplified example of a process that may be performed by a debug interface. The process of embodiment is quite linear however many of the interactive features of a debug interface may happen in different sequences or may occur in parallel with other operations.

A snapshot instance may be retrieved in block . From the snapshot instance links or pointers to the source code may be identified in block . The source code may be retrieved from a source code repository in block .

A view of the snapshot may be selected in block . In many cases the code associated with the deepest level of the call stack may be selected as the first view. The source code associated with the view may be displayed in block . Local variables may be displayed in block and global variables may be displayed in block . The call stack may be displayed in block . At this point a user may be able to browse through the data.

The user may identify a variable to add to the snapshot definition in block and may modify the condition under which the snapshot may be taken in block . The changes in blocks and may update the snapshot definition. The updated snapshot definition may be deployed to cause future snapshot instances to be collected.

If another view of the snapshot were desired in block the process may return to block . Another view of the snapshot may be requested when a user selects another frame on a call stack for example.

After the views may be analyzed in block the updated snapshot definition may be stored in block . When additional snapshots may be viewed in block the process may return to block otherwise the process may end in block .

The foregoing description of the subject matter has been presented for purposes of illustration and description. It is not intended to be exhaustive or to limit the subject matter to the precise form disclosed and other modifications and variations may be possible in light of the above teachings. The embodiment was chosen and described in order to best explain the principles of the invention and its practical application to thereby enable others skilled in the art to best utilize the invention in various embodiments and various modifications as are suited to the particular use contemplated. It is intended that the appended claims be construed to include other alternative embodiments except insofar as limited by the prior art.

