---

title: Debug in a multicore architecture
abstract: A method of monitoring thread execution within a multicore processor architecture which comprises a plurality of interconnected processor elements for processing the threads, the method comprising receiving a plurality of thread parameter indicators of one or more parameters relating to the function and/or identity and/or execution location of a thread or threads, comparing at least one of the thread parameter indicators with a first plurality of predefined criteria each representative of an indicator of interest, and generating an output consequential upon thread parameter indicators which have been identified to be of interest as a result of the said comparison.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09129050&OS=09129050&RS=09129050
owner: Fujitsu Semiconductor Limited
number: 09129050
owner_city: Kanagawa
owner_country: JP
publication_date: 20130812
---
This application is a continuation of co pending U.S. application Ser. No. 10 941 457 filed Sep. 14 2004 which is incorporated by reference in its entirety.

In recent years there has been a trend towards producing processors containing multiple cores in order to maximise silicon efficiency i.e. application available MIPs mmor MIPs mW . Such multicore architectures are ideally suited to running applications based on threads because a thread defines an autonomous package of work containing an execution state instruction stream and dataset which by definition may execute concurrently with other threads. However this concurrency of execution introduces additional problems into the software debug process used on these multicore architectures. Software debug is the general term for locating and correcting errors in the execution of a computer application.

One of the key problems faced in software debug is the Heisenberg bug also known as the probe effect . Any code which is added for the purpose of debug for example to increase the level of system diagnostics is likely to subtly change the timing of concurrent and or parallel executing threads. This brings with it the risk of masking bugs that would otherwise be observed in the production release of the same application. It is also difficult to extract meaningful performance measurements and instrumentation when extensive debug code is present in the build. This is because second order effects like cache and bus performance may be affected by the additional code as well as it having the more obvious impact on code size.

Additionally there is an increasing demand for improving the reusability of the software produced for such multicore architectures due to the extensive resources used in its production. In the past applications for multicore architectures have been written on a bespoke basis thus producing hardware specific applications with little portability. In extension the debug of these applications has also been very specialised.

According to a first aspect of the present invention there is provided a method of monitoring thread execution within a multicore processor architecture which comprises a plurality of interconnected processor elements for processing the threads the method comprising receiving a plurality of thread parameter indicators indicative of one or more parameters relating to the function and or identity of a thread or threads comparing at least some of the thread parameter indicators with a first plurality of predefined criteria each representative of an indicator of interest and generating an output consequential upon thread parameter indicators which have been identified to be of interest as a result of the said comparison.

This provides the ability to debug and trace an application running on a multicore processor architecture at the thread level without the requirement of adding code specifically for the purpose of thread level debug. Additionally this also provides the advantage of enabling the debug of a multicore architecture application without the introduction of additional code and therefore probe effect.

According to a further aspect of the invention there is provided a thread level software debug controller for a multicore processor architecture having a plurality of interconnected processor elements each element providing resources for processing threads the debug controller being in communication with each of the said processor elements and comprising monitor logic for monitoring the allocation and execution of threads within the multicore processor architecture.

The system frame work also comprises a centralised thread management and allocation system which includes a thread management and allocation controller and a dedicated tightly coupled memory connected to the thread management and allocation controller controller hereinafter via memory interface . Each processing resource is able to access the controller via an interconnect . It is to be understood that no particular interconnection strategy that is the arrangement by which the controller communicates with each processing resource and vice versa and the arrangement by which each processing resource communicates with the system resources for example memory is required in the implementation of the arrangement of in particular point to point links a central system bus or even a pipelined architecture may equally be employed save only that each of the processing resources should be able to communicate directly or indirectly i.e. via other processing resources or otherwise with the controller .

As seen in each of the multiple processing resources has an associated controller client configured to receive control information from the central controller and to administer the processing resources in accordance with the control information received. The function and purpose of the controller clients is described in more detail below. Each processing resource also has an associated interconnect agent for communication with the controller via the system interconnect . The interconnect agent provides a generic interface to the controller client which is independent of the underlying interconnect protocol in use on the system interconnect i.e. it provides protocol translation between the communication protocols in use on the system interconnect and the communication protocol in use by the controller client . Due to the use of an interconnect agent the controller clients of embodiments of the present invention may be used with any system interconnect protocol currently available. Indeed the interface protocol through which the controller client communicates with the controller may be physically distinct and of dissimilar nature to any or all of the interface protocols deployed to enable communication between the processing resources and shared system resources for example system memory.

The multicore processor as a whole is configured to execute a target application which may be broken down into a number of individual tasks called threads. Each processing resource is allocated a suitable thread by the controller . This allocation is carried out according to a number of parameters including but not limited to the priority of the thread in question the availability of each processing resource and the suitability of a particular processing resource to the execution of a particular thread.

It is however to be understood that the addition of the controller and its dedicated memory do not otherwise require a redesign of the layout of the processor .

One specific arrangement is shown in which shows a typical System on Chip SoC architecture in block diagram form and which illustrates the various processing resources that might be placed under the control of the controller in a practical application. It will be noted that the processing resources may in particular be of relatively general capability such as a DSP or may of relatively limited functionality such as a peripheral IO.

The system control group comprises the miscellaneous signals required to ensure the correct operation of the controller . These include a system clock a real time clock and a reset signal RST . All output signals from the controller are synchronous to the system clock although they may be re synchronised into other clock domains as is required by the system. All input signals to the controller are synchronised to the system clock prior to processing. The RST input is a synchronous reset signal for resetting the controller .

The external interrupt group consists of a group of external interrupts sourced from outside the thread management and allocation system. Signals in the external interrupt group may be driven from for example input interfaces with the outside world or directly from outside the multicore processor via pins. The number of external interrupt inputs may be defined during the multicore processor design phase.

The internal control group consists of a synchronous interrupt for each controller client and its associated processing resource . Therefore the number of signals will typically correspond with the number of processing resources within the system and will be defined during the multicore processor design phase. The internal interrupt signal is an internal thread ready interrupt signal indicative of a thread ready for execution and that is being assigned to the particular processing resource associated with that controller client .

1. The auxiliary debug interface which enables an external debug agent to gain debug access to the controller and the system as a whole. Through this interface breakpoints and watchpoints may be set both internally and externally and system state information may be read.

2. The trace buffer output which is a streaming output providing run time system state according to a set of pre configured filtering guidelines and under the ultimate control of the debug manager .

3. External debug enable signals which may be used as breakpoint signals in their own right or may be combined with processing resource specific enables.

The particular format construction and use of the above debug interface group will be described in more detail below.

The tightly coupled memory interface group interfaces the controller to its own dedicated tightly coupled memory resource .

The attached memory is assumed to be a synchronous SRAM device. The dedicated tightly coupled memory contains an integer number of controller memory elements as defined during the multicore processor design phase according to the needs of the target application. In the currently preferred embodiment each controller memory element consumes 256 bits of memory space. Again in the currently preferred embodiment the controller supports a maximum of 65536 controller memory elements i.e. a 16 Mb memory . Although queue descriptors as described later do consume controller memory elements in a typical system the number of controller memory elements required would be dominated by thread support requirements. For example a system capable of supporting threads simultaneously within the controller would require approximately 128 kb of attached memory.

The interconnect interface group of conforms to the chosen interconnect protocol or protocols used in the multicore processor and the interconnect agent which is defined during the multicore processor design phase. In the case where there are multiple distinct interconnect structures the interconnect interface group may consist of multiple possibly dissimilar interfaces. In the embodiment shown a bus interface is used. It will nevertheless be apparent that various other forms of interface could equally be employed as suggested previously.

1. A Thread Input Manager TSIM configured to maintain a list of free controller memory elements within the dedicated tightly coupled memory and to oversee controller memory element recovery.

2. A Thread Synchronisation Manager TSPM configured to maintain Pending lists and a timer queue within the dedicated tightly coupled memory and to perform synchronisation between threads and to perform promotion of threads to Ready queue structures within the dedicated tightly coupled memory as required. The Thread Synchronisation manager maintains the integrity of the pending and timer queue structures via insertion and extraction of pending thread descriptors within the dedicated tightly coupled memory .

3. A Thread Output Manager TSOM configured to maintain Ready queue structures within the dedicated tightly coupled memory and Dispatch queues for each processing resource within the dedicated tightly coupled memory . Maintenance of the integrity of the ready queue structures is performed by insertion and extraction of thread descriptors held in controller memory elements within the dedicated tightly coupled memory .

4. A Thread Schedule Manager TSSM configured to provide scheduling decisions for each processing resource within the ready queue structures located within the dedicated tightly coupled memory .

5. A Thread Memory Manager TSMM configured to provide aggregate access to the attached dedicated tightly coupled memory including mutual exclusivity and locking.

6. An Interrupt Manager TSIC configured to convert incoming external system interrupts into internal synchronisation primitives.

7. A Time Manager TSTC configured to provide timer functions for synchronisation purposes and watchdog timer functionality to each processing resource .

8. A System Interface TSIF providing interfacing between software commands received from the multicore processing resources and the individual sub blocks within the controller .

9. A Server Shim TSSS configured to provide physical interfacing between the controller and the multicore processing resources .

Each of the primary and secondary subblocks listed above also include a debug output forming part of a debug interface for informing a debug controller of the present invention of events occurring within each subblock corresponding to that signal. Where a command may complete with particular conditions status flags are administered within the subblock.

In general terms the controller manages threads by maintaining a number of queue structures within the dedicated controller memory . These queue structures include Pending. Ready Timer and Dispatch queues. Threads awaiting execution are held in one or more of these queues and are allocated to suitable processing resources once they become ready. Manipulation of the threads within the queues is mainly carried out using push pop and sort operations. Full details of the operation of the controller are described in co pending U.S. application Ser. No. 10 308 895 and is incorporated by reference herein in its entirety.

There now follows a detailed description of the interaction of the above primary and secondary processing subblocks within the controller .

Each sub block presents a set of functions to other sub blocks enabling each to instruct its peers to execute manipulations on their respective maintained structures within the dedicated tightly coupled memory . Functions are called by a particular subblock on receipt of a similar command received at a controller software Application Programming Interface API .

The FreeListStatus function returns the head pointer and number of elements within the controller memory element free list. The free list is a list of the controller memory elements that are currently unused. This function can only be called by the system interface on receipt of a similar command at the controller software API

The PushFreeIndex function is used to push a liberated controller memory element index back onto the free list. This function can only be called by the thread Schedule Manager .

The PopFreeIndex function is used to pop a free controller memory element index from the free list. It is typically called from within the API call service routine within the system interface .

The Thread Synchronisation Manager provides seven public functions to the other sub blocks within the controller .

The first five of the following 7 functions can only be called by the system interface in response to similar commands received by the controller software API.

The TimingQueueGetStatus function returns the head pointer and a number of elements within the timer queue.

The TimingQueueSetStatus function sets the head pointer and number of elements within the timer queue.

The PendingQueueGetStatus function returns the head pointer and number of elements within the pending descriptor queue.

The SyncPrim function is used to issue a synchronization primitive to a given pending queue. This function is called by either the thread interrupt manager or the system interface .

The TimeoutPrim function is used to issue a timer based synchronisation primitive to the timer queue. This function is only called by the time manager .

The Thread Output Manager provides six public functions to the other sub blocks within the controller .

The PushIndex function places a thread descriptor within the ready queue structure. The method may be called by either the system interface or the Thread synchronisation manager and it may be called with high priority to expedite processing speed for example to handle interrupts . Where threads are independent immediately ready the call will be made from the system interface where the thread descriptor originally had dependencies the call is made from the thread synchronisation manager .

The following three functions can only be called by the system interface in response to the receipt of a similar command at the controller software API

The DispatchQueueGetStatus function returns the head pointer and number of elements within the dispatch queue list.

The DispatchQueueSetStatus function sets the head pointer and number of elements within the dispatch queue list.

The DispatchQueueSetMetrics function sets the metrics of the currently executing thread such that informed pre emption decisions can be made.

The DispatchQueueEvent function propagates a scheduling event from the ready queue structure to the dispatch queues administered by the Thread Output Manager TSOM . This function is only called by the Thread Schedule Manager TSSM .

The Thread Schedule Manager provides two public functions one to the Thread Output Manager and one to the system interface both of which are located within the controller .

The Schedule function is called by the thread output manager immediately after it adds a thread descriptor to a ready queue structure or removes a thread descriptor from a dispatch queue structure.

The FreeIndex function is called by the system interface to liberate controller memory elements after they are popped from the dispatch queue. The requests are filtered through the Thread Schedule Manager command interface to ensure that all related scheduling will be guaranteed complete prior to the release of the controller memory element .

As described earlier the term processing resource is applied to any resource that may execute an instruction regardless of how rudimentary the instruction may be. Therefore resources that have a fixed function such as an input output module are also included. Depending on the type of processing resource the connection between the system interconnect and the processing resource via the controller client may be either uni directional or bi directional.

On appropriate processing resources for example general purpose processors or Digital Signal Processors the controller client will typically be implemented in software. However where the processing resource is of limited function the controller client will require a hardware component.

When a hardware component is used the controller client still interfaces to the processing resource using the same interface. That is to say the controller client presents an identical interface to the interconnect agent as that of the processing resource to the controller client . In some cases it is appropriate to treat the data path into the processing resource as distinct from the data path out of the processing resource for example in the case of an Input Output device.

In addition to the main interface the controller client also provides out of band interfaces for use as outputs for run time and debug events. Where a software controller client is used these are provided using standard interrupts calling appropriate service routines or form inputs to processing resource specific debug and trace units .

Each controller client is fully interrupt driven. Upon receipt of an internal interrupt from the controller the controller client pops the thread descriptor from the head of the dispatch queue associated with that particular processing resource which is held in the dedicated tightly coupled memory . The unique reference within the thread descriptor is then used to read further thread control information the Thread Control Block TCB from the main memory resource . The information contained within the TCB may be any of 

1. Controller client configuration content. This information may be used to configure controller client system resource usage policing address or data bus trigger configuration for debug purposes data presentation mode and the like.

2. Processing Resource Configuration content. This is information required to prepare the processing resource for execution of a particular thread. This may include recovery from a previous partial execution of this thread or configuration of a specialist hardware accelerator such as an audio CODEC.

3. Instruction content. In the case of a fixed function hardware accelerator the instruction will be implicit in the targeted hardware processing resource for example an output instruction when the processing resource is an output module and any required specialisation or configuration will be accommodated within the configuration information. In the context of a software controller client this will typically be a pointer to the function code associated with the thread.

4. Data content. This content may define the start address or multiple addresses in the system memory and range of data over which the thread may operate.

5. Controller client post processing content. This content determines the actions of the controller client after the completion of the thread execution.

1. Configuration phase where the processing resource and the controller client are prepared for execution of a particular thread. In the simplest case the configuration phase will be null.

2. Execution phase where the thread is being executed and the controller client may be supplying data or monitoring resource utilization.

3. Completion phase. Completion of processing may result in no action the creation of another thread the issuance of a synchronisation primitive or a combination of thread creation and synchronisation. Furthermore the controller client may also be required to set or update scheduler metrics and terminate threads. In the event that during execution of the thread further memory is required to store results the controller client must also execute this server method.

As mentioned previously the controller client may be implemented in software. In this case some of the functionality of the controller client for example shared resource usage policing will typically make use of existing hardware components which may already be present in the processing resource hardware for example a memory management unit MMU .

Consequently the software controller client architecture and implementation is partially processing resource specific.

Hardware controller clients may also have specialist requirements according to the idiosyncrasies of the associated processing resource . The following section describes a generic architecture which will be suitable in the majority of cases.

The basic structure of the hardware controller client is shown in . At the functional heart of the design is the controller client Finite State Machine FSM . This Finite State Machine FSM may be active during all three phases. The controller client FSM is activated by an interrupt from the controller .

Firstly the controller client FSM masters the system interconnect to read the TCB from the shared memory resource which contains a reference to its own instructions. During the configuration phase the controller client may master the processing resource interface interpreting configuration commands and translating them into write cycles issued to the processing resource . Furthermore the controller client configures its own resource policing. The manner in which the transition from the configuration state to the executing state is processing resource specific but may be marked by an explicit execute primitive or merely an entry into a data transferral state.

From a controller client perspective the simplest architecture has an identical interface protocol on both the processing resource and the system side. In this case during the execution phase processing resource read and write cycles are simply mapped across to the system interface with checking where appropriate.

The simplest controller client implementation would require a FIFO style interface in both the system to processing resource and processing resource to system paths. During the execution phase of a controller client of this nature data can be presented to a processing resource by message or streaming modes. Message mode where the entire dataset is accumulated locally within the controller client prior to processing engenders a more coarse grained blocky interconnect behaviour which may facilitate more complex interconnect arbiters. Streaming mode where data is streamed directly from the system memory into the processing resource presents a more silicon efficient solution requiring more careful consideration of hand shaking and exhibiting fine grained interconnect transactions and tight coupling to interconnect performance.

The transition from the execution to the completion phase may be inferred by measuring the presentation of data to the processing resource or explicitly signalled by the processing resource itself. During the completion phase the controller client once again executes from the set of instructions provided by the original thread control block.

Note that in some cases it is appropriate to treat the datapath into the processing resource for example an input output device and the path out of the processing resource as distinct. In contrast it will be natural in some cases for example algorithmic accelerators such as DSPs to couple the consumer and the producer of data within the same controller client framework.

In order to provide a level of decoupling between the processing resource and the other system resources a number of additional facilities may also be provided by the controller client 

a Addresses generated by the processing resource may be checked against expected behaviour as defined by a base address and offset definition by using a comparator and a comparison address register .

b Addresses generated by the processing resource may be offset using a subtractor and offset address register enabling the processing resource to have a normalised view of the address map for any given thread typically normalised around address 0x0.

c A debug watch register may be included where the processing resource is of limited functionality and therefore does not include its own instruction level debug hardware. Such a register can then be used to monitor address usage for enabling instruction level debug capabilities to the otherwise lacking fixed function hardware resources .

Instances of datatypes used within the controller are divided into public visible from and manipulated by the system at large and private visibility visible only within the controller and manipulated only by the controller sub blocks . To ensure portability of the design across multiple end applications all thread queue and aggregated queue descriptors are stored within the dedicated tightly coupled memory using a common base class the controller memory element .

1. Free List Element. This element is free for usage by any of the other descriptor types. No user initialization or runtime manipulation is required.

2. Thread descriptor TD . This is a data structure representative of an application administration thread. This descriptor may exist in either a pending queue a Ready queue or a dispatch queue within the dedicated tightly coupled memory . No user initialization is required but runtime manipulation is required.

3. Scheduler Root Descriptor SRD . This is the top descriptor of a scheduler hierarchy. User initialization is required but no runtime manipulation is required. The root descriptor has no parent but children can be any of an SSTD a DSTD or a TD.

4. Static Scheduler Tier Descriptor SSTD . This is a static scheduler tier descriptor whose parent may be either an SRD or another SSTD. The SSTD s children can be any of another SSTD a DSTD or a TD.

5. Dynamic Scheduler Tier Descriptor DSTD . This is a dynamic scheduler tier descriptor. User initialization is not required but runtime manipulation is required. The parent of a DSTD may be either an SRD or an SSTD but a DSTD may only have TD children.

6. Dispatch Queue Descriptor. This type of descriptor describes a list of thread descriptors which are waiting for pop operations from the associated processing resource . User initialization is required including depth watermarks but no runtime manipulation is required.

7. Pending Queue Descriptor. This type of descriptor describes a list of thread descriptors which are awaiting a synchronisation event. User initialization is required but no runtime manipulation is required.

8. Pool Attachment Node PAN . PANs are used to attach the scheduler root tier to the processing resource pool root tier. User initialization is required but no runtime manipulation is required.

9. Pool Static Node PSN . PSNs are also used to attach the scheduler root tier to the processing resource pool root tier. User initialization is required but no runtime manipulation is required.

10. Pool Root Node PRN . There is a single PRN for each processing resource pool. User initialization is required but no runtime manipulation is required.

However according to the application and or target processing resource the complexity of the controller client control block may vary. In particular note that further levels of indirection may be included which given appropriate control instruction code and corresponding datapath code may enable disparate processing resources to execute the same functions on the same data under certain circumstances. In this case there are pointers for each type of processing resource corresponding to the particular instruction stream required by the dissimilar processing resource . The ability to allow dissimilar processing resources to execute the same threads also enables load balancing to be carried out across all processing resources available within the multicore architecture. Furthermore processing resources may be pooled together.

Processor resource pools enable the aggregation of instances of a specific processing resource into a single distribution node. The distribution nodes may then provide load balancing intelligent pre emption and power management across the individual processing resources that belong to a particular processing resource pool.

Typically each processing resource provides an instruction level debug and trace unit for use at the instruction level or equivalent and only local to the associated processing resource . These are processing resource specific however operate using the same or similar data.

Broadly speaking the approaches to debug can be split into two areas. Static operations where the system is halted during the extraction of debug information and dynamic operations where information is gathered monitored and distributed at run time.

Static operations include amongst other things setup configuration of breakpoints and watchpoints the management of halt and single step snapshots of system state and memory load observation and analysis.

Dynamic operations include amongst other things the monitoring of processor cycles cache operations inter processor communication and system interconnect e.g. bus transactions. This type of monitoring is collectively referred to as trace and it is used in the profiling of system behaviour. Dynamic debug or trace information is typically generated autonomously by the components of the embedded system.

The local instruction level debug and trace units contain embedded trigger logic that causes the processing of instructions within the associated processing resource to halt under certain pre defined circumstances but may also be used to initiate or terminate the accumulation of trace information or some other function. The trigger is typically an event bit which indicates that the predefined trigger sequence has been observed.

As a minimum such trigger logic typically includes breakpoint logic which issues an interrupt trigger to the local processing resource when a given instruction is encountered. The amount of functionality that is contained within these units is processing resource specific however where required as mentioned previously the controller client can include debug watch registers to provide a minimum level of instruction level debug and trace capability. This would be required when the processing resource was of limited function for example a dedicated Audio CODEC.

Each of the instruction level debug and trace units have a bi directional interface connected to a Debug Access Port and a trace output interface connected to a trace port via one or more optional local trace buffers a trace aggregation point and an optional unified trace buffer .

The Debug Access Port allows an external debug host to control and to access the debug process. Typically these hosts interface through a serial port or other similar low speed connection interface protocol.

The trace port provides access to the trace data to outside devices. This allows observation of the trace data to occur as part of the software debug process.

The optional local trace buffers and unified trace buffers are used to temporarily store trace data before output. This allows a running snap shot of the system to be stored and then read out through the trace port at some later point. By doing this the trace port does not have to be capable of the potentially high transfer speeds required should the debug data be outputted in real time. This removes the requirement for a large number of output pins that are at least in part dedicated to debug data output. This is important since at present it is the number of input output pads that can be fitted onto any particular Integrated Circuit IC die that restricts size of the IC die as opposed to the size of the functional logic itself.

The trace aggregation point simply serves to multiplex the multiple debug trace streams outputted from the local debug and trace units into a single output stream ready for either storage in the unified trace buffer or simply for output across the trace port interface in the case of no unified trace buffer being present.

Connected to each of the local debug and trace units is the thread debug controller of the present invention. This thread debug controller is also connected to the controller debug access port and the trace output port again via one or more optional local and unified trace buffers.

Each of the controller subblocks to has a debug interface for carrying signals into the thread debug controller . These input signals notify the thread debug controller of events happening in each of the corresponding subblocks of the controller as the subblocks interact to manage and allocate individual threads between the individual processing resources . The thread debug controller can also filter subblock events for trace and trigger information.

Command execution within each subblock of the controller results in the sending of an EventID field and an EventData field to the thread debug controller . The subblock to which each event relates is determined by which interface these fields are sent over as each subblock has its own dedicated interface to the thread debug controller . The EventID field is user definable therefore can be N bits long however in a preferred embodiment of the invention the EventID is four bits long. Each individual EventID field identifies an individual event occurring in a particular subblock to .

Examples of events that might occur within the subblocks include pushing popping of threads to or from queues read write access to a Controller Memory Element generation of synchronisation events and events that provide a form of low level communication between processing resources and the controller .

The EventData field that accompanies each EventID is in the currently preferred embodiment 32 bits long. This field contains the main data used by the event currently being executed. Usually this contains the 32 bit long pReference field of the Controller Memory Element however it may also include any one of a number of other data types or combinations of these datatypes when each datatype is less than 32 bits long. Examples of these other datatypes include Controller Memory Element indices interrupt masks timer values and sub module IDs.

The thread debug controller also has a Time interface . This interface provides a 32 bit time indication which is used by the thread debug controller to time stamp all events logged as the thread debug controller receives them from each of the individual subblocks of the controller via the subblock input interfaces .

The Auxiliary debug interface is a bi directional interface for enabling standard external software debug and system visualisation and control tools to access the thread debug controller . These external software debug tools are used to both set up the debug parameters on initialization of the system and to capture and display the resultant trace data. Examples of the interfaces supported include the IEEE 1149.1 JTAG interface and the more capable IEEE Nexus 5001 AUX port Interface.

Originally intended for boundary scan of chip devices JTAG is a technology based on a 4 wire interface comprising serial links and low speed clocking strategies that is now used extensively within multicore architectures for enabling debug data access. Due to its bandwidth limitations and the fact that the interface is mastered by the debug host over a slow serial link the use of JTAG is typically limited to static operations. However since it is relatively cheap in terms of silicon area and chip I O and easy to implement JTAG has become the standard physical layer for on chip debug purposes.

The Nexus 5001 AUX port Interface provides a richer set of debug capabilities including extensive dynamic activities such as dynamic access to debug registers internal to the thread debug controller .

The trace buffer interface is designed to be used with any currently available buffer technology. In the specific embodiment the trace data is outputted through a simple byte wide First In First Out interface. shows the byte wide interface and its associated control signals while shows the timing of the electrical signals forming these data and control inputs outputs. Whilst a single byte wide interface is shown it would be understood to the skilled person that the invention is not so limited in scope.

Referring back to the external debug enable signal group are all local debug and trace unit enable signals. There is one provided for each local debug and trace unit present within the multicore architecture therefore the exact number is set during design phase. Each of these signals may enable a particular local debug and trace unit upon detection of a trigger event. By using such local debug and trace unit enable signals and due to the inherent thread level abstraction of operation of the controller the thread debug controller provides a thread i.e. macro architectural level debug capability that can be gated with the local instruction micro architectural level of the local debug and trace units . This provides both a coarse grained thread based debug and a finer grained instruction based debug to software engineers thereby facilitating the debug process without introducing additional debug software that would otherwise cause probe effects.

It is to be noted that the thread debug controller also provides a number of fine grained debug capabilities to the subblocks that make up the task allocation controller . These will be described in more detail in relation to below.

The Internal debug enable signal group consists of signals that are sent by the thread debug controller to each of the individual subblocks that make up the task allocation controller . These are used to allow the thread debug controller to make each subblock single step through its next instructions or to halt the subblock entirely according to the configuration of the thread debug controller .

The thread debug controller interrupts signal group consists of 2 signals. They allow the feedback of interrupts from the thread debug controller back to the controller . These interrupts are handled in the same way as all other external interrupts to the controller . The use of these signals is entirely programmable but typical examples of their use would include the collection of statistics on events requiring attention in the application and the activation of a debug monitor thread in a particular processing resource .

The TSIF system interface allows communication between the interface manager sub module of the controller and the thread debug controller . This interface comprises both an SubBlockCmd slave input interface and a GenericReg master output interface . All processing resources situated within the multicore processor and the TSIF subblock may access the thread debug controller through the SubBlockCmd slave input interface for normal and debug operations for example to program the debug parameters during run application time. Equally the thread debug controller may be granted full access to all internal subblocks of the controller via the GenericReg master output interface .

The thread debug controller also provides a number of system wide closed loop debug capabilities. Firstly the Interrupt manager TSIC has additional thread debug controller feedback interrupts . These interrupts are used by the thread debug controller to indicate that a particular set of user definable events that are being watched for have occurred. This interrupt can then be used to make the interrupt manager TSIC generate SyncEvents to liberate system management threads which are awaiting that particular SyncEvent. In this way the debug system can trigger system management threads on detection of particular system events.

Secondly dedicated TSIF system interface commands can generate TSIF DebugEvents capable of holding 32 bits of data. These can then be utilized as a low bit rate communication channel between a host debugger and each of the processing resources .

The dynamic debug interface is used to control the specifics of the dynamic operation of the thread debug controller for example what system management and allocation events are to be looked for by the thread debug controller and what actions are to be carried out by the thread debug controller when a particular event is observed.

The static debug interface is used to control the specifics of the static operation of the thread debug controller for example the static event filters.

The SubBlockCmd interface allows the interface manager of the controller to access the dynamic debug interface . A specially designed multiplexer only allows access to the dynamic debug interface from the SubBlockCmd interface . The Nexus protocol converter converts signals from an external debug host using the IEEE Nexus 5001 protocol standard into internal signals suitable for controlling the debug operation of the thread debug controller . In so doing the converter also provides a subset of the Nexus recommended registers. The external debug host is allowed to access both the dynamic debug interface and the static debug interface via the multiplexer . The external debug host is also allowed to access all the internal subblocks of the controller via the interface manager generic interface.

Debug Machines provide a flexible and user configurable method of setting up multiple break or watch points and complex trigger scenarios for any individual pool or arbitrary group of the processing resources . The debug machine s can also enable disable internal trace recording modules and static event filters as a result of observing the occurrence of a trigger scenario.

Each debug machine comprises an EventWatchInst First In First Out FIFO register for storing events to be watched for by that debug machine and an ActionListInst FIFO register for storing the action to be carried out upon detection of a particular event from the EventWatchInst FIFO . These registers are programmed with their respective instructions through the dynamic debug interface . Each debug machine also comprises an event service module which takes the outputs from both the EventWatchInst and ActionListInst registers and compares them with the system management and allocation events inputted from the individual subblocks of the controller . The event service module then outputs one or more of the following a DebugEnable signal for use in enabling the local debug and trace unit of the corresponding processing resource a TraceEnable Disable to enable or disable the static event filter outputting the trace information to the trace buffer a SyncEnable signal for controlling the other debug machines concatenated together with the current debug machine . The debug machines also have an input from the dynamic debug interface for debug programming purposes.

EventWatch instructions are used to catch single events from a particular subblock to within the controller . The Finite State Machine FSM that controls each debug machine will look for the subblock events specified in the EventWatch instruction and perform the action e.g. breakpoint enable etc defined within the associated ActionList Instruction.

Each EventWatch instruction is 44 bits wide. There are two main types of EventWatch instruction single and double word EventWatch instructions. Double word EventWatch instructions are 88 bits long and occupy two entries within the EventWatchInst FIFO . The two types are shown below 

3. EventID This 4 bit code defines the individual subblock event as described by the EventID provided within each Event provided across interface from each of the subblocks to that make up the controller .

4. EventData This 32 bit code defines the individual subblock to event being watched for for example the pReference field within the controller dedicated controller memory .

For a single word event watch the next EventWatch Instruction is first loaded from the EventWatchInst FIFO into the first of two EventWatch instruction buffers within the event service module . Next the SubModuleID EventID and EventData parts are compared to the incoming controller events using a comparator . Although these only contain the EventID and EventData the SubModuleID is known because each subblock has its own particular interface . The result of the comparison is then ORed with the results of the other comparisons being carried out by the other debug machines if applicable using the OR logic block . The output of the OR function block is used to control the output of an EventWatch instruction decoder which decodes the EWOpcode contained within the EventWatch instruction. The output of the EventWatch instruction decoder itself controls the output of the ActionList instruction decoder which decodes the ActionList instruction associated with the EventWatch instruction which has previously been loaded in from the ActionList instruction FIFO via an ActionList buffer . The output of the ActionList instruction decoder can be any one of a DebugEnable signal for controlling the local debug and trace unit of the processing resource associated with the debug machine in question a TraceEnable signal for enabling the output of the trace data from this point onwards a SyncEnable signal for enabling synchronisation between debug machines .

In addition to the fields present within a single word EventWatch instruction the double word EventWatch instruction contains a set of masks which are applied to the SubmoduleID EventID and EventData inputs according to the instruction specified in the MaskOp field prior to being evaluated against the EventWatch instruction field. The MaskOp field can have any of the values 

Both single and double EventWatch instructions use the same ActionList Instructions. The ActionList instruction enables the debug machine s to perform complex break point triggering trace enabling or disabling and synchronisation between various debug machines and contain the following Fields 

The static event module provides a set of user programmable via the static interface event filter masks to which are used to select whether a particular event from a particular subblock to should be captured. The event filter masks are applied to the SubModuleID EventID and EventData fields. There are two bits allocated in every event filter mask for every single bit of the data. This results in a filter mask of 76 bits assigned for each event filter mask. The operative meaning of each of these two bits is as follows 

The user definable number of Event filter masks to can be allocated to one of four event filter mask tables . Each event filter table can be contain a user definable number of event filter masks to . However in this specific embodiment these tables must contain contiguous filter masks. These tables allow further programmability and efficient use of hardware resources through the provision of filter mask subsets which can be enabled for individual debug machine to use.

The trace data formatter compressor module compresses the trace data to ensure that the best possible use is made of the limited capacity on chip trace buffer modules. Although compression modules may be provided together with the trace aggregation device or unified trace buffer these are designed to aggregate and compress instruction level or equivalent debug and trace data from each of the local debug and trace units associated with each of the processing resources . Since compression is optimised when the nature of the data is both well known and of similar type. Therefore this compressor acts on the well known type and similar form data derived from the static event filter before being output from the thread debug controller to the unified aggregation point if present.

The trace data formatter compressor contains an event switch which routes all the filtered and time stamped subblock events into the next available two entry FIFO which form the inputs to the field base correlator . The FIFOs are two entry to allow either single or double word events to be stored. The event switch is capable of accepting ten simultaneous events from the ten subblocks to of the controller . The event switch always writes to the lowest numbered FIFO currently available.

Once all the FIFOs contain at least one entry or once an internal timer expires denoting the end of the current FIFO load cycle then the FIFOs are pushed into the field base correlator. The internal timer is loaded with a fixed value when at least one entry resides in any of the 10 FIFOs and is reloaded when the events are read out.

The field base correlator performs fixed function operations on each of the fixed length event fields to maximise the number of zeros in the field on output. This is done by exploiting spatial and temporal correlation within each field referenced to the first FIFO. The first FIFO is therefore left as it is. The resultant fixed length fields for FIFOs to and the unaltered FIFO are then output to another field correlated FIFO prior to input into an intra symbol run length encoder . This intra symbol run length encoder performs zero run length encoding on each input symbol resulting in a set of variable length output symbols. These are again stored in a set of output FIFOs before being loaded into an Inter symbol run length encoder that produces the final output bitstream. The final output bitstream is packetized into variable length packets which are suitable for the trace buffer interface by a variable length packetizer .

The format of the trace packet data is physical layer dependent. Under circumstances where the physical layer does not have an explicit start of packet signal a receiver FSM may use the fixed pattern header and packet length field to over a number of packets to obtain a lock on to the packet delineations. An example packet format 

Referring back to the internal debug control module of the thread debug controller provides individual subblock debug enable signals and single step functionality for subblocks to within the controller . On receiving the internal DebugEnable signal from any of the debug machines the internal debug control module will put the specified subblock into debug mode. The user can also single step specified subblocks via the dynamic debug interface .

Whilst a specific embodiment of the invention has been described it is to be understood that this is by way of example only and that various modifications may be considered. Moreover the invention is of general application in any device or application that employs a multicore processor such as but not limited to a mobile telephone or voice over Internet Protocol VoIP gateway for example. Therefore the specific embodiment is not to be seen as limiting of the scope of protection which is to be determined by the following claims.

