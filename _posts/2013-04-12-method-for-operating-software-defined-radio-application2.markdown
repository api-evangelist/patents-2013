---

title: Method for operating software defined radio application
abstract: Disclosed is a structure for operating a unified radio application for a software defined radio terminal. The structure for operating a unified radio application according to the present invention can be classified into two types depending on whether a configuration code (configcode) of the radio application is constituted by an executable code or implemented in an intermediate representation (IR) code. With the structure for operating a unified radio application according to the present invention, it is possible to develop and distribute a radio application capable of operating on all radio platforms.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09612816&OS=09612816&RS=09612816
owner: INDUSTRY-UNIVERSITY COOPERATION FOUNDATION HANYANG UNIVERSITY
number: 09612816
owner_city: Seoul
owner_country: KR
publication_date: 20130412
---
The present invention relates to operational structures of radio applications for a software defined radio SDR terminal and more specifically to operational structures of unified radio applications which have hardware independency and can be developed as corresponding to various radio platforms.

The technologies of the present invention may cover software define radio digital radio communications baseband processors application processors application stores long term evolution LTE worldwide interoperability for microwave WiMax and radio applications.

In the present invention various radio applications such as LTE WiMax wireless microphone walkie talkie etc. can be downloaded from application stores and installed into a cellular phone so that the cellular phone can be changed into an LTE terminal or a WiMax terminal or can be used as a wireless microphone a walkie talkie etc. Therefore the present invention may be applied to smart phones which need to support various radio access technologies such as LTE wideband code division multiple access WCDMA and WIFI.

In connection with the software defined radio SDR technology there exists a software communication architecture SCA which is a defacto standard technology. It may comprise specifications related to frameworks for SDR middleware and real time operating system OS which guarantees compatibility of interfaces between SDR systems. The core of SCA is a core framework which is a framework specification. In the core framework various parts constituting radio applications are componentized and the components may be reused and assembled so as to create a new radio application.

In case of SCA it is possible to make rearrangement of blocks which are already installed in a terminal. However user defined blocks to be used for a specific radio application cannot be installed even into SCA compatible terminals having different hardware configurations. Thus single executable codes cannot be used for all SCA compatible terminals. This means that executable codes optimized for each hardware configuration on which each SCA compatible terminal is based should be respectively created and distributed. This demands very much time and cost and makes commercial uses of radio applications difficult Also it does not provide baseband application programming interface API for implementation of radio applications and accordingly it makes selective utilization of hardware acceleration functions difficult.

The purpose of the present invention for resolving the above described problems is to provide operational structures of unified radio applications which can be freely developed distributed installed and executed as corresponding to various radio platforms.

In some example embodiments of the present invention a method of operating a radio application in a radio processor layer of a terminal having a radio processor the method may comprise determining whether a shadow radio platform to which the radio application is targeted is identical to a real radio platform of the terminal and executing configuration codes of the radio application in the radio processor when the shadow radio platform is identical to the real radio platform of the terminal.

Here the configuration codes may include user defined function block codes for configuring user defined function blocks of the radio application and a radio library for configuring standard function blocks used by the radio application in form of execution codes executable on the real radio platform.

Also at least part of the standard function blocks may be implemented as dedicated hardware logics executed by the radio application through a hardware abstraction layer HAL of the radio processor layer.

Here the method may further comprise downloading a radio application package including the configuration codes of the radio application from a server.

Here the radio application may operate on at least one of the radio processor and an application processor of the terminal and interwork with a radio control framework providing the radio application with operation environments.

Also the radio control framework includes at least one of a configuration manager CM performing installation uninstallation of the radio application and creating deleting an instance of the radio application and managing radio parameters for the radio application a radio connection manager RCM performing activation deactivation of the radio application and managing user data flow switching between radio applications a flow controller FC controlling sending receiving and flows of user data packets a multi radio controller MRC scheduling requests for spectrum resources issued by radio applications and a resource manager RM sharing radio resources with radio applications.

In other example embodiments of the present invention a method of operating a radio application in a radio processor layer of a terminal having a radio processor the method may comprise determining whether a shadow radio platform to which the radio application is targeted is identical to a real radio platform of the terminal and executing configuration codes of the radio application in the radio processor by compiling the configuration codes through a radio virtual machine RVM when the shadow radio platform is different from the real radio platform of the terminal.

Here the configuration codes may include user defined function block codes for configuring user defined function blocks of the radio application in intermediate representation IR form which can be converted into execution codes executable on the real radio platform.

Here the RVM may include a just in time JIT compiler or which compiles the configuration codes into execution codes of the real radio platform.

Here the RVM may include an ahead of time AOT compiler which compiles the configuration codes into execution codes of the real radio platform.

Here the terminal may have native implementations of standard function blocks in the radio processor layer.

Here the terminal may have standard function blocks implemented as dedicated hardware logics executed by the radio application through a hardware abstraction layer HAL of the radio processor layer.

Here the method may further comprise downloading a radio application package including the configuration codes of the radio application from a server.

Here the radio application may operate on at least one of the radio processor and an application processor of the terminal and interwork with a radio control framework providing the radio application with operation environments.

Here the radio control framework may include at least one of a configuration manager CM performing installation uninstallation of the radio application and creating deleting an instance of the radio application and managing radio parameters for the radio application a radio connection manager RCM performing activation deactivation of the radio application and managing user data flow switching between radio applications a flow controller FC controlling sending receiving and flows of user data packets a multi radio controller MRC scheduling requests for spectrum resources issued by radio applications and a resource manager RM sharing radio resources with radio applications.

Using the operational structures of unified radio applications according to the present invention it can become possible to develop and distribute radio applications which can be executed in various radio platforms. Therefore a new business model in which radio applications are commercially traded may be created.

In addition in aspect of mobile operators it may become possible to switch radio access technologies of which terminals based on various radio platforms that subscribers are using into desired radio access technologies according to their needs so that flexible operation of mobile networks may be possible.

In addition in aspect of subscribers it may become possible that they can use new radio access technologies only by downing a radio application package for a desired radio application and installing the desired radio application in their terminals without purchasing new terminals.

The present invention may be variously modified and may include various embodiments. However particular embodiments are exemplarily illustrated in the drawings and will be described in detail. However it should be understood that the particular embodiments are not intended to limit the present disclosure to specific forms but rather the present disclosure is meant to cover all modification similarities and alternatives which are included in the spirit and scope of the present disclosure. Like reference numerals refer to like elements throughout the description of the drawings.

Relational terms such as first second A B and the like may be used for describing various elements but the elements should not be limited by the terms. The terms are used solely for distinguishing one element from another. For instance without departing the scope of the present disclosure a first element may be named as a second element and similarly a second element may be named as a first element. The term and or encompasses both combinations of the plurality of related items disclosed and any item from among the plurality of related items disclosed.

It will be understood that when an element is referred to as being connected or coupled to another element it can be directly connected or coupled to the other element or intervening elements may be present. In contrast when an element is referred to as being directly connected or directly coupled to another element there are no intervening elements present.

The terminology used herein is not for delimiting the present invention but for describing the specific embodiments. The terms of a singular form may include plural forms unless otherwise specified. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this invention belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

Hereinafter example embodiments of the present invention will be described in detail with reference to the accompanying drawings. In describing the invention to facilitate the entire understanding of the invention like numbers refer to like elements throughout the description of the figures and a repetitive description on the same element is not provided.

Terminologies used for explaining the present invention are defined as follows. Other terminologies except the following terminologies will be defined in the corresponding parts of the present specification.

Referring to a monolithic kernel is a kernel to which all necessary functions are integrated. Since all necessary functions exist in the same memory space each of the functions provided by the kernel may be accessed by using a function call method. Thus its implementation can be simplified and system resources can be efficiently utilized. However it is difficult that the implemented kernel is not easily ported to various hardware environments or different systems. Also when its functions are extended a size of the kernel may become too large and management of the kernel may become difficult.

Also referring to a micro kernel is a kernel in which necessary functions are designed as small server modules and only minimum functions for managing the server modules are implemented as a core part of the kernel. This type of kernel has advantages that expansion and reconfiguration of its functions are easy and it can be easily reused by other systems. However since frequent message exchanges and context switching may occur during a procedure of using services there is a shortcoming that its working speed may become relatively lower.

Referring to and a software architecture according to the present invention may comprise an application processor layer which operates on an application processor AP and a radio processor layer which operates on a radio processor RP . Here the radio processor may be also referred to as a baseband processor BP .

A non real time OS such as Andriod OS of Google iOS of Apple etc. may operate on the AP and a real time OS hereinafter referred to as a radio OS may operate on the RP. Hereinafter for clear discrimination the non real time OS operating on the AP layer may be referred to as OS and the real time OS operating on the RP layer may be referred to as radio OS .

Hereinafter the AP layer the RP layer and components constituting the radio control framework will be described in detail.

If the radio control framework is configured to operate on the AP and the RP both as shown in an AP layer part of the radio control framework may exist on the OS. If the radio control framework is configured to operate only on the RP as shown in the radio control framework does not exist on the AP layer.

If the radio control frame work operates on both the processors a composition of a communication service layer may exist on the OS of the AP.

The communication service layer may be a layer providing at least some of the following three services to the radio control framework.

The first service is related to an administrative. It may be a service related to installation uninstallation of radio applications creating deleting instances of radio applications and acquisition of a list of radio applications in each status installed instanced activated .

The second service is related to connection control. It may be a service related to activation deactivation of radio applications creation of data flow creation of network allocation and acquisition of a list of radio applications in each status installed instanced activated .

Lastly the third service is related to data flow. That is this service is a service related to sending receiving user data.

As an example of communication service layer configurations for providing at least some of the above described three services the communication service layer may be configured to comprise an administrator application a mobility policy manager application a networking stack i.e. a protocol stack operating on the communication service layer and a monitor application.

However the communication service layer may comprise only some of the above described components or may further comprise additional components as well as the above described components. Also one or more components among the above components may be integrated into a single component existing within the communication service layer. Also the above described components are only examples of components which the communication service layer can comprise in order to support services which should be performed by the communication service layer. That is the communication service layer may be defined based on functions performed by it. The above described exemplary composition of components does not restrict composition of the communication service layer.

In the configuration in which the radio control framework operates on both the AP and the RP the composition of radio applications and to which distribution installation operation methods according to the present invention are applied may respectively comprise AP layer parts and and RP layer parts and . A radio controller RC which is the AP layer part of radio application may be configured to transmit context information to a monitor application of the communication service layer transmit data to a networking stack of the communication service layer and receive data from the networking stack.

If the radio control framework is configured to operate on the AP and the RP both as shown in a RP layer part of the radio control framework may exist on the radio OS. If the radio control frame work operates only on the RP as shown in the radio control framework does not exist on the AP layer. That is the radio control framework exists only on the RP layer.

Since role and configuration of the communication service layer illustrated in are identical to those of the communication service layer illustrated in redundant explanations are omitted.

Radio controllers and of respective radio applications may be configured to transmit context information to a monitor application of the communication service layer transmit data to a networking stack of the communication service layer and receive data from the networking stack.

A multi radio interface MURI is an interface between the communication service layer and the control framework and a unified radio application interface URAI is an interface between the radio application and the control framework.

A radio application is an application enabling communications of a mobile terminal and may be distributed in form of a radio application package. Components of a radio application package may be configured as follows.

4 Radio library a radio library is distributed in form of executable codes as included in a radio application package when the standard function blocks SFB are distributed as executable codes.

The radio application package may be downloaded onto the OS of the application processor layer and the user defined function block codes and the radio library may be loaded from the application processor to the radio processor by referring to the pipeline configuration metadata and finally loaded to the radio OS on the radio processor layer.

The radio control framework RCF or is a component for providing operation environment of radio applications.

If the radio control framework is configured to operate on the AP and the RP both as shown in components of the radio control framework may be classified into two groups and . That is one group operates on the AP and other group operates on the RP. It may be determined differently according to each vendor which components of the RCF operate on the RP i.e. in real time and which components of the RCF operate on the AP i.e. in non real time .

If the radio control framework is configured to operate only on the RP i.e. a configuration of the radio control framework exists only on the RP layer without discrimination of a RP layer part and an AP layer part.

Basically the RCF may include at least some of the following 5 components for managing radio applications.

However the radio control framework may comprise only some of the following 5 components and may further comprise additional components as well as the following 5 components. Also one or more components among the following components may be integrated into a single component existing within the radio control framework.

The role of the radio control framework may be defined based on functions performed by the components which will be described. The following exemplary components do not restrict composition of the radio control framework. That is the radio control framework may have various configurations at least some of functions of the following components.

1 Configuration Manager CM Installation uninstallation and creating deleting instance of radio applications into RP as well as access management of radio parameters for radio applications.

2 Radio Connection Manager RCM Activation deactivation of RAs according to user requests and overall management of user data flows which can also be switched from one RA to another.

3 Flow Controller FC Sending and receiving of user data packets and controlling the flow of signaling packets.

4 Multiradio Controller MRC Scheduling the requests for radio resources issued by concurrently executing RAs and detecting and managing the interoperability problems among the concurrently executing RAs.

5 Resource Manager RM Managing the computational resources to share them among simultaneously active RAs and to guarantee their real time requirements

In the above descriptions overall software architecture and operation environment of radio applications according to the present invention were explained. Hereinafter provided are further detail explanations operational structures of radio applications within the radio processor layer.

If a radio application package is downloaded user defined function block code and radio library which should operate on the RP layer are installed so that they can be accessed in the RP layer.

Hereinafter codes for configuring components which should be executed on the RP layer including the above described user defined function block code may be referred to as configuration code or configcodes . Configcodes may include only user defined function block code or may include radio library as well as the user defined function block code. Configcodes may be in form of executable codes or Intermediate Representation IR .

Also hereinafter a real radio platform is defined as a target radio platform and a concept of a shadow radio platform is defined as a virtual entity having hardware abstraction on the target radio platform. That is a shadow radio platform may mean a virtual radio platform into which developers of radio applications virtualize an operation environment of radio applications. For example a shadow radio platform may be equal to or different from a target radio platform. If the Shadow radio platform is different from the target radio platform the shadow radio platform may be understood as an abstract device independent of hardware. That is the shadow radio platform may be a radio virtual machine RVM .

If the shadow radio platform is different from the target radio platform so that the shadow radio platform becomes RVM the RVM performs virtualization functions for helping the above described configcodes to operate on the actual target radio platform. The implementation may include the Back end Compiler which might provide Just in Time JIT or Ahead of Time AOT method for compilation of configcodes into executable codes of the target radio platform.

The radio process provides a mobile device with communication capabilities and the software architecture for radio processor which is illustrated in may be configured to comprise the following components.

2 The RP layer part of RCF when RCF is configured with the RP layer part and the AP layer part or the entire RCF when RCF is configured to operation only on the RP .

3 The communication service layer when RCF operates only on the RP Although the communication service layer is illustrated as operating only on the RP in the communication service layer may operate on the AP when RCF is configured to operate on both the RP and the AP .

6 Configuration codes configcodes of radio applications configcodes may be provided in form of executable codes of the target radio platform or platform independent intermediate representation.

The configcodes are interpreted by RVM when the shadow radio platform is equal to RVM or are equal to executable codes when RVM is equal to the target radio platform.

The shadow radio platform can be either RVM or a target radio platform. If the Shadow radio platform is equal to the target radio platform then front end compiler will generate executable code for the target radio platform and configcodes is equivalent to the executable code for that radio platform.

The RVM is an abstract machine which is capable of executing configcodes. It is independent of the hardware. The configcodes are executed on a target platform through a specific RVM. Thus RVM includes a back end compiler which might provide Just in Time JIT or Ahead of Time AOT method for compilation of configcodes into executable codes.

The radio library consists of function blocks representing the computational basis. The radio application can be expressed as a set of these interconnected function blocks. Function blocks of the radio library are represented in the normative language of the radio platform. The native implementation of the radio library provides executable codes of function blocks from the library for the target platform. The radio library is extendable.

Operational structure of unified radio applications may be represented considering two different cases. One case is when RA configcodes are executable on a target radio platform illustrated in and the other case is when RA configcodes are Intermediate Representation IR that is to be back end compiled at a given mobile device illustrated in .

Referring to a radio and user defined function blocks UDFB library needed for execution of a given radio application are included in executable configcodes of the radio application.

Meanwhile referring to user defined function blocks needed for execution of a given radio application are included in the configcodes of the radio application and should be back end compiled by RVM shown in . In this case since the radio library cannot be included in the radio application configcodes a native implementation of the radio library should be additionally prepared in a given mobile device. Usually the native implementation of the radio library is provided by a core chip vendor because the radio library includes standard function blocks SFB implemented on the core processor.

Basically the radio library i.e. native implementation which can be implemented without dedicated hardware accelerator s are necessary for enhancing speed of the standard function blocks and for generating other standard function blocks by combining accelerator s and program codes.

For both a case when the radio application configcodes are executable codes and a case when the radio application configcodes are intermediate representation the standard function blocks are supported by dedicated hardware logic accelerator s through the radio hardware abstract HAL layer shown in and . That is every time when the standard function blocks implemented using dedicated hardware logics are called by given radio application codes the standard function blocks should be executed on the corresponding dedicated hardware logic accelerator s through the radio HAL regardless of whether the radio application configcodes are executable codes or intermediate representation. As explained later the radio HAL also includes hardware abstraction for interfaces prepared for user defined function block library s .

The standard function blocks may be function blocks which are commonly used by various radio applications for example a Fast Fourier Transform FFT block. Also the standard function blocks may be function blocks which should be efficiently implemented using a special purpose accelerator in a given radio platform for example a turbo coder block.

On the other hand a standard function block set UDFB set shown in includes all user defined function blocks which are used by given radio application s . It is important that any standard function block can be modified and or extended by replacing it with a proper standard function block which is a modified and or extended version of the standard function block to be replaced. Therefore some user defined function blocks can be good candidates for standard function block extension which means they might be added as standard function blocks later. In that case after addition they will become atomic as the normal standard function blocks. Since the user defined function block Set UDFB set is to be provided by radio application provider i.e. 3rd party instead of radio platform vendor in order for radio control framework to be able to perform basic controls of every UDFB s event and or command a standard set of control interfaces such as start stop pause get port and initialize may have to be specified for the corresponding user defined function blocks. For this purpose an ETSI RRS may specify a standard set of control interfaces for each user defined function block to be implemented properly via the standard set of control interfaces. Specification of the standard control interfaces for user defined function blocks may be given in the document of Protocol Interface technical specification TS . The radio platforms shown in generally comprise both core s and dedicated hardware accelerator s for implementing each of function blocks.

As shown in the operational structure of unified radio applications may comprise the following components.

In the example shown in the number of standard function blocks implemented on a core processor has been set to M and the number of standard function blocks implemented on dedicated hardware logic accelerators has been set to N. As mentioned earlier standard function blocks to be implemented using dedicated hardware logic accelerator such as FFT Turbo decoder Multi Input Multi Output MIMO decoder etc. can be implemented directly on the corresponding dedicated hardware logic accelerator for high performance and low power consumption. Those standard function blocks are supported by the radio HAL for implementation on the dedicated accelerator s . This means that when each of standard function blocks to be implemented on the dedicated accelerator is called in a radio application it is executed directly on the corresponding dedicated accelerator through the radio HAL. Similarly when each of standard function blocks to be implemented on core processor such as bit reverse multiply and accumulation etc. is called in RA it is executed on a given core e.g. ARM with Neon .

Consequently the execution codes required on a radio processor consists of the following two parts. One part is execution codes for standard function blocks executed on programmable core s and the other part is radio HAL codes for standard function blocks implemented on dedicated accelerators.

This can be summarized as follows. C execution code required on RP for SFB implementation A execution codes for SFBs implemented on programmable cores B Radio HAL codes for SFBs implemented on accelerators. That is C A B where A and B may be determined by each vendor.

This may also mean that SFBs SFBs implemented on core processor SFBs implemented on dedicated hardware accelerators and SFBs implemented on core processor SFBs implemented on dedicated hardware accelerators .

Meanwhile UDFB as mentioned earlier should be written with standard interfaces. As shown in it should be observed that the standard interfaces of UDFB might be associated with either SFB s implemented on core processor or SFB s implemented on dedicated hardware accelerator or both.

The reason why we classify standard interfaces into two groups i.e. the one corresponding to SFB s implemented on core processor and the other corresponding to SFB s implemented on dedicated hardware accelerator is that each category has its own pros and cons. The latter since it is implemented on dedicated hardware logic is advantageous for power consumption speed up operation and probably cost effectiveness. On the contrary the former since it is implemented on microprocessor is advantageous mainly for flexibility. It is expected that the dedicated hardware accelerator s will be used relatively more widely at the beginning stage until programmable devices become competitive to dedicated hardware devices in performance. As semiconductor technology evolves more and more the core dependent SFB will gradually become more and more dominant compared to the core and peripheral dependent SFB in a long term standpoint and be implemented via Instruction Set Architecture ISA level acceleration.

The granularity of the standard function blocks shown in the present specification are just for the purpose of explanation and the standard function block interfaces may be defined in other documents as mentioned earlier.

Hereinafter procedures of interfacing between a radio control framework and a radio application for embodying installation uninstallation creating deleting of instances and operations of the unified radio application will be explained as examples.

In each solid line between two blocks denotes a reference point defined between the two blocks through which direct interactions between the two blocks are performed. Also each dotted line between two blocks denotes that interactions between the two blocks is performed through radio OS based on commands issued by a corresponding block. As will be explained later blocks in RCF i.e. CM RCM MRC and RM issue the command for the interaction to take place at the unified radio application through the radio OS.

The definition of each reference point is based on the three kinds of interfaces MURI which are interfaces between components of communication services layer and those of RCF URAI which are interfaces between URA and component of RCF and Reconfigurable Radio Frequency Interfaces RRFI which are interfaces between URA and Radio Frequency RF part. In addition to MURI URAI and RRFI interfaces between components of RCF have also been defined as reference points. In the present document we classify the reference points according to procedures of their functions such that the classification of each of the reference points becomes coincident with each of the procedures which will be described later.

1 Reference Point 1 Interfaces for Installation Uninstallation and Creating Deleting Instance of Radio Application

Referring to CFis an interface between an administrator and a configuration manager CM which is for the administrator to request CM to perform installing uninstalling of RA or for the administrator to receive response of the request from CM.

CFis an interface between a mobility policy manager MPM and CM which is for MPM to request CM to perform creating instance or deleting instance of RA or for MPM to receive response of the request from CM.

CF is an interface between CM and a multiradio controller MRC which is for CM to request MRC to send parameters related to radio resources to CM or for CM to receive response of the request i.e. the parameters related to radio resources from MRC during the procedure of creating instance of RA.

CF is an interface between CM and a resource manager RM which is for CM to request RM to send parameters related to computational resources to CM or for CM to receive response of the request i.e. the parameters related to computational resources from RM during the procedure of creating instance of RA.

Referring to CFis an interface between the administrator and CM which is for the administrator to request CM to send the RA list to Administrator or for Administrator to receive response of the request i.e. the RA list from CM.

Reference Point CFis an interface between MPM and CM which is for MPM to request CM to send the RA list to MPM or for MPM to receive response of the request i.e. the RA list from CM.

Referring to CTRLis an interface between the MPM and a radio connection manager RCM which is for MPM to request RCM to perform activation deactivation of radio applications or for MPM to receive response of the request i.e. activation deactivation of RA from RCM.

Referring to CII is an interface between Monitor and RC in RA which is for Monitor to request RC in RA to send context information to Monitor or for Monitor to receive response of the request i.e. the context information from RC in RA.

The context information is generated from corresponding function block s of RA s and transferred to RC. There should be interfaces between RC within a radio application and each of corresponding function blocks. This means that BBI for transferring context information between the RC and each of the corresponding function blocks should be defined.

5 Reference Point 5 Interfaces for Creating Data Flow and Sending Receiving User Data is a diagram illustrating reference points for creating data flow and sending receiving user data.

Referring to CTRLis an interface between MPM and RCM which is for MPM to request RCM to form data flow or network association with peer equipment or for MPM to receive response of the request from RCM.

Reference Point CTRL is an interface between RCM and FC which is for RCM to request FC to form data flow or for RCM to receive response of the request from FC.

Reference Point DCTRL is an interface between FC and Networking stack which is for FC to receive transfer user data from to Networking stack for the procedure of sending receiving data. It also includes an acknowledgement of transmit user data from FC to Networking stack upon completion of sending data. It also includes an acknowledgement of transmit user data from FC to Networking stack upon completion of sending data.

Reference Point DCTRL is an interface between FC and RA which is for FC to transfer the transmit user data to RA and to request RA to transfer the information of transmit user data such as throughput data bandwidth etc. to FC. DCTRL interface is also used for FC to receive response of the request from RA. In the case of the procedure of receiving data DCTRL interface is used to transfer the receive user data from RA to FC.

Reference Point DCTRL is an interface between RA and RF transceiver XCVR with antenna s which is for RA to receive transfer receive transmit user data from to RF XCVR with antenna.

The administrator sends a DownloadRAPReq signal including a RAP identification ID to a radio apps store.

The administrator receives the DownloadRAPCnf signal including RAP ID and RAP from the radio apps store.

The administrator sends an InstallRAReq signal including RAP ID to CM to request radio application installation.

CM first performs the procedure of certifying the RA code in order to verify its compatibility authentication etc.

The CM sends an InstallRAReq signal including RAP ID to File Manager FM to perform installation of RA.

FM performs installation of RA and transfers InstallRACnf signal including RA ID to CM which transfers InstallRACnf signal including RA ID to Administrator.

In the case when the downloaded RA is IR CM first sends CompileReq signal including RAP ID to Back end Compiler in advance of RA installation. After completion of back end compilation Back end Compiler transfers CompileCnf signal including RAP ID to CM which performs the procedure of certifying usability of the back end compiled RA code.

In the case of installation failure CM reports Administrator the failure of RA installation using InstallRAFailCnf signal including RAP ID and failure reason.

FM performs uninstallation of RA and transfers UninstallRACnf signal including RA ID as an acknowledgement of uninstallation completion to CM.

For creating instance of installed RA MPM transfers InstantiateRAReq signal including ID of RA to be instantiated to CM.

The CM transfers a RMParameterReq signal and a MRCParameterReq signal including ID of RA to get parameters needed for RA activation e.g. Forward Error Correction FEC parameters MIMO parameters bandwidth etc. to RM and MRC.

The CM receives a MRCParameterCnf signal including ID of RA and computational resource parameters from MRC.

Upon completion of receiving parameters needed for RA activation the CM transfers RA ID and the parameters for performing the RA instantiation to the radio OS.

Upon completion of creating instance the CM transfers an InstantiateRACnf signal including RA ID to MPM.

When the CM fails to get parameters needed for RA activation from RM and or MRC RM and or MRC reports the failure of parameters transfer to the CM using RMParameterFailCnf and or MRCParameterFailCnf respectively.

If the creating instance of RA fails i.e. CM receives RMParameterFailCnf and or MRCParameterFailCnf signal CM reports the instantiation failure to MPM using InstantiateRAFailCnf signal.

Upon the request of the CM for the radio OS to perform deleting instance of RA the radio OS deletes the instance of designated RA.

Upon completion of deleting instance the CM acknowledges deleting instance of RA to MPM using a DeInstantiateRACnf signal.

Referring to the procedure of checking the list of installed instantiated active radio applications can be described as follows.

The administrator or MPM transfers a ListRAReq signal to CM for obtaining the radio application list.

Upon the request of the RCM for the radio OS to perform RA activation ROS activates the designated RA.

After the radio OS completes the activation of RA RCM acknowledges the completion of RA activation by sending ActivateCnf signal to MPM.

If RA activation is failed RCM reports the failure of RA activation to MPM by transferring the failed RA ID and failure reason in ActivateFailCnf signal.

In the case of hard deactivation MPM transfers a HardDeactivateReq signal including ID of RA to request hard deactivation of the designated RA to RCM.

Upon the request of RCM for the radio OS to perform hard deactivation of RA the radio OS deactivates the designated RA.

After the radio OS completes the hard deactivation of RA RCM acknowledges the completion of hard deactivation of RA by sending a HardDeactivateCnf signal to MPM.

Meanwhile in the case of soft deactivation MPM transfers a SoftDeactivateReq signal including ID of RA to request soft deactivation of the designated RA to RCM.

Upon the request of RCM for the radio OS to perform soft deactivation of RA the radio OS deactivates the designated RA.

After the radio OS completes the soft deactivation of RA RCM acknowledges the completion of soft deactivation of RA by sending SoftDeactivateCnf signal to MPM.

Referring to a procedure for a radio application to transfer context information to a monitor or a baseband parameter aggregation BPA unit can be described as follows.

The RC in the radio application transfers a ContextInformation signal including RA ID and context information generated in corresponding function block s in RA to the monitor.

In the case of using the BPA unit RC of the radio application transfers a ContextInformation signal including RA ID and context information to the BPA unit. Then the BPA unit aggregates and compresses the context information to minimize the bandwidth occupied by the context information to be transferred. Upon completion of the procedure of context information aggregation and compression the BPA unit transfers an AggregatedMetric signal including RA ID and aggregated metric s to the monitor.

In the case of generating context information failure RC of the radio application transfers a ContextInformationFailCnf signal including to RA ID and failure reason to the monitor.

5 Procedure for Creating Data Flow and Sending Receiving User Data is a signaling diagram illustrating a procedure of creating a network association.

The MPM transfers an AssociateReq signal including RA ID and peer equipment ID to RCM. The peer equipment may be Wireless Local Area Network WLAN access point s Internet Protocol IP access node s such as Gateway General Packet Radio Service GPRS Support Node GGSN etc. in cellular networks or Bluetooth headset digital radio television broadcasting station s Global Positioning System GPS satellite s etc.

Upon the request of the RCM for the radio OS to perform creating the network association the radio OS transfers an AssociateReq signal from RCM to RA. Then the radio application transfers ID of corresponding peer equipment using a NetAssociateReq signal.

Upon completion of creating the network association the peer equipment transfers a NetAssociateCnf signal to the radio application. Then the radioOS transfers an AssociateCnf signal to RCM which transfers the AssociateCnf signal to MPM.

In the case of creating the network association failure the peer equipment transfers a NetAssociateFailCnf signal to the radio application. Then the radioOS transfers an AssociateFailCnf signal to RCM which transfers the AssociateFailCnf signal to MPM.

The MPM transfers a CreateDataFlowReq signal to RCM including peer equipment ID active RA ID and user ID in order to associate a logical radio link with another mobile device MD .

The RCM requests the radio OS to create a data flow using a CreateDataFlowReq signal including peer equipment ID active RA ID user ID and another MD user ID. The radio application transfers corresponding user ID another MD user ID and peer equipment ID using a LogicalRadioLinkReq signal to the peer equipment.

Upon receiving a LogicalRadioLinkReq signal including user ID and another MD user ID from the peer equipment the network transfers a LogicalRadioLinkCnf signal including a logical link ID to the peer equipment.

Upon transferring the LogicalRadioLinkCnf signal including the logical link ID from the peer equipment to the radio application the radio OS transfers a CeateDataFlowCnf signal including a network association ID the RA ID and the logical link ID to RCM.

In order to set up data flow the RCM transfers a CreateFlowReq signal including the network association ID and the RA ID to FC. After creating the data flow FC transfers a CreateFlowCnf signal including the network association ID the RA ID and the created data flow ID to RCM.

The RCM transfers a CreateDataFlowCnf signal including the network association ID the RA ID and the data flow ID to MPM.

When the radio application receives the LogicalRadioLinkRej signal from the peer equipment the radio OS transfers a CreateDataFlowFailCnf signal including the network association ID and failure reason to RCM. The RCM transfers the CreateDataFlowFailCnf signal to MPM to acknowledge the failure of creating the data flow.

A networking stack transfers a DataTransferReq signal together with a data flow ID and user data to FC in order to transfer the user data.

The FC transfers an RAEnvironmentReq signal to the radio application in order to request information about the user data to be transferred to the radio application such as throughput data bandwidth etc.

Upon receiving the RAEnvironmentCnf signal including the data flow ID FC transfers a UserData signal together with the data flow ID and the user data to the radio application.

The radio application transfers the user data including the data flow ID using a TransmitData signal to RF XCVR.

After completion of sending data the radio application acknowledges the completion of sending user data by transferring a DataCnf signal to FC.

Upon receiving the DataCnf signal FC transfers a DataTransferCnf signal together with the data flow ID to the networking stack.

In the case of sending data failure the radio application reports the failure of sending data to FC by transferring a DataFailCnf signal including the data flow ID.

Upon receiving the DataCnf signal FC transfers a DataTransferCnf signal together with the data flow ID to the networking stack.

The RF XCVR with antenna transfers received user data including data flow ID using an ReceiveData signal to the radio application.

The radio application transfers a UserData signal including the data flow ID and the user data to FC after decoding the data received from the RF XCVR with antenna.

The FC transfers a DataInd signal including the data flow ID and the user data received from the radio application to the networking stack.

While the example embodiments of the present invention and their advantages have been described in detail it should be understood that various changes substitutions and alterations may be made herein without departing from the scope of the invention.

