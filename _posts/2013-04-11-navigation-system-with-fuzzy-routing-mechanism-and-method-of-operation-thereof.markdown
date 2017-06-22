---

title: Navigation system with fuzzy routing mechanism and method of operation thereof
abstract: A method of operation of a navigation system includes: receiving an origin and a destination; receiving a route keyword for routing between the origin and the destination; identifying a via point matching the route keyword; calculating a keyword group locale based on the via point within a group distance threshold from a keyword group center; and calculating a travel route from the origin to the destination traversing the keyword group locale for displaying on a device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09043147&OS=09043147&RS=09043147
owner: TELENAV, INC.
number: 09043147
owner_city: Sunnyvale
owner_country: US
publication_date: 20130411
---
The present invention relates generally to a navigation system and more particularly to a system for navigation system with a fuzzy routing mechanism.

Modern portable consumer and industrial electronics especially client devices such as navigation systems smart phones portable digital assistants and combination devices are providing increasing levels of functionality to support modern life including location based information services. Research and development in the existing technologies can take a myriad of different directions.

As users become more empowered with the growth of mobile location based service devices new and old paradigms begin to take advantage of this new device space. There are many technological solutions to take advantage of this new device location opportunity. One existing approach is to use location information to provide navigation services such as a global positioning system GPS for a vehicle or on a mobile device such as a cell phone portable navigation device PND or a personal digital assistant PDA .

Often the routing algorithm of navigation devices subjects the user to cumbersome directions in light of simpler choices. In unfamiliar areas the user has no choice but to endure the longer travel time and the added inconvenience without even knowing of other choices.

Thus a need still remains for a navigation system to provide information with improvement in usability performance and accuracy. In view of the importance of positioning systems in modern life it is increasingly critical that answers be found to these problems.

Solutions to these problems have been long sought but prior developments have not taught or suggested any solutions and thus solutions to these problems have long eluded those skilled in the art.

The present invention provides a method of operation of a navigation system including receiving an origin and a destination receiving a route keyword for routing between the origin and the destination identifying a via point matching the route keyword calculating a keyword group locale based on the via point within a group distance threshold from a keyword group center and calculating a travel route from the origin to the destination traversing the keyword group locale for displaying on a device.

The present invention provides a navigation system including a get endpoints module for receiving an origin and a destination a receive route keywords module coupled to the get endpoints module for receiving a route keyword for routing between the origin and the destination a get via points module coupled to the receive route keywords module for identifying a via point matching the route keyword a calculate keyword group locales module coupled to the get via points module for calculating a keyword group locale based on the via point within a group distance threshold from a keyword group center and a get route module coupled to the calculate keyword group locales module for calculating a travel route from the origin to the destination traversing the keyword group locale for displaying on a device.

Certain embodiments of the invention have other steps or elements in addition to or in place of those mentioned above. The steps or elements will become apparent to those skilled in the art from a reading of the following detailed description when taken with reference to the accompanying drawings.

The following embodiments are described in sufficient detail to enable those skilled in the art to make and use the invention. It is to be understood that other embodiments would be evident based on the present disclosure and that system process or mechanical changes may be made without departing from the scope of the present invention.

In the following description numerous specific details are given to provide a thorough understanding of the invention. However it will be apparent that the invention may be practiced without these specific details. In order to avoid obscuring the present invention some well known circuits system configurations and process steps are not disclosed in detail.

The drawings showing embodiments of the system are semi diagrammatic and not to scale and particularly some of the dimensions are for the clarity of presentation and are shown exaggerated in the drawing FIGS. Similarly although the views in the drawings for ease of description generally show similar orientations this depiction in the FIGS. is arbitrary for the most part. Generally the invention can be operated in any orientation. The embodiments have been numbered first embodiment second embodiment etc. as a matter of descriptive convenience and are not intended to have any other significance or provide limitations for the present invention.

The term relevant information referred to herein includes the navigation information described as well as information relating to points of interest to the user such as local business hours of businesses types of businesses advertised specials traffic information maps local events and nearby community or personal information.

The term module referred to herein can include software hardware or a combination thereof in the present invention in accordance with the context used. For example the software can be machine code firmware embedded code and application software. Also for example the hardware can be circuitry processor computer integrated circuit integrated circuit cores a pressure sensor an inertial sensor a micro electromechanical system MEMS optical components passive devices or a combination thereof. The term module represents hardware implementation as described or used later in this document especially when used in apparatus or system claims.

Referring now to therein is shown a navigation system with fuzzy routing mechanism in an embodiment of the present invention. The navigation system includes a first device such as a client or a server connected to a second device such as a client or server with a communication path such as a wireless or wired network. The fuzzy routing mechanism is a mechanism for routing to groups of locations rather than to individual locations.

For example the first device can be of any of a variety of mobile devices such as a cellular phone personal digital assistant a notebook computer automotive telematic navigation system or other multi functional mobile communication or entertainment device. The first device can be a standalone device or can be incorporated with a vehicle for example a car truck bus or train. The first device can couple to the communication path to communicate with the second device .

For illustrative purposes the navigation system is described with the first device as a mobile computing device although it is understood that the first device can be different types of computing devices. For example the first device can also be a non mobile computing device such as a server a server farm or a desktop computer.

The second device can be any of a variety of centralized or decentralized computing devices. For example the second device can be a computer grid computing resources a virtualized computer resource cloud computing resource routers switches peer to peer distributed computing devices or a combination thereof.

The second device can be centralized in a single computer room distributed across different rooms distributed across different geographical locations embedded within a telecommunications network. The second device can have a means for coupling with the communication path to communicate with the first device . The second device can also be a client type device as described for the first device .

In another example the first device can be a particularized machine such as a mainframe a server a cluster server rack mounted server or a blade server or as more specific examples an IBM System z10 Business Class mainframe or a HP ProLiant ML server. Yet another example the second device can be a particularized machine such as a portable computing device a thin client a notebook a netbook a smartphone personal digital assistant or a cellular phone and as specific examples an Apple iPhone Palm Centro or Moto Q Global .

For illustrative purposes the navigation system is described with the second device as a non mobile computing device although it is understood that the second device can be different types of computing devices. For example the second device can also be a mobile computing device such as notebook computer another client device or a different type of client device. The second device can be a standalone device or can be incorporated with a vehicle for example a car truck bus or train.

Also for illustrative purposes the navigation system is shown with the second device and the first device as end points of the communication path although it is understood that the navigation system can have a different partition between the first device the second device and the communication path . For example the first device the second device or a combination thereof can also function as part of the communication path .

The communication path can be a variety of networks. For example the communication path can include wireless communication wired communication optical ultrasonic or the combination thereof. Satellite communication cellular communication Bluetooth Infrared Data Association standard IrDA wireless fidelity WiFi and worldwide interoperability for microwave access WiMAX are examples of wireless communication that can be included in the communication path . Ethernet digital subscriber line DSL fiber to the home FTTH and plain old telephone service POTS are examples of wired communication that can be included in the communication path .

Further the communication path can traverse a number of network topologies and distances. For example the communication path can include direct connection personal area network PAN local area network LAN metropolitan area network MAN wide area network WAN or any combination thereof.

Referring now to therein is shown a first example of a first display interface of the first device . The navigation system of can display a travel route on a map to guide a vehicle from an origin to a destination .

The navigation system can display the travel route including the origin and the destination overlaid on the map . The travel route is a path for traversing from the origin to the destination . The map is defined as a representation of a geographical area. The origin is a location where a vehicle can start travelling. The destination is the location where a vehicle is designated to finish travelling.

The navigation system can display a current location . The current location is defined as a physical location of the first device . The current location can be displayed on the map if the first device is located in a geographic area represented by the map . The origin can be assigned to the current location at the beginning of the routing process.

The navigation system can display via points on the map . The via points are defined as representations of individual locations of points of interest. The via points can include point of interest locations such as businesses residences or landmarks. Each of the via points are associated with one of the keyword group locales .

The navigation system can display the travel route traversing keyword group locales . The keyword group locales are defined as areas representing groups of the via points having a common property. For example the keyword group locales can include the locations for groups of gas stations restaurants or supermarkets. Routing to one of the keyword group locales can include routing to one of the via points included in one of the keyword group locales .

The navigation system can display keyword groups . The keyword groups are defined as the set of the via points having a common property. The keyword groups are associated with the keyword group locales .

Each of the keyword group locales can include a keyword group center . The keyword group center is defined as a location defining the geometric center of one of the keyword group locales .

The keyword group center can be determined in a variety of ways. For example the keyword group center can be assigned to the location of one of the via points . The keyword group center can be assigned to be the geometric center of the via points associated with one of the keyword group locales . The keyword group center can be assigned to be a weighted centroid of the via points of one of the keyword group locales . The keyword group center can be assigned to be a location determined statistically based on the distribution of the via points .

The travel route can include route segments between the origin and one of the keyword group locales between keyword group locales and between one of keyword group locales and the destination . The route segments are defined as the path between two locations. For example the route segments can represent the path from the origin to one of the keyword group locales the path between the keyword group locales or the path from one of the keyword group locales to the destination .

Referring now to therein is shown a second example of the first display interface of the first device . The navigation system can display a route keywords a group distance threshold and a personalization profile .

The route keywords are defined as identifiers representing desired destinations along the travel route of . For example the route keywords can include the entries gas station and fast food indicating that the travel route from the origin to the destination can include the location of a gas station and the location of a fast food restaurant. Each of the route keywords can be represented by one or more of the keyword group locales .

The keyword group locales can include the via points for the individual locations that match the route keywords . For example one of the route keywords for gas station can represent one of the keyword group locales having the via points that indicate the locations of gas stations such as a Shell gas station. In another example one of the via points can indicate the location of a Safeway supermarket for the route keywords for supermarket .

The via points can be clustered into the keyword group locales based on the group distance threshold . The group distance threshold is defined as the maximum distance between the keyword group center of and the via points of one of the keyword group locales . The keyword group center is the geometric center of the location of the via points for one of the keyword group locales .

The group distance threshold is used to calculate which of the via points are assigned to one of the keyword group locales . For example if the group distance threshold is one mile then all of the via points in one of the keyword group locales are within one mile of the keyword group center .

The keyword group locales for one of the route keywords can be further divided based on proximity. One of the route keywords can include multiple instances of the keyword group locales with each of the keyword group locales having a portion of the via points associated with one of the route keywords . For example the via points associated with one of the route keywords for supermarket can be divided up into two of the keyword group locales where each of the keyword group locales represents a different group of supermarkets in a different location.

The group distance threshold can be implemented in a variety of ways. For example the group distance threshold can be a single global value for each of the keyword group locales . Alternatively the group distance threshold can be applied individually to each one of the keyword group locales and provide a different instance of the group distance threshold for each of the keyword group locales .

The personalization profile can include information about preferences that can be used to modify the route keywords and routing operations. The personalization profile can include keyword preferences routing preferences social network preferences and advertising preferences .

The keyword preferences are defined as information that can be used to modify the route keywords . The keyword preferences can be indicate specific preferences for types of locations to be used with the route keywords .

For example the keyword preferences can include a preference for Shell gas stations that can be used to replace the one of the route keywords from gas station to Shell gas station . In another example the keyword preferences can include a preference for McDonalds restaurants by supplementing one of the route keywords for fast food with fast food and McDonalds .

The routing preferences are defined as information used to modify the calculation of the travel route . The routing preference can include information for changing the order of intermediate routing stages preferred locations for the route keywords or a combination thereof.

For example the routing preferences can include the preference to traverse gas stations before visiting a supermarket . In another example the routing preferences can include the preference to visit a supermarket near a home location instead of near a work location.

The social network preferences are defined as information to modify the route keywords based on information retrieved from social networks. The social network preferences can be retrieved from the driver s social networks such as Facebook LinkedIn or Twitter .

For example the social network preferences can include preferences acquired from Facebook indicating the driver likes Starbucks coffee. The personalization profile can be used to modify the route keywords for coffee to include Starbucks Coffee . The social network preferences can be retrieved using an application programming interface API a database query text extraction or a combination thereof.

The advertising preferences are defined as information to modify the route keywords based on advertisements. The advertising preferences can include preferences where the driver has opted in to receiving certain advertisements such as advertisements for locations with discount coupons. For example the personalization profile can be used to modify the route keywords for fast food to only include McDonalds locations offering a discount.

Referring now to therein is shown a third example of the first display interface of the first device . The navigation system can display the route segments a route segment distance a route segment duration a route segment difficulty an optimization criterion and a keyword group count .

The route segment distance is defined as the length of one of the route segments . The route segment distance can include the physical distance along the path a straight line distance between locations a weighted distance based on road conditions or a combination thereof. For example the route segment distance can be two miles.

The route segment duration is defined as the estimated amount of time required to traverse one of the route segments . For example the route segment duration can be ten minutes.

The route segment difficulty is defined as a routing weighing factor indicating the complexity of the route segments . For example one of the route segments with many sharp turns on a mountain road can have the route segment difficulty assigned to ninety. In another example one of the route segments having mostly freeway driving with few turns can have the route segment difficulty assigned to fifty.

The optimization criterion is defined as a metric to determine the relative cost of a route selection. The optimization criterion can include optimization by travel route length travel route duration travel route difficulty or a combination thereof. For example if the optimization criterion is based on the route length then the travel route of can be calculated to include the route segments with the lowest total distance. In another example if the optimization criterion is based on route duration then the travel route can be calculated to include the route segments with the lowest total duration.

The keyword group count is defined as the maximum number of the via points of for one of the keyword group locales of . The keyword group count can be used to determine if one of the keyword group locales should be divided.

Referring now to therein is shown an exemplary diagram of a first routing stage. The first routing stage can calculate the keyword group locales for the via points based on the route keywords of . For example the first display interface of the first device can show two of the keyword group locales having the via points for two of the route keywords of .

The navigation system can include calculating the travel route of using a routing process having multiple stages. For example the first routing stage can identify the via points and the keyword group locales for the route keywords . The second stage can cluster the via points into the keyword group locales based on the proximity of the via points .

The third routing stage can calculate the route segments of between the origin and each of the keyword group locales associated with one of the route keywords . The fourth routing stage can calculate the route segments between the keyword group locales associated with one of the route keywords with the keyword group locales of another of the route keywords . The fifth routing stage can calculate one of the route segments between one of the keyword group locales and the destination .

The navigation system can receive the origin the destination and the route keywords of . The navigation system can use the route keywords for identifying the via points associated with each of the route keywords and cluster the via points to form the keyword group locales . Each of the keyword group locales can include the via points associated with one of the route keywords . Each of the keyword group locales can include the keyword group center .

For example the via points of the one of the route keywords for gas stations can be designated by circles and clustered together into one of the keyword group locales . In another example the via points of one of the route keywords for supermarket can be designed by squares and clustered together into another of the keyword group locales .

Referring now to therein is shown an exemplary diagram of a second routing stage. The first display interface of the first device can show the via points clustered into the keyword group locales based on the route keywords of and the proximity of the via points to the keyword group center .

The navigation system can display the via points on the first display interface The via points of one of the route keywords can be further partitioned into the keyword group locales based on the location of the via points being within the group distance threshold of the keyword group center . Each of the route keywords can have one or more of the keyword group locales that encompass all of the via points associated with one of the route keywords .

For example the via points as indicated by the circles in associated with the route keywords for gas stations can be clustered into two of the keyword group locales as indicated by the triangular lines around the two groups of circles. Each of the keyword group locales includes the via points having a location within the group distance threshold of the keyword group center and associated with the route keywords for gas station .

In another example the via points as indicated by the squares in associated with the route keywords for supermarket can be clustered into two of the keyword group locales as indicated by the hexagonal lines around the two groups of squares. Each of the keyword group locales includes the via points located within the group distance threshold from the keyword group center and associated with the route keywords for supermarket .

Referring now to therein is shown an exemplary diagram of a third routing stage. The first display interface of the first device can show the route segments from the origin to each of the keyword group locales associated with one of the route keywords of .

The navigation system can select the first of the keyword group locales as a route segment target and calculate each of the route segments from the origin to each of the keyword group locales of the route segment target . The route segment target is the next set of the keyword group locales representing one of the route keywords for routing.

The navigation system can select one of the keyword group locales as the route segment target in a variety of ways. For example the route segment target can be selected based on the order of the route keywords . In another example the route segment target can be selected based on the route preference of . In yet another example the route segment target can be selected based on the proximity of one of the keyword group locales to a previously routed location. The route segment target can be the closest of the keyword group locales to the origin .

For example the keyword group locales for gas station can be selected as the route segment target based on the distance from the origin to the keyword group locales . The closest one of the keyword group locales can be selected as the route segment target . In another example the route segment target can be selected based on the routing preference indicating that the route should include supermarkets after gas stations .

The navigation system can calculate the route segments from the origin to the keyword group locales for gas station . Since there are two of the keyword group locales representing clusters of the via points for gas station the navigation system can calculate two of the route segments from the origin to each of the keyword group locales for gas station .

Referring now to therein is shown an exemplary diagram of a fourth routing stage. The first display interface of the first device can show the route segments from each of the keyword group locales for the route keywords of for gas station to each of the keyword group locales for the route keywords for supermarket .

The navigation system can select the next instance of the route segment target of and calculate the route segments from each of the keyword group locales of the previous routing stage to each of the keyword group locales in the current instances of the route segment target .

For example the first display interface can show the route segments from the first set of keyword group locales for gas station to the second set of the keyword group locales for supermarket . The navigation system can calculate the route segments between each of the keyword group locales for gas station and each of the keyword group locales for supermarket .

Because there are two of the keyword group locales for gas station the navigation system can calculate the route segments from the first two locations to the keyword group locales for supermarket . Routing to the two locations can include an additional four of the route segments to be calculated between the keyword group locales for gas station to the keyword group locales for supermarket .

Referring now to therein is shown an exemplary diagram of a fifth routing stage. The first display interface of the first device can show the travel route from the origin to the destination traversing the keyword group locales .

The navigation system can calculate the route segments from the keyword group locales of the previous routing stage to the destination . Since the destination is a single location the route segments can be calculated by clustering all of the via points for the last of the route keywords of together into a single one of the keyword group locales and calculating the final instance of the route segments to the destination .

The navigation system can calculate the travel route by calculating the selected instances of the route segments between the origin the keyword group locales and the destination . The route segments can be selected by calculating a local optimum routing result based on the route segment distance of the route segment duration of the route segment difficulty of or a combination thereof.

For example the travel route can include the route segments between the origin and the keyword group locales for gas station between the keyword group locales for gas station and the keyword group locales for supermarket and between the keyword group locales for supermarket and the destination . The route segments are selected based on the route segment distance having the lowest length. The travel route can be calculated to include the route segments with the lowest overall route cost the lowest route distance the fastest route time or a combination thereof.

Referring now to therein is shown a functional block diagram of the navigation system . The navigation system can include the first device the communication path and the second device . The first device can send information over the communication path to the second device . The second device can send information over the communication path to the first device .

The first device can exchange information over the communication path with the second device . The second device can exchange information over the communication path with the first device .

For illustrative purposes the navigation system is shown with the first device as a client device although it is understood that the navigation system can have the first device as a different type of device. For example the first device can be a server.

Also for illustrative purposes the navigation system is shown with the second device as a server although it is understood that the navigation system can have the second device as a different type of device. For example the second device can be a client device.

For brevity of description in this embodiment of the present invention the first device will be described as a client device such as a smart phone. The present invention is not limited to this selection for the type of devices. The selection is an example of the present invention.

The first device can include a first control unit . The first control unit can include a first control interface . The first control unit can execute a first software to provide the intelligence of the navigation system .

The first control unit can be implemented in a number of different manners. For example the first control unit can be a processor an embedded processor a microprocessor a hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof.

The first control interface can be used for communication between the first control unit and other functional units in the first device . The first control interface can also be used for communication that is external to the first device .

The first control interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first control interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the first control interface . For example the first control interface can be implemented with electrical circuitry microelectromechanical systems MEMS optical circuitry wireless circuitry wireline circuitry or a combination thereof.

The first device can include a first storage unit . The first storage unit can store the first software . The first storage unit can also store the relevant information such as images video maps profiles sensor data navigation information or any combination thereof.

The first storage unit can be a volatile memory a nonvolatile memory an internal memory an external memory or a combination thereof. For example the first storage unit can be a nonvolatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The first storage unit can include a first storage interface . The first storage interface can be used for communication between the first storage unit and other functional units in the first device . The first storage interface can also be used for communication that is external to the first device .

The first storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first storage interface can include different implementations depending on which functional units or external units are being interfaced with the first storage unit . The first storage interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first device can include a first communication unit . The first communication unit can be for enabling external communication to and from the first device . For example the first communication unit can permit the first device to communicate with the second device an attachment such as a peripheral device or a computer desktop and the communication path .

The first communication unit can also function as a communication hub allowing the first device to function as part of the communication path and not limited to be an end point or terminal unit to the communication path . The first communication unit can include active and passive components such as microelectronics or an antenna for interaction with the communication path .

The first communication unit can include a first communication interface . The first communication interface can be used for communication between the first communication unit and other functional units in the first device . The first communication interface can receive information from the other functional units or can transmit information to the other functional units.

The first communication interface can include different implementations depending on which functional units are being interfaced with the first communication unit . The first communication interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first device can include a first user interface . The first user interface allows a user not shown to interface and interact with the first device . The first user interface can include a first user input not shown . The first user input can include buttons sliders knobs virtual buttons voice recognition controls or any combination thereof.

The first user interface can include a first display interface . The first display interface can allow the user to interact with the first user interface . The first display interface can include a display a video screen a speaker or any combination thereof.

The first control unit can operate with the first user interface to display information generated by the navigation system on the first display interface . The first control unit can also execute the first software for the other functions of the navigation system including receiving display information from the first storage unit for display on the first display interface . The first control unit can further execute the first software for interaction with the communication path via the first communication unit .

The first device can include a first location unit . The first location unit can provide the location of the first device . The first location unit can access location information current heading and current speed of the first device as examples.

The first location unit can be implemented in many ways. For example the first location unit can function as at least a part of a global positioning system an inertial navigation system a cellular tower location system a pressure location system or any combination thereof.

The first location unit can include a first location interface . The first location interface can be used for communication between the first location unit and other functional units in the first device . The first location interface can also be used for communication that is external to the first device .

The first location interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first location interface can include different implementations depending on which functional units or external units are being interfaced with the first location unit . The first location interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first device can include a first position unit . The first position unit can provide the position motion and orientation of the first device . The first position unit can access position information of the first device including tilt angle direction orientation rotation motion acceleration or a combination thereof.

The first position unit can be implemented in many ways. For example the first position unit can be an accelerometer a gyroscopic system a MEMS system an electrical contact system an optical orientation system a triangulating system or a combination thereof.

The first position unit can include a first position interface . The first position interface can be used for communication between the first position unit and other functional units in the first device . The first position interface can also be used for communication that is external to the first device .

The first position interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first position interface can include different implementations depending on which functional units or external units are being interfaced with the first position unit . The first position interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

For illustrative purposes the first device can be partitioned having the first user interface the first storage unit the first control unit and the first communication unit although it is understood that the first device can have a different partition. For example the first software can be partitioned differently such that some or all of its function can be in the first control unit and the first communication unit . Also the first device can include other functional units not shown in for clarity.

The navigation system can include the second device . The second device can be optimized for implementing the present invention in a multiple device embodiment with the first device . The second device can provide the additional or higher performance processing power compared to the first device .

The second device can include a second control unit . The second control unit can include a second control interface . The second control unit can execute a second software to provide the intelligence of the navigation system .

The second control unit can be implemented in a number of different manners. For example the second control unit can be a processor an embedded processor a microprocessor a hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof.

The second control interface can be used for communication between the second control unit and other functional units in the second device . The second control interface can also be used for communication that is external to the second device .

The second control interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second control interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the second control interface . For example the second control interface can be implemented with electrical circuitry microelectromechanical systems MEMS optical circuitry wireless circuitry wireline circuitry or a combination thereof.

The second device can include a second storage unit . The second storage unit can store the second software . The second storage unit can also store the relevant information such as images video maps profiles sensor data navigation information or any combination thereof.

The second storage unit can be a volatile memory a nonvolatile memory an internal memory an external memory or a combination thereof. For example the second storage unit can be a nonvolatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The second storage unit can include a second storage interface . The second storage interface can be used for communication between the second storage unit and other functional units in the second device . The second storage interface can also be used for communication that is external to the second device .

The second storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second storage interface can include different implementations depending on which functional units or external units are being interfaced with the second storage unit . The second storage interface can be implemented with technologies and techniques similar to the implementation of the second control interface .

The second device can include a second communication unit . The second communication unit can enable external communication to and from the second device . For example the second communication unit can permit the second device to communicate with the first device an attachment such as a peripheral device or a computer desktop and the communication path .

The second communication unit can also function as a communication hub allowing the second device to function as part of the communication path and not limited to be an end point or terminal unit to the communication path . The second communication unit can include active and passive components such as microelectronics or an antenna for interaction with the communication path .

The second communication unit can include a second communication interface . The second communication interface can be used for communication between the second communication unit and other functional units in the second device . The second communication interface can receive information from the other functional units or can transmit information to the other functional units.

The second communication interface can include different implementations depending on which functional units are being interfaced with the second communication unit . The second communication interface can be implemented with technologies and techniques similar to the implementation of the second control interface .

The second device can include a second user interface . The second user interface allows a user not shown to interface and interact with the second device . The second user interface can include a second user input not shown . The second user input can include buttons sliders knobs virtual buttons voice recognition controls or any combination thereof.

The second user interface can include a second display interface . The second display interface can allow the user to interact with the second user interface . The second display interface can include a display a video screen a speaker or any combination thereof.

The second control unit can operate with the second user interface to display information generated by the navigation system on the second display interface . The second control unit can also execute the second software for the other functions of the navigation system including receiving display information from the second storage unit for display on the second display interface . The second control unit can further execute the second software for interaction with the communication path via the second communication unit .

The second device can include a second location unit . The second location unit can provide the location of the second device . The second location unit can access location information current heading and current speed of the second device as examples.

The second location unit can be implemented in many ways. For example the second location unit can function as at least a part of a global positioning system an inertial navigation system a cellular tower location system a pressure location system or any combination thereof.

The second location unit can include a second location interface . The second location interface can be used for communication between the second location unit and other functional units in the second device . The second location interface can also be used for communication that is external to the second device .

The second location interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second location interface can include different implementations depending on which functional units or external units are being interfaced with the second location unit . The second location interface can be implemented with technologies and techniques similar to the implementation of the second control interface .

The second device can include a second position unit . The second position unit can provide the position motion and orientation of the second device . The second position unit can access position information of the second device including tilt angle direction orientation rotation motion acceleration or a combination thereof.

The second position unit can be implemented in many ways. For example the second position unit can be an accelerometer a gyroscopic system a MEMS system an electrical contact system an optical orientation system a triangulating system or a combination thereof.

The second position unit can include a second position interface . The second position interface can be used for communication between the second position unit and other functional units in the second device . The second position interface can also be used for communication that is external to the second device .

The second position interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second position interface can include different implementations depending on which functional units or external units are being interfaced with the second position unit . The second position interface can be implemented with technologies and techniques similar to the implementation of the second control interface .

For illustrative purposes the second device can be partitioned having the second user interface the second storage unit the second control unit and the second communication unit although it is understood that the second device can have a different partition. For example the second software can be partitioned differently such that some or all of its function can be in the second control unit and the second communication unit . Also the second device can include other functional units not shown in for clarity.

The functional units in the first device can work individually and independently of the other functional units. For illustrative purposes the navigation system is described by operation of the first device . It is understood that the first device can operate any of the modules and functions of the navigation system . For example the first device can be described to operate the first control unit .

The functional units in the second device can work individually and independently of the other functional units. For illustrative purposes the navigation system can be described by operation of the second device . It is understood that the second device can operate any of the modules and functions of the navigation system . For example the second device is described to operate the second control unit .

For illustrative purposes the navigation system is described by operation of the first device and the second device . It is understood that the first device and the second device can operate any of the modules and functions of the navigation system . For example the first device is described to operate the first control unit although it is understood that the second device can also operate the first control unit .

Referring now to therein is shown a control flow of the navigation system . The navigation system can receive the origin of and the destination of in a get endpoints module . The navigation system can receive the route keywords of and calculate the keyword group locales of in a get route keywords module . The navigation system can calculate the travel route of between the origin and the destination traversing the keyword group locales for each of the route keywords in a get route module . The navigation system can display the travel route of in a display route module .

In the control flow of the navigation system as an example each module is indicated by a number and successively higher module numbers follow one another. The control flow can pass from one module to the next higher numbered module unless explicitly otherwise indicated. The modules can be implemented as hardware as hardware acceleration functional units in the first device of or the second device of outside the first control unit of or the second control unit of or as hardware acceleration functional units within the first control unit or the second control unit .

The navigation system can include the get endpoints module . The get endpoints module receives the origin and the destination to calculate the travel route of . After the get endpoints module has completed the control flow can be transferred to the get route keywords module .

The origin can be received in a variety of ways. For example the origin can be automatically selected from the current location of . In another example the origin can be selected on the first device of .

The destination can be received in a variety of ways. For example the destination can be a pre defined location such as home or the office. In another example the destination can be selected on the first device .

The navigation system can include the get route keywords module . The get route keywords module receives the route keywords and identify the via points of associated with the route keywords . The get route keywords module can include a receive route keywords module a personalization module a get via points module and an calculate keyword group locales module . After the get route keywords module has completed the control flow can be transferred to the get route module .

The get route keywords module receives the route keywords in the receive route keywords module . The receive route keywords module receives the route keywords for calculating the keyword group locales to be traversed along the travel route . Each of the route keywords can be used to form the keyword group locales . After the receive route keywords module has completed the control flow can be transferred to the personalization module .

The route keywords represent the category of locations to be traversed along the travel route . For example the driver not shown can provide the route keywords supermarket and gas station to find the travel route from the origin to the destination which includes visiting a gas station and stopping at a supermarket.

The route keywords can be received in a variety of ways. For example the route keywords can selected on the first device . In another example the route keywords can be received as voice commands using speech recognition. In yet another example the route keywords can be retrieved from memory as pre defined values for commonly traveled routes.

The get route keywords module can include the personalization module . The personalization module modifies the route keywords based on the personalization profile of . After the personalization module has completed the control flow can be transferred to the get via points module .

The personalization module can modify the route keywords by modifying certain words with other words based on the personalization profile . The personalization profile can include information to customize the route keywords to reflect the personal preferences of the driver not shown .

The personalization profile includes different types of customization information and can modify the route keywords in a variety of ways. The personalization module can modify the route keywords by replacing or supplementing one of the route keywords with matching entries from the keyword preferences of .

For example the route keywords for supermarket can be replaced with the entry in the keyword preferences linking supermarket with Safeway . The personalization module can calculate the travel route from the origin to the destination including stopping at a Safeway supermarket instead of another type of supermarket.

In another example the personalization module can modify the route keywords by supplementing the route keywords with the matching entry in the keyword preferences . For example the route keywords for grocery store can be modified by adding the terms Wal Mart Target from the matching entry of the keyword preferences to the route keywords . The personalization module can calculate the travel route from the origin to the destination including stopping at a supermarket or a Walmart or a Target .

The keyword preferences can include exclusion preferences for the route keywords . For example the keyword preferences can include the negative preference that the route keywords for gas station should exclude particular types of gas stations such as Shell or BP .

The personalization profile can include the routing preferences of that can be applied during routing to modify the selection of intermediate locations. For example the routing preferences can indicate the driver routing preference to get gas before going grocery shopping or to only shop at stores near a pre defined location such as home or work.

The personalization profile can include the social network preferences of that can modify the route keywords based on information from the driver s social networks including the preferences of the driver s friends. For example the social network preferences can include preferences acquired from LinkedIn indicating the driver has friends who like Starbucks coffee. The social network preferences can be used to modify the route keywords for coffee to include Starbucks Coffee .

The personalization profile can include the advertising preferences of . For example the personalization profile can include preferences where the driver has opted in to receiving certain advertisements such as advertisements with discount coupons. The personalization profile can be used to modify the route keywords for fast food to only include McDonalds locations offering a discount coupon.

The personalization profile can acquire the keyword preferences the routing preference the social network preference and the advertising preference in a variety of ways. For example the personalization profile can be received as an electronic update from an external system an automatic update from another device or received from the first device .

The get route keywords module can include the get via points module . The get via points module identifies the via points for the route keywords . After the get via points module has completed the control flow can be transferred to the calculate keyword group locales module .

The get via points module can identify the via points associated with each of the route keywords . The via points for the route keywords can be identified in a variety of ways. For example the via points can be identified by searching a local mapping database for entries that match each of the route keywords . In another example the via points can be identified by querying an external navigation database system to retrieve entries that match the route keywords .

The via points can represent locations corresponding the one of the route keywords . For example one of the via points for the route keywords for gas station can represent the Shell gas station on Lafayette Street in Santa Clara Calif.

The set of the via points for the route keywords can be constrained to the geographical region surrounding the origin and the destination . For example the via points can be can be constrained to locations within one half of the straight line distance between the origin and the destination . In another example the via points can be constrained to a fixed distance value such as ten miles.

The get route keywords module can include the calculate keyword group locales module . The calculate keyword group locales module calculates the keyword group locales by identifying the via points for the route keywords . After the calculate keyword group locales module has completed the control flow can be transferred to the get route module .

The keyword group locales can be calculated by identifying the via points associated with one of the route keywords to one of the keyword group locales . Each of the route keywords can have one or more keyword group locales . Each of the keyword group locales can have the keyword group center of that indicates the location of each of the keyword group locales .

The calculate keyword group locales module calculates the distance between the via points and the keyword group center for each of the keyword group locales . The via points within the group distance threshold of of the keyword group center are associated with the keyword group .

The keyword group center can be assigned in a variety of ways. The keyword group center can be assigned to the location of one of the via points . The keyword group center can be assigned to the location determined by calculating the geometric center for the via points associated with one of the route keywords . The keyword group center can be based on the distribution of the via points for one of the route keywords .

The via points associated with one of the route keywords can be identified with the keyword group locales in a variety of ways. The via points can be calculated to be associated with one of the keyword group locales based on the route keyword the proximity of the via points or a combination thereof.

For example the via points associated with one of the route keywords can be assigned to one of the keyword group locales . The via points associated with gas station can all be assigned to one of the keyword group locales designated as gas station .

In another example the via points associated with gas station can be split into two of the keyword group locales based on location of each of the via points lying within the group distance threshold of the keyword group center . The via points associated with supermarket can be clustered into two of the keyword group locales designed supermarket1 and supermarket2 where the keyword group locales are in locations separated in distance.

The keyword group locales can be adjusted to change the size and number of the keyword group locales . For example one of the keyword group locales can be split into two of the keyword group locales or two of the keyword group locales can be combined to form a single one of the keyword group locales .

The via points can be calculated to be assigned to one of the keyword group locales based on the proximity of the via points within the group distance threshold to the keyword group center . The group distance threshold can be varied to include more or fewer of the via points .

The via points can be calculated to be assigned to one of the keyword group locales based on the keyword group count of . For example if the keyword group count is set to three indicating that the keyword group locales can have a maximum of three of the via points then the number of the keyword group locales can be determined by dividing the number of the via points associated with the one of the route keywords by three.

The navigation system can include the get route module . The get route module calculates the travel route from the origin to the destination traversing the keyword group locales for the route keywords .

The get route module can include a select keyword group locale module an adjust keyword group locales module a calculate route segments module and a calculate travel route module . After the get route module has completed the control flow can be transferred to the display route module .

The get route module calculates the travel route iteratively by selecting the route segment target of adjusting the keyword group locales in the adjust keyword group locales module calculating one the route segments of between two locations and repeating until the route segments of for all locations have been calculated. Once the route segments have been calculated the calculate travel route module can calculate the travel route based on the route segments matching the optimization criterion of .

The get route module can include the select keyword group locale module . The select keyword group locale module selects the keyword group locales to be used for routing. After the select keyword group locale module has completed the control flow can be transferred to the adjust keyword group locales module .

The select keyword group locale module can determine the order of routing for the keyword group locales by selecting the route segment target of for the next routing destination along the travel route . The select keyword group locale module can iteratively identify the next routing destination based on the previous routing destination.

The select keyword group locale module can identify one of the keyword group locales to be the next routing destination in a variety of ways. The route segment target can be selected based on the order of the route keywords the preference profile the distance from the previous one of the keyword group locales or a combination thereof.

For example the route segment target can be selected based on the order of the route keywords . The route segment target for the next routing destination can be the next one of the route keywords .

In another example the route segment target can be selected based on the preference profile including the routing preferences indicating that a gas station should be routed to first before routing to a supermarket. In another example the preference profile can include the routing preferences that a supermarket should be located near the target destination when the target destination is home.

In yet another example the route segment target can be selected based on the distances between the keyword group locales . The route segment target can be the closest of the keyword group locales from the previous routing destination.

The get route module can include the adjust keyword group locales module . The adjust keyword group locales module adjusts the size and number of the keyword group locales associated with each of the route keywords to optimize the routing cost of the travel route . After the adjust keyword group locales module has completed the control flow can be transferred to the calculate route segments module .

The size and number of the keywords groups can be adjusted to change the amount of time and resources required to calculate the route segments between the origin the keyword group locales and the destination . The keyword group locales can be adjusted to optimize the efficiency and precision of routing. Adjusting is defined as altering the size and number of the keyword group locales . Adjusting can include splitting one of the keyword group locales into two groups or combining two of the keyword group locales into one of the keyword group locales .

Routing efficiency is defined as routing to reduce the amount of time and resources needed to calculate the routing combinations between locations. Routing efficiency can be increased by reducing the number of routing locations in the travel route . For a route through two possible intermediate destinations such as a bank with four locations and the post office with two locations a total of 8 4 32 possible routing solutions must be calculated. Routing through an instance of the keyword group for the banks and an instance of the keyword group for the post offices has only one routing solution and results in the routing efficiency increasing by a factor of 32.

Routing precision is defined as routing to find a global minimum of routing cost for a travel route. Routing precision can be based on minimizing the routing time routing distance or a combination thereof. Routing precision can be improved by increasing the number of routing locations to determine the global minimum of routing cost.

For example for a keyword group of three banks with two banks close to one another and the third bank far away from the first two banks the keyword group can be partitioned into one instance of the keyword group with the two nearby banks and another instance of the keyword group with the more distant bank. Increasing the number of the keyword group allows routes through either instance of the keyword group and can increase the routing precision by a factor of two over the routing precision of the single instance of the keyword group routing solution.

The keyword group locales can be adjusted in a variety of ways. The keyword group locales can be adjusted by increasing the number of the keyword group locales and reducing the number of via points in each of the keyword group locales . The keyword group locales can also be adjusted by combining two of the keyword group locales and increasing the number of via points in each of the keyword group locales .

For example the keyword group locales can be adjusted to increase the routing efficiency by reducing the number of the keyword group locales . Two or more of the keyword group locales can be combined into one of the keyword group locales . The keyword group locales can be adjusted to include all of the via points for each of the route keywords assigned to one of the keyword group locales . By reducing the number of the keyword group locales associated with one of the route keywords the total number of the keywords groups is minimized reducing the total number of routing path permutations and increasing routing efficiency.

In another example the keyword group locales can be adjusted to increase the precision of routing. The keyword group locales can be adjusted to include only one of the via points in each of the keyword group locales . By increasing the number of intermediate locations the global minimum of routing cost can be determined but the total number of routing path permutations is increased.

In yet another example the keyword group locales can be adjusted based on the results of the previous routing phase including the number of the route segments . For example if the number of route segments calculated between two of the keyword group locales is greater than three then the adjust keyword group locales module can reduced the number of keyword group locales to reduce the total number of path permutations.

The get route module can include the calculate route segments module . The calculate route segments module calculates the route segments between the origin the keyword group locales and the destination .

The calculate route segments module can calculate the route segments between two locations. The calculate route segments module can calculate the route segments from the origin to one of the keyword group locales between two of the keyword group locales or from one of the keyword group locales to the destination . The route segments can be calculated independently of one another.

The route segments can be calculated in a variety of ways. For example the route segments can be calculated by determining the path between locations with the shortest distance the shortest time or a combination thereof.

In another example the route segments can be calculated by determining the path with the fewest turns between the two locations. In yet another example the route segments can be calculated using a depth first search a breadth first search adaptive routing heuristic routing rule based routing dynamic routing or a combination thereof.

In an illustrative example the calculate route segments module can calculate the route segments from the origin to each of the keyword group locales associated with the route keywords for gas station . In another example the calculate route segments module can calculate the route segments from the keyword groups associated with the route keywords for gas station to the keyword group locales associated with the route keywords for supermarket .

In another example once the driver has arrived at the one of the keyword group locales the get route module can provide a secondary routing for navigating to one of the via points . Since the via points are within the group distance threshold of the keyword group center the terminal routing to one of the via points can be calculated by determining the route segments from the current location of at one of the keyword group locales to one of the via points .

The get route module can include the calculate travel route module . The calculate travel route module calculates the travel route between the origin and the destination based on the optimization criterion . After the calculate travel route module has completed the control flow can be transferred to the display route module .

The travel route can be calculated by selecting a path through the route segments between the origin the keyword group locales and the destination . The route segments can be selected based on the optimization criterion .

The travel route can be calculated in a variety of ways. For example if the optimization criterion is for shortest distance then the travel route can be calculated by identifying the path with the route segments have the lowest total distance. The calculate travel route module can select the route segments with the shortest length at each stage to form the travel route .

In another example if the optimization criterion is for shortest time then the travel route can be calculated by identifying the path with the route segments having the lowest total travel time. The calculate travel route module can select the route segments where the route segment duration of is shortest at each stage and combine the route segments to form the travel route .

The navigation system can include the display route module . The display route module can display the travel route on the first display interface of of the first device .

The display route module presents the travel route and the route segments overlaid on the map of on the first display interface . The display route module can provide audible instruction and navigation commands based the current location of of the vehicle of using the first location unit of .

The physical transformation from displaying the travel route results in movement in the physical world such as people using the first device the vehicle or a combination thereof to navigate along the travel route via the keyword group locales based on the operation of the navigation system . As the movement in the physical world occurs the movement itself creates additional information that is converted back to assist in routing and adjusting the keyword group locales for calculating the travel route . This supports the continued operation of the navigation system along the travel route via the keyword group locales and to continue the movement in the physical world.

The first software of of the first device can include the navigation system . For example the first software can include the get endpoints module the get route keywords module the receive route keywords module the personalization module the get via points module and the calculate keyword group locales module .

The first software can include the get route module the select keyword group locale module the adjust keyword group locales module the calculate route segments module and the calculate travel route module . The first software can include the display route module .

The first control unit of can execute the first software for the get endpoints module to receive the origin and the destination for the travel route . The first control unit can execute the first software for the get route keywords module to receive the route keywords and identify the keyword group locales .

The first control unit can execute the first software for the receive route keywords module to receive the route keywords . The first control unit can execute the first software for the personalization module to modify the route keywords .

The first control unit can execute the first software for the get via points module to identify the locations of the via points associated with the route keywords . The first control unit can execute the first software for the calculate keyword group locales module to cluster the via points into the keyword group locales .

The first control unit can execute the first software for the get route module to calculate the travel route . The first control unit can execute the first software for the select keyword group locale module to identify the next one of the keyword group locales for routing. The first control unit can execute the first software for the adjust keyword group locales module to adjust the number of keyword group locales and the number of the via points in each of the keyword group locales .

The first control unit can execute the first software for the calculate route segments module to calculate the route segments of the travel route . The first control unit can execute the first software for the calculate travel route module to calculate the travel route . The first control unit can execute the first software for the display route module to present the travel route on the first display interface of the first device .

The second software of of the second device can include the navigation system . For example the second software can include the get endpoints module the get route keywords module the receive route keywords module the personalization module the get via points module and the calculate keyword group locales module .

The second software can include the get route module the select keyword group locale module the adjust keyword group locales module the calculate route segments module and the calculate travel route module . The second software can include the display route module .

The second control unit of can execute the second software for the get endpoints module to receive the origin and the destination for the travel route . The second control unit can execute the second software for the get route keywords module to receive the route keywords and identify the keyword group locales .

The second control unit can execute the second software for the receive route keywords module to receive the route keywords . The second control unit can execute the second software for the personalization module to modify the route keywords .

The second control unit can execute the second software for the get via points module to identify the locations of the via points associated with the route keywords . The second control unit can execute the second software for the calculate keyword group locales module to cluster the via points into the keyword group locales .

The second control unit can execute the second software for the get route module to calculate the travel route . The second control unit can execute the second software for the select keyword group locale module to identify the next one of the keyword group locales for routing. The second control unit can execute the second software for the adjust keyword group locales module to adjust the number of keyword group locales and the number of the via points in each of the keyword group locales .

The second control unit can execute the second software for the calculate route segments module to calculate the route segments of the travel route . The second control unit can execute the second software for the calculate travel route module to calculate the travel route . The second control unit can execute the second software for the display route module to present the travel route on the first display interface of the first device .

The navigation system can be partitioned between the first software and the second software . For example the second software can include the get route module the select keyword group locale module the adjust keyword group locales module the calculate route segments module and the calculate travel route module . The second control unit can execute modules partitioned on the second software as previously described.

The first software can include the get endpoints module the get route keywords module the receive route keywords module the personalization module the get via points module the calculate keyword group locales module and the display route module . Based on the size of the first storage unit of the first software can include additional modules of the navigation system . The first control unit can execute the modules partitioned on the first software as previously described.

The first user interface of can receive an entry by the user for the route keywords . The first control unit can operate the first communication unit of to send the route keywords to the second device . The first control unit can operate the first software to operate the first location unit .

The second communication unit of can receive the route keywords from the first device . The second control unit can adjust the keyword group locales and calculate the travel route . The second communication unit can send the travel route to the first device through the communication path of to be displayed on first display interface .

It has been discovered that the present invention provides faster routing with reduced computational power requirements by routing between the keyword group locales . By limiting routing to the keyword group locales the total number of possible routing permutations is reduced providing fasting routing with fewer resources.

It has been discovered that the present invention balances efficiency and routing precision by routing to the keyword group locales and adjusting the keyword group locales by altering the number of the via points in each of the keyword group locales . By adjusting the size of the keyword group locales the navigation system can identify better routes with fewer resources.

It has been discovered that the present invention provides increased functionality and provides improved route selection by identifying the via points associated with one of the route keywords by modifying the route keywords with the keyword preference . By modifying the route keywords with the keyword preferences the navigation system can find better choices when routing by keywords.

It has been discovered that the present invention provides improved routing quality by reducing the number of the via points associated with the route keywords by using keyword preferences with exclusion preferences to indicate locations not to include with the route keywords . Automatically modifying the route keywords with negative preferences allows the navigation system more accurate locations when routing.

It has been discovered that the present invention provides increased functionality and improved routing by identifying the via points associated with the route keywords by modifying the route keywords with the personalization profile based on the social network preferences . Automatically modifying the route keywords with social network preferences can generate the via points that are better suited to the user based on the preferences of their social network.

It has been discovered that the present invention provides more accurate routing by clustering the via points in the keyword group locales based on the route keywords and proximity within the group distance threshold . Because the via points associated with the keyword group locales are within the group distance threshold of the keyword group center the driver can navigate to an individual one of the via points nearby after navigating to the keyword group locales . The proximity of the via points within the keyword group locales allows the terminal routing to the via points to be performed on a smaller geographical regions reducing the time required to route to one of the via points .

The navigation system describes the module functions or order as an example. The modules can be partitioned differently. For example the receive route keywords module the personalization module and the get via points module can be combined. Each of the modules can operate individually and independently of the other modules.

Furthermore data generated in one module can be used by another module without being directly coupled to each other. For example the calculate route segments module can receive the keyword group locales from the calculate keyword group locales module .

Referring now to therein is shown a flow chart of a method of operation of the navigation system in a further embodiment of the present invention. The method includes receiving an origin and a destination in a block receiving a route keyword for routing between the origin and the destination in a block identifying a via point matching the route keyword in a block calculating a keyword group locale based on the via point within a group distance threshold from a keyword group center in a block and calculating a travel route from the origin to the destination traversing the keyword group locale for displaying on a device in a block .

The resulting method process apparatus device product and or system is straightforward cost effective uncomplicated highly versatile and effective can be implemented by adapting known components for ready efficient and economical manufacturing application and utilization.

Another important aspect of the present invention is that it valuably supports and services the historical trend of reducing costs simplifying systems and increasing performance.

These and other valuable aspects of the present invention consequently further the state of the technology to at least the next level.

While the invention has been described in conjunction with a specific best mode it is to be understood that many alternatives modifications and variations will be apparent to those skilled in the art in light of the aforegoing description. Accordingly it is intended to embrace all such alternatives modifications and variations that fall within the scope of the included claims. All matters hithertofore set forth herein or shown in the accompanying drawings are to be interpreted in an illustrative and non limiting sense.

