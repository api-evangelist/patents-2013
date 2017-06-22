---

title: Electronic system with system modification control mechanism and method of operation thereof
abstract: An electronic system and method of operation thereof includes: a control unit for receiving a patterned signal; a recognizer module, coupled to the control unit, for recognizing an unique trigger from the patterned signal; an operation module, coupled to the recognizer module, for detecting an operational mode from the unique trigger; and a change module, coupled to the operation module, for configuring a system state change of a memory sub-system based on the operational mode.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09043780&OS=09043780&RS=09043780
owner: SMART STORAGE SYSTEMS, INC.
number: 09043780
owner_city: Chandler
owner_country: US
publication_date: 20130327
---
The present invention relates generally to an electronic system and more particularly to a system with system modification control mechanism.

All electronic systems require some form of memory or storage. Data storage often called storage or memory refers to computer components and recording media that retain digital data. Data storage is a core function and fundamental component of consumer and industrial electronics especially devices such as computers televisions cellular phones mobile devices and digital video cameras.

Recently forms of long term storage other than electromechanical hard disks have become feasible for use in computers. One of these is flash Electrically Erasable Programmable Read Only Memory EEPROM . Flash EEPROM memory includes a plurality of floating gate field effect transistors arranged as memory cells. NAND flash is one form of non volatile memory used in solid state storage devices. The memory cells are arranged in typical row and column fashion with circuitry for accessing individual cells.

The development of Flash technology has led to the development of Solid State Drives SSD . Solid State Drives are an alternative to hard disk drives HDD and are usually made from flash memory. However Solid State Drives and other such embedded systems that boot and execute firmware stored in a non volatile memory require periodic updates. Usually the update requires physically shorting two electrical points on the hardware which requires the factory or the customer to have access to these points on a circuit board. This physical method of shorting the hardware for updating can present the risk of permanent damage to the product.

Thus a need still remains for safer methods of updating and modifying device settings while eliminating the risk of physical and permanent damage to the device. In view of the increasing demand for storage management of electronic systems it is increasingly critical that answers be found to these problems. In view of the ever increasing commercial competitive pressures along with growing consumer expectations and the diminishing opportunities for meaningful product differentiation in the marketplace it is critical that answers be found for these problems. Additionally the need to reduce costs improve efficiencies and performance and meet competitive pressures adds an even greater urgency to the critical necessity for finding answers to these problems.

Solutions to these problems have been long sought but prior developments have not taught or suggested any solutions and thus solutions to these problems have long eluded those skilled in the art.

The present invention provides a method of operation of an electronic system including receiving a patterned signal recognizing an unique trigger from the patterned signal detecting an operational mode from the unique trigger and configuring a system state change of a memory sub system based on the operational mode.

The present invention provides an electronic system including a control unit for receiving a patterned signal a recognizer module coupled to the control unit for recognizing an unique trigger from the patterned signal an operation module coupled to the recognizer module for detecting an operational mode from the unique trigger and a change module coupled to the operation module for configuring a system state change of a memory sub system based on the operational mode.

Certain embodiments of the invention have other steps or elements in addition to or in place of those mentioned above. The steps or elements will become apparent to those skilled in the art from a reading of the following detailed description when taken with reference to the accompanying drawings.

The following embodiments are described in sufficient detail to enable those skilled in the art to make and use the invention. It is to be understood that other embodiments would be evident based on the present disclosure and that system process or mechanical changes may be made without departing from the scope of the present invention.

In the following description numerous specific details are given to provide a thorough understanding of the invention. However it will be apparent that the invention may be practiced without these specific details. In order to avoid obscuring the present invention some well known circuits system configurations and process steps are not disclosed in detail.

The drawings showing embodiments of the system are semi diagrammatic and not to scale and particularly some of the dimensions are for the clarity of presentation and are shown exaggerated in the drawing FIGS. Similarly although the views in the drawings for ease of description generally show similar orientations this depiction in the FIGS. is arbitrary for the most part. Generally the invention can be operated in any orientation.

Where multiple embodiments are disclosed and described having some features in common for clarity and ease of illustration description and comprehension thereof similar and like features one to another will ordinarily be described with similar reference numerals. The embodiments have been numbered first embodiment second embodiment etc. as a matter of descriptive convenience and are not intended to have any other significance or provide limitations for the present invention.

The term module referred to herein can include firmware or hardware running software or a combination thereof in the present invention in accordance with the context in which the term is used. For example the software being run by hardware can be machine code firmware embedded code and application software. Also for example the hardware can be circuitry processor computer integrated circuit integrated circuit cores a pressure sensor an inertial sensor a microelectromechanical system MEMS passive devices or a combination thereof.

Referring now to therein is shown an electronic system with system modification control mechanism in an embodiment of the present invention. The electronic system includes a memory sub system having a memory controller and a memory array . The electronic system includes a host system communicating with the memory sub system .

The memory controller provides data control and management of the memory array . The memory controller interfaces with the host system and controls the memory array to transfer data between the host system and the memory array .

The memory array includes an array of memory devices including flash memory devices or non volatile memory devices. The memory array can include pages of data or information. The host system can request the memory controller for reading writing and deleting data from or to the logical address space of the storage device that includes the memory array .

The memory devices can include chip selects which are defined as control inputs for enabling the memory devices . Each of the chip selects can be used to control the operation of one of the memory devices . When the chip selects are enabled the memory devices are in active state for operation including reading writing or recycling. This is also true for sub addresses LUNs logical units within a device controlled by one chip select.

Referring now to therein is shown an exemplary hardware block diagram of the memory controller . The memory controller can include a control unit a storage unit a memory interface unit and a host interface unit . The control unit can include a control interface . The control unit can execute software stored in the storage unit to provide the intelligence of the memory controller .

The control unit can be implemented in a number of different manners. For example the control unit can be a processor an embedded processor a microprocessor a hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof.

The memory controller can include a signal envelope follower which is defined as a circuit used to monitor and produce signals. The signal envelope follower monitors or follows the outline of an alternating current AC signal.

The signal envelope follower can use a discrete circuit than the circuit used for the control unit for monitoring and producing signals. The signal envelope follower can also be a component of the control unit . The signal envelope follower can also include hardware or software running on hardware for monitoring or following the outline of an AC signal.

The signal envelope follower can monitor continuous wave signals and produce signals including patterned pulses and signals with direct current envelopes. The signal envelope follower can be configured to recognize unique signals that cannot be recognized by other components of the memory controller . For example the host system of can also include the signal envelope follower for detecting out of band B signaling and for performing speed negotiation operations.

The control interface can be used for communication between the control unit and other functional units in the memory controller . The control interface can also be used for communication that is external to the memory controller .

The control interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the memory controller .

The control interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the control interface . For example the control interface can be implemented with dedicated hardware such is an application specific integrated circuit ASIC configurable hardware such as an FPGA Field programmable Gate Array discrete electronic hardware or a combination thereof.

The storage unit can include hardware control firmware and the software . The storage unit can contain a volatile memory a non volatile memory an internal memory an external memory or a combination thereof. For example the storage unit can be a non volatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The storage unit can include a storage interface . The storage interface can also be used for communication that is external to the memory controller . The storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the memory controller .

The storage interface can include different implementations depending on which functional units or external units are being interfaced with the storage unit . The storage interface can be implemented with technologies and techniques similar to the implementation of the control interface .

The memory interface unit can enable external communication to and from the memory controller . For example the memory interface unit can permit the memory controller to communicate with the memory array of .

The memory interface unit can include a memory interface . The memory interface can be used for communication between the memory interface unit and other functional units in the memory controller . The memory interface can receive information from the other functional units or can transmit information to the other functional units.

The memory interface can include different implementations depending on which functional units are being interfaced with the memory interface unit . The memory interface can be implemented with technologies and techniques similar to the implementation of the control interface .

The host interface unit allows the host system of to interface and interact with the memory controller . The host interface unit can include a host interface to provide communication mechanism between the host interface unit and the host system .

The control unit can operate the host interface unit to send control or status information generated by the memory controller to the host system . The control unit can also execute the software for the other functions of the memory controller . The control unit can further execute the software for interaction with the memory array via the memory interface unit .

The functional units in the memory controller can work individually and independently of the other functional units. For illustrative purposes the memory controller is described by operation of the memory controller with the host system and the memory array . It is understood that the memory controller the host system and the memory array can operate any of the modules and functions of the memory controller .

Referring now to therein is shown an example diagram of the system modification control mechanism of the electronic system of . The example includes three sample signals sent from the host system of to the memory controller of . The signals can include a continuous wave signal which is defined as a non modulated base frequency signal wave with a constant amplitude and frequency.

A patterned signal is defined as a continuous wave signal which includes a pattern of signaling bits for transmission. The patterns of the patterned signal can include active signal envelopes and null signals in specific sequences. The patterned signal can be an out of band signal used for communication between components of the electronic system .

The patterned signal can include a pulse width time and a pulse separation time . The pulse width time is defined as a period of time that a pulse is active or during an active direct current envelope within the signal. For example the pulse width time can indicate that a pulse is on for a duration of 106.7 nanoseconds or 160 unit interval out of band UIOOB .

The pulse separation time is defined as a period of time of a null signal or when the pulse is off within the patterned signal . The pulse separation time can also have a duration of 106.7 nanoseconds and alternate with the pulse width time to compose the pattern or sequence within the patterned signal .

The patterned signal can include a speed negotiation signal . The speed negotiation signal is the out of band signal used in the speed negotiation protocol of SATA devices. For example the speed negotiation signal can include COMREST COMINT and COMWAKE which are used for handshaking between the host system and the memory controller . Further for example the speed negotiation signal can include the pulse width time of 106.7 nanoseconds and the pulse separation time of 106.7 nanoseconds as depicted by T1 in the diagram.

The patterned signal can include a unique trigger which is defined as a signal for modifying settings on the memory sub system of . Instead of being used in speed negotiation the unique trigger can be used to trigger specific modes of operation or to trigger specific actions in the memory sub system . For example the unique trigger can trigger a firmware update for the memory sub system .

The signal of the unique trigger can be different from the speed negotiation signal by having different patterns sequences frequencies durations amplitudes or a combination thereof. The pulse sequences that are associated with the unique trigger can be used to differentiate the patterned signal from another such as the SATA protocol signal used for COMWAKE. For example the durations of the pulse width time can be a ratio from a range of 2 1 to 10 1 to differentiate the unique trigger from the speed negotiation signal .

The unique trigger can include a plurality of different signals that are each tied to a specific mode of operation or action to be performed by the memory sub system . For example the unique trigger can include a first trigger and a second trigger as two examples of the unique trigger .

As an example the first trigger can include a sequence of the pulse width time of T1 and T3 and alternating with the pulse separation time of T2. The duration of T2 can equal 320 nanoseconds UIOOB and the duration of T3 can be three to six times the duration of the T1 time. Because the sequencing of the pulse width time and the pulse separation time of the first trigger is out of characteristic of the speed negotiation signal the risk of false triggering is avoided. For illustrative purposes the first trigger can be the unique trigger that is tied to executing a system recovery of the memory sub system .

Further for example the second trigger can include a time break which is a signal with the pulse width time with a long duration. The long duration of the pulse width time of the time break is to distinguish the signal from the speed negotiation signal for preventing false triggering. For illustrative purposes the second trigger can be the unique trigger that is tied to executing a firmware update of the memory sub system . It is understood that the first trigger and the second trigger can be interchangeable in being tied to specific actions or modes of operation of the electronic system .

It has been discovered that the electronic system eliminates the need for physically shorting two electrical points on the hardware boards of storage devices or the need for an overt hardware interaction by using the patterned signal as the unique trigger to modify settings on the electronic system . For example the specific sequences and patterns within the unique trigger can trigger specific modes of operation of the memory sub system including updating or reverting firmware of the memory sub system . The unique trigger provides an alternative method to physical methods and removes the requirement to disassemble the device to have access to electrical points normally done during pin strapping. Thus the risk to the electronic system is reduced from the danger of physical damage caused by physical tampering.

It has been discovered that the electronic system can use specific sequences for the unique trigger for special device operations outside normal drive operation such as triggering firmware updates using an out of band communications channel. For example the unique trigger can include the first trigger and the second trigger having different aspect ratios for the pulse width time and the pulse separation time to differentiate the unique trigger from other SATA communication protocols for the prevention of false triggering.

It has been discovered that the time break provides the unique trigger that is out of the specifications for the speed negotiation signal such as COMREST COMWAKE or COMINIT signaling which avoids false triggering. The time break includes the pulse width time that is at least three times the width of the pulse width time for COMREST COMWAKE or COMINIT signaling which prevents false triggering of other operations such as speed negotiation.

Referring now to therein is shown a control flow of the memory controller of . The memory controller can include a power module a status module a signal module a recognizer module an operation module a change module and a power cycle module .

In the control flow as an example each module is indicated by a number and successively higher module numbers follow one another. Control flow can pass from one module to the next higher numbered module unless explicitly otherwise indicated.

The control unit of can be coupled to the power module the status module the signal module the recognizer module the operation module the change module and the power cycle module for executing the modules. The power module detects a power up of the electronic system of . The power module can be coupled to the status module and the power cycle module .

The status module checks the condition or state of the memory sub system of . For example the status module can determine that the memory sub system is in a functioning state and is capable of proceeding with data storage operations. The status module can determine if a firmware of the memory sub system is functioning properly. The status module can also determine a non functional state of the memory sub system .

The non functional state is defined as a firmware failure which can cause boot up issues with the memory sub system . For example the non functional state can indicate that the memory sub system is corrupted or an incorrect version of the firmware is installed. The non functional state can be caused by a previous failed attempt at modifying the firmware such as an installation interruption or a power failure during a firmware update.

If the non functional state is detected the status module can also generate a revert signal . The revert signal is the unique trigger of for executing a firmware reset for the memory sub system . For example the memory sub system can be reverted back to an original factory version of the firmware or reverted back to an earlier valid version of the firmware .

The signal module can receive the patterned signal of . For example the signal module can receive the revert signal . The patterned signal can be received from the status module or from the host system of . The host system can also send the patterned signal to the signal module . The signal module can be coupled to the status module the recognizer module the signal envelope follower of and the host system .

The signal module can include a window module . The window module can determine an available period for the signal module to accept the patterned signal . For example the window module can determine that the available period is at all times while the memory sub system is operating. For example the signal envelope follower can be operating in the system background for receiving the patterned signal .

Further for example the window module can determine that the available period is only for a short period after the power up . In this example the patterned signal will not be valid or accepted by the signal module if the patterned signal is sent to the signal module after the available period . The available period can be used to prevent unintended or unauthorized uses for increasing the security and the reliability of the electronic system .

The recognizer module interprets and recognizes the unique trigger from the patterned signal received by the signal module . The recognizer module can differentiate the unique trigger from other examples of the patterned signals . For example the recognizer module can recognize the revert signal as being different from the speed negotiation signal of .

The recognizer module can recognize the patterns within the patterned signal including tracking the pulse width time of and the pulse separation time of . In one example the recognizer module can be coupled to the signal envelope follower of for monitoring and recognizing the unique trigger using the control unit of or a separate and discrete circuit.

For example the recognizer module can use the signal envelope follower for monitoring the first trigger of and the second trigger of . The recognizer module can also use a trigger envelope follower which is a second and dedicated envelope follower than the signal envelope follower for monitoring the patterned signal having the unique trigger .

The unique trigger can include a plurality of different signals that are each tied to a specific trigger for modifying operational settings on the memory sub system . For example the unique trigger can include a version signal an update signal a security signal and a manufacturing signal .

The version signal is the unique trigger for changing the firmware of the memory sub system to a specific version. The update signal is the unique trigger for updating the firmware to the newest available version. The security signal is the unique trigger for enabling and disabling security features of the memory sub system . The manufacturing signal is the unique trigger for enabling and disabling a diagnostic or special factory mode of operation for the memory sub system . The recognizer module can be coupled to the operation module for selecting a mode of operation associated with each of the types of the unique trigger .

The version signal the update signal the security signal the manufacturing signal and the revert signal can have a sequence that is similar to the examples of the unique trigger shown in . For illustrate purposes the version signal can have the same sequence as the first trigger and the update signal can have the same sequence as the second trigger .

The recognizer module can also receive and recognize multiple triggers or multiple instances of the unique trigger . For example the recognizer module can receive the first trigger and subsequently the second trigger for modifying two different settings for the memory sub system in a single power cycle. In this example the first trigger can enable security features in the memory sub system and the second trigger can trigger a diagnostic mode of operation within the same power cycle.

The recognizer module can also recognize if the patterned signal includes multiple triggers within the same transmission. For example the patterned signal received by the signal module can include both the patterns for the first trigger and the second trigger . Two different settings for the memory sub system can be manipulated within a single power cycle using one transmission of the patterned signal .

The operation module selects an operational mode for the memory sub system based on the unique trigger received. The operational mode allows the modification of settings and specific operations of the memory sub system . The operational mode can include modes of operation outside of normal device operation of the electronic system . The operation module can be coupled to the change module for executing modifications.

For example the operational mode can include enabling drive functions including updating the firmware executing special run modes and modifying security settings. The operational mode can include a reset mode a version mode an update mode a security mode and a manufacturing mode .

The reset mode enables a reset of the memory sub system to an original factory condition including the original version of the firmware. For example the operational mode can receive the revert signal from the recognizer module for selecting the reset mode . While in the reset mode the non functional state can be removed from the memory sub system by enabling a reset of the firmware for returning to a functioning state.

The version mode can enable the firmware of the memory sub system to be changed to any previous version of the firmware stored in the memory sub system . For example the version mode can enable the memory sub system to be flashed by any valid version of the firmware that is stored in the storage unit of .

The update mode can enable the firmware of the memory sub system to be updated to a new version after receiving the unique trigger . The new and updated version of the firmware can be stored in the storage unit .

The security mode can enable the toggling of secure erase features built into the memory sub system . The security mode can be enabled or disabled after receiving the unique trigger associated with the mode. The security mode can be used for secure erase operations allowing the information in the memory sub system to be quickly erased or destroyed. The security mode can also be disabled to prevent accidental erasures.

The manufacturing mode can enable the memory sub system to enter into a manufacturing test environment mode or a diagnostic mode after receiving the unique trigger . The manufacturing mode can allow special commands and actions used during the manufacturing stage or repair periods for the memory sub system .

The change module perform a system state change on the memory sub system based on the operational mode selected by the operation module . The system state change is defined as a modification of a setting or modification of the operational mode of the memory sub system . For example the system state change can be a change from one of the operational mode to another of the operational mode .

The system state change can also include a change from the non functional state to another of the operational mode . For example the change module can execute the processes of the reset mode or the version mode to execute a reversion of the firmware . The reversion is defined as a process for reverting the firmware to an original factory version of the firmware or to a previously stored version of the firmware . The change module can be coupled to the storage unit for accessing firmware information.

The power cycle module performs a reboot of the memory sub system . The rebooting of the memory sub system may be necessary after the system state change such as installing a new or different version of the firmware . The power cycle module can be coupled to the power module for detecting the power up . The status module can check the status of the memory sub system after a reboot.

The electronic system describes the module functions or order as an example. The modules can be partitioned differently. For example the power module the status module the signal module the recognizer module the operation module the change module and the power cycle module can be implemented as one module or with lesser number of modules. Each of the modules can operate individually and independently of the other modules.

It has been discovered that the electronic system eliminates the need for physically shorting two electrical points on the hardware boards of storage devices or the need for an overt hardware interaction by using the patterned signal as the unique trigger to modify settings on the electronic system . For example the specific sequences and patterns within the unique trigger can trigger specific modes of operation of the memory sub system including updating or reverting firmware of the memory sub system . The unique trigger provides an alternative method to physical methods and removes the requirement to disassemble the device to have access to electrical points normally done during pin strapping. Thus the risk to the electronic system from the danger of physical damage caused by physical tampering is reduced

It has been discovered that the electronic system can use specific sequences for the unique trigger for special device operations outside normal drive operation such as triggering an update of the firmware using an out of band communications channel. For example the unique trigger can include the first trigger and the second trigger having different aspect ratios for the pulse width time and the pulse separation time to differentiate the unique trigger from other SATA communication protocols for the prevention of false triggering.

It has been discovered that the patterned signal having the unique trigger associated with different version of the firmware allows for the reversion of any version of the firmware that is available. For example various versions of the firmware can be stored on the memory sub system and each version of the firmware can be tied to a different trigger signal. The unique trigger associated with different versions of the firmware allows for flexibility in installing and modifying the firmware on the memory sub system .

It has been discovered that the available period provides security and reliability to the electronic system by determine time periods for accepting the unique trigger . For example the available period can be for all times during operation of the memory sub system or for a short period after the power up . The discovery of the available period can be used to prevent unintended or unauthorized modifications to the electronic system .

It has been discovered that the electronic system increases the speed and efficiency of the burn in and bring up processes during the manufacturing stage of a large number of devices because the unique trigger can be sent to multiple devices simultaneously. Further for example the unique trigger sent to the memory controller eliminates the need to attach special cables to each device during a volume manufacturing process and thus also provides additional efficiency to the manufacturing and testing stages of the electronic system .

It has been discovered that the time break of provides the unique trigger that is out of the specifications for the speed negotiation signal such as COMREST COMWAKE or COMINIT signaling which avoids false triggering. The time break includes the pulse width time that is at least three times the width of the pulse width time for COMREST COMWAKE or COMINIT signaling which prevents fails triggering of other operations such as speed negotiation.

Referring now to therein is shown a flow chart of a method of operation of the electronic system of in a further embodiment of the present invention. The method includes receiving a patterned signal in a block recognizing an unique trigger from the patterned signal in a block detecting an operational mode from the unique trigger in a block and configuring a system state change of a memory sub system based on the operational mode in a block .

Thus it has been discovered that the electronic system of the present invention furnishes important and heretofore unknown and unavailable solutions capabilities and functional aspects for an electronic system with read disturb management mechanism. The resulting method process apparatus device product and or system is straightforward cost effective uncomplicated highly versatile accurate sensitive and effective and can be implemented by adapting known components for ready efficient and economical manufacturing application and utilization.

Another important aspect of the present invention is that it valuably supports and services the historical trend of reducing costs simplifying systems and increasing performance. These and other valuable aspects of the present invention consequently further the state of the technology to at least the next level.

While the invention has been described in conjunction with a specific best mode it is to be understood that many alternatives modifications and variations will be apparent to those skilled in the art in light of the aforegoing description. Accordingly it is intended to embrace all such alternatives modifications and variations that fall within the scope of the included claims. All matters hithertofore set forth herein or shown in the accompanying drawings are to be interpreted in an illustrative and non limiting sense.

