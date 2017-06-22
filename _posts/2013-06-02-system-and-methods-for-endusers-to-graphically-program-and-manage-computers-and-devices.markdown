---

title: System and methods for end-users to graphically program and manage computers and devices
abstract: A system that enables end-users who are not skilled in the art of traditional computer programming to intuitively program, configure and manage computers and devices and/or systems that contain many computers and devices. End-users connect graphical parts using graphical wires using a graphical user interface. The timing of the messages that are carried in the wires that connect the parts is deterministic, consistent and intuitive to the end-user. Parts and their user-configurable features are typically designed, fully tested and certified by the original equipment manufacturer or independent software vendor. This invention relates to ubiquitous computing, a model of human-computer interaction in which information processing has been thoroughly integrated into everyday objects and activities associated with those objects.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08966438&OS=08966438&RS=08966438
owner: 
number: 08966438
owner_city: 
owner_country: 
publication_date: 20130602
---
This invention relates to a means of programming computers and devices that contain embedded computers using visual programming language VPL .

VPLs described in prior art relate to audiences who already have some skill in traditional textual based computer programming. This invention is unique in that the user of the VPL does not require programming skill.

With this invention end users develop their own application programs for computers and computing devices using a visual graphic programming technique involving Parts and Wires. The Parts represent software modules that are developed and fully tested and certified by Original Equipment Manufacturers OEMs or Independent Software Vendors ISVs . End users can modify exposed properties of a Part but they do not have access to the programming logic within. An optional Programmable Part may be exposed by the OEM ISV if the anticipated user audience includes programmers.

Various prior art describes application of VPLs to one specific scenario. Examples of specific scenarios are web apps test instrumentation digital signal processing and data streaming. This invention is a system for using a VPL to program any computer or computing device for many purposes. A major advantage of this invention is that it enables non programmer end users to program broad categories of end user products such as everyday consumer appliances and toys. This invention would serve well as a model for an industry standard.

In a common scenario OEMs design and test the Parts for the end user to fulfill the needs of a particular product. The end user does not need to know how to program. Instead the end user simply needs to connect the graphical parts with graphical wires and optionally fine tune the behavior of the parts by editing Part properties.

The Parts are pre compiled by the OEM into object code. The part object code is combined with the target device kernel to create a working application.

Users fine tune the behavior of a part instance by editing its properties page. That page is also developed and fine tuned by the OEM.

VPLs present a data synchronization challenge that prior art does not address in a simple and intuitive way for non programmers. Considered from a dataflow perspective a VPL design can contain multiple parallel data paths and looping data paths. This invention incorporates a double buffering of the data output messages in each Part. Double buffering enforces a deterministic lock step message passing behavior. For example if a new message appears at the Input Terminal of the first Part Instance in a sequential chain of three parts a serial pipeline three distinct system clocks occur before possible changes may appear at the Output Terminal of the last Part Instance in the daisy chain. This pipeline behavior is relatively easy for end users to visualize as the timing of the message passing is clear and deterministic.

Double buffering also simplifies the issue of optimizing the use multiple central processing unit CPU cores in order to implement parallel processing. No part has a dependency upon execution order of any other part. Each part may be assigned to an arbitrary CPU and may be executed in parallel with other parts.

A computer or computing device that has a means of connecting to others is a Networkable Computer Entity NCE . This invention relates to a system that enables consumers end users who are not skilled in traditional computer programming to nevertheless program manage and configure Networkable Computer Entities NCEs and enable NCEs to communicate with each other. For example the end user can use their personal computer as a tool for configuring programming and interconnecting devices toys home appliances robotic devices and the personal computer itself.

A small electronic product that contains a computer may be referred to as a device. The device may use a reduced functionality operating system as compared to a traditional PC and its capabilities may be more specialized and limited.

Consider the end user who may own a PC smartphone and one or more devices. Historically the connectivity relationship between these products has been limited. Since devices commonly serve one specific function and cannot be reconfigured or reprogrammed by the average end user this limits the functional utility and end user value of the device. Many devices do not or cannot communicate with the PC or the internet cloud wired or wirelessly . This isolation limits device utility. There is no consistently used communication protocol or messaging system that enables computerized products such as personal computers and devices to communicate with each other as peers. To use the Tower of Babel metaphor they all speak different languages.

Those few appliances devices etc. that do communicate with the PC often use a unique custom proprietary protocol communicating with a custom application running on the PC. Further the end user can usually only configure existing program settings and cannot change the program flow or create a new program. An example is a wireless router that is configurable via a web page allowing the end user to configure its settings but the end user cannot reprogram its core functional behavior.

Many devices are very limited in internal resources and performance and they are commonly pre programmed when manufactured to perform a single very specific task as defined by an internal dedicated computer application. Devices are often not configurable or have limited configuration choices. Examples include but are not limited to the electronic greeting card powered toothbrush digital thermometer home cellar flooding sensor USB storage stick and an electric motor and special effects microcontroller for radio controlled models.

More advanced devices offer additional configurability but typically do not allow the end user with limited or no programming skills to program them without needing to learn a programming language such as a home weather station synthesized musical instrument home automation and management systems robots computer controlled plotters and other products that typically require true real time timing critical performance and animatronics and assorted entertainment appliances such as special effects generators.

This invention includes an architectural model that enables end users to develop their own application programs for NCE products using a visual graphic programming technique involving Parts and Wires. Such Applications are henceforth named Part Graph Applications PGAs .

Here is an example scenario that outlines the steps followed by the end user to create design and deploy a consumer designed application PGA to a small device using a PC. Both the PC and the device are NCEs.

This invention offers a flexible architectural model that is deployed within computers and computing devices to allow diverse computers and computing devices generically referenced as Networkable Computer Entities NCEs to freely communicate with one another and to allow a computer to host a Visual Part Graph Application Designer Tool PGAD whose purpose is to enable end users to visually configure and program the NCE by developing one or more Part Graph Applications PGAs that execute in NCEs.

Professional systems designers and Original Equipment Manufacturers OEMs may design custom implementations of the PGAD in order to accommodate their specific target computers and computer based devices and their intended usage role s . For example the PGAD can be crafted to enable end users to develop a PGA for delivery to and execution within a powerful personal computer. At the opposite extreme a PGAD may be crafted that targets PGA development for a small simple inexpensive embedded device.

PGAD is an application that typically runs in a computer that contains a visual program window and a human input interface with menus and controls a visual list of choosable part types and a visual part graph application area . The end user can pick and choose Parts interconnect the Parts with Wires and set Part properties using a visual user interface keyboard and mouse and or touch input.

PGAD is represented in as a dashed box because it is optional and used in a physical hardware platform that is capable of supporting it.

The Physical Device Hardware Platform is the computer or computing device hardware. This may refer to but is by no means limited to the following types of products 

Physical devices may connect to each other via a wired or wireless link such as Ethernet in which case communications may travel through but is not limited to any of the following network entities mechanisms or arrangements proxy gateway bridge router switch network hub repeater and wireless access point.

Other examples of communication links include USB Bluetooth ZigBee and Near Field Communication NFC . For USB one physical device NCE contains the host USB controller and the other physical device NCE contains the client USB controller .

The Container Operating System COS whether real or virtualized resides in the physical device hardware platform and hosts the NCE. The COS may host more than one NCE. The use of a COS in a physical device is optional for example very small microcontroller based devices can be configured without one in which case the NCE s Master Control Program itself is the effective operating system. The COS may be any operating system including but not limited to personal computer operating systems such as Microsoft Windows Apple OS X and Linux or embedded operating systems such as Windows CE FreeBSD VxWorks and Embedded Linux.

The Visual Part Graph Application Designer Tool PGAD is itself an application or collection of applications used by the end user to develop applications PGAs for an NCE . PGAD itself is custom tailored by a professional software developer to specifically accommodate a particular NCE product and its intended usage scenarios. The professional software developer may collaborate with an OEM who designed a specific targeted Physical Device Hardware Platform. A company that makes software development tools may provide a general PGAD Software Development Kit PGAD SDK targeting the OEMs and developers in order to facilitate development of their specific custom PGA Designer application.

PGAD typically is developed for operation within a PC smartphone or other tool hosting device that meets minimum requirements. For example the PGA Designer s host computer needs to contain human interface hardware memory resources and a communication interface to the target NCE s that the PGA Designer will be programming.

A Networkable Computer Entity NCE presents itself as a discoverable entity in the network cloud. A single physical computing device or computer may manifest itself as more than one entity in the network cloud. The NCE is based on a lowest common denominator baseline specification that can accommodate the limited features and capabilities of extremely simple devices. The baseline can then be extended with higher layer features in order to leverage rich and more extended and or extensible features and capabilities of higher performance computers.

Higher performance devices such as personal computers and servers commonly use state of the art managed code CIL based programming development tools e.g. .NET Framework C XAML WPF Silverlight HTML5 etc. . If the target NCE accommodates managed code there is a strong incentive to develop the NCE using managed code such as C . On the other hand the simplest least expensive computing devices may not have the resources or performance needed for managed code. For such devices the end user may use non managed programming languages such as C C or even native processor assembly language .

Here are a few architectural considerations when designing a system of intercommunicating NCEs that can fully leverage this invention. The architecture should be 

If a PGA is not ready to execute at FindingPga the next state is NoPga where the NCE waits until a PGA is received from an internal or external source.

NCE features and capabilities are scalable. A NCE can expose very simple functionality to other NCEs for example it can be simply a digital home thermometer or it can expose very sophisticated functionality for example it can be a Windows Service application functioning as a librarian service agent on the web that manages and exposes collections of NCE information to other NCEs .

For a diverse community of NCEs to communicate with each other all NCEs use a common protocol i.e. speak the same language and this relationship remains true as new functionality is developed. Formation of a central feature functionality clearing house would be beneficial. For convenience call it the Networkable Computer Standards Organization NCSO . NCSO could manage feature functionality that is common to all Networkable Computers as well as managing custom feature functionality that is unique to a class of Networkable Computers and this functionality can optionally be secured and private to a specific group .

The lowest network messaging layer of the NCE is that which accommodates a command message sent to another NCE and a corresponding response message sent back with no guarantee of a returned response i.e. a connectionless service . A NCE sends a message to exactly one receiver NCE who may reply with a response message.

Higher layer messaging protocols are structured and designed in accordance with the particular needs of each corresponding feature or function. For example a feature that requires two or more state sensitive transactions likely requires that a session is first established between two NCEs in order to use a connection ID to manage the session for the life of the session.

A NCE may contain multiple processors and establish multiple topology relationships between the processors.

Examples of types of services features or functions are represented below. This is not intended to be a complete list.

For devices using write wear limited persistent storage the NCE OS and the library may be placed at the beginning of the download module and the PGA application is located at the end to minimize bit rewriting when re flashing. Also an NCE or PGA image may be deployed to volatile memory e.g. RAM or non volatile memory e.g. flash memory .

Transmission pushing to another NCE or requesting and receiving pulling the following information from another NCE 

Referencing a Part Graph Application PGA is an application typically developed by the end user using the PGA Designer and executes within the NCE.

Data Payload within the Message references or contains either a simple data type for example a Byte a Uint32 or a byte array or a structure that comprises a collection of data types. Custom structures may be defined by the OEM.

A PGA may also be designed in part or in whole via computer automation instead of being designed entirely by an end user technician or programmer.

A PGA may consist of only one Part instance. In this case the implementation of the PGA Designer does not require the ability to connect multiple parts via Wires. In this scenario one embodiment may be that the PGA Designer may offer a simplified visual application representation to the end user that does not include Wires and multiple Parts or if wires are used both ends of each wire connect to the single part.

Further the end user may drag and drop the following visual icons into the same design work area that contains Visual Parts and Visual Wires.

Refer to . Small embedded microcontroller based devices commonly include a built in integrated set of hardware features such as parallel I O A D converters serial communication ports internal timers etc. Furthermore microcontrollers systems on a chip frequently offer the ability to flexibly map and assign physical I O pins to these internal features. Examples include but are not limited to microcontroller offerings from ARM based chip manufacturers as well as Microchip PIC and Silicon Laboratories 8051 processor.

Almost invariably today s microcontroller based devices assign these hard wired pin resources exactly once when a device is powered up in device initialization code. Once initialized that assignment typically remains fixed. The configuration of the microcontroller and its peripherals are often frozen for the life of the device.

This invention offers the ability for the end user to reconfigure the use of the microcontroller s peripheral resources.

The Resource Part type offers the ability to enable the end user to flexibly assign these features within a given end user s PGA.

The PGA Designer manages the full set of hardware features available and automatically prevents hardware features and physical I O pins from being inadvertently used by more than one Part unless a hardware resource is designed to be shared.

Software that services a peripheral hardware resource is called a Hardware Layer Driver . A resource type part that has been assigned to a hardware resource is mapped to corresponding Hardware Layer Driver s . For devices the Hardware Layer Driver typically includes the software that handles one or more hardware interrupts associated with the hardware resource. If a hardware resource does not have an associated hardware interrupt the Hardware Layer Driver may use a hardware interrupt timer that is used to periodically poll the physical resource. The Hardware Layer Driver may allow multiple parts to communicate with the hardware in which case the Hardware Layer Driver is responsible for managing hardware sharing.

When the end user programs a small computing device it is usually for a specific intended use in a specific environment. Switches or jumpers may need to be configured in specific ways for the device to function for its intended purpose in the intended environment.

With the introduction of this invention the physical setup requirements for the NCE can vary depending on how the physical resources are configured by the Resource Parts within the PGA. Physical Setup Requirements Management addresses two needs 

The end user picks and chooses from a collection of available Parts. It is possible for the end user to inadvertently choose two or more Parts that are mutually incompatible with each other because they have conflicting physical or functional requirements.

Refer to Managing resource conflicts between Resource parts for an example Property page for a Resource Part within an NCE design that manages a binary input pin on a device. This example indicates in the Part Status section that the Resource setting conflicts with the setting on another Resource Part in the design. The other part is named Binary Output 1. In this example there is a physical switch S1 that must be set to the OFF position to accommodate the needs of Binary Output 1. At the same time S1 must be set to the ON position to accommodate the needs of Binary Input 1. The operator using PGA Designer must reconfigure one or more Resource Part s settings until there is no longer a reported conflict in the Property Page. The PGA Designer will prevent the PGA from being fully compiled until this conflict is corrected.

A general purpose input output pin on a microcontroller chip might be programmable to serve as a digital input 0 or 1 a single bit output 0 or 1 or it may be configurable for a specialized function such as a bidirectional serial port. Once the end user programs pin the specific purpose of that pin becomes hardwired and it is important that the pin must be connected correctly to the intended electronic hardware.

The Physical Setup Requirements report is automatically generated by the PGA Designer. It reports to the end user 

The end user can review this report to ensure that the device is properly configured and properly connected to other physical hardware devices etc. before deploying the PGA to the device.

Identify whether the chosen Parts have been designed tested and approved for use in various environments such as those in a closed loop feedback human life monitoring system when used appropriately .

Refer to . The OEM can choose to offer the Programmable Part as a choosable part in the PGA Designer. This is a Part whose function is defined through the use of a custom scripted program that defines its behavior. The program within the Programmable Part may be written by end users who have skills in traditional scripted computer language programming. A preferred language platform is managed code for example the C language.

The Programmable Part receives input messages contains part instance specific internal variables and transmits output messages depending on the custom program s response to the input messages.

When a Programmable Part is added to a PGA the end user edits the part instance s Property Page in order to specify the number and name of Part inputs and outputs. For each defined input the end user specifies which message types it can accommodate Int32 Byte etc. . For each defined Output Terminal the end user specifies which message types may be generated by the terminal . By doing so the PGA Designer is aware of the terminal properties so it can determine whether to allow or disallow wire connections between the Programmable Part and other Parts in the PGA.

Refer to for an example of a programmable part script using the C language. The purpose of the automatically generated code bracketed with region endregion is to identify the message type choices that are available for the Input Terminals and Output Terminals.

The program contained with each programmable part is run at every parts enumeration cycle when the PGA is not sleeping.

To maximize overall NCE performance the programmer should include early exit tests near the beginning of the custom program. For example the Compute function above should exit early if no Input Terminals contain new messages.

The offered feature set of the language may need to be restricted if the target device has limited computing power or resources. For example a minimal implementation may contain only very simple arithmetic tests and simple if then statements.

A more feature rich programming language would include the ability to perform database like lookups for example LINQ .

The script language may be interpreted compiled or a mixture of the two. For example the program can be compiled into an intermediate form such as CIL and the CIL might then be either interpreted similar to .NET Micro Framework or compiled JITted.

If the programming operator new is used dynamically during normal program runtime in order to create new instances of class objects this causes memory to be allocated and then deallocated when variables are no longer referenced. This results in the need for a periodic garbage collection to reorganize memory which may produce unacceptable real time performance results. Therefore several options should be considered with respect to memory management 

In order to minimize the performance penalty latency associated with garbage collection one option is to initialize heap memory as a collection of fixed length memory pages. Then manage memory through linked list management. This would impose restrictions on how to use the allocated memory owing to the linked list behavior of the memory.

The memory heap model may be avoided completely if temporary data is maintained only in the following places 

When the end user is testing and debugging the end user may finely tune the conditions that cause the tester debugger to halt by creating a condition that sends a message to a Programmable Part s output pin when the condition is hit and then specifying a debug halt that includes the name of the output and additional debug parameters such as 

A NCE may have multiple PGAs installed in persistent storage such as in flash memory storage and be ready to run. In such cases the PGAs each have an ordinal ID. The PGA that executes by default upon startup has an ordinal ID of zero.

PGA zero can be used to select and launch in turn alternative designs that are preloaded into the NCE designs with ordinal IDs of 1 through n . The OEM may choose to create a special part that the OEM might name the PGA Launcher part. This part is present in the default PGA PGA zero and can make decisions regarding what subsequent runtime to launch PGA designs through n .

For example PGA zero might inspect the NCE hardware host switch settings etc. to determine which working PGA to launch.

PGA zero may also choose to launch a Self Test Part before launching the intended normal runtime PGA. The self test may be optionally invoked depending on whether a switch or push button is engaged when the PGA host hardware is reset.

A Native Application is an application that is created using the conventional programming tools traditionally used when developing conventional software applications for the associated target device. A programmer can write conventional applications that communicate with other NCEs by using the NCE Manager APIs and the Kernel APIs.

The Kernel is roughly analogous to the traditional definition of an operating system kernel including a kernel API library interface. What it contains and does depends on parameters such as the target hardware that it runs in whether or not NCE is hosted nested within another operating system.

Embedded microcontrollers that have minimal resources would likely host a NCE in the complete absence of a host operating system other than NCE itself. In such cases the Kernel must contain the classic low level operating system capabilities to handle 

If the NCE is hosted within another operating system such as Windows or Linux then the above functions may be optionally be disabled or stubbed for example the bootstrap code that is used to initialize memory.

The Hardware Layer Drivers function at the hardware interface layer. These drivers expose a consistent interface to the layers above it enabling the upper software layers to interface with device peripherals in a uniform manner.

If there is no Host Operating System layer in the NCE then the Hardware Layer Driver interfaces directly with the physical hardware in the device performing direct hardware I O and reacting to hardware interrupts.

If there is a Host Operating System layer in the NCE then the Hardware Layer Driver interfaces with the corresponding Host Operating System in order to gain access to peripheral hardware. For example in the case of the Microsoft Windows operating system hardware is accessed using the appropriate Windows APIs those APIs in turn interact with the corresponding kernel mode or user mode device drivers which in turn interact with the peripheral hardware.

Consider a small electronic device whose purpose is to enhance hobby market radio control toys with special audio and video effects and allow the end user to control those effects by leveraging the unused channels in a hobbyist s radio control system. illustrates an Application Development Computer and an Application Destination Computer where the latter computer is a device. Referencing system diagram outlines a model aircraft special effects generator for a working flying scale model P51 Mustang aircraft of World War II vintage. describe the property settings for the Parts found in the example PGA.

The device will reside on board the P51 Mustang model. Radio control transmitter wirelessly connects to radio control receiver where receiver channels throttle 4 Gun and 5 audio volume are used to control sound and lighting effects for a simulated machine gun and to simulate the sound of the Rolls Royce engine that was originally used in the real aircraft.

The hobbyist programs the special effects generator using a PC that is hosting the Visual Part Graph Application Designer Tool. shows the completed design .

Display the Physical Setup Requirements report to the end user. An example of such a report is in . This serves as a checklist for the end user to ensure that the target NCE is setup correctly to accommodate the particular PGA that is being sent to it and to ensure the target NCE is configured correctly switches jumpers cables etc. .

Use a Personal Computer PC to manage a network of home automation devices within a home. The end user creates a custom PGA that runs on the PC and is used to manage the devices in accordance with the end user s needs and desires. The PGA running on the PC can offer a visual representation of all the devices in the household and also offer management monitoring and scheduling capabilities. The NCE implementation in the personal computer uses pure managed code.

Each home automation device serves to control various electrical and electronic devices in the home. The end user can create a custom PGA for each device as desired and fine tune the behavior of each device. Examples of these devices include lamp controllers fan controllers and electronic power switches. The devices are physically located throughout the home. The NCE implementation in these devices uses pure unmanaged native code.

The PC can communicate with the devices and the devices can communicate with each other. For this example these devices use the Zigbee wireless protocol and the PC contains a Zigbee wireless host controller.

A home PC is connected to a small USB device to enable the end user to program a PGA into that device using the PGA Designer software. After programming the user disconnects the device and the device runs standalone. An example would be a programmable greeting card that connects to the PC via a USB cable and the end user can customize its audio and LED effects.

The same setup as above except the device remains connected to the PC. The end user programs the device via the PGA Designer to serve as a functional peripheral to the PC for example as an input device for monitoring weather or collecting data instrumentation . Custom applications on the desktop can interact with the custom programmed device or the device can manifest itself as a keyboard joystick mouse or storage device.

The same arrangement as above except the small devices are simulated via simulation PGAs running in the desktop PC. This enables local setup scenario testing or demonstration of a home automation system before needing to purchase the small device hardware.

Any of the above scenarios except the end user uses virtualized PC technology to create instances of NCEs running within virtual OS instances.

PGA Designer can run the PGA application on the target NCE. Instead of free running the end user can choose to single step the PGA application or simulation . This is accomplished by setting the state of the PGA within the NCE to TestingPga . When in this state the Designer can issue SingleStepCommand s to the PGA. This has the effect of calling SingleSteplterator once.

Single step mode offers the ability to visually monitor the state of the messages being passed between the Parts in the PGA design.

The Properties page contains a debug checkbox. When checked a Message Test control button appears for every Input and Output Terminal in the Part.

Within the visual part click on the Message Test button once. The Part will display a read only value of the message. If the message is too big to feasibly fit into the visual Part only a portion of the message is shown but the end user can click on the message to see the whole thing or create a watch window that appears elsewhere in the Designer.

A second click of the same Message Test button results in displaying a modifiable value within the message i.e. the end user can click on it and change its value in between single steps.

When the end user changes the value of a message manually the PGA Designer tool will send any Part Output Message modifications directly to the target device. When the end user single steps the target device will step SingleSteplterator using the modified Output Messages the modified message s will be used and will propagate to any connected Parts as expected.

The end user can have the PGA Designer automatically launch single step commands at user choosable intervals. This way the end user can control the speed at which the PGA runs while watching the various messages change on the Designer screen. is one representation of a PGA Tester control panel. In the Figure the Start Monitored Run button launches this mode while the Monitored Speed Control slider controls the rate at which timed Single Steps execute.

One possible manifestation is to enable the end user to configure PGA Designer to emit visual and audible feedback as it single steps. For example the Part terminal and the Wire can momentarily flash and an audio effect can be launched each time the message changes value.

The end user can configure Monitored Run so that it will halt running when certain message states or conditions have occurred. The end user specifies the desired break conditions by instructing the PGA Designer to compare message state information against manually entered break criteria. This behavior is similar to Conditional Break as used in other programming environments.

