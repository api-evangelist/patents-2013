---

title: In-vehicle infotainment device and data processing method using the same
abstract: An in-vehicle infotainment device includes a first processor for executing a web application, and a second processor for outputting vehicle data to the first processor. The first processor includes a first-processor-side inter-node communication (INC) interface module for transmitting and receiving information to and from the second processor, the second processor includes a second-processor-side INC interface module for transmitting and receiving information to and from the first processor, and the first processor provides the vehicle data received from the second processor to the web application if a request for vehicle data is received from the web application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09110775&OS=09110775&RS=09110775
owner: LG Electronics Inc.
number: 09110775
owner_city: Seoul
owner_country: KR
publication_date: 20130621
---
Pursuant to 35 U.S.C. 119 e this application claims the benefit of earlier filing date and right of priority to U.S. Provisional Application Ser. No. 61 662 928 filed on Jun. 22 2012 the contents of which are hereby incorporated by reference in their entirety.

The present invention relates to a data processing method using an in vehicle infotainment device mounted in a vehicle and more particularly to an in vehicle infotainment device configured to efficiently process status information of a vehicle including an in vehicle infotainment device and a data processing method using the same.

An in vehicle infotainment device provides a user with a vehicle information display function a navigation function or a TV output function through an image display device mounted in a vehicle. Recently with technological development it is possible to execute a web application through an in vehicle infotainment processor mounted in a vehicle.

Accordingly a web application executed by an in vehicle infotainment device mounted in a vehicle requires a data processing method of utilizing data corresponding to a vehicle status such as drive mode speed or fuel quantity of the vehicle.

Accordingly the present invention is directed to an in vehicle infotainment device and a data processing method using the same that substantially obviate one or more problems due to limitations and disadvantages of the related art.

An object of the present invention is to provide an in vehicle infotainment device configured to efficiently process status information of a vehicle including an in vehicle infotainment device and a data processing method using the same.

Additional advantages objects and features of the invention will be set forth in part in the description which follows and in part will become apparent to those having ordinary skill in the art upon examination of the following or may be learned from practice of the invention. The objectives and other advantages of the invention may be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

To achieve these objects and other advantages and in accordance with the purpose of the invention as embodied and broadly described herein an in vehicle infotainment device includes a first processor for executing a web application and a second processor for outputting vehicle data to the first processor. The first processor includes a first processor side inter node communication INC interface module for transmitting and receiving information to and from the second processor the second processor includes a second processor side INC interface module for transmitting and receiving information to and from the first processor and the first processor provides the vehicle data received from the second processor to the web application if a request for vehicle data is received from the web application.

The first processor may control change of an execution screen of the displayed web application according to the provided vehicle data.

The first processor may receive a user action through an execution screen of the displayed web application and output a vehicle control command according to the user action.

If a vehicle control command is received from the web application the first processor may output the vehicle control command to the second processor via the first processor side INC interface module.

The first processor may restrictively receive the user action according to the vehicle data received from the second processor.

The first processor may restrictively output the vehicle control command according to the vehicle data.

The first processor may provide the vehicle control command to the second processor such that the second processor performs a specific vehicle function.

The first processor may provide the web application with the vehicle data received from the second processor in an interface definition language IDL via a web vehicle plug in.

The vehicle data transmitted and received via the INC interface module may be formatted in a CAN communication language.

In another aspect of the present invention a data processing method includes receiving a request for vehicle data from a web application receiving the vehicle data from an external processor providing the received vehicle data to the web application receiving a vehicle control command from the web application and outputting the received vehicle control command to the external processor such that the external processor controls a vehicle.

It is to be understood that both the foregoing general description and the following detailed description of the present invention are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

Hereinafter a mobile terminal according to the present invention will be described in greater detail with reference to the drawings. The suffixes module and unit of the components used in the following description are used interchangeably for convenience of explanation and are not distinguished from each other in terms of meaning or role.

As shown in the IVI system comprises a main board including an in vehicle infotainment device configured to control an overall operation of the IVI system e.g. a central processing unit CPU a memory configured to store therein programs for processing the in vehicle infotainment device and input output data a key controller configured to control each kind of key signals and an LCD controller configured to control a liquid crystal display LCD .

The memory may store therein map information map data for displaying road guidance information on a digital map. Also the memory may store therein a traffic information collection control algorithm for inputting traffic information according to a road condition in which a vehicle is currently traveling and information for controlling the algorithm.

To the main board may be connected a CDMA code division multiple access module provided with a unique device number and mounted in a vehicle a GPS module configured to receive a GPS signal for guiding a position of a vehicle and tracking a travel path from a starting point to a destination point or to transmit traffic information collected by a user in the form of a global positioning system GPS signal a CD deck configured to play a signal recorded in a compact disk CD a gyro sensor etc. The CDMA module and the GPS module may transmit or receive signals through antennas and .

A broadcast signal receiving module may be connected to the main board and may receive a broadcast signal through an antenna . To the main board may be connected a display unit LCD controlled by the LCD controller through an interface board a front board controlled by the key controller and a camera configured to capture inside and or outside of a vehicle. The display unit is configured to display each kind of video signals and text signals. The front board is provided with buttons for inputting each kind of key signals and supplies a key signal corresponding to a button selected by a user to the main board . And the display unit includes the proximity sensor and the touch sensor touch screen of .

The front board may be provided with a menu key for directly inputting traffic information and the menu key may be configured to be controlled by the key controller .

The audio board is connected to the main board and processes each kind of audio signals. The audio board includes a micro computer configured to control the audio board a tuner configured to receive a radio signal a power unit configured to supply power to the micro computer and a signal processor configured to process each kind of audio signals.

The audio board includes a radio antenna configured to receive a radio signal and a tape deck configured to play an audio tape. The audio board may further interface an audio output unit e.g. amplifier configured to output an audio signal processed by the audio board .

The audio output unit amplifier is connected to a vehicle interface . That is the audio board and the main board are connected to the vehicle interface . To the vehicle interface may be connected to a hands free unit for inputting an audio signal an air bag for a passenger s safety a speed sensor for detecting a vehicle speed etc. The speed sensor is configured to calculate a vehicle speed and to provide information on the calculated vehicle speed to the in vehicle infotainment device .

The navigation session applied to the IVI system is configured to generate road guidance information based on map data and information on a current position of a vehicle and to provide the generated road guidance information to a user.

The display unit is configured to detect a proximity touch in a display window through a proximity sensor. For instance when a pointer e.g. a finger or a stylus pen executes a proximity touch the display unit detects a position where the proximity touch has occurred and output position information corresponding to the detected position to the in vehicle infotainment device .

An audio recognition device or audio recognition module is configured to recognize an audio signal voice generated from a user and to perform a corresponding function according to the recognized audio signal.

The navigation session applied to the IVI system displays a travel path on map data. When the mobile terminal is within a preset distance from a blind spot included in the travel path the navigation session automatically forms a wireless network with a terminal mounted to a peripheral vehicle e.g. vehicle navigation system and or a mobile terminal held by a passerby through a wireless communication network e.g. short range wireless communication network . This may allow the navigation session to receive position information of the peripheral vehicle from the terminal mounted to the peripheral vehicle and to receive position information of the passerby from the mobile terminal held by the passerby.

The main board may be connected to the interface unit and the interface unit may include an external device interface unit and a network interface unit .

The external device interface unit may connect an external device to the IVI system . For this the external device interface unit may include an A V input output unit not shown or a wireless communication unit not shown .

The external device interface unit may be connected to an external device in a wired or wireless manner the external device such as a DVD Digital Versatile Disk a Blu ray a game player a camera a camcorder and a notebook computer. The external device interface unit transmits to the in vehicle infotainment device a video signal or an audio signal or a data signal input from the outside through the connected external device. And the video signal or the audio signal or the data signal processed by the in vehicle infotainment device may be output to the connected external device.

The A V input output unit may include a USB terminal a CVBS Composite Video Banking Sync terminal a component terminal an S video terminal analogue a DVI Digital Visual Interface terminal an HDMI High Definition Multimedia Interface terminal an RGB terminal and a D SUB terminal so that an audio signal and a video signal of an external device are input to the IVI system .

The wireless communication unit may perform a short range wireless communication with other electronic device. For instance the IVI system may be connected to other electronic device through a network according to a communication standard such as Bluetooth RFID Radio Frequency Identification IrDA infrared Data Association UWB Ultra Wideband ZigBee and DLNA Digital Living Network Alliance .

The external device interface unit may be connected to various set top boxes through one of the aforementioned terminals thereby performing inputs and outputs with the set top boxes.

The external device interface unit may receive applications inside a neighboring external device or a list of applications and transmit the received applications or list to the in vehicle infotainment device or the memory .

The network interface unit provides an interface for connecting the image display apparatus to a wired wireless network including an internet network. The network interface unit may be provided with an Ethernet terminal for connection with a wired network and may utilize communication standards such as WLAN Wireless LAN Wi Fi Wibro Wireless broadband Wimax World Interoperability for Microwave Access and HSDPA High Speed Downlink Packet Access for connection with a wireless network.

The network interface unit provides an interface for connecting the IVI system to a wired or wireless network including an internet network. The network interface unit may be provided with an Ethernet terminal for accessing a wired network and may utilize a communication standard such as WLAN Wireless LAN Wi Fi Wibro Wireless broadband Wimax World Interoperability for Microwave Access and HSDPA High Speed Downlink Packet Access for accessing a wireless network.

The network interface unit may transmit or receive data to from other user or other electronic device through an accessed network or other network linked to an accessed network. Especially the network interface unit may transmit some of contents data stored in the IVI system to a user or an electronic device selected from a plurality of users or electronic devices pre registered in the IVI system .

The network interface unit may access a predetermined web page through an accessed network or other network linked to an accessed network. More concretely the network interface unit may access a predetermined web page through a network thus to perform data transmission or data reception with a corresponding server. Also the network interface unit may receive contents or data provided from a contents provider or a network operator. More concretely the network interface unit may receive contents of a film an advertisement a game a VOD a broadcasting signal etc. provided from a contents provider or a network provider through a network and information relating to the contents. The network interface unit may receive update information and an update file of a firmware provided from a network operator. The network interface unit may transmit data to an internet or contents provider or a network operator.

And the network interface unit may receive through a network a desired application by selecting from applications open to the public.

Hereinafter the in vehicle infotainment device included in the IVI system and a vehicle data processing method using the same will be described.

First the in vehicle infotainment device includes a first processor for executing a web application and a second processor for outputting vehicle data to the first processor .

The first processor may include a first processor side inter node communication INC interface module for transmitting and receiving information to and from the second processor and a second processor side INC interface module for transmitting and receiving information to and from the first processor.

The first processor and the second processor may be connected via respective INC interface modules and . INC is a communication protocol between a vehicle processor and an infotainment processor.

The second processor may receive data related to the status of each part of a vehicle or data sensed by a sensor included in the vehicle from a CAN controller . For example the second processor may receive information about whether or not a vehicle is being driven from the CAN controller .

At this time the second processor may receive vehicle data as a message based on the CAN communication standard.

The second processor may output the vehicle data received from the CAN controller to the first processor via the INC module . At this time the INC module may include vehicle data in a CAN interaction region of an INC message and output the vehicle data to the first processor .

Then the first processor may receive an INC message including the vehicle data from the second processor via the INC module .

The first processor may provide the web application with the vehicle data included in the INC message via the web application platform .

The web application platform is used to execute the web application which will be described below with reference to .

In addition the execution screen of the web application may be displayed on a display unit mounted in the vehicle. Then the first processor may receive a user action via the displayed execution screen of the web application .

For example the first processor may receive a user action through buttons for inputting each kind of key signals of the front board . As another example if the display unit is a touchscreen a user action for selecting an object displayed on the execution screen of the web application may be received.

Then the first processor may output a vehicle control command to the second processor according to the received user action. At this time the first processor may output the INC message including the vehicle control command in the CAN interaction region to the second processor through the INC module.

Next the second processor may output the vehicle control command included in the INC message to the CAN controller to control parts of the vehicle.

Hereinafter a web application platform used when the first processor executes the web application will be described.

The web API may be defined as an interface for the web application in the in vehicle infotainment system for accessing vehicle data received via a vehicle data bus. At this time the web API for vehicle data may be defined in a web interface definition language IDL .

The web API may restructure and provide the vehicle data received from the second processor to the web application in the web IDL via the web vehicle plug in .

In addition the web API may output a GET command of the web application for requesting vehicle data or a SET command of the web application for controlling a vehicle to the INC module via the web vehicle plug in.

By the GET command if the vehicle data is received from the second processor the web application platform may change each value included in the vehicle data to a web IDL.

By the SET command if a vehicle control command is output from the web application the web application platform may change the vehicle control command to CAN communication language.

The vehicle control command changed to CAN communication language by the web application platform may be output to the second processor via the INC module .

All interfaces for data exchange may pass to a VehicleEvent interface and may be defined. All vehicle data may be one kind of VehicleEvent and may be accessed as attributes of VehicleEvent.

At this time the GET command the SET command may be Java Script objects. This will be described below with reference to .

At this time an internal value of vehicle data changed to the IDL may be located at distal nodes and . The higher node having at least one lower node and may be defined as an ID indicating a data group having an internal value of common attributes.

In addition the vehicle data may be located as the internal value of the lower nodes and of any one higher node according to the common attributes of the vehicle data.

All nodes may be defined by a variable Type ID. The type attributes may be used as an ID for identifying a vehicle data type and a data validity range. For example with respect to the shown data structure only an A1 b node is valid if the attribute type is A1 b only an A1 a node an A1 b node and an A1 c node are valid if the attribute type is A1 and an A1 a node an A1 b node an A1 c node and an A2 node are valid if the attribute type is A .

Hereinafter a message for requesting vehicle data and outputting a vehicle control command will be described with reference to .

If only data about a vehicle transmission gear type is requested using the GET command the vehicle data may be delivered to the web application via a unified object including a vehicle data set. However only data about a vehicle transmission gear type requested using the GET command in the vehicle data set is valid.

As shown a vehicle transmission gear type variable may be defined. An automatic transmission gear type variable may be defined as TRANSMISSION GEAR TYPE AUTO 1 and a manual transmission gear type variable may be defined as TRANSMISSION GEAR TYPE MANUAL 2.

The web application may request vehicle info transmission gear type from the web vehicle plug in via the GET command and perform a function according to the vehicle transmission gear type data received by the request.

For example if the vehicle transmission type data is TRANSMISSION GEAR TYPE AUTO the web application may output a phase Automatic transmission equipped on the display unit as a console.log function. As another example if the vehicle transmission type data is TRANSMISSION GEAR TYPE MANUAL the web application may output a phase Manual transmission equipped on the display unit as a console.log function.

If only data about a vehicle tire pressure status is requested using the GET command the vehicle data may be delivered to the web application as a unified object including a vehicle data set. However only data about a vehicle tire pressure status requested using the GET command in the vehicle data set is valid.

As shown a variable according to data about vehicle tire pressure status may be defined. A normal vehicle tire pressure status may be defined as TIRE PRESSURE STATUS NORMAL 1 a low vehicle tire pressure status may be defined as TIRE PRESSURE STATUS LOW 2 and a high vehicle tire pressure status may be defined as TIRE PRESSURE STATUS HIGH 3.

The web application may request maintenance tire pressure status from the web vehicle plug in via the GET command and perform a function according to data about the vehicle tire pressure status by the request.

For example if data about all vehicle tire pressure statuses is not 0 the web application may output a message Check your tire pressure on the display unit as a console.log function.

 maintenance tire pressure status may be used as an upper level VehicleEventType of  FRONT LEFT  FRONT RIGHT  REAR LEFT and  REAR RIGHT . Vehicle data requested and received by maintenance tire pressure status may include data of  FRONT LEFT  FRONT RIGHT  REAR LEFT and  REAR RIGHT .

That is if upper level data is requested by the web application all data values of a level lower than the requested upper level may be output.

Next is a diagram showing an example of a message for controlling a vehicle according to an embodiment of the present invention. As the value of each part of a vehicle is set via the SET command the function of the vehicle may be controlled. In assume that a value of a vehicle driving mode is set.

First a driving mode variable may be defined as DRIVING MODE COMFORT 1 DRIVING MODE AUTO 2 DRIVING MODE SPORT 3 DRIVING MODE ECO 4 and DRIVING MODE MANUAL 5.

If the driving mode value is set to DRIVING MODE SPORT the first processor may output a message for changing the driving mode according to the set value to the second processor via the INC module and the web application may output a message Setting driving mode command has been successfully sent to the vehicle bus on the display unit as a console.log function.

At this time the first processor may restrict vehicle function setting via the vehicle data received from the second processor .

For example if the vehicle is being driven the first processor may determine that the vehicle is in a driving mode via the vehicle data received from the second processor . Then even when a SET command for opening a vehicle door is output from the web application the first processor may not output a message for opening the vehicle door to the second processor .

Alternatively if the vehicle is being driven the first processor may halt execution of the web application for controlling the vehicle door.

Alternatively if the vehicle is being driven the first processor may stop the display of the display unit of the web application for controlling the vehicle door.

That is the first processor may halt execution of web application according to the vehicle status determined as the vehicle data. In addition the first processor may stop the display of the web application according to the vehicle status determined as the vehicle data. In addition the first processor may not output the SET command output from the web application to the second processor according to the vehicle status determined as the vehicle data.

In addition the first processor may restrict the range for setting the vehicle by the web application according to the vehicle status determined as the vehicle data.

For example when the vehicle is being driven if a SET command for changing the height of a driver s seat by a predetermined range or more is output the first processor may not output the SET command to the second processor . At this time the first processor may output a message The height of the seat cannot be changed by the predetermined range or more on the display unit .

Alternatively the first processor may change the execution screen of the web application displayed in order to change the height of the driver s seat if the vehicle is being driven. For example the first processor may control the web application which is displayed in order to change the height of the driver s seat to display only a height range of the driver s seat changeable by the user.

As shown an event handler addEventListener for monitoring variation in driving safety door open status which is vehicle event data indicating the open close status of the vehicle door is set.

This means an event handler for executing a handleVehicleData function if the current open close status of the vehicle door is changed.

The handleVehicleData function outputs a message indicating the open closed status of the vehicle door on the display unit according to the value of driving safety door open status .

According to at least one of the embodiments of the present invention it is possible to easily execute a web application in the in vehicle infotainment device.

According to at least one of the embodiments of the present invention it is possible to efficiently process vehicle status information in a web application.

It will be apparent to those skilled in the art that various modifications and variations can be made in the present invention without departing from the spirit or scope of the inventions. Thus it is intended that the present invention covers the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

