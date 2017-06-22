---

title: Integrated-circuit radio
abstract: An integrated-circuit radio communication device () comprises a processor (), memory (), and radio communication logic (). The memory () has a firmware module () stored at a firmware memory address, the firmware module () comprising instructions for controlling the radio communication logic () according to a predetermined radio protocol. The processor () is configured to receive supervisor call instructions, each having an associated supervisor call number, and to respond to a supervisor call instruction by (i) invoking a supervisor call handler in the firmware module (), and (ii) making the supervisor call number available to the call handler. A software application () is loaded into the memory () of the device (), and stored at a predetermined application memory address. It is arranged to invoke a radio communication function from the firmware module () by issuing a supervisor call instruction having an associated predetermined supervisor call number corresponding to the function to be invoked.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09317348&OS=09317348&RS=09317348
owner: NORDIC SEMICONDUCTOR ASA
number: 09317348
owner_city: Trondheim
owner_country: NO
publication_date: 20130621
---
This invention relates to integrated circuit radio communication devices and methods of configuring such devices.

Integrated circuit radio communication devices typically integrate a processor memory and radio communication logic on a silicon chip. An antenna may be fabricated on the silicon or may be connecting externally. The device will have pins for connecting to a power supply clock source and any external peripherals such as sensors timers digital to analog converters and output devices. The processor interfaces with the radio communication logic in order to supervise the sending and or receiving of radio messages.

Such radio communication devices or chips can be used in a wide range of wireless products such as wireless mice and keyboards controllers for game consoles bicycle speedometers remote controls garage door openers wireless loudspeakers etc.

The processor on such a device may run software directly from non volatile memory in order to control the radio communication logic according to a predetermined radio protocol such as Bluetooth or ZigBee .

The manufacturing of a complete product such as a wireless mouse that incorporates such a radio communication chip typically involves the manufacturer of the radio chip supplying it to a product manufacturer who will integrate the chip into the rest of the product. The chip manufacturer may also provide a development kit containing tools such as a cross compiler loader and debugger and documentation that allow the product manufacturer to develop install and debug custom application software for the radio device. The custom application software may for instance include routines for receiving input from a movement sensor on a wireless mouse and for transmitting suitable radio messages according to a desired protocol.

A development kit may additionally include source code for a software library and or operating system written by the chip manufacturer. The product manufacturer can then compile and link the supplied source code with its own custom software application to create a single object file for loading to a predetermined address in the memory of each chip.

The library or operating system may contain instructions that implement a particular radio protocol. It could include other functions such as memory management processor scheduling inter process communication etc. The application developer can call these supplied functions from its application code rather than having to write them from scratch. This can make development of the application software simpler and quicker. It can also ease portability between different models of the radio chip.

From one aspect the invention provides a method of configuring an integrated circuit radio communication device wherein 

Thus it will be seen by those skilled in the art that in accordance with the invention a software application can be loaded onto a radio communication chip so as to interface via supervisor call instructions with a firmware module that provides radio control functions.

This removes the need for the software application developer to link the application code with a library or operating system supplied by the chip manufacturer thereby resulting in a simpler and more efficient development process. By avoiding the need for link time dependencies the chances of bugs arising during development of the software application can be reduced. Because there is no need to keep re linking the firmware module that provides radio control functions at successive development stages the location of member objects in memory can remain unchanged during the development process. This continuity in memory location can avoid bugs occurring and can also aid debugging if errors do arise.

In preferred embodiments the firmware module stored at the firmware memory address is a linked binary. Thus no linking between the firmware module and the software application is required or is even possible. It is envisaged that the firmware module will usually be a compiled binary module e.g. compiled from the C programming language although it is possible that it could be assembled directly from machine code.

In order to develop the software application the only non standard information i.e. not determined by the processor or device architecture that the application developer need know is the predetermined software application memory address information relating to the amount of any data memory e.g. in RAM available for the software application to use and the predetermined correspondence between supervisor call numbers and radio communication functions in the firmware module. This information can be sufficient to write compile and load a software application for the device. It is envisaged that the application developer could conveniently be provided with a header file e.g. in the C programming language which would contain this information. Such a header file may of course optionally contain other additional features to provide further assistance to the application developer. 

Another advantage of configuring a device according to methods of the invention is that the device manufacturer need not reveal confidential source code in its firmware module to the application developer.

The integrated circuit device may be provided to a developer of the software application with the firmware module already pre loaded on the device. This can further increase the security of any confidential information contained in the firmware module. However this is not essential. The application developer may instead receive the firmware module as a binary image of pre compiled instructions and load the firmware module onto the device.

Thus from a further aspect the invention provides a method of configuring an integrated circuit radio communication device wherein the device comprises a processor memory and radio communication logic the method comprising 

The firmware module and the software application may be loaded onto the device in any order or substantially simultaneously. It will be appreciated that loading the two simultaneously is still fundamentally different from loading a single linked software application and library as the skilled person might have done in the past. As before the firmware module is preferably a compiled and linked binary module but without being linked to the software application .

Thus from a third aspect the invention provides an integrated circuit radio communication device wherein 

From further aspects the invention provides a firmware module and a transitory or non transitory medium storing the same for loading on an integrated circuit radio communication device comprising a processor memory and radio communication logic at a firmware memory address the firmware module comprising 

From still further aspects the invention provides a software application and a transitory or non transitory medium storing the same for loading on an integrated circuit radio communication device comprising a processor memory and radio communication logic at a predetermined software application memory address the software application being arranged to invoke a radio communication function by issuing a supervisor call instruction having an associated predetermined supervisor call number corresponding to the function to be invoked.

In preferred embodiments of any of the above aspects the firmware module is arranged so that all the radio communication functions provided by the firmware module are invoked by supervisor call instructions having respective supervisor call numbers according to a predetermined correspondence between numbers and functions. In this way no other mechanism for invoking firmware functions need be supported by the device thereby avoiding substantial static or run time link dependencies and simplifying the device and development of the software application.

It will be appreciated that the firmware module may provide other functions not necessarily related to radio communication which the software application can invoke for example an encryption algorithm. Preferably the device is configured so that the invoking of all such functions is carried out by the issuing of supervisor call instructions.

Because embodiments of the device need not contain a traditional full operating system the application developer can be free to develop the software application as a native application for the processor architecture without having to learn how to interface with a proprietary operating system supplied by the chip manufacturer. Especially when the processor is well known in the art this is a particularly attractive feature for the application developer.

If the device has a hardware abstraction layer in addition to the firmware module the software application may interface directly with this layer. Application specific drivers may also be loaded onto the device.

Configuring the device may comprise using the correspondence between supervisor call numbers and radio communication functions when compiling the software application. Compiling or loading the software application may make use of the predetermined software application memory address. In some embodiments configuring the device may comprise receiving the correspondence between supervisor call numbers and radio communication functions and or receiving the predetermined software application memory address e.g. as a header file. Such information may then be used when compiling the software application.

The device is preferably configured so that no run time linking is required when executing the software application on the device.

The processor may implement the supervisor call instructions in any appropriate way. In one set of preferred embodiments the processor is an ARM Ltd. processor such as a processor from the Cortex M family and the supervisor call instructions are then SVC instructions supported by the processor.

The software application may issue a supervisor call instruction by executing a dedicated SVC processor instruction. Such an instruction may be generated by a compiler when compiling the software application e.g. by the developer including a specific pre processor directive in the source code for the software application.

The number associated with the supervisor call may be made available to the call handler via a register or via the call stack or via any other appropriate mechanism.

Preferably the processor and or software application are configured to make the values of one or more arguments available to the supervisor call handler. In this way the software application can pass arguments to a radio communication function such as data to be transmitted. The call handler may be able to pass a return value from the radio communication function to the software application.

The processor is preferably configured to handle a supervisor call instruction from the software application as an exception software interrupt . In this way the software application can interrupt less time critical processing when a time critical radio communication function needs to be invoked.

The processor preferably supports a plurality of interrupt priorities. In some embodiments some event driven functions in the firmware module are assigned a relatively high priority while others are assigned a relatively low priority. Preferably functions associated with time critical radio communication operations are assigned the relatively high priority.

The software application may be arranged to handle interrupts forwarded by the firmware module as explained below and may have a relatively high priority for some event driven functions and a relatively low priority for others. The software application priorities are preferably interleaved with those of the firmware module. The highest firmware priority level is preferably higher than the highest software application priority level so that critical radio communication operations implemented in the firmware module can always take precedence over the software application. This can provide protection against careless programming in the software application.

The firmware module is preferably configured to invoke a function in the software application in response to the firmware module receiving an interrupt. Such an interrupt may arise for example from a peripheral such as a movement sensor.

The firmware module and the software application may each have a respective interrupt vector table. The two tables preferably use the same interrupt vector address offsets as each other. The offsets of interrupt vector addresses in the firmware module s vector table and hence the software application s vector table when the two use the same offsets are typically fixed by the processor architecture. The device is preferably configured to use the firmware module s vector table when processing an interrupt i.e. as the system interrupt vector table .

However the firmware module is preferably configured so that all interrupts that the firmware module is not programmed to handle itself are passed on to the software application. This may be implemented by the firmware module causing execution to branch to the address contained in the corresponding offset in the software application s vector table whenever it is not configured to handle a particular interrupt. This is possible because the software application is loaded to a predetermined memory address so that the firmware module can know in advance where to find the software application s vector table once the application has been loaded onto the device.

For example in some embodiments the RESET interrupt handler address is always placed at offset 0 by the compiler. Therefore the RESET handler address in the firmware module s vector table will be at address 0x0000 0000 0 0x0000 0000 in the memory. The RESET handler address in the software application s vector table is at address CLENR 0 CLENR where CLENR is the predetermined base memory address at which the software application is located.

This interrupt forwarding mechanism conveniently allows the software application to be programmed to handle hardware interrupts in substantially the same way as if no firmware module were present on the device. I.e. the firmware module can be invisible to the software application for the purposes of receiving interrupts. The forwarding is preferably implemented in such a way that it adds latency of fewer than about 30 instructions or less than about 3 microseconds compared with a direct hardware interrupt to a software application.

The firmware module may be arranged to be substantially disabled. Such disabling may be carried out via a call to the firmware module preferably using the SVC mechanism . Disabling the firmware module may cause the firmware module to reset the protocol stack and to disable any memory protection if present in order to give resources back to the software application. When disabled the firmware module preferably forwards all interrupts to the software application even those which it might otherwise have handled itself .

The processor preferably supports seamless transitions from one interrupt priority level to another. This is sometimes referred to as tail chaining. This provides an elegant means of transferring control between the software application and the firmware module and vice versa so as to allow time critical radio communication functions to take precedence when necessary.

The device preferably comprises memory protection logic arranged to intercept memory access instructions. This logic may be located between the processor and the memory. It may use the location of a memory access instruction i.e. where the processor has read the instruction from to determine whether to allow access. The memory protection logic is preferably configured to prevent the software application from reading or overwriting the firmware module or both .

Such memory protection can provide benefits in protecting sensitive information in the firmware module from being read by the developer of the software application. It can also minimise potential damage from programming errors in the software application as well as aiding the detection and correction of bugs in the software application.

The memory protection logic may be configured to protect RAM associated with the firmware module from being read or written to by the software application or both .

The processor memory and radio communication logic are preferably integrated on a single silicon chip. However they may alternatively be integrated in a multi chip module.

The memory is preferably a non volatile memory such as EEPROM or flash. It preferably supports random access reading so that the firmware module and software application can be executed directly from the memory.

The skilled person will appreciate that the device will typically also comprise volatile memory. It may additionally comprise one or more peripherals. It may have connections for receiving power and a clock signal. It may have a connection for an antenna. It may have one or more input and or output interfaces such as a serial connection.

Optional or preferred features of one aspect or embodiment described herein may wherever appropriate be applied to any other aspect or embodiment.

These components are interconnected in a conventional manner e.g. using lines and buses not shown . The memory protection logic is situated so as to intercept instructions from the processor to the RAM and flash memory . When installed in a product the microcontroller may be connected to a number of external components such as a power supply radio antenna crystal oscillator sensors output devices etc.

The firmware module is a binary application comprising a number of embedded software blocks. A radio protocol block implements one or more wireless protocol stacks. A radio event manager provides access scheduling for the radio communication logic and event multiplexing. A library provides shared hardware resource management and functions such as random number generation configuring interrupts and priority power management e.g. for enabling and disabling peripherals encryption functions etc. A firmware manager supports enabling and disabling the firmware module and enabling and disabling the wireless protocol stack.

The firmware module owns the system vector table and is the entry point for the program on all resets.

An application programming interface API for the firmware module allows the software application to invoke functions in the firmware module . It is implemented entirely using system calls. When using an ARM processor each API function prototype is mapped to a firmware function via an associated supervisor call SVC number at compile time. This mapping can be provided to the developer of the software application to allow the functions to be called correctly.

The firmware module can communicate events to the software application as software interrupts the content of which is buffered until read polled by the software application . The reading is done through an API call e.g. event get .

The software application can access the microcontroller hardware directly or via a hardware abstraction layer e.g. by means of application specific drivers in addition to being able to use the firmware module to use the hardware indirectly.

The flash comprises two distinct regions either side of address CLENR code length region . Region between zero and CLENR is where the firmware module is loaded. Its interrupt vector table is stored at address zero. Region extending upwards from CLENR is where the software application is loaded. It too has an interrupt vector table at address CLENR the purpose of which is explained below. It will be appreciated that the device may have other non volatile memory not shown which may be used for other purposes such as storing configuration information or flags.

The RAM similarly has a Region from the base address 0x2000 000 to RLENR and a Region extended upwards from RLENR. RAM Region provides data storage for the firmware module while RAM Region provides data storage for the software application . A call stack is shared between the firmware module and the software application and grows downwards e.g. from 0x2000 0000 SizeOfRAM. The memory allocated to the call stack must be big enough for the needs of both the software application and the firmware module .

The firmware module call stack usage requirement may be published for the device by the chip manufacturer. The developer of the software application must then define an initial stack pointer and reserve sufficient stack memory for both the firmware module and his software application . The firmware module will initialize the main stack pointer on reset.

The memory protection logic is arranged to intercept all memory access requests e.g. read requests from the processor to the flash and the RAM . It determines the source of the access request instruction e.g. whether the request is from the firmware module or from the software application . It also accesses memory protection configuration data e.g. stored in one or more dedicated registers which specifies respective access permissions for the various sources and allows or denies the access request accordingly.

In some preferred embodiments of the invention the software application is denied read and or write access to flash Region and to RAM Region . This protects confidentiality for the firmware module and can prevent inadvertent or malicious writing by the software application to memory locations allocated to the firmware module thereby increasing robustness and security. The software application flash Region may also be protected from read access e.g. to protect against read back via an external debugging interface.

This means that the initial stack pointer cannot be in RAM Region as the software application does not have write access to this region. In other embodiments of the invention the call stack may be in two parts where the firmware module call stack is located in RAM Region and the software application call stack is located in RAM Region .

Above the Main background context are four interrupt priorities which are used as follows in increasing order of priority software application low priority firmware module low priority software application high priority and firmware module high priority. The high priority software application interrupt is used for critical interrupts where low latency is required.

The processor invokes the SVC handler via the firmware module s interrupt vector table which acts as the system interrupt vector table . The SVC number associated with the function called by the software application is passed to the SVC handler along with any arguments. Such arguments may be passed via registers or via the call stack depending on the processor. The SVC handler uses the SVC number to call the correct firmware module function. This could be a radio control function e.g. an instruction to transmit data by radio or a firmware management function e.g. to disable the firmware module or a library function e.g. to generate a random number . The function executes and then returns to the software application . A return value may be available in a register or on the call stack.

On receiving an interrupt e.g. from a motion sensor an interrupt handler in the firmware module is vectored to. This checks whether the firmware module is enabled and whether it is an interrupt that the firmware module is set up to deal with. If so the firmware module handles the interrupt. If not it branches execution to an interrupt handler routine in the software application . The firmware module can know where to find this routine because the location of the software application vector table at CLENR is predetermined and the offsets into this vector table are the same as the offsets into the firmware module s vector table.

In this way a firmware module implementing radio control logic programmed to a firmware memory address on an integrated radio communication chip can be configured and used both securely and conveniently.

