---

title: Navigation system with display control mechanism and method of operation thereof
abstract: A method of operation of a navigation system includes: determining a frame of a map based on a current travel-direction for tracking a movement of a first device; generating a directional-tile from the frame based on the current travel-direction; and transferring the directional-tile for displaying a navigation map on a second device using the directional-tile from the first device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09103679&OS=09103679&RS=09103679
owner: TELENAV, INC.
number: 09103679
owner_city: Sunnyvale
owner_country: US
publication_date: 20130201
---
This application claims the benefit of U.S. Provisional Patent Application Ser. No. 61 594 335 filed Feb. 2 2012 and the subject matter thereof is incorporated herein by reference thereto.

An embodiment of the present invention relates generally to a navigation system and more particularly to a navigation system with display control mechanism.

Modem consumer and industrial electronics especially devices such as graphical navigation systems televisions projectors cellular phones portable digital assistants and combination devices are providing increasing levels of functionality to support modern life including location based information services. Research and development in the existing technologies can take a myriad of different directions.

As users become more empowered with the growth of mobile communication technology new and old paradigms begin to take advantage of this new space. One consumer electronics growth where mobility is quintessential is in location based services such as navigation systems utilizing satellite based Global Positioning System GPS devices. Location based services allow users to create transfer store and or consume information in order for users to create transfer store and consume in the real world . One such use of location based services is to efficiently transfer or route users to the desired destination or service.

Navigation systems and location based services enabled systems have been incorporated in automobiles notebooks handheld devices and other portable products. Today these systems aid users by incorporating available real time relevant information such as maps directions local businesses or other points of interest. The real time information provides invaluable relevant information when available or in service areas. The relevant information is also invaluable when service is not available as well.

Thus a need still remains for a navigation system with display control mechanism. In view of the ever increasing commercial competitive pressures along with growing consumer expectations and the diminishing opportunities for meaningful product differentiation in the marketplace it is increasingly critical that answers be found to these problems. Additionally the need to reduce costs improve efficiencies and performance and meet competitive pressures adds an even greater urgency to the critical necessity for finding answers to these problems.

Solutions to these problems have been long sought but prior developments have not taught or suggested any solutions and thus solutions to these problems have long eluded those skilled in the art.

An embodiment of the present invention provides a method of operation of a navigation system including determining a frame of a map based on a current travel direction for tracking a movement of a first device generating a directional tile from the frame based on the current travel direction and transferring the directional tile for displaying a navigation map on a second device using the directional tile from the first device.

An embodiment of the present invention provides a navigation system including a framing module for determining a frame of a map based on a current travel direction for tracking a movement of a first device a tiling module coupled to the framing module for generating a directional tile from the frame based on the current travel direction and a communication unit coupled to the tiling module for transferring the directional tile for displaying a navigation map on a second device using the directional tile from the first device.

Certain embodiments of the invention have other steps or elements in addition to or in place of those mentioned above. The steps or elements will become apparent to those skilled in the art from a reading of the following detailed description when taken with reference to the accompanying drawings.

The following embodiments are described in sufficient detail to enable those skilled in the art to make and use the invention. It is to be understood that other embodiments would be evident based on the present disclosure and that system process or mechanical changes may be made without departing from the scope of an embodiment of the present invention.

In the following description numerous specific details are given to provide a thorough understanding of the invention. However it will be apparent that the invention may be practiced without these specific details. In order to avoid obscuring an embodiment of the present invention some well known circuits system configurations and process steps are not disclosed in detail.

The drawings showing embodiments of the system are semi diagrammatic and not to scale and particularly some of the dimensions are for the clarity of presentation and are shown exaggerated in the drawing figures. Similarly although the views in the drawings for ease of description generally show similar orientations this depiction in the figures is arbitrary for the most part. Generally the invention can be operated in any orientation. The embodiments have been numbered first embodiment second embodiment etc. as a matter of descriptive convenience and are not intended to have any other significance or provide limitations for an embodiment of the present invention.

One skilled in the art would appreciate that the format with which navigation information is expressed is not critical to some embodiments of the invention. For example in some embodiments navigation information is presented in the format of X Y where X and Y are two coordinates that define the geographic location i.e. a position of a user.

In an alternative embodiment navigation information is presented by longitude and latitude related information. In a further embodiment of the present invention the navigation information also includes a velocity element including a speed component and a heading component.

The term relevant information referred to herein can include the navigation information described as well as information relating to points of interest to the user such as local business hours of businesses types of businesses advertised specials traffic information maps local events and location based community or personal information.

The term module referred to herein can include software hardware or a combination thereof in an embodiment of the present invention in accordance with the context in which the term is used. For example the software can be machine code firmware embedded code and application software. Also for example the hardware can be circuitry processor computer integrated circuit integrated circuit cores a pressure sensor an inertial sensor a microelectromechanical system MEMS passive devices or a combination thereof.

Referring now to therein is shown a navigation system with display control mechanism in an embodiment of the present invention. The navigation system includes a first device such as a client or a server connected to a second device such as a client or server. The navigation system can further include a host device such as a client or a server connected to the first device the second device or a combination thereof. The first device the second device the host device or a combination thereof can communicate using a communication path such as a wireless or wired network.

For example the first device the second device or a combination thereof can be of any of a variety of devices such as a cellular phone personal digital assistant a notebook computer automotive telematics navigation system or other multi functional mobile communication or entertainment device. The first device the second device or a combination thereof can couple either directly or indirectly to the communication path to communicate with each other the host device or a combination thereof or can be a stand alone devices. The first device the second device or a combination thereof further be separate form or incorporated with a vehicle such as a car truck bus or train.

For illustrative purposes the navigation system is described with the first device as a mobile computing device and the second device as a device incorporated with a vehicle. However it is understood that the first device and the second device can be different types of devices. For example the first device can also be a non mobile computing device such as a server a server farm or a desktop computer and the second device can also be a mobile computing device such as a laptop or a tablet computer.

The host device can be any of a variety of centralized or decentralized computing devices or video transmission devices. For example the host device can be a computer grid computing resources a virtualized computer resource cloud computing resource routers switches peer to peer distributed computing devices or a combination thereof.

The host device can be centralized in a single room distributed across different rooms distributed across different geographical locations embedded within a telecommunications network. The host device can couple with the communication path to communicate with the first device the second device or a combination thereof. The host device can also be a client type device as described for the first device .

For illustrative purposes the navigation system is described with the host device as a non mobile computing device although it is understood that the host device can be different types of computing devices. For example the host device can also be a mobile computing device such as notebook computer another client device or a different type of client device. The host device can be a standalone device or can be incorporated with a vehicle such as a car a truck a bus or a train.

Also for illustrative purposes the navigation system is described with the host device as a computing device although it is understood that the host device can be different types of devices. Also for illustrative purposes the navigation system is shown with the first device the second device and the host device as end points of the communication path although it is understood that the navigation system can have a different partition between the first device the second device the host device and the communication path . For example the first device the second device the host device or a combination thereof can also function as part of the communication path .

The communication path can span and represent a variety of networks. For example the communication path can include wireless communication wired communication optical ultrasonic or the combination thereof. Satellite communication cellular communication Bluetooth near field communication NFC Infrared Data Association standard IrDA wireless fidelity WiFi and worldwide interoperability for microwave access WiMAX are examples of wireless communication that can be included in the communication path . Ethernet digital subscriber line DSL fiber to the home FTTH and plain old telephone service POTS are examples of wired communication that can be included in the communication path . Further the communication path can traverse a number of network topologies and distances. For example the communication path can include direct connection personal area network PAN local area network LAN metropolitan area network MAN wide area network WAN or a combination thereof.

Referring now to therein is shown an example of a display interface of the first device and a further display of the second device . The display interface can show a map . The map can be a representation of a geographic area.

For example the map can be a visual representation a set of written or audible coordinates such as global positioning system GPS coordinates or longitude and latitude coordinates of locations entities or a combination thereof within a given geographic area. The map can represent a layout of the given geographic area including a continent a country a state or province a county a city a city block a combination thereof or a region therein.

The map can include a frame . The frame is defined as a portion of the map . The frame can be formatted for displaying on devices such as on the display interface or the further display . A size a shape a format or a combination thereof for the frame can be determined by the navigation system . Details regarding the frame will be discussed below.

The map can include a rotation set having selections for generating a directional tile . The directional tile is defined as a portion of the frame . The directional tile can be displayed on various devices such as on the display interface or the further display . The directional tile can be used to update a portion of the map guidance information or a combination thereof communicated to a user not shown .

For example the directional tile or a portion therein can be displayed or used to update a displayed portion of the map based on movement of the first device the second device or a combination thereof. Also for example the directional tile can be used to maintain a relative direction of the user pointed along a known direction when displaying any portions of the map for the user.

The rotation set is defined as a set of tools for managing orientation of the displayed portion of the frame . The rotation set can include methods or processes for rotating the map or a portion thereof according to a heading of the user. The rotation set can include equations tables process steps methods or a combination thereof predetermined by the navigation system for rotating the map or a portion thereof.

The rotation set can include a set of tiles with each of the selections being an instance of a tile in the set of tiles which can be selected for generating the directional tile . For example the rotation set can have two instances of the selections . The rotation set can have a North Up orientation where navigational north is oriented upward and a South Up orientation where navigational south is oriented upward. The navigation system can select either the North Up tile or the South Up tile for the directional tile .

The rotation set can also include a set of directions such as 0 180 or North East South West and corresponding processes for rotating a display of a portion of the map accordingly. The selections can correspond to individual orientations and the corresponding processes. For example the rotation set can include instructions or steps for rotating the display of a tile such as from North Up display to South Up display to generate the directional tile .

The rotation set can have two four eight or more instances of the selections therein. The rotation set can have instances of tiles or instructions for managing divisions of North South North N East E South S West W N NW W SW S SE E NE or other similar divisions. Details regarding the directional tile and the rotation set will be discussed below.

The map can include a map characteristic . The map characteristic is defined as data for displaying visual characteristics of the map . The map characteristic can include size granularity color display format or a combination thereof.

The display interface can further show a text layer . The text layer can be a display format for displaying a letter a symbol or a combination thereof. The text layer can be displayed in conjunction with displaying the map . The text layer can be displayed separately and over the map . For example the contents of the text layer can remain at a constant location on the display interface while a display of the map can update based on movement of the user.

The display interface can also show status and movement data detected by the navigation system . The display interface can show acceleration a rotational movement a current location and a current travel direction . The acceleration is defined as a change in rate or speed along a direction. The acceleration can be a measure of a linear movement or force associated therewith. The acceleration can also include a change in direction of a movement.

The acceleration can include an acceleration magnitude and an acceleration heading . The acceleration magnitude can be an amount of change in the rate relative to a direction and the acceleration heading can be a direction for the change in the rate.

The navigation system can determine the acceleration of a device. The first device can have a component or a functional unit therein such as an accelerometer determining the acceleration magnitude and the acceleration heading relative to an orientation of the first device .

The rotational movement is defined as a change in orientation relative to a known direction. The rotational movement can be relative to a downward direction as defined by gravity. The rotational movement can be a measure of rotational motion along an axis for defining the orientation of the first device relative to a direction of the gravitational force.

The rotational movement can include a rotational magnitude and a rotational heading . The rotational magnitude can be an amount of change in the orientation relative to the downward direction and the rotational heading can be a direction of the change including a turning axis and direction such as positive or clockwise.

The navigation system can determine the rotational movement of a device. The first device can have a component or a functional unit therein such as a gyroscope determining the rotational magnitude and the rotational heading for the first device relative to the downward direction.

The current travel direction is defined as a direction of movement for a device. The current travel direction can be the direction of the linear movement of the first device . The current travel direction can be a directional component of a velocity of the first device as determined by the navigation system such as by using GPS coordinates for the first device over time or the acceleration of the first device.

The current travel direction can represent a direction of travel for the user the second device or a combination thereof. Details regarding determination of the current travel direction will be discussed below.

The current location can be a representation of a geographical location of the first device . The current location can be represented in various ways. For example the current location can be coordinates such as GPS coordinates or longitude and latitude. Also for example the current location can be an address or a set of landmarks such as an intersection between roads or a highway exit. For further example the current location can be represented on a display of the map .

The display interface can further show a device orientation and a relative forward direction . The device orientation can be an absolute orientation of the first device or a component therein. For example an outward facing portion or side of the display interface can be determined as back or y direction.

The relative forward direction is defined as a determined direction for the user. The relative forward direction can be based on the user s physical attributes such as eyes face torso or a combination thereof. The relative forward direction can be determined based on the device orientation the acceleration the rotational movement the current travel direction downward direction or a combination thereof.

The relative forward direction can be used to distinguish between the user moving forward or backward and can be further used to update the current travel direction . Details regarding the relative forward direction will be discussed below.

The navigation system can show elements similar to the ones displayed on the display interface on the further display of the second device . The further display can show a navigation map . The navigation map is defined as a portion of the map intended for displaying on the further display .

The navigation map can be a representation or display of the frame or a portion therein based on movement of the user. The navigation map can be represented or displayed on the further display of the second device using the directional tile .

The navigation map can also include the current location the current travel direction the text layer or a combination thereof. The navigation map can be displayed to have a vertical component within the current travel direction oriented in an upward direction. Details regarding the representation or display process for the navigation map will be discussed below.

The display interface the further display or a combination thereof can include a display characteristic . The display characteristic is defined as physical traits of a display mechanism within a device. The display characteristic can include a size a dimension a granularity a display format a color scheme or capability or a combination thereof. The display characteristic can be specific to the first device or the second device .

The display characteristic can be different between the first device and the second device . The display characteristic can also be different from the map characteristic . The navigation system can adjust displaying of the map or portions therein based on the display characteristic of the intended device. Details regarding the adjustment will be discussed below.

The further display can include a screen top portion and a screen bottom portion . The navigation system can display the navigation map based on movement of the first device while maintaining the current travel direction pointed toward the screen top portion and not the screen bottom portion .

For illustrative purposes the first device has been described as a consumer mobile device for detecting user movement and the second device has been described as a vehicle integrated device facilitating user travel. However it is understood that the devices can be of different types. For example the second device can be a tablet or a smart phone. Also for example the second device can have a gyroscope and an accelerometer and determine the movement of the second device . For further example the first device can display the navigation map .

Referring now to therein is shown an exemplary block diagram of the navigation system . The navigation system can include the first device the communication path and the second device . The first device can send information in a first device transmission over the communication path to the second device . The second device can send information in a second device transmission over the communication path to the first device .

For illustrative purposes the navigation system is shown with the first device and the second device as client devices although it is understood that the navigation system can have the first device and the second device as different type of devices. For example the first device the second device or a combination thereof can be a server having a display interface.

For brevity of description in this embodiment of the present invention the first device and the second device will be described as client devices. The embodiment of the present invention is not limited to this selection for the type of devices. The selection is an example of an embodiment of the present invention.

The first device can include a first control unit a first storage unit a first communication unit and a first user interface and a location unit . The first control unit can include a first control interface . The first control unit can execute a first software to provide the intelligence of the navigation system .

The first control unit can be implemented in a number of different manners. For example the first control unit can be a processor an application specific integrated circuit ASIC an embedded processor a microprocessor a hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof. The first control interface can be used for communication between the first control unit and other functional units in the first device . The first control interface can also be used for communication that is external to the first device .

The first control interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first control interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the first control interface . For example the first control interface can be implemented with a pressure sensor an inertial sensor a microelectromechanical system MEMS optical circuitry waveguides wireless circuitry wireline circuitry or a combination thereof.

The first storage unit can store the first software . The first storage unit can also store the relevant information such as data representing incoming images data representing previously presented image sound files or a combination thereof.

The first storage unit can be a volatile memory a nonvolatile memory an internal memory an external memory or a combination thereof. For example the first storage unit can be a nonvolatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The first storage unit can include a first storage interface . The first storage interface can be used for communication between the location unit and other functional units in the first device . The first storage interface can also be used for communication that is external to the first device .

The first storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first storage interface can include different implementations depending on which functional units or external units are being interfaced with the first storage unit . The first storage interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first communication unit can enable external communication to and from the first device . For example the first communication unit can permit the first device to communicate with the second device of the host device of an attachment such as a peripheral device or a computer desktop and the communication path .

The first communication unit can also function as a communication hub allowing the first device to function as part of the communication path and not limited to be an end point or terminal unit to the communication path . The first communication unit can include active and passive components such as microelectronics or an antenna for interaction with the communication path .

The first communication unit can include a first communication interface . The first communication interface can be used for communication between the first communication unit and other functional units in the first device . The first communication interface can receive information from the other functional units or can transmit information to the other functional units.

The first communication interface can include different implementations depending on which functional units are being interfaced with the first communication unit . The first communication interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first user interface allows a user not shown to interface and interact with the first device . The first user interface can include an input device and an output device. Examples of the input device of the first user interface can include a keypad a touchpad soft keys a keyboard a microphone an infrared sensor for receiving remote signals or any combination thereof to provide data and communication inputs.

The first user interface can include a graphics processing unit GPU and a first display interface . The first display interface can include a display a projector a video screen a speaker or any combination thereof. The first display interface can include the display interface of .

The first control unit can operate the first user interface to display information generated by the navigation system . The first control unit can also execute the first software for the other functions of the navigation system including receiving location information from the location unit . The first control unit can further execute the first software for interaction with the communication path via the first communication unit .

The location unit can generate location information current heading current acceleration and current speed of the first device as examples. The location unit can be implemented in many ways. For example the location unit can function as at least a part of GPS an inertial navigation system a cellular tower location system a pressure location system or any combination thereof. Also for example the location unit can utilize components such as an accelerometer a gyroscope GPS receiver or a combination thereof.

The location unit can include a location interface . The location interface can be used for communication between the location unit and other functional units in the first device . The location interface can also be used for communication external to the first device .

The location interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The location interface can include different implementations depending on which functional units or external units are being interfaced with the location unit . The location interface can be implemented with technologies and techniques similar to the implementation of the first control unit .

The second device can be optimized for implementing an embodiment of the present invention in a multiple device embodiment with the first device . The second device can provide the additional or higher performance processing power compared to the first device . The second device can also provide optimized display interface compared to the first device such as a bigger screen or a higher definition. The second device can include a second control unit a second communication unit and a second user interface .

The second user interface allows a user not shown to interface and interact with the second device . The second user interface can include an input device and an output device. Examples of the input device of the second user interface can include a keypad a touchpad touch screen soft keys a keyboard a microphone or any combination thereof to provide data and communication inputs. Examples of the output device of the second user interface can include a second graphics processing unit and a second display interface . The second display interface can include a display a projector a video screen a speaker or any combination thereof. The second display interface can also include the further display of .

The second control unit can execute a second software to provide the intelligence of the second device of the navigation system . The second software can operate in conjunction with the first software . The second control unit can provide additional performance compared to the first control unit .

The second control unit can operate the second user interface to display information. The second control unit can also execute the second software for the other functions of the navigation system including operating the second communication unit to communicate with the first device the host device or a combination thereof over the communication path .

The second control unit can be implemented in a number of different manners. For example the second control unit can be a processor an application specific integrated circuit ASIC an embedded processor a microprocessor hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof.

The second control unit can include a second controller interface . The second controller interface can be used for communication between the second control unit and other functional units in the second device . The second controller interface can also be used for communication that is external to the second device .

The second controller interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second controller interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the second controller interface . For example the second controller interface can be implemented with a pressure sensor an inertial sensor a microelectromechanical system MEMS optical circuitry waveguides wireless circuitry wireline circuitry or a combination thereof.

A second storage unit can store the second software . The second storage unit can also store the such as data representing incoming images data representing previously presented image sound files or a combination thereof. The second storage unit can be sized to provide the additional storage capacity to supplement the first storage unit .

For illustrative purposes the second storage unit is shown as a single element although it is understood that the second storage unit can be a distribution of storage elements. Also for illustrative purposes the navigation system is shown with the second storage unit as a single hierarchy storage system although it is understood that the navigation system can have the second storage unit in a different configuration. For example the second storage unit can be formed with different storage technologies forming a memory hierarchal system including different levels of caching main memory rotating media or off line storage.

The second storage unit can be a volatile memory a nonvolatile memory an internal memory an external memory or a combination thereof. For example the second storage unit can be a nonvolatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The second storage unit can include a second storage interface . The second storage interface can be used for communication between other functional units in the second device . The second storage interface can also be used for communication that is external to the second device .

The second storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second storage interface can include different implementations depending on which functional units or external units are being interfaced with the second storage unit . The second storage interface can be implemented with technologies and techniques similar to the implementation of the second controller interface .

The second communication unit can enable external communication to and from the second device . For example the second communication unit can permit the second device to communicate with the first device over the communication path .

The second communication unit can also function as a communication hub allowing the second device to function as part of the communication path and not limited to be an end point or terminal unit to the communication path . The second communication unit can include active and passive components such as microelectronics or an antenna for interaction with the communication path .

The second communication unit can include a second communication interface . The second communication interface can be used for communication between the second communication unit and other functional units in the second device . The second communication interface can receive information from the other functional units or can transmit information to the other functional units.

The second communication interface can include different implementations depending on which functional units are being interfaced with the second communication unit . The second communication interface can be implemented with technologies and techniques similar to the implementation of the second controller interface .

The first communication unit can couple with the communication path to send information to the second device in the first device transmission . The second device can receive information in the second communication unit from the first device transmission of the communication path .

The second communication unit can couple with the communication path to send information to the first device in the second device transmission . The first device can receive information in the first communication unit from the second device transmission of the communication path . The navigation system can be executed by the first control unit the second control unit or a combination thereof.

The first device the second device or a combination thereof can similarly communicate and interact with the host device . Details for the host device will be described below.

For illustrative purposes the second device is shown with the partition having the second user interface the second storage unit the second control unit and the second communication unit although it is understood that the second device can have a different partition. For example the second software can be partitioned differently such that some or all of its function can be in the second control unit and the second communication unit . Also the second device can include other functional units not shown in for clarity.

The functional units in the first device can work individually and independently of the other functional units. The first device can work individually and independently from the second device the host device and the communication path .

The functional units in the second device can work individually and independently of the other functional units. The second device can work individually and independently from the first device the host device and the communication path .

For illustrative purposes the navigation system is described by operation of the first device and the second device . It is understood that the first device the second device and the host device can operate any of the modules and functions of the navigation system .

Referring now to therein is shown a further exemplary block diagram of the navigation system . Along with the first device and the second device of the navigation system can include the host device . The first device can send information in the first device transmission over the communication path to the host device . The host device can send information in a host device transmission over the communication path to the first device .

For illustrative purposes the navigation system is shown with the host device as a server although it is understood that the navigation system can have the host device as a different type of device. For example the host device can be a client device.

Also for illustrative purposes the navigation system is shown with the first device communicating with the host device . However it is understood that the second device can also communicate with the host device in a similar manner as the communication between the first device and the host device between the first device and the second device or a combination thereof.

For brevity of description in this embodiment of the present invention the host device will be described as a server device. The embodiment of the present invention is not limited to this selection for the type of devices. The selection is an example of an embodiment of the present invention.

The host device can be optimized for implementing an embodiment of the present invention in a multiple device embodiment with the first device . The host device can provide the additional or higher performance processing power compared to the first device the second device or a combination thereof. The host device can include a host control unit a host communication unit and a host user interface .

The host user interface allows a user not shown to interface and interact with the host device . The host user interface can include an input device and an output device. Examples of the input device of the host user interface can include a keypad a touchpad touch screen soft keys a keyboard a microphone or any combination thereof to provide data and communication inputs. Examples of the output device of the host user interface can include a host display interface . The host display interface can include a display a projector a video screen a speaker or any combination thereof.

The host control unit can execute a host software to provide the intelligence of the host device of the navigation system . The host software can operate in conjunction with the first software the second software of or a combination thereof. The host control unit can provide additional performance compared to the first control unit .

The host control unit can operate the host user interface to display information. The host control unit can also execute the host software for the other functions of the navigation system including operating the host communication unit to communicate with the first device the second device or a combination thereof over the communication path .

The host control unit can be implemented in a number of different manners. For example the host control unit can be a processor an application specific integrated circuit ASIC an embedded processor a microprocessor hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof.

The host control unit can include a host controller interface . The host controller interface can be used for communication between the host control unit and other functional units in the host device . The host controller interface can also be used for communication that is external to the host device .

The host controller interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the host device .

The host controller interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the host controller interface . For example the host controller interface can be implemented with a pressure sensor an inertial sensor a microelectromechanical system MEMS optical circuitry waveguides wireless circuitry wireline circuitry or a combination thereof.

A host storage unit can store the host software . The host storage unit can also store the such as data representing incoming images data representing previously presented image sound files or a combination thereof. The host storage unit can be sized to provide the additional storage capacity to supplement the first storage unit .

For illustrative purposes the host storage unit is shown as a single element although it is understood that the host storage unit can be a distribution of storage elements. Also for illustrative purposes the navigation system is shown with the host storage unit as a single hierarchy storage system although it is understood that the navigation system can have the host storage unit in a different configuration. For example the host storage unit can be formed with different storage technologies forming a memory hierarchal system including different levels of caching main memory rotating media or off line storage.

The host storage unit can be a volatile memory a nonvolatile memory an internal memory an external memory or a combination thereof. For example the host storage unit can be a nonvolatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The host storage unit can include a host storage interface . The host storage interface can be used for communication between other functional units in the host device . The host storage interface can also be used for communication that is external to the host device .

The host storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the host device .

The host storage interface can include different implementations depending on which functional units or external units are being interfaced with the host storage unit . The host storage interface can be implemented with technologies and techniques similar to the implementation of the host controller interface .

The host communication unit can enable external communication to and from the host device . For example the host communication unit can permit the host device to communicate with the first device the second device or a combination thereof over the communication path .

The host communication unit can also function as a communication hub allowing the host device to function as part of the communication path and not limited to be an end point or terminal unit to the communication path . The host communication unit can include active and passive components such as microelectronics or an antenna for interaction with the communication path .

The host communication unit can include a host communication interface . The host communication interface can be used for communication between the host communication unit and other functional units in the host device . The host communication interface can receive information from the other functional units or can transmit information to the other functional units.

The host communication interface can include different implementations depending on which functional units are being interfaced with the host communication unit . The host communication interface can be implemented with technologies and techniques similar to the implementation of the host controller interface .

The first communication unit can couple with the communication path to send information to the host device in the first device transmission . The host device can receive information in the host communication unit from the first device transmission of the communication path .

The host communication unit can couple with the communication path to send information to the first device in the host device transmission . The first device can receive information in the first communication unit from the host device transmission of the communication path . The navigation system can be executed by the first control unit the host control unit or a combination thereof. The second device can similarly communicate and interact with the host device using the corresponding units and functions therein.

For illustrative purposes the host device is shown with the partition having the host user interface the host storage unit the host control unit and the host communication unit although it is understood that the host device can have a different partition. For example the host software can be partitioned differently such that some or all of its function can be in the host control unit and the host communication unit . Also the host device can include other functional units not shown in for clarity.

The functional units in the host device can work individually and independently of the other functional units. The host device can work individually and independently from the first device the second device and the communication path .

For illustrative purposes the navigation system is described by operation of the first device and the host device . It is understood that the first device the second device and the host device can operate any of the modules and functions of the navigation system .

Referring now to therein is shown a control flow of the navigation system . The navigation system can include a direction normalization module a movement calculation module a map calculation module and a display update module .

The direction normalization module can be coupled to the movement calculation module using wired or wireless connections by having an output of one module as an input of the other module by having operations of one module influence operation of the other module or a combination thereof. Similarly the movement calculation module can be coupled to the map calculation module and the map calculation module can be coupled to the display update module .

The direction normalization module is for determining a direction the user is facing. The direction normalization module can determine the user s movement by determining the relative forward direction of for the user relative to the device orientation of .

The direction normalization module can determine the relative forward direction using the first user interface of . The direction normalization module can use a camera to determine a location and an orientation of the user s eyes face torso or a combination thereof. The direction normalization module can determine the direction the user s eyes face torso or a combination thereof is facing as the relative forward direction .

For example the direction normalization module can determine a plane and a line across known points on the user s body such as eyes shoulders hips edge points of the lips ears or a combination thereof. The direction normalization module can determine a direction orthogonal to the line between the known points and along the plane including the known points as the relative forward direction .

The direction normalization module can represent the relative forward direction using the device orientation . For example if the user is directly in front of and facing the display interface of with the first device of oriented perpendicular to the ground and rotated 90 counter clockwise as shown in the relative forward direction can be the positive y direction of the device orientation as shown in .

The direction normalization module can also determine the relative forward direction using the downward direction as determined by the location unit of . The direction normalization module can determine the direction of the gravitational force using the location unit . The direction normalization module can determine the downward direction as the direction of the gravitational force. The direction normalization module can determine the relative forward direction to be orthogonal to the downward direction.

The direction normalization module can also calculate the relative forward direction using the acceleration of of the first device . The direction normalization module can use the location unit to determine the acceleration magnitude of the acceleration heading of or a combination thereof.

The direction normalization module can assume that the user will mostly move in the relative forward direction . The direction normalization module can determine the relative forward direction as the acceleration heading of occurring most frequently over a period of time predetermined by the navigation system .

For example the direction normalization module can add or integrate all of the acceleration magnitude according to the acceleration heading during the previous minute five minutes an hour or a combination thereof. The direction normalization module can set the direction of the resulting vector as the relative forward direction .

The direction normalization module can use the acceleration stored in the first storage unit of the second storage unit of the host storage unit of or a combination thereof to determine the relative forward direction . The direction normalization module can use the first control unit of the second control unit of the host control unit of or a combination thereof to process the above described data and determine the relative forward direction .

The direction normalization module can the first control unit the second control unit the host control unit or a combination thereof to further determine an independent device movement . The independent device movement is defined as an indication of change in location or orientation of the first device relative to the user. The independent device movement can be represented by a Boolean value or vectors representing the movement of the first device relative to the user.

The direction normalization module can determine the independent device movement using the first user interface . For example the direction normalization module can use the first user interface to determine the independent device movement when the image observed on a camera therein changes. The direction normalization module can adjust the relative forward direction by re determining the relative forward direction as described above.

The direction normalization module can further determine the independent device movement using a movement profile . The movement profile is defined as a set of movement data typical for different types of movement.

The movement profile can include frequency magnitude pattern typically observed by the first device for different types of movement by the user such as walking running walking up steps traveling in a vehicle utilizing an apparatus or a combination thereof. The movement profile can further include data typical for user jumping falling or slipping being involved in a vehicle accident picking up the phone dropping the phone or a combination thereof.

The movement profile can include thresholds for determining the independent device movement . For example the movement profile can have thresholds for identifying the acceleration the rotational movement of a frequency of change thereof or a combination thereof exceeding the thresholds as when user drops the first device or when the user is pulling the first device out of the user s pocket or bag.

The movement profile can include ranges for determining the independent device movement . For example the movement profile can have ranges of values for the acceleration the rotational movement or a combination thereof typical for driving vehicle maneuvers such as turning or stopping user movements user manipulation of the first device or a combination thereof.

The direction normalization module can determine the independent device movement by assigning the appropriate Boolean value when the acceleration the rotational movement or a combination thereof matches exceeds is in range of or a combination thereof as specified by the movement profile . The direction normalization module can further determine the independent device movement by setting the independent device movement as the acceleration the rotational movement or a combination thereof matching exceeding is in range of or a combination thereof as specified by the movement profile .

The direction normalization module can use the relative forward direction the independent device movement the acceleration the rotational movement or a combination thereof to calculate the current travel direction of for tracking a movement of the first device the second device or a combination thereof.

The direction normalization module can use the first device the second device the host device of or a combination thereof to calculate the current travel direction . For example the direction normalization module can use the first control unit the second control unit the host control unit or a combination thereof. Also for example the direction normalization module can use only the first device to calculate the current travel direction .

The direction normalization module can calculate the current travel direction by initializing the current travel direction as the value or vector for the relative forward direction . The direction normalization module can continue with the assumption that the user will mostly travel in the relative forward direction . As such the orientation of the first device used to determine the relative forward direction can also be relative to the current travel direction .

The direction normalization module can further calculate the current travel direction by adding or integrating the acceleration the rotational movement or a combination thereof over a time period predetermined by the navigation system . For example the direction normalization module can determine the current travel direction to be the direction of the vector resulting from adding or integrating the instances of the acceleration the rotational movement or a combination thereof occurring in the preceding one five or thirty minutes an hour or a combination thereof.

The direction normalization module can ignore the acceleration the rotational movement or a combination thereof in calculating the current travel direction when the independent device movement is TRUE . The direction normalization module can alternatively subtract the independent device movement from the acceleration the rotational movement or a combination thereof and use the result of the subtraction to calculate the current travel direction .

The direction normalization module can use the first control interface of the second control interface of the host control interface of or a combination thereof to access the acceleration the rotational movement or a combination thereof. The direction normalization module can store the relative forward direction the current travel direction or a combination thereof in the first storage unit the second storage unit the host storage unit or a combination thereof.

After determining the relative forward direction the current travel direction or a combination thereof the control flow can pass from the direction normalization module to the movement calculation module . The control flow can pass by having the relative forward direction the current travel direction or a combination thereof as an output from the direction normalization module to an input of the movement calculation module storing the relative forward direction the current travel direction or a combination thereof at a location known and accessible to the movement calculation module by notifying the movement calculation module such as by using a flag an interrupt a status signal or a combination thereof or a combination of processes thereof.

The movement calculation module is for calculating a geographical displacement of the user to track a movement of the user. The movement calculation module can calculate the geographical displacement by calculating a displacement vector of the travel for the first device the second device or a combination thereof. The displacement vector can include a magnitude or amount of displacement and a direction of displacement.

The movement calculation module can calculate the displacement vector by summing integrating or a combination of operations thereof using the acceleration the rotational movement or a combination thereof with respect to time duration for the acceleration the rotational movement or a combination thereof. The movement calculation module can access the location unit for determining the acceleration the rotational movement or a combination thereof.

For example the movement calculation module can integrate the acceleration over time to calculate the displacement use the rotational movement to adjust the direction of the displacement combine the components of the displacement over time or a combination thereof. The movement calculation module can further adjust the displacement vector by subtracting or ignoring the independent device movement from the acceleration the rotational movement or a combination thereof.

The movement calculation module can further determine various states representing vehicular maneuvers such as a turn or a lane change user specific movements or maneuvers or a combination thereof. The movement calculation module can use the determined states in conjunction with the acceleration the rotational movement or a combination thereof and the corresponding time duration to calculate the displacement vector .

The movement calculation module can also use positional component of the navigation information such as the GPS coordinates or the longitude latitude information from the location unit . For example the movement calculation module can calculate the displacement vector using the current location of and a previous instance thereof.

The movement calculation module can also use the displacement vector the acceleration the rotational movement various determined states or a combination thereof to determine the current location . For example the movement calculation module can add the displacement vector to the previous instance of the current location to update the current location between positional updates or when positioning functions of the location unit is not available such as when GPS signals or cellular signals are not available or unreliable.

The movement calculation module can determine a reverse movement . The reverse movement is defined as an indication of movement in a direction opposite to a forward direction relative to the user. The direction normalization module can determine the reverse movement such as when a user is walking backwards or driving a vehicle in reverse when the displacement vector includes a component in a direction opposite to the relative forward direction .

For example the movement calculation module can determine the reverse movement when the acceleration includes a directional component opposite to the relative forward direction following a determined stopped state or zero velocity for the first device . Also for example the movement calculation module can use inputs from the second device to determine the reverse movement such as an indication that a gear selection for a vehicle is for travelling in reverse.

The navigation system can assume that the user has the first device on their person. Thus the displacement vector the position the acceleration the rotational movement or a combination thereof detected determined or calculated for the first device can be assumed to be identical to that of the user.

Further the displacement vector the position the acceleration the rotational movement or a combination thereof can be attributed to the second device when the user is operating a vehicle having the second device integrated therein. The navigation system can identify when the user is operating the vehicle with the second device by recognizing when the first device communicates or links to the second device such as using Blue Tooth or NFC.

After calculating the displacement vector determining the reverse movement or a combination thereof the direction normalization module can pass the results to the direction normalization module . The direction normalization module can further use the results to adjust the relative forward direction the current travel direction or a combination thereof. For example the direction normalization module can adjust the current travel direction the relative forward direction or a combination thereof when the reverse movement is maintained for more than a duration predetermined by the navigation system .

Also after calculating the displacement vector determining the reverse movement or a combination thereof the control flow can pass from the movement calculation module to the map calculation module . The control flow can pass in a manner similar to the manner described above from the direction normalization module to the movement calculation module . The control flow can also pass at regular intervals such as after a preset duration or after a preset number of samples from the location unit as prescribed by the navigation system .

The map calculation module is for displaying the map of or portions thereof. The map calculation module can display the map or portions thereof on the first device the second device or a combination thereof. The map calculation module can display based on the current location the movement of the first device or a combination thereof. The map calculation module can include a framing module a tiling module and an adjustment module for displaying the map .

The framing module is for determining the frame of of the map . The framing module can determine the frame based on the current travel direction the current location the displacement vector the acceleration the rotational movement or a combination hereof. The frame can be used to track and display a movement of the user relative to the map .

The framing module can determine the frame by selecting an area in the map corresponding to locations surrounding the current location . The framing module can have a size a division a shape or a combination thereof for selecting the area around a location in the map corresponding to the current location . The size the division such as cells or regions the shape or a combination thereof for selecting the area can be determined by the navigation system .

The framing module can further determine the frame based on the current travel direction . The framing module can include more of area along the current travel direction instead of selecting an area with the current location in the center. For example if the user is traveling north the framing module can determine the frame to include more of the area north of the current location within a given size for the frame and have the current location included in the lower half of the frame .

The framing module can use the first device the second device the host device or a combination thereof to determine the frame . For example the framing module can use the first communication unit of the second communication unit of the host communication unit of or a combination thereof to send and receive the map between the devices. The framing module can use the first control unit the second control unit the host control unit or a combination thereof to determine the frame from the map .

The framing module can also use only the first device to determine the frame . The framing module can use the first storage interface of to access the map stored in the first storage unit . The framing module can use the first control unit to determine the frame from the map .

The tiling module is for generating an appropriate portion of the map for updating a display based on movement of the user. The tiling module can generate the appropriate portion by generating the directional tile of .

The tiling module can generate the directional tile by processing or selecting the rotation set of corresponding to a portion of the frame ahead of the current location according to the current travel direction . The tiling module can use the process step method equations or a combination thereof included in the rotation set to rotate the directional tile to have a upward direction on the directional tile is parallel with the current travel direction .

The tiling module can select the directional tile as the tile having an orientation of the top portion parallel with a directional component of the current travel direction . When the rotation set includes more than two tiles the tiling module can generate the directional tile by selecting the tile having the orientation of the top portion closest to the current travel direction .

The tiling module can also generate the directional tile by rotating a portion of the map according to the rotation set . For example the tiling module can rotate the frame such that the current travel direction would point upward on a display. The tiling module can use the rotational amounts equations processes or a combination thereof included in the rotation set to rotate the frame . The tiling module can then generate the directional tile by selecting a portion of the frame ahead of the current location according to the current travel direction .

Also for example the tiling module can select the rotation set corresponding to an area ahead of the current location according to the current travel direction . The tiling module can rotate the display of the selected area according to rotational amounts equations processes or a combination thereof included in the rotation set matching an orientation closest to the current travel direction .

For a more specific example the tiling module can generate the directional tile from the rotation set having two four eight or more selections for controlling display of the map . The tiling module can calculate the difference between the current travel direction and the upward directions for each of the selections in the rotation set . The tiling module can generate the directional tile using the selection within the rotation set having the smallest difference between the associated upward direction and the current travel direction .

The tiling module can further generate the directional tile from the frame based on the current travel direction and the reverse movement . The tiling module can withhold generating the directional tile for a duration predetermined by the navigation system when the reverse movement is determined by the navigation system . After the predetermined duration the tiling module can generate the directional tile behind the current location according to the current travel direction .

The tiling module can also process the directional tile separate from or before the text layer of . The tiling module can perform the rotations or selections for the directional tile and lay the text layer over the direction tile .

Alternatively the tiling module can be configured to use the area ahead of the current location as described above. The persisting backward motion can be used to update the current travel direction as described above for the direction normalization module and the movement calculation module . After the update the current travel direction can reflect the backward motion and the tiling module can generate the directional tile for the appropriate area for the current travel direction and the reverse movement .

The adjustment module is for adjusting the directional tile based on the map characteristic of the display characteristic of or a combination thereof. The adjustment module can adjust color sizing definition format or a combination thereof based on the display characteristic of the intended display interface to maintain the map characteristic when displayed.

For example the adjustment module can adjust the color the size the definition the display format or a combination thereof for the directional tile to have the directional tile displayed as intended according to the map characteristic . The adjustment module can adjust the directional tile for displaying on the first device the second device the host device or a combination thereof.

For a more specific example the adjustment module can adjust the directional tile using the first device for displaying on the second device . The adjustment module can use the first control unit to adjust the directional tile and use the first communication unit the second communication unit the second user interface or a combination thereof to display the directional tile .

Continuing with the example the map calculation module can transferring the directional tile for displaying the navigation map of on the second device using the directional tile from the first device . The map calculation module can transferring the directional tile by using the first communication unit the second communication unit the host communication unit or a combination thereof to transmit receive or a combination of processes thereof regarding the directional tile .

Continuing with the example the navigation map can be generated based on the directional tile using the second user interface the second control unit or a combination thereof. Based on the use of the directional tile the navigation map can have the current travel direction toward the screen top portion of and not pointed toward the screen bottom portion of .

Also as an example the map calculation module can generate the navigation map using the first control unit the first user interface the second user interface the second control unit the host control unit the host user interface or a combination thereof based on the directional tile . The map calculation module can transfer the navigation map having the directional tile integrated therein to the first device the second device the host device or a combination thereof.

The control flow can pass from the map calculation module to the display update module in a manner similar to the manner between the direction normalization module and the movement calculation module . The display update module is for displaying the navigation map .

When the map calculation module transfers the directional tile the display update module can generate the navigation map . The display update module can generate the project map by moving a portion of the previously displayed portion of the map downward and displaying the directional tile above the corresponding portion.

For example the display update module can use the second control unit the second user interface or a combination thereof to move the previously displayed portion of the map and display the directional tile . Also for example the display update module can the second control unit the second user interface or a combination thereof to update only portions of the navigation map without recalculating or regenerating an entire display of the screen.

It has been discovered that generating the map or the frame in the first device and sending the directional tile from the first device to the second device reduces processing burden and increases efficiency for the navigation system . The first device can generate one whole frame and supply that in tile by tile basis to the second device . The second device can show partial tile receive the tiles only on on demand basis or a combination thereof which reduces the need to generate a whole new image for displaying on the second device .

Based on generating the frame in the first device the navigation system can provide guidance even when both the first device and the second device not connected to the host device . For example the first device can use acceleration velocity durations for acceleration or velocity or a combination thereof to determine the location of the first device and use the rest of the frame to continue providing guidance for the user.

When the map calculation module transfers the navigation map the display update module can remove the previously displayed portion of the map and display the navigation map . For example the display update module can use the second communication unit of to receive the navigation map . The display update module can use the second control unit the second user interface or a combination thereof to display the navigation map .

The display update module can display portions of the directional tile based on the movement of the first device the second device or a combination thereof. The first device can provide control signals for displaying the directional tile or portions therein or provide positional information for the first device the second device or a combination thereof to the second device .

It has been discovered that the frame determined by the first device and the directional tile generated by the first device for displaying on the second device provides stability and accuracy for the navigation system . The frame determined by the first device and the directional tile generated by the first device can provide the stability and accuracy by providing navigational updates for the second device for tracking the user without relying on the host device and continue navigation when connection to the host device is lost or unstable.

It has further been discovered that the navigation map displayed on the second device using the directional tile generated by the first device provides faster and accurate guidance for the user. The navigation map displayed on the second device using the directional tile generated by the first device provides faster and accurate guidance by using immediate readings of the acceleration and the rotational movement from the first device to track the user and update the display of the map instead of relying only on GPS signals.

It has also been discovered that the navigation map displayed using the directional tile the relative forward direction and the reverse movement using the acceleration and the rotational movement of the first device provide consistency and increased usability. The navigation map displayed using the directional tile the relative forward direction and the reverse movement using actual movement of the first device provide consistency and increased usability by displaying the map such that the user s movements are consistently displayed in a known orientation which provides a constant orientation for displaying the map . The use of actual movement readings and the reverse movement can increase the accuracy and provide faster updates for the navigation system .

The navigation system can divide the processes between the functional units of the first device . For example the direction normalization module the movement calculation module or a combination thereof can use the first control unit to process the movement related data. The map calculation module can use the first user interface which can have a GPU implemented with hardware acceleration to process the map and generate the directional tile .

It has been discovered that generating the directional tile using the first user interface for displaying on the second device provides decreased processing burden for the navigation system . The directional tile generated using the first user interface provides decreased processing burden by allowing the first control unit to process other information while decreasing processing burden of the second device the host device or a combination thereof.

For example the host device can be supporting many instances of users increasing processing burden and making it difficult or impossible to provide portions of the map suitable for each of the users. The processes for generating and rotating the directional tile specifically for each user can be performed by the first device . Thusly the navigation system can provide a unique way to serve map requirements for each user by supporting it uniquely from the first device .

Also for example the second device can be a light weight head unit integrated with the vehicle. The second device can access an application programming interface API or a uniform resource locator URL to receive services and images of the map or portions thereof from the first device . The second device can be without or not utilize an operating system positioning or route calculating functionality or a combination thereof.

As a specific example of embodiment for the navigation system the second device can have no capability to rotate the map and the first device cannot create directional tile corresponding to each heading direction. The resource cost and the processing burden can be reduced by having different orientations of the directional tile stored in the rotation set and selecting the appropriate orientation as described above.

The navigation system has been described with module functions or order as an example. The navigation system can partition the modules differently or order the modules differently. For example functions of the direction normalization module and the movement calculation module or functions of the framing module and the tiling module can be combined. Also for example the tile generation or the functions of the adjustment module can be done in the display update module .

The modules described in this application can be hardware implementation or hardware accelerators in the first control unit the second control unit the host control unit the first user interface the second user interface the hose user interface or a combination thereof. The modules can also be hardware implementation or hardware accelerators within the first device the second device or the host device but outside of the first control unit the second control unit the host control unit the first user interface the second user interface the hose user interface or a combination thereof.

The physical transformation from the navigation map and the directional tile results in the movement in the physical world such as user searching for or traveling to a destination using the display of the map . Movement in the physical world results in changes to the current location the acceleration the rotational movement or a combination thereof which can be further captured by the directional tile and the navigation map .

Referring now to therein is shown a flow chart of a method of operation of a navigation system in an embodiment of the present invention. The method includes determining a frame of a map based on a current travel direction for tracking a movement of a first device in a block generating a directional tile from the frame based on the current travel direction in a block and transferring the directional tile for displaying a navigation map on a second device using the directional tile from the first device in a block .

The resulting method process apparatus device product and or system is straightforward cost effective uncomplicated highly versadirectional tile accurate sensitive and effective and can be implemented by adapting known components for ready efficient and economical manufacturing application and utilization. Another important aspect of an embodiment of the present invention is that it valuably supports and services the historical trend of reducing costs simplifying systems and increasing performance.

These and other valuable aspects of an embodiment of the present invention consequently further the state of the technology to at least the next level.

While the invention has been described in conjunction with a specific best mode it is to be understood that many alternatives modifications and variations will be apparent to those skilled in the art in light of the aforegoing description. Accordingly it is intended to embrace all such alternatives modifications and variations that fall within the scope of the included claims. All matters set forth herein or shown in the accompanying drawings are to be interpreted in an illustrative and non limiting sense.

