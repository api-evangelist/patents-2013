---

title: Device for detection and prevention of an attack on a vehicle
abstract: A new device for detection and prevention of an attack on a vehicle via its communication channels, having: an input-unit configured to collect real-time and/or offline data from various sources such as sensors, network based services, navigation applications, the vehicles electronic control units, the vehicle's bus-networks, the vehicle's subsystems, and on board diagnostics; a database, for storing the data; a detection-unit in communication with the input-unit; and an action-unit, in communication with the detection unit, configured for sending an alert via the communication channels and/or prevent the attack, by breaking or changing the attacked communication channels. The detection-unit is configured to simultaneously monitor the content, the meta-data and the physical-data of the data and detect the attack.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09560071&OS=09560071&RS=09560071
owner: Tower-Sec Ltd.
number: 09560071
owner_city: Kfar-Saba
owner_country: IL
publication_date: 20131017
---
This invention generally relates to a device that enables detection of an attack such as a cyber attack or communication attack on vehicles

Modern automobiles are no longer mere mechanical devices they are pervasively monitored and controlled by dozens of digital computers coordinated via internal vehicular networks. While this transformation has driven major advancements in efficiency and safety it has also introduced a range of new potential risks.

Because many of today s cars contain cellular connections and Bluetooth wireless technology it is possible for a hacker working from a remote location to take control of various features like the car locks and brakes as well as to track the vehicle s location eavesdrop on its cabin and steal vehicle data. Modern automobiles are pervasively computerized and hence potentially vulnerable to such an attack. However while previous research has shown that the internal networks within some modern cars are insecure the associated threat model requiring prior physical access has justifiably been viewed as unrealistic. Exploitation is feasible via a broad range of attack vectors remote or physical connections including mechanic diagnostic tools and CD players Bluetooth cellular and radio further wireless communications channels allow long and short distance vehicle control and communication location tracking in cabin audio ex filtration and theft.

Chutorash U.S. Pat. No. 6 314 351 disclosed a vehicle computer system which provides a firewall between an auto PC and its application software and the vehicle bus and vehicle components. The firewall prevents unauthorized access by software in the auto PC to the vehicle bus and vehicle components. Preferably the firewall utilizes encryption technology within the handshake between the auto PC software and firewall.

Dierickx U.S. Pat. No. 8 402 268 disclosed a system for providing network security on a vehicle information system and methods for manufacturing and using same. The security system comprises an all in one security system that facilitates security system functions for the vehicle information system. Exemplary security system functions include secure storage of keys used to encrypt and or decrypt system data security related application programming interfaces a security log file and or private data. The security system likewise can utilize antivirus software anti spyware software an application firewall and or a network firewall. As desired the security system can include an intrusion prevention system and or an intrusion detection system. If the information system includes a wireless distribution system the security system can include an intrusion prevention and or detection system that is suitable for use with wireless network systems. Thereby the security system advantageously can provide a defense in depth approach by adding multiple layers of security to the information system.

Melman U.S. Pat. No. 7 917 261 disclosed a method of controlling a control system for a vehicle comprising providing at least one data communications bus providing at least one firewall in communication with at least one data communications bus wherein the at least one firewall creates at least two data communications bus from the at least one data communications bus providing at least one vehicle device in communication with at least one of at least two data communications bus providing at least one vehicle device in communication with at least one firewall and providing at least one firewalled controller in communication with at least one firewall wherein the firewalled controller transmits a directive to the firewall and the firewall transmits the directive through the at least two data communications bus which controls the at least one vehicle device.

However none of the above prior art disclosures utilizes the unique characteristics of the vehicle s functioning logic and potential attack vectors.

It is one object of the present invention to disclose a device for detection and prevention of at least one attack on a vehicle via its one or more communication channels said device comprising 

It is another object of the present invention to disclose the device as defined above wherein said detection unit configured to detect said attack based on at least one characteristic selected from a group consisting of 

It is another object of the present invention to disclose the device as defined above wherein said database further comprises parameters of at least one known attack previously detected as said attack.

It is another object of the present invention to disclose the device as defined above wherein said action unit and or said detection unit further configured to extract said parameters of said attack and update said database.

It is another object of the present invention to disclose the device as defined above wherein said device further comprising an identification unit configured to identify said parameters of said known attack and update said action unit.

It is another object of the present invention to disclose the device as defined above wherein said device further comprising a remote server configured to communicate with said database for delivering and or receiving at least one additional said parameters of said known attack.

It is another object of the present invention to disclose the device as defined above wherein said remote server configured to collect said data from at least one additional vehicle monitor the content the meta data and the physical data of said data detect said attack and update said attack to database.

It is another object of the present invention to disclose the device as defined above wherein said parameters are selected from a group consisting of 

It is another object of the present invention to disclose the device as defined above wherein said detection unit comprising a machine learning engine configured to learn the features and behaviour of said data s content meta data and physical data and recognize any unfamiliar behaviour.

It is another object of the present invention to disclose the device as defined above wherein said device further comprising a display unit configured to notify and alert a user of said attack.

It is another object of the present invention to disclose the device as defined above wherein said device is in communication with a remote display unit configured to notify and alert a user of said attack.

It is another object of the present invention to disclose the device as defined above wherein said one or more said sensors are selected from a group consisting of 

It is another object of the present invention to disclose the device as defined above wherein said one or more said subsystems are selected from a group consisting of 

It is another object of the present invention to disclose the device as defined above wherein said ECU is selected from a group consisting of 

It is another object of the present invention to disclose the device as defined above wherein said action unit configured to initiate further collection of said data from said at least one source.

It is another object of the present invention to disclose the device as defined above wherein said device further comprises a commercialized anti virus malware application firewall or other malicious code database Which can be provided by a third party.

It is another object of the present invention to disclose the device as defined above wherein said vehicle is driven by a human by an at least partially autonomous driving system or by a remote control system or by full autonomous driving system.

It is another object of the present invention to disclose the device as defined above wherein said vehicle is a robotic platform.

It is another object of the present invention to disclose the device as defined above wherein said vehicle travels via land water or air.

It is another object of the present invention to disclose the device as defined above wherein said device is at least partially embedded within one of said vehicle s hardware cards software units and or within said remote server.

It is another object of the present invention to disclose the device as defined above wherein said device further comprises an assessment engine configured to evaluate risk level of said attack to said vehicle and its passengers and prioritize said attack.

It is another object of the present invention to disclose the device as defined above wherein said one or more network based services are selected from a group consisting of web physical cable Wi Fi cellular blue tooth RF GPS vehicle to vehicle communication vehicle to passenger infrastructure environment to vehicle infrastructure.

It is another object of the present invention to disclose the device as defined above wherein said one or more navigation applications or devices are selected from a group consisting of satellite navigator cellular navigator and inertial dedicated navigator.

It is another object of the present invention to disclose the device as defined above wherein said one or more navigation applications or devices are said vehicle s own subsystem navigator.

It is another object of the present invention to disclose a method for detecting and preventing at least one attack on a vehicle via its one or more communication channels said method comprising steps of 

It is another object of the present invention to disclose the method as defined above wherein said detecting of said attack based on at least one characteristic selected from a group consisting of 

It is another object of the present invention to disclose the method as defined above wherein said step of storing further comprises storing of parameters of at least one known attack previously detected as said attack.

It is another object of the present invention to disclose the method as defined above further comprising step of extracting said parameters.

It is another object of the present invention to disclose the method as defined above further comprising step of identifying said parameters of said known attack and updating for said step of alerting.

It is another object of the present invention to disclose the method as defined above further comprising step of communicating said database with a remote server delivering and or receiving at least one additional said parameters of said known attack.

It is another object of the present invention to disclose the method as defined above wherein said remote server configured for collecting said data from at least one additional vehicle monitoring the content the meta data and the physical data of said data detecting said attack and updating said attack to database.

It is another object of the present invention to disclose the method as defined above wherein said parameters are selected from a group consisting of 

It is another object of the present invention to disclose the method as defined above wherein said step of detecting further includes learning the features and behaviour of said data s content meta data and physical data and recognizing any unfamiliar behaviour.

It is another object of the present invention to disclose the method as defined above further comprising step of displaying said alert for notifying and alerting a user of said attack.

It is another object of the present invention to disclose the method as defined above wherein said one or more said sensors are selected from a group consisting of 

It is another object of the present invention to disclose the method as defined above wherein said one or more said subsystems are selected from a group consisting of 

It is another object of the present invention to disclose the method as defined above wherein said ECU is selected from a group consisting of 

It is another object of the present invention to disclose the method as defined above further comprising step of evaluating the risk level of said attack to said vehicle and its passengers and prioritizing said attack.

It is still an object of the present invention to disclose the method as defined above further comprising step of selecting said one or more network based from a group consisting of web physical cable Wi Fi cellular blue tooth RF GPS vehicle to vehicle communication vehicle to passenger infrastructure environment to vehicle infrastructure.

It is lastly an object of the present invention to disclose the method as defined above further comprising step of selecting said one or more navigation applications or devices from a group consisting of satellite navigator cellular navigator north finding systems NFS or inter vehicle orientation system and inertial dedicated navigator.

The following description is provided alongside all chapters of the present invention so as to enable any person skilled in the art to make use of the invention and sets forth the best modes contemplated by the inventor of carrying out this invention. Various modifications however are adapted to remain apparent to those skilled in the art since the generic principles of the present invention have been defined specifically to provide a device and method for detecting and preventing vehicle s attack.

The potential damage of a cyber attack on vehicles functional units can be unprecedented for example a remote attack on air bag system can potentially trigger activation of the airbag during a regular driving or manipulating tire pressure management system wireless transmission in order to spoof actual pressure reporting. The traditional information security approaches such as firewall antivirus and network IDS may not be sufficient to answer this critical need since attack vectors are different since while the vehicle has unique inter unit functional logic such as direct access through vehicle s different sensors or through remote control service or through other vehicles or infrastructure units V2V V2I .

This present invention present a new device and method for dealing with attack threats such as cyber attack or communication attack. The present invention is suited for protecting such attacks by utilizing the unique characteristics of the vehicle s functioning logic the potential attack vectors the communication between the vehicle s systems and their combination.

The term Electronic Control Units ECU used herein refers to any embedded system that controls one or more of the electrical system or subsystems in a motor vehicle. Types of ECU include electronic engine control module ECM powertrain control module PCM transmission control module TCM brake control module BCM or EBCM central control module CCM central timing module CTM general electronic module GEM body control module BCM suspension control module SCM control unit or control module. Taken together these systems are sometimes referred to as the car s computer. Technically there is no single computer but multiple ones. Sometimes one assembly incorporates several of the individual control modules PCM is often both engine and transmission . Some modern motor vehicles have up to 80 ECUs. Embedded software in ECUs continues to increase in line count complexity and sophistication. Managing the increasing complexity and number of ECUs in a vehicle has become a key challenge for original equipment manufacturers OEMs .

The term Meta data used herein refers to data about data . The term is used in two fundamentally different concepts structural meta data and descriptive meta data. Structural meta data is about the design and specification of the data s structure or in other words data about the containers of data. Descriptive meta data is about individual instances of application data the data content. In this case a useful description would be data about data content or content about content thus meta content.

The term physical data used herein refers to the electrical and physical specifications of the data connection. The physical data defines the characteristics between a device and a physical transmission medium e.g. a copper or fiber optical cable . This includes the layout of pins voltages line impedance cable specifications signal timing hubs repeaters network adapters Intensity frequency gradient changing amplitude modulation method and more.

The term irrational used herein refers to fallacious illegitimate inconsequent inconsequential invalid illogical non rational unreasonable unreasoning unsound unexpected or weak data s content meta data physical data or the resulted action based on the vehicle s present status action or condition or when comparing to data collected from the different data sources.

The term vehicle used herein refers to a mobile machine that transports passengers or cargo such as bicycle car truck bus motorcycles trains ships boats aircraft watercraft aircraft and spacecraft. The vehicle can be driven by a human by an at least partially autonomous driving system or by a remote control system. The vehicle may also be a robotic platform. The vehicle may travel via land water or air.

The term communication channels used herein refer to a physical transmission medium such as a wire or to a logical connection over a multiplexed medium such as a radio channel. Channels are used to convey information signals for example a digital bit stream from one or several senders or transmitters to one or several receivers. A channel has a certain capacity for transmitting information often measured by its bandwidth in Hz or its data rate in bits per second. Communicating data from one location to another requires some form of pathway or medium. These pathways called communication channels use two types of media cable twisted pair wire cable and fiber optic cable and broadcast microwave satellite radio and infrared . Cable or wire line media use physical wires of cables to transmit data and information. Twisted pair wire and coaxial cables are made of copper and fiber optic cable is made of glass.

The term network based services used herein refers to web physical cable Wi Fi mobile blue tooth RF and GPS.

The present invention provides a new device for detection and prevention of at least one attack on a vehicle via its one or more communication channels the device comprising 

The detection unit configured for monitoring and detecting the attack based on at least one characteristic selected from a group consisting of 

The present invention provides a new method for detecting and preventing at least one attack on a vehicle via its one or more communication channels the method comprising steps of 

According to an embodiment of the present invention the database further comprises parameters of at least one known attack previously detected. The parameters can be selected from irregular the data s content irregular source of the data irregular destination for the data irrational the data s content when compared with data received by at least one other the source irrational action of at least one of the vehicle s subsystems when compared with data received by at least one other subsystem irrational action between at least two of the subsystems irrational action of at least one of the vehicle s subsystems when compared with the data received by at least one of the sensors irrational meta data irrational meta content jam or blockage of the communication channels and or the network based services sudden change in the signal features of the network based services and or the sensors the vehicle location the vehicle brand the sensors the communication channels the navigation application the navigation device and communication interfaces.

According to another embodiment the action unit and or the detection unit are configured to extract these parameters of the attack and update the database.

According to an embodiment of the present invention the device further comprises an identification unit configured to identify the above mentioned known parameters of the known attack and update the action unit.

According to another embodiment the action unit may initiate further collection of data from at least one the sources.

According to an embodiment of the present invention the device further comprises a remote server configured to communicate with the database for delivering and or receiving additional parameters of known attacks detected by other similar devices.

According to another embodiment the remote server is configured to collect the data from at least one additional vehicle to monitor the content the meta data and the physical data of the data to detect the attack and to update the database of an attack.

According to an embodiment of the present invention the detection unit comprises a machine learning engine configured to learn the features and behaviour of the data s content meta data and physical data and recognize any unfamiliar behaviour.

According to an embodiment of the present invention the device further comprises a display unit configured to notify and alert a user of the attack. The device can also be in communication with a remote display unit configured to notify and alert a user of an attack.

According to another embodiment of the present invention the device may utilize a commercialized anti virus malware application firewall or other malicious code database that are offered in the market.

According to another embodiment the device is at least partially embedded within one of the vehicle s hardware cards software units and or within the remote server.

According to another embodiment the device further comprises an assessment engine for evaluating risk level of the attack to the vehicle and its passengers and for prioritizing the detected attack.

The sensors as mentioned above can be selected from distance sensor for avoiding collision velocity and acceleration sensors temperature sensor satellite transmission sensor cellular transmission sensors video image air fuel ratio meter blind spot monitor crankshaft position sensor curb feeler used to warn driver of curbs defect detector used on railroads to detect axle and signal problems in passing trains engine coolant temperature sensor or ECT sensor used to measure the engine temperature hall effect sensor used to time the speed of wheels and shafts Manifold Absolute Pressure MAP sensor used in regulating fuel metering mass flow sensor or mass airflow MAF sensor used to tell the ECU the mass of air entering the engine oxygen sensor used to monitor the amount of oxygen in the exhaust parking sensors used to alert the driver of unseen obstacles during parking maneuvers radar gun used to detect the speed of other objects speedometer used measure the instantaneous speed of a land vehicle speed sensor used to detect the speed of an object throttle position sensor used to monitor the position of the throttle in an internal combustion engine tire pressure monitoring sensor used to monitor the air pressure inside the tires torque sensor or torque transducer or torque meter measures torque twisting force on a rotating system transmission fluid temperature sensor used to measure the temperature of the transmission fluid turbine speed sensor TSS or input speed sensor ISS used to measure the rotational speed of the input shaft or torque converter variable reluctance sensor used to measure position and speed of moving metal components vehicle speed sensor VSS used to measure the speed of the vehicle water sensor or water in fuel sensor used to indicate the presence of water in fuel wheel speed sensor used for reading the speed of a vehicle s wheel rotation and any combination thereof.

The subsystems as mentioned above can be selected from tire pressure monitoring stability control cruise control airbag control Powertrain Control Module PCM Transmission Control Module TCM Brake Control Module BCM Central Control Module CCM Central Timing Module CTM General Electronic Module GEM Body Control Module BCM Suspension Control Module SCM Convenience Control Unit CCU Convenience Control Unit CCU Convenience Control Unit CCU Engine Control Unit ECU Electric Power Steering Control Unit PSCU Human Machine Interface HMI seat control unit speed control unit Telephone Control Unit TCU Transmission Control Unit TCU Brake Control Module ABS or ESC crash sensors airbags seatbelts Tire Pressure Monitoring System TPMS Electronic Stability Control system ESC Traction Control System TCS Anti lock braking system ABS Electronic Brake Assistance system EBA electronic brake force distribution electronic brake force distribution EBD system Emergency shutdown Driven notifications and alerts Pedestrian object recognition Lane keeping assistance Collation avoidance Adaptive headlamps control Reverse backup sensors Adaptive cruise control Active Cruise Control ACC Traction control systems Electronic Stability Control Automated parking system Multimedia Active noise cancelation ANC Radio Radio Data System RDS Driver information functions AM FM or satellite radio DC DVD player Payment systems In vehicle Wi Fi router Internal lights Climate control Chairs adjustment Electric windows Mirror adjustment Central locking Battery management Charging management Vehicle grid system ACC Remote control keys Theft deterrent systems Immobilizer system other security systems Digital cameras night vision Lasers Radar RF Sensors and robotic gear shaft.

The ECU as mentioned above can be selected from electronic engine control module ECM powertrain control module PCM transmission control module TCM brake control module BCM or EBCM central control module CCM central timing module CTM general electronic module GEM body control module BCM suspension control module SCM airbag control unit ACU body control module BCU controls door locks electric windows and courtesy lights convenience control unit CCU door control unit DCU engine control unit Electric Power Steering Control Unit PSCU integrated into the electric power steering EPS power pack human machine interface HMI Powertrain control module PCM seat control unit speed control unit SCU telephone control unit TCU telematic control unit TCU transmission control unit TCU Brake Control Module BCM and any combination thereof.

The network based services as mentioned above may be selected from a group consisting of web physical cable Wi Fi cellular blue tooth RF GPS vehicle to vehicle communication vehicle to passenger infrastructure environment traffic to vehicle infrastructure.

The navigation applications or devices as mentioned above may be selected from a group consisting of satellite navigator cellular navigator and inertial gyro dedicated navigator north finding system NFS relational location system based on RF communication with other vehicles land signs and beacon. The navigation applications or devices may also be the vehicle s own subsystem navigator.

Reference is now made to disclosing a schematic diagram of the device and its basic components and including 

Reference is now made to disclosing an example of implementation to the vehicle s cyber attack detection device. In this implementation the detection unit includes the database the assessment engine analysis engine the machine learning engine and where the irrational or irregular message is analyzed separately from the cross detection unit. This example discloses communication between the detection unit and the remote server the input unit interface unit the network based services and where the detection unit further outputs potential attack alerts and triggers the action unit.

Examples for functioning logic and potential attack vectors which are the characteristics detected by the detection unit 

