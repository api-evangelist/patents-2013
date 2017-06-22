---

title: Method for distributing, installing and executing software-defined radio application
abstract: Disclosed is a method for distributing, installing and operating software-defined radio-based radio application independent of hardware and a user application. The radio application comprises a radio controller code and a user-defined function block code. A radio application package for distributing and installing the radio application includes pipeline component metadata for constituting a pipeline of the radio application. The user-defined function block code may be provided in the form of an execution code, a source code or an intermediate representation, and the radio controller code and the user-defined function block code may call a standard function block. Accordingly, with the configuration of the radio application of the present invention and the method for distributing, installing and operating the radio application according to the present invention, various wireless communication systems can be used independently of a modem chip just by downloading and installing the radio application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09350848&OS=09350848&RS=09350848
owner: INDUSTRY-UNIVERSITY COOPERATION FOUNDATION HANYANG UNIVERSITY
number: 09350848
owner_city: Seoul
owner_country: KR
publication_date: 20130412
---
The present invention relates to methods for distribution installation and executing of radio applications for a software defined radio SDR terminal and more particularly to methods for distribution installation and executing of SDR radio applications which operate independently on hardware and user applications.

As communication technology advances various new kinds of radio applications are being used as adapted for tastes and objectives of users. The most of radio applications such as a Long Term Evolution LTE a Wide band Code Division Multiple Access WCDMA a Worldwide Interoperability for Microwave Access WiMAX a Global System for Mobile Communications GSM may operate on radio terminals by interworking with a modem embedded in the radio terminal.

In order to make it possible that a radio application controls the modem a customized module should be developed based on understanding unique instructions of each modem designed by various modem manufactures or having various models. This situation leads to a result that a specific application can be executed on a specific modem designed by a specific manufacturer or even on a specific model of modem designed by the specific manufacturer. To overcome the above mentioned problem different control instruction codes customized for various kinds of modems should be comprised in the radio application or different executable file for each modem should be built and distributed.

However since it is practically impossible to optimize the radio application to all the various kinds of modem hardware currently available in the market currently by the above mentioned methods there is a problem that a great manpower is needed to develop a radio application.

In order to resolve the above described problems the present invention provides methods for distributing software defined radio applications which operate independently on hardware and user applications.

In order to resolve the above described problems the present invention also provides methods for installing software defined radio applications which operate independently on hardware and user applications.

In order to resolve the above described problems the present invention also provides methods for operating software defined radio applications which operate independently on hardware and user applications.

In some example embodiments of the present invention a radio application distribution method using a radio application package for installing a radio application into a terminal the method may comprise generating a radio application package and uploading the radio application package to a server wherein the radio application package includes radio controller codes function block codes and pipeline configuration metadata.

Here the function block codes may include standard function block codes which are codes calling function blocks implemented using dedicated hardware logics included in a radio processor of the terminal or codes operating on a core of the radio processor of the terminal and user defined function block codes which are not provided as the standard function block codes or which are customized from functions provided by the standard function block codes.

Also when the standard function block codes are provided as execution codes executable on the radio processor of the terminal the radio application package may further include a radio library comprising the execution codes.

Also the user defined function block codes may be at least one of execution codes executable on the radio processor of the terminal source codes which can be compiled into execution codes executable on the radio processor of the terminal and intermediate representation IR codes which can be compiled into execution codes executable on the radio processor of the terminal.

Also when the user defined function block codes are source codes or IR codes the user defined function block codes may be included in the radio application package as encrypted.

Also the pipeline configuration metadata may define relations among the radio controller codes the user defined function blocks and the standard function blocks for data transmission functions or data reception functions of the radio application.

Also the radio controller codes may be execution codes executed on an application processor or the radio processor of the terminal provide a user application with context information of the radio application and transmit receive data with a networking stack of a communication service layer existing on the application processor or the radio processor.

In other example embodiments of the present invention a method for installing a radio application into a user terminal by using a radio application package the method may comprise downloading a radio application package from a server and installing a radio application included in the radio application package into the user terminal wherein the radio application package includes radio controller codes function block codes and pipeline configuration metadata.

Here the function block codes may include standard function block codes which are codes calling function blocks implemented using dedicated hardware logics included in a radio processor of the terminal or codes operating on a core of the radio processor of the terminal and user defined function block codes which are not provided as the standard function block codes or which are customized from functions provided by the standard function block codes.

Also when the standard function block codes are provided as execution codes executable on the radio processor of the terminal the radio application package may further include a radio library comprising the execution codes.

Also the user defined function block codes may be at least one of execution codes executable on the radio processor of the terminal source codes which can be compiled into execution codes executable on the radio processor of the terminal and intermediate representation IR codes which can be compiled into execution codes executable on the radio processor of the terminal.

Also when the user defined function block codes are source codes or IR codes the user defined function block codes may be compiled using a compiler executed by the application processor or the radio processor of the terminal.

Also when the user defined function block codes are source codes or IR codes the user defined function block codes may be included in the radio application package as encrypted.

Also the radio controller codes may be execution codes executed on an application processor or the radio processor of the terminal provide a user application with context information of the radio application and transmit receive data with a networking stack of a communication service layer existing on the application processor or the radio processor.

Also in the installing the radio application the radio controller codes and the function block codes may be installed into a storage device which can be accessed by at least one of an application processor and a radio processor of the terminal by referring to the pipeline configuration metadata.

In still other example embodiments of the present invention a method of executing a radio application comprising function block codes and radio controller codes in a terminal having an application processor and a radio processor the method may comprise receiving an execution instruction for the radio application and loading the radio controller codes and the function block codes from a storage part by referring to pipeline configuration metadata of the radio application wherein the radio controller codes are executed by the application processor or the radio processor and the user defined function block codes are executed by the radio processor.

Here the function block codes may include standard function block codes which are codes calling function blocks implemented using dedicated hardware logics included in a radio processor of the terminal or codes operating on a core of the radio processor of the terminal and user defined function block codes which are not provided as the standard function block codes or which are customized from functions provided by the standard function block codes.

Also a radio control framework which operates on at least one of the application processor and the radio processor may provide the radio controller codes and the function block codes with operation environments.

Also when the radio control framework operates on both the application processor and the radio processor the radio control framework may be configured to comprise a part executed on the application processor and a part executed on the radio processor.

Also when the radio control framework operates on both the application processor and the radio processor the radio controller codes may operate on the application processor.

Also when the radio control framework operates only on the radio processor the radio controller codes may operate only on the radio processor.

Also the radio control framework may include at least one of a configuration manager CM performing installation uninstallation of the radio application and creating deleting an instance of the radio application and managing radio parameters for the radio application a radio connection manager RCM performing activation deactivation of the radio application and managing user data flow switching between radio applications a flow controller FC controlling sending receiving and flows of user data packets a multi radio controller MRC scheduling requests for spectrum resources issued by radio applications and a resource manager RM sharing radio resources with radio applications.

When a software defined radio terminal apparatus according to the present invention as described above is used the same application may be executed in terminals having modem chips with different structures thorough a standard baseband API. Also by providing various digital signal processing algorithms needed in wireless digital communication based on the standard baseband API for optimal digital signal processing manufacturers of modem hardware may select hardware or software implementation according to complexity and power consumption of each block included in the standard baseband API and producers of radio applications may produce radio applications which are independent of the modem hardware using the standard baseband API. Also various extensions of the baseband API may be possible by providing user defined type blocks to implement functions not included in the standard baseband API.

The present invention may be variously modified and may include various embodiments. However particular embodiments are exemplarily illustrated in the drawings and will be described in detail. However it should be understood that the particular embodiments are not intended to limit the present disclosure to specific forms but rather the present disclosure is meant to cover all modification similarities and alternatives which are included in the spirit and scope of the present disclosure. Like reference numerals refer to like elements throughout the description of the drawings.

Relational terms such as first second A B and the like may be used for describing various elements but the elements should not be limited by the terms. The terms are used solely for distinguishing one element from another. For instance without departing the scope of the present disclosure a first element may be named as a second element and similarly a second element may be named as a first element. The term and or encompasses both combinations of the plurality of related items disclosed and any item from among the plurality of related items disclosed.

It will be understood that when an element is referred to as being connected or coupled to another element it can be directly connected or coupled to the other element or intervening elements may be present. In contrast when an element is referred to as being directly connected or directly coupled to another element there are no intervening elements present.

The terminology used herein is not for delimiting the present invention but for describing the specific embodiments. The terms of a singular form may include plural forms unless otherwise specified. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this invention belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

Hereinafter preferred embodiments according to the present invention will be described in detail with reference to the accompanying drawings. In describing the invention to facilitate the entire understanding of the invention like numbers refer to like elements throughout the description of the figures and a repetitive description on the same element is not provided.

Terminologies used for explaining the present invention are defined as follows. Other terminologies except the following terminologies will be defined in the corresponding part of the present specification.

Referring to and a radio software architecture according to the present invention may comprise an application processor layer which operates on an application processor AP and a radio processor layer which operates on a radio processor RP . Here the radio processor may be also referred to as a baseband processor BP .

A non real time OS such as Android OS of Google iOS of Apple etc. may operate on the application processor and a real time OS hereinafter referred to as a radio OS may operate on the radio processor. Hereinafter for clear discrimination the non real time OS operating on the application processor layer may be referred to as OS and the real time OS operating on the radio processor layer may be referred to as radio OS .

Hereinafter the application processor layer the radio processor layer and components constituting the radio control framework will be described in detail.

If the radio control framework is configured to operate on the application processor and the radio processor both as shown in an application processor layer part of the radio control framework may exist on the OS. If the radio control framework is configured to operate only on the radio processor as shown in the radio control framework does not exist on the application processor layer.

If the radio control frame work operates on both the processors a composition of a communication service layer may exist on the OS of the application processor.

The communication service layer may be a layer providing at least some of the following three services to the radio control framework.

The first service is related to an administrative. It may be a service related to installation uninstallation of radio applications creating deleting instance of radio applications and acquisition of a list of radio applications in each status installed instanced activated .

The second service is related to connection control. It may be a service related to activation deactivation of radio applications creation of data flow creation of network allocation and acquisition of a list of radio applications in each status installed instanced activated .

The third service is related to data flow. That is this service is a service related to sending receiving user data.

As an example of communication service layer configurations for providing at least some of the above described three services the communication service layer may be configured to comprise an administrator application a mobility policy manager application a networking stack i.e. a protocol stack operating on the communication service layer and a monitor application.

However the communication service layer may comprise only some of the above described components and may further comprise additional components as well as the above described components. Also one or more components among the above components may be integrated into a single component existing within the communication service layer. Also the above described components are only examples of components which the communication service layer can comprise in order to support services which should be performed by the communication service layer. That is the communication service layer may be defined based on functions performed by it. The above described exemplary composition of components does not restrict composition of the communication service layer.

In the configuration in which the radio control framework operates on both the AP and the RP the composition of radio applications and to which distribution installation operation methods according to the present invention are applied may respectively comprise application processor layer parts and and radio processor layer parts and . A radio controller RC which is the application processor layer part of radio application may be configured to transmit context information to a monitor application of the communication service layer transmit data to a networking stack of the communication service layer and receive data from the networking stack.

If the radio control framework is configured to operate on both the application processor and the radio processor as shown in a radio processor layer part of the radio control framework may exist on the radio OS. If the radio control frame work operates only on the radio processor as shown in the radio control framework does not exist on the application processor layer. That is the radio control framework exists only on the radio processor layer.

Since role and configuration of the communication service layer illustrated in are identical to those of the communication service layer illustrated in redundant explanations are omitted.

Radio controllers and of respective radio applications may be configured to transmit context information to a monitor application of the communication service layer transmit data to a networking stack of the communication service layer and receive data from the networking stack.

A multi radio interface MURI is an interface between the communication service layer and the control framework and a unified radio application interface URAI is an interface between the radio application and the control framework.

A radio application is an application enabling communications of a mobile terminal and may be distributed in form of a radio application package. Components of a radio application package may be configured as follows.

4 Radio library a radio library is distributed in form of executable codes as included in a radio application package when the standard function blocks SFB are distributed as executable codes.

The radio application package may be downloaded onto the OS of the application processor layer and the user defined function block codes and the radio library may be loaded from the application processor to the radio processor by referring to the pipeline configuration metadata and finally loaded to the radio OS on the radio processor layer.

The radio control framework RCF or is a component for providing operation environment of radio applications.

If the radio control framework is configured to operate on both the application processor and the radio processor as shown in components of the radio control framework may be classified into two groups and . That is one group operates on the application processor and other group operates on the radio processor. Which components of the RCF operate on the radio processor i.e. in real time and which components of the RCF operate on the AP i.e. in non real time may be determined differently by each vendor.

If the radio control framework is configured to operate only on the radio processor i.e. a configuration of the radio control framework exists only on the radio processor layer without discrimination of a radio processor layer part and an application processor layer part.

Basically the RCF may include at least some of the following 5 components for managing radio applications.

However the radio control framework may comprise only some of the following 5 components and may further comprise additional components as well as the following 5 components. Also one or more components among the following components may be integrated into a single component existing within the radio control framework.

The role of the radio control framework may be defined based on functions performed by the components which will be described. The following exemplary components do not restrict composition of the radio control framework. That is the radio control framework may have various configurations at least some of functions of the following components.

1 Configuration Manager CM Installation uninstallation and creating deleting instance of radio applications into RP as well as access management of radio parameters for radio applications.

2 Radio Connection Manager RCM Activation deactivation of RAs according to user requests and overall management of user data flows which can also be switched from one RA to another.

3 Flow Controller FC Sending and receiving of user data packets and controlling the flow of signaling packets.

4 Multiradio Controller MRC Scheduling the requests for radio resources issued by concurrently executing RAs and detecting and managing the interoperability problems among the concurrently executing RAs.

5 Resource Manager RM Managing the computational resources to share them among simultaneously active RAs and to guarantee their real time requirements.

Methods for Distribution Installation and Operation of Radio Applications According to the Present Invention

The user defined function block codes included in a radio application according to the present invention may be provided in at least one of source code form executable code form i.e. object code form and intermediate representation IR form or two or more forms can be combined and provided . According to the provided forms at least one of distribution installation and execution methods shown in may be selected.

For example illustrates a process in which user defined function block codes in source code form are distributed and executed and illustrates a process in which user defined function block codes and standard function block codes radio library are distributed together in executable code form and executed and illustrates a process in which user defined function block codes in IR form are distributed and executed.

Hereinafter composition of a radio application package RAP for distribution of a radio application according to the present invention will be explained in detail.

As explained earlier a radio application according to the present invention may comprise function blocks and a radio controller and a radio application package may be configured to comprise user defined function block codes radio library and radio controller codes for them. Thus the radio application package for distribution of radio application may basically comprise user defined function block codes and radio controller codes . Also it may further comprise pipeline configuration metadata .

The radio controller codes may be determined to be included in the radio application package in executable code form of either the radio processor or the application processor according to software architecture environment explained through and . That is if the radio control framework is divided into the application processor layer part and the radio processor layer part the radio controller codes may be configured as codes executable on the application processor. Otherwise if the radio control framework is executed only on the radio processor the radio controller codes may be configured as codes executable on the radio processor. Meanwhile the user defined function block codes are codes which always operate on the radio processor and so the radio application package may include the user defined function block codes in executable code form of the radio processor in source code form or in IR form.

A pipeline means a combination of radio controller user defined function blocks and standard function blocks for implementing transmission or reception functions of the radio application and their relations and may be defined based on the pipeline configuration metadata.

Also if the standard function block codes are configured as codes executable on cores of the radio processor the radio application package may be configure to further comprise radio library in executable code form executable code of the radio processor cores as explained earlier.

The radio application package may be downloaded from a server onto the OS of the application processor layer and the user defined function block codes and the radio library may be loaded from the application processor to the radio processor by referring to the pipeline configuration metadata and finally loaded to the radio OS on the radio processor layer.

Referring to a process from distribution to execution of radio applications according to the present invention may comprise three steps including a design and distribution time an installation time and a run time.

A design distribution step of of of is a step in which a radio application is designed and distributed. A radio application supplier generates a radio application package comprising radio controller codes and user defined function block codes for implementing the radio application. Here the radio controller codes and the user defined function block codes are written to call standard function blocks by using standard baseband API header defining standard baseband interfaces. Meanwhile the radio controller codes may be included in the radio application package in executable code form through a compiler .

In the user defined function block codes are also included in radio application packages to via compilers to in executable code form. In the user defined function block codes are included in a radio application package via a front end compiler in intermediate representation form.

Also when the user defined function block codes are distributed in source code form as shown in the user defined function block codes may be distributed in encrypted source code form via an encryptor which is an optional component. If the user defined function block codes are distributed in source code form the user defined function block codes may be compiled in a terminal which will execute the user defined function block codes and thereby device independency of the user defined function block codes may be achieved.

Meanwhile as shown in when the user defined function block codes are distributed in executable code form which can be directly executed in a terminal the user defined function block codes may be compiled by a compiler suitable for an execution environment of the terminal among various compilers to and included in the radio application package in executable code form . . . . Also the radio library which is a set of standard function blocks which operate on cores of the radio processor may be compiled by a compiler suitable for execution environment of the terminal and included in the radio application package to in executable code form.

The radio application package generated according to the above described procedure may be uploaded to a distribution sever e.g. radio application store and and then downloaded to a terminal desiring to use the corresponding radio application.

Referring to a user may access an on line app store via a terminal select a desired radio application in a list of radio applications provided by the on line app store which support various radio access technologies and download a radio application package corresponding to the selected radio application.

The various radio access technologies may include Long Term Evolution LTE Wideband Code Division Multiple Access WCDMA Worldwide Interoperability for Microwave Access WiMax Global System for Mobile Communications GSM Radio Frequency Identification RFID and so on. The user may freely select a radio application to be used situationally among a plurality of radio applications which have been downloaded and installed in the terminal.

The install step of of of is a step in which a radio application package is downloaded and installed in a terminal. Here user defined function block codes radio controller codes and pipeline configuration metadata which are included in the radio application package may be installed in the application processor layer or the radio processor layer. That is the radio controller codes may be installed in the application processor layer or the radio processor layer and the user defined function block codes may be installed in the radio processor layer. If the standard function block codes are in executable code form of the radio processor the radio application package may further comprise a radio library including the executable code as mentioned earlier.

Here as shown in if the user defined function block codes are in source code form the user defined function block codes may be complied and generated into at least one executable user defined function block by a compiler i.e. a RP compiler . The compile may operate on the application processor or the radio processor. That is the compiler may perform a role of compiling the user defined function block codes in source code form into the executable code of the radio processor and it may operate on the radio processor or the application processor.

If the user defined function block codes are encrypted the encrypted source code may be compiled after being decrypted by a decryptor which is an optional component.

Referring to the user defined codes may be written in high level language such as C or C during development of the radio application. Optionally the user defined function block codes may be converted into encrypted source codes by an encoder .

The encrypted source codes generated in the above described manner may be distributed to each terminal as included in radio application package. In the procedure of installation to the terminal the encrypted source codes may be converted to machine codes to executable in a modem hardware embedded in the terminal by decoders to and compilers to . Since the compilers to are required to generate machine codes optimized for a modem hardware embedded in the terminal the compilers are dependent on the modem hardware. Radio processor vendors may develop compilers optimized for their radio processors embed the compilers within their radio processors or provide them to vendors of terminals using their radio processors. The compiler optimized for the radio processor may be implemented to operate on the radio processor or the application processor.

Meanwhile if the user defined function block codes are compiled for the terminal and distributed in executable codes the compiling in the install step is not necessary as shown in .

Referring to the user defined function block codes may be written in high level language such as C or C during development of the radio application may be compiled into executable machine codes by one of compilers suitable for corresponding radio processor. These machine codes may be packaged to respective radio application package for each and the radio application packages may be uploaded to a radio application server. The terminal may download the radio application operable in its radio processor . Thus suppliers of modem hardware may produce compilers optimized to their modem hardware and provide them to radio application developers.

Referring to the radio application installation step may be performed in the application processor or the radio processor. That is the compiler and the storage illustrated in may exist in at least one of the application processor and the radio processor or in both the application processor and the radio processor.

The run time of of of is a step in which an installed radio application is executed in an actual terminal. In this step corresponding components of the radio application for radio signal processing may be loaded on the application processor or the radio processor and executed for performing radio communications.

For example when an execution command of the radio application installed in the terminal is received a loader and may determine which function blocks are needed for executing the radio application by referring to the pipeline configuration metadata and . Based on this a radio controller and user defined function blocks may be loaded from the storage and of the terminal. Also the loader loads radio controller codes into the application processor layer or the radio processor layer as mentioned earlier it is determined according to operation layer of the radio controller framework which layer the radio controller codes are loaded into and the user defined function blocks and standard function blocks may be loaded into the radio processor layer by referring to the pipeline configuration metadata.

A standard function block pool or is a set of standard function blocks and exists in the radio processor layer or in the application processor layer. In the standard function block pool there may exist standard function blocks implemented using dedicated hardware and standard function blocks executed on cores of the radio processor. In the step for an installer to install the radio application by referring to the pipeline configuration metadata in the rum time standard function blocks to be used by the corresponding radio application may be selected from the standard function block pool and installed in the storage.

Referring to a standard baseband interface is an application programming interface API standardizing digital signal processing algorithms needed for baseband domain in modem and the standard interfaces and the standard function blocks are shown as an example.

As a type of the standard interface the standard interface may include a transformation a channel coding a network mapper an interleaving and a source coding and so on. Also as standard function blocks for the transformation a spreading a dispreading a scrambling a descrambling a Fast Fourier Transform FFT and an Inverse Fast Fourier Transform IFFT may be defined.

For example Input Out data through the FFT properties of the data and member functions may be defined for the FFT . Also an object oriented design of radio application may be made possible by assigning common properties to function blocks having the same type.

Meanwhile in the example embodiments of the present invention a standard application programming interface API header file which is written in high level language according to the above described standard baseband interface may be used. Therefore a developer of radio application may develop radio applications by referring to the standard interface API header.

Hereinafter a procedure of distributing radio application for a software defined radio terminal according to an example embodiment of the present invention will be explained.

Referring to a procedure of distributing a radio application according to an example embodiment of the present invention may be configured to include a step of encrypting user defined function block codes S a step of generating application package S and a step of distributing application package S.

In addition the step S of generating an application package may comprise a step of generating and compiling user defined function block codes a step of generating and compiling radio controller codes a step of generating pipeline configuration metadata and a step of generating an application package.

As described above radio applications according to the present invention may be distributed in form of application packages each of which comprises user defined function block codes radio controller codes and pipeline configuration metadata. If the user defined function block codes are configured in executable code form the application package may further comprise a radio library in executable code form as explained earlier.

Hereinafter each step of the distribution procedure of radio application according to an example embodiment of the present invention will be explained in detail.

The step of encrypting user defined function block codes S is a step of encrypting the user defined function block codes to be included in a radio application package. The user defined function block codes may be distributed in source code form in intermediate representation IR form or in executable code form according to selection of radio application provider. In the case that the user defined function block codes are distributed in source code form it is desirable that the user defined function block codes are written in standard languages in order to be compiled in various terminals. Meanwhile in the case that the user defined function block codes are distributed in source code form since source codes of the user defined function block codes may be exposed the user defined function block codes may be encrypted before distribution in order to prevent exposure of source codes.

The step of generating application package S is a step of generating a radio application package including radio application to be executed in a software defined radio terminal. As shown in the radio application package may comprise user defined function block codes radio controller codes and pipeline configuration metadata . When the user defined function block codes are in executable code form the radio application package may further comprise a radio library .

The user defined function block codes are codes defining function blocks needed for implementing a desired radio application and the radio controller codes are codes written for performing the above described radio controller functions. Also the function blocks defined by the user defined function block codes are related to implementations of digital signal processing functions which are not implemented in the standard function blocks defined in the standard baseband API header .

On the other hand the user defined function block codes may be constituted as one of codes executable directly in the radio processor of the terminal which the application package is installed to codes in source code form which needs to be compiled for execution intermediate representation and executable codes.

Therefore if the user defined functions block codes are in executable code form the user defined function block codes may be codes compiled by various compilers for various terminals.

The radio controller codes may comprise codes for transferring context information to a monitor of the application layer and for sending receiving user data to or from a networking stack of the application layer. The radio controller codes may be executable codes compiled by compilers so that they can be executed by the application processor or the radio processor.

Meanwhile the pipeline configuration metadata may define function blocks needed for implementing corresponding radio application and connections between the function blocks. Also the pipeline configuration metadata may include information on connections between the standard function blocks included in the standard baseband API header and the function blocks defined by the user defined function block codes and information on initial configuration values for attributes of each of the function blocks.

The user defined function block codes the radio controller codes and the pipeline configuration metadata which have been generated in the above described manner may be uploaded to a server and may be downloaded to the terminal wanting to use the corresponding radio application and installed to the terminal in form of application package .

In the step of distributing application package S the application package which has been in the above described manner may be uploaded to a radio application distribution server and downloaded to a software defined radio terminal wanting the corresponding radio application.

Hereinafter a procedure of installing radio application according to an example embodiment of the present invention will be explained.

Referring to the procedure of installing radio application according to an example embodiment of the present invention may be configured to include a step of downloading application package S and a step of installing application package S.

Hereinafter referring to each step of the installation procedure of radio application according to an example embodiment of the present invention will be explained in detail.

The step of downloading application package S is a step of downloading radio application to be executed in software defined radio terminal from a distribution server. In the step of downloading application package S as shown in the application package comprising the user defined function block codes the radio controller codes and the pipeline configuration metadata may be downloaded from the distribution server to the software defined radio terminal. Here when the user defined function block codes are in executable code form the radio application package may comprise a radio library compiled into executable codes as mentioned earlier.

The step of installing application package S is a step of installing the application package downloaded from the distribution server to the terminal as a form executable by the terminal and may include a step of compiling the user defined codes S a step of installing the compiled user defined codes to the storage Si and a step of loading the user defined function blocks S.

In step S of compiling the user defined function block codes when the user defined function block codes included in the downloaded application package are source codes or intermediate representation type codes which are different from odes that can be directly executed in a core of the radio processor of the terminal the user defined function block codes may be compiled into codes that can be directly executed in the core of the radio processor of the terminal to thereby create user defined function blocks.

Also if the user defined function block codes are encrypted the user defined function block codes are compiled after being decrypted.

Also the step of installing the compiled user defined function block codes to the storage S is a step of installing the pipeline configuration metadata included in the downloaded application package the user defined function blocks defined by the user defined function block codes the radio controller codes and the standard function blocks which include standard command instruction codes based on the predefined standard baseband interface to the storage of the terminal by referring to the pipeline configuration metadata .

The step of loading the user defined function blocks S is a step of loading the user defined function blocks defined by the user defined function block codes included in the downloaded radio application package directly to the radio processor layer. Here if the user defined function block codes are written in code form which can be directly executed on the radio processor the user defined function blocks included in the user defined function block codes may be directly loaded into the radio processor layer without the user defined function block code compiling step S.

While the example embodiments of the present invention and their advantages have been described in detail it should be understood that various changes substitutions and alterations may be made herein without departing from the scope of the invention.

