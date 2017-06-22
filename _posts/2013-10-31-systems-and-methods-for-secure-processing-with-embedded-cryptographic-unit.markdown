---

title: Systems and methods for secure processing with embedded cryptographic unit
abstract: Processor system with a general purpose processor and a cryptographic processor dedicated to performing cryptographic operations and enforcing the security of critical security parameters. The cryptographic processor prevents exposure of critical security parameters outside the cryptographic processor itself, and instead implements a limited scripting engine, which can be used by the general purpose processor to execute operations that require the critical security parameters.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09135472&OS=09135472&RS=09135472
owner: Square, Inc.
number: 09135472
owner_city: San Francisco
owner_country: US
publication_date: 20131031
---
The described embodiments relate to secure transaction processing and in particular to apparatus and methods for facilitating secure transaction processing using a hardware processor.

Payment cards such as debit and credit cards enjoy widespread use among consumers. New devices such as mobile phones with Near Field Communication NFC functionality are also joining payment cards as a means of payment. These payment methods generally rely upon a merchant having a point of sale POS terminal that is capable of handling the payment transaction for example to verify that the payment card is present and valid.

Generally POS terminals must be certified for compliance with accepted security standards before they will be accepted by payment card issuers. One common certification is for compliance with the Federal Information Processing Standards FIPS 140 series of computer security standards. The most recently issued version of the 140 series is the FIPS 140 2 standard.

FIPS 140 2 defines four levels of security from Level 1 to Level 4 . Level 1 is the lowest level standard and imposes only limited requirements. Level 2 requires physical tamper evidence measures and role based authentication. Level 3 adds the requirement for physical or logical separation for interfaces via which critical security parameters are input or output. Finally Level 4 requires even more stringent physical security requirements and protections against environmental attacks.

FIPS certification is a time consuming process that can take many months. Moreover any modifications to a certified module require an update to the FIPS certification if it is to be maintained. However when designing a hardware device that is to be FIPS certified it can be difficult to accurately forecast all application requirements. Hardware design has long lead times which can be compounded by the delay required to obtain FIPS certification. It would be preferable to offer a flexible environment in association with a FIPS certified cryptographic module without crossing over into a modifiable environment e.g. general purpose operating systems that requires extensive additional certification.

In a first broad aspect there is provided a non transitory computer readable medium storing instructions executable by a cryptographic processor the instructions which when executed by the cryptographic processor cause the cryptographic processor to carry out a method of cryptographic processing in conjunction with a general purpose processor the method comprising receiving a script identifier from the general purpose processor verifying that a script identified by the script identifier is authorized for execution on the cryptographic processor and executing the script to produce a script result.

The method may further comprise determining whether the script result comprises a critical security parameter that cannot be output from the cryptographic processor in unencrypted form.

The method may further comprise encrypting at least the critical security parameter in the script result using a secret key stored in a protected memory of the cryptographic processor.

In some cases the protected memory of the cryptographic processor is not readable externally to the cryptographic processor.

The method may further comprise receiving the script from the general purpose processor and retrieving a script verification value from a protected memory of the cryptographic processor the protected memory not readable by the general purpose processor wherein the verifying comprises computing a second script verification value based on the received script and comparing the second script verification value to the retrieved script verification value.

In some cases the instructions specify a limited instruction set that limits instructions able to be used in the script. In some cases the limited instruction set is non Turing equivalent. In some cases the limited instruction set excludes conditional branching instructions. In some cases the limited instruction set excludes loop instructions.

In another broad aspect there is provided a cryptographic processing unit for cryptographic processing in conjunction with a general purpose processor the cryptographic processing unit comprising a cryptographic processor the cryptographic processor configured to receive a script identifier from the general purpose processor verify that a script identified by the script identifier is authorized for execution on the cryptographic processor and execute the script to produce a script result.

In some cases the cryptographic processor is further configured to determine whether the script result comprises a critical security parameter that cannot be output from the cryptographic processor in unencrypted form.

In some cases the cryptographic processing unit further comprises a protected memory that stores a secret key and the cryptographic processor is further configured to encrypt at least the critical security parameter in the script result using the secret key.

In some cases the cryptographic processor is further configured to transmit the script result to the general purpose processor.

In some cases the cryptographic processing unit further comprises a protected memory not readable by the general purpose processor wherein the cryptographic processor is further configured to receive the script from the general purpose processor and retrieve a script verification value from the protected memory wherein the verifying comprises computing a second script verification value based on the received script and comparing the second script verification value to the retrieved script verification value.

In some cases the cryptographic processing unit further comprises a non transitory computer readable memory wherein the cryptographic processor is configured by instructions stored in the non transitory computer readable memory and wherein the instructions specify a limited instruction set that limits instructions able to be used in the script.

In some cases the limited instruction set is non Turing equivalent. In some cases the limited instruction set excludes conditional branching instructions. In some cases the limited instruction set excludes loop instructions.

In some cases the general purpose processor executes a set of instructions stored in a general non transitory computer readable memory and the cryptographic processing unit is configured to access the general non transitory computer readable memory to read the set of instructions and verify using at least one verification value stored in the protected memory that the set of instructions has not been altered.

In some cases the general non transitory computer readable memory is accessible via a general debugging interface and the cryptographic processing unit further comprises a cryptographic processing unit debugging interface wherein each of the general debugging interface and the cryptographic processing unit debugging interface is independently controlled.

In some cases the general debugging interface is controlled using a first electronic fuse block and the cryptographic processing unit comprises a second electronic fuse block for controlling the cryptographic processing unit debugging interface.

In some cases the cryptographic processor is configured to control the first and second electronic fuse blocks.

In some cases the general debugging interface and the cryptographic processing unit debugging interface are JTAG interfaces.

In some cases the cryptographic processing unit further comprises a clock source for both the general purpose processor and the cryptographic processor wherein the clock source is manipulable by the cryptographic processor but not the general purpose processor.

In some cases the cryptographic processing unit further comprises a power supply for providing power to the general purpose processor and the cryptographic processor wherein the power supply is controllable by the cryptographic processor but not the general purpose processor.

In another broad aspect there is provided a cryptographic processor system comprising a general purpose unit comprising a general purpose processor configured to execute a general instruction set a cryptographic unit comprising a protected memory not readable by the general purpose processor and a cryptographic processor configured to receive a script identifier from the general purpose processor verify that a script identified by the script identifier is authorized for execution on the cryptographic processor and execute the script to produce a script result.

In some cases the cryptographic processor system further comprises a communications interface between the general purpose processor and the cryptographic processor.

In some cases the communications interface is a universal asynchronous receiver transmitter and wherein the universal asynchronous receiver transmitter communicates with each of the general purpose processor and the cryptographic processor via a peripheral bus.

In some cases the cryptographic processor system further comprises a general debugging interface coupled to the general purpose unit and a cryptographic unit debugging interface coupled to the cryptographic processing unit wherein each of the general debugging interface and the cryptographic unit debugging interface is independently controlled.

In some cases the general debugging interface is controlled using a first electronic fuse block and the cryptographic unit debugging interface is controlled using a second electronic fuse block.

In some cases both the first and second electronic fuse blocks are controllable by the cryptographic processor.

In some cases the general debugging interface and the cryptographic unit debugging interface are JTAG interfaces.

In some cases the cryptographic processor system further comprises a clock source for both the general purpose processor and the cryptographic processor wherein the clock source is settable by the cryptographic processor but not the general purpose processor.

In some cases the cryptographic processor system further comprises a power supply for both the general purpose processor and the cryptographic processor wherein the power supply is controllable by the cryptographic processor but not the general purpose processor.

In some cases the cryptographic processor is further configured to determine whether the script result comprises a critical security parameter that cannot be output from the cryptographic processor in unencrypted form.

In some cases the protected memory stores a secret key and the cryptographic processor is further configured to encrypt at least the critical security parameter in the script result using the secret key.

In some cases the cryptographic processor is further configured to transmit the script result to the general purpose processor.

In some cases the cryptographic processor is further configured to receive the script from the general purpose processor and retrieve a script verification value from the protected memory wherein the verifying comprises computing a second script verification value based on the received script and comparing the second script verification value to the retrieved script verification value.

In some cases the cryptographic processing unit further comprises a non transitory computer readable memory wherein the cryptographic processor is configured by instructions stored in the non transitory computer readable memory and wherein the instructions specify a limited instruction set that limits instructions able to be used in the script.

In some cases the limited instruction set is non Turing equivalent. In some cases the limited instruction set excludes conditional branching instructions. In some cases the limited instruction set excludes loop instructions.

In some cases the cryptographic processor is configured to halt the general purpose processor if a fault is detected.

In some cases the cryptographic unit is configured to flush state if a fault is detected and to disable at least one external interface of the processor system.

In some cases the cryptographic processor system further comprises a memory access block wherein the general purpose unit further comprises a general purpose unit computer readable memory storing a set of instructions executable by the general purpose processor and wherein the cryptographic processor is configured to access the general purpose unit computer readable memory via the memory access block to read the set of instructions verify using at least one verification value stored in the protected memory that the set of instructions has not been altered.

In some cases the general purpose unit comprises a general volatile memory and the cryptographic unit comprises a protected volatile memory that is accessible only to the cryptographic processor.

In some cases the cryptographic processor is configured to write a data item to the protected volatile memory.

In some cases the cryptographic unit is configured to read the data item from the protected volatile memory upon subsequently receiving a script for execution.

In some cases the cryptographic unit is certified for compliance with a computer security standard and the general purpose unit is excluded from certification. In some cases the computer security standard is FIPS 140 2. In some cases the computer security standard is FIPS 140 2 Level 3.

In some cases the general purpose unit the cryptographic unit and the communications interface are provided on a single die. In some cases the general purpose unit is provided on a first die and the cryptographic unit is provided on a second die.

The drawings are provided for the purposes of illustrating various aspects and features of the example embodiments described herein. Where considered appropriate reference numerals may be repeated among the figures to indicate corresponding or analogous elements.

It will be appreciated that numerous specific details are set forth in order to provide a thorough understanding of the example embodiments described herein. However it will be understood by those of ordinary skill in the art that the embodiments described herein may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the embodiments described herein.

The described embodiments generally provide a hardware platform that provides a FIPS compliant cryptographic processing element in combination with a flexible general purpose processing element where the general purpose element is not subject to the more stringent requirements of FIPS certification e.g. the general purpose element can be excluded from the requirements of FIPS 140 2 Level 3 . The cryptographic processing element can be certified to perform a limited set of instructions that it receives from the general purpose element generally in the form of a sequence of commands e.g. a script within the secure processor environment. However this limited instruction set nevertheless provides a comprehensive suite of operations used in cryptographic operations to minimize the need for subsequent modifications to the cryptographic processing element. In contrast the general purpose processing element can execute arbitrary code without requiring re certification of the entire device. However the general purpose processing does not compromise the security or the functionality of the cryptographic processing element.

The described embodiments provide a processor system intended to meet FIPS 140 2 Level 3 certification requirements and Payment Card Industry Point of Sale PIN Transaction Security Standard PCI PTS certification for Point of Sale POS applications.

In accordance with the FIPS security model the described embodiments make a distinction between ordinary Users and a Cryptography Officer CO . All access to the module is authenticated in some fashion. All users including the CO have unique user identifiers IDs . Users are able to securely use their keys within the cryptographic processing element module with access controllable on a per user basis. It will be understood that Users may include specific application programs that reside or execute in the general purpose processor of the system.

Referring now to there is illustrated a block diagram of a transaction processing system. System may be generally used to carry out financial transactions such as retail payment and the like. In some embodiments system may be used to perform authentication transactions for example verifying a user s credential as at a government office.

System includes an issuer server a data network a terminal device and a user credential which is typically in the possession of an end user .

User credential may be a credit card equipped with a GlobalPlatform Secure Element or other smart chip. User credential may further be equipped for contactless communication using for example radiofrequency identification RFID or other related technologies e.g. ISO IEC 14443 15693 Sony Felica NFC etc. . In some cases user credential may be a hardware device such as a smartphone equipped with a NFC interface.

In use user credential is presented to terminal which is equipped with a suitable card reader device. For example if user credential is equipped for contactless communication terminal may be equipped with a RFID reader to interrogate and communicate with the user credential.

Terminal is further equipped with a network interface as described below for communication with issuer server via data network .

Network can include a local area network or a wide area network e.g. the Internet or some combination thereof. In general communications between terminal and issuer server are encrypted either using a suitable encryption protocol a secure virtual private network or both. In some embodiments terminal may be directly coupled to an issuer server via dedicated communication lines.

Issuer server can include one or more computer servers operated by the issuers of credential and configured to authenticate and verify transactions carried out using credential . Issuer server is shown as a single entity for ease of exposition however it will be understood that multiple parties may work in conjunction to provide the services attributed herein to issuer server .

Referring now to there is illustrated a system block diagram of an example terminal such as terminal .

Terminal includes a cryptographic processor system a network interface a power supply e.g. battery an input device e.g. keyboard keypad an output device e.g. display a volatile memory and a non volatile memory . Terminal may further include an antenna e.g. for NFC . In other embodiments terminal may include a contact based card reader not shown .

Terminal also generally includes one or more testing and general debugging interfaces such as a port compliant with the IEEE 1149.1 Standard Test Access Port and Boundary Scan Architecture also sometimes referred to as the Joint Test Action Group JTAG port. General debugging interface allows a programming device to transfer firmware to an internal non volatile memory of terminal as described herein.

Network interface may be a wired or wireless communication interface such as for the Ethernet or IEEE 802.11 protocol families for network communication.

Volatile memory may be a random access memory used by cryptographic processor system to temporarily store data and computer executable instructions. Non volatile memory may be a mass storage memory such as flash memory used by cryptographic processor system for long term storage of programs and data.

Cryptographic processor system is a computer processor or processors as described herein. Referring now to there is illustrated a system block diagram of an example cryptographic processor system .

As illustrated cryptographic processor system is a dual core system on chip processor. System can be generally divided into two main portions a first general purpose unit and a second cryptographic unit which may be referred to as the protected or secured portion. In general the general purpose unit has access to input output interfaces for external communications. In contrast the cryptographic unit has limited or no external interfaces but can enable or disable the interfaces of the general purpose unit . Likewise the cryptographic unit controls important elements of the system including the system clock which can be controlled to throttle or disable the general purpose unit when needed.

Cryptographic processor system can be implemented using the Advanced Microcontroller Bus Architecture AMBA . However it will be understood that other specifications may be followed in designing processor system .

General purpose processor is a general purpose processor such as a Reduced Instruction Set Computing RISC processor which is coupled to a first hardware bus such as the Advanced High performance Bus AHB . Similarly cryptographic processor is coupled to a second hardware bus . First and second hardware busses and are not directly coupled to each other.

General purpose processor is coupled via the first hardware bus to a universal serial bus USB communications interface an external memory controller an internal volatile memory general volatile memory a first peripheral bus bridge and an internal non volatile memory general non volatile memory .

Non volatile memory stores the firmware used by general purpose processor which includes data and one or more control programs and application programs executed by general purpose processor .

First peripheral bus bridge is coupled to a peripheral bus such as an Advanced Peripheral Bus APB which is further coupled to other peripheral devices such as a watch dog an external timer a JTAG interface a Universal Asynchronous Receiver Transmitter UART an Inter Integrated Circuit I2C port and a Serial Peripheral Interface SPI for connecting to devices such as output device input device etc. A Single Wire Protocol SWP interface may also be provided to interface with a Subscriber Identity Module SIM card for example.

Peripheral bus is also coupled to a radio link control module which is further coupled to an analog frontend for NFC or RFID communications for example.

Cryptographic processor may also be a RISC processor which is coupled via the second hardware bus to a second peripheral bus bridge an internal volatile memory protected volatile memory and an internal non volatile memory protected non volatile memory .

Non volatile memory stores the firmware used by cryptographic processor which includes data and one or more control programs executed by cryptographic processor . Data stored in non volatile memory is generally protected by storing in encrypted form to prevent offline tampering.

Internal volatile memory may be subdivided into a number of smaller volatile memories. In particular the volatile memory may have a battery backed portion and a non battery backed portion. Part of the non battery backed portion may be divided between session storage which is cleared each time a user logs out and a semi persistent portion which retains data between user sessions.

If an attack is detected or if cryptographic processor identifies a fault in a script under execution volatile memory may be protected by immediately erasing or zeroing data and in particular critical security parameters may be removed from volatile memory .

The battery backed portion may be used to store critical keys e.g. a master key to decrypt non volatile memory contents .

Since the volatile memory and non volatile memory are only connected to the second hardware bus only the cryptographic processor has access to these memories. In particular neither general purpose processor nor any peripheral or external device can directly access these memories.

Second peripheral bus bridge is coupled to a second peripheral bus such as an APB which is coupled to a UART JTAG interface watch dog external timer random number generator and a clock e.g. an internal oscillator in a frequency locked loop .

To protect cryptographic processor against attacks or snooping by general purpose processor or other peripherals internal communications interfaces between cryptographic processor and general purpose processor may be fused using an electronic fuse block which is controlled only by the cryptographic processor .

Generally cryptographic processor may disable internal communications interfaces following manufacturing test and configuration in order to comply with certification requirements for certain FIPS 140 2 levels. When the internal communications interfaces are disabled via fuse block a communications interface between cryptographic processor and general purpose processor can be provided via external peripheral devices such as UART and UART .

Fuse block can also be used to enable or disable JTAG interface or JTAG interface as well as a Design For Test DFT interface used to screen for manufacturing defects or any other production test interface of the processor system in general. Disabling the JTAG or test interfaces can prevent unauthorized attempts to modify the firmware of general purpose processor cryptographic processor or access any memory of the system.

The fuses for JTAG interface may be controlled by cryptographic processor independently of the fuses for JTAG interface which can enable modification of firmware for general purpose processor while preventing modification of firmware for cryptographic processor . This allows the cryptographic processor to remain FIPS compliant while developing and debugging applications on the general purpose processor .

In addition to disabling JTAG and programming interfaces cryptographic processor can also halt the clock signal provided to general purpose processor . In particular cryptographic processor may have access to an internal register interface a clock block of the system . This register interface is controlled by cryptographic processor and it can be used to halt the clock of general purpose processor for example by setting a register in the clock block .

While the clock of general purpose processor is halted a general purpose input output port not shown may be used to indicate an error status. The error state control can be controlled by cryptographic processor .

To prevent clock timing attacks while each processor and also controls its own clock divider network to set its own operating clock frequency the setting of the main clock source that feeds both divider networks is only controlled by the cryptographic processor. This prevents any attacks from malicious software running on the general purpose processor from altering the clock of the cryptographic processor .

In some cases fuse block may be used to control clock input to general purpose processor effectively halting any further processing by processor .

Similarly power supply controls e.g. 3.3V and 1.2V regulators may be controllable by cryptographic processor but not general purpose processor .

In general system implements a number of features designed to secure the system against attack. For example access to cryptographic unit is allowed using a well defined protocol such as the GlobalPlatform Secure Channel Protocol 03 SCP03 . User access to cryptographic unit requires a login and user script hashes are checked against a list of permitted hashes provided at login time. In addition only one user or administrator may be logged in to cryptographic unit at any given time.

Referring now to there is illustrated an example schematic diagram of a user environment in cryptographic unit . The user environment illustrates data held in memory e.g. volatile and non volatile by cryptographic unit and associated with a particular user. Data in the user environment does not include critical security parameters such as secret keys.

For example a user environment for a first user includes a login block an encrypted user data block a first command sequence or script and a second command sequence and an application data block . Each script identifies a sequence of commands to be executed by a cryptographic processor but generally does not include data to be operated on by the processor . Application data that is to be supplied to cryptographic processor is stored in an application data block which can include application data that has been encrypted and signed for example by the cryptographic processor on a previous occasion.

Login block includes a user identifier and a list of hash values generated by applying a known one way hash function to the scripts and . By providing hash values at login time cryptographic processor can independently verify that scripts have not been modified after login before the scripts are executed by processor . If any scripts are modified or if hash values are changed cryptographic processor can determine that modification has occurred since the a hash calculation for the user s login block will not match the login hash stored in a user s data block as shown in .

Encrypted user data block is encrypted and optionally signed using user data block encryption keys stored only within a secure environment of cryptographic processor as shown with reference to . Accordingly while encrypted user data block may be stored outside cryptographic processor the data within the encrypted user data block is only accessible within cryptographic processor .

Encrypted user data block may store data including a user identifier a login hash data regarding user permissions cryptographic keys used for SCP03 communication and data keys. Data keys are one or more keys generated for each user and used for data encryption or cryptographic signing operations.

Referring now to there is illustrated an example schematic diagram of a secure environment such as that of cryptographic processor .

Secure environment includes at least one user data block a finite state machine block a session storage block a semi persistent blackboard block and a battery backed volatile memory block .

Battery backed volatile memory block may be used to store the Local Master Key LMK which is used to encrypt other keys generated by cryptographic processor such as Firmware Management Master Key FMK Crypto Officer Master Key CMK User Master Key UMK and the like.

User data block may include for example a user identifier counters e.g. for detecting or preventing side channel attacks as described herein and one or more encryption signing keys for encrypting decryption signing and verifying the encrypted user data block .

A Cryptographic Officer CO is an administrative user who is granted permission to create update or remove user accounts inside the cryptographic processor .

In particular the CO can generate or set user authentication keys which include SCP03 master keys Message Authentication Code Key MAC Encryption Key ENC and Key Encryption Key KEK which are 256 bit Advanced Encryption Standard AES symmetric keys with associated key derivation data or Key Agreement Keys e.g. user server signature verification public key user server static public key user static key pair with both public and private key .

The CO can also generate data keys for each user set the user s login hash and grant or remove user privileges.

Privileges can include for example a list of commands e.g. from an application programming interface available to the user permission to read and or write to the blackboard memory permission to read and or write to the battery backed memory permission to login using a login block permission to open an SCP03 channel Symmetric or Asymmetric with the system permission to update the user s own authentication keys and permission to set or update the user s own login hash. Not all of these permissions need be available or implemented in every embodiment. For example in some embodiments a permission to read or write to the blackboard or battery backed memories may not be available.

The CO can be enabled to communicate with the system via a SCP03 connection. In some embodiments the CO user is prevented from executing application programming interface API commands in cryptographic processor . To enforce this and to prevent tampering with user data the cryptographic processor may be configured to erase its volatile memory when a CO logs in.

Once created by the CO a regular user can log in to cryptographic processor using the assigned login block and execute scripts.

If permitted the user can also login via SCP03 and reset the user s own authentication keys and login hash.

Each user account has certain data stored encrypted and signed in a user environment such as user environment described with reference to . The account data generally includes a user ID a login hash e.g. a hash of the login block authentication keys SCP03 Master keys MAC ENC KEK or Key Agreement Keys data keys e.g. one for data encryption one for signing a list of user permissions and a storage quota for non volatile and volatile memories.

It may be desirable for a user to save data between login sessions. Accordingly users may be allocated a block of memory in the blackboard block of cryptographic processor for this purpose. Each user s portion of the blackboard block can only be written to or read by the specific user. The blackboard block is stored in volatile memory so that it does not persist beyond a reset of the system.

In general users are prevented from permanently storing any data in cryptographic processor . Accordingly user authentication keys can be set by the CO. However some users may have permission to update their authentication keys or login hash via SCP03.

Any application data that is to be stored by users should be stored outside the cryptographic processor in general purpose non volatile memory or mass storage for example. Since cryptographic processor is generally configured not to export any critical security parameters in unencrypted form the user cannot accidentally expose critical security parameters by storing them in unprotected general purpose memory.

When the system is in an operational state a user can authenticate by one of two ways. In a first authentication approach SCP03 Mutual Authentication to a server can be used. In another approach the user can login using a login block. Login via SCP03 allows the user to execute any command in they have been granted permission to use. Login via the login block allows the user to execute pre authorized scripts command sequences only.

Login via a login block comprises sending a user identifier and a data block which includes a list of hashes of the scripts the user is allowed to execute. The hash of the data block supplied by the user must match the login hash stored in the user data block. In effect the data block acts as the user s password. Optionally the login block may be encrypted or authenticated with a message authentication code.

Scripts or command sequences are deliberately limited to a set of predefined operations or instructions. This limited instruction set is designed to minimize the risk of exploitable code or instructions being passed to cryptographic processor by limiting the available instructions to commands that cannot provide Turing equivalent processing.

In particular to avoid Turing equivalence in scripts support for iteration conditional branching and flow control is deliberately excluded from the command set. Thus command sequences are limited to a linear list of commands. Since the script cannot perform iteration and flow control a user application which executes on general purpose processor can be adapted to submit multiple scripts as necessary. Any error during execution of a script may result in the termination of the session.

Scripts generally have a name or script identifier. In general scripts have no dependencies on any previous scripts. Cryptographic processor can be configured to clear all previously retained data in session storage prior to the execution of each new script.

However in some cases it may be desirable to provide a mechanism for enforcing the order in which a series of related sequences are executed. To support this finite state machine block can maintain a hash list of scripts. Each script can contain a command indicating that the script is the start or end script of a series of scripts. The cryptographic processor can record a sequence s identifier in finite state machine block and present this identifier to a subsequent script. Scripts can also include a command that designates the next script that should be executed which when set should treat as an error attempts to run a script other than the one designated. Scripts may also contain commands to verify that a particular script preceded the present script s execution by checking a previous sequence identifier stored in finite state machine block . Data used by a series of scripts can be retained in session storage while the series of scripts is completed.

In addition to the CO and ordinary users additional users may also be provided by cryptographic processor .

A Transport Management User TM can be provided and used in an initial creation state create the CO. System is in a creation state after manufacturing or following a BOOT application protocol data unit APDU command. While in the creation state the only permitted operations are the creation of the Transport Management Key TMK updating of the TMK and the creation of the CO in which case the LMK is generated .

In the event that an attack is detected e.g. backup battery removal system can switch to a terminated state. While in the terminated state no further processing can be performed. System can exit the terminated state by reverting to the creation state following the attack or following a power cycle.

In the illustrated embodiment system is implemented on a single processor die. However in alternative embodiments multiple processor dice may be used. For example general purpose unit may be implemented on a first processor die while cryptographic unit may be implemented on a second die.

In some cases system can also provide countermeasures against some attacks such as side channel attacks against SCP03 symmetric keys. In particular cryptographic processor may include two counters for each symmetric key used by the system.

To slow side channel attacks symmetric keys each attempt to use a key will be counted and each successful attempt will be counted separately. If there is a difference between counts system can implement a delay between subsequent key usage attempts. The delay may scale based on the difference between the two counters. For example the delay may correspond to X seconds where X is the difference in the counts. A maximum difference may also be specified to set an upper limit on the delay.

Referring now to there is illustrated a flow diagram for an example method of cryptographic processing in conjunction with a general purpose processor. Method begins at with system being powered on or reset. For ease of exposition system is assumed to have been configured with a CO and one or more users. Accordingly non volatile memory should contain a LMK TMK FMK and CO data encrypted with the LMK.

As described herein with reference to limited user data can be stored in a user data block stored within cryptographic unit . Additional user data can be stored in an encrypted user data block stored within general purpose unit where the encrypted user data block is encrypted and signed by cryptographic unit such that the data it contains is not accessible to general purpose unit . The user data block can include the user identifier counters and encrypted user data block keys. The encrypted user data block may include the user identifier user keys a login hash permissions data further counters assigned to the user blackboard block quota and battery backed memory quota. User keys may be symmetric keys in which case the data includes a personalization identifier a key index key version ENC key MAC key and KEK key or asymmetric keys in which case the data includes a personalization identifier elliptic curve key pair server key agreement public key and server signature verification public key .

At system receives a login block for example via a NFC communication interface e.g. analog frontend link control peripheral bus bridge first hardware bus general purpose processor fuse block and on to cryptographic processor .

Cryptographic processor determines the user identifier associated with the received login block at locates a corresponding user data block and retrieves the decryption key for the encrypted user data block for the identified user. Cryptographic processor also requests the encrypted user data block for the identified user and the login block stored in the user environment e.g. by general purpose unit .

Once the decryption key is found and the encrypted user data block is received cryptographic processor decrypts the encrypted user data block to recover user data.

At cryptographic processor computes a hash computation using the recovered raw login block to produce a computed login block hash.

At cryptographic processor compares the computed login block hash to a stored login block hash that is stored in user data block in its non volatile memory . If the two hash values fail to match an error condition is identified and the cryptographic processor may halt or reset processor system .

If the two hash values match cryptographic processor indicates to general purpose processor that login was successful and waits to receive a script for execution.

At cryptographic processor receives a script for execution. Optionally cryptographic processor may receive additional data to be used during execution of the script.

At cryptographic processor verifies that the script is authorized for execution on the cryptographic processor by the current user by computing a script verification value e.g. hash function using the received script as input.

At the computed script verification value for the script is compared to the script verification value hash value stored in the login block received from the user. If the script verification values do not match this may indicate an attempt to circumvent security and an error condition is identified and the cryptographic processor may halt or reset processor system .

Since the user data block pre configured and stored in encrypted form by cryptographic processor in its non volatile memory contains the login hash for each user s login block and since each user s login block contains a hash of each authorized script cryptographic processor can verify that each script it receives is authorized and unmodified by hashing each script and comparing to the hash values in the login block received from the user which is itself hashed and compared to a known hash value. This hash on hash scheme allows for cryptographic processor to operate with minimal memory requirements and there is no need for cryptographic processor to store scripts or even the script verification values for the scripts.

This allows the cryptographic processor to be certified for FIPS compliance and have its firmware frozen without the need to foresee every possible script that may need to be executed.

Once a script has completed execution cryptographic processor may determine whether the output of the script contains a critical security parameter that must be encrypted e.g. encryption key and whether the critical security parameter is encrypted in the output. Critical security parameters includes any data that may not be output in unencrypted form if FIPS certification is to be achieved and maintained.

If no critical security parameter is included the output may be transmitted to general purpose processor at either encrypted or in the clear for further use by an application program.

Otherwise at cryptographic processor determines if the critical security parameter included in the output is encrypted. If the critical security parameter is encrypted the output may be transmitted at .

Otherwise if the critical security parameter is not encrypted or if a condition has not been satisfied at or for example cryptographic processor may halt execution of the current script without transmitting the output. An error message may be transmitted instead. Optionally cryptographic processor may halt general purpose processor entirely as described herein.

Accordingly the described embodiments provide for a cryptographic calculator approach in which a first general purpose processor is relieved of the need to perform sensitive cryptographic operation. A second cryptographic processor is dedicated to performing cryptographic operations and enforcing the security of critical security parameters. In some cases both the general purpose and cryptographic processors may be similarly specified processors in terms of processing design e.g. both may be similar RISC or ARM processors .

The cryptographic processor protects sensitive data from exposure outside the cryptographic processor itself. For example a master data encryption key is stored in a battery powered volatile memory exclusive to the cryptographic processor. The master key may be used to encrypt a master key for each user application.

When data exceeds the protected storage available to the cryptographic processor the cryptographic processor may encrypt such data and allow it to be stored by general purpose processor which allows for virtually unbounded secure storage.

The cryptographic processor executes a firmware that is stored in protected non volatile memory and which can be certified for FIPS 140 2 compliance. The firmware implements a FIPS compliant scripting engine which limits scripts to a sequence of commands by design. The general purpose processor can submit scripts for execution inside the cryptographic processor using the scripting engine where critical security parameters e.g. secret keys can be used.

Because the general purpose processor is physically prevented from accessing the cryptographic processor or its protected memory it can be excluded from portions of the FIPS certification process. Moreover the general purpose processor can be permitted to run arbitrary programs without invalidating the FIPS certification of the system.

Accordingly the general purpose processor executes a firmware that can be modified more freely albeit still under the control of the cryptographic processor without invalidating FIPS certification of the system. For example firmware updates for one or both processors can be managed and controlled using keys stored in the cryptographic processor. Firmware images may be checked to verify that they have been signed by a known or trusted source.

The described embodiments can be configured to support a wide variety of cryptographic algorithms including but not limited to AES Data Encryption Standard DES Triple Data Encryption Algorithm 3DES Elliptic Curve Cryptography ECC Rivest Shamir Adleman RSA algorithm and the family of Secure Hash Algorithms SHA . Various of these algorithms can also be used to implement Message Authentication Code MAC Cipher based MAC CMAC and keyed hash message authentication code HMAC .

The described embodiments can also be configured to support common protocols such as GlobalPlatform SCP03 key agreement schemes SP800 56A and SP800 56B and even Transport Layer Security TLS SSL .

Referring now to there is illustrated another example cryptographic processor system . System is generally analogous to system and like elements are labeled using like reference numerals.

System differs from system in that it includes a block which is able to directly access the memories of both general purpose unit and cryptographic unit . In particular memory access block can read volatile memory non volatile memory volatile memory and non volatile memory . Memory access block can directly each memory in a read only fashion to verify its contents. However cryptographic processor is not configured to actively use memory via memory access block for program execution or data storage. Preferably memory access block cannot write to any of these memories. Accordingly cryptographic processor can indirectly read volatile memory or non volatile memory via memory access block without the intermediation of general purpose processor . This allows more complete checks of memory such as computing hashes to verify the integrity of the application software being executed by general purpose processor .

To facilitate verification memory access block may also include a verification element to perform computations using at least one verification value such as a Cyclic Redundancy Check CRC to calculate CRC checksums that can be used to periodically verify memory contents. The calculated checksums are only output to cryptographic processor for example via peripheral bus . Other checksum or cryptographic verification functions may also be incorporated into memory access block .

The described systems and methods are capable of being used in a variety of environments. For example a module incorporating a system could be installed in any computing device and tasked with supplying general cryptographic functions such as calculating hashes. In such applications no keys or data would need to be stored in a secure manner and there would be no requirement to deny access to any instance of the user. A login block and user data block could be created for a user where the login block contains a list of hashes for a wide variety of anticipated scripts. The user can subsequently login using the login block and can use scripts as required without the need for any additional configuration.

In another example system can be used to support a virtual token application in which system can emulate a smartcard device. The virtual token may include software that executes on a general purpose processor. The software includes an implementation of the SCP03 protocol for external communication while the cryptography processor can be configured to perform SCP03 encryption decryption key generation and other card functions.

In practice the virtual token application may be implemented by including scripts for SCP03 related cryptography in the virtual application token. A login data block can be created for the token application and a hash of the login data block stored in the user data block by the cryptographic processor.

Personalization may occur in a secure facility in similar fashion to conventional smartcards. For example a personalization application may use CO access to create a user identifier for the virtual token application i.e. login hash signing key and data key etc. .

The general purpose processor has access to the SCP03 user identifier login block and scripts necessary to create a SCP03 to a server. The token application executing on the general purpose processor can use the SCP03 user id login and scripts to have cryptographic processor create and encrypt the keys for its SCP03 connection to the server. The encrypted keys are received from the cryptographic processor and stored in non volatile memory for subsequent use.

When establishing a SCP03 connection to a server the token application executing on general purpose processor can use appropriate scripts to send its encrypted SCP03 keys to the cryptographic processor which can then decrypt and use the SCP03 keys within the cryptographic processor environment to create session keys and to encrypt and decrypt messages to and from the server.

Aspects of the embodiments described herein may be implemented in hardware or software or a combination of both. These aspects may be implemented in computer programs which execute on programmable computers each computer including at least one processor a data storage system including volatile memory or non volatile memory or other data storage elements or a combination thereof and at least one communication interface as described for example with reference to . The various programmable computers may be a server network appliance set top box embedded device computer expansion module personal computer laptop personal data assistant cellular telephone smartphone device tablet and wireless hypermedia device or any other computing device capable of being configured to carry out the methods described herein. For greater certainty the programmable

Program code is applied to input data to perform the functions described herein and to generate output information. The output information is applied to one or more output devices in known fashion. In some embodiments the communication interface may be a network communication interface. In embodiments in which elements of the invention are combined the communication interface may be a software communication interface such as those for inter process communication IPC . In still other embodiments there may be a combination of communication interfaces implemented as hardware software and combination thereof.

Each program may be implemented in a high level procedural or object oriented programming or scripting language or both to communicate with a computer system. However alternatively the programs may be implemented in assembly or machine language if desired. The language may be a compiled or interpreted language. Each such computer program may be stored on a storage media or a device e.g. ROM magnetic disk optical disc readable by a general or special purpose programmable computer for configuring and operating the computer when the storage media or device is read by the computer to perform the procedures described herein. Embodiments of the system may also be considered to be implemented as a non transitory computer readable storage medium configured with a computer program where the storage medium so configured causes a computer to operate in a specific and predefined manner to perform the functions described herein.

Furthermore the systems and methods of the described embodiments are capable of being distributed in a computer program product including a physical non transitory computer readable medium that bears computer usable instructions for one or more processors. The medium may be provided in various forms including one or more diskettes compact disks tapes chips magnetic and electronic storage media and the like. Non transitory computer readable media comprise all computer readable media with the exception being a transitory propagating signal. The term non transitory is not intended to exclude computer readable media such as a volatile memory or RAM where the data stored thereon is only temporarily stored. The computer useable instructions may also be in various forms including compiled and non compiled code.

The present invention has been described here by way of example only while numerous specific details are set forth herein in order to provide a thorough understanding of the example embodiments described herein. However it will be understood by those of ordinary skill in the art that these embodiments may in some cases be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the description of the embodiments. Various modification and variations may be made to these example embodiments. The scope of the claims should not be limited by the described embodiments and examples but should be given the broadest interpretation consistent with the description as a whole.

