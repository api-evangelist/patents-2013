---

title: Method and apparatus for setting controlled events for network devices
abstract: A method for controlling a device during content playback commences by receiving at the device at least one user-entered command to instruct the device to take at least one action upon the occurrence of an event during content playback. The device will execute the command to take the at least one action upon occurrence of the event during content playback. The action can include providing a notification to another device, such as in the form of a URL.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09326017&OS=09326017&RS=09326017
owner: Thomson Licensing
number: 09326017
owner_city: Issy les moulineaux
owner_country: FR
publication_date: 20130813
---
This application claims priority under 35 U.S.C. 119 e to U.S. Provisional Patent Application Ser. No. 61 728 044 filed Nov. 19 2012 the teachings of which are incorporated herein.

This invention relates to a method and apparatus for allowing a user to control a device during content playback.

Advances in technology have given rise to a variety of devices capable of displaying audio visual content such as television programs or movies. Traditionally users watched such audio visual video on television sets. Now with the advent of wireless communications devices such as smart cellular telephones portable computers and tablets users can watch audio visual content on many different devices. In most instances such wireless communications devices can interact with each other though one or more networks. The ability of such wireless devices to interact with each other can allow a user to watch content while switching between devices.

The current methodology for enabling a user to interact with remote device relies on trap messages using the Simple Network Messaging Protocol. This approach incurs drawbacks.

Thus a need exists for an easier method for allowing a user to instruct a remote device to perform a given action.

Briefly in accordance with a preferred embodiment of the present principles there is provided a method for controlling a device during content playback. The method commences by receiving at the device at least one user entered command to instruct the device to take at least one action upon the occurrence of an event during content playback. The device will execute the command to take at least one action upon occurrence of the event during content playback.

In addition to the television platform the device of includes elements and which serve as C3XML and C3 command processors respectively for handing C3XML and C3 commands respectively which as discussed hereinafter enable control of the device in accordance with the present principles. For example the elements and could each take the form of memory elements for storing computer code e.g. Java or Javascript for execution by the microprocessor not shown comprising part of the TV platform of the device . Alternatively the elements and could each take the form of separate microprocessors or the like and associated hardware including memories to executing stored code for processing C3XML and C3 commands respectively.

The device also includes an element typically a memory for storing computer code e.g. Javascript or HTML . Such computer code when executed by the microprocessor not shown in the television platform enables content downloading to the second device from the device via the communications protocol . Rather than comprise a memory the element could take the form of a separate microprocessor or the like and associated hardware including one or more memories for executing computer code to enable content downloading from the device to the device via the communications protocol .

In practice the communications protocol takes the form of a wired or wireless network for interconnecting the devices and . For example the communications protocol could comprise a wireless network that utilizes either the Bluetooth or the IEEE 802.11 protocols or any other well known wireless communications protocol. The communications protocol could utilize any one of a wide variety of network protocols without departing from the spirit of the device control technique of the present principles.

The device can comprise any one of a variety of wireless communications devices for example a smart cellular telephone a lab top computer a tablet etc. The particular structure of the device remains unimportant provided that the device has the capability of communicating with the smart television set through the communications protocol to download audio visual content for subsequent playback. For that reason most of the details of the device have been omitted from .

To effectuate remote control of its operation in accordance with the present principles the device includes elements and which serve as C3XML and C3 command processors respectively for handing C3XML and C3 commands respectively. For example the elements and could each take the form of memory elements for storing computer code e.g. Java or Javascript for execution by a microprocessor not shown within the device . Alternatively the elements and could each take the form of separate microprocessors or the like and associated hardware including memories to executing stored code in connection with processing C3XML and C3 commands respectively.

The device also includes an element typically a memory for storing computer code e.g. Javascript or HTML which when executed enables content downloading to the device from the device via the communications protocol . Rather than comprise a memory the element could take the form of a separate microprocessor or the like and associated hardware including one or more memories for executing computer code to enable content downloading from the device to the device via the communications protocol .

Control of a device such either of the devices and occurs though user entered commands typically in the form of either one or more C3XML or C3 commands to instruct the device to take at least one action upon the occurrence of a defined condition during content playback. Two examples of such commands include the Set Cue Point referenced as command 46 and ToggleEvents referenced as command 36 described hereinafter. Each of these commands when executed upon the occurrence of a defined condition during content playback causes the device to perform a particular action.

The SetCuePoint command triggers a given action event upon the reaching a certain point in the content during playback by the device. For example if content has had a certain time elapse the device can take an action including providing a notification to another device. An example of the SetCuePoint command for the smart television expressed in XML appears below.

The ToggleEvent command turns on or off a particular notification when an event takes place during content playback by the device. Instead of the notification comprising a specific message the notification take the form of a Uniform Resource Locator URL corresponding to a resource available to devices interconnected through the communication protocol of including a website media file server and the like. An example of the ToggleEvent command for the smart television expressed in XML appears below.

The system of can also include a content delivery service for delivering content to the devices and via the web proxy . Further the system of can include an authentication server for authenticating the devices and to determine their eligibility to download content from the content delivery service .

Control of the devices and device of occurs in the same manner as discussed above with respect to . In other words a user enters a command typically in the form of either a C3XML or C3 command to instruct the device to take at least one action upon the occurrence of an event during content playback. Just as with the devices and of the Set Cue Point referenced as command 46 and the ToggleEvents referenced as command 36 will cause the device receiving that command to execute the operations described previously with respect to .

The foregoing describes a technique for controlling a device user to control a device during content playback.

