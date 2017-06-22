---

title: Apparatus and method for generating virtual sensor in sensor network
abstract: A virtual sensor generation apparatus of a sensor network sets a communication connection to a sensor node at a periphery of a smart device, generates a logical sensor corresponding to a physical sensor that is connected to the sensor node, generates a virtual sensor with the logical sensor, and provides an application service to a user using the virtual sensor.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09225781&OS=09225781&RS=09225781
owner: ELECTRONICS AND TELECOMMUNICATIONS RESEARCH INSTITUTE
number: 09225781
owner_city: Daejeon
owner_country: KR
publication_date: 20130709
---
This application claims priority to and the benefit of Korean Patent Application No. 10 2012 0074734 filed in the Korean Intellectual Property Office on Jul. 9 2012 the entire contents of which are incorporated herein by reference.

The present invention relates to an apparatus and method for generating a virtual sensor in a sensor network. More particularly the present invention relates to an apparatus and method for generating a virtual sensor using a physical sensor and an actuator in a sensor network.

A sensor network system is generally formed with a sensor node communicating with a sensor actuator a personal area network PAN coordinator that manages the sensor node and a gateway for forwarding actual data to a server through communication between the sensor nodes.

An existing sensor actuator application service has been researched and developed for a web based service with priority given to a server a wide area sensor actuator service and a network search and connection service with priority given to a gateway.

Nowadays a new individual service that uses various peripheral sensor actuators through a smart phone smart TV smart household appliances and a smart vehicle that are widely used in a daily life is requested.

The present invention has been made in an effort to provide an apparatus and method for generating a virtual sensor having advantages of being capable of using various peripheral sensors actuators.

An exemplary embodiment of the present invention provides a virtual sensor generation apparatus in a sensor network. The virtual sensor generation apparatus includes a sensor node coordinator a logic sensor manager a virtual sensor manager and a service manager. The sensor node coordinator sets a communication connection to a sensor node at a periphery of a smart device. The logic sensor manager generates at least one logical sensor corresponding to at least one physical sensor of a plurality of physical sensors of the sensor node. The virtual sensor manager generates a virtual sensor using the at least one logical sensor and at least one of previously generated virtual sensors. The service manager generates an application service using an application programming interface API of at least one of the logical sensor and the virtual sensor and that provides the application service to a user.

The virtual sensor generation apparatus may further include an identifier manager. The identifier manager may allocate a layer identifier representing a hierarchical location of the logical sensor and the virtual sensor to the logical sensor and the virtual sensor.

The layer identifier of the at least one logical sensor may be the same as a layer identifier of the at least one physical sensor and the layer identifier of the virtual sensor may be distinguished from the layer identifier of the at least one logical sensor.

The sensor node coordinator may receive a profile of the sensor node and the plurality of physical sensors through the sensor node and the logic sensor manager may set a profile of the at least one physical sensor to the at least one logical sensor.

Another embodiment of the present invention provides a method of generating a virtual sensor in a virtual sensor generation apparatus of a sensor network. The method includes setting a communication connection to a sensor node at a periphery of a smart device generating a plurality of logical sensors corresponding to a plurality of physical sensors respectively that are connected to the found sensor node generating a virtual sensor using at least one logical sensor of the plurality of logical sensors and generating an application service using the generated virtual sensors and providing the application service to the user.

The generating of a plurality of logical sensors may include allocating a layer identifier representing a hierarchical location of the plurality of logical sensors to the plurality of logical sensors and the generating of a virtual sensor may include allocating a layer identifier representing a hierarchical location of the virtual sensor to the virtual sensor.

The generating of a plurality of logical sensors may include setting a profile of the plurality of physical sensors to the plurality of logical sensors.

The providing of the application service may include activating at least one physical sensor that is connected to the at least one logical sensor using an application programming interface API of the at least one logical sensor.

In the following detailed description only certain exemplary embodiments of the present invention have been shown and described simply by way of illustration. As those skilled in the art would realize the described embodiments may be modified in various different ways all without departing from the spirit or scope of the present invention. Accordingly the drawings and description are to be regarded as illustrative in nature and not restrictive. Like reference numerals designate like elements throughout the specification.

In addition in the entire specification and claims unless explicitly described to the contrary the word comprise and variations such as comprises or comprising will be understood to imply the inclusion of stated elements but not the exclusion of any other elements.

Hereinafter an apparatus and method for generating a virtual sensor of a sensor network according to an exemplary embodiment of the present invention will be described in detail with reference to the drawings.

Referring to the sensor network includes a plurality of sensor nodes and PAN coordinators and a gateway and a server .

The gateway and the server are connected to an IP based network and the PAN coordinators and are mounted in the gateway .

The sensor nodes and may include at least one sensor and or actuator . The sensor wirelessly senses environment information of temperature light and acceleration of a periphery and a material for example physical state information and recognition information of the actuator according to a kind. The actuator has a function of operating a predetermined apparatus or a function of turning power of a predetermined apparatus on off.

The sensor nodes and forward data that is sensed by the sensor to the PAN coordinators and respectively and control operation of the actuator . In this case data of the sensor nodes and may be forwarded to the PAN coordinators and respectively through multi hop.

The PAN coordinators and manage the sensor nodes and in network areas and thereof and forward data received from the sensor nodes and in the network areas and thereof to the gateway .

The gateway forwards sensing data received through the PAN coordinators and to the server . For a connection of the server and the sensor nodes and the gateway supports a multimode multichannel communication protocol.

Further the server registers profiles of an entire resource of a sensor network for example the sensor and the actuator the sensor nodes and the PAN coordinators and and the gateway and manages the registered profiles.

The profile may include a resource management application programming interface API and additional information. The resource management API provides a function of initialization access to a resource activation of a resource setting an inactivation cycle and resource monitoring. The additional information may include a local identifier and a layer identifier of a resource a type of a resource a unit of a resource and a type of sensing data.

The sensor nodes and the PAN coordinators and and the gateway store and manage profiles thereof. The sensor nodes and the PAN coordinators and and the gateway store and manage profiles thereof at a non volatile memory. The profiles of the sensor and the actuator are stored and managed at a non volatile memory of the sensor nodes and in which the sensor and the actuator are mounted.

As shown in the server the gateway the PAN coordinator the sensor node the sensor and or the actuator have a local identifier LID .

The LIDs of the server and the gateway are allocated according to an international mobile station identity IMSI or an Internet protocol IP address system which is a number system of a mobile communication network.

The PAN coordinator the sensor node the sensor and or the actuator may be allocated by a user or may be allocated according to a self identification system that is defined in a sensor network such as ZigBee or Bluetooth and a PAN.

Further the gateway the PAN coordinator the sensor node the sensor and or the actuator have a hierarchical resource identifier RSCID representing location information about a resource.

That is the sensor network is formed in a hierarchical structure of order of the gateway the PAN coordinator the sensor node the sensor and or the actuator . Therefore RSCIDs of the gateway the PAN coordinator the sensor node the sensor and or the actuator each represent hierarchical location information thereof.

Specifically because the gateway is an uppermost superordinate layer an RSCID of the gateway may be set to an LID of the gateway . Because the PAN coordinator is located subordinate of the gateway an RSCID of the PAN coordinator may be set by combining an LID of the gateway and an LID of the PAN coordinator . In this way an RSCID of the sensor node may be set by combining an LID of the gateway an LID of the PAN coordinator and an LID of the sensor node . Further an RSCID of the sensor may be set by combining an LID of the gateway an LID of the PAN coordinator an LID of the sensor node and an LID of the sensor and an RSCID of the actuator may be set by combining an LID of the gateway an LID of the PAN coordinator an LID of the sensor node and an LID of the actuator .

For example as shown in when an LID of the gateway is www.gw.com an LID of the PAN coordinator is 1 an LID of the sensor node is 1 and an LID of the sensor is 1 an RSCID of the gateway may be set to www.gw.com an RSCID of the PAN coordinator may be set to www.gw.com 1 an RSCID of the sensor node may be set to www.gw.com 1 1 and an RSCID of the sensor may be set to www.gw.com 1 1 1.

The smart device may be a user terminal of a smart phone a smart TV a smart household appliance and a smart vehicle.

The virtual sensor generation apparatus connects peripheral sensor nodes of the smart device to generate a logic sensor and or actuator corresponding to a sensor and or an actuator of the sensor node and generates a virtual sensor and or a virtual actuator using the logic sensor and or actuator. The smart device provides an application service to the user using the generated virtual sensor and or actuator.

That is the virtual sensor generation apparatus may generate a new virtual sensor and or virtual actuator through cooperation with a physical sensor and or actuator of a peripheral sensor node of the smart device and may provide a new application service to the user using the virtual sensor and or the virtual actuator.

Referring to the virtual sensor generation apparatus includes a sensor node coordinator a logic sensor manager an identifier manager a virtual sensor manager and a service manager .

The sensor node coordinator performs the same function as the PAN coordinators and that are described in .

When the smart device enters for example the network area of the PAN coordinator the sensor node coordinator searches for the sensor node of the network area and sets a communication connection to the found sensor node . For connection to various sensor nodes the sensor node coordinator supports a multimode multichannel communication protocol.

The logic sensor manager generates a logical sensor and or an actuator to correspond to the physical sensor and or the actuator of the sensor node in which a connection is set and sets and gives profiles of the physical sensor and or the actuator to a corresponding logical sensor and actuator respectively. The logic sensor manager connects and sets a logical sensor and or an actuator corresponding to the physical sensor and or the actuator .

The identifier manager allocates an RSCID to the logical sensor and or the logical actuator. Further the identifier manager allocates an RSCID to a virtual sensor and a virtual actuator.

The virtual sensor manager generates a new virtual sensor by combining at least one of logical sensors or random virtual sensors and generates a new virtual actuator by combining at least one of logical actuators or random virtual actuators. Such a generated virtual sensor has a characteristic of a physical actuator that is related to virtual sensor generation and the generated virtual actuator also has a characteristic of a physical actuator that is related to virtual actuator generation.

The service manager generates an application service using an API of at least one of a logical sensor a logical actuator a virtual sensor and a virtual actuator and manages the generated application service.

Referring to a virtual sensor VS is generated by combining at least one of a plurality of logical sensors LS LS. For example as shown in a new virtual sensor VS may be generated by combining logical sensors LS and LS.

The identifier manager allocates an RSCID to a plurality of logical sensors LS LS and the virtual sensor VS.

The identifier manager allocates an RSCID of the logical sensors LS LS with the same value as that of an RSCID of a physical sensor that is connected to each of the logical sensors LS LS. Further the identifier manager may allocate an RSCID of the virtual sensor VS with a different value from that of an RSCID of a physical sensor and logical sensors LS LS and allocate an RSCID of the virtual sensor VS to know a hierarchical location of the virtual sensor VS. Such an RSCID may be used for identifying the virtual sensor VS.

For example when an RSCID of each of logical sensors LS LSn has a value of the RSCID of the virtual sensor VS may be set to www.gw.com 0 1 1. The virtual sensor VS may follow an identifier hierarchical structure that is shown in . 0 representing an immediate subordinate of www.gw.com is an LID of a PAN coordinator and may be set as a value representing the virtual sensor VS. A value of an immediate subordinate of 0 indicates an LID of the sensor node and a lowermost subordinate value indicates an LID of the sensor.

Referring to when the smart device enters for example the network area of the PAN coordinator in order to search for a physical sensor actuator resource the sensor node coordinator of the virtual sensor generation apparatus searches for the physical sensor node at a periphery of the smart device using a multimode and a multichannel and sets a connection to the found sensor node S .

The sensor node coordinator requests the profile of a sensor node and the sensor actuator that is mounted in the sensor node from the sensor node through a SensorProfileRequest message S and receives a profile of the sensor node and the sensor actuator of the sensor node through a SensorProfileResponse message from the sensor node S . In this case the sensor node coordinator may receive a profile of the sensor node and the sensor actuator through a beacon message that the sensor node periodically broadcasts.

The logic sensor manager of the virtual sensor generation apparatus generates a logical sensor actuator corresponding to the physical sensor actuator based on the profile of the sensor node and the sensor actuator S .

The virtual sensor manager generates a virtual sensor actuator using a logical sensor actuator and or a random virtual sensor actuator S .

When the virtual sensor actuator is generated the identifier manager allocates an RSCID to the generated virtual sensor actuator S .

The service manager generates an application service using an API of a logical sensor actuator and or a virtual sensor actuator S and provides the application service to the user S .

For example when a temperature sensor a humidity sensor and an atmospheric pressure sensor exist at the network area the virtual sensor generation apparatus of the smart device generates a logical temperature sensor a logical humidity sensor and a logical atmospheric pressure sensor from the temperature sensor the humidity sensor and the atmospheric pressure sensor respectively corresponding to a physical sensor that is mounted at the physical sensor node and generates a virtual arthritis sensor with a combination of logical sensors a temperature sensor a humidity sensor and an atmospheric pressure sensor .

Thereafter when wanting to acquire an arthritis sensing value in a 10 minute cycle a sensing data collection cycle parameter is forwarded to a virtual arthritis sensor and the virtual arthritis sensor calls each of data collection APIs of a logical sensor and activates a corresponding physical sensor. Thereafter the logical sensors forward a collected result of sensing data of the corresponding physical sensor to the virtual arthritis sensor and the virtual arthritis sensor visualizes the received sensing data to an application service user through a user interface.

Thereby the smart device can freely use a sensor actuator that is installed at a periphery like a sensor actuator that is mounted in the smart device as needed and can thus provide various USN services.

According to an exemplary embodiment of the present invention by generating a virtual sensor using a physical sensor and actuator of a sensor node that is installed at an area in which a smart device visits a sensor and an actuator that are installed at the visit area can be personally used like a sensor and an actuator that are mounted in the smart device. Thereby various ubiquitous sensor network USN services can be generated and activated through a peripheral sensor actuator.

An exemplary embodiment of the present invention may not only be embodied through the above described apparatus and or method but may also be embodied through a program that executes a function corresponding to a configuration of the exemplary embodiment of the present invention or through a recording medium on which the program is recorded and can be easily embodied by a person of ordinary skill in the art from a description of the foregoing exemplary embodiment.

While this invention has been described in connection with what is presently considered to be practical exemplary embodiments it is to be understood that the invention is not limited to the disclosed embodiments but on the contrary is intended to cover various modifications and equivalent arrangements included within the spirit and scope of the appended claims.

