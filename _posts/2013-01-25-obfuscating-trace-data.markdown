---

title: Obfuscating trace data
abstract: A tracer may obfuscate trace data such that the trace data may be used in an unsecure environment even though raw trace data may contain private, confidential, or other sensitive information. The tracer may obfuscate using irreversible or lossy hash functions, look up tables, or other mechanisms for certain raw trace data, rendering the obfuscated trace data acceptable for transmission, storage, and analysis. In the case of parameters passed to and from a function, trace data may be obfuscated as a group or as individual parameters. The obfuscated trace data may be transmitted to a remote server in some scenarios.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09021262&OS=09021262&RS=09021262
owner: Concurix Corporation
number: 09021262
owner_city: Kirkland
owner_country: US
publication_date: 20130125
---
Tracing gathers information about how an application executes within a computer system. Trace data may include any type of data that may explain how the application operates and such data may be analyzed by a developer during debugging or optimization of the application. In many cases trace data may be used for debugging an application as well as understanding and optimizing the application. Trace data may also be used by an administrator during regular operation of the application to identify any problems.

An instrumented execution environment may connect to an execution environment to provide detailed tracing and logging of an application as it runs. The instrumented execution environment may be configured as a standalone service that can be configured and purchased. The instrumented execution environment may be deployed with various authentication systems administrative user interfaces and other components. The instrumented execution environment may engage a customer s system through a distributor that may manage an application workload to distribute work to the instrumented execution environment as well as other worker systems. A marketplace may provide multiple preconfigured execution environments that may be selected further configured and deployed to address specific data collection objectives.

A load balanced system may incorporate instrumented systems within a group of managed devices and distribute workload among the devices to meet both load balancing and data collection. A workload distributor may communicate with and configure several managed devices some of which may have instrumentation that may collect trace data for workload run on those devices. Authentication may be performed between the managed devices and the workload distributor to verify that the managed devices are able to receive the workloads and to verify the workloads prior to execution. The workload distributor may increase or decrease the amount of instrumentation in relation to the workload experienced at any given time.

A parallel tracer may perform detailed or heavily instrumented analysis of an application in parallel with a performance or lightly instrumented version of the application. Both versions of the application may operate on the same input stream but with the heavily instrumented version having different performance results than the lightly instrumented version. The tracing results may be used for various analyses including optimization and debugging.

A tracer may obfuscate trace data such that the trace data may be used in an unsecure environment even though raw trace data may contain private confidential or other sensitive information. The tracer may obfuscate using irreversible or lossy hash functions look up tables or other mechanisms for certain raw trace data rendering the obfuscated trace data acceptable for transmission storage and analysis. In the case of parameters passed to and from a function trace data may be obfuscated as a group or as individual parameters. The obfuscated trace data may be transmitted to a remote server in some scenarios.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

An instrumented execution environment may be deployed as a service. After creating an account a user may add the instrumented execution environment to a workload distributor within the user s own execution environment. The workload distributor may receive an incoming workload stream and direct some or all of the workload to the instrumented execution environment.

The instrumented execution environment may contain software hardware and other components that may capture various information while processing a workload. The instrumentation may collect various trace data that may be stored and analyzed. In some cases the trace data may be analyzed after collection while in other cases trace data may be analyzed on a real time basis.

A user may use an administrative user interface to configure the instrumented execution environment for use with a distributor. The user may be able to establish an account determine a payment mechanism and select various features of an instrumented execution environment.

The administrative activities may also include creating various authentication keys or other mechanisms that may authenticate the interacting systems to each other. The authentication system may be used to verify that the instrumented execution environment has been permitted to receive the output of a distributor and that the distributor is authorized to send work items to the instrumented execution environment.

A distributor may be added to a user s execution environment to introduce a redirection point or decision point in an application. In some cases the distributor may be an application that intercepts an input stream and applies both load balancing and instrumentation logic to identify an execution environment to process a given work item. In some cases the distributor may be executable code that may be included in a library that may be called from within an application.

The instrumentation may be provided as a service to a developer or administrator of an application. The instrumentation may collect data using sophisticated tools and analysis that may be complex to install configure or operate. A user may pay for such a service using many different payment schemes such as paying based on part on how much processing storage or other resource may be consumed. In some cases the payment may be a subscription for use over a period of time such as a fixed fee payment for a month of service. Many other payment schemes may be deployed.

A load balanced or other managed computation environment may distribute work items to instrumented and non instrumented systems. The load balancing or distribution may occur with consideration of instrumentation objectives for an application. In one example the instrumentation may be performed when the load on the systems may allow but instrumentation may be reduced or eliminated when load factors increase.

The workload distributor may have several instrumentation objectives that define conditions to collect data as well as the data to be collected. The objectives may include items such as sampling rates events or conditions that start or stop instrumentation quantity or quality of data to be collected as well as the specific parameters or types of instrumentation to be applied.

The workload distributor may transmit instrumentation objectives to a worker system where the objectives may cause the worker system to collect the described data. In such cases the distributor may be able to create customized objectives for instrumenting each work item.

The computation environment may have multiple worker systems that execute work items as defined by a distributor. Each worker system may register with the distributor which may include initial contact and registration as well as establishing an authentication mechanism between the devices. The status of the worker systems may be collected periodically and used to determine availability to perform a given work item.

A heavily instrumented tracer may operate in parallel with a lightly instrumented tracer to capture both detailed and performance measurements of an application. In many cases heavy instrumentation may adversely affect the performance of an application thereby corrupting any performance metrics that may be collected at the same time. As the instrumentation becomes more detailed the performance metrics generally may become more affected.

The tracing system may operate in parallel to trace in a performance environment that may capture only performance metrics while another detailed tracer may capture detailed results. In some cases the same application workload may be analyzed in parallel and the performance and detailed results may be aggregated together to produce a complete representation of the application.

The architecture of a parallel tracing system may be deployed in a distributed computing environment. In such an environment multiple devices or processors may each perform some of the work of an application. A computing cluster may be one example of a distributed computing environment where multiple devices each execute a portion of an input stream.

A single device may be capable of parallel tracing. A multi processor device may have some processors that may process an application workload in a high performance manner while other processors execute the application using a detailed tracer.

The concept of parallel tracing may be applied to a single system or single processor system. In such a system the separate tracing operations may be performed sequentially. For example a first run of an application workload may be performed using a performance level instrumentation followed by a second run of the workload using a detailed instrumentation system. In such an embodiment the input stream may be captured for later execution in a detailed manner.

A distributor may identify units of work from an input stream to transmit to different components. A unit of work may be any computing workload that may be executed in a relatively independent fashion. For each program or application the units of work may be different.

In some applications a unit of work may be a function call that may include input parameters for the function. For functional languages such as Erlang Haskell Scala F or for non functional languages that are written in a functional manner portions of an application may be able to be computed independently. In some cases the units of work may have dependencies or other interactions with other units of work.

A unit of work may be an input item or request made to an application. In an example of an application programming interface a call to the interface may be considered a unit of work that may be executed by an instance of the application. Such requests may or may not depend on other requests but in general many such systems may have requests that may operate independently from other requests.

In some cases a unit of work that may be executed by two differently instrumented systems may return different results. In a simple example a unit of work may perform a function based on the exact time of day. In such an example a unit of work executed on performance level instrumentation would return a different value than the same unit of work executed on a highly instrumented system that may be considerably slower.

When a unit of work executed on two different systems returns different values an algorithm may be applied to determine a return value. In systems where latency response time or other performance related factors may adversely affect results results from a performance level instrumented system may be used while results collected from highly instrumented system may be discarded. In some cases the results from the performance level instrumented system may be discarded in favor of results from a highly instrumented system. In still other cases averages or other summaries may be used to aggregate the application results from two separate runs of a unit of work.

A tracer may obfuscate data collected from an application and transmit obfuscated data to an analysis engine. The analysis engine may perform all analyses on the obfuscated data such that the analysis engine may not be exposed to any confidential private or otherwise sensitive data contained in the tracer collected data.

A tracer may collect data during the execution of an application. The application may process data that may be sensitive. When the tracer encounters application data such data may be obfuscated prior to analysis. The obfuscated data may then be analyzed to understand categorize optimize or perform other functions relating to the application. In some cases the analysis may generate recommendations or other results that may refer to specific data elements that may be obfuscated. In such cases a mechanism for determining the underlying data values may be provided through a reverse obfuscation process.

The obfuscation process may consist of a hash function which may be lossy or not. In other embodiments the obfuscation process may be an encryption process that may or may not be cryptographically secure. Still other embodiments may employ a lookup table maintained on a client device that translates a meaningful data value to an arbitrary value for analysis.

Multiple values may be hashed or otherwise considered as a single element in the tracer output. For example a function may be called with three arguments. In some embodiments the three arguments may be combined into a single argument and hashed or otherwise obfuscated into a single value. In other embodiments the three arguments may be individually obfuscated and stored as three separate values.

Throughout this specification and claims the terms profiler tracer and instrumentation are used interchangeably. These terms refer to any mechanism that may collect data when an application is executed. In a classic definition instrumentation may refer to stubs hooks or other data collection mechanisms that may be inserted into executable code and thereby change the executable code whereas profiler or tracer may classically refer to data collection mechanisms that may not change the executable code. The use of any of these terms and their derivatives may implicate or imply the other. For example data collection using a tracer may be performed using non contact data collection in the classic sense of a tracer as well as data collection using the classic definition of instrumentation where the executable code may be changed. Similarly data collected through instrumentation may include data collection using non contact data collection mechanisms.

Further data collected through profiling tracing and instrumentation may include any type of data that may be collected including performance related data such as processing times throughput performance counters and the like. The collected data may include function names parameters passed memory object names and contents messages passed message contents registry settings register contents error flags interrupts or any other parameter or other collectable data regarding an application being traced.

Throughout this specification and claims the term execution environment may be used to refer to any type of supporting software used to execute an application. An example of an execution environment is an operating system. In some illustrations an execution environment may be shown separately from an operating system. This may be to illustrate a virtual machine such as a process virtual machine that provides various support functions for an application. In other embodiments a virtual machine may be a system virtual machine that may include its own internal operating system and may simulate an entire computer system. Throughout this specification and claims the term execution environment includes operating systems and other systems that may or may not have readily identifiable virtual machines or other supporting software.

Throughout this specification like reference numbers signify the same elements throughout the description of the figures.

When elements are referred to as being connected or coupled the elements can be directly connected or coupled together or one or more intervening elements may also be present. In contrast when elements are referred to as being directly connected or directly coupled there are no intervening elements present.

The subject matter may be embodied as devices systems methods and or computer program products. Accordingly some or all of the subject matter may be embodied in hardware and or in software including firmware resident software micro code state machines gate arrays etc. Furthermore the subject matter may take the form of a computer program product on a computer usable or computer readable storage medium having computer usable or computer readable program code embodied in the medium for use by or in connection with an instruction execution system. In the context of this document a computer usable or computer readable medium may be any medium that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The computer usable or computer readable medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus device or propagation medium. By way of example and not limitation computer readable media may comprise computer storage media and communication media.

Computer storage media includes volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can accessed by an instruction execution system. Note that the computer usable or computer readable medium could be paper or another suitable medium upon which the program is printed as the program can be electronically captured via for instance optical scanning of the paper or other medium then compiled interpreted of otherwise processed in a suitable manner if necessary and then stored in a computer memory.

When the subject matter is embodied in the general context of computer executable instructions the embodiment may comprise program modules executed by one or more systems computers or other devices. Generally program modules include routines programs objects components data structures etc. that perform particular tasks or implement particular abstract data types. Typically the functionality of the program modules may be combined or distributed as desired in various embodiments.

Embodiment illustrates an example of a tracing system that gathers data in a secure environment and obfuscates the data prior to sending the data to a remote system for analysis. The remote system may be in an unsecured environment but because the sensitive data are obfuscated any analysis on those data can be performed without compromising the security of the underlying data.

In an example a secure environment may have an application that may process sensitive data. The sensitive data may be for example credit card numbers social security numbers employment data healthcare data classified military data financial data or any other type of data that may be sensitive from a legal business personal or other perspective.

A tracer may monitor the application to collect performance and operational data while the application executes. The tracer may examine individual functions threads processes messages data objects and other information and that are part of the application or may be handled by the application. The tracer may perform low level inspection of various program elements the results of which may be used to analyze the program execution. Such analysis may be for debugging auditing optimization or other purposes.

In many cases the tracer may handle or come in contact with information that includes sensitive data. In such a circumstance the data may be obfuscated prior to leaving the secure environment . In a simple example a function may receive a data object such as a raw credit card number. A trace of the function may collect the credit card number as a value passed to the function. In another example a message passed from one thread to another may contain unfiltered financial information a medical record object or other sensitive information. During normal tracing operations such sensitive data may be collected but the sensitive data may be obfuscated before passing the data outside of the secure environment.

When sensitive data are collected and handled within the secure environment the data may be considered safe. In a typical secure environment data may be processed in a facility that complies with various privacy and security standards and procedures. Such facilities may maintain physical security that limits access to certain personnel as well as network security that restricts access to the data.

An obfuscator may obfuscate some or all of the trace data to create obfuscated trace data . The obfuscator may use various hash functions encryption algorithms substitution schemes or other techniques to make protect the sensitive data. In some cases the obfuscator may create a lookup database that may contain the raw and obfuscated values for the traced data.

The obfuscated trace data may be transmitted outside the secure environment . The obfuscated trace data may be located on a remote device or other system that may have an analysis engine that may perform analytics optimizations or other analyses on the obfuscated trace data . The results of the analysis engine may reference individual data items or may contain references to data elements that remain obfuscated.

The results may be passed back into the secure environment and acted upon by a results processor . The results processor may determine the raw data values from the obfuscated data values. In some cases such an operation may involve looking up the raw data value from the lookup database .

In one use scenario a tracer may analyze an application that may handle bank account information for example. The tracer may identify a function to monitor where the function receives a bank account number and returns a balance. In this example the bank account number and the balance may be treated as private information.

The tracer may detect that the function has been called and may capture the data sent to the function and the data returned by the function. In this case the bank account information has been transferred to the function and the balance returned. The function may be called many times and the tracer may capture each time the function is called. After monitoring the application for a period of time the trace data may contain bank account information and balance information.

Before transmitting the trace data outside of the secure environment an obfuscator may obfuscate the trace data to create obfuscated trace data . Once obfuscated the data may be analyzed by a remote system to determine performance metrics or debugging information for the application .

The analysis may handle each data object using the obfuscated value. In an example a debugging analysis may determine that a specific input value to the function causes an unexpected behavior to the function. Because the analysis is performed on the obfuscated data the analysis results may be transmitted back to the secure environment where the original value for the trace data may be determined and action taken on the results.

In such a scenario the sensitive data may be kept within the secure environment yet the analysis may be performed in an environment that does not share the same level of security. For example a trace analyzer or program optimizer may analyze applications that may be secret secure private or otherwise sensitive yet the results may be transmitted and analyzed in a relatively open environment. For example the obfuscated trace data may be transmitted in clear text with minimum or no encryption and stored in a facility that may not meet the high security standards of the application .

The analysis engine may be an automated semi automated or manual analysis of the obfuscated trace data . The results may contain direct references to the obfuscated trace data such as identifying the data values that caused an error condition for example. However because the analyses may be performed only on obfuscated trace data the analysis engine may not be exposed to the underlying raw data.

In some cases the remote system may collect data from multiple users each of which may produce obfuscated trace data. The data from each user may be combined into a single database containing trace data from many sources. In such cases the remote system may store only obfuscated data and sensitive data may be kept within the secure environment .

The obfuscator may create obfuscated trace data using several different mechanisms. In some cases the obfuscation mechanisms may or may not be lossy.

An example of a non lossy system may be an encryption system that may use a key to encrypt the data. In such a system the obfuscator may encrypt the data items using the key and the analysis engine may process the encrypted data objects. Once the results are returned to the secure environment the results processor may decrypt the results using the key. Such a system may not use a lookup database to re create the raw values from the obfuscated values.

Another example of a non lossy system may be the use of a non reversible secure hash such as MD5 SHA or other hash functions. Such functions may have none or very few collisions but may be extremely difficult to extract the original value from the obfuscated value. In such systems a lookup database may be used to store the hashed and raw values so that results may be converted back to raw un hashed values.

An example of a lossy system may apply a lossy hash function such as a checksum or other lossy compression technique to the raw data. Examples of such systems may be hash functions that have many collisions. Such a system may create obfuscated data elements that may not be reversed into a single value with a degree of certainty.

An example of another system a lookup database may be used to assign a random or sequential value to a raw value. For example a record for each new raw value may be assigned an incrementing index and the index may serve as the obfuscated value. Because the lookup database may contain sensitive data the lookup database may be stored and protected within the secure environment .

In some embodiments different types of obfuscation may be applied to different trace data. For example highly sensitive data elements may be obfuscated with encryption while less sensitive data elements may be obfuscated with a simpler hash function. Such an embodiment may apply more computationally expensive obfuscation to more sensitive data and less computationally expensive obfuscation to less sensitive data.

Some trace data may be stored in cleartext or may not be obfuscated. For example some embodiments may store function names in cleartext yet may obfuscate data passed to and from a function. In general a function name parameter name variable name or other hard coded descriptors within an application may describe operations of an application but not the underlying data that may be processed.

Cleartext descriptors of application elements may be extracted from a source code description of the application. Some embodiments may include a source code analyzer that extracts the descriptors of various application elements. In some embodiments such analyzers may be built into a compiler the output of which may include debugging or tagging information.

Cleartext descriptors of application elements such as functions variables data objects methods or other elements may give a developer and administrator meaningful feedback regarding the performance of their application even when the underlying data may be obfuscated. For example an analysis engine may identify function FOO has behaving in a certain manner and provide feedback that names function FOO. An application developer may recognize function FOO and be able to take action. Such an analysis may be performed in an unsecure manner using obfuscated data elements but with cleartext representations of program elements.

Cleartext descriptors of application elements may include function names variable names data object names record descriptors column descriptors annotations method names class names library names file names parameter names tags control flow diagrams and other descriptors. Typically such descriptors may be created by a programmer or developer and may reflect the programmer s intent or logic.

In certain circumstances such descriptors may reflect confidential information. The confidential information may be the underlying logic or program flow which may be separate from the confidential nature of the data handled by the application. For example an application that processes healthcare records may have a proprietary or trade secret method for analyzing a healthcare record. While the healthcare record itself may be confidential under HIPPA or other statutory or regulatory provisions the methodology of the application may be a separate class of confidential information.

In cases where such descriptors reflect application logic third party analysis may be performed under a nondisclosure agreement privacy arrangement or other confidentiality provision as the third party may be exposed to the underlying methodology in an application but not be exposed to the data handled by the application.

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be execution environment level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the functions described.

Embodiment illustrates a device that may have a hardware platform and various software components . The device as illustrated represents a conventional computing device although other embodiments may have different configurations architectures or components.

In many embodiments the device may be a server computer. In some embodiments the device may still also be a desktop computer laptop computer netbook computer tablet or slate computer wireless handset cellular telephone game console or any other type of computing device.

The hardware platform may include a processor random access memory and nonvolatile storage . The hardware platform may also include a user interface and network interface .

The random access memory may be storage that contains data objects and executable code that can be quickly accessed by the processors . In many embodiments the random access memory may have a high speed bus connecting the memory to the processors .

The nonvolatile storage may be storage that persists after the device is shut down. The nonvolatile storage may be any type of storage device including hard disk solid state memory devices magnetic tape optical storage or other type of storage. The nonvolatile storage may be read only or read write capable. In some embodiments the nonvolatile storage may be cloud based network storage or other storage that may be accessed over a network connection.

The user interface may be any type of hardware capable of displaying output and receiving input from a user. In many cases the output display may be a graphical display monitor although output devices may include lights and other visual output audio output kinetic actuator output as well as other output devices. Conventional input devices may include keyboards and pointing devices such as a mouse stylus trackball or other pointing device. Other input devices may include various sensors including biometric input devices audio and video input devices and other sensors.

The network interface may be any type of connection to another computer. In many embodiments the network interface may be a wired Ethernet connection. Other embodiments may include wired or wireless connections over various communication protocols.

The client may have an operating system that may execute various applications . In some embodiments an execution environment may execute the applications . In either case the operating system or execution environment may manage execution of the applications by managing resources consumed by the applications as well as controlling the execution.

The resources managed by the operating system or execution environment may be memory resources network resources input output resources processor resources and other resources. The operating system or execution environment may allocate memory perform garbage collection schedule processor availability prioritize and allocate storage resources and other functions. In some embodiments the execution environment may be referred to as a virtual machine.

Tracers and may operate within the operating system or execution environment . The tracers and may monitor the execution of an application and collect various information including performance data operational data debugging data and other types of information. In many cases the tracers and may be exposed to sensitive data that may be processed by an application .

Raw trace data may be the data as collected by the tracers or . The raw trace data may include data elements processed by the applications as well as references to application elements such as function names and other descriptors.

An obfuscator may process the raw trace data to create obfuscated trace data . The obfuscator may obfuscate some or all of the raw trace data using various mechanisms. In some cases only certain elements may be obfuscated while other elements in the raw trace data may remain in a cleartext format.

In some embodiments a source code analyzer may create a set of source code annotations . The source code annotations may be used to decorate the raw trace data with meaningful function names and other information.

The source code annotations may be annotations tags labels or other information that may be derived from source code. Such information may be created by a compiler debugging tool or other source. In some cases source code annotations may be created by a dedicated source code analyzer .

A communications agent may transmit the obfuscated trace data to a remote device for processing. The remote device may be located outside of a secure environment which may be protected by a firewall as well as other security measures. The communications agent may pass the obfuscated trace data through a firewall and network to the remote device .

The remote device may operate on a hardware platform . The hardware platform may be similar to the hardware platform . In some instances the hardware platform may be a virtual machine cloud computing system computing cluster or some other execution environment.

A communications agent may receive obfuscated trace data from the device and store the obfuscated trace data . An analyzer may perform analyses against the obfuscated trace data to generate various analysis results which may be debugging and performance information optimization information or any other type of analysis results.

The obfuscated trace data may contain trace data from multiple devices . In such embodiments the trace data from two or more devices may be combined to create a more comprehensive trace data set than what may be created from merely one device.

In some embodiments results from the remote device may be transmitted to the device for further inspection and use. In such embodiments a lookup database may be populated with obfuscated and raw data elements. The lookup database may be used to translate from obfuscated results to more meaningful results when results are received from a remote device .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment illustrates an interaction between a device in a secure location with a remote device which may be outside the secure location. Trace data are gathered on the device obfuscated and transmitted to the remote device . The remote device may process only the obfuscated data to create certain results which are returned to the device and de obfuscated.

On the device an application may be executed in block . While the application executes trace data may be gathered in block . Some or all of the parameters may be obfuscated using hashing encryption lookup tables randomization or other obfuscation techniques.

The obfuscated data may be transmitted in block to the remote device which may receive the obfuscated data in block .

The remote device may perform analysis on the obfuscated trace data in block to generate analysis results in block . The analysis results may be transmitted in block to the device which may receive the analysis results in block .

The device may de obfuscate the data in block and act on the analysis results in block . The de obfuscating in block may employ a mechanism that determines a raw original value from results computed from obfuscated data.

Embodiment may be an example of a system where units of work may be executed in different environments which may include execution under no instrumentation performance level instrumentation and detailed instrumentation. In many cases an increasing level of instrumentation may cause performance to degrade. However a more complete understanding about an application may combine both performance and detailed instrumentation results. By collecting trace data from two different environments the performance related data may be unaffected by the detailed tracing.

A single unit of work may be analyzed by two different systems. In such systems the performance results and detailed tracing results may be combined for those units of work. Such systems may tag the tracing results with an identifier that may allow an aggregator to match the results to the same unit of work.

In other embodiments a single unit of work may be analyzed only one time. In such systems results from performance and detailed analyses may be combined to give an overall picture without being able to directly compare individual units of work. Such a picture may be statistically significant when the distribution of workloads to each type of analysis may have a statistically normal distribution for example.

A requestor may send a request to a distributor . The request may be a workload to be processed by a cluster of execution environments. In one example the request may be a call to an application programming interface where the application programming interface may be executed by a computing cluster. In another example a request may be a workload within a high performance computing system. In still another example the request may be a function or method call within a computer application.

The distributor may analyze the request to determine how to route the request . In the example of embodiment the request may be routed to an non instrumented system a performance instrumented system or a detailed instrumented system . Other embodiments may have more or fewer systems that may be able to perform the request .

The distributor may have a configuration that may define how the distributor may perform its distribution functions. The configuration may have conditions under which detailed or performance tracing may be performed as well as conditions defining when no tracing may be performed.

The conditions may contain filters that limit instrumentation to only a subset of available requests. The filters or objectives may define parameters relating to the input stream a sampling frequency or other parameters that may define how and when instrumentation may occur. The objectives may define instrumentation granularity such a functional component function process memory object or other level of detail of the data collection. As an example of parameters relating to the input stream the conditions may indicate that instrumentation may be performed on requests that contain a specific variable with a specific value or range of values. An example of other types of configuration definitions may define a sample frequency for requests that may be instrumented.

An non instrumented system may process the requests with little or no tracing or instrumentation. In many cases an non instrumented system may contain minimal instrumentation that may monitor the status of the system or other actions. The non instrumented system may not generate instrumentation results that may be analyzed with data gathered from other instrumented systems.

A performance instrumented system may process a request while gathering performance related metrics. The instrumentation may be designed to have minimal impact on the performance of system so that the performance metrics may be considered accurate.

A detailed instrumentation system may process a request while gathering detailed operational information. In many cases such systems may trace function calls gather data objects passed between processes and functions gather object values as certain points during execution and other data. In many cases the detailed instrumented system may be significantly slower than the performance system .

In the example of embodiment three systems are illustrated as processing the requests . In some embodiments such devices may be identical hardware devices with the same or different software components while in other embodiments different devices with different hardware or software components may be used. Such systems that are not similar may have specialized hardware or software components designed for high performance detailed instrumentation or other function.

The application output may be received from the various systems that execute the request . The application output may be returned to the requestor .

In cases where two systems execute the same request the application output may be compared to determine whether both systems generated the same output. In some embodiments the output may be considered reliable or substantiated when two parallel devices generate the same output. When the output from two systems is not the same one of the output values may be selected the values averaged or some other action taken.

A results combiner may collect trace data from both the performance instrumented system and the detailed instrumented system and store the results in a set of instrumentation results . In some cases the results combiner may match specific execution runs or characteristics between two or more different trace data. Examples of such matching may be found later in this specification.

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be execution environment level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the functions described.

Embodiment illustrates an example of a system that processes requests received over an external network from a requestor . A distributor system may parse the incoming request stream and cause the various execution systems to execute the requests. The application output or response to the request may be passed back to the requestor while any trace data gathered from the execution systems may be stored and used by an analysis system .

Each of the various devices illustrated in embodiment may have a hardware platform. The respective hardware platforms may be similar to the hardware platform in embodiment . The devices may be any type of hardware platform such as a personal computer server computer game console tablet computer mobile telephone or any other device with a programmable processor.

The distributor system may receive and parse an input stream then direct units of work to various execution systems . The distributor system may operate on a hardware platform and contain a distributor that receives work requests via an external interface . The distributor may have a tracing configuration and distribution configuration that define how the units of work may be distributed.

The tracing configuration may define an algorithm conditions or other conditions that may define how and when to collect instrumentation data. The tracing configuration may include granularity sampling rates sample sizes data to be collected and other information. The tracing configuration may also include specific conditions when to trace or not to trace.

Such conditions may evaluate data elements in a request as well as data elements from external sources. For example a condition may cause detailed tracing to happen during evening hours when an input parameter is blue .

The distribution configuration may define conditions for allocating other units of work. The distribution configuration may define a load balancing algorithm for example that allocates work to devices that are lightly loaded while avoiding sending work to devices that are heavily loaded.

A local network may connect the distributor system with various execution systems . The execution systems may have a hardware platform on which an operating system or execution environment may run. An application may be executed on the execution systems to respond to a unit of work and various tracers may collect data while the application processes the unit of work.

In some embodiments the application may execute directly on the operating system . In such embodiments an operating system may have a lightweight tracer for collecting performance related measurements as well as a detailed tracer that may collect detailed information during application execution.

In other embodiments the application may execute in an execution environment . The execution environment may be a virtual machine such as a process virtual machine that may manage execution and provide various support functions such as memory allocation garbage collection process management message passing or other functions. Such execution environments may have a tracer .

The various tracers may be configured using a tracer configuration that may define what information to collect and under what circumstances the information may be collected. In some embodiments the tracer configuration may be sufficient information to cause a single tracer to behave as a performance level tracer or as a detailed tracer.

In some embodiments the distributor may be located within an execution system . In one such embodiment the system may execute an application which may be executed in part by distributing workload items to multiple processing instances. One of the processing instances may be a detailed instrumented instance while another processing instance may be a performance tracing instance. In such a case the operation of embodiment may be performed on a single device.

An analysis system may collect the trace data from various execution systems to gather the results in a centralized trace data . The analysis system may operate on a hardware platform which may have a data store for the trace data as well as a combiner an analyzer and an optimizer .

The analysis system may gather and aggregate trace data from both performance and detailed tracers. The combiner may create a joined set of results. The analyzer may perform various analyses of the results such as reports alerts or other output. The optimizer may generate optimized settings for the application or other optimizations.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

In block an application may be initiated by the distributor and combiner which may cause the application to begin execution in the performance environment in block and in the detailed execution environment in block .

The operations of blocks through illustrate an embodiment where an application may be configured to execute then workload items may be transmitted to the application for processing. In such embodiments the workload items may be data items consumed by the applications. In other embodiments a workload item may be executable commands that may be passed to the various environments. In such embodiments the operations of blocks through may not be performed.

An input stream may be received in block . The input stream may be parsed to identify a work unit in block . The work unit may be a block of data executable code or other workload that may be processed by an execution environment.

A distributor may analyze the work unit in block to determine whether the work unit may be processed using detailed instrumentation or not. If the distributor selects detailed instrumentation in block the workload may be transferred to the detailed instrumentation environment to be executed in block . If the distributor does not select detailed instrumentation in block the workload may be transferred to the performance environment to be executed in block .

In some cases the distributor and combiner may send the same workload item to both the performance environment and detailed execution environment .

The distributor may create an identifier for the work unit. In some cases a work unit may include an identifier within the request such as a sequence number or other identifier that may be used by a requestor to match application results with the request. In some cases a timestamp identification code or other identifier may be created by the distributor and used to correlate results data from two or more trace data gather from different execution environments.

During execution in the performance environment some tracing results may be collected which may be transmitted in block to the distributor and combiner and received in block . Similarly the detailed instrumented environment may generate tracing results that may be transmitted in block and received by the distributor and combiner in block .

The results may be combined in block and stored in block . The process may return to block to handle another unit of work.

An example of a method to combine trace data from a performance environment and detailed instrumented environment may be illustrated in embodiment .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Performance trace data may be received in block and detailed trace data may be received in block . Within each set of results one or more identifiers may be present. Such identifiers may be identified in block .

The identifiers may be any item that may be used to correlate the data between two different tracing operations of an application or work unit. In some cases each unit of work may have an identifier which may be used to match detailed and performance trace data when the unit of work has been executed by both types of tracers in separate runs.

For each identifier in block the performance results may be gathered in block and the detailed results may be gathered in block . The two sets of results may be combined in block and stored in block .

Embodiment may represent a managed computing environment such as a cluster computing system or other system where multiple devices may be used to deliver an application. While a conventional cluster or load balanced environment may be used as the example in embodiment the same principles may be applied to any computational system where workload may be partitioned and distributed to multiple instances threads processors devices or other compute elements.

An application input stream may be sent to a distributor which may partition out work items to various non instrumented systems and instrumented systems . The application output may be produced by either type of systems but the instrumented systems may produce trace data that may be stored in a results database .

The worker systems include the non instrumented systems and instrumented systems . The worker systems may be capable of processing work units which may be any element of an application. In some embodiments the application may receive requests items on an application programming interface then process each request as an individual work item. In such embodiments incoming requests may be data items that are processed individually and independently.

In some embodiments the application may be capable of parallel execution with each work item being an independent computational element that may or may not interact with other work items. In such embodiments incoming requests may be executable code or a combination of executable code and data objects to be processed by the executable code.

The distributor may use a configuration to define how to allocate the work items across the worker systems. The configuration may define load balancing algorithms and parameters as well as the data collection configuration.

The data collection configuration may define how and when data items may be collected by any instrumentation on a worker system. In many cases the data collection configuration may define specific objectives such as data items to collect and conditions for collecting the data items.

The distributor may create a tracer configuration that may configure the instrumentation on an instrumented system to collect specific data. Some embodiments may create specific or customized tracer configurations for each work element. Such embodiments may allow the system to change the instrumentation with a tracer configuration from run to run allowing fine tuned control over the data collection.

Because both the instrumentation and load balancing may be incorporated into the distributor the instrumentation may become a factor in overall load balancing. For example when the load on the system is heavy and there may be few resources available the distributor may be able to reduce the instrumentation so that the overall system performance may not suffer. Similarly the distributor may increase instrumentation during slack periods and there may be an excess of resources.

In systems that may implement a tracer configuration each worker system may be configured as an instrumented or non instrumented system merely by updating the tracer configuration for a particular work item. In some such systems all of the worker systems may be identically configured.

Some worker systems may have additional instrumentation capabilities that other non instrumented systems may not have. For example an instrumented system may have different or additional processors memory storage network connectivity and even additional software resources that may support instrumentation. In such systems the various worker systems may not be identical.

A worker manager may manage the various worker systems by registering the worker systems determining the availability of the worker systems and other functions. In many embodiments the worker manager may deploy a two way authentication mechanism that may allow the distributor to authenticate to the worker systems and vice versa.

The worker manager may collect status information by periodically querying the worker systems or have other regular. The status information may include the capabilities of the worker system which may include the hardware and software capabilities and configuration as well as the current load or capacities of the worker system. Some elements may change in real time such as the availability of the system to process a new request while other elements may be more static such as the hardware configuration.

The authentication mechanisms may help ensure that the various devices are supposed to be communicating with each other. When a worker device authenticates itself to a distributor the distributor may rely on the authentication to assure that the worker is not a malicious device. When the distributor authenticates itself to the worker device the worker device may rely on the authentication to assure that the distributor has the permission or authority to send work to the worker device. The authentication mechanisms may also be deployed for other scenarios including instrumentation as a service scenarios.

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be execution environment level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the functions described.

Embodiment illustrates an environment in which multiple worker systems may perform portions of an application as determined by a distributor device. The distributor may receive a stream of workload items divide the incoming stream into units of work determine which worker device may process each unit of work and cause those units of work to be performed.

The distributor may also determine what type of instrumentation may be performed on a given unit of work. The instrumentation may include various types of tracing data collection performance monitoring or other data that may be used for diagnosis debugging administrative monitoring optimization or other uses.

The instrumentation may be configurable by the distributor . In some cases the distributor may be capable of routing work units to worker devices that may be preconfigured to perform specific types of tracing or instrumentation. For example one of the instrumented systems may be preconfigured to perform a specific set of data collection in addition to executing a work unit. In such an example the distributor may determine when to send a work unit to the instrumented system and when to send another work unit to a worker which may not have instrumentation configured.

In another example the distributor may transmit a configuration file or other descriptor to an instrumented system where the configuration file may contain specific data items to collect tests to perform or other data collection activities. In such an embodiment the instrumentation or tracers on the instrumented systems may be configurable. In some cases such a system may be able to execute a work unit with little or no instrumentation then switch to a high level of instrumentation for the next work unit as defined in a configuration file.

Each of the various devices illustrated in embodiment may have a hardware platform. The respective hardware platforms may be similar to the hardware platform in embodiment . The devices may be any type of hardware platform such as a personal computer server computer game console tablet computer mobile telephone or any other device with a programmable processor.

The distributor may have a hardware platform on which various software components may operate. A distributor may receive an incoming workload stream from a load receiver and determine which worker device will execute the work unit. The distributor may use a load balancing configuration that may define load balancing objectives algorithms or other definition for managing a quality of service or other factor. The distributor may refer to a worker database that may include the availability and status of the various worker devices.

The distributor may balance the workload over multiple devices including instrumented systems and general workers . The workload balancing may use multiple devices in parallel to process a workload that may be larger than the capacity of a single device. For example a large web scale application may be processed by many devices which may scale into several hundred server computers in some cases. The load balancing aspect of the distributor may attempt to divide the workload and distribute the workload to available devices.

A tracer configuration may define a set of instrumentation objectives which may include data to be collected sample rates and many other factors.

In many cases the instrumentation objectives may be in tension with the load balancing objectives. In general instrumentation and data collection may come at some computational cost meaning that as the instrumentation is increased the performance of a system may decrease. In a high speed high throughput environment the distributor may balance the instrumentation objectives against the processing capacity to handle the incoming workload. In some instances the distributor may scale back the instrumentation objectives during high loads so that a quality of service metric for the overall system may be met. In other instances the distributor may allow the quality of service metric to be missed so that instrumentation objectives may be met. The decisions made by the distributor may be defined in the various configuration files.

A tracer manager may manage the instrumentation to generate the overall objectives for data collection. The tracer manager may cause different data elements to be collected from various work units or instrumented systems then collect the data. In some cases the tracer manager may perform first level aggregation summaries or other initial processing.

The tracer manager may use an artificial load generator to create or modify work units for testing and data collection. For example the artificial load generator may create a work unit that stresses a specific portion of an application. When such a work unit is performed the instrumentation may collect data for the work unit. Such a work unit may produce application results that may be discarded by the instrumented system .

The distributor may include a worker status collector that may communicate with each worker device to determine a current status. The status may indicate whether the device may be available to accept work units. In some cases the status may include statistics such as excess capacity current workload or other performance metrics.

A worker manager may manage available worker devices by adding and removing devices into a pool of managed devices. The worker manager may allow new devices to connect authenticate and be added to the pool of managed devices. An administrator may use the worker manager to monitor individual devices configure devices and add and remove devices to the pool.

In many embodiments a worker manger may issue authentication keys to worker devices. The authentication keys may be part of a public private encryption key system where the private key may be stored on a device and used to secure a communication and a public key transmitted to a receiving device to decrypt the communication. Such systems may be one example of a system for authenticating between devices and other embodiments may use other systems.

The workers may operate on a hardware platform to execute an application within an execution environment . The application may be a preinstalled set of executable code that processes work items from the distributor . In some cases the application may execute within an execution environment which may be an operating system virtual machine framework or other supporting software component.

The workers may have an authentication key which may be used to authenticate communication with the distributor . The key may be any type of authentication component such as a public private encryption key set or other component.

The instrumented system may be similarly configured as the workers . A hardware platform may support an execution environment that executes the application . The instrumented system may include a tracer which may or may not be configurable by the distributor during execution. The instrumented system may also include a key for authentication with the distributor .

In some embodiments the instrumented system may be identical hardware and software configuration as the workers . Other embodiments may have different hardware or software configurations between the instrumented system and workers .

The analysis system may have a hardware platform where a data collector may collect trace data from various tracers. An analyzer may process the tracer for analysis optimization summarization or other functions.

The example of the distributor and other components illustrate devices that may have multiple functions. In different embodiments each of the various illustrated components may be deployed on a separate device or group of devices. For example the worker manager worker status collection tracer manager and other functions may be deployed on individual devices or groups of devices.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment illustrates an operating sequence for establishing and administering a pool of worker resources in block then an operational mode in block for parsing an input stream and distributing work units to the worker resources. In the example of embodiment the worker resources may be individual devices but in other embodiments the worker resources may be any resource used to process work units. In some cases the worker resources may be sub device resources such as processors schedulers threads or other objects. In other cases the worker resources may be multiple devices acting together such as clusters managed services or other resource groups.

In an administrative mode in block the various execution environments may be identified in block . The execution environment may refer to any resource used for processing a work unit. In many cases the execution environment may be a device processor or other computation worker.

For each execution environment in block an attempt may be made to communicate and authenticate the environment in block . If the authentication is not successful in block the environment may be marked as unavailable in block .

After successfully authenticating in block the configuration and availability of the environment may be tested in block . If the configuration and availability are not OK in block the environment may be marked as unavailable in block . When the environment has successfully authenticated in block and the configuration and availability are OK in block the execution environment may be marked as available in block .

The process of blocks may represent an administrative function that may be performed prior to distributing work to the various execution environment. In some cases the process of blocks may be performed in parallel with the operational mode of block . In such cases the operations of the administrative mode may be an ongoing and repeated check of the various execution environments.

The operational mode of block may begin by receiving tracer configuration and load balancer configuration in block .

The input stream may be received in block . The input stream may be parsed in block to identify work items. For a given work item a determination may be made in block identifying a device to process the work item. In some cases a tracer configuration may be created in block that defines any data collection parameters. Once the determination is made in block the work item may be transmitted to the selected execution environment in block . The process may return to block to process the next work item.

A customer premise may execute an application under control of a user. The customer premise may be a physical premise such as a building or business to which the user may have access. In some cases the customer premise may include one or more computers that may be owned by and located at a third party s premise but under the control of the user. An example of such a system may be a cloud hosted execution system where a user may purchase computing resources. The resources may be owned by a third party but the user may control how those resources may be deployed.

The remote service may receive work items and execute those work items using an instrumented environment . The instrumented environment may have various hardware and software components that may capture various trace data while a work item executes. In some cases the instrumented environment may include tools measuring algorithms probes and other components that may be difficult or costly to install manage execute or otherwise deploy.

Within the customer premise an application input stream may be passed to a distributor . The distributor may parse work items from the input stream and pass the work items to various execution environments . The output of the execution environments may be application output .

The distributor may transfer some or all of the work items to an instrumented environment which may be part of a remote service . In some cases multiple instances of the instrumented environment may be used.

A load generator may create test loads that may be injected into the input stream . The test loads may be data that may be processed by the instrumented environment to exercise an application. In many cases the test loads may exercise an application in a more comprehensive manner than a typical or random input stream. Such test loads may perform unit tests or other tests that may be designed to exercise various corner cases and conditions. In some cases the test loads may subject an application to large loads that may stress the performance of the system. Such test loads may help identify performance bottlenecks and measure overall throughput or response time during peak loading times.

The remote service may include an authentication authorization and accounting system which may manage various administrative aspects of the remote service . An administrative user interface may permit a user to create an account define a payment mechanism and administer the instrumented environments .

An instrumentation marketplace may be a website or other interface through which a user may browse preconfigured instrumented systems and preconfigured load generators . Each of the various preconfigured systems may be customized for specific types of data collection. Some preconfigured systems may have additional features algorithms or capabilities that may not be available on other preconfigured systems. As such some preconfigured systems may have different cost structures than other preconfigured systems.

A user may be able to select a preconfigured instrumented system and preconfigured load generator as a starting point for configuring a test regime for a given application. In some embodiments a user may select a preconfigured system then add remove or edit various settings to achieve a specific objective.

In some embodiments a user may be able to save a preconfigured instrumented system in the instrumentation marketplace for reuse. In some such embodiments a third party may be able to upload their own instrumented system for sale in the instrumentation marketplace .

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be execution environment level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the functions described.

Each of the various devices illustrated in embodiment may have a hardware platform. The respective hardware platforms may be similar to the hardware platform in embodiment . The devices may be any type of hardware platform such as a personal computer server computer game console tablet computer mobile telephone or any other device with a programmable processor.

Embodiment may illustrate an environment in which instrumentation systems may be provided from a remote service then added to the computational pipeline of a user s system. The instrumentation system may include load generators as well as data collectors which may operate in concert with a user s application to collect various data about the application during execution.

A user may interact with the remote service through an administrative user interface. The user may be able to perform various administrative tasks such as establishing an account and a method for payment as well as to select and configure test components that may integrate into the user s application. The remote service may include an instrumentation marketplace in which a user may browse various preconfigured load generators and preconfigured instrumented workers. Once selected the user may be able to configure or customize a component then manage how the component may be deployed.

A user s system may include a workload distributor and various workers connected within an internal network . The workload distributor may receive units of work for an application then distribute the work units to various workers . An example of such a system may be a cluster work environment.

In the example of embodiment the user s system is illustrated as multiple devices that each may contribute to the execution of a large application. In other embodiments the components may be deployed on a single device.

The distributor may operate on a hardware platform that may include a distributor . The distributor may be a software component that may receive an input stream parse the input stream into work units then cause the work units to be executed on the various workers .

The distributor may include a configuration which may include both load balancing and instrumentation objectives. The configuration may also include information that may be used to distribute some or all of the work units to one or more instrumented workers which may execute the workloads and collect data about the execution.

An authentication system may enable the distributor to establish trusted and in some cases secure communications with remote system components.

The workers may include a hardware platform and an execution environment that may execute the various work items. The workers in embodiment may be connected to the distributor through an internal network . In many systems connections within an internal network may be considered trusted and secure because of a firewall and other security measures. As such the workers may be deployed without an authentication system.

The firewall may define a boundary between devices directly under a user s control and devices or services that may be provided by a third party. In some embodiments the various instrumentation components may be available across an external network which may include the Internet. In many cases the various remote services may be made available to many different users.

A third party may provide load generation and instrumentation services to the user by establishing a connection with a distributor within the user s system.

The distributor may operate at a location in an application where instrumentation may be desired. In some cases the distributor may be a function call or other instruction that may be inserted into an application. Such an instruction may be added to a user s application by a programmer.

The instrumented workers may execute a portion of an application as defined by the distributor . The instrumented workers may have a hardware platform on which an execution environment may execute work units from the distributor . While executing the work unit a tracer may collect data which may be analyzed by an analyzer . Not shown in embodiment may be a separate device that may collect and store trace data.

The instrumented workers may include an authentication system which may include a key . The key may be any type of token key passphrase or other item that may be used to authenticate the instrumented worker to the authentication system on the distributor . In some cases the key may be a set of pubic private encryption keys.

A load generator may be another instrumentation component that may be configured and deployed as a remote service. The load generator may generate artificial loads or other inputs that may be performed by the application under test. In some cases the load generator may create unit tests or other inputs that may exercise an application. In other cases the load generator may generate large loads that may exercise an application to determine performance bottlenecks or other limits to performance.

The load generator may have a hardware platform with a load generator . A configuration may define how the load generator may operate including the type of data to generate along with the timing frequency and other operational aspects.

An authentication system may authenticate the load generator to the distributor . The authentication system may include one or more keys for communicating with the distributor .

An administrative server may perform many of the setup configuration and management operations to deploy various instrumented workers and load generators . The administrative server is illustrated as operating on a single hardware platform although other embodiments may deploy the various components on different platforms.

An administrative user interface may be a website application or other user interface through which a user may perform many administrative tasks. A user may establish an account and create various authentication components using an authentication and authorization system . A key generator and key database may respectively create and store the various authentication keys that may be deployed to the instrumentation components and the user s system.

An accounting system and payment system may be a mechanism through which a remote service may collect monies for operation. The accounting system may identify each usage of the various instrumentation components and the payment system may transfer money from the user to the service provider in exchange for the use of the system.

Many different payment schemes may be deployed to bill a user for the remote service. For example a monthly subscription may pay for one or more instrumented systems. In another example the instrumented systems and load generator may be billed on a processor cycle basis per compute hour per storage consumed or other basis.

An instrumentation marketplace may be an interface through which a user may browse various preconfigured instrumented workers and preconfigured load generator . The user may then be able to select and further configure a preconfigured component before deploying the component.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment illustrates a method by which a user may set up and deploy instrumentation systems. The instrumentation systems may be instrumented worker devices load generators or other components.

A user may begin a session in block establish a user account in block and establish a payment method in block . The user account may allow the user to log in at a later time and add remove and edit the operation of the various instrumentation systems. The payment method may be the mechanism through which payment may be made to a third party that provides the instrumentation services.

The user may browse preconfigured instrumentation systems in block . The preconfigured systems may have varying capabilities. For example one instrumented execution environment may have performance monitoring capabilities while another instrumented execution environment may have process or call tracing capabilities. In another example one load generator may be configured for producing HTTP requests while another load generator may be configured for TCP IP requests.

After selecting an instrumentation system in block data to be collected may be defined in block as well as various collection parameters and logic in block . The configuration variables defined in blocks and may be stored in block to enable an instrumentation system to be deployed in block .

The data to be collected in block may define specific parameters types of parameters or other information regarding data collection. In the case of a load generator the parameters of block may define the load to be produced which may be coordinated with the data collection performed by a corresponding instrumented execution environment.

The collection parameters and logic defined in block may define the conditions under which data may be collected. The conditions may be events parameter values timeframe sampling rates or other definitions that may define when data may be collected. In some cases the conditions may be interpreted by a distributor to determine which work units to transmit to an instrumented execution environment.

After defining the data to be collected and when and how the data may be collected the configuration may be stored in block . In some cases the stored configuration may be added as another preconfigured instrumented system in the instrumentation marketplace. Such a storage may be made accessible to the public at large or may be restricted to only the user who created the configuration.

If another system is to be configured in block the process may return to block . Once all systems are deployed a user may browse and view deployed systems in block . The user may select a system in block and if the user wishes to make changes to the system in block the process may return to block .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment may illustrate one example of a process that may be performed to deploy an instrumented system. The instrumented system may be a load generator instrumented worker or other component.

A configuration file for the instrumented system may be created in block and the instrumented system may be instantiated in block . In some embodiments each instrumented system may be a virtual machine or other component that may be instantiated and managed within a datacenter environment.

Authentication keys may be created for the system in block and the keys may be transmitted to the system in block . In blocks and any protocols or other configuration may be performed to connect to a distributor or to an administrative system.

An attempt may be made in block to connect to a distributor on a customer s system. If the connection is not successful in block the distributor may be installed and configured by identifying the instrumentation point in block and adding the distributor to the customer system in block . In many cases a programmer may add a function call or make other changes to the customer s application to add the distributor. The distributor may be configured in block to communicate with the instrumented system. The process may proceed to block .

After the distributor is configured in block or there is success in connecting in block the instrumentation system may be added to the distributor as an available system in block . The authentication mechanism may be established in block and the system may start operation in block .

The foregoing description of the subject matter has been presented for purposes of illustration and description. It is not intended to be exhaustive or to limit the subject matter to the precise form disclosed and other modifications and variations may be possible in light of the above teachings. The embodiment was chosen and described in order to best explain the principles of the invention and its practical application to thereby enable others skilled in the art to best utilize the invention in various embodiments and various modifications as are suited to the particular use contemplated. It is intended that the appended claims be construed to include other alternative embodiments except insofar as limited by the prior art.

