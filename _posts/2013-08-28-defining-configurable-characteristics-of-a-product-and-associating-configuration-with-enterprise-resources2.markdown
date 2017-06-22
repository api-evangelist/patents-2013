---

title: Defining configurable characteristics of a product and associating configuration with enterprise resources
abstract: A computer-controlled method of managing third party installations within an enterprise can include inventorying the third party installations, specifying a number of configuration parameters for each third party installation, and storing the configuration parameters for the third party installations in a WSM metadata repository.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09632764&OS=09632764&RS=09632764
owner: Oracle International Corporation
number: 09632764
owner_city: Redwood Shores
owner_country: US
publication_date: 20130828
---
This application claims benefit of provisional patent applications 61 747 913 and 61 747 924 both filed Dec. 31 2012 and provisional patent application 61 800 701 filed Mar. 15 2013 all of which are incorporated by reference herein their entirety.

When managing resources that exist within an enterprise the ability to describe such resources including their logical structure and relationships with each other is critical for allowing an administrator to visualize the enterprise. It is also important to use well established and standardized mechanisms such as those defined by the WS Policy and WS SecurityPolicy standards when configuring resources behavior especially with regard to how access to such resources will be secured. It is also helpful to allow administrators to associate arbitrary metadata e.g. aliases categories or pointers to related information with the resources they are managing.

However every platform has its own method for describing the structure of its resources and the metadata that describe them. Further such methods rarely provide a mechanism for an administrator to associate additional metadata with them especially metadata required for configuring the behavior of third party add on products e.g. Oracle Web Services Manager . In those situations where a platform actually provides some type of mechanism to store custom metadata however it is generally proprietary to the platform thus making any solutions for managing third party resources difficult and potentially prohibitively expensive to develop especially if the product is to consistently manage resources in multiple differing platforms.

Many enterprise products provide an ability to configure certain aspects of its behavior. One of the current solutions is to express all of the associated information as a simple flat collection of name value pairs or dictionary e.g. where each name identifies one aspect of the product to be configured and store the collection as either a block of plain text or simple XML document or database table.

Mobile applications are a rapidly expanding market. With the meteoric rise in the use of smart phones and tablets in recent years businesses are seeking solutions to enable remote access to their services from these devices. Since many of these interactions will happen via the cloud e.g. over the public Internet it is critical that access to these services be secured. Minimally this requires that mobile clients be authenticated but in many cases it also requires that messages be protected from interception and modification.

Current authentication mechanisms vary widely. Since these interactions are typically built on an HTTP transport model the standard HTTP Basic authentication scheme is frequently used. Additionally other new authentication mechanisms e.g. OAUTH are emerging and growing in popularity. For SOAP services WS SecurityPolicy provides more advanced authentication mechanisms such as those based on the use of SAML tokens.

Message protection typically involves keeping the contents of a message confidential e.g. preventing inspection by a third party and ensuring that the integrity of a message is protected e.g. preventing modification thereof . As with authentication there are a wide number of algorithms that are currently employed to fulfill this. However many of those that are performed at the message layer are computationally expensive often prohibitively so on the constrained platform available on mobile devices. Therefore most message protection is done at the transport layer using secure sockets SSL .

Service oriented client applications that access SOAP web services and RESTful resources often must ensure that the requests they send to a service adhere to certain requirements prescribed by the service. For example the service might require that all clients provide a special token that identifies the user on whose behalf a request is being made. This is currently accomplished by building the client application using a comprehensive client library that provides a rich set of features to support various service side requirements. This is often one that implements a standard API e.g. WLS JAX WS for SOAP or Jersey JAX RS for REST . While this may work well in environments with relatively few constraints such as within a JEE container in tightly constrained environments e.g. the iOS or Android mobile platforms it is often unacceptable to require large multi megabyte libraries to enforce these behaviors. In the absence of any native support being provided by the platform application developers are thus forced to implement each variation themselves.

Thus there remains a need for a way to address these and other problems associated with the prior art.

A new WSM Console may be created to provide a WI for managing third party enterprises. The WSM Console may provide an administrator with easy access to the most common management tasks relevant for third party enterprises. This may include application registration modification policy attachment detachment and agent PAP configuration. Secondary tasks currently supported by EM i.e. DMS enforcement audit reporting PSEC Audit configuration policy authoring global policy attachment and policy usage analysis that could be relevant for third party enterprises may or may not be supported.

New applications may be registered with Web Services. This registration process may include the following 

New applications may be registered with Web Service Clients. This registration process may include the following 

New applications may be registered with both Web Services and Web Service Clients. This registration process may include the following 

A policy may be attached to a registered application. This attachment process may include the following 

A policy may be detached from a registered application. This detachment process may include the following 

Application registration may be used to describe an application that has been deployed in an enterprise. The registration process may require the administrator to provide all relevant topology information about the deployed application. This may include details such as the type of platform e.g. WebSphere or JBOSS name of the management domain e.g. cell in WebSphere and server or servers to which it has been targeted.

A registered application may be stored as a document within a WSM metadata repository. The creation deletion or modification of a registered application may be audited using a Common Audit Framework. An audit record may be generated when modifying a registered application to indicate the application that was modified but may not indicate the nature of the modification including any attachment or detachment of policies.

Database based metadata repositories may provide support for document versioning. In these environments an administrator may be able to view an earlier version of a registered application or make an earlier version the current one. Making an earlier version of the current one will generally result in a new version that is an exact copy of the one that was restored.

Port registration may be used to describe the client or service ports that are being hosted by a registered application. The registration may require the administrator to provide all relevant structural information about a port. This may include details such as the type and name of the module that is hosting it the type of port e.g. client or service the name of the enclosing client or service and the name of the port itself.

The module client service and port names will generally match those that are understood by the hosting third party web service stack. Typically these logical names are derived from the physical names for the corresponding entities. A port registration may be stored within a registered application document describing the application that is hosting it.

During registration an administrator may provide the names of the hosting module client and client port. If it is available the administrator may also supply the URL for a WSDL describing the service that a client port connects to. The information within the WSDL may be used to guide the attachment of compatible policies to a client port.

The URL for a WSDL may be modified after registration but the other data generally cannot be changed. If the data needs to be adjusted the relevant port registration may be deleted and a new one declared.

During registration the administrator may provide the name of the hosting module service and service port. If it is available the administrator may instead supply the name of the hosting module and the URL of the WSDL associated with it. When provided the WSDL may be scanned and each service port it contains may be automatically declared.

While the URL for the WSDL may be changed after registration other information provided during registration generally cannot be changed. If such data needs to be adjusted the relevant port registration may be deleted and a new one declared.

Resource management generally allows an administrator to view or modify the registered applications in an enterprise. This may include the ability to unregister an application unregister any of the ports a registered application hosts or register an additional port in an existing registered application.

The task of locating a specific registered application or port registration may be time consuming in an enterprise that hosts a large number of resources but the administrator may simplify this process by providing relevant criteria in a search for resources. An administrator may be able to search for registered applications by supplying any combination of platform type management domain and application name criterion. Similarly the administrator may be able to search for port registration by supplying any combination of platform type management domain application name module name port type and port name criterion. To further simplify the process the administrator may be able to include an asterisk wildcard character for a name type criterion that will match any number of characters in its place.

exportRepository and importRepository CLI commands may provide a mechanism to migrate the contents of a WSM repository from one environment to another. This may be used to migrate a verified configuration from a test environment to a production environment. Because the target environment often uses different names for its entities the importRepository command may allow an administrator to provide a file that describes how to map physical information from the source environment to the target environment. This may be used to transform each document as it is imported to ensure that it is valid.

Physical information in a registered application resource may be updated during import. This may include the ability to rename the management domain modify the list of servers to which a registered application has been targeted and update the URL of a WSDL that has been associated with a client or service port. The command will generally not support the migration of registered applications from one platform to another or the modification of the port registrations hosted in a registered application.

A feature may provide an administrator with the capability to attach web service policies to the client and service ports within an enterprise. These attachments may be declared external to the native deployment descriptors of the hosting application. This mechanism may operate independent of and exclusive to an existing global policy attachment feature.

Attachment by reference may be used to attach policies to a port registration by providing the URI e.g. within a WSM metadata repository of the desired policy. The runtime may automatically retrieve the policy from the repository when it needs to enforce the behavior it describes. The administrator may be able to attach or detach any number of policies as well as indicate whether each policy reference is enabled or disabled.

A policy attachment may be stored within the registered application document containing the port registration it is attached to. The policy attachment will generally not be managed as an independent resource.

Policy subject configuration analysis may be used to validate a port s configuration validate that the set of attached policies are compatible with each other and determine whether it is secured or not. A port is generally considered secure if one or more of the assertions in the policies attached to it enforce a security behavior.

Compatible client policy selection may be used to determine the URIs of the policies that are compatible with the service a client interacts with. If the WSDL of the service is available then the administrator may request a list of the policies that are compatible with it and select from it the policies to attach to the client port.

Scoped configuration overrides may be used to provide properties that affect the behavior of the assertions within a policy. A configuration override may be expressed as a simple name value pair. The effect of a given property generally depends on the assertions it is applied to. The administrator may be able to define any number of configuration overrides that are scoped to a specific policy attachment. Each policy may expose the properties that it recognizes and their default values. This information may be used to assist an administrator with providing relevant configuration overrides for each attachment.

A configuration override may be stored within the registered application document containing the policy attachment it is configuring. The product may implement features to assist with managing configuration and providing an inventory of third party agent installations.

A feature may provide an administrator with the capability to centrally manage product configuration. This may include the ability to specify the PM connection information cache refresh rates nonce timeout clock skew and other similar configuration parameters.

Product configuration parameters may be stored in a WSM metadata repository. An agent instance may use bootstrap connection information specified during installation to connect to the PM to retrieve its full configuration. Whenever a configuration parameter is added modified or removed the agent will generally update its active configuration and persist the full set of parameters locally for the next time it initializes. The detection of configuration changes may be performed periodically using a configurable polling mechanism.

An administrator may be able to specify the value for each supported parameter and have it applied to all agents within a management domain. Additionally some parameters may allow the administrator to override a value for a single server or application.

A feature may provide an administrator with the capability to inventory third party agent installations within an enterprise. This inventory may track various statistics about each installation including the hosting platform its version and the version of the WSM product in use. The inventory will generally include relevant details about each management domain and server. It may also indicate which applications have been configured to support a third party agent.

Certain embodiments of the disclosed technology are generally directed toward techniques for managing multiple resources in an enterprise in an independent and consistent manner regardless of the native capabilities of the platform containing them. Such embodiments generally allow a management product e.g. a Web Services Manager to easily support any third party platform without any dependency on features that are specific to the platform.

Certain embodiments of the disclosed technology are generally directed toward techniques for describing the structure or model of various types of physical and or logical resources in an enterprise e.g. traditional entities such as applications servers management domains platforms and the enterprise itself and the relationships that exist between instances of such resources. Alternatively or in addition thereto embodiments may be generally directed toward defining different types of virtual resources in an enterprise that can be used to represent various collections of resources that are either defined statically i.e. having a constant set of members based on identifying specific resource instances or defined dynamically i.e. having a variable set of members based on the current characteristics of resource instances.

Certain embodiments of the disclosed technology are generally directed toward techniques for describing specific instances of a resource type along with any standard or custom characteristics that may be relevant thereto. Such techniques may also include attaching web service policies to any part of a resource structure that describes behaviors to be enforced during interactions with the resource.

A model metadata component may define a schema used to describe a type of resource or model using an XML infoset. The following describes certain attributes and elements that may be in the schema 

A Policy Manager component may store model metadata in its document repository. The type of these documents is generally model and the URI of these documents is generally the name of the model. Model metadata may be accessed using a document manager component of the Policy Manager.

An instance metadata component may provide a schema to describe a specific resource as an instance of a resource model using an XML infoset. The following describes certain attributes and elements in such a schema 

A Policy Manager component may store instance metadata in its document repository. The type of these documents is resource and the URI of these documents is indicated by its model. Instance metadata may be accessed using a document manager component of the Policy Manager.

A properties metadata component may provide a schema to describe the configuration or inventory of a specific resource using an XML infoset. The following describes certain attributes and elements that may be in the schema 

A Policy Manager component may store properties metadata in its document repository. The type of these documents is the lowercase form of their type attribute and the URI for these documents is the value of their resource attribute. Configuration properties metadata may be accessed using a document manager component of the Policy Manager. Inventory properties metadata may be accessed using a usage tracker component of the Policy Manager.

A seed model metadata component may define a set of documents describing the models predefined by the product. Each document may be loaded into the repository during seeding operations performed by the existing upgrade manager bean APIs.

Enterprise model metadata may be used to describe an enterprise that is managed by the product and access the configuration properties supported by the product. Because the product can typically manage only a single enterprise attempts to create an Enterprise instance will usually result in an error.

Search criterion identifying the model may be the following model Enterprise Search criterion identifying an instance of the model may use the following pattern 

Platform model metadata may be used to describe a platform certified for use by the product. Because the product can typically manage only certified platforms attempts to create or modify a Platform instance will usually result in an error.

Server model metadata may be used to describe a server instance running in a management domain that is managed by the product.

Application model metadata may be used to describe an application that has been deployed into a management domain managed by the product and potentially targeted to one or more of the domain s servers.

A seed instance metadata component may define a set of documents describing the instances predefined by the product. Each document may be loaded into the repository during seeding operations performed by the existing upgrade manager bean APIs.

Certain embodiments of the disclosed technology are generally directed toward techniques for defining a product s configurable characteristics which may also be referred to herein as properties including the specifying of each property s name description structure and default value for example along with indicating which resource type s each property may be associated with. Alternatively or in addition thereto embodiments may be generally directed toward techniques for associating one or more supported configuration values with a resource and collecting an arbitrary set of values which may also be referred to herein as an inventory that describes the particular environment that is hosting the resource.

Certain embodiments of the disclosed technology may allow an administrator to model an application and its client and service ports by describing them in terms of the nodes and components. Furthermore such embodiments may allow an administrator to attach security and management policies to these ports and configure their behavior.

Certain embodiments may implement a feature that provides an administrator with the capability to model the applications within an enterprise and the client and service ports which they host. This may be limited to J2EE applications which host web service or web service client ports using the SOAP over HTTP protocol.

Certain embodiments of the disclosed technology generally allow developers to build applications that satisfy client side requirements without having to implement standard behaviors e.g. providing security tokens themselves. Such implementations may do so in a manner that builds on top of the platform s native APIs for REST or other commonly used lightweight libraries for SOAP instead of requiring a developer to learn how to use an entirely new one. Such embodiments generally define a declarative lightweight solution for enforcing behaviors required by accessing SOAP web services and RESTful resources that requires little integration.

Certain embodiments of the disclosed technology are directed to an agent for mobile application development framework APPDF applications which may be implemented as a Web Services Manager component. Such a component may provide a library that can be used by application development frameworks e.g. APPDF Mobile to enforce authentication message protection and other behaviors for Java based mobile clients that access REST resources and SOAP based web services.

An APPDF Mobile product in accordance with the disclosed technology may be used to enforce policies attached to mobile web service clients. In their architecture web service clients may be defined by entries in the APPDF s connections.xml file for example. These entries may indicate the location of the web service and the protocol used to access it e.g. SOAP or RESTful . They may also specify the policies to be enforced by URI and any policy configuration properties.

Mobile applications may use the APPDF Mobile product to access SOAP version 1.1 1.2 for example and RESTful web services exposed by an application deployed to an enterprise class server e.g. a JEE container . In an example a SOAP service may be hosted by a WebLogic Server and be configured to use WSM to enforce security policies. For example SOAP web services may be configured to use a seed policy that allows a client to use one of a variety of different authentication mechanisms e.g. HTTP Basic authentication credentials a WS SecurityPolicy username token or a WS SecurityPolicy SAML token with either WS SecurityPolicy message protection or SSL.

An agent for mobile applications in accordance with the disclosed technology may provide the ability to enforce pre defined security and management scenarios when making requests to REST resources and SOAP based web services. A scenario to be enforced may be specified in the form of a URI that references a web service policy document e.g. expressed using the WS Policy language that contains one or more assertions that define the desired behavior. Additionally a reference may be accompanied by configuration properties that override the default behavior defined by the policy.

Such an agent for mobile applications may be packaged with a framework e.g. APPDF Mobile that provides facilities for developing mobile applications including Java based business logic that accesses REST resources or SOAP based web services. Rather than being directly consumed by an application s business logic the agent may act as an internal component supporting the application development framework.

An agent for mobile applications in accordance with the disclosed technology may be delivered to consuming frameworks in the form of a library e.g. packaged as a set of Java archives JAR files to be included with the customer s application. The framework will be generally responsible for calling the relevant APIs provided by the library to initialize the agent and integrating it with the appropriate web service stack e.g. kSOAP2 before client requests and server responses are processed.

Embodiments of the disclosed technology may be integrated with systems that use separate specific abstractions for web service messages and the transports used to send receive them.

In the example a Mobile Application initializes the APPDF Mobile Framework before it can invoke SOAP based web services. Internally the APPDF Mobile Framework manages a list of APPDF Connection components one for each callable web service. When an APPDF Connection component is created for a SOAP web service it creates one instance of a kSOAP2 HTTP Transport component to call the web service and one instance of the WSM kSOAP2 Agent component to enforce policies attached to it according to the Configuration supplied to it .

When a Mobile Application 1 invokes a web service the APPDF Mobile Framework component 2 creates an envelope for a request a kSOAP SOAP Envelope component and then 3 calls the service by passing the envelope to the kSOAP2 HTTP Transport component created during initialization. The transport 4 creates a connection based on a kSOAP2 Service Connection through which the envelope will be sent and uses the agent to 5 create an enforcement context. This context is used to create proxies for both the envelope a WSM SOAP Envelope Proxy and connection a WSM Service Connection Proxy . Finally the transport 6 streams the proxy envelope through the proxy connection to the web service.

Embodiments of the disclosed technology may be integrated with systems that use a single specific abstraction for the transportation of web service messages but do not have a specific abstraction for the messages themselves and instead use primitive mechanisms such as binary text data streams. illustrates an example of system implementing a Java ME HTTPConnection API in accordance with certain embodiments of the disclosed technology.

In the example a Mobile Application initializes the APPDF Mobile Framework before it can invoke RESTful web services. Internally the APPDF Mobile Framework manages a list of APPDF Connection components one for each callable web service. When an APPDF Connection component is created for a SOAP web service it creates one instance of the WSM HTTP Connection Agent component to enforce policies attached to it according to the Configuration supplied to it .

When a Mobile Application 1 invokes a RESTful web service the APPDF Mobile Framework component 2 creates a connection based on a Java ME HTTP Connection through which a request will be sent and uses the agent to 3 create an enforcement context. This context is used to create a proxy for the connection a WSM HTTP Connection Proxy . Finally the framework 4 streams the request through the proxy connection to the web service.

The following discussion is intended to provide a brief general description of a suitable machine in which embodiments of the disclosed technology can be implemented. As used herein the term machine is intended to broadly encompass a single machine or a system of communicatively coupled machines or devices operating together. Exemplary machines may include computing devices such as personal computers workstations servers portable computers handheld devices tablet devices and the like.

Typically a machine includes a system bus to which processors memory such as random access memory RAM read only memory ROM and other state preserving medium storage devices a video interface and input output interface ports can be attached. The machine may also include embedded controllers such as programmable or non programmable logic devices or arrays Application Specific Integrated Circuits ASICs embedded computers smart cards and the like. The machine may be controlled at least in part by input from conventional input devices such as keyboards and mice as well as by directives received from another machine interaction with a virtual reality VR environment biometric feedback or other pertinent input.

The machine may utilize one or more connections to one or more remote machines such as through a network interface modem or other communicative coupling. Machines can be interconnected by way of a physical and or logical network such as an intranet the Internet local area networks wide area networks etc. One having ordinary skill in the art will appreciate that network communication may utilize various wired and or wireless short range or long range carriers and protocols including radio frequency RF satellite microwave Institute of Electrical and Electronics Engineers IEEE 545.11 Bluetooth optical infrared cable laser etc.

Embodiments of the disclosed technology may be described by reference to or in conjunction with associated data including functions procedures data structures application programs instructions etc. that when accessed by a machine may result in the machine performing tasks or defining abstract data types or low level hardware contexts. Associated data may be stored in for example volatile and or non volatile memory such as RAM and ROM or in other storage devices and their associated storage media which can include hard drives floppy disks optical storage tapes flash memory memory sticks digital video disks biological storage and other non transitory physical storage media.

Associated data may be delivered over transmission environments including the physical and or logical network in the form of packets serial data parallel data etc. and may be used in a compressed or encrypted format. Associated data may be used in a distributed environment and stored locally and or remotely for machine access.

Having described and illustrated the principles of the invention with reference to illustrated embodiments it will be recognized that the illustrated embodiments may be modified in arrangement and detail without departing from such principles and may be combined in any desired manner. And although the foregoing discussion has focused on particular embodiments other configurations are contemplated. In particular even though expressions such as according to an embodiment of the invention or the like are used herein these phrases are meant to generally reference embodiment possibilities and are not intended to limit the invention to particular embodiment configurations. As used herein these terms may reference the same or different embodiments that are combinable into other embodiments.

Consequently in view of the wide variety of permutations to the embodiments described herein this detailed description and accompanying material is intended to be illustrative only and should not be taken as limiting the scope of the invention. What is claimed as the invention therefore is all such modifications as may come within the scope and spirit of the following claims and equivalents thereto.

