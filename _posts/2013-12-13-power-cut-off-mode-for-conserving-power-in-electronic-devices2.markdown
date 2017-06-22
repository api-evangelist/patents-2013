---

title: Power cut off mode for conserving power in electronic devices
abstract: External jolts, such as those occurring during shipment, may inadvertently activate an electronic device. Such inadvertent activations may result in the electronic device entering an active mode during shipment, draining battery power. This document describes a power cut off mode that prevents inadvertent device activations and minimizes current consumption during shipment or storage of a device. This conserves battery power for operational use by the user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09568983&OS=09568983&RS=09568983
owner: Amazon Technologies, Inc.
number: 09568983
owner_city: Reno
owner_country: US
publication_date: 20131213
---
This application is a continuation of and claims priority to U.S. patent application Ser. No. 12 770 031 filed Apr. 29 2010 issued as U.S. Pat. No. 8 635 481 and which is incorporated by reference herein in its entirety.

Electronic devices such as electronic book readers eBook reader devices cellular telephones portable media players desktop computers laptops tablet computers netbooks personal digital assistants and the like rely on electrical power to function.

Within these electronic devices several components utilize significant amounts of power during operation including the processor s and peripheral devices. These peripheral devices include external memory interfaces EMIs Universal Serial Bus USB controllers image processing units IPUs and so forth. These peripheral devices may reside on the same chip or die as the processor and or may reside on another die.

Inadvertent activation of the electronic device due to environmental factors may occur. For instance devices may experience transient accelerations from jostling during transport and in response may activate or power up certain components of the device. For example a box containing the electronic device may be dropped during shipment. Such a drop may inadvertently activate the device. During inadvertent activation the electronic device consumes power thus depleting power available in a battery powering the electronic device. A user that later attempts to use the electronic device may thus find the battery substantially or completely discharged. The user is therefore required to charge the device a process which may be inconvenient and take several hours depending upon the charger battery capacity and other parameters.

While mechanical switches with high activation forces may mitigate this problem these solutions introduce other problems. For instance design and engineering constraints such as available volume ability to control the device and so forth may preclude device designers from including such mechanical switches in electronic devices. Furthermore such an approach may render inoperable a real time clock of the device introducing adverse side effects with regard to digital rights management DRM .

As described above inadvertent activation of electronic devices depletes power stored in a battery. This creates inconvenience by requiring a user to locate and employ an external power supply spend time charging the battery or replace the battery before actually operating the device.

Traditional off modes may maintain a power management integrated circuit in an active state resulting in significant consumption of power. Over time such as during shipment or storage this consumption may deplete the battery. Also traditional off modes may deactivate the real time clock complicating digital rights management DRM or other functions. Furthermore traditional off modes may be susceptible to awakening as a result of transient wakeup interrupts resulting in even more rapid discharge and depletion of the battery.

This disclosure describes techniques for placing a device into a power cut off mode. While in the power cut off mode a sustained wakeup interrupt will awaken the device while transient wakeup interrupts will not. Also while the device is in the power cut off mode described herein the power management integrated circuit maintains a real time clock and minimal circuitry configured to accept a sustained wakeup interrupt. As a result a large portion of the power management integrated circuit remains off which significantly reduces power consumption. Such significant reductions in power consumption minimize battery depletion thus extending the shelf life of the electronic device. In addition the operational real time clock facilitates date time related functions such as DRM.

The techniques described herein may apply to electronic devices and may provide the ability to access content via a network connection. For example an eBook reader device may have a wireless network connection to allow convenient access to content stored elsewhere and accessible by the network connection. The content accessed on the device may be subject to DRM restraints. In several implementations of DRM real time date and time are at least one of the inputs used to determine accessibility.

For example DRM may call for an electronic book to be accessible for only a specific two month period such as when loaned from a library. During the period the electronic book is accessible while at the expiration of the period the electronic book is inaccessible. Without the real time clock or access to an external authoritative time server DRM may be inoperable precluding access to content that the user may be entitled to.

When in the power cut off mode a sustained wakeup interrupt will awaken the device. The sustained wakeup interrupt includes for example the interrupt generated by a user intentionally activating a power switch or from attachment of a charger. The power cut off mode protects the device from inadvertent activations such as from brief contacts of a power switch due to transient accelerations because the power management integrated circuit in power cut off mode requires a sustained wakeup interrupt to activate.

In some implementations the device may enter the power cut off mode after meeting one or more pre determined conditions. For example the pre determined condition may be an elapsed time limit. Thus when the device is activated after being idle for a length of time greater than the elapsed time limit rather than resuming a sleep mode the device may enter the power cut off mode. Thus the power cut off module prevents a cycle of repeated inadvertent activations which could deplete the power in the device s battery.

By implementing a power cut off mode described in this disclosure at least the following several advantages accrue First a reduction in the effects of inadvertent activation to avoid depletion of the battery. Second minimization of the power consumed while a device is off. Third maintenance of an active real time clock. The techniques described herein function to in part extend the shelf life of battery powered devices such as eBook reader devices and other handheld electronic devices and enhance a user s overall experience with the device. These techniques may be implemented by an electronic device utilizing a processor capable of entering a low power mode. For example the i.MX architecture from Freescale Semiconductor Incorporated of Austin Tex. United States of America is one suitable family of processors with associated power management integrated circuits PMICs .

The processor executes an operating system including but not limited to Linux UNIX Microsoft Corporation s Microsoft Windows Microsoft Corporation s Windows Mobile Apple Corporation s Mac OS Apple Corporation s Mac OS X and Wind River Systems Inc. s VxWorks .

For example an eBook reader device may incorporate a Freescale processor having an i.MX architecture with an Atlas PMIC and executing a Linux kernel. The kernel uses device drivers to communicate with peripheral devices such as the PMIC external memory interfaces EMIs Universal Serial Bus USB controllers image processing units IPUs and so forth. These peripheral devices may reside on the same chip or die as the processor as in the case of the i.MX architecture and or may reside on another die.

While this overview is described in terms of an eBook reader device the concepts described herein may also be applicable to cellular telephones portable media players desktop computers laptops tablet computers netbooks personal digital assistants or other electronic devices.

As described in more detail below with regards to a power cut off module is configured to place the eBook reader device into a power cut off mode. While in the power cut off mode the real time clock remains operational and the device will awaken upon a sustained wakeup interrupt.

As illustrated the eBook reader device includes a power switch . The power switch and associated circuitry is configured to generate an interrupt upon activation of the switch. In some implementations the power switch may be a momentary contact switch biased with a spring to maintain an open state unless activated a capacitive switch and so forth.

The eBook reader device also includes a display as well as a keypad that may include one or more page turning buttons and a keyboard for user input. Furthermore the keypad may include any other controls configured to receive user input via buttons touch screen inputs or the like.

The memory may also store the power cut off module which is coupled to kernel . The power cut off module is configured to perform specific acts including placement of the device into a power cut off mode.

Kernel may operatively couple to one or more device drivers that are stored in memory . These device drivers may include a display driver external memory interface driver USB host controller driver and so forth. The device drivers are operatively coupled to devices . Several illustrative devices in eBook reader device are described next.

The PMIC may incorporate or couple to a real time clock RTC . The RTC is configured to maintain a clock suitable for tracking calendar date and time. The RTC may be used for several purposes including acting as a source of information for digital rights management DRM providing time comparison for a global position system unit for ephemeris checking and so forth.

The RTC may facilitate DRM controlled interactions. For example a user of a first eBook reader device may loan an eBook to a second user for the month of May. The RTC s in each eBook reader device may be used to enforce that the loaned eBook is inaccessible to the first user and accessible to the second user during the month of May. For example when the first user attempts to access the loaned eBook during the month of May as indicated by the RTC the DRM may prohibit access to the eBook that has been temporarily loaned to the second user during this time period.

The RTC may be periodically updated from an external reference such as a user input cellular network time network time protocol and so forth. Maintaining the RTC enhances the user experience by allowing DRM functionality even when no external reference is available or when the external reference is not deemed to be trustworthy.

In some implementations the RTC may be coupled to an RTC battery . The RTC battery may provide a power source independent of a primary battery within the eBook reader device to maintain operation of the RTC . For example the RTC battery provides power for the RTC to continue functioning when the primary battery is depleted or removed. The RTC battery may comprise a capacitor coin cell and so forth.

An image processing unit is shown coupled to a display . For example display may be display on eBook reader device described above with reference to . Image processing unit may be configured to at the direction of processor take input data and generate an image suitable for presentation on a display . For example the text data of an eBook may be converted into a bitmap of the page suitable for presentation on the display .

The display may be capable of presenting an image while the processor is in a low power or off mode. Reflective displays including electrophoretic displays cholesteric liquid crystal displays electrofluidic displays and so forth present an image without applied power. In some implementations displays that present an image using applied power such as an organic light emitting diode OLED display may be configured to enter a self refresh mode allowing the display to remain active and present content while the processor is in the low power or off mode. In some implementations the eBook reader device may comprise two or more displays using different technologies. For example a first display may comprise an electrophoretic display while a second display comprises an OLED.

The eBook reader device may also include a keypad coupled thereto. For example this may be the keypad of eBook reader device described above which incorporates page turn buttons and keyboard . As described above the device may also include a power switch . Activation of the power switch generates an interrupt that may be used to trigger a change in power state. For example when the eBook reader device is in a sleep mode activation of the power switch may wakeup the device. In another example the duration of activation of the power switch may be used to specify a particular mode. For example a two second activation while the device is in awake mode may result in the device entering a sleep mode while a four second activation may place the device in the power cut off mode.

Various sleep or low power modes may be used including that which is discussed in pending U.S. patent application Ser. No. 12 261 980 filed Oct. 30 2008 and entitled Low Power Mode for Processor. For example on the Freescale architecture the low power modes many include a doze mode or a state retention mode. While in a low power mode power consumption is reduced. This reduction in power consumption may be accomplished by shutting down unused hardware reducing supply voltages and so forth.

When the eBook reader device is in an active awake mode activation of the power switch may trigger entry into a sleep mode or a power cut off mode. Configuration duration of the activation and so forth may determine whether sleep or power cut off mode are triggered.

The device may also include a USB controller device which may couple to USB devices such as a wireless wide area network modem. The USB controller device may comply with any of the USB standards including USB 1.0 1.1 2.0 3.0 as set forth by the USB Implementers Forum.

The device may also include a hard drive which may use magnetic or optical memory on spinning disks or solid state storage. The hard drive may be used to store content for consumption by the user such as electronic books.

The eBook reader device may further include one or more other devices. These other devices may include a Firewire bus camera global positioning system receiver Bluetooth wireless device PC Card device and so forth.

Operative couplings such as those between the kernel the power cut off module and the device drivers are shown for emphasis. All devices in are operatively coupled with their respective arrows omitted only for clarity of illustration.

Operation shows an eBook reader device in a power cut off mode . In the power cut off mode power is discontinued to components within the eBook reader device except for portions of the PMIC such as the RTC and wait for interrupt circuitry. For example the processor the memory the display the hard drive the external memory the USB devices the devices and so forth are off while the device remains in the power cut off mode .

Operation shows the eBook reader device receiving a transient wakeup interrupt while in power cut off mode . This transient wakeup interrupt may include a momentary activation of the power switch. In some implementations the transient wakeup interrupt comprises a duration of less than 25 milliseconds. In contrast a sustained wakeup interrupt comprises a duration of at least 25 milliseconds. In some implementations the duration of the transient wakeup interrupt may comprise a duration of less than 100 ms while a sustained wakeup interrupt comprises a duration of at least 100 ms.

Transient wakeup interrupts may be generated by factors that are external or internal to the eBook reader device . For example as shown here at operation the eBook reader device may be jostled or bumped resulting in the power switch being physically bounced and generating a transient wakeup interrupt. This jostling may occur during shipment of the device during travel by the user and so forth. Other inadvertent transient activations may occur as a result of the power switch brushing other objects. For example the user placing the eBook reader device in a backpack filled with other items may result in a transient wakeup interrupt.

Operation shows the device remaining in power cut off mode. Here the power cut off module has disregarded the transient wakeup interrupt resulting from the jolt due to the fact that the duration of the transient wakeup interrupt was below a pre determined threshold. As a result the battery of the device has not been needlessly depleted by an unnecessary and here unintended awakening.

Operation shows the user pressing and holding the power switch for at least a pre determined period of time. When this period exceeds the pre determined threshold a sustained wakeup interrupt is generated.

Operation shows the PMIC receiving the sustained wakeup interrupt. The wait for interrupt circuitry which has been minimally active is triggered by the sustained wakeup interrupt and begins the power up of the PMIC . The PMIC powers up the regulators which provide power to components of the device . Once power is applied to the processor memory device and so forth the restart of the device begins. The device is now in an awake mode with the components of the device being active and operational.

Once in the low power sleep mode the device may be inadvertently activated. For example as described above the device may be jostled resulting in a transient wakeup interrupt. It is worthwhile to avoid or minimize a cycle of inadvertent wakeups which could lead to depletion of the battery.

At an eBook reader device is in sleep mode. While sleep mode affords a significant reduction in power consumption over that required during awake mode operation power usage as indicated by graph continues. For example in some implementations the sleep mode may consume about 0.400 milliamps mA . Over the course of several months such as during shipment warehousing transport to the customer and so forth even this low power draw may deplete the battery. As a result of this depletion the user activating the device for the first time may be faced with a lengthy and discouraging charging interval to replenish the depleted battery.

At the device receives a wakeup interrupt and resumes an awake mode. Once awake at when the device determines one or more pre determined conditions have been met the process may proceed to .

An administrator programmer application or the user may specify one or more of the pre determined conditions and associated threshold values upon which the device will engage the power cut off mode.

The pre determined condition may comprise an elapsed time limit since last action by a user. In this implementation when the device has been unused for a pre determined amount of time the device will engage the power cut off mode. The power cut off module calculates an elapsed time by accessing a last active time comprising the date and time of a last action by the user such as stored in a system log file. The time last active may be the last time of a user input last access of content stored on the device and so forth. A current time is accessed from the RTC which has remained operational and thus provides accurate date and time. An elapsed time since last active is calculated by subtracting the current time from the time last active. The elapsed time since last active is compared with an elapsed time limit. When the elapsed time since last active exceeds a pre determined threshold value the process may proceed to . Otherwise the pre determined condition s are not met in this example and the device remains awake.

In another implementation the pre determined condition may comprise a current battery status. For example when the battery status drops below a threshold value the device may engage the power cut off mode.

In yet another implementation the pre determined condition may be a flag indicating when the device has completed initial setup by the user. A device in transit which has not yet been used or personalized through the initial setup by the user would thus have the flag set to a value indicating this un configured state. Thus when the device has not been setup by the user the process may proceed to .

When at the one or more pre determined conditions are met at the power cut off mode is engaged. As described below in more detail with regards to the power cut off mode shuts down the operating system and deactivates power to each component of the device except the RTC and wait for interrupt circuitry.

While in the power cut off mode power consumption of the device is significantly reduced as compared to the sleep mode as shown by graph . For example power consumption may be decreased while in power cut off mode to about 0.034 mA or about 8.5 of the power used in sleep mode. This decrease in power consumption results in a corresponding increase in the period of time during which the device may be stored without depleting the battery. For example rather than a few months of storage possible with the device in sleep mode the device in power cut off mode may be stored for years before depleting the battery.

At a userspace application executes a halt or reboot program. As a part of the halt the init program is run with argument 0 which sends a shutdown signal to all running processes.

At the processes on the device are shutdown at least partly in response to receiving the shutdown signal. Once the userspace applications have shut down control is transferred to the operating system kernel .

At the operating system kernel sends a shutdown event to each registered device driver of the device. The device drivers in turn shutdown or stop associated devices . After each of the devices have been stopped control is transferred to a core kernel code which handles the shutdown or otherwise places the device into OFF mode.

At the PMIC is configured for power cut off mode. A wakeup source is configured and the RTC is configured to remain active. Each switching and linear regulator is also configured to be turned off. For example this includes the switching regulators SW SW CPU Core SW DDR and so forth.

Because a restart of the device is not desired in some instances a watchdog reset signal WDIRESET is configured to 0 which prevents a restart. For example this may involve setting a RESTARTEN bit to 0 in Atlas register 15.

A universal serial bus input voltage VUSBIN may also be turned off when the device is not operating in USB On The Go mode. When on the SWBST is internally switched to supply the VUSB regulator and SWBST will drive VBUS from the VUSBIN pin. This results in a leakage current of about 0.150 mA resulting in unnecessary power consumption.

The PMIC configuration also includes configuring the watchdog reset signal WDIRESET pin on the power management integrated circuit as a general purpose input output interface GPIO . The WDIRESET pin is used in the next step to finalize the power cut off mode.

At the PMIC is placed into the power cut off mode. The placing of the PMIC into the power cut off mode comprises setting the watchdog reset signal pin to a logical low voltage value which in turn places the PMIC into OFF mode. While in this off mode the PMIC retains the operation of the RTC and the wait for interrupt circuitry. Because the RESTARTEN bit has been cleared the Atlas does not restart which would in turn lead to a reset on the processor . The device now settles into the power cut off mode.

At the PMIC is awakened and the switching and linear regulators are powered up thus bringing the device into the awake mode. At the device begins the restart with the processor loading and executing the operating system and other applications.

Although the subject matter has been described in language specific to structural features and or methodological acts it is to be understood that the subject matter defined in the appended claims is not necessarily limited to the specific features or acts described. Rather the specific features and acts are disclosed as illustrative forms of implementing the claims. For example the methodological acts need not be performed in the order or combinations described herein and may be performed in any combination of one or more acts.

