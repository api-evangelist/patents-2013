---

title: Systems and methods for metadata-driven command processor and structured program transfer protocol
abstract: Systems and methods for facilitating on-demand delivery and processing of one or more programs and program-compatible applications on a plurality of different machines. In an embodiment, a metadata-driven command processor on a machine sends a request for a booting program and application to an agent. In response to the request, the agent invokes a resource to generate a booting program dataset that defines the booting program and an application dataset that defines the application, generates a response dataset comprising two or more nested datasets, wherein the two or more nested datasets comprise at least the booting program dataset and the application dataset, and sends the response dataset to the metadata-driven command processor. The metadata-driven command processor copies the booting program dataset and the application dataset into a process dataset comprising two or more nested datasets, and processes the first process dataset to execute the booting program and application on the machine.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09336013&OS=09336013&RS=09336013
owner: Automatic Data Capture Technologies Group, Inc.
number: 09336013
owner_city: Irvine
owner_country: US
publication_date: 20130314
---
This application claims priority to U.S. Provisional Patent App. No. 61 762 779 filed on Feb. 8 2013 and titled Systems and Methods for Metadata driven Command Processor MCP and Structured Program Transfer Protocol SPTP and further claims priority to U.S. Provisional Patent App. No. 61 783 362 filed on Mar. 14 2013 and titled Systems and Methods for Metadata driven Database Application Framework both of which are hereby incorporated herein by reference in their entireties as if set forth in full.

The invention is generally directed to the on demand delivery and processing of codeless programs and program compatible applications on any machine.

Conventionally in order to execute an application on a machine it must be specifically designed and implemented for that particular machine. For example different versions of a software application must be created to work on both the Microsoft Windows operating system and Mac OS . Virtual machines have mitigated this issue to an extent. Specifically a virtual machine is a software simulation of an abstract or real machine that is generally different from the machine on which it is being executed. A virtual machine allows a software application designed for the virtual machine to be run on each machine on which the virtual machine is installed and executed regardless of the machine s particular architecture. However currently there is no way to allow programs and applications to be transferred on demand from machine to machine while preserving their processing or execution states across those different machines. In addition there is currently no way to execute a program and application on any machine e.g. from an appliance controller e.g. home thermostat to a mobile device e.g. smart phone . For instance conventional home thermostats cannot act as a virtual machine running a Windows application.

Accordingly systems and methods are disclosed for on demand transfer and delivery and processing of programs and program compatible applications on any machine and across different machines.

In an embodiment a method for facilitating on demand delivery and processing of one or more programs and program compatible applications is disclosed. The method comprises using at least one hardware processor by a first metadata driven command processor on a first machine sending a first request for a booting program and application to an agent wherein the first request comprises an identification of a resource in response to the first request by the agent invoking the identified resource to generate a booting program dataset that defines the booting program and an application dataset that defines the application generating a first response dataset wherein the first response dataset comprises two or more nested datasets wherein the two or more nested datasets comprise at least the booting program dataset and the application dataset and sending the first response dataset to the first metdata driven command processor and by the first metadata driven command processor copying the booting program dataset and the application dataset into a first process dataset comprising two or more nested datasets and processing the first process dataset to execute the booting program and the application on the first machine.

In an additional embodiment a system for facilitating on demand delivery and processing of one or more programs and program compatible applications is disclosed. The system comprises a first machine comprising at least one hardware processor and a first metadata driven command processor and an agent wherein the first metadata driven command processor sends a first request for a booting program and application to the agent wherein the first request comprises an identification of a resource wherein in response to the first request the agent invokes the identified resource to generate a booting program dataset that defines the booting program and an application dataset that defines the application generates a first response dataset wherein the first response dataset comprises two or more nested datasets wherein the two or more nested datasets comprise at least the booting program dataset and the application dataset and sends the first response dataset to the first metdata driven command processor and wherein the first metadata driven command processor copies the booting program dataset and the application dataset into a first process dataset comprising two or more nested datasets and processes the first process dataset to execute the booting program and the application on the first machine.

In an additional embodiment a non transitory computer readable medium is disclosed. The medium has stored thereon a first metadata driven command processor comprising a first set of instructions and an agent comprising a second set of instructions wherein the first metadata driven command processor sends a first request for a booting program and application to the agent wherein the first request comprises an identification of a resource wherein in response to the first request the agent invokes the identified resource to generate a booting program dataset that defines the booting program and an application dataset that defines the application generates a first response dataset wherein the first response dataset comprises two or more nested datasets wherein the two or more nested datasets comprise at least the booting program dataset and the application dataset and sends the first response dataset to the first metdata driven command processor and wherein the first metadata driven command processor copies the booting program dataset and the application dataset into a first process dataset comprising two or more nested datasets and processes the first process dataset to execute the booting program and the application on the first machine.

A metadata driven command processor MCP and structured program transfer protocol SPTP are disclosed in various embodiments.

For purposes of understanding the present disclosure the following terms should be defined as indicated below 

 Machine An electronic device capable of performing one or more computing processes receiving data from one or more other electronic devices e.g. other machines and or sending data to one or more other electronic devices e.g. other machines . Examples of machines include without limitation a server personal computer PC laptop computer tablet in vehicle media entertainment and or control system smart phone feature phone appliance mechanical controller sensor thermostat etc.

 Agent A hardware or software component or module that acts for a user or program in an agency relationship. Examples of agents include without limitation a central processing unit CPU microprocessor operating system OS native Hypertext Markup Language HTML container web browser window web service database server etc.

 Statement A string of characters that are constructed in the syntax of a scripting language and which can be executed in their entirety by a compatible resource to perform a computing process. Examples of computing processes which may be performed by executing a statement include without limitation rendering a display manipulating and or retrieving data printing a document invoking an application programming interface API controlling a mechanism etc.

 Resource A computer program that transforms statements written in a high level scripting language to a lower level language that can be executed on a machine to manipulate and or retrieve data render display content etc. Examples of resources include without limitation a data engine layout and or rendering engine machine control and or printing engine etc.

 Remote Resource A resource on a remote machine that can be invoked directly by an agent on another machine. For example two or more machines may be separated by one or more networks such as the Internet rendering each of the machines remote from the other. An example of a remote resource includes without limitation a web service.

 Request A message sent to a resource or remote resource via a communication protocol that is intended to elicit a responding message. An example of a request includes without limitation a Hypertext Transfer Protocol HTTP request.

 Response A message returned from a resource or remote resource via a communication protocol in response to a request e.g. after executing the request . Examples of responses include without limitation an error message user event SQL result set etc.

 Metadata based Method A metadata based subroutine that is associated with a program and includes one or more single line commands method steps which are interpreted by the disclosed metadata driven command processor to manipulate datasets loaded in a memory on a machine and invoke machine resources.

 Program A static set of instructions that are executed by a command processor to control the behavior of a machine. The execution of a program is a series of actions following the set of instructions that it contains. Each instruction may produce an effect that alters the state of a machine according to the instruction s predefined meaning. A program manages and integrates a machine s capabilities but typically does not directly apply in the performance of tasks that benefit the user or machine. An example of a program includes without limitation the Microsoft Windows operating system.

 Application Computer software that applies the power of a particular program to a particular purpose. A command processor serves the program which serves the application which serves a specific purpose. Examples of applications include without limitation enterprise software accounting software office suites graphics software media players etc.

 Dataset A collection of data presented in tabular form. Each column in a dataset may represent a particular variable. Each row in a dataset may correspond to a given member of the dataset in question. A dataset may comprise data for one or more members corresponding to the number of rows.

 Dataset Element Any value in a dataset. A dataset element can be referenced by a combination of its column position column index and row position row index within the dataset.

 Nested Dataset A dataset stored as a dataset element within another dataset. Nested datasets are one to many relationships embodied in a single parent dataset memory store.

 Metadata There are two types of metadata. Structural metadata is data about the design and specification of data structures. Structural metadata cannot be data about data since at design time the application contains no data. Rather structural metadata is data about the containers of data. Descriptive metadata is data about data content. This data content is the individual instances of application data.

 Communication Protocol A system of digital message formats and rules for exchanging messages in or between computing systems e.g. in telecommunications . Protocols may include signaling authentication and error detection and correction capabilities. Each message has an exact meaning intended to provoke a defined response by the receiver. The nature of the communication the actual data exchanged and any state dependent behaviors are defined by a technical specification or communication protocol standard. Examples of conventional communication protocols include without limitation HTTP HTTP Secure HTTPS File Transfer Protocol FTP etc.

 Command Processor A software shell with the primary purposes of 1 loading or booting another program and 2 processing commands from the launched program. Processing of these commands can include without limitation data transfers event handling display renderings and machine to machine communications. Examples of conventional command processors include without limitation the Microsoft Disk Operating System MS DOS command line tools e.g. command.exe or cmd.exe Unix or Linux shells etc.

 Command A subroutine within a command processor that can be invoked by an agent or by another command and which executes an instruction set. Certain commands can be referenced by a command code.

 Scripting Language A programming language that supports the writing of scripts. Scripts are programs written for a software environment that automate the execution of tasks which alternatively could be executed one by one by a human operator. Environments that can be automated through scripting include without limitation software applications web pages within a web browser shells of operating systems and several general purpose and domain specific languages such as those for embedded systems. Examples of scripting languages include without limitation Structured Query Language SQL HTML Printer Control Language PCL eXtensible Markup Language XML Computer Numeric Control CNC etc.

 Booting The process of loading and executing bootstrap software by a computer during the start up process. Booting is a chain of events that start with execution of hardware based procedures that may then hand off to firmware and software which is loaded into memory. Booting often involves processes such as performing self tests and loading configuration settings Basic Input Output System BIOS resident monitors a hypervisor an operating system and or utility software.

 Event An action that is initiated outside the scope of a command processor and that is handled by the command processor. Typical sources of events include users e.g. via keystroke s i.e. pressing one or more keys on a keyboard and software or hardware devices e.g. a timer . A computer program that changes its behavior in response to events is said to be event driven often with the goal of being interactive.

 Instruction Set A collection of computer instructions including native data types instructions registers addressing modes memory architecture interrupt and exception handling and external Input Output I O . Instructions are in the form of a programming language i.e. source code or machine language i.e. machine code that is compatible with a machine resource. Source code is written using some human readable computer language usually as text. The source code of a program is specially designed to facilitate the work of computer programmers who specify the actions to be performed by a computer primarily by writing source code. The source code is automatically translated at some point to machine code that the computer can directly read and execute.

The disclosed metadata driven command processor and structured program transfer protocol facilitate on demand delivery and processing of codeless programs and program compatible applications on virtually any machine from an appliance controller e.g. home thermostat to a smart device e.g. smart phone . The disclosed embodiments also facilitate the transfer and delivery of programs and applications on one machine e.g. tablet PC to another machine e.g. in vehicle navigation system via a communications interface while maintaining the process state of the programs and or applications. The request delivery and transfer of program and application metadata between machines are facilitated by a novel structured program transfer protocol for communications. The applications can be as simple as an on off switch or as complex as client server business solutions e.g. enterprise resource planning ERP customer relationship management CRM etc. .

For example the disclosed metadata driven command processor and structured program transfer protocol can facilitate codeless rapid development and on demand delivery of database applications on end user devices such as smart phones tablets PCs and in vehicle navigation systems. The database application may be a spreadsheet web site client server business solution etc. From the database application s metadata the metadata driven command processor can dynamically generate statements in various scripting languages e.g. HTML SQL XML PCL executed on the end user device EUD or on a remote resource e.g. web service to render a user interface retrieve and manipulate database content and invoke EUD specific functionality e.g. print documents capture signatures scan barcodes read credit cards etc. .

The metadata driven command processor may have functionality and purpose similar to that of MS DOS whereas the programs may have functionality and purpose similar to Microsoft Windows and the applications may have functionality and purpose similar to Windows based applications. However the disclosed systems and methods are metadata driven to provide nearly universal applicability across all machines. The instruction set within the metadata driven command processor is minimal and can be embedded within a machine s operating system chipset or other machine component. Alternatively or additionally the instruction set can be embedded within a container software application e.g. web browser that is installed on the machines.

A structured program transfer protocol is also disclosed. The structured program transfer protocol is a type of communication protocol that defines the dataset schema for sending a type of request SPTPRequest and receiving programs applications data and execution state collectively as a type of response SPTPResponse from one machine to another.

Agent may launch metadata driven command processor on machine passing it a booting SPTPRequest that specifies the source of the booting program and application to be processed. Metadata driven command processor may send a SPTPRequest to agent and receive a SPTPResponse from that agent.

The SPTPRequest may identify the resource needed to execute the SPTPRequest. If the resource identified in the SPTPRequest is on a remote machine e.g. machine then the SPTPRequest also identifies the agent e.g. agent on the remote machine that can communicate with the resource e.g. resource on the remote machine. In this case agent forwards the SPTPRequest e.g. SPTPRequest to the remote agent e.g. agent .

If the SPTPRequest specifies a request to send a booting program and application then agent or the identified remote agent e.g. agent invokes the identified resource or remote resource e.g. resource to generate the booting Program and Application datasets. The invoking agent generates a SPTPResponse that includes a structured version of the booting Program and Application datasets e.g. Program dataset and Application dataset . If the SPTPResponse is generated by a remote agent e.g. agent then the remote agent returns the SPTPResponse e.g. SPTPResponse to agent . Agent returns the SPTPResponse to metadata driven command processor for processing. Metadata driven command processor copies the contents of the Program and Application datasets included in the SPTPResponse to Program dataset and Application dataset nested in Process dataset and continues processing.

If the SPTPRequest specifies a request to send an additional program compatible application then agent or the identified remote agent e.g. agent invokes the identified resource or remote resource e.g. to generate the additional program compatible application datasets. The invoking agent generates a SPTPResponse that includes a structured version of the additional program compatible application datasets e.g. Application dataset . If the SPTPResponse is generated by a remote agent e.g. agent then the remote agent returns the SPTPResponse e.g. SPTPResponse to agent . Agent returns the SPTP to metadata driven command processor for processing. Metadata driven command processor copies the contents of the Application dataset included in the SPTPResponse to Application dataset nested in Process dataset and continues processing.

If the SPTPRequest specifies a request to execute a statement included in the SPTPRequest then agent or the identified remote agent e.g. agent sends the statement e.g. statement or statement to identified resource or a remote resource e.g. for execution. The executing resource may return a response e.g. response or response to the invoking agent. The invoking agent generates a SPTPResponse that includes a structured version of the resource response e.g. Data dataset . If the SPTPResponse is generated by a remote agent e.g. agent then the remote agent returns the SPTPResponse e.g. SPTPResponse to agent . Agent returns the SPTPResponse to metadata driven command processor for processing. Metadata driven command processor copies the contents of the Data dataset included in the SPTPResponse to Data dataset nested in Process dataset and continues processing.

If the SPTPRequest specifies a request to send a program loaded application s and current execution state from a remote machine e.g. machine then agent forwards the SPTPRequest e.g. SPTPRequest to the identified remote agent e.g. agent . The identified remote agent e.g. agent invokes the remote metadata driven command processor e.g. metadata driven command processor to return its Process dataset e.g. Process dataset which includes its program loaded application s and current execution state e.g. Message dataset Program dataset Application dataset and Data dataset . The remote agent generates a SPTPResponse that includes the Process dataset and returns the SPTPResponse e.g. SPTPResponse to agent . Agent returns the SPTPResponse to metadata driven command processor for processing. Metadata driven command processor copies the contents of the Process dataset included in the SPTPResponse to its Process dataset which includes the program loaded application s and current execution state within its nested Message dataset Program dataset Application dataset and Data dataset . Metadata driven command processor continues program processing from the execution state that existed on the remote machine.

In an embodiment metadata driven command processor generates or updates Process dataset from SPTPResponse or receives Process dataset through SPTPResponse transferred from Process dataset . illustrates SPTPResponse in more detail according to an embodiment. Process dataset generated by metadata driven command processor may contain the same defined schema as SPTPResponse or SPTPResponse . Thus the elements of Process dataset are simply populated from the elements of the dataset in SPTPResponse or SPTPResponse .

SPTPResponse dataset SPTPResponse dataset and Process dataset may each comprise a single row having four nested datasets Message dataset Program dataset Application dataset and Data dataset . In turn Program dataset may comprise a single row containing seven nested datasets Methods dataset MethodSteps dataset Transfers dataset TransferColumns dataset TransferConditions dataset TransferFormulas dataset and DatasetColumns dataset .

If the SPTPResponse includes a booting program and application metadata driven command processor generates Process dataset from SPTPResponse and then identifies a MethodID dataset element in a row of Methods dataset which is associated with booting. Next metadata driven command processor identifies one or more rows in the MethodSteps dataset that are associated with the identified MethodID dataset element. Metadata driven command processor processes these one or more rows by invoking a command that is associated to a CommandCode dataset element in each row. After completion of all the commands associated with applicable rows identified from the MethodSteps dataset metadata driven command processor maintains its state and waits for one of its commands to be invoked by agent based on a user event machine event or request from a remote agent.

 2 Conditionally append update or delete a dataset row based on the current value s of element s in one or more other datasets.

 3 Build a statement from the current values of dataset elements that is specific to a scripting language.

 4 Invoke an agent or remote agent to execute a statement via a compatible resource on the machine of the invoked agent. The response from the resource may be converted by the agent into a SPTPResponse that is processed by the metadata driven command processor.

 5 Transfer the Process dataset within the metadata driven command processor to a remote agent. This allows the remote agent s metadata driven command processor to continue program processing from its current state.

As mentioned above a dataset structure for an embodiment of a structured program transfer protocol is illustrated in . In this case the dataset structure includes nested relationships. SPTPRequest and SPTPResponse are both single row datasets. In an embodiment Message dataset Program dataset and Application dataset are each single row nested datasets within SPTPResponse and Data dataset is a multi row nested dataset within SPTPResponse .

In the illustrated embodiment Methods dataset MethodSteps dataset Transfers dataset TransferColumns dataset TransferConditions dataset TransferFormulas dataset and DatasetColumns dataset are all multi row nested datasets within Program nested dataset . Program dataset may also include one or more program specific nested datasets . The schema of Application dataset and its nested one or more datasets is program specific and may vary. Similarly the schema of Data dataset is statement specific and may vary.

In the illustrated embodiment of the column index CI of SPTPResponse is referred to as DSI dataset index . The column index of Program dataset and Application dataset is referred to as NDSI nested dataset index . The row index RI is zero for all single row datasets. Datasets may be created as two dimensional arrays. Elements within the datasets may be referenced using x y notation where x is the row index and y is the column index. For example the dataset element RequestType of an SPTPRequest in the illustrated embodiment of Table 1 may be referenced in an instruction set as SPTPRequest 0 0 . While row and column indexing are illustrated herein as zero based other index bases e.g. one based indexing are possible.

The following description illustrates a non limiting embodiment of a structured program transfer protocol request. The structured program transfer protocol request may comprise a single row SPTPRequest dataset which may be sent from an agent e.g. agent to a metadata driven command processor e.g. MCP from a metadata driven command processor e.g. MCP to an agent e.g. agent or from an agent e.g. agent to a remote agent e.g. agent or agent . The SPTPRequest dataset includes structured dataset elements that any metadata driven command processor agent or remote agent can interpret and process. In this embodiment the dataset comprises the columns illustrated in Table 1 

The following description illustrates a non limiting embodiment of a structured program transfer protocol response. The structured program transfer protocol response may comprise a single row SPTPResponse dataset which may be returned to a metadata driven command processor e.g. MCP from an agent e.g. agent or to an agent e.g. agent from a remote agent e.g. agent or agent in response to a SPTPRequest. In an embodiment this dataset contains four columns. Each dataset element may contain a specific nested dataset as shown in Table 3 

In an embodiment the Message dataset is a single row dataset with the columns illustrated in Table 4 

In an embodiment the Program dataset is a single row dataset with the seven defined columns illustrated in Table 6. It may also include one or a plurality of program specific columns beginning at NDSI 7. Each dataset element may contain a specific nested dataset as shown below 

In an embodiment the Methods dataset nested within the Program dataset contains one or more rows with the columns illustrated in Table 7 

In an embodiment the MethodSteps dataset nested within the Program dataset contains one or more rows with the columns illustrated in Table 9 

In an embodiment the Transfers dataset nested within the Program dataset contains one or more rows with the columns illustrated in Table 11 

In an embodiment the TransferColumns dataset nested within the Program dataset contains one or more rows with the columns illustrated in Table 13 

In an embodiment the TransferConditions dataset nested within the Program dataset contains one or more rows with the columns illustrated in Table 15 

In an embodiment the TransferFormulas dataset nested within the Program dataset contains one or more rows with the columns illustrated in Table 17 

In an embodiment the DatasetColumns dataset nested within the Program dataset contains one or more rows with the columns illustrated in Table 19 

In an embodiment the Application dataset nested within the SPTPResponse dataset contains a single row with a variable number of columns that are program specific as shown in Table 20. Each dataset element may contain a nested dataset that is program specific.

In an embodiment the Data dataset nested within the SPTPResponse dataset comprises one or more rows that are generated from the response of a resource to a statement. The Data dataset may include a variable number of columns that is statement specific. Each Data dataset element may contain a value that is statement specific and resource specific.

As mentioned above the metadata driven command processor generates a Process dataset which may contain the same defined schema as the SPTPResponse. Process dataset elements are populated from the SPTPResponse dataset elements. All of the processing within the metadata command processor then references elements within the Process dataset. For instance in the disclosed exemplary schema the nested datasets can be referenced within the Process dataset using the indices shown in Table 21 

In an embodiment the metadata driven command processor contains six commands that each include instruction sets ProcessRequest ProcessEvent TransferData ClearData Send Receive and CallMethod. The ProcessRequest command is invoked by components of an agent. The TransferData ClearData and Send Receive commands are invoked within instruction sets of commands of the metadata driven command processor. The ProcessEvent and CallMethod commands may be invoked by agent components and within command instruction sets of the metadata driven command processor. The CallMethod TransferData ClearData and Send Receive commands may be assigned command codes 1 2 3 and 4 respectively.

Receive send monitor of agent is configured to receive requests from remote agent send results to remote agent and invoke ProcessRequest command of metadata driven command processor and resource handler of agent . Booter of agent is configured to invoke ProcessRequest command of metadata driven command processor . Machine event handler of agent is configured to receive machine events and invoke ProcessEvent command of metadata driven command processor . User event handler of agent is configured to receive user events and invoke CallMethod command of metadata driven command processor . Resource handler of agent is configured to send requests to remote agent receive results from remote agent receive requests from Send Receive command send statements to resource receive results from resource and return results to Send Receive command .

ProcessRequest command may be invoked by receive send monitor and booter of agent and may invoke ProcessEvent command and Send Receive command . ProcessEvent command may be invoked by a ProcessRequest command and machine event handler and may invoke CallMethod command . CallMethod command may be invoked by a ProcessEvent command user event handler and CallMethod command and may invoke CallMethod command TransferData command ClearData command and Send Receive command . TransferData command may be invoked by CallMethod command and TransferData command and may invoke TransferData command . ClearData command may be invoked by CallMethod command . Send Receive command may be invoked by ProcessRequest command and CallMethod command and may send requests to resource handler of agent .

In an embodiment metadata driven command processor contains instruction sets in a programming language or machine language that is compatible with machine . The example instruction sets below illustrate non limiting examples of instruction sets using the JavaScript programming language. However it should be understood that any suitable alternative programming language or machine language may be utilized.

ProcessRequest command facilitates 1 loading of a booting program and application and 2 transferring a loaded program application s and their processing states to a metadata driven command processor on another machine. Instruction Set 1 of the example instruction sets below illustrates an example of how the functionality of ProcessRequest command may be implemented in JavaScript. ProcessRequest command may be invoked by the receive send monitor and booter components of an agent when a SPTPRequest is to be processed by metadata driven command processor . Based on the value of a RequestType element in the SPTPRequest dataset one of the following instruction sets may be executed 

 1 If RequestType is 0 a defined value representing a Load Booting Program and Application request type then ProcessRequest command resets the RequestType to 1 a defined value representing a Send Booting Program and Application request type invokes Send Receive command with the updated SPTPRequest to retrieve a booting program and application and creates an initial Process dataset from the returned SPTPResponse. ProcessRequest command then invokes ProcessEvent command to execute the booting method by setting command parameters as follows EventType 1 RecordID 0 and Value .

 2 If RequestType is 2 a defined value representing a Send Loaded Program and Applications request type then ProcessRequest command sets SPTPResponse to the Process dataset. Agent returns the SPTPResponse comprising the Process dataset to remote agent to allow the metadata driven command processor of remote agent to continue program processing from its current state.

ProcessEvent command identifies the method associated with a machine event and invokes CallMethod command to execute the identified method. Instruction Set 2 of the example instruction sets below illustrates an example of how the functionality of ProcessEvent command may be implemented in JavaScript. ProcessEvent command may be invoked by machine event handler of agent whenever a machine event is to be processed by metadata driven command processor . ProcessEvent command may also be conditionally invoked by ProcessRequest command and Send Receive command . ProcessEvent command may include the parameters shown in Table 22 

If the EventType parameter value is 3 a defined value for a Message event type before the Program dataset has been generated then ProcessEvent command generates a system level error message. Regardless of the value of the EventType parameter if the Program dataset has not been generated ProcessEvent command terminates its processing.

Otherwise the MethodID variable is set to the MethodID element value in the Methods dataset for the row in which the EventType element value matches the EventType parameter value. Then CallMethod command is invoked with the MethodID variable RecordID parameter and Value parameter values passed as the MethodID RecordID and Value parameters respectively for CallMethod command .

If the EventType parameter is set to 3 a defined value for a Message event type then the values for the MessageCode TypeCode Description and SourceCode elements in the Message dataset are cleared.

CallMethod command CommandCode 1 executes the rows within the MethodSteps dataset that are associated with a specific method. The MethodStep row execution invokes the command associated with a row when the row s condition if any is met. Instruction Set 3 of the example instructions sets below illustrates an example of how the functionality of CallMethod command may be implemented in JavaScript. CallMethod command may be invoked by user event handler of agent whenever a user event is to be processed by metadata driven command processor . CallMethod command may also be invoked by ProcessEvent command and conditionally invoked within the instruction set of CallMethod command . CallMethod command may include the parameters shown in Table 23 

CallMethod command updates the SPTPRequest dataset elements RecordID and Value from its RecordID and Value parameters respectively. CallMethod command then executes the rows within the MethodSteps dataset that are associated with the MethodID parameter. For each MethodStep row an instruction set represented by the following pseudocode may be performed 

TransferData command CommandCode 2 appends updates or deletes a dataset row based on the current values of another dataset row s elements. Instruction Set 4 of the example instruction sets below illustrates an example of how the functionality of TransferData command may be implemented in JavaScript. TransferData command may be conditionally invoked by CallMethod command and within the instruction set of TransferData command . TransferData command may include the parameter shown in Table 24 

TransferData command executes the row in the Transfers dataset that is associated with the TransferID parameter. The FromDataset variable is set to the Dataset identified from the FromDSI and FromNDSI elements values within the Transfers dataset. If the FromDSI value is 1 then the FromDataset is set to the SPTPRequest dataset. The ToDataset variable is set to the dataset identified from the ToDSI and ToNDSI elements values within the Transfers dataset. If to ToDSI value is 1 then the ToDataset is identified as the SPTPRequest dataset.

If the FromDataset is a single row then the FromRI variable is set to 0. Otherwise the FromRI variable is set to the row index within the FromDataset whose element values meet the criteria defined within the TransferConditions dataset rows that are associated with the TransferID parameter. For each matching row in the TransferConditions dataset an instruction set represented by the following pseudocode may be performed 

Based on the value of TransferType element of the Transfer dataset one of the following instruction sets is executed 

If TransferType is 1 or 2 defined values representing Append and Update respectively then for each row in the TransferColumns dataset that is associated with the TransferID parameter an instruction set represented by the following pseudocode may be performed 

TransferData command may invoke itself for each row in the Transfers dataset in which its ParentID element value matches the TransferID parameter. The matching row s TransferID element value is passed as the TransferID parameter.

ClearData command CommandCode 3 clears the data in a nested dataset contained within the Application dataset. Instruction Set 5 of the example instructions sets below illustrates an example of how the functionality of ClearData command may be implemented in JavaScript. ClearData command may be invoked by CallMethod command . ClearData command may include the parameter shown in Table 25 

Send Receive command CommandCode 4 may invoke resource handler of agent to 1 execute a statement using resource or 2 forward a SPTPRequest to remote agent for processing. Instruction Set 6 of the example instruction sets below illustrates an example of how the functionality of Send Receive command may be implemented in JavaScript. Send Receive command may conditionally update the Process dataset from the SPTPResponse. Send Receive command may be conditionally invoked by ProcessRequest command and CallMethod command .

In an embodiment based on the value of the RemoteConnectType element of the SPTPRequest dataset one of the following instructions sets is executed 

Resource handler creates a SPTPResponse dataset within metadata driven command processor based on the response from resource remote agent or remote resource . Send Receive command updates the Process dataset by setting the Message element of the Process dataset to the Message element of the SPTPRequest dataset.

If the MessageType element within the Message nested dataset is 1 a defined value representing Error then Send Receive command invokes ProcessEvent command passing the value 3 as the EventType parameter a defined value representing Message and terminates its processing. Otherwise Send Receive command updates the Process dataset by setting the Data element of the Process dataset to the Data element of the SPTPRequest dataset.

In an embodiment based on the value of the RequestType element of the SPTPRequest dataset one of the following instructions is executed 

As discussed above agent may comprise receive send monitor booter machine event handler user event handler and resource handler . In an embodiment receive send monitor monitors incoming requests from remote agents e.g. remote agent . When a SPTPRequest is received receive send monitor invokes a resource manager component of agent or the ProcessRequest command of metadata driven command processor based on the RequestType element. Receive send monitor creates a SPTPResponse based on the process results from resource handler or metadata driven command processor and returns the result to the requesting remote agent.

In an embodiment booter creates a booting SPTPRequest within metadata driven command processor and invokes ProcessRequest command of metadata driven command processor to load the booting program and application.

In an embodiment machine event handler invokes ProcessEvent command of metadata driven command processor when a machine event is to be processed by metadata driven command processor . For instance when a machine display size change event occurs machine event handler updates Width and Height elements within the SPTPRequest dataset of metadata driven command processor based on the new machine display size and sets the EventType parameter of ProcessEvent command to the value 2 a defined value for Screen Size Change .

In an embodiment user event handler invokes CallMethod command of metadata driven command processor when a user event occurs that is associated with a dynamic display rendering generated from a statement. Examples of user events include without limitation an OnClick event OnLostFocus event OnChange event etc.

In an embodiment resource handler is invoked by Send Receive command of metadata driven command processor to 1 execute a statement using resource or 2 forward a SPTPRequest to remote agent . Resource handler converts a response from resource or remote agent into a SPTPResponse that is processed by metadata driven command processor . The MessageCode MessageType Description and SourceCode elements in the Message nested dataset are set based on a system message e.g. error or alert in the response.

An implementation of a sample utility which utilizes an embodiment of the disclosed metadata driven command processor and structured program transfer protocol will now be described. The utility is a metadata driven database application whose booting program and application enable an end user of an end user device e.g. a type of a machine to add update delete view and navigate the same program and application metadata stored in a SQL relational database on a remote machine by rendering dynamic HTML content on the end user device based on user invoked events.

An agent contains an instruction set in a programming language or machine language that is compatible with a resource on an end user device or other machine. A sample agent instruction set is illustrated in Instruction Set 7 of the example instruction sets below. In this example the agent and MCP instruction sets are in the form of JavaScript. The MCP instruction set exists in a JS file in this example x10Data MCP.js that is referenced within the agent instruction set. The agent instruction set includes booter and resource handler components.

The booter creates a SPTPRequest within the metadata driven command processor that contains the dataset element values illustrated in Table 26A 

It should be understood that these values may alternatively be illustrated in a row column format as shown in Table 26B 

The booter invokes the ProcessRequest command of the metadata driven command processor. The ProcessRequest command updates the dataset element values in the SPTPRequest shown in Table 26C 

The booter invokes the Send Receive command. Then the Send Receive command invokes the agent s resource handler component. The resource handler forwards the SPTPRequest to the remote agent identified as SOAP based web service appCase.mobi . The remote agent creates a SPTPResponse that includes the booting program and application retrieved from a remote resource in the form of a SQL relational database. In this example the SPTPResponse has the nested Program dataset element values shown in Tables 27A 35B 

In this example the SPTPResponse has the nested program defined Application dataset element values shown in Tables 36A 44B. In this example the appConditions dataset in Table 42B does not contain any rows.

The resource handler returns control to the Send Receive command. The Send Receive command creates the Process dataset from the SPTPResponse and returns control to the ProcessRequest command. The ProcessRequest command then invokes the ProcessEvent command by calling ProcessEvent 1 0 i.e. passing parameters 1 0 and to subroutine ProcessEvent . In turn the ProcessEvent command invokes the CallMethod command by calling CallMethod 1 0 . The CallMethod command updates the SPTPRequest dataset element values from its parameters. After being updated by the CallMethod command the SPTPRequest contains the following updated values for column indices 10 and 12 

The CallMethod command invokes the TransferData command by calling TransferData 6 1 1 1 1 1 1 1 . The TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 10 from constant values. The appended row is shown in Table 46 

The CallMethod command calls CallMethod 46 which sequentially invokes the ClearData command by calling ClearData 11 ClearData 12 ClearData 13 ClearData 14 ClearData 15 and ClearData 16 to remove the rows from process generated Application nested datasets referenced as Process 0 2 0 11 Process 0 2 0 12 Process 0 2 0 13 Process 0 2 0 14 Process 0 2 0 15 and Process 0 2 0 16 respectively.

The CallMethod command then calls TransferData 68 1 1 1 1 1 1 1 and the TransferData command updates the SPTPRequest dataset elements from the Application nested dataset referenced as Process 0 2 0 10 as shown in Table 47 

The CallMethod command then calls CallMethod 2 . The CallMethod command calls TransferData 11 1 1 1 1 1 1 1 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 16 from condition matching rows in the Commands Program nested dataset i.e. Process 0 1 0 8 . In this case no rows matched the conditions.

The CallMethod command then calls CallMethod 23 . The CallMethod command calls TransferData 12 1 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 9 from a single row in the appSession Application nested dataset i.e. Process 0 2 0 0 as shown in Table 48 

The TransferData command then calls TransferData 32 2 0 0 2 9 0 . The TransferData command updates the appended row in the Application nested dataset referenced as Process 0 2 0 9 from the single row in the Application nested dataset referenced as Process 0 2 0 10 as shown in Table 49 

The TransferData command then calls TransferData 15 2 0 0 2 9 0 . The TransferData command copies the Application nested dataset referenced as Process 0 2 0 10 into a data element of the appended row in the Application nested dataset referenced as Process 0 2 0 9 as shown in Table 50 

The TransferData command then calls TransferData 16 2 0 0 2 9 0 . The TransferData command copies the Application nested dataset referenced as Process 0 2 0 11 into a data element of the appended row in the Application nested dataset referenced as Process 0 2 0 9 as shown in Table 51 

The TransferData command then calls TransferData 17 2 0 0 2 9 0 . The TransferData command copies the Application nested dataset referenced as Process 0 2 0 12 into a data element of the appended row in the Application nested dataset referenced as Process 0 2 0 9 as shown in Table 52 

The TransferData command then calls TransferData 244 2 0 0 2 9 0 . The TransferData command copies the Application nested dataset referenced as Process 0 2 0 13 into a data element of the appended row in the Application nested dataset referenced as Process 0 2 0 9 as shown in Table 53 

The TransferData command then calls TransferData 245 2 0 0 2 9 0 . The TransferData command copies the Application nested dataset referenced as Process 0 2 0 14 into a data element of the appended row in the Application nested dataset referenced as Process 0 2 0 9 as shown in Table 54 

The TransferData command then calls TransferData 18 2 0 0 2 9 0 . The TransferData command copies the Application nested dataset referenced as Process 0 2 0 15 into a data element of the appended row in the Application nested dataset referenced as Process 0 2 0 9 as shown in Table 55 

The TransferData command then calls TransferData 19 2 0 0 2 9 0 . The TransferData command copies the Application nested dataset referenced as Process 0 2 0 16 into a data element of the appended row in the Application nested dataset referenced as Process 0 2 0 9 as shown in Table 56 

The CallMethod command calls TransferData 14 1 1 1 1 1 1 1 and the TransferData command updates the single row in the appSession Application nested dataset i.e. Process 0 2 0 0 from constant formula values as shown in Table 57 

The CallMethod command calls CallMethod 7 . The CallMethod command sequentially calls ClearData 17 ClearData 18 and ClearData 19 to remove the rows from process generated Application nested datasets referenced as Process 0 2 0 17 Process 0 2 0 18 and Process 0 2 0 19 respectively.

The CallMethod command calls CallMethod 8 . The CallMethod command calls TransferData 20 1 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 17 from constant values as shown in Table 58 

The TransferData command calls TransferData 71 2 10 0 2 17 0 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 18 from constant and parameter values as shown in Table 59 

The TransferData command calls TransferData 22 2 10 0 2 18 0 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 19 from the single row in the appSession Application nested dataset i.e. Process 0 2 0 0 and constant and parameter values as shown in Table 60 

The TransferData command calls TransferData 83 2 10 0 2 18 0 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 19 from the single row in the appSession Application nested dataset i.e. Process 0 2 0 0 and constant and parameter values as shown in Table 61 

The CallMethod command calls CallMethod 9 . The CallMethod command calls TransferData 24 1 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 17 from constant values as shown in Table 62 

The TransferData command calls TransferData 73 2 10 0 2 17 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 18 from constant and parameter values as shown in Table 63 

The TransferData command calls TransferData 48 2 10 0 2 18 1 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 19 from condition matching rows in the Menus Program nested dataset i.e. Process 0 1 0 7 and constant and parameter values as shown in Table 64 

The CallMethod command calls CallMethod 10 . The CallMethod command calls TransferData 26 1 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 17 from constant values as shown in Table 65 

The TransferData command calls TransferData 74 2 10 0 2 17 2 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 18 from constant and parameter values as shown in Table 66 

The TransferData command calls TransferData 84 2 10 0 2 18 2 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 19 from the single row in the Application nested dataset referenced as Process 0 2 0 10 and constant and parameter values as shown in Table 67 

The TransferData command calls TransferData 229 2 10 0 2 19 9 and the TransferData command updates the last appended row in the process generated Application nested dataset referenced as Process 0 2 0 19 from the condition matching single row in the Application nested dataset referenced as Process 0 2 0 10 . In this case the row did not match the condition.

The TransferData command calls TransferData 86 2 10 0 2 17 2 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 18 from constant and parameter values as shown in Table 68 

The TransferData command calls TransferData 87 2 10 0 2 18 3 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 19 from the single row in the Application nested dataset referenced as Process 0 2 0 10 and constant and parameter values as shown in Table 69 

The TransferData command calls TransferData 235 2 10 0 2 19 10 and the TransferData command updates the last appended row in the process generated Application nested dataset referenced as Process 0 2 0 19 from the condition matching single row in the Application nested dataset referenced as Process 0 2 0 10 . In this case the row did not match the condition.

The TransferData command then calls TransferData 88 2 10 0 2 18 3 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 19 from the single row in the Application nested dataset referenced as Process 0 2 0 10 and constant and parameter values as shown in Table 70 

The TransferData command calls TransferData 236 2 10 0 2 19 11 and the TransferData command updates the last appended row in the process generated Application nested dataset referenced as Process 0 2 0 19 from the condition matching single row in the Application nested dataset referenced as Process 0 2 0 10 . In this case the row did not match the condition.

The CallMethod command calls CallMethod 13 . The CallMethod command calls TransferData 30 1 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 17 from constant values as shown in Table 71 

The TransferData command calls TransferData 75 2 10 0 2 17 3 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 18 from constant and parameter values as shown in Table 72 

The TransferData command calls TransferData 50 2 10 0 2 18 4 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 19 from condition matching rows in the Commands Program nested dataset i.e. Process 0 1 0 8 and constant and parameter values. In this case no rows matched the conditions.

The CallMethod command calls CallMethod 14 . The CallMethod command calls TransferData 60 1 1 1 1 1 1 1 and the TransferData command updates the rows in the process generated Application nested dataset referenced as Process 0 2 0 18 from condition matching rows in the Application nested dataset referenced as Process 0 2 0 19 and constant values as shown in Table 73 

The CallMethod command calls TransferData 61 1 1 1 1 1 1 1 and the TransferData command updates the rows in the process generated Application nested dataset referenced as Process 0 2 0 17 from condition matching rows in the Application nested dataset referenced as Process 0 2 0 18 and constant values as shown in Table 74 

The CallMethod command calls TransferData 69 1 1 1 1 1 1 1 and the TransferData command updates the single row in the SPTPRequest dataset from constant values as shown in Table 75 

The CallMethod command calls TransferData 53 1 1 1 1 1 1 1 and the TransferData command updates the single row in the SPTPRequest dataset from the rows in the Application nested dataset referenced as Process 0 2 0 17 and constant values as shown in Table 76 

The CallMethod command invokes the Send Receive command by calling Send Receive . The Send Receive command invokes the resource handler of the agent. The resource handler invokes the HTML DOM layout engine resource to incorporate the statement included in the SPTPRequest which renders the first display shown in .

If a user clicks the Cards element on the display illustrated in the user event handler of the agent will invoke CallMethod 5 4 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 77 

The CallMethod command then invokes the TransferData command by calling TransferData 7 1 1 1 1 1 1 1 . The TransferData command updates the single row in the Application nested dataset referenced as Process 0 2 0 10 from the condition matching row in the Application nested dataset referenced as Process 0 2 0 19 as shown in Table 78 

The CallMethod command calls CallMethod 46 which sequentially invokes the ClearData command by calling ClearData 11 ClearData 12 ClearData 13 ClearData 14 ClearData 15 and ClearData 16 to remove the rows from process generated Application nested datasets referenced as Process 0 2 0 11 Process 0 2 0 12 Process 0 2 0 13 Process 0 2 0 14 Process 0 2 0 15 and Process 0 2 0 16 respectively.

The CallMethod command then calls TransferData 68 1 1 1 1 1 1 1 and the TransferData command updates the SPTPRequest dataset elements from the Application nested dataset referenced as Process 0 2 0 10 as shown in Table 79 

The CallMethod command calls CallMethod 3 which calls TransferData 10 1 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 15 from condition matching rows in the appEntities Application nested dataset i.e. Process 0 2 0 1 as shown in Table 80 

The CallMethod command calls TransferData 11 1 1 1 1 1 1 1 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 16 from condition matching rows in the Commands Program nested dataset i.e. Process 0 1 0 8 as shown in Table 81 

The process defined in Sample Process 2 is repeated with dataset element values appended and updated as shown in the tables within those sections.

The CallMethod command calls CallMethod 11 . The CallMethod command calls TransferData 28 1 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 17 from constant values as shown in Table 82 

The TransferData command calls TransferData 79 2 10 0 2 17 2 and the TransferData command updates the last appended row in the process generated Application nested dataset referenced as Process 0 2 0 17 from condition matching rows in the Application nested dataset referenced as Process 0 2 0 15 and constant values as shown in Table 83 

The CallMethod command calls CallMethod 13 . The CallMethod command calls TransferData 30 1 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 17 from constant values as shown in Table 84 

The TransferData command calls TransferData 75 2 10 0 2 17 3 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 18 from constant and parameter values as shown in Table 85.

The TransferData command calls TransferData 50 2 10 0 2 18 4 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 19 from condition matching rows in the Commands Program nested dataset i.e. Process 0 1 0 8 and constant and parameter values as shown in Table 86 

The TransferData command calls TransferData 136 2 16 0 2 19 8 and the TransferData command updates the last appended row in the Application nested dataset referenced as Process 0 2 0 19 from the condition matching single row in the Application nested dataset referenced as Process 0 2 0 10 . In this case the row did not match the condition.

The TransferData command calls TransferData 222 2 16 0 2 19 8 and the TransferData command updates the last appended row in the Application nested dataset referenced as Process 0 2 0 19 from the condition matching single row in the Application nested dataset referenced as Process 0 2 0 10 . In this case the row did not match the condition.

The CallMethod command calls CallMethod 14 . The CallMethod command calls TransferData 60 1 1 1 1 1 1 1 and the TransferData command updates the rows in the process generated Application nested dataset referenced as Process 0 2 0 18 from condition matching rows in the Application nested dataset referenced as Process 0 2 0 19 and constant values as shown in Table 87 

The CallMethod command calls TransferData 61 1 1 1 1 1 1 1 and the TransferData command updates the rows in the process generated Application nested dataset referenced as Process 0 2 0 17 from condition matching rows in the Application nested dataset referenced as Process 0 2 0 18 and constant values as shown in Table 88 

The CallMethod command calls TransferData 69 1 1 1 1 1 1 1 and the TransferData command updates the single row in the SPTPRequest dataset from constant values as shown in Table 75.

The CallMethod command calls TransferData 53 1 1 1 1 1 1 1 and the TransferData command updates the single row in the SPTPRequest dataset from the rows in the Application nested dataset referenced as Process 0 2 0 17 and constant values as shown in Table 89 

The CallMethod command invokes the Send Receive command by calling Send Receive . The Send Receive command invokes the resource handler of the agent. The resource handler invokes the HTML DOM layout engine resource to incorporate the statement included in the SPTPRequest which renders the second display shown in .

If a user clicks the Entities element on the display in the user event handler of the agent will invoke CallMethod 6 12 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 90 

The CallMethod command then invokes the TransferData command by calling TransferData 38 1 1 1 1 1 1 . The TransferData command calls TransferData 38 2 1 20 2 10 0 . The TransferData command updates the single row in the Application nested dataset referenced as Process 0 2 0 10 from the condition matching row in the Application nested dataset referenced as Process 0 2 0 4 as shown in Tables 91 

The CallMethod command calls CallMethod 46 which sequentially invokes the ClearData command by calling ClearData 11 ClearData 12 ClearData 13 ClearData 14 ClearData 15 and ClearData 16 to remove the rows from process generated Application nested datasets referenced as Process 0 2 0 11 Process 0 2 0 12 Process 0 2 0 13 Process 0 2 0 14 Process 0 2 0 15 and Process 0 2 0 16 respectively.

The CallMethod command then calls TransferData 68 1 1 1 1 1 1 and the TransferData command updates the SPTPRequest dataset elements from the Application nested dataset referenced as Process 0 2 0 10 as shown in Table 92 

The CallMethod command then calls CallMethod 3 . The CallMethod command calls TransferData 213 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 10 from the condition matching row in the appEntities Application nested dataset referenced as Process 0 2 0 1 as shown in Table 93 

The CallMethod command calls TransferData 10 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 10 from condition matching rows in the appViews Application nested dataset referenced as Process 0 2 0 4 as shown in Table 94 

The CallMethod command calls TransferData 9 1 1 1 1 1 1 and the TransferData command appends rows in the process generated Application nested dataset referenced as Process 0 2 0 12 from condition matching rows in the appConditions Application nested dataset referenced as Process 0 2 0 6 . In this case no rows matched the conditions.

The CallMethod command calls TransferData 260 1 1 1 1 1 1 and the TransferData command appends rows in the process generated Application nested dataset referenced as Process 0 2 0 12 from condition matching rows in the appConditions Application nested dataset referenced as Process 0 2 0 6 . In this case no rows matched the conditions.

The CallMethod command calls CallMethod 47 . The CallMethod command calls TransferData 89 1 1 1 1 1 1 and the TransferData command appends a row in the process generated Application nested dataset referenced as Process 0 2 0 11 from the condition matching row in the appKeyAttributes Application nested dataset referenced as Process 0 2 0 2 as shown in Table 95 

The CallMethod command calls TransferData 8 1 1 1 1 1 1 and the TransferData command appends rows in the process generated Application nested dataset referenced as Process 0 2 0 11 from condition matching rows in the appColumns Application nested dataset referenced as Process 0 2 0 5 as shown in Table 96 

The CallMethod command calls TransferData 257 1 1 1 1 1 1 and the TransferData command removes condition matching rows in the process generated Application nested dataset referenced as Process 0 2 0 11 . In this case no rows matched the conditions.

The CallMethod command calls TransferData 207 1 1 1 1 1 1 and the TransferData command appends rows in the process generated Application nested dataset referenced as Process 0 2 0 13 from condition matching rows in the appRelations Application nested dataset referenced as Process 0 2 0 7 as shown in Table 97 

The CallMethod command calls TransferData 208 1 1 1 1 1 1 and the TransferData command appends rows in the process generated Application nested dataset referenced as Process 0 2 0 14 from condition matching rows in the appRelationFields Application nested dataset referenced as Process 0 2 0 8 as shown in Table 98 

The CallMethod command calls CallMethod 16 which calls ClearData 20 . The ClearData command removes the single row from the process generated Application nested datasets referenced as Process 0 2 0 20 . In this case no row pre existed.

The CallMethod command then calls TransferData 81 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 20 from the SPTPRequest dataset as shown in Table 99 

The CallMethod command then calls TransferData 54 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the condition matching rows in the Application nested dataset referenced as Process 0 2 0 11 as shown in Table 100 

The CallMethod command then calls TransferData 76 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the single row in the Application nested dataset referenced as Process 0 2 0 10 as shown in Table 101 

The CallMethod command then calls TransferData 55 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the condition matching rows in the Application nested dataset referenced as Process 0 2 0 13 as shown in Table 102 

The TransferData command calls TransferData 56 2 13 0 2 20 0 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the condition matching rows in the Application nested dataset referenced as Process 0 2 0 14 as shown in Table 103 

The TransferData command calls TransferData 120 2 13 0 2 20 0 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 to trim the element value as shown in Table 104 

The TransferData command calls TransferData 77 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the single row in the Application nested dataset referenced as Process 0 2 0 10 as shown in Table 105 

The TransferData command calls TransferData 78 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the single row in the Application nested dataset referenced as Process 0 2 0 0 as shown in Table 106 

The CallMethod command calls TransferData 129 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the condition matching single row in the Application nested dataset referenced as Process 0 2 0 10 . In this case the row did not match the conditions.

The CallMethod command calls TransferData 57 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from condition matching rows in the Application nested dataset referenced as Process 0 2 0 12 . In this case the row did not match the conditions.

The CallMethod command calls TransferData 58 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the condition matching rows in the Application nested dataset referenced as Process 0 2 0 11 as shown in Table 107 

The TransferData command calls TransferData 198 2 11 1 2 20 0 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the condition matching current row in the Application nested dataset referenced as Process 0 2 0 11 as shown in Table 108 

The TransferData command calls TransferData 199 2 11 1 2 20 0 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 20 from the condition matching current row in the Application nested dataset referenced as Process 0 2 0 11 . In this case the current row does not match the conditions.

The CallMethod command calls TransferData 70 1 1 1 1 1 1 1 and the TransferData command updates the single row in the SPTPRequest dataset from constant values as shown in Table 109 

The CallMethod command calls TransferData 59 1 1 1 1 1 1 1 and the TransferData command updates the single row in the SPTPRequest dataset from the single row in the Application nested dataset referenced as Process 0 2 0 20 as shown in Table 110 

The CallMethod command invokes the Send Receive command by calling Send Receive The Send Receive command invokes the resource handler of the agent. The resource handler forwards the SPTPRequest to the remote agent identified in the SPTPRequest as SOAP based web service appCase.mobi . The remote agent invokes the remote resource identified in the SPTPRequest as SQL Server ADCMAIN SQL2005 and database x10DATA MDB . The remote resource executes the statement contained in the SPTPRequest and returns the execution results to the remote agent. The remote agent creates an SPTPResponse dataset that includes the execution results as a structured dataset and returns the SPTPResponse to the resource handler.

The resource handler returns control to the Send Receive command. The Send Receive command copies the Data dataset within SPTPResponse 0 3 to Process 0 3 and returns control to the CallMethod command.

The CallMethod command calls TransferData 37 1 1 1 1 1 1 and the TransferData command copies the Process 0 3 dataset to the process generated Application nested dataset referenced as Process 0 2 0 15 as shown in Table 111 

The CallMethod command calls TransferData 11 1 1 1 1 1 1 1 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 16 from condition matching rows in the Commands Program nested dataset i.e. Process 0 1 0 8 as shown in Table 112 

The process defined in Sample Process 1 is executed with dataset element values appended and updated as shown in the tables within those sections. Data element values may vary slightly.

The CallMethod command calls CallMethod 11 . The CallMethod command calls TransferData 256 1 1 1 1 1 1 and the TransferData command updates the single row in the SPTPRequest dataset to reset the Statement element value to an empty string as shown in Table 113 

The CallMethod command calls TransferData 255 1 1 1 1 1 1 and the TransferData command updates the single row in the SPTPRequest dataset from constant values as shown in Table 114 

The TransferData command calls TransferData 249 2 15 0 1 1 0 and the TransferData command updates the single row in the SPTPRequest dataset from the first row in the process generated Application nested dataset referenced as Process 0 2 0 15 as shown in Table 115 

The TransferData command calls TransferData 250 2 15 0 1 1 0 and the TransferData command cross updates the rows in the process generated Application nested dataset referenced as Process 0 2 0 11 from the current row in the process generated Application nested dataset referenced as Process 0 2 0 15 . The element value in the RI in Process 0 2 0 11 is set to the element value in the CI in Process 0 2 0 15 where the CI matches the RI as shown in Table 116 

The TransferData command calls TransferData 253 2 15 0 1 1 0 and the TransferData command calls TransferData 251 2 11 1 1 1 0 which updates the Statement element value in the SPTPRequest dataset from the RecordID element value and constant values as shown in Table 117 

The TransferData command calls TransferData 252 2 11 1 1 1 0 and the TransferData command updates the single row in the SPTPRequest dataset from the first condition matching row in the Application nested dataset referenced as Process 0 2 0 11 as shown in Table 118 

The process discussed above with respect to Table 97 is repeated for all remaining condition matching rows in the Process 0 2 0 11 dataset. When the last row in Process 0 2 0 11 dataset is processed the element value in the single row in the SPTPRequest dataset is updated as shown in Table 119 

The TransferData command calls TransferData 254 2 15 0 1 1 0 and the TransferData command updates the single row in the SPTPRequest dataset from constant values as shown in Table 120 

The process in the preceding seven paragraphs is repeated for all remaining rows in the Process 0 2 0 15 dataset. When the last row in Process 0 2 0 15 dataset is processed the element value in the single row in the SPTPRequest dataset is updated as shown in Table 121 

The CallMethod command calls TransferData 248 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 17 from the single row in the SPTPRequest dataset as shown in Table 122 

The CallMethod command calls CallMethod 13 . The CallMethod command calls TransferData 30 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 17 from constant values as shown in Table 123 

The TransferData command calls TransferData 75 2 10 0 2 17 4 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 18 from constant and parameter values as shown in Table 124 

The TransferData command calls TransferData 50 2 10 0 2 18 4 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 19 from condition matching rows in the Commands Program nested dataset i.e. Process 0 1 0 8 and constant and parameter values as shown in Table 125 

The process defined in Sample Process 4 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the New element on the display in the user event handler of the agent will invoke CallMethod 5 12 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 126 

The CallMethod command then invokes the TransferData command by calling TransferData 7 1 1 1 1 1 1 1 . The TransferData command updates the single row in the Application nested dataset referenced as Process 0 2 0 10 from the condition matching row in the Application nested dataset referenced as Process 0 2 0 19 as shown in Tables 127 

The CallMethod command calls CallMethod 46 which sequentially invokes the ClearData command by calling ClearData 11 ClearData 12 ClearData 13 ClearData 14 ClearData 15 and ClearData 16 to remove the rows from process generated Application nested datasets referenced as Process 0 2 0 11 Process 0 2 0 12 Process 0 2 0 13 Process 0 2 0 14 Process 0 2 0 15 and Process 0 2 0 16 respectively.

The CallMethod command then calls TransferData 68 1 1 1 1 1 1 and the TransferData command updates the SPTPRequest dataset elements from the Application nested dataset referenced as Process 0 2 0 10 as shown in Table 128 

The CallMethod command then calls CallMethod 4 . The CallMethod command calls TransferData 240 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 10 from constant values as shown in Table 129 

The CallMethod command calls TransferData 212 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 10 from the condition matching row in the appEntities Application nested dataset referenced as Process 0 2 0 1 as shown in Table 130 

The CallMethod command calls TransferData 125 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 10 from the condition matching row in the appEntities Application nested dataset referenced as Process 0 2 0 1 as shown in Table 131 

The CallMethod command calls TransferData 127 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 10 from the condition matching row in the Application nested dataset referenced as Process 0 2 0 8 as shown in Table 132 

The CallMethod command calls TransferData 122 1 1 1 1 1 1 and the TransferData command updates the single row in the process generated Application nested dataset referenced as Process 0 2 0 10 from the condition matching row in the appViews Application nested dataset referenced as Process 0 2 0 4 as shown in Table 133 

The CallMethod command calls CallMethod 62 which calls TransferData 8 1 1 1 1 1 1 and the TransferData command appends rows in the process generated Application nested dataset referenced as Process 0 2 0 11 from condition matching rows in the appColumns Application nested dataset referenced as Process 0 2 0 5 as shown in Table 134 

The CallMethod command calls TransferData 142 1 1 1 1 1 1 and the TransferData command copies the nested dataset within a data element in the single row Application dataset referenced as Process 0 2 0 9 to the Application nested dataset referenced as Process 0 2 0 12 .

The CallMethod command calls TransferData 265 1 1 1 1 1 1 and the TransferData command removes rows in the Application dataset referenced as Process 0 2 0 11 for condition matching rows in the Application nested dataset referenced as Process 0 2 0 12 . In this case no rows existed in the Process 0 2 0 12 dataset.

The CallMethod command calls TransferData 259 1 1 1 1 1 1 and the TransferData command appends rows to the Application dataset referenced as Process 0 2 0 11 for condition matching rows in the Application nested dataset referenced as Process 0 2 0 12 . In this case no rows existed in the Process 0 2 0 12 dataset.

The CallMethod command calls TransferData 11 1 1 1 1 1 1 1 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 16 from condition matching rows in the Commands Program nested dataset i.e. Process 0 1 0 8 as shown in Table 135 

The process defined in Sample Process 1 is executed with dataset element values appended and updated as shown in the tables within those sections. Data element values may vary slightly.

The CallMethod command calls CallMethod 12 . The CallMethod command calls TransferData 51 1 1 1 1 1 1 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 17 from constant values as shown in Table 136.

The TransferData command calls TransferData 72 2 10 0 2 17 3 and the TransferData command appends a row to the process generated Application nested dataset referenced as Process 0 2 0 18 from constant and parameter values as shown in Table 137 

The TransferData command calls TransferData 52 2 11 0 2 18 4 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 19 from condition matching rows in the Application nested dataset referenced as Process 0 2 0 11 and constant and parameter values as shown in Table 138 

The TransferData command calls TransferData 123 2 11 0 2 18 4 and the TransferData command appends rows to the process generated Application nested dataset referenced as Process 0 2 0 19 from condition matching rows in the Application nested dataset referenced as Process 0 2 0 11 and constant and parameter values as shown in Table 139 

The process in the preceding two paragraphs is repeated for all remaining condition matching rows in the Process 0 2 0 11 dataset resulting in additional appended rows in the Process 0 2 0 19 dataset shown in Table 140 

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the Tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user inputs the text Function within the Name input element on the display as shown in and then causes the display element s OnChange event to execute the user event handler of the agent will invoke CallMethod 15 715 Function . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 141 

The CallMethod command then invokes the TransferData command by calling TransferData 223 1 1 1 1 1 1 1 . The TransferData command calls TransferData 47 2 11 0 2 11 0 which updates the condition matching row in the Application nested dataset referenced as Process 0 2 0 11 from the single row in the SPTPRequest dataset as shown in Table 142 

The CallMethod command then calls TransferData 163 1 1 1 1 1 1 which calls TransferData 164 2 9 2 2 9 2 . The TransferData command copies the Application nested dataset referenced as Process 0 2 0 11 into a data element of the condition matching row in the Application nested dataset referenced as Process 0 2 0 9 as shown in Table 143 

The TransferData command then calls TransferData 221 2 9 2 2 9 2 . The TransferData command copies the Application nested dataset referenced as Process 0 2 0 10 into a data element of the appended row in the Application nested dataset referenced as Process 0 2 0 9 as shown in Table 144 

If a user clicks the Type input element on the display the user event handler of the agent will invoke CallMethod 5 15 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 145.

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the Bound element on the display in the user event handler of the agent will invoke CallMethod 6 1 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 146 

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display shown in .

If a user clicks the Table input element on the display in the user event handler of the agent will invoke CallMethod 5 17 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 147 

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the Views element on the display in the user event handler of the agent will invoke CallMethod 6 15 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 148 

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the Save element on the display in the user event handler of the agent will invoke CallMethod 5 26 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 149 

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the Function element on the display in the user event handler of the agent will invoke CallMethod 6 64 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 150 

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the Table label element on the display in the user event handler of the agent will invoke CallMethod 5 16 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 151 

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the Detail element on the display in the user event handler of the agent will invoke CallMethod 5 9 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 152.

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the Entities element on the display in the user event handler of the agent will invoke CallMethod 6 6 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 153.

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the X10DATA.COM element on the display in the user event handler of the agent will invoke CallMethod 5 0 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 154.

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the Windows element on the display in the user event handler of the agent will invoke CallMethod 5 6 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 155.

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

If a user clicks the Entity Function element on the display in the user event handler of the agent will invoke CallMethod 6 8 . The CallMethod command will then update the SPTPRequest dataset elements from its parameters for those elements shown in Table 156.

The process defined in Sample Process 3 is executed with dataset element values appended and updated as shown in the tables within those sections. Specific dataset element values will vary in some cases. The completion of this process renders the display as shown in .

The system preferably includes one or more processors such as processor . Additional processors may be provided such as an auxiliary processor to manage input output an auxiliary processor to perform floating point mathematical operations a special purpose microprocessor having an architecture suitable for fast execution of signal processing algorithms e.g. digital signal processor a slave processor subordinate to the main processing system e.g. back end processor an additional microprocessor or controller for dual or multiple processor systems or a coprocessor. Such auxiliary processors may be discrete processors or may be integrated with the processor .

The processor is preferably connected to a communication bus . The communication bus may include a data channel for facilitating information transfer between storage and other peripheral components of the system . The communication bus further may provide a set of signals used for communication with the processor including a data bus address bus and control bus not shown . The communication bus may comprise any standard or non standard bus architecture such as for example bus architectures compliant with industry standard architecture ISA extended industry standard architecture EISA Micro Channel Architecture MCA peripheral component interconnect PCI local bus or standards promulgated by the Institute of Electrical and Electronics Engineers IEEE including IEEE 488 general purpose interface bus GPIB IEEE 696 S 100 and the like.

System preferably includes a main memory and may also include a secondary memory . The main memory provides storage of instructions and data for programs executing on the processor . The main memory is typically semiconductor based memory such as dynamic random access memory DRAM and or static random access memory SRAM . Other semiconductor based memory types include for example synchronous dynamic random access memory SDRAM Rambus dynamic random access memory RDRAM ferroelectric random access memory FRAM and the like including read only memory ROM .

The secondary memory may optionally include a internal memory and or a removable medium for example a floppy disk drive a magnetic tape drive a compact disc CD drive a digital versatile disc DVD drive etc. The removable medium is read from and or written to in a well known manner. Removable storage medium may be for example a floppy disk magnetic tape CD DVD SD card etc.

The removable storage medium is a non transitory computer readable medium having stored thereon computer executable code i.e. software and or data. The computer software or data stored on the removable storage medium is read into the system for execution by the processor .

In alternative embodiments secondary memory may include other similar means for allowing computer programs or other data or instructions to be loaded into the system . Such means may include for example an external storage medium and an interface . Examples of external storage medium may include an external hard disk drive or an external optical drive or and external magneto optical drive.

Other examples of secondary memory may include semiconductor based memory such as programmable read only memory PROM erasable programmable read only memory EPROM electrically erasable read only memory EEPROM or flash memory block oriented memory similar to EEPROM . Also included are any other removable storage media and communication interface which allow software and data to be transferred from an external medium to the system .

System may also include a communication interface . The communication interface allows software and data to be transferred between system and external devices e.g. printers networks or information sources. For example computer software or executable code may be transferred to system from a network server via communication interface . Examples of communication interface include a modem a network interface card NIC a wireless data card a communications port a PCMCIA slot and card an infrared interface and an IEEE 1394 fire wire just to name a few.

Communication interface preferably implements industry promulgated protocol standards such as Ethernet IEEE 802 standards Fiber Channel digital subscriber line DSL asynchronous digital subscriber line ADSL frame relay asynchronous transfer mode ATM integrated digital services network ISDN personal communications services PCS transmission control protocol Internet protocol TCP IP serial line Internet protocol point to point protocol SLIP PPP and so on but may also implement customized or non standard interface protocols as well.

Software and data transferred via communication interface are generally in the form of electrical communication signals . These signals are preferably provided to communication interface via a communication channel . In one embodiment the communication channel may be a wired or wireless network or any variety of other communication links. Communication channel carries signals and can be implemented using a variety of wired or wireless communication means including wire or cable fiber optics conventional phone line cellular phone link wireless data communication link radio frequency RF link or infrared link just to name a few.

Computer executable code i.e. computer programs or software is stored in the main memory and or the secondary memory . Computer programs can also be received via communication interface and stored in the main memory and or the secondary memory . Such computer programs when executed enable the system to perform the various functions of the present invention.

In this description the term computer readable medium is used to refer to any non transitory computer readable storage media used to provide computer executable code e.g. software and computer programs to the system . Examples of these media include main memory secondary memory including internal memory removable medium and external storage medium and any peripheral device communicatively coupled with communication interface including a network information server or other network device . These non transitory computer readable mediums are means for providing executable code programming instructions and software to the system .

In an embodiment that is implemented using software the software may be stored on a computer readable medium and loaded into the system by way of removable medium I O interface or communication interface . In such an embodiment the software is loaded into the system in the form of electrical communication signals . The software when executed by the processor preferably causes the processor to perform the inventive features and functions previously described herein.

The system also includes optional wireless communication components that facilitate wireless communication over a voice and over a data network. The wireless communication components comprise an antenna system a radio system and a baseband system . In the system radio frequency RF signals are transmitted and received over the air by the antenna system under the management of the radio system .

In one embodiment the antenna system may comprise one or more antennae and one or more multiplexors not shown that perform a switching function to provide the antenna system with transmit and receive signal paths. In the receive path received RF signals can be coupled from a multiplexor to a low noise amplifier not shown that amplifies the received RF signal and sends the amplified signal to the radio system .

In alternative embodiments the radio system may comprise one or more radios that are configured to communicate over various frequencies. In one embodiment the radio system may combine a demodulator not shown and modulator not shown in one integrated circuit IC . The demodulator and modulator can also be separate components. In the incoming path the demodulator strips away the RF carrier signal leaving a baseband receive audio signal which is sent from the radio system to the baseband system .

If the received signal contains audio information then baseband system decodes the signal and converts it to an analog signal. Then the signal is amplified and sent to a speaker. The baseband system also receives analog audio signals from a microphone. These analog audio signals are converted to digital signals and encoded by the baseband system . The baseband system also codes the digital signals for transmission and generates a baseband transmit audio signal that is routed to the modulator portion of the radio system . The modulator mixes the baseband transmit audio signal with an RF carrier signal generating an RF transmit signal that is routed to the antenna system and may pass through a power amplifier not shown . The power amplifier amplifies the RF transmit signal and routes it to the antenna system where the signal is switched to the antenna port for transmission.

The baseband system is also communicatively coupled with the processor . The central processing unit has access to data storage areas and . The central processing unit is preferably configured to execute instructions i.e. computer programs or software that can be stored in the main memory or the secondary memory . Computer programs can also be received from the baseband processor and stored in the data storage area or in secondary memory or executed upon receipt. Such computer programs when executed enable the system to perform the various functions of the present invention as previously described. For example data storage areas may include various software modules not shown .

Various embodiments may also be implemented primarily in hardware using for example components such as application specific integrated circuits ASICs or field programmable gate arrays FPGAs . Implementation of a hardware state machine capable of performing the functions described herein will also be apparent to those skilled in the relevant art. Various embodiments may also be implemented using a combination of both hardware and software.

Furthermore those of skill in the art will appreciate that the various illustrative logical blocks modules circuits and method steps described in connection with the above described figures and the embodiments disclosed herein can often be implemented as electronic hardware computer software or combinations of both. To clearly illustrate this interchangeability of hardware and software various illustrative components blocks modules circuits and steps have been described above generally in terms of their functionality. Whether such functionality is implemented as hardware or software depends upon the particular application and design constraints imposed on the overall system. Skilled persons can implement the described functionality in varying ways for each particular application but such implementation decisions should not be interpreted as causing a departure from the scope of the invention. In addition the grouping of functions within a module block circuit or step is for ease of description. Specific functions or steps can be moved from one module block or circuit to another without departing from the invention.

Moreover the various illustrative logical blocks modules and methods described in connection with the embodiments disclosed herein can be implemented or performed with a general purpose processor a digital signal processor DSP an ASIC FPGA or other programmable logic device discrete gate or transistor logic discrete hardware components or any combination thereof designed to perform the functions described herein. A general purpose processor can be a microprocessor but in the alternative the processor can be any processor controller microcontroller or state machine. A processor can also be implemented as a combination of computing devices for example a combination of a DSP and a microprocessor a plurality of microprocessors one or more microprocessors in conjunction with a DSP core or any other such configuration.

Additionally the steps of a method or algorithm described in connection with the embodiments disclosed herein can be embodied directly in hardware in a software module executed by a processor or in a combination of the two. A software module can reside in RAM memory flash memory ROM memory EPROM memory EEPROM memory registers hard disk a removable disk a CD ROM or any other form of storage medium including a network storage medium. An exemplary storage medium can be coupled to the processor such the processor can read information from and write information to the storage medium. In the alternative the storage medium can be integral to the processor. The processor and the storage medium can also reside in an ASIC.

The above description of the disclosed embodiments is provided to enable any person skilled in the art to make or use the invention. Various modifications to these embodiments will be readily apparent to those skilled in the art and the generic principles described herein can be applied to other embodiments without departing from the spirit or scope of the invention. Thus it is to be understood that the description and drawings presented herein represent a presently preferred embodiment of the invention and are therefore representative of the subject matter which is broadly contemplated by the present invention. It is further understood that the scope of the present invention fully encompasses other embodiments that may become obvious to those skilled in the art and that the scope of the present invention is accordingly not limited.

