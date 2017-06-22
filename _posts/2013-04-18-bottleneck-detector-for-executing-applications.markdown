---

title: Bottleneck detector for executing applications
abstract: A bottleneck detector may analyze individual workloads processed by an application by logging times when the workload may be processed at different checkpoints in the application. For each checkpoint, a curve fitting algorithm may be applied, and the fitted curves may be compared between different checkpoints to identify bottlenecks or other poorly performing sections of the application. A real time implementation of a detection system may compare newly captured data points against historical curves to detect a shift in the curve, which may indicate a bottleneck. In some cases, the fitted curves from neighboring checkpoints may be compared to identify sections of the application that may be a bottleneck. An automated system may apply one set of checkpoints in an application, identify an area for further investigation, and apply a second set of checkpoints in the identified area. Such a system may recursively search for bottlenecks in an executing application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09323651&OS=09323651&RS=09323651
owner: Microsoft Technology Licensing, LLC
number: 09323651
owner_city: Redmond
owner_country: US
publication_date: 20130418
---
Computer applications often have bottlenecks that may limit the throughput or efficiency of an application. Often bottlenecks may not be fully appreciated when the application code is being written and may only be noticeable when the code may be executed under load.

The bottlenecks may be an artifact of the application design poor programming technique or may be the result of outside constraints on an application. When a bottleneck may be identified a programmer may be able to investigate the bottleneck and rewrite or otherwise improve the code to increase application performance.

A bottleneck detector may analyze individual workloads processed by an application by logging times when the workload may be processed at different checkpoints in the application. For each checkpoint a curve fitting algorithm may be applied and the fitted curves may be compared between different checkpoints to identify bottlenecks or other poorly performing sections of the application. A real time implementation of a detection system may compare newly captured data points against historical curves to detect a shift in the curve which may indicate a bottleneck. In some cases the fitted curves from neighboring checkpoints may be compared to identify sections of the application that may be a bottleneck. An automated system may apply one set of checkpoints in an application identify an area for further investigation and apply a second set of checkpoints in the identified area. Such a system may recursively search for bottlenecks in an executing application.

An application programming interface may receive workload identifiers and checkpoint identifiers from which bottleneck detection may be performed. Workloads may be tracked through various checkpoints in an application and timestamps collected at each checkpoint. From these data bottlenecks may be identified in real time or by analyzing the data in a subsequent analysis. The workloads may be processed by multiple devices which may comprise a large application. In some cases the workloads may be processed by different devices in sequence or in a serial fashion while in other cases workloads may be processed in parallel by different devices. The application programming interface may be part of a bottleneck detection service which may be sold on a pay per use model a subscription model or some other payment scheme.

A bottleneck detector may use an iterative method to identify a bottleneck with specificity. An automated checkpoint inserter may place checkpoints in an application. When a bottleneck is detected in an area of an application the first set of checkpoints may be removed and a new set of checkpoints may be placed in the area of the bottleneck. The process may iterate until a bottleneck may be identified with enough specificity to aid a developer or administrator of an application. In some cases the process may identify a specific function or line of code where a bottleneck occurs.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

Bottlenecks in executing programs may be identified by analyzing the timestamps taken as workloads pass certain checkpoints. A bottleneck may be identified when the time to execute a workload between two checkpoints increases at a greater rate than the load increases.

A bottleneck detector may capture timestamps as workloads pass checkpoints within an application then analyze the timestamps to identify bottlenecks. The workloads may be any type of memory object message process thread or other application element that may be operated upon through a sequence of operations. Throughout the course of the workload various checkpoints may be placed to track the progress of the workload. For each workload a sequence of timestamps may be collected for each of the checkpoints that the workload may pass.

In a lightly loaded application each workload may typically be executed in approximately the same elapsed time. As the load increases to the point where a bottleneck may occur workloads may take an increasing amount of time at a bottleneck.

In a simple analogy workloads may be visualized as cars travelling on a multilane highway. When there is very little traffic each car may pass mile posts at approximately the same time from the previous mile post. If there was a bottleneck in the highway due to construction or an accident the number of lanes may constrict forcing the cars to slow down through the bottleneck. In such a case the time from one mile post to another for each car that may pass through the bottleneck may increase. This effect may be measured and detected as a bottleneck.

The timestamps may be taken at various locations within an application. In some cases an application may be decorated with function calls that may transmit a workload identifier and capture a timestamp for each checkpoint. The function calls may be placed throughout an application to track a workload s progress through the application. In such an embodiment the executable code for an application may be changed to include the checkpoint function calls. Such embodiments may make such changes in source code intermediate code binary code or other phases of an application.

In some embodiments an instrumented execution environment may identify checkpoints and set events at each checkpoint to capture timestamp data. In such embodiments the checkpoints may be created and managed without changing the executable code of an application. Such embodiments may have an identification system for creating and setting the checkpoints as well as a detection and collection system that may detect the checkpoint and collect related data.

The application may operate on a single device or across multiple devices. In a single device embodiment the application may execute on a single hardware platform which may have multiple processors and various memory and peripheral components. In a single device embodiment the device may have a clock from which timestamps may be taken.

In a multiple device application the application may consist of similar or different software components that may operate on different devices. For example some applications may operate in a computer cluster where each device may execute a similar instance of an application to the other devices. In another example several devices may process workloads in series where one device may process a workload which may be passed to another device for additional processing. In such embodiments a synchronized clock may be used to coordinate timestamps that may be gathered from multiple devices.

A bottleneck detection system may use various time series techniques for capturing analyzing and displaying bottleneck information in real time or near real time. With each data collection event a set of statistical parameters may be gathered and summed which may enable other statistical analyses to be performed. The statistical parameters may be lightweight enough to be calculated and updated with minimal computer processing overhead and a separate analysis routine may analyze the data for bottlenecks in an offline or near real time basis.

An application programming interface may receive workload identifiers and checkpoint identifiers from applications being analyzed for bottlenecks. The application programming interface may receive and store timestamped data. In some embodiments the application programming interface may analyze and display the data in real time or near real time. In other embodiments a detailed analysis may be performed on historical data.

The application programming interface may operate in several different architectures. In one architecture a programmer may add function calls within an application where the function calls may communicate with an application programming interface locally or over a network connection. In another architecture an execution environment may have alerts or other monitoring functions that may transmit information to the application programming interface when each checkpoint is reached. In some such architectures the execution environment may be an integrated development environment with code editors compilers debugging tools and other components.

The application programming interface may operate as a programmatic gateway to accept data in real time and an accompanying analysis and rendering engines may identify bottlenecks and may generate visualizations of the data. In some cases the analysis engines may identify bottlenecks automatically and generate an alert or other report. In other cases the analysis engine may generate graphs or other visualizations that may be displayed as data are received or using a secondary analysis.

The application programming interface may be one component of a paid service for application developers. The service may be a subscription based service pay per use service or have some other payment mechanism.

An automated bottleneck detection system may use a recursive mechanism to isolate and identify a bottleneck in an application. A first set of checkpoints may be used to identify a portion of an application that contains a bottleneck then a second set of checkpoints may be deployed within the identified portion. From analysis of the second set of checkpoints the location of a bottleneck may be refined. Such a process may iterate until a bottleneck is defined with a high degree of specificity.

An automated bottleneck detection system may include an automated mechanism for identifying and placing checkpoints in an application. In some embodiments such a mechanism may insert function calls or otherwise decorate an application in source code intermediate code binary code or some other form. In some cases an automated bottleneck detection system may attempt to identify natural breaks or other elements in an application into which to insert checkpoints. In some cases an automated mechanism for inserting checkpoints may place checkpoints at locations that may not be natural breaks.

In some cases an automated bottleneck detection system may use a set of predefined checkpoint function calls that may be inserted automatically or inserted by a programmer. In such embodiments the automated bottleneck detection system may turn on a first subset of checkpoint function calls identify the general area of a bottleneck then turn on a second subset of checkpoint function calls that are nearer to the bottleneck to home in on the bottleneck location.

Throughout this specification and claims the terms profiler tracer and instrumentation are used interchangeably. These terms refer to any mechanism that may collect data when an application is executed. In a classic definition instrumentation may refer to stubs hooks or other data collection mechanisms that may be inserted into executable code and thereby change the executable code whereas profiler or tracer may classically refer to data collection mechanisms that may not change the executable code. The use of any of these terms and their derivatives may implicate or imply the other. For example data collection using a tracer may be performed using non contact data collection in the classic sense of a tracer as well as data collection using the classic definition of instrumentation where the executable code may be changed. Similarly data collected through instrumentation may include data collection using non contact data collection mechanisms.

Further data collected through profiling tracing and instrumentation may include any type of data that may be collected including performance related data such as processing times throughput performance counters and the like. The collected data may include function names parameters passed memory object names and contents messages passed message contents registry settings register contents error flags interrupts or any other parameter or other collectable data regarding an application being traced.

Throughout this specification and claims the term execution environment may be used to refer to any type of supporting software used to execute an application. An example of an execution environment is an operating system. In some illustrations an execution environment may be shown separately from an operating system. This may be to illustrate a virtual machine such as a process virtual machine that provides various support functions for an application. In other embodiments a virtual machine may be a system virtual machine that may include its own internal operating system and may simulate an entire computer system. Throughout this specification and claims the term execution environment includes operating systems and other systems that may or may not have readily identifiable virtual machines or other supporting software.

Throughout this specification like reference numbers signify the same elements throughout the description of the figures.

In the specification and claims references to a processor include multiple processors. In some cases a process that may be performed by a processor may be actually performed by multiple processors on the same device or on different devices. For the purposes of this specification and claims any reference to a processor shall include multiple processors which may be on the same device or different devices unless expressly specified otherwise.

When elements are referred to as being connected or coupled the elements can be directly connected or coupled together or one or more intervening elements may also be present. In contrast when elements are referred to as being directly connected or directly coupled there are no intervening elements present.

The subject matter may be embodied as devices systems methods and or computer program products. Accordingly some or all of the subject matter may be embodied in hardware and or in software including firmware resident software micro code state machines gate arrays etc. Furthermore the subject matter may take the form of a computer program product on a computer usable or computer readable storage medium having computer usable or computer readable program code embodied in the medium for use by or in connection with an instruction execution system. In the context of this document a computer usable or computer readable medium may be any medium that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The computer usable or computer readable medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus device or propagation medium. By way of example and not limitation computer readable media may comprise computer storage media and communication media.

Computer storage media includes volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can accessed by an instruction execution system. Note that the computer usable or computer readable medium could be paper or another suitable medium upon which the program is printed as the program can be electronically captured via for instance optical scanning of the paper or other medium then compiled interpreted of otherwise processed in a suitable manner if necessary and then stored in a computer memory.

When the subject matter is embodied in the general context of computer executable instructions the embodiment may comprise program modules executed by one or more systems computers or other devices. Generally program modules include routines programs objects components data structures etc. that perform particular tasks or implement particular abstract data types. Typically the functionality of the program modules may be combined or distributed as desired in various embodiments.

A set of workloads may be executed by an application in an execution environment . The workloads may be any units of work that may be traced tracked or otherwise monitored on a series of checkpoints. As each workload is executed the various checkpoints and may capture a respective set of timestamps and . The timestamps may include load factors and other data.

A data collector may gather and transmit the data to an analyzer which may generate a graph or provide other output. In some cases the analyzer may produce output in real time while in other cases the analyzer may process the various data elements after collection has completed.

The bottleneck detection of embodiment may identify bottlenecks by measuring the difference in timestamps between various checkpoints for each workload. A bottleneck may be identified when the time difference between two checkpoints grows for each successive workload. In such a condition the downstream process may be processing fewer workloads than may be coming in causing the bottleneck.

The workloads may be any unit of work that may be tracked through an application. In some cases the unit of work may be captured in a data item that may be passed from one portion of executable code to another. In other cases the unit of work may be a process transaction thread or other executable or data element that may undergo transformations or changes by several portions of an application.

In some embodiments the workloads may be passed from one device to another. For example a high performance computing environment may use message passing to transmit workloads from one device to another. Other systems such as computer cluster arrangements may use multiple devices to handle workloads in parallel or in series.

The workloads may or may not be independent of each other. In some embodiments the workloads may be clearly delineated and independent. Other embodiments may have workloads that may interact with each other or are not fully independent. In many cases a more reliable bottleneck detection may occur with independent workloads.

At each checkpoint a timestamp and workload identifier may be captured. In many embodiments a load factor and other data may also be gathered. The timestamp may be a wall clock time that may reflect the actual time a checkpoint may have been encountered. Such a timestamp may be useful in cases where a workload may be processed by multiple devices.

In some embodiments the timestamp may be an elapsed time from some designated start time. For example some embodiments may start a clock when a workload encounters a first checkpoint then collect elapsed time from the first checkpoint for each subsequent checkpoint. Other embodiments may determine elapsed time from the preceding checkpoint.

With each checkpoint and timestamp a workload identifier may be captured. The workload identifier may be a mechanism to link subsequent checkpoint timestamps to each other. In some cases a workload identifier may have a natural and meaningful name. In other cases an arbitrary name may be assigned to workloads one example of which may be to assign consecutive numbers as workload identifiers.

A load factor may be collected with the timestamp. The load factor may be any indicator for the busy ness or amount of work attempting to be processed by a system. In some embodiments the load factor may be collected by a different data collection mechanism and matched to the data collected from the checkpoints by the timestamps or other mechanism. For example a load factor may be a network traffic metric gathered from a network interface a processor use metric collected from a hardware counter or other monitoring system.

The load factor may be implied in some embodiments. For example a load factor may be inferred from the number of workload items being processed at a given time or by the rate at which work items may be received by the system.

The analyzer may organize the data by checkpoint and may create a time series representing the time lag between a baseline time and the checkpoint timestamp for each workload. Such a time series may be analyzed to determine when the values grow. In a non bottleneck steady state such a time series would be expected to be a flat straight line. When a bottleneck occurs the values in such a time series would be expected to grow.

The growth in the time series values may be linear or non linear depending on the application. Some embodiments may monitor the checkpoint data in real time and using time series analyses may evaluate the data stream to determine when the data stream has deviated from an expected constant value.

In many embodiments such an analysis may take into consideration the variance of the data. Some data sets may contain more noise than others and the correlation coefficient or other metrics of noise may be different for each application. In general the larger the variance in the data the greater a deviation may be present before a bottleneck may be identified.

A single device architecture may gather tracer data containing timestamps gathered at various checkpoints analyze the data and graphically display the data or perform bottleneck detection.

A multiple device architecture may divide different components of the data gathering analysis and management functions over different devices. The multiple device architecture may be one way to deliver an application programming interface that may detect bottlenecks from tracer data.

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be execution environment level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the functions described.

Embodiment illustrates a device that may have a hardware platform and various software components. The device as illustrated represents a conventional computing device although other embodiments may have different configurations architectures or components.

In many embodiments the device may be a server computer. In some embodiments the device may still also be a desktop computer laptop computer netbook computer tablet or slate computer wireless handset cellular telephone game console or any other type of computing device.

The hardware platform may include a processor random access memory and nonvolatile storage . The hardware platform may also include a user interface and network interface .

The random access memory may be storage that contains data objects and executable code that can be quickly accessed by the processors . In many embodiments the random access memory may have a high speed bus connecting the memory to the processors .

The nonvolatile storage may be storage that persists after the device is shut down. The nonvolatile storage may be any type of storage device including hard disk solid state memory devices magnetic tape optical storage or other type of storage. The nonvolatile storage may be read only or read write capable. In some embodiments the nonvolatile storage may be cloud based network storage or other storage that may be accessed over a network connection.

The user interface may be any type of hardware capable of displaying output and receiving input from a user. In many cases the output display may be a graphical display monitor although output devices may include lights and other visual output audio output kinetic actuator output as well as other output devices. Conventional input devices may include keyboards and pointing devices such as a mouse stylus trackball or other pointing device. Other input devices may include various sensors including biometric input devices audio and video input devices and other sensors.

The network interface may be any type of connection to another computer. In many embodiments the network interface may be a wired Ethernet connection. Other embodiments may include wired or wireless connections over various communication protocols.

The software components may include an operating system on which various software components and services may operate. An operating system may provide an abstraction layer between executing routines and the hardware components and may include various routines and functions that communicate directly with various hardware components.

An execution environment may execute an application and a tracer may collect timestamps and other information at checkpoints in the application . The tracer may store its output as tracer data .

The execution environment may be any mechanism that may cause the application to be executed and include a tracer that may gather data at each checkpoint. In some embodiments the execution environment may be a virtual machine such as a process virtual machine or system virtual machine that may be instrumented with a tracer . In other embodiments the execution environment may be an integrated development environment that may include a code editor compiler debugging tools and other functionality.

The tracer may be any mechanism that may collect data at each checkpoint. In some cases the tracer may include function calls or other code that may be inserted into the executable code as binary code intermediate code or source code. In other cases the tracer may operate without modifying the executable code of the application .

A checkpoint inserter may create checkpoints and cause the tracer to collect data at the various checkpoints. In some cases the checkpoint inserter may decorate the application with function calls or other tracer related code. In other cases the checkpoint inserter may create checkpoints that may be monitored by the tracer to collect the tracer data .

In some embodiments the checkpoint inserter may be a fully automated application part that may select checkpoints and cause the tracer to execute at each checkpoint. In other embodiments the checkpoint inserter may have some user interface through which a human programmer may select locations for checkpoints which may be automatically or manually inserted into an application.

A data analyzer may receive the tracer data to detect various bottlenecks. In some embodiments the output of the data analyzer may be transmitted to a rendering engine to display graphical results.

A tracer manager device may operate on a hardware platform which may be similar to the hardware platform . In some cases the various hardware platforms may include cloud based execution environments which may or may not have a notion of a computing device .

A tracer manager may manage the operations of a tracing system over multiple devices such as applications that may be deployed on a clustered computer configuration or other multiple device architecture. In such embodiments the tracer manager may coordinate execution of an application tracers on each device as well as load generators and other components. The tracer manager may also control a checkpoint inserter and data analyzer .

In some embodiments the tracer manager may operate bottleneck detection as a paid service. In such an embodiment customers may pay for bottleneck detection analysis using a payment manager which may charge on a subscription basis a pay per use basis or other mechanisms.

One or more execution platforms may execute the application and may collect checkpoint data. The execution platforms may each have a hardware platform on which an execution environment may run. Each application may be identical instances of the same application or may be different components of a larger application. The tracers may gather trace data when a checkpoint is reached.

A data collection device may operate on a hardware platform and may contain an application programming interface that may receive data from the tracers and store the tracer data for analysis. The application programming interface may receive data taken at each checkpoint occurrence then store the data.

In some cases the application programming interface may perform some processing of the incoming data. For example some embodiments may create a timestamp when a data element is received from a tracer . In another example some embodiments may preprocess the incoming data into a format that may be further processed by an analysis engine.

The application programming interface may be used by the tracer that may operate on an embodiment with a single execution environment as well as gathering data from multiple tracers on multiple execution environments.

A load generator device may operate on a hardware platform and may have a load generator application. The load generator may create workloads that may be processed by an application. In some cases such workloads may be artificial or fictitious workloads that may exercise the application so that bottlenecks may appear in the tracer data.

The backlog may indicate the amount of time that a workload took to reach a given checkpoint. Five lines and are shown in the graph and each line may represent the backlog for a given checkpoint as a function of the load experienced by the system.

The graph of embodiment may or may not reflect the sequence of workloads processed by an application but instead may reflect measurements taken at different levels of loading. If the workload was applied in ever increasing amounts the graph may represent the backlog received over time but in many cases data used to generate a graph such as embodiment may be gathered over many cycles of high medium and low loads.

In a normal situation where a checkpoint does not experience a bottleneck the checkpoint lines may be horizontal lines such as for checkpoints and .

At a certain amount of load checkpoint line may diverge at the inflection point . The inflection point may identify the load at which a bottleneck occurred as well as identified that the bottleneck occurred between checkpoints and . A programmer may be able to spot the inflection point visually and investigate the bottleneck in the code between checkpoints and .

As the load increases a second inflection point may indicate a second bottleneck that may occur between checkpoints and . Again a programmer may be able to investigate and attempt to address the bottleneck.

The graph of embodiment may be created by mapping the elapsed time for each workload measured from an initial starting point. When such a measurement or calculation is performed each checkpoint may be illustrated as a stacked line configuration where the sequence of workflow may be from the bottom of the graph to the top.

The result of such a measurement may also yield lines that are parallel to each other. For example checkpoint remains parallel to checkpoint after the inflection point . This indicates that the time between checkpoints and may not have changed even after the bottleneck was incurred. The rise of the checkpoint may reflect the downstream effects of the bottleneck in checkpoint .

In some embodiments the infection points and may be identified through numerical analysis. Such numerical analysis may attempt to fit a curve to the data points beginning with a straight line curve and progressing to more complex curves. When the data may not fit a straight line curve an analysis may attempt to find an inflection point by fitting two line segments. The correlation coefficient for each curve fitting step may be used as a measure of variance in the data as well as a metric for determining when a fitted curve is a sufficient match.

The analysis of checkpoint lines may involve comparing the slope of a linear curve fitting analysis such as linear regression. In such analysis a positive change in slope from one checkpoint line to a subsequent checkpoint line may indicate a bottleneck.

The backlog may indicate the amount of time that a workload took to reach a given checkpoint. Six lines and are shown in the graph and each line may represent the backlog for a given checkpoint as a function of the time.

The graph of embodiment may illustrate a system s response to increasing and decreasing loads. The amount of load is not shown in the graph but the effects of load may be illustrated.

As with graph checkpoints and illustrate checkpoints where no bottlenecks have been experienced. At inflection point checkpoint experienced a bottleneck that continues to build until inflection point where the bottleneck recedes until the bottleneck dissipates. While that is occurring checkpoint experiences an inflection point which indicates a second bottleneck. In the graph the bottleneck of checkpoint appears to build while the bottleneck of checkpoint recedes.

The X axis may show datasets for individual workloads as organized by the start time for the workload. Workloads and are illustrated with data points indicating when the workloads passed checkpoints and . Additional workloads are also shown.

The checkpoints and may have lines representing a best fit across the various checkpoint data points for the workloads. From even casual observation the line fitted to checkpoint data appears to be flat and does not change over time while the line fitted to checkpoint appears to rise and the line fitted to checkpoint appears to rise even further.

The difference between the slopes of the lines for checkpoint and may indicate that a bottleneck exists between checkpoints and and that the bottleneck grows as time increases. A similar situation may also be present between checkpoints and . In some datasets workloads may be processed in irregular patterns. In the example of embodiment workloads and may be received with a time distance while workloads and may have been received with a shorter time distance .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

A tracer may operate in an execution environment to gather timestamp and other data at each checkpoint. In some cases the checkpoint may be identified by function calls or other markers in the executable code. In other cases a checkpoint may be an event executable code component or other identifiable element of an executing code.

An execution environment may receive workloads for an application in block . For each workload in block the workload may be executed to a first checkpoint in block and timestamp and other data may be taken in block . The workload may be executed to a second checkpoint in block and a second timestamp and other data may be taken in block . Similarly the workload may be executed to a third checkpoint in block and a third timestamp and other data may be taken in block . The sequence of execution to a checkpoint and collecting data may continue until the workload has finished being processed.

The execution environment may process many workloads in the manner of blocks through . In many cases multiple workloads may be progressing through an application at once.

After collecting all the timestamps and other data the data may be stored in block and analysis may be performed on the data in block .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment illustrates one method for analyzing tracer data in real time or near real time. A timestamp may be received in block and a workload level or other data may be determined in block . The timestamp may include a workload identifier and checkpoint identifier. In some embodiments only the workload identifier and checkpoint identifier may be received and the timestamp may be determined after receiving the data.

In the example of embodiment the timestamp may represent a value in the Y axis and the workload level may represent a value in the X axis which may be used to generate a graph such as may be shown in embodiment .

In the example of embodiment where the X axis represents time the workload level may not be collected in block .

A set of time series statistics may be updated in block . The time series statistics may be any type of statistics from which further analyses may be performed. In a simple example of such statistics the time series statistics may reduce or compress the full trace of X and Y values to the sum of all X values sum of all Y values the sum of the square of X values the sum of the square of Y values the sum of the product of XY and the number of samples. From these time series data linear regression may be performed on the dataset to generate a slope and intercept as well as a correlation coefficient.

In such an embodiment an analysis may be performed that compares the slope of adjacent checkpoint datasets. When the slope of a later checkpoint diverges or increases from a previous checkpoint a bottleneck may be identified.

After updating the time series statistics in block the process may loop back to block to process another incoming dataset. Such a loop may be performed relatively quickly and the remaining blocks and may be performed either offline or in a different thread or process so that the data collection of blocks through may proceed without delay.

In block new values for a visualization graph may be determined and the visualization may be rendered in block . In many cases the calculation and rendering operations of blocks and may consume a relatively large amount of resources than blocks through thus blocks and may be separated.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment illustrates a method that analyzes data gathered in a process such as that of embodiment and detects bottlenecks.

Historical data may be received in block . The data may be analyzed for each checkpoint in block . For a given checkpoint the data for each workload may be analyzed in block .

For each workload a time difference may be calculated from a previous checkpoint in block . The time difference may be calculated from the immediately preceding checkpoint in some embodiments while other embodiments may calculate the time difference from a start time for the workload.

In block a workload factor may be identified for the time corresponding to the timestamp of the current workload at the current checkpoint. The workload factor may be used in embodiments where the analysis may be performed on historical data. In an embodiment such as embodiment where the X axis of a graph may be time a workload factor may not be used.

After preparing the data in blocks through a curve fitting analysis may be performed. In some cases the curve fitting may be performed against a load factor while in other cases the curve fitting may be performed against time.

An analysis of the fitted curve may be performed in block for any anomalies. An anomaly may be a very high correlation coefficient in a linear curve fitting attempt an inflection point in a more complicated curve fitting method or some other indicator that that data may not be adequately represented by a line. When an anomaly is not detected in block the checkpoint curve may not reveal a bottleneck. When an anomaly is detected in block the location may be labeled as a bottleneck.

The analysis of blocks through may analyze the data at each checkpoint to attempt to identify a bottleneck. The analysis from blocks through may attempt to identify bottlenecks by comparing two checkpoint data streams to each other.

For each checkpoint in block the curve of the current checkpoint is compared to the curve of the previous upstream checkpoint in block . The comparison in block may compare the slope of one checkpoint dataset to the slope of a second checkpoint dataset. In such embodiments a diverging slope may indicate that a later checkpoint contains a bottleneck with respect to the previous checkpoint.

In other embodiments where the curve fitting is a more complex expression the comparison may detect whether both checkpoint curves are offset or parallel to each other. Diverging data sets may indicate that the later checkpoint may contain a bottleneck with respect to the earlier checkpoint.

When the difference between the two curves is not significant in block the current checkpoint may not be considered as a bottleneck in block .

When the difference between the two curves is significant in block the current checkpoint may be considered to have a bottleneck in block and the checkpoint may be labeled as a bottleneck in block .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment is an example of an iterative method to identify a bottleneck with a high degree of specificity. Embodiment is an example of a method by which a relatively small number of checkpoints may be spread through an application and when a bottleneck is detected between two of the checkpoints another set of checkpoints may be placed in the area of the application between the checkpoints and the process may be repeated.

The method of embodiment may iterate repeatedly to find a bottleneck with a high degree of specificity. Such specificity may be at the level of a single function call or even a specific line of an application depending on the embodiment.

In block an application may be received. The application may be analyzed in block to identify checkpoints and the checkpoints may be added to the application in block .

In some embodiments the checkpoints in block may be natural locations in an application where a checkpoint may be relevant. Examples of such locations may be at function calls or other points within the application. In other embodiments the checkpoints may be identified by merely spacing the checkpoints within the application code by a predefined number of instruction lines or some other method.

The application may begin execution in block and data may start to be collected. In block a load may be applied which may be an artificial load or a natural load in a production system.

The checkpoint data may be analyzed to identify a bottleneck in block . In some cases the application may be driven with ever increasing loads until a bottleneck becomes apparent.

If the bottleneck is identified in block but the bottleneck is not identified with enough specificity in block an additional set of checkpoints may be determined in block and added to the application in block . The older checkpoints may be removed or turned off in block and the process may return to block to iterate again.

The iterations may continue with smaller and smaller spacing between checkpoints until the bottleneck is defined with sufficient specificity in block at which point the iterations may stop and the bottleneck may be identified for the developer in block .

The foregoing description of the subject matter has been presented for purposes of illustration and description. It is not intended to be exhaustive or to limit the subject matter to the precise form disclosed and other modifications and variations may be possible in light of the above teachings. The embodiment was chosen and described in order to best explain the principles of the invention and its practical application to thereby enable others skilled in the art to best utilize the invention in various embodiments and various modifications as are suited to the particular use contemplated. It is intended that the appended claims be construed to include other alternative embodiments except insofar as limited by the prior art.

