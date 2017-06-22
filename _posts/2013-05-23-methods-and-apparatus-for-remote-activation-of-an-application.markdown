---

title: Methods and apparatus for remote activation of an application
abstract: An application activation method includes interfacing a vehicle computing system with a remote device using an interface protocol. The method also includes sending a query from the vehicle computing system to the remote device to determine applications and/or services available on the remote device that are capable of interaction with the vehicle computing system. Once the applications have been determined, the method includes selecting, at the vehicle computing system, an application or service from the determined available applications and/or services for interaction. The method also includes sending an instruction from the vehicle computing system to an agent on the remote device, the instruction including an indication that the selected application or service is to be activated. Finally, the method includes receiving confirmation, at the vehicle computing system, that the application or service has been activated.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09307012&OS=09307012&RS=09307012
owner: Ford Global Technologies, LLC
number: 09307012
owner_city: Dearborn
owner_country: US
publication_date: 20130523
---
This application is a continuation of U.S. application Ser. No. 12 869 148 filed Aug. 26 2010 issued as U.S. Pat. No. 8 473 575 on Jun. 25 2013 the disclosure of which is incorporated in its entirety by reference herein.

The illustrative embodiments generally relate to methods and apparatus for remote activation of an application.

Modern vehicle communication and or computing systems are becoming increasingly capable of interaction with remote i.e. not part of the vehicle computing system devices. These devices range from but are not limited to cellular phones pdas GPS devices remote servers wireless routers smartphones medical devices personal health and wellness devices tablet PCs laptops etc.

In some instances such as with the FORD SYNC system a remote device may be used as an intermediary means of communication to send a signal to a remote network. Although the remote or nomadic device is used to send this signal it may also be capable of further interaction with the vehicle computing system.

Through the use of application programming interfaces APIs applications running on the nomadic device can interface with the vehicle computing system. For example a program that selectively plays digital music on the nomadic device can be used to play music through the vehicle speaker system using an interface with the vehicle computing system.

Of course when a person is driving a vehicle it is safer to have as much of the driver interaction with devices be as hands free as possible. Accordingly the driver is able to interact with the vehicle computing system through the use of a microphone and voice commands. This prevents to a large extent the driver from having to take focus from the road to activate a desired feature.

Similarly interaction with the nomadic device may or may not be hands free. Of course if the driver is speaking commands to a plurality of devices the devices themselves may be confused not knowing which device the driver is addressing. Further although there may be a particular nomadic device application the driver wishes to have interact with the vehicle the application may not be able to interact with the vehicle until the driver actually activates the application on the nomadic device.

On certain nomadic devices applications are running in a background layer constantly at least in part whereas in other devices the applications may need to be activated. If there is no option to activate an application hands free on the device the driver may need to take focus from the road and manually access the desired application to activate it for interaction with the vehicle computing system.

In a first illustrative embodiment an application activation method includes interfacing a vehicle computing system with a remote device using an interface protocol.

The method also includes sending a query from the vehicle computing system to the remote device to determine applications and or services available on the remote device that are capable of interaction with the vehicle computing system.

Once the applications have been determined the method includes selecting at the vehicle computing system an application or service from the determined available applications and or services for interaction. The method also includes sending an instruction from the vehicle computing system to an agent on the remote device the instruction including an indication that the selected application or service is to be activated.

Finally the method includes receiving confirmation at the vehicle computing system that the application or service has been activated.

In a second illustrative embodiment a computer readable storage medium such as but not limited to a hard drive RAM ROM DVD CD disk flash memory etc. stores instructions for an application activation method. When the instructions are processed a vehicle computing system is caused to perform the steps including sending a query from the vehicle computing system to a remote device to determine applications and or services available on the remote device that are capable of interaction with the vehicle computing system.

The system is also caused to select an application or service from the determined available applications and or services for interaction. The system is further caused to send an instruction from the vehicle computing system to an agent on the remote device the instruction including an indication that the selected application or service is to be activated.

Finally the system is caused to receive confirmation that the application or service has been activated.

In a third illustrative embodiment an application activation method includes receiving at a vehicle computing system a list of applications available on a remote device for interaction with the vehicle computing system.

The method further includes determining that one of the applications is desired for activation. The method also includes sending from the vehicle computing system an instruction to an agent running on the remote device indicating that the one of the applications should be activated.

Finally the method includes receiving at the vehicle computing system confirmation that the one of the applications has been activated.

In the illustrative embodiment shown in a processor controls at least some portion of the operation of the vehicle based computing system. Provided within the vehicle the processor allows onboard processing of commands and routines. Further the processor is connected to both non persistent and persistent storage . In this illustrative embodiment the non persistent storage is random access memory RAM and the persistent storage is a hard disk drive HDD or flash memory.

The processor is also provided with a number of different inputs allowing the user to interface with the processor. In this illustrative embodiment a microphone an auxiliary input for input a USB input a GPS input and a BLUETOOTH input are all provided. An input selector is also provided to allow a user to swap between various inputs. Input to both the microphone and the auxiliary connector is converted from analog to digital by a converter before being passed to the processor.

Outputs to the system can include but are not limited to a visual display and a speaker or stereo system output. The speaker is connected to an amplifier and receives its signal from the processor through a digital to analog converter . Output can also be made to a remote BLUETOOTH device such as PND or a USB device such as vehicle navigation device along the bi directional data streams shown at and respectively.

In one illustrative embodiment the system uses the BLUETOOTH transceiver to communicate with a user s nomadic device e.g. cell phone smart phone PDA etc. . The nomadic device can then be used to communicate with a network outside the vehicle through for example communication with a cellular tower or satellite . In some embodiments tower may be a WiFi access point.

Exemplary communication between the nomadic device and the BLUETOOTH Transceiver is represented by signal .

Pairing a nomadic device and the BLUETOOTH transceiver can be instructed through a button or similar input. Accordingly the CPU is instructed that the onboard BLUETOOTH transceiver will be paired with a BLUETOOTH transceiver in a nomadic device.

Data may be communicated between CPU and network utilizing for example a data plan data over voice or DTMF tones associated with nomadic device . Alternatively it may be desirable to include an onboard modem having antenna in order to communicate data between CPU and network over the voice band. The nomadic device can then be used to communicate with a network outside the vehicle through for example communication with a cellular tower . In some embodiments the modem may establish communication with the tower for communicating with network . As a non limiting example modem may be a USB cellular modem and communication may be cellular communication.

In one illustrative embodiment the processor is provided with an operating system including an API to communicate with modem application software. The modem application software may access an embedded module or firmware on the BLUETOOTH transceiver to complete wireless communication with a remote BLUETOOTH transceiver such as that found in a nomadic device .

In another embodiment nomadic device includes a modem for voice band or broadband data communication. In the data over voice embodiment a technique known as frequency division multiplexing may be implemented when the owner of the nomadic device can talk over the device while data is being transferred. At other times when the owner is not using the device the data transfer can use the whole bandwidth 300 Hz to 3.4 kHz in one example .

If the user has a data plan associated with the nomadic device it is possible that the data plan allows for broad band transmission and the system could use a much wider bandwidth speeding up data transfer . In still another embodiment nomadic device is replaced with a cellular communication device not shown that is installed to vehicle . In yet another embodiment the ND may be a wireless local area network LAN device capable of communication over for example and without limitation an 802.11g network i.e. WiFi or a WiMax network.

In one embodiment incoming data can be passed through the nomadic device via a data over voice or data plan through the onboard BLUETOOTH transceiver and into the vehicle s internal processor . In the case of certain temporary data for example the data can be stored on the HDD or other storage media until such time as the data is no longer needed.

Additional sources that may interface with the vehicle include a personal navigation device having for example a USB connection and or an antenna or a vehicle navigation device having a USB or other connection an onboard GPS device or remote navigation system not shown having connectivity to network .

Further the CPU could be in communication with a variety of other auxiliary devices . These devices can be connected through a wireless or wired connection. Also or alternatively the CPU could be connected to a vehicle based wireless router using for example a WiFi transceiver. This could allow the CPU to connect to remote networks in range of the local router .

With certain nomadic devices applications already existent may not be able to interact with a vehicle computing system unless those applications are already running Since it may be dangerous and or inconvenient for a driver to take focus from the road to activate an application the illustrative embodiments provide a means to activate an application using the vehicle computing system and or verbal driver provided commands so that the driver s focus can remain on driving.

In a first illustrative embodiment shown in the vehicle computing system is made aware of the applications available on a nomadic device that may be interfaceable with the computing system. In this embodiment this is done through the use of BLUETOOTH service discovery protocol SDP records. Other records and or indexes that provide similar information can also be used in conjunction with further illustrative embodiments.

In this embodiment applications are loaded on to a nomadic device by a user. When the application is added to the device the application may be detected and added to a list of available applications as a service record .

In this embodiment the service record contains a list of attributes associated with that service. Additional services may be added to the record or if no more applications exist the index may cease compiling .

Once a list of available services is indexed this list may be searchable by a remote device using BLUETOOTH protocols. One illustrative example of this is shown in .

In this illustrative embodiment the vehicle computing system first detects a connection to a nomadic device . Once the connection has been established the vehicle computing system determines one or more attributes on which it would like to search . For example in this embodiment the system is searching for service records that have an attribute indicating compatibility with the particular vehicle computing system.

Queries could also be for other attributes of applications in the service records. Queries can further be for more than one attribute for example a query for compatible programs that also play music could be launched. Any attribute or combination of attributes recorded in the service record can be searched by the query.

A query may be compiled by the vehicle computing system and is sent to the nomadic device . Alternatively if the nomadic device is capable of compiling the query the desired attribute s may be sent to the device for compilation. In either event the query is designed to return information about the services available on the nomadic device that are compatible with the vehicle computing system.

In yet another embodiment a copy of the service record could be sent to the vehicle computing system for local querying. In this instance a copy of the service record could even be saved locally so that when the vehicle computing system is in communication with a particular nomadic device it already has a record of what programs exist on that device. In this instance it may be desirable to assign or have a version attribute associated with the service record so the vehicle computing system can quickly check to see if a new version exists on the nomadic device.

The query is run using the service record and a list of matching service records is compiled . This list of service records or a corresponding set of information may be returned to the vehicle computing system so the system knows which applications are available on the nomadic device for interface. At this point the vehicle computing system presumably has a list of available services on the nomadic device.

In a further illustrative embodiment the nomadic device is of the sort where an application must be launched before interaction with the vehicle computing system is possible. An example of this interaction is shown in . In this illustrative embodiment the vehicle computing system is able to remotely instruct the activation of a desired service so that the user does not have to manually interact with the nomadic device in order to launch the desired application.

In this embodiment the vehicle computing system checks to see if an agent exists on the nomadic device . The agent in this illustrative case is a program that is capable of instructing the activation of a further application on the nomadic device. The agent can be permanently installed on the nomadic device or it can be loaded activated by the vehicle computing system any time interaction with the nomadic device is desired or each time communication is synched between the system and the device etc. .

If the agent is not present the vehicle computing system will load the agent onto the nomadic device similar checks and steps can be taken for detecting for example if the agent is active and or for activation of a present but not active agent .

Once the agent is present active the vehicle computing system may send a request for activation of a particular application . In this case the request is an activation request although in other instances the vehicle computing system may send a request for interaction with a particular service.

When the agent receives the request from the vehicle computing system it is capable of determining which application on the remote device is to be activated . Then using native device procedures the agent is capable of activating the desired application for interaction with the pending request or in response to an activation request . Once the application is running on the nomadic device the interaction between the vehicle computing system and the nomadic device application can then proceed in an intended fashion.

In this illustrative embodiment control is passed to the vehicle computing system once the application is activated . In another example however the vehicle computing system could continue to pass messages through the agent program.

Using such a system this entire indexing startup procedure can remain completely transparent to a driver. shows an illustrative example of driver interaction with a vehicle computing system in a transparent manner. In this example all the driver knows of the interaction is that the requested feature is performing the requested service.

In this illustrative example the driver submits a request to the vehicle computing system . In this case it is a verbal request for a music service called PANDORA. Of course this is just one illustrative example showing the possibilities for application across a variety of services.

The actual service requested in this case PANDORA is installed on a nomadic device in communication with the vehicle computing system not on the system itself. Accordingly the vehicle computing system may desire to run the application from the nomadic device. Such an act would be possible if either the application was already running or if the vehicle computing system had a means of making the application begin. Of course the user could also activate the application manually but this may create a hazardous driving condition and is preferred to be avoided if possible.

Once the system receives the driver request for the service the system checks its internal logs created in this instance when the nomadic device first interfaced with the vehicle computing system to see if PANDORA is an available service. In other non limiting instances the first time a remote service is requested the indexing could be performed.

If PANDORA is available the system proceeds with activation but if PANDORA is not available the system may recheck the service record . If the service record is checked and it is confirmed that the application is not available the driver may be notified and the attempt to activate the service will cease.

If PANDORA is available the vehicle computing system sends the appropriate command to the agent on the nomadic device . The agent receives the command and if PANDORA is not already activated activates PANDORA . The vehicle computing system may be notified of the activation and then interaction between the vehicle computing system and PANDORA can continue as desired .

In still another illustrative embodiment the vehicle computing system may compile a list of compatible applications on the nomadic device and read display that list to the user.

For example when the nomadic device app provides a list of applications to the vehicle computing system via BT or other wireless communication the system then can determine which of those applications are compatible with the vehicle computing system assuming the app providing the applications has not already determined this . The vehicle computing system could then output the list of available applications so the user knows what applications are currently available.

In still a further embodiment processes running within the vehicle computing system may trigger certain applications dynamically based for example on the user s environment. For example the applications could have certain triggers associated therewith. When one of these triggers was met the vehicle computing system could activate the application or prompt activation of the application. In one example if the user is low on gasoline and a gas station is nearby an application to output the local price average price etc. of gasoline could be activated.

In yet a further embodiment the vehicle computing system is operable to exchange data with the nomadic device to assist the application running on the nomadic device in determining which applications can run on this particular vehicle computing system.

For example if an application requires a 4 navigation display and the vehicle is not equipped with such a display the remote activation application may not list this application as an available application for that session.

If communication is interrupted for example if the battery on the nomadic device dies and the driver has to plug the nomadic device into a power source and reactivate the device this communication procedure can be used to restore the previous connection. In at least one illustrative embodiment the vehicle computing system can store a record of the unexpected interruption and can automatically restore the service and communication once the device is again powered up and available for interaction.

As required detailed embodiments of the present invention are disclosed herein however it is to be understood that the disclosed embodiments are merely exemplary of the invention that may be embodied in various and alternative forms. The figures are not necessarily to scale some features may be exaggerated or minimized to show details of particular components. Therefore specific structural and functional details disclosed herein are not to be interpreted as limiting but merely as a representative basis for teaching one skilled in the art to variously employ the present invention.

While exemplary embodiments are described above it is not intended that these embodiments describe all possible forms of the invention. Rather the words used in the specification are words of description rather than limitation and it is understood that various changes may be made without departing from the spirit and scope of the invention. Additionally the features of various implementing embodiments may be combined to form further embodiments of the invention.

