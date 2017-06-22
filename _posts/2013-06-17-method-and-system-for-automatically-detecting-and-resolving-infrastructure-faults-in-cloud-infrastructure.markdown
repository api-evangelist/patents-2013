---

title: Method and system for automatically detecting and resolving infrastructure faults in cloud infrastructure
abstract: Systems and methods are provided for any party in a cloud ecosystem (cloud providers of such resources, the intermediate management software for such resources, and the end user of such resources) to detect and resolve faulty resources synchronously or asynchronously, before said faults adversely affect the users' workloads. The system requests a service or set of one or more resources within a cloud, automatically checking the infrastructure for various faults that would cause it to be non-functional, including pre-defined and user-defined checks, and resolving them before including the infrastructure in the working service cluster of resources. The system presents an API to the user that returns only functional, production-quality resources that are not in a faulty state. An API that tests and resolves bad infrastructure can be registered during the request or a preceding/subsequent API call, removing the need for the end-user to deal with various types of infrastructure faults.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09146840&OS=09146840&RS=09146840
owner: Cycle Computing, LLC
number: 09146840
owner_city: Greenwich
owner_country: US
publication_date: 20130617
---
This application claims the benefit of priority from U.S. Patent Application Ser. No. 61 660 300 entitled Method and System for Automatically Detecting and Resolving Infrastructure Faults in Cloud Infrastructure filed Jun. 15 2012 the contents of which are incorporated herein by reference.

The present invention relates to adaptive cloud computing systems and to a method and system for automatically detecting and resolving infrastructure faults in cloud infrastructure.

Cloud computing environments enable the provisioning of infrastructure platforms and software all of them generalized as resources available as a service via an Application Programming Interface API most commonly over a network protocol or web service API. When using these cloud resources there are varying Fault rates in acquiring as an example server instances that will run a user s application.

User client application makes an API request that requires resources from a Cloud using the Cloud s API

The servers implementing the Cloud API allocate all or part of the resources from the infrastructure available in the Cloud that are required to fulfill the request

As an example of current systems a request for server instances or a service that requires server instances to be implemented can be fulfilled and given to a user. In practice some of these nodes contain resources that are and are not functioning properly and would not execute their intended workload due to various potential faults. Specifically on today s cloud environments 0.5 to 40 Fault rates occur for server instances which when they occur cause the requested service or the systems that the user is using the resources for to not function properly. This situation becomes a particularly acute problem with larger numbers of requested resources as even small Fault rates can represent large numbers of faulty resources.

The current art in adaptive cloud infrastructures deals with load U.S. Pat. No. 8 458 717 and disaster recovery based scenarios U.S. Pat. No. 8 381 015 without considering the health viability of infrastructure within the cloud in general. The present invention addresses this shortcoming by disclosing a system and method for running checks and resolving errors in the infrastructure automatically either as part of management software or cloud provider operations which allows for efficient rerouting across healthy infrastructure resources.

In one aspect of the invention software that manages creating individual infrastructure or clusters of infrastructure responds to a user request for more resources by acquiring them from a cloud provider checking the resources provided by the cloud provider for faults resolving them appropriately either through a solution or through requesting new or more infrastructure. Faulty infrastructure may be held on to before requesting new infrastructure or using scripts to resolve the fault or remove the infrastructure. The client request then receives fully working infrastructure for use.

In another aspect of the invention the a cloud provider accepts web service requests to acquire virtual machine resource s or a platform that is powered by a cluster of virtual machine or bare metal resource s . After the request for new instances come in the infrastructure required to respond to the request are either checked and resolved at request time or picked from an asynchronously determined list of healthy resources. The response to the web request or the cluster of resources provisioned to provide a working service would then contain a majority of healthy resources that have been vetted by various checks.

The invention provides a system and method for any party in the cloud ecosystem including the cloud providers of such resources the intermediate management software for such resources and the end user of such resources to detect and resolve any faulty resources from adversely affecting the users workloads. The invention also relates to outlining the impact to billing for resources that are determined to be erroneous.

The invention provides a system for requesting a service or set of one or more resources within a cloud automatically checking the infrastructure for various faults that would cause it to be non functional including pre defined and user defined checks and resolving them before including the infrastructure in the working service cluster of resources. Additionally the invention provides a system further reacts to bad server infrastructure in a running computing environment and removes it from service. Additionally the invention provides a method for returning the infrastructure that will optimally keep the infrastructure in use below any limits imposed by the provider. The invention provides a system that presents an API to the user that returns only functional production quality resources that are not in a faulty state. The invention also provides an API where tests and resolution methods for bad infrastructure can be registered during the request or a preceding subsequent API call removing the need for the end user to deal with various types of infrastructure faults. These systems implement innovative new ways of resolving faulty resources automatically so they do not affect end user cluster environments the limits set up by cloud providers or end user workloads.

A process for validating a service or set of one or more resources within a cloud comprising automatically checking an infrastructure to detect for any faults including pre defined and user defined checks that would cause the infrastructure to be non functional resolving any faults that are detected including the infrastructure in a working service cluster of resources and presenting to the user only functional resources that are free of faults.

The process may include wherein the step of resolving the fault is performed synchronously. The process may also include wherein the step of resolving the fault is performed asynchronously. The process may also include wherein the process further comprises the step of removing from working service a faulty server infrastructure in a running computing environment.

A process of using management or client software comprising receiving resources from a cloud application programming interface that may be non faulty or faulty running fault tests against the resources or service to detect for the presence of faults making the detected faulty resources non faulty and communicating the resources to a client application.

The process may include wherein the step of making comprises removing the detected fault. The process may also include wherein the step of making comprises correcting the detected fault.

A process for validating cloud based resources in order to maintain a list of fault free resources comprising a testing the ability to log into an infrastructure server b testing the ability to access a file system within the infrastructure server c alerting the results of steps a and b back to fault detection and resolution software in at least one of the Cloud Management or Client software and if a fault is detected in any of steps a c performing at least one of d holding the resources for examination e ensuring that the same faulty resource is not re acquired or f shutting down the resource.

The process may include wherein steps a c are performed by software run external to the cloud based resources. The process may also include wherein at least one of steps a f is performed synchronously. The process may also include wherein at least one of steps a f is performed asynchronously. The process may also include wherein if no fault is detected in any of steps a c further including the step of including the server infrastructure in a working server cluster of resources.

A process for returning infrastructure that will keep the infrastructure in use below any limits imposed by the provider.

A system comprising an application programming interface API which tests infrastructure for faults resolves any faults in the infrastructure and registers the faulty infrastructure during the request or a preceding subsequent API call thereby removing the need for an end user to deal with infrastructure faults in user defined fault checks.

A system for validating a service or set of one or more resources within a cloud comprising an application programming interface API which automatically checks an infrastructure to detect for any faults including pre defined and user defined checks that would cause the infrastructure to be non functional resolves any faults that are detected includes the infrastructure in a working service cluster of resources and presents to the user only functional resources that are free of faults.

A system for using management or client software comprising an application programming interface API which receives resources from a cloud application programming interface that may be non faulty or faulty runs fault tests against the resources or service to detect for the presence of faults makes the detected faulty resources non faulty and communicates the resources to a client application.

A system for validating cloud based resources in order to maintain a list of fault free resources comprising an application programming interface API which a tests the ability to log into an infrastructure server b tests the ability to access a file system within the infrastructure server c alerts the results of steps a and b back to fault detection and resolution software in at least one of the Cloud Management or Client software and if a fault is detected in any of steps a c performs at least one of d holds the resources for examination e ensures that the same faulty resource is not re acquired or f shuts down the resource.

The system may include wherein the API performs at least one of steps a f synchronously. The system may also include wherein the API performs at least one of steps a f asynchronously.

A preferred embodiment of a process and system according to the invention will be described but the invention is not limited to this embodiment. It is understood that the fault check and resolution process performed by the invention may be performed synchronously e.g. just in time JIT or asynchronously beforehand . It is also understood that the term infrastructure as used in this application encompasses servers and other nodes connected to a cloud computing environment but it not limited thereto.

Although the present invention has been described in detail it should be understood that various changes substitutions and alterations can be made hereto without departing from the spirit and scope of the invention as defined by the appended claims.

The Client Application A1 sends a request A2 for a service or set of resources from an IaaS PaaS SaaS cloud API A3 . As used here is understood that IaaS means Infrastructure as a Service PaaS means Platform as a Service and SaaS means Software as a Service. 

This causes the Cloud A0 to allocate A4a dashed arrow path resources A4b some of which are Healthy A5 and Faulty A6 .

These resources are passed to a Fault detection and correction software component A8a that runs a set of one or more checks against the resources A8b some of which are pre defined for that cloud A0 and by that client A1 .

Based upon the results of the checks for faults A8b the Fault detection and correction software component A8a then holds or shuts down the faulty resources A9 or deploys the healthy infrastructure into a production service or resources A10 . These checks for faults A8b may be performed in advance asynchronously on cloud resources causing allocation A4a to be based on previously checked resources. Allocation A4a is represented by a dotted arrow path.

The Fault Detection and Correction software might notice infrastructure that is going faulty A12a through sporadic or periodic checks A12b and resolve that as well.

The final Production or Healthy service or resources would be communicated A13 back to the Cloud API A3 for subsequent communication A14 to the Client A1 .

The Client Application B1 sends a request B2 for a service or set of resources from an IaaS PaaS SaaS cloud API B3 .

These resources are communicated back B7 to the Cloud API B3 and presented back to the user facing API which is communicating with a Fault Detection and Resolution Management or Client software B8a . The Fault Detection and Resolution Management or Client software B8a runs a set of one or more checks against the resources B8b some of which are pre defined for that cloud B0 and by that client B1 .

Based upon the results of the checks for faults B8b the Fault Detection and Resolution Management or Client software B8a then holds or shuts down the faulty resources B9 or deploys the healthy infrastructure into a production service or resources B10 .

The Fault Detection and Correction software might notice infrastructure that is going faulty B12 through sporadic or periodic checks B13 and resolve that as well.

The final Production or Healthy service or resources B10 would be returned back B14 to the Client B11 for its use.

Fault detection and correction software with pre defined and user defined fault checks C1 that runs optional external resource fault checks C2 on the Resource C3 e.g. test whether resource can be SSH s into without error.

An Optional fault detection software C4 running in the resource C3 alerts C5 the Fault detection and correction software with pre defined and user defined fault checks C1 that the node is faulty or becoming faulty or in a given state. The Fault detection and correction software with pre defined and user defined fault checks C1 the chooses optional actions including optionally calling the Cloud API for Resource Shutdown C6 to keep the resources used below the provider limits or the Cloud API for new resource requests with a subject optional shutdown.

A system for requesting a service or set of one or more resources within a cloud automatically checking the infrastructure for various faults that would cause it to be non functional including pre defined and user defined checks and resolving them before including the infrastructure in the working service cluster of resources as shown in and its description. The Cloud API in this system presents to the user only functional production quality resources that are not in a faulty state 

This system further reacts to bad server infrastructure in a running computing environment and removes it from service A12 as shown in 

A separate system that uses management or client software to receive resources from the Cloud API that may be healthy or fault run fault tests against the resources or service and make them all healthy before communicating them to the Client application as shown in 

An API where tests and resolution methods for bad infrastructure can be registered during the request or a preceding subsequent API call removing the need for the end user to deal with various types of infrastructure Faults as shown in in the user defined fault checks 

Additionally a system for running tests against resources which includes software run external to the resource e.g. testing the ability to log into a server and internal to the resource e.g. testing the ability to access a file system alerting the status back to the Fault Detection and Resolution software either in the Cloud Management or Client software and either holding the resources for examination or to make sure the same faulty resource is not re acquired or merely shutting down the resource as depicted in .

Additionally a method for returning the infrastructure that will optimally keep the infrastructure in use below any limits imposed by the provider as shown in .

While a preferred embodiment according to the invention has been described the invention is not limited to this embodiment and variations and modifications can be made without departing from the scope of the invention. The scope of the invention is defined by way of the following claims.

