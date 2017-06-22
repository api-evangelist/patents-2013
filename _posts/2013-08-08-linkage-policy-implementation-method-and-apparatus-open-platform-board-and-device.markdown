---

title: Linkage policy implementation method and apparatus, open platform board, and device
abstract: Embodiments of the present invention disclose a linkage policy implementation method, which includes: receiving, by a linkage proxy module, a linkage policy request delivered by a third-party application service; calling a corresponding protocol converter according to a protocol identifier in the linkage policy request, and performing protocol conversion for the linkage policy request to convert it into a linkage policy request in a set protocol format; and sending the protocol-converted linkage policy request to a linkage client to instruct the linkage client to parse the linkage policy request based on the set protocol and execute linkage policy configuration. With the present invention, a linkage proxy is set to execute protocol conversion of various protocols. Therefore, the cost of the linkage client would not be increased for supporting multiple protocols; and when third-party applications are increased or decreased, it is unnecessary to reconfigure the linkage client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09413592&OS=09413592&RS=09413592
owner: Huawei Technologies Co., Ltd.
number: 09413592
owner_city: Shenzhen
owner_country: CN
publication_date: 20130808
---
This application is a continuation of International Patent Application No. PCT CN2011 072812 filed on Apr. 14 2011 which is hereby incorporated by reference in its entirety.

Embodiments of the present invention relate to communication technologies and in particular to a linkage policy implementation method and apparatus an open platform board and a device.

As an enterprise intranet develops constantly and more services run on the enterprise intranet an access router AR serving as a switching device and a switch need to support more services. To support multiple services the switching device in the conventional art is provided with an open platform board in addition to a main control board. The open platform board can provide diversified distinctive services. According to different service sources the services may include a service customized by a switching device manufacturer a third party cooperative service a user developed service and so on and according to different service types the services may include a network traffic analysis service an antivirus service and an application acceleration service. The above services additionally integrated into the switching device may be uniformly referred to as the third party application services. The open platform board in the form of a board can conveniently add or remove the software of the third party application services.

The third party application services in the conventional art usually require the configuration of the main control board which is mainly reflected in the form of linkage policy configuration. Taking the antivirus software as an example when a third party antivirus software detects that a service flow passing through the main control board carries a virus the software may need to configure a linkage blocking policy or rule for the main control board for example instruct the main control board to block a port or a type of service flow.

To implement the linkage policy configuration of a third party application service for the main control board both the main control board and the open platform board on the switching device need to support the protocols used by the third party application service mainly including a network management protocol or a man machine command format and so on. Different third party application service providers may use different protocols for example the used network management protocol may be the Simple Network Management Protocol SNMP and Extensible Markup Language XML .

Therefore in the conventional art it is required that the switching device should support multiple protocols. Accordingly how to configure the switching device to support multiple protocols so as to implement the linkage policy configuration of the third party application services while taking the configuration cost of hardware and software into account is a problem to be solved in the conventional art.

Embodiments of the present invention provide a linkage policy implementation method and apparatus an open platform board and a device so that a device is enabled to support multiple protocols with a low cost optimized solution.

receiving by a linkage proxy module a linkage policy request delivered by a third party application service 

calling by the linkage proxy module a corresponding protocol converter according to a protocol identifier in the linkage policy request and performing protocol conversion for the linkage policy request to convert it into a linkage policy request in a set protocol format and

a request receiving unit configured to receive a linkage policy request delivered by a third party application service 

a protocol converting unit configured to call a corresponding protocol converter according to a protocol identifier in the linkage policy request and perform protocol conversion for the linkage policy request to convert it into a linkage policy request in a set protocol format and

a linkage configuring unit configured to send the protocol converted linkage policy request to a linkage client to instruct the linkage client to parse the linkage policy request based on the set protocol and execute linkage policy configuration.

An embodiment of the present invention also provides an open platform board including the linkage proxy module provided by any embodiment of the present invention.

An embodiment of the present invention also provides a device including a main control board and an open platform board where 

the open platform board is the open platform board provided by any embodiment of the present invention and

With the linkage policy implementation method and apparatus the open platform board and the device provided by the embodiments of the present invention a linkage proxy module is arranged to execute protocol conversion of various protocols which may isolate the linkage client based on the set protocol and multiple third party application services executing different protocols. The linkage client may be integrated in a main control board or may interact with the main control board to implement the linkage policy configuration. On one hand the linkage client may support only one protocol and the cost of the linkage client would not be increased for supporting multiple protocols on the other hand when the third party application services are increased or decreased it is unnecessary to extend or update the linkage client.

When the embodiments of the present invention are applied to the device including a main control board and an open platform board no impact is imposed on the software and hardware structures or the normal work of the main control board. Especially when a protocol is added or updated the main control board is not reconfigured thereby avoiding interruption of work due to the restart of the main control board caused by reconfiguration. Therefore both extensibility and compatibility of the device are improved and the device can deploy a new third party application service quickly without imposing impact on the main control board.

To make objectives technical solutions and advantages of embodiments of the present invention more comprehensible the following clearly describes the technical solutions in the embodiments of the present invention with reference to the accompanying drawings in the embodiments of the present invention. Apparently the described embodiments are merely a part rather than all of the embodiments of the present invention. All other embodiments obtained by persons of ordinary skill in the art based on the embodiments of the present invention without creative efforts shall fall within the protection scope of the present invention.

Step A linkage proxy module receives a linkage policy request delivered by a third party application service and specifically the linkage proxy module may receive the linkage policy request through a third party interface.

The third party interface set on the open platform board is preferably an software development kit Software Development Kit SDK application programming interface Application Programming Interface API and may be applicable to different protocols respectively. For example the network management protocol may be a command line interface Command Line Interface CLI protocol an SNMP a network configuration Network Configuration NETCONF protocol an OpenFlow open flow protocol and so on. In step preferably the linkage proxy module receives linkage policy requests delivered by different third party application services through third party interfaces corresponding to different protocols the third party application services using the same protocol can use the same third party interface.

Step The linkage proxy module calls a corresponding protocol converter according to a protocol identifier in the linkage policy request and performs protocol conversion for the linkage policy request to convert it into a linkage policy request in a set protocol format.

In step the linkage proxy module may specifically search and call a protocol converter according to an interface type. Specifically the linkage proxy module may collect an interface type in the linkage policy request and use the interface type as the protocol identifier the linkage proxy module queries according to the interface type a protocol converter global table for a corresponding protocol converter for calling. When the third party interfaces correspond to different protocols the interface type of the third party interface receiving the linkage policy request corresponds to different protocols based on which the corresponding protocol converter can be found. is a schematic logical architecture diagram of an open platform board. Multiple protocol converters are set in the linkage proxy module of the open platform board and correspond to different protocols. The protocol converter converts the linkage policy request based on a set protocol where the set protocol is a protocol that is currently used by the main control board and is determined through interaction with the linkage proxy module such as SNMP. Various protocol converters may respectively convert NETCONF CLI and OpenFlow protocols into the SNMP protocol. Of course other protocol may also be determined as a set protocol according to requirements of the main control board and the corresponding protocol convert is provided. The main work of a protocol converter is to convert the format of a linkage policy request according to the substance of the linkage policy request so that the linkage policy request is in a format readable based on a set protocol. This embodiment is described by using conversion between various network management protocols as an example. However those skilled in the art can understand that the protocol conversion in the actual application is not limited to conversion between various network management protocols.

Step The linkage proxy module sends the protocol converted linkage policy request to a linkage client to instruct the linkage client to parse the linkage policy request based on the set protocol and execute linkage policy configuration. With respect to the structure of a switching device the linkage client may be integrated in a main control board and in this case this step may be specifically as follows The linkage client directly controls the main control board to execute linkage policy configuration. Or the linkage client may also be located outside the main control board and parse the linkage policy request and execute linkage policy configuration through interaction with a control apparatus on the main control board.

The technical solution of this embodiment has many advantages. For example compared with the solution in which multiple network management protocols are loaded on the main control board to support network management protocols of different third party application services the technical solution of this embodiment sets a linkage proxy on the open platform board of the device to execute protocol conversion and may isolate the main control board based on a set network management protocol and multiple third party application services executing different network management protocols. On one hand the main control board may support only one network management protocol and the cost of the main control board would not be increased for supporting multiple network management protocols on the other hand when third party application services are increased or decreased it is unnecessary to extend or update the main control board and no impact would be imposed on the software and hardware structures and normal work of the main control board. Especially when a network management protocol is added or updated the main control board would not be reconfigured thereby avoiding interruption of work due to restart of the main control board caused by reconfiguration. Therefore both extensibility and compatibility of the device are improved and the device can deploy a new third party application service quickly without imposing impact on the main control board. This advantage is especially outstanding in the switching device.

Step A linkage proxy module receives a linkage policy request delivered by a third party application service.

Step The linkage proxy module calls a corresponding protocol converter according to a protocol identifier in the linkage policy request and performs protocol conversion for the linkage policy request to convert it into a linkage policy request in a set protocol format.

Subsequently in this embodiment the linkage proxy module sending the protocol converted linkage policy request to a linkage client to instruct the linkage client to parse the linkage policy request based on the set protocol and execute linkage policy configuration which specifically includes the following steps 

Step The linkage proxy module adds an application identifier to the protocol converted linkage policy request where the application identifier corresponds to the third party application service delivering the linkage policy request.

The application identifier in the above step may be carried in the linkage policy request. However preferably the linkage proxy module generates a corresponding application identifier for the third party application service according to a predetermined algorithm so that the linkage proxy module can identify the third party application service.

Step The linkage proxy module sends the linkage policy request carrying the application identifier to the linkage client to instruct the linkage client to parse the linkage policy request based on the set protocol and execute linkage policy configuration.

Step The linkage proxy module receives a linkage policy response generated by the linkage client for executing linkage policy configuration where the linkage policy response carries the application identifier.

Step The linkage proxy module calls according to the application identifier included in the linkage policy response a corresponding protocol converter to perform protocol conversion for the linkage policy response and returns a protocol converted linkage policy response to a corresponding third party application service.

In step specifically the linkage proxy module may find the corresponding third party application service based on the application identifier and may further determine the corresponding third party application platform and protocol identifier and perform protocol conversion for the linkage policy response before returning it to the thread started by the third party application service for subsequent processing.

This embodiment provides a technical solution for responding to the third party linkage policy request. An application identifier corresponding to the third party application service is added to the linkage policy request so that the linkage client also carries the application identifier in the returned linkage policy response. The linkage proxy module may return the linkage policy response to the corresponding third party application service according to the application identifier specifically through a third party interface so that the third party application service can know the state of progress of the linkage policy configuration.

In specific applications the linkage policy generated and delivered by the third party application service mainly includes two forms. One form is delivering a linkage parameter and configuring the linkage parameter on the main control board to control the operation of the main control board. The other form is delivering a linkage event where the linkage event configured for the main control board usually requires the main control board to monitor an event of interest and return an event notification message to the third party application service when the event of interest occurs so that the third party application service is triggered to execute the set callback function.

For example the antivirus application service is used as a third party application service for description. The third party application service may deliver a drain rule to a main control board of a switching device where the drain rule is a linkage parameter instructing the main control board of the switching device to mirror the received service flow to an intrusion detection system Intrusion Detection System IDS antivirus application on the open platform board. Subsequently the IDS antivirus application analyzes the service flow and detects the service flow carrying a virus. The IDS antivirus application may deliver a linkage blocking policy rule to the main control board through the open platform board according to the detection result where the linkage blocking policy rule may be in the form of a linkage parameter or in the form of a linkage event. For example the linkage blocking policy may be a port number instructing the main control board to block the service flow of the port number when the linkage blocking policy being in the form of a linkage event the linkage blocking policy may also be a port state indicating that when the main control board monitors a change of the port state that is an event of interest the event of interest is notified to the third party application service so that the third party application service is triggered to execute a corresponding callback function for example to make a corresponding analysis.

The technical solution for returning a linkage policy response to the third party application service in this embodiment may be respectively applicable to the form of delivering a linkage parameter and the form of delivering a linkage event. The linkage policy response may reflect whether the linkage parameter or event of interest is configured successfully so that the third party application service can know whether the linkage parameter is configured successfully.

Step A linkage proxy module receives a linkage policy request delivered by a third party application service.

Step The linkage proxy module parses the linkage policy request to obtain an event of interest when identifying that the linkage policy request is an event registration request and records the event of interest corresponding to an application identifier where the application identifier corresponds to the third party application service delivering the linkage policy request.

Step The linkage proxy module calls a corresponding protocol converter according to a protocol identifier in the linkage policy request and performs protocol conversion for the linkage policy request to convert it into a linkage policy request in a set protocol format.

Step The linkage proxy module adds the application identifier to the protocol converted linkage policy request.

Step When receiving an event of interest reported by the linkage client the linkage proxy module constructs an event notification message according to the event of interest.

Step The linkage proxy module calls according to a mapping between the recorded event of interest and the application identifier and according to the application identifier a corresponding protocol converter to perform protocol conversion for the event notification message and returns the protocol converted event notification message to a corresponding third party application service to trigger the third party application service to execute a callback function.

This embodiment is applicable to the case of delivering a linkage event. The linkage proxy module constructs an event notification message and reports it to the third party application service so that the main control board notifies the third party application service when the main control board monitors an event of interest. The specific execution process of delivering the linkage parameter and linkage event is described in detail through the subsequent embodiments.

On the basis of the above embodiment before the linkage proxy module sends the protocol converted linkage policy request to the linkage client the following operation may be included When identifying that the linkage policy request is an event deregistration request the linkage proxy module clears the recorded event of interest corresponding to the application identifier.

Step A linkage proxy module receives an application registration request delivered by a third party application service. No time sequence is specified for this step and the above technical solution. This step may be executed when before or after other third party application service executes linkage policy configuration.

Step The linkage proxy module obtains a protocol identifier according to the application registration request.

Step The linkage proxy module finds a corresponding protocol converter identifier according to the protocol identifier and adds the protocol identifier and the protocol converter identifier to a protocol converter global table for querying.

In the above technical solution the protocol converter identifier is used to identify a protocol converter. For example the protocol converter identifier may be a protocol converter program pointer indicating the place from which the protocol converter is called. By adding an entry to the protocol converter global table the newly added third party application service can select a corresponding protocol converter so that a corresponding protocol converter can be found for protocol conversion when a linkage policy request is delivered subsequently. The protocol converter global table stores a protocol identifier and a protocol converter identifier to facilitate finding of a protocol converter but is not limited to the two entry contents.

The linkage proxy module may further obtain one or more application identifiers corresponding to the third party application service from the application registration request and correspondingly store the obtained application identifier and the protocol identifier and the protocol converter identifier in the protocol converter global table. Or after the linkage proxy module receives the application registration request delivered by the third party application service the following is further included The linkage proxy module generates an application identifier corresponding to the third party application service delivering the application registration request and correspondingly stores the generated application identifier and the protocol identifier and the protocol converter identifier in the protocol converter global table.

There may be multiple storage formats for example each application identifier corresponds to one entry and therefore each third party application service may have multiple entries as shown in Table 1 so as search is convenient. The entry content of the protocol converter global table may preferably include the service application name App application identifier interface type protocol converter program pointer and so on.

The technical solution of this embodiment is applicable to the case that a third party application service is newly added and can support dynamically loading a new third party application service. The work of the linkage client or main control board is not affected when a new third party application service is loaded. Therefore the technical solution of this embodiment has good extensibility and can easily deploy third party application services quickly. The linkage proxy module may record the protocol identifier corresponding to the third party application service and the protocol converter identifier for example information such as an interface type and a program pointer so that the corresponding protocol converter can be called when a linkage policy request delivered by the third party application service is received. Further the application identifier of the third party application service may be stored to indicate the interaction objects of the linkage policy request and response.

Correspondingly when it is necessary to update or delete a third party application service or when an application identifier of the third party application service needs to be updated or the third party application service needs to be deleted the entries of the protocol converter global table may also be updated and deleted through an application update request or an application deletion request.

Step An application function of a third party application process that is a third party application service calls an OAP open application platform Open Application Platform API function and inputs a linkage parameter or callback function thereby generating a linkage policy request.

Step The OAP API function processes the linkage policy request and sends the linkage policy request to an OAP linkage proxy process that is a linkage proxy module and if the application function of the third party application process needs to call the callback function creates a corresponding receiving thread.

Step The receiving thread in the linkage proxy process performs protocol conversion after receiving the linkage policy request and sends the linkage policy request to the linkage client process on the main control board of the switching device.

Step The linkage client process of the main control board of the switching device generates and sends a linkage policy response to the OAP linkage proxy process where the linkage policy response may be a configuration success response or may be a linkage event after an event is monitored.

Step The receiving thread in the linkage proxy process performs protocol conversion after receiving the linkage policy response and sends the linkage policy response to the OAP API function in the third party application process.

Step The OAP API function in the third party application process is returned the third party application process continues to execute the original application function or the receiving thread of the third party application process executes the callback function after receiving an event notification message.

The technical solution of this embodiment specifically describes the coordination operation of each thread on the third party application service the linkage proxy module and the linkage client. It can be seen that the protocol used by the third party application service and the linkage client may be converted on the linkage proxy module which basically has no impact on the solution executed by the third party application service and linkage client.

The following describes the procedure of the technical solution of this embodiment in detail by using an instance. The procedure includes the following steps 

Step An application function in a third party application process calls a linkage parameter processing API whose network management protocol is CLI and inputs a linkage parameter in the corresponding protocol format.

Step The linkage parameter processing API constructs an OAP request message OAP SET REQUEST request that is a linkage policy request which carries the linkage parameter and sends the linkage policy request to the linkage proxy process on the open platform board.

Step The receiving thread in the linkage proxy process receives the OAP SET REQUEST request parses the request message finds the corresponding application identifier according to the source address in the request message calls a corresponding protocol converter according to the interface type to construct an SNMP MSG SET request of the configuration policy rule that is a protocol converted linkage policy request and sends the SNMP MSG SET request to the linkage client of the main control board.

Step The linkage client process of the main control board receives the SNMP MSG SET request processes the request and sends an SNMP MSG RESPONSE response that is a linkage policy response to the linkage proxy process.

Step The receiving thread in the linkage proxy process receives the SNMP MSG RESPONSE response parses the response finds the corresponding address according to the application identifier constructs an OAP SET RESPONSE response that is a protocol converted linkage policy response and sends it to the linkage parameter processing API.

Step The third party application process calls the original application function of the linkage parameter processing API to continue execution.

The above process is an implementation method for executing the linkage policy in the form of a linkage parameter where the form of a linkage parameter includes but is not limited to a port number an access control list a source address a destination address a control policy rule and so on.

The linkage proxy module may start multiple threads to execute the above process which specifically includes the following steps 

Step An application function in a third party application process calls an event registration API and inputs an event of interest and the identifier of a callback function to be triggered after the event occurs for example uses the change of a port state as the event of interest.

Step The event registration API records the callback function constructs an OAP event registration message OAP EVENT REGISTER REQUEST that is a linkage policy request and sends it to the linkage proxy process.

Step The receiving thread in the linkage proxy process receives the OAP EVENT REGISTER REQUEST message parses the message finds the corresponding application identifier according to the address and records the event of interest for example records the port number of each port the state change of which is of interest then calls the corresponding protocol converter according to the interface type to construct an application event registration request SNMP MSG SET that is a protocol converted linkage policy request and sends it to the linkage client process.

Step The linkage client process receives the SNMP MSG SET request processes the request and sends an SNMP MSG RESPONSE response that is a linkage policy response to the linkage proxy process notifying that the event registration is successful.

Step The receiving thread in the linkage proxy process receives the SNMP MSG RESPONSE response parses the response finds the corresponding address according to the application identifier constructs an OAP event registration response OAP EVENT REGISTER RESPONSE that is a protocol converted linkage policy response and sends it to the event registration API.

Step The event registration API receives the OAP EVENT REGISTER RESPONSE response and analyzes whether the registration result is successful if the registration fails step is executed or if the registration is successful step is executed.

Step The event registration API is returned and the third party application process calls the application function of the linkage event registration API to continue execution and the procedure is ended.

Step The event registration API creates a receiving thread and waits for the event notification message sent by the linkage proxy.

Step The event registration API is returned the third party application process calls the application function of the linkage event registration API to continue execution and then step is executed when the application process is no longer concerned about the event or before the process is terminated an event deregistration API is called.

Step The linkage client process sends an SNMP MSG TRAP notification message to the linkage proxy process to report the event of interest after detecting that the event of interest registered by the third party application process occurs.

Step The snmptrapd process in the linkage proxy module receives the SNMP MSG TRAP notification message parses the message and triggers the notification process according to a predetermined configuration file where the snmptrapd process is started and executed when the linkage proxy process is started initially for triggering the notification process.

Step The notification process of the linkage proxy module constructs an OAP notification message OAP NOTIFY that is an event notification message according to the parameter in the configuration file and the parameter in the event of interest and sends the OAP notification message OAP NOTIFY to the receiving thread in the linkage proxy.

Step The receiving thread in the linkage proxy process receives the OAP NOTIFY notification message parses the message constructs an OAP NOTIFY RESPONSE response and sends the response to the notification process.

Step The receiving thread in the linkage proxy process constructs a protocol converted OAP NOTIFY notification message and sends the event notification message to the corresponding third party application service according to identifiers such as the application identifier.

Step The receiving thread created by the event registration API receives the OAP NOTIFY notification message parses the message and constructs and sends an event notification response to the linkage proxy process so that the linkage proxy process receives the OAP NOTIFY RESPONSE response.

Step The receiving thread created by the event registration API executes the callback function input when the third party application process is registered and the above steps to are executed repeatedly so that an event of interest is processed once it occurs.

Step An application function in a third party application process calls an event deregistration API and inputs an event of interest and a callback function.

Step The event deregistration API constructs an OAP event deregistration message OAP EVENT DEREGISTER REQUEST request that is a linkage policy request and sends the OAP EVENT DEREGISTER REQUEST request to the linkage proxy process.

Step The receiving thread in the linkage proxy process receives the OAP EVENT DEREGISTER REQUEST request parses the request finds the corresponding application identifier according to the address clears the recorded event of interest corresponding to the application identifier from the linkage proxy calls the corresponding protocol converter according to the interface type to construct a SNMP MSG SET request of the event deregistration and sends the SNMP MSG SET request to the linkage client of the main control board.

Step The linkage client process receives the SNMP MSG SET request processes the request and sends an SNMP MSG RESPONSE response to the linkage proxy process.

Step The receiving thread in the linkage proxy process receives the SNMP MSG RESPONSE response parses the response finds the corresponding address according to the application identifier constructs an OAP event deregistration response OAP EVENT DEREGISTER RESPONSE and sends the OAP event deregistration response OAP EVENT DEREGISTER RESPONSE to the event deregistration API.

Step The event deregistration API is returned after receiving the OAP EVENT DEREGISTER RESPONSE response and the third party application process calls the application function of the linkage event registration API to continue execution.

The technical solution of this embodiment can conveniently implement the linkage policy configuration of the linkage event. With the technical solutions of the seventh embodiment and eighth embodiment the linkage proxy module records the event of interest and constructs an event notification message. Therefore the linkage event is mainly configured and updated by the linkage proxy module arranged on the open platform board which reduces the impact on normal work of the linkage client or main control board.

The technical solution of this embodiment of the present invention sets a linkage proxy to execute protocol conversion of various protocols and may isolate the linkage client based on the set protocol and multiple third party application services executing different protocols. The linkage client may be integrated in a main control board or may interact with the main control board to implement linkage policy configuration. On one hand the linkage client may support only one protocol and the cost of the linkage client would not be increased for supporting multiple protocols on the other hand when third party application services are increased or decreased it is unnecessary to extend or update the linkage client.

The linkage proxy module provided by each embodiment of the present invention may execute the linkage policy implementation method provided by the embodiment of the present invention and has the corresponding functional modules.

The technical solution of this embodiment may implement dynamic loading of a third party application service on the linkage proxy module.

This embodiment provides a technical solution for responding to the third party linkage policy request. By adding an application identifier corresponding to the third party application service to the linkage policy request the linkage client also carries the application identifier in the returned linkage policy response and the linkage proxy module may return the linkage policy response to the corresponding third party application service according to the application identifier.

This embodiment is applicable to the case of delivering a linkage event. The linkage proxy module constructs an event notification message and reports it to the third party application service so that the linkage client notifies the monitored event of interest to the third party application service.

An embodiment of the present invention also provides an open platform board including the linkage proxy module provided by any embodiment of the present invention. The open platform board preferably further includes multiple third party interfaces corresponding to different protocols configured to implement interaction between the third party application service and the linkage proxy module where the third party interfaces are application programming interfaces of a software development kit and the protocol identifier is an interface type.

An embodiment of the present invention also provides a device including a main control board and an open platform board the structures of which may be as shown in . The open platform board is the open platform board provided by any embodiment of the present invention the main control board includes a linkage client where the linkage client is configured to receive a linkage policy request delivered by the linkage proxy module and parse the linkage policy request based on a set protocol and execute linkage policy configuration.

Typically the device including the main control board and open platform board is a switching device. The technical solution of the embodiment of the present invention does not impose any impact on the software and hardware structures and normal work of the main control board. Especially when a protocol is added or updated the main control board is not reconfigured thereby avoiding interruption of work due to restart of the main control board caused by reconfiguration. Therefore both extensibility and compatibility of the device are improved and the device can deploy a new third party application service quickly without imposing impact on the main control board.

Persons of ordinary skill in the art may understand that all or a part of the steps of the methods in the embodiments may be implemented by a program instructing relevant hardware. The program may be stored in a computer readable storage medium. When the program runs the steps of the methods in the embodiments are performed. The storage medium may be any medium that is capable of storing program codes such as a ROM a RAM a magnetic disk or an optical disk.

Finally it should be noted that the above embodiments of the present invention are merely intended for describing the technical solutions of the present invention other than limiting the present invention. Although the present invention is described in detail with reference to the foregoing embodiments persons of ordinary skill in the art should understand that they may still make modifications to the technical solution described in the foregoing embodiments or make equivalent substitutions to some technical features thereof without departing from the spirit and scope of the technical solution of the embodiments of the present invention.

