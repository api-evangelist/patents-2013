---

title: Access control system for override elevator control and method therefor
abstract: A system and method for an access control system for an elevator system that overrides landing matrices that define the access to the floors in the elevator system. The system overrides the landing matrices of the access control system in response to conditions defined by security system operators, such as emergency situations, and sends the landing matrices to elevator controllers for controlling the access to the floors. In examples, the system supports configuration of vendor-neutral landing matrix objects sent to the access control system over a security network for creating new landing matrices, and overriding the contents of the existing landing matrices.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09463954&OS=09463954&RS=09463954
owner: Sensormatic Electronics, LLC
number: 09463954
owner_city: Boca Raton
owner_country: US
publication_date: 20130807
---
This application claims the benefit under 35 U.S.C. 119 e of U.S. Provisional Application No. 61 810 326 filed on Apr. 10 2013 which is incorporated herein by reference in its entirety.

Elevator systems in buildings typically utilize an elevator controller to control one or more elevators. Typically elevator systems are integrated with security control systems that provide landing matrices to the elevator controllers for controlling the access to the floors. Elevator systems with integrated access control systems are also referred to as elevator integrations and communicate over a security network with the security control system.

The landing matrices define access to the floors on a time per floor and or per user basis and are typically stored in an access control system ACS of the security control system. Security personnel create and configure the landing matrices using management applications on workstations. Typically the elevator controllers accept one landing matrix at a time for controlling the access to the floors. Based on security objectives security personnel select a landing matrix on the ACS also known as the active landing matrix and send the active landing matrix to the elevator controller to control the access to the floors.

Security personnel create and select landing matrices for controlling access to the floors based with daily working conditions in the buildings. Default landing matrices typically provide floor access to all users with the exception of secured floors. User specific matrices or cardholder matrices can provide the ability for individual users or groups of users to access one or more otherwise secured floors.

For the cardholder matrices users typically provide their credentials over the security network via card readers. The user credentials are included within access cards created by security personnel. The card readers send the user credentials to the access control system to authenticate the users. Upon authenticating the users the access control system can select associated cardholder matrices that grant access to the floors.

Current elevator integrations have difficulty handling and implementing exceptions to normal behavior such as the need to change access to the floors in response to emergency conditions. Existing systems typically require that security personnel manually configure an active landing matrix on the ACS that provides access to all floors and send it to the elevator controller for an indefinite time period. To clear the emergency condition security personnel manually revert the active landing matrix to the landing matrix used prior to the emergency condition.

The present invention provides the ability to define access to one or more floors on a per exception basis and apply the exception as an override to the stored landing matrices on the ACS. This includes overriding the active landing matrix. The override can be applied manually by an operator for an indefinite or a fixed time and can be scheduled in advance via a scheduler on the ACS.

The ACS sends the overridden contents of the active landing matrix to the elevator controller to control the access to the floors for the duration of the override event. Upon the completion of a fixed time or scheduled override the ACS automatically reverts to using the landing matrix utilized prior to the override as the active landing matrix and sends the new active landing matrix to the elevator controller. In addition the present invention also provides the ability to define personnel exceptions to the overrides such as emergency responders or security personnel.

Moreover current manufacturers of elevator systems implement proprietary mechanisms for configuring and defining the access to the floors. The present invention also provides a vendor neutral format for defining and overriding the access to the floors via landing matrix objects. Using the landing matrix objects elevator vendors can also implement the access override capabilities of the present invention by integrating the content of the landing matrix objects with proprietary application programming interfaces API .

In embodiments of the access control system an ACS landing matrix API or framework is used that supports vendor neutral requests for overriding the contents of the landing matrices on the ACS and submits landing matrix to override the currently active landing matrix for the elevator controller in response to the requests.

The embodiments of the invention utilize a landing matrix object that operators configure using management applications. The landing matrix object supports information associated with standard landing matrix configuration as well as for specifying override behavior.

This includes the ability to secure or unsecure a given elevator floor indefinitely or for a fixed period of time to provide temporary floor access through a manual action for visitors not having routine access to floors.

The landing matrix object also includes an override exemption list that grants access to individuals whose user credentials are included in the override exemption list. This allows individuals such as emergency responders to gain access to otherwise secure floors during an override event in response to emergency conditions.

In general according to one aspect the invention features a security control system for an elevator system which comprises an elevator controller that controls access to floors served by one or more elevators and an access control system that stores one or more landing matrices that define the access to the floors the access control system providing the landing matrices to the elevator controller. The access control system includes a landing matrix API that accepts landing matrix objects in messages received over a security network the landing matrix API overriding the landing matrices with the landing matrix objects. The security control system also comprises a security network control system that enables configuration of the landing matrix objects and sends the landing matrix objects in the messages to the access control system over the security network.

The system further comprises one or more card readers that receive user credentials from users and send the user credentials in the messages over the security network to the access control system. The card readers are included within car operation panels and or destination operation panels.

The landing matrix API creates new landing matrices from the landing matrix objects. In response to the messages received over the security network the access control system preferably selects one of the landing matrices as an active landing matrix and sends the active landing matrix to the elevator controller to control the access to the floors.

The elevator controller executes an active landing matrix sent by the access control system to control the access to the floors and executes the landing matrices sent by the access control system to control the access to the floors.

The landing matrices include a default offline matrix utilized by the elevator controller when the access control system is unable to communicate with the elevator controller. The landing matrices also include one or more user specific matrices associated with cardholders which the access control system sends to the elevator controller in response to receiving user credentials associated with users when the access control system authorizes the user credentials for the users.

The landing matrices further include a default online matrix which the access control system sends to the elevator controller when the access control system communicates with the elevator controller and no user credentials are received in the messages over the security network.

In embodiments the access control system further comprises a scheduler for providing the landing matrices to the elevator controller according to a schedule.

The security control system includes a configuration application for configuring the landing matrix objects. Preferably the security control system further comprises a security guard workstation that includes a security management application for enabling configuration of the landing matrix objects and for providing the landing matrix objects to the access control system in the messages sent over the security network.

The security guard workstation typically includes a display device for displaying the security management application and a keyboard and a pointing device for configuring the landing matrix objects in the security management application.

Preferably the landing matrix objects provide a vendor neutral format for overriding the landing matrices sent to the elevator controller. The landing matrix objects include bitmasks for defining the access to the floors associated with cab doors of the elevators a user credentials list that includes user credentials for defining the access to the floors associated with users a landing matrix type field that defines operations for the landing matrix API to perform from contents of the landing matrix objects and a time limit field that specifies a duration associated with the operations of the landing matrix type field.

In general according to another aspect the invention features a security control method for an elevator system. The security control method comprises an access control system providing a landing matrix API that accepts landing matrix objects in messages received over a security network in the access control system storing one or more landing matrices defining access to floors by one or more elevators the access control system receiving the landing matrix objects from a security network control system and overriding the stored landing matrices with the landing matrix objects and providing the landing matrices to an elevator controller of the elevator.

The security control method further comprises receiving user credentials from users via card readers and sending the user credentials in the messages over the security network to the access control system.

In one implementation the security control method further comprises the landing matrix API creating new landing matrices from the landing matrix objects.

Preferably in response to receiving the messages over the security network the access control system selects one of the landing matrices as an active landing matrix and sends the active landing matrix to the elevator controller to control the access to the floors.

The above and other features of the invention including various novel details of construction and combinations of parts and other advantages will now be more particularly described with reference to the accompanying drawings and pointed out in the claims. It will be understood that the particular method and device embodying the invention are shown by way of illustration and not as a limitation of the invention. The principles and features of this invention may be employed in various and numerous embodiments without departing from the scope of the invention.

The ACS includes one or more landing matrices that define the access to the floors for the elevator controller . When the communications between the ACS and the elevator controller are active the ACS sends a landing matrix to the elevator controller for controlling access to the floors served by the elevators . The elevator controller includes a default offline landing matrix in the event that the communications fail between the ACS and the elevator controller .

The landing matrices also include a default online landing matrix that specifies access to floors independent of user credentials and one or more user specific landing matrices that include user credential information from users. The ACS creates the user specific matrices in response to receiving the user credentials over the security network from card readers .

While the ACS stores one or more landing matrices only one landing matrix at any given time is sent by the ACS to the elevator controller for controlling the access to the floors. This is also known as an active landing matrix . The active landing matrix is the matrix sent by the ACS to the elevator controller for granting the access to the floors served by the elevators when the connection between the elevator controller and the access control system is active.

The ACS also includes scheduled landing matrices that the ACS schedules with its scheduler . A scheduled landing matrix becomes the active landing matrix during the scheduled time of the scheduler . Once the scheduler completes the ACS reverts to using the active landing matrix utilized prior to the scheduling event which is typically the default online landing matrix .

The ACS additionally includes an ACS landing matrix API that accepts ACS landing matrix objects included within messages over the security network . In response to receiving the ACS landing matrix objects the ACS landing matrix API reads the ACS landing matrix objects creates new landing matrices from the ACS landing matrix objects and performs operations upon the stored landing matrices using the ACS landing matrix objects .

Users can request access to the elevator system via access card readers included within Destination Operation Panels DOP and Car Operation Panels COP . COPs are located within an elevator car of the elevator or mounted outside elevator doors of the elevator . DOPs are typically located in natural entrance areas within close proximity of an elevator lobby. Users present access cards to the card readers that include user credentials and the card readers send the user credentials in messages over the security network to the ACS .

Personnel such as security guards configure access to the elevator system via a security guard workstation and a security network control system . The security guard workstation and the security network control system connect to the security network . The security guard workstation has a display device a pointing device such as a mouse or touchscreen and a keyboard . The security guard workstation includes an ACS security management application .

In typical elevator systems one vendor manufactures the majority of the components that communicate over the security network such as the elevator controller the ACS the COPs and DOPs . In addition vendors provide full management and configuration for these components via vendor specific security ACS security management applications on the security guard workstation .

In contrast the security network control system is typically a third party system the capabilities of which are limited to configuration and management of the ACS and its landing matrices via the ACS configuration application .

A security guard uses the ACS security management application on the security guard workstation for configuration and management of the ACS and its landing matrices. The ACS security management application typically supports all functions of the ACS . Security personnel also configure information for the landing matrices of the ACS using the ACS configuration application on the security network control systems.

Security personnel configure information for creating and modifying the landing matrices in response to security objectives and in response to changes in operational conditions. Operators use the ACS configuration application and the ACS security management application to create ACS landing matrix objects . The ACS landing matrix objects are sent over the security network to the ACS to create new landing matrices and to apply the content of the landing matrix objects to the stored landing matrices of the ACS .

The ACS landing matrix objects include fields that specify access to floors within a building. The ACS landing matrix objects support one or two elevator doors per elevator car. The fields of the ACS landing matrix objects include a context specific user credentials list a front cab door bitmask a rear cab door bitmask a landing matrix type field and a time limit field .

The user credentials list is context specific depending on the value of the landing matrix type field . The user credentials list includes a list of user credentials associated with users.

The front cab door bitmask and rear cab door bitmask define access to elevator floors for the front cab door and rear cab door respectively of an elevator . The front cab door bitmask and rear cab door bitmask define access for as many as 128 floors in one implementation as shown in .

In one example positions within the front cab door bitmask and rear cab door bitmask are associated with floor numbers. A zero 0 value for the position indicates secure or denial of access to that floor and a one 1 value for the position indicates unsecure or granting of access to that floor.

The time limit field is context specific depending on the value of the landing matrix type field . In one example the time limit field is supported when the landing matrix type is set to override . The value of the time limit field specifies the duration for the associated override . In one embodiment the time limit field value is defined in seconds with a value of 0 associated with an indefinite time period.

The landing matrix type includes the following types default offline default online user specific and override . The ACS uses the ACS Landing matrix API to read the contents of ACS Landing matrix objects received in messages over the security network .

The security guard workstation and the security network control system send the ACS landing matrix objects in response to requests for configuration changes to the landing matrices by operators. In response to receiving the ACS Landing matrix objects the ACS Landing matrix API instructs the ACS to configure the landing matrices on the ACS and or designate one of the landing matrices as the active landing matrix and send the active landing matrix to the elevator controller for controlling the access to the floors.

Operators specify the default offline type for the landing matrix type for configuring parameters associated with the default offline landing matrix . The user credentials list and time limit fields are not supported for the default offline type.

In response to receiving an ACS landing matrix object with the default offline type specified the ACS landing matrix API instructs the ACS to create a new default offline landing matrix . However the ACS does not assign the newly created default offline landing matrix as the active landing matrix . Rather the ACS sends the newly created default offline landing matrix to the elevator controller which the elevator controller uses to provide access to the floors when the ACS is no longer communicating with the elevator controller .

The operator defines the values in the front cab door bitmask and rear cab door bitmask for controlling the access to the floors independent of user credentials. Typical examples include secure access to all floors unsecure access to all floors or a custom matrix of secure and unsecure access to floors.

Operators specify the default online type for the landing matrix type for configuring parameters associated with the default online landing matrix . The ACS utilizes the default online landing matrix as the active landing matrix when the connection between the ACS and the elevator control is active and the ACS is not receiving messages over the security network that include user credentials associated with users requesting access from card readers .

As with the default offline type the default online type utilizes the front cab door bitmask and rear cab door bitmask of the ACS landing matrix object for controlling floor access independent of user credentials. The user credentials list and time limit fields are not supported.

In response to receiving an ACS landing matrix object with the default online type specified the ACS landing matrix API instructs the ACS to create a new default online landing matrix from the ACS landing matrix object . Then the ACS assigns the newly created default online landing matrix as the active landing matrix and sends the active landing matrix to the elevator controller to control the access to the floors.

Operators specify the user specific type for the landing matrix type for configuring parameters associated with the user specific online landing matrix also known as a cardholder matrix. The user credentials list is supported for the user specific type value but the time limit field is not supported. The user credentials list includes the user credentials of authorized users for the floors.

The user specific type also provides the ability to create a new user specific online landing matrix that combines the user credentials in the user credentials list with the values for the front cab door bitmask and rear cab door bitmask .

In response to receiving an ACS landing matrix object with the user specific type specified the ACS landing matrix API instructs the ACS to create a new user specific online landing matrix from the ACS landing matrix object .

When users swipe their access cards at the DOPs and COPs the ACS determines if the user credential matches a user credential in the newly created user specific online landing matrix . If a match occurs in response the ACS sets the newly created user specific online landing matrix as the active landing matrix and sends the active landing matrix to the elevator controller to control the access to the floors.

Operators specify the override value for the landing matrix type for configuring parameters associated with overriding all landing matrices on the ACS . The user credentials list and the time limit field are supported for the override type .

In response to receiving an ACS landing matrix object with the override value specified for the landing matrix type the ACS Landing matrix API applies the values for the front cab door bitmask and rear cab door bitmask of the received ACS landing matrix object in one example in a logical exclusive or XOR fashion to all landing matrices on the ACS including the active landing matrix .

In other examples the operator can specify different Boolean operations or logical operations for applying the front cab door bitmask and rear cab door bitmask of the received ACS landing matrix object to the landing matrices on the ACS . Examples of Boolean operations include logical AND OR and exclusive OR XOR operations.

In another example for the override type the user credentials list specifies the user credentials of users such as emergency personnel for which the ACS grants access for all floors independent of the values for the front cab door bitmask and rear cab door bitmask in the ACS landing matrix object .

The time limit field defines the duration for override events associated with the override type . The time limit field supports values associated with fixed time periods in seconds and values associated with special events such as a value that indicates an unlimited time period for executing the override event. The operator must administratively configure the ACS with a landing matrix type other than the override type to end the override event.

In the example the graphical user interface includes checkboxes associated with each floor for the front and rear cab doors. Deselection of a checkbox indicates secured access to the associated floor for the cab door and selection of a checkbox indicates unsecured access to the associated floor for the cab door.

In response to the selection or deselection of the checkboxes the graphical user interface populates the front cab door bitmask and rear cab door bitmask of an ACS landing matrix object .

In one implementation the graphical user interface is included as part of a configuration wizard that creates a new instance of an ACS landing matrix object populates the fields of the ACS landing matrix object in response to operator security objectives and sends the completed ACS landing matrix object to the ACS .

In step on the security guard workstation the operator opens the ACS security management application to connect to the Access Control System ACS . In step the operator specifies the default online landing matrix as the active online landing matrix .

According to step the operator creates a new instance of an ACS landing matrix object specifying the override value for the landing matrix type . The operator also specifies values for the front cab door bitmask and rear cab door bitmask that specify unsecure access to floors and and specifies a value in the time limit field associated with a one hour time limit.

In step the operator sends the completed ACS landing matrix object to the ACS and exits the ACS security management application . The ACS landing matrix API receives the ACS landing matrix object and applies the information in the front cab door bitmask and rear cab door bitmask in an exclusive or operation XOR in one example to all landing matrices on the ACS for the specified one hour duration in the time limit field according to step .

As a result of step all landing matrices on the ACS are overridden with the contents of the ACS landing matrix object including the active matrix object . In step the ACS sends the overridden active landing matrix to the elevator controller . When the specified time limit expires the ACS reverts to using the prior active landing matrix which is the default online landing matrix and sends it to the elevator controller in step .

In step using the ACS Security Management Application the operator defines and schedules a daytime user specific landing matrix as the active landing matrix using the scheduler . The operator indicates for the scheduler to apply the daytime user specific landing matrix for the duration of normal business hours. In step the ACS sets the daytime user specific landing matrix as the active landing matrix .

In step in response to an emergency condition the operator uses the ACS Security Management Application to configure an ACS landing matrix object to override the landing matrices on the ACS . In the example the operator populates the ACS landing matrix object  with an override value for the landing matrix type and the values for the front cab door bitmask and rear cab door bitmask specify unsecure access to floors and secured access to the remaining floors.

In addition the operator populates the value in the time limit field to specify a one hour duration for the override event. In addition the user credentials list includes the user credentials of users for the ACS to provide access to all of the floors independently of the override event. Such users can include first responders to the emergency condition.

In step the ACS receives a message including an ACS landing matrix object from the ACS Security Management Application . The contents of the ACS landing matrix object indicate an override event with unsecured access to floors and and secured access otherwise for one hour time limit.

In response according to step the ACS Landing matrix API applies the front cab door bitmask and rear cab door bitmask of the ACS landing matrix object in an exclusive or operation XOR in one example to all landing matrices on the ACS and applies the user credential list for the one hour specified in the time limit field .

In step the ACS receives user credentials from an access card reader at either Destination Operation Panel DOP or Car Operating Panel COP at floor . According to step the ACS determines if the value for the landing matrix type is set to override . If the result of step is false the ACS executes non override operations associated with the active landing matrix in step . Otherwise the ACS proceeds to step .

In step the ACS then determines if the user s credentials presented to the card reader match any of the user credentials in the user credentials list of the ACS landing matrix object . If the result of step is false indicating no match the ACS denies access to the user in step . This is because the user has attempted to access floor which the override event has specified has secure access and the user s credentials are not in the exemption list provided by user credentials list of the ACS landing matrix object .

If the result of step is true indicating a match the ACS allows access to the user for floor in step . In step the ACS determines if the time limit of the override has expired. If the duration of the override associated with the value in the time limit field has not expired the ACS must wait for the override time limit to expire in step . Otherwise the ACS reverts to using the daytime landing matrix as the active landing matrix in step as the daytime landing matrix in step was defined to be the active landing matrix prior to the override event.

In step in response to an emergency condition an operator uses the ACS configuration application on the security network control system to configure an ACS landing matrix object to override the landing matrices on the ACS . In the example the operator populates the ACS landing matrix object  with an override value for the landing matrix type and the values for the front cab door bitmask and rear cab door bitmask to specify secured access to all floors.

In addition the operator populates the value in the time limit field to specify a one hour duration for the override event. In addition the user credentials list includes the user credentials of users for the ACS to provide access to all of the floors independently of the override event. Such users can include first responders to the emergency condition.

In step the ACS receives a message including an ACS landing matrix object from the security network control system . In step the ACS landing matrix API determines that the ACS landing matrix object indicates an override with secured access to all floors for a one hour time limit.

According to step the ACS Landing matrix API applies the front cab door bitmask and rear cab door bitmask in an exclusive or operation XOR in one example to all landing matrices on the ACS and applies the user credentials list for the time limit specified by the time limit field .

In step the ACS receives user credentials from an access card reader of either a Destination Operation Panel DOP or Car Operating Panel COP at floor for example. The ACS in step then determines if the landing matrix type of the ACS landing matrix object is set to override . If the result of step is false the ACS executes non override operations associated with the active landing matrix in step . Otherwise the ACS proceeds to step .

In step the ACS then determines if the user s credentials presented to the card reader match any of the user credentials in the user credentials list of the ACS landing matrix object . If the result of step is false indicating no match the ACS denies access to the user in step . This is because the user has attempted to access floor which the override event has specified has secure access and the user s credentials are not in the exemption list provided by user credentials list of the ACS landing matrix object .

If the result of step is true indicating a match the ACS allows access to the user for floor in step . In step the ACS determines if the time limit of the override has expired. If the duration of the override associated with the value in the time limit field has not expired the ACS must wait for the override time limit to expire in step . Otherwise the ACS reverts to using the default online landing matrix as the active landing matrix in step .

While this invention has been particularly shown and described with references to preferred embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the scope of the invention encompassed by the appended claims.

