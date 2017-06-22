---

title: Modularly managed service platform
abstract: A service method and associated system is provided. The method includes generating event types for events and services associated with the events. Virtual or physical machines associated with the services are provisioned and a message associated with a first event is published. The message is routed to a queue of a second service and the second service is notified of the message. The services are enabled and a selection for a sub-set of the services is received. The selection is enabled.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09547835&OS=09547835&RS=09547835
owner: International Business Machines Corporation
number: 09547835
owner_city: Armonk
owner_country: US
publication_date: 20130820
---
One or more embodiments of the invention relates generally to a method and associated system for managing services and in particular to a method and associated system for modularly managing a service platform.

Performing management functions typically includes an inaccurate process with little flexibility. Providing an efficient method for determining a basis for managing may include a complicated process that may be time consuming and require a large amount of resources. Accordingly there exists a need in the art to overcome at least some of the deficiencies and limitations described herein above.

A first embodiment of the invention provides a method comprising generating by a computer processor of a computing system multiple event types for a plurality of events generating by the computer processor a plurality of services associated with said plurality of events the plurality of services comprising a platform provided service a customer provided service and or a third party provided service provisioning by the computer processor a plurality of virtual or physical machines associated with the plurality of services publishing by the computer processor executing a first service of the plurality of services via an exchange associated with a first event of the plurality of events a first message associated with the first event routing by the computer processor to a queue of a second service of the plurality of services the first message notifying by the computer processor the second service of the first message within the queue enabling by the computer processor based on the provisioning the platform provided service the customer provided service and or the third party provided service receiving by the computer processor from a user during the provisioning a selection comprising a sub set of the platform provided service the customer provided service and or the third party provided service and enabling by the computer processor the selection.

A second embodiment of the invention provides computer program product comprising a computer readable hardware storage device storing a computer readable program code the computer readable program code comprising an algorithm that when executed by a computer processor of a computer system implements a method the method comprising generating by the computer processor multiple event types for a plurality of events generating by the computer processor a plurality of services associated with the plurality of events the plurality of services comprising a platform provided service a customer provided service and or a third party provided service provisioning by the computer processor a plurality of virtual or physical machines associated with the plurality of services publishing by the computer processor executing a first service of the plurality of services via an exchange associated with a first event of the plurality of events a first message associated with the first event routing by the computer processor to a queue of a second service of the plurality of services the first message notifying by the computer processor the second service of the first message within the queue enabling by the computer processor based on the provisioning the platform provided service the customer provided service and or the third party provided service receiving by the computer processor from a user during the provisioning a selection comprising a sub set of the platform provided service the customer provided service and or the third party provided service and enabling by the computer processor the selection.

A third embodiment of the invention provides computer system comprising a computer processor coupled to a computer readable memory unit the memory unit comprising instructions that when executed by the computer processor implements a method comprising generating by the computer processor multiple event types for a plurality of events generating by the computer processor a plurality of services associated with the plurality of events the plurality of services comprising a platform provided service a customer provided service and or a third party provided service provisioning by the computer processor a plurality of virtual or physical machines associated with the plurality of services publishing by the computer processor executing a first service of the plurality of services via an exchange associated with a first event of the plurality of events a first message associated with the first event routing by the computer processor to a queue of a second service of the plurality of services the first message notifying by the computer processor the second service of the first message within the queue enabling by the computer processor based on the provisioning the platform provided service the customer provided service and or the third party provided service receiving by the computer processor from a user during the provisioning a selection comprising a sub set of the platform provided service the customer provided service and or the third party provided service and enabling by the computer processor the selection.

The present invention advantageously provides a simple method and associated system capable of performing management functions.

System comprises network connected to terminals and . Network comprises a controller server connected to remote servers a software application and a database s . System enables the following network types 

1. A hardware infrastructure as a service for providing virtual machines as a service an operating system and applications.

2. A managed infrastructure as a service for providing full service virtual machines. A service contract may include providing software services for an underlying virtual machine. The services may include inter alia software upgrades patch support support for compliance license management etc. for a provided software infrastructure.

System enables a method such that when a VM is provisioned a set of selected managed services will be installed and configured on the VM. Selected services may include inter alia MIaaS services customer services etc. Each managed service provides a set of standard APIs that allow 

1. Public service A public service comprises a service available to all customers registered on an MIaaS platform.

2. Private service A private service comprises a service available to one or a pre specified set of customers.

3. Untrusted service An untrusted service comprises a service that is untrusted and is not allowed to perform any actions on an associated platform.

4. Trusted service A trusted service comprises a service that may perform actions on the platform e.g. on hypervisors . Trusted services comprise public services created by the MIaaS platform provider or a trusted source.

3. One or more virtual physical machines are provisioned. Provisioning a virtual physical machine requires at least one service i.e. a provisioning service s .

A. Uploading installing and configuring scripts for an associated service in a script repository managed by a script execution manager.

C. Registering event types that the associated service will subscribe to in the event register. A unique queue is created for each service event type pair and the queue is connected to an exchange corresponding to the event type.

D. Registering a service with information regarding associated scripts SLAs and additional arguments in a service register.

A. Selecting by a user one or more services including a provisioning service as a first service for a new virtual machine. Additionally the user selects a resource configuration e.g. CPU memory resources required and image file to use for the provisioning. B. Creating a plan comprising a sequence of steps. Each step is configured to execute an install script or a configure script for a selected service. C. A plan and request are added to a provisioning queue. D. A choreographer module retrieves a request from the head of the provisioning queue. E. A script execution manager executes each step of the plan i.e. each script in sequence. F. Executing all steps of the plan thereby provisioning a VM with all requested services.

A. A service e.g. a service A publishes an event via an event message transmitted to an exchange for the event.

B. The event message is routed to the queues of each subscribing service e.g. a service B a service C etc. .

C. Each subscribing service e.g. service B is notified of the event message in its queue thereby enabling an associated action.

System enables a process allowing data exchange between services. For example system enables data exchange between a composite service and component services. Additionally system enables data exchange between a service and impacted services. Data exchange between a composite service and component services uses APIs provided by the service to retrieve data generated by the service e.g. a placement service retrieves resource usage data from a monitoring service . The two services are responsible for transport. Data exchange between a service and impacted services comprises a platform providing a publish subscribe mechanism to receive and notify events.

1. Uploading scripts associated with the first service and a second service to a script repository managed by a script execution manager.

4. Registering a group of the multiple event types that the services will publish in the event register.

5. Registering an additional group of the multiple event types that the services will subscribe to in the event register.

6. Generating unique queues for pairs of event types of the multiple event types and associated service types of the services.

7. Connecting each queue of the unique queues to an associated unique exchange corresponding to an associated event type of the multiple event types.

8. Registering in a service register the services with information describing associated scripts of the service.

In step a plurality of virtual or physical machines associated with the services are provisioned. Provisioning the plurality of virtual or physical machines may include the following process 

1. Receiving from a user a selection for one or more services of the services for application to a new virtual or physical machine of the plurality of virtual or physical machines.

2. Receiving from the user a selection for a resource configuration and image file for use in the provisioning.

3. Generating a plan comprising a sequence of steps for configuring the scripts for selected services.

In step the platform provided service the customer provided service and or the third party provided service are enabled. In step a selection comprising a sub set of the platform provided service the customer provided service and or the third party provided service is received from the user. In step the selection is enabled. In step a first message associated with first event is published. In step the first message is routed to a queue of a second service. In step the second service is notified of the first message within the queue.

Still yet any of the components of the present invention could be created integrated hosted maintained deployed managed serviced etc. by a service supplier who offers to modularly manage a service using a network of remote servers hosted on the Internet. Thus the present invention discloses a process for deploying creating integrating hosting maintaining and or integrating computing infrastructure including integrating computer readable code into the computer system wherein the code in combination with the computer system is capable of performing a method for modularly managing a service using a network of remote servers hosted on the Internet. In another embodiment the invention provides a business method that performs the process steps of the invention on a subscription advertising and or fee basis. That is a service supplier such as a Solution Integrator could offer to modularly manage a service using a network of remote servers hosted on the Internet. In this case the service supplier can create maintain support etc. a computer infrastructure that performs the process steps of the invention for one or more customers. In return the service supplier can receive payment from the customer s under a subscription and or fee agreement and or the service supplier can receive payment from the sale of advertising content to one or more third parties.

While shows the computer system as a particular configuration of hardware and software any configuration of hardware and software as would be known to a person of ordinary skill in the art may be utilized for the purposes stated supra in conjunction with the particular computer system of . For example the memory devices and may be portions of a single memory device rather than separate memory devices.

While embodiments of the present invention have been described herein for purposes of illustration many modifications and changes will become apparent to those skilled in the art. Accordingly the appended claims are intended to encompass all such modifications and changes as fall within the true spirit and scope of this invention.

