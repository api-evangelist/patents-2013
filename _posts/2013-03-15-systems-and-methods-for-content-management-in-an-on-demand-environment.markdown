---

title: Systems and methods for content management in an on demand environment
abstract: The technology disclosed relates to hosting legacy data sources in a cloud environment. In particular, it relates to providing users with flyweight access to content stored in legacy content repositories from within cloud based applications. It uses full-duplex secure transport tunnels and repository-specific connectors to traverse security layers and access the content repositories. It also creates virtual objects representing the content in the content repositories and embeds them in the cloud based applications.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08990958&OS=08990958&RS=08990958
owner: salesforce.com, inc.
number: 08990958
owner_city: San Francisco
owner_country: US
publication_date: 20130315
---
This application claims the benefit of U.S. Provisional Patent Application No. 61 695 984 entitled Content Management filed on 31 Aug. 2012. The provisional application is hereby incorporated by reference for all purposes.

The subject matter discussed in the background section should not be assumed to be prior art merely as a result of its mention in the background section. Similarly a problem mentioned in the background section or associated with the subject matter of the background section should not be assumed to have been previously recognized in the prior art. The subject matter in the background section merely represents different approaches which in and of themselves may also correspond to implementations of the claimed inventions.

The technology disclosed relates to hosting legacy data sources in a cloud based environment. In particular it relates to providing users with flyweight access to content stored in legacy content repositories from within cloud based applications. It uses full duplex secure transport tunnels and repository specific connectors to traverse security layers and access the content repositories. It also creates virtual objects representing the content in the content repositories and embeds them in cloud based applications.

With the cloud revolution there is an ever increasing need for integrating legacy systems into the cloud environment. Also organizations that have been maintaining legacy databases for years desire integration of their legacy systems with various cloud based applications such as Data.com Work.com etc. Seamlessly integrating legacy systems into a cloud based environment remains a problem that has yet to be solved.

An opportunity has arisen to allow users to host and access content stored in legacy data sources from within a cloud based environment. Better information exchange and inter environmental communication channels may result.

The technology disclosed relates to hosting legacy data sources in a cloud environment. In particular it relates to providing users with flyweight access to content stored in legacy content repositories from within cloud based applications. It uses full duplex secure transport tunnels and repository specific connectors to traverse security layers and access the content repositories. It also creates virtual objects representing the content in the content repositories and embeds them in the cloud based applications.

Other aspects and advantages of the present invention can be seen on review of the drawings the detailed description and the claims which follow.

The following detailed description is made with reference to the figures. Sample implementations are described to illustrate the technology disclosed not to limit its scope which is defined by the claims. Those of ordinary skill in the art will recognize a variety of equivalent variations on the description that follows.

The technology disclosed relates to providing abstracted and aggregated access to multiple content repositories in a cloud environment. In particular it relates to integrating external legacy data sources within cloud based applications.

In one implementation a method for providing flyweight access within a cloud environment to a content object stored in an external content repository such as SharePoint Google Docs Dropbox Box.net etc. The flyweight access can refer to providing access to a document without the document leaving its original source. In other implementations it can refer to making a document accessible from a non original source without making a copy of the document.

In some implementations a content object identifier for a content object stored in an external content repository that a user or a system has selected to access can be received from a cloud or web based software system such as Salesforce.com. The content object identifier can then be passed to a content hub that identifies the data source from the object identifier and uses a repository specific connector to access the content repository and the content object. The content hub can convert the content object identifier to a data type that can be interpreted by the content repository.

In some implementations a two way full duplex secure transport tunnel can be established that traverses one or more firewalls or security layers between the content hub and the content repository that forwards authentication requests and authentication credentials to the content repository. The content object can then be accessed using the repository specific connector.

In some implementations a virtual object can be created that includes an access controlled preview representing the content object and the content object identifier. The virtual object can then be embedded in the content feed. In other implementations the virtual object can include metadata describing the content object and an icon identifying the content repository. In other implementations users can be allowed to manipulate the metadata based on their access rights.

In some implementations the content object identifier can include a variety of fields such as title description origin URL and or unique ID of the content object.

In some implementations the technology disclosed can determine whether the user is authorized to view the preview representing the content object and the content object identifier. If the user is not authorized to view the preview the technology disclosed can determine whether the user is authorized to view the metadata and the icon identifying the external content repository. If the user is authorized to view the metadata and the icon it can select the metadata and the icon for display and if the user is not authorized to view the metadata and the icon it can send a link to request access or automatically grant access based on user preferences.

The technology disclosed can receive from an author a document identifier for a document stored on an external data source that the author has selected to share or post in a social feed. It can then access the author s credentials for access to the external data source and send the document identifier to a content hub that identifies the data source from the document identifier.

As explained above the content hub can then use a secure transport tunnel to traverse one or more firewalls or security layers and use source specific connectors to access the data source. Following this a virtual object that includes an access controlled preview representing the document and the document identifier can be created and embedded into in the social feed.

The technology disclosed can inspect a virtual object representing a document residing on an external data source in the feed item that an author has selected to share or post in response to a recipient request to view a social feed including a feed item. After accessing the recipient s credential the virtual object can be sent to the content hub that identifies the data source from the virtual object.

In some implementations the content hub can use a secure transport tunnel to traverse one or more firewalls or security layers and use source specific connectors to access the data source and supply the recipient s credentials to the data source for authentication checking. Subject to the recipient s access the content hub can provide metadata describing the document an icon identifying the data source and a preview of the document in the social feed and when the recipient does not have access providing only the metadata describing the document and the icon identifying the content repository. In other implementations when the recipient does not have access the content hub can supply a link to request preview of the document in the social feed or automatically grant access based on user preferences.

In some implementations the technology disclosed can include a method for performing a federated search of content across fragmented data sources from a social application. The technology disclosed can receive content identifiers for content stored in fragmented data sources that a user desires access to from the social application. It can send the content identifier to a content hub that uses a secure transport tunnel to traverse one or more firewalls or security layers and uses source specific connectors to access the fragmented data sources and identify the content in at least one of the fragmented data sources.

In some implementations it can create virtual objects that include an access controlled preview representing the content in at least one of the fragmented data sources and present the virtual objects in a user interface responsive to user selection which can be embedded in a social feed as feed items upon user selection.

The technology disclosed relates to generating content management for use in a computer implemented system. The described subject matter can be implemented in the context of any computer implemented system such as a software based system a database system a multi tenant environment or the like. Moreover the described subject matter can be implemented in connection with two or more separate and distinct computer implemented systems that cooperate and communicate with one another. One or more implementations may be implemented in numerous ways including as a process an apparatus a system a device a method a computer readable medium such as a computer readable storage medium containing computer readable instructions or computer program code or as a computer program product comprising a computer usable medium having a computer readable program code embodied therein.

Regarding the multi tenant on demand system SFDC applications SFDC Apps can represent any application running inside the multi tenant on demand system examples can include Force.com Work.com Data.com VisualForce.com and or any of the applications provided by the AppExchange product of SFDC. Apex is an object oriented programming language that can allow developers to execute flow and transaction control statements on Relational Content S Object API . Search can take user input to perform a federated search across the content repositories using Relational Content S Object API as described later in this application. Third party chatter files TPCFs are representations of content stored in the Content Repositories held in virtual objects as described later in this application. Examples of TPCFs can include text audio video or image files or any combination of these file types.

Relational Content S Object API can process database stored procedures from SFDC Apps search apex and TPCFs and submit them to the Internal C HUB API which further forwards them to content hub . In some implementations Relational Content S Object API includes virtual objects that can describe the individual metadata for any of the content objects in the content repositories .

Internal CHUB API can act as a gateway for all data stored procedures and calls made on the content hub . In some implementations all process calls from any of the components of the multi tenant on demand system the customer data center and or CHUB API consumer can be processed through the Internal CHUB API .

Content hub is a single platform that can provide access to various data sources and using repository specific connectors assembled in the remote connector service and full duplex transport tunnel referred to as wormhole. In some implementations content hub can be accessed by users and applications external to the multi tenant on demand system through the CHUB API Consumer which can forward external requests to the Rich Content CHUB API . Rich Content CHUB API can be hosted within the multi tenant on demand system to process requests that include content not addressable by the Relational Content S Object API .

Wormhole tunnel can serve as a bridge between the multi tenant on demand system . In some implementations wormhole tunnel can set up a wormhole service at the content hub and a wormhole client at the remote connector service as described later in this application.

The remote connector service can include various repository specific connectors that are specific to a particular data source. In some implementations repository specific connectors can read and or write to from the Content Repositories .

Content hub can provide unified access to various types of content and data repositories and integrate data from these heterogeneous sources into cloud based applications. In some implementations content hub can access the various content repositories using repository specific connectors that are assembled in a remove connector service.

In some implementations the content hub can use a split architecture where a portion of it runs in a cloud based environment and the client site uses the remote connector service to connect to the different content repositories. The content hub can use a secure transport tunnel to connect with the remote connector service.

Regarding content hub deployment architecture Virtual S Object accessible by users U1 and U2 in ORG1 can assign data stored procedures to Content Hub CHUB 1 . In some implementations Content Hub CHUB 1 can be the primary handler that calls operations on Secure Tunnel Server T1 Secure Tunnel Server T2 connected to SharePoint ORG 1 at Site A and SharePoint ORG 1 at Site B respectively.

Similarly Virtual S Object accessible by user U3 in ORG3 can assign data stored procedures to Content Hub CHUB 2 . In some implementations Content Hub CHUB 2 can be the primary handler that calls operations on Secure Tunnel Server T3 connected to SharePoint ORG 2 at Site C .

In some implementations Secure Tunnel Server T4 can be left idle as a backup server. Organization binding databases and data fields maintain the records for the organization relating to content hub mapping whereas routing table database with data fields maintains the records for the organization relating to site mapping.

At link the Remote Connector Service RCS can set up a serial port SP connection and make a speech to speech STS dial out call to the Secure Tunnel Server Endpoint . If the STS connection drops the RCS can redial. The organization site product combination can be used to route the STS dial out call to specific clusters of secure tunnel servers.

At link the Secure Tunnel Server Endpoint can update the share routing table to reflect the latest mapping. In some implementations organizations ORGs can map to an active and a passive content hub instance to avoid any single point of failure. In other implementations this can be enhanced via internal virtual APIs. At link S Object performs a lazy resolution with the CHUB for ORGs and makes an API call to content hub at link . This call can include an implicit timeout counter and an explicit timeout counter. If any of the following links are broken the timeout counters can throw an error.

Content hub can map to multiple sites based on the user ID and can also map to the STS endpoint at link . Following this the content hub can call the RCS via a secure tunnel at links and . The RCS can send a response to STS at which can be forwarded to the content hub at and to s object at .

In some implementations users can download and install a bootstrap on a local machine in their data center that makes calls to the secure transport tunnel. The secure transport tunnel or wormhole can traverse firewalls and other security layers protecting the various external content repositories. In some implementations wormhole can establish a two way full duplex secure transport channel that is used for communication between a multi tenant on demand system like Salesforce.com and various external content repositories.

In some implementations the wormhole can deploy repository specific connectors and to the remote connector service and configure them at the remote connector service. It can enable integration of various content repositories in the cloud based environment by abstracting the underlying secure connection and providing the standard protocol implementations such as vanilla TCP client software development kit for dynamic proxy remote method invocation RMI via a custom socket factory for the repository specific connectors custom jave.net.SocketFactory SocketChannelFactory and a Java database connectivity driver for a SQL server.

In some implementations the wormhole can support existing repository specific connectors and also configure new connectors. It can setup a wormhole service at the multi tenant on demand system that provides a custom client SDK and internal representational state transfer REST API. The SDK and REST API can be used to query and interact with the repository specific connectors deployed to the remote connector service.

Secure Tunnel Client Endpoint STCE can send an HTTP connection request to HTTP proxy at client site at link . At link HTTP proxy at client site can send a proxy authorization challenge to STCE . STCE can respond to the proxy authorization at link .

HTTP proxy at client site can send an SSL connection request to Secure Tunnel Server Endpoint STSE at link . STSE can send an SSL connection complete confirmation to HTTP proxy at client site at link . HTTP proxy at client site can send an SSL connection complete confirmation to STCE at link .

At link a secure tunnel client handshake can be performed between the STCE and STSE . STSE can send a secure tunnel client challenge to STCE at link . STCE can respond to the challenge at link and STSE can send a secure tunnel server session acknowledgement at link . Following this STCE can establish a secure tunnel server session at link .

The wormhole can include two endpoints referred to as wormhole client service and the wormhole server service . In some implementations the wormhole client can be preconfigured with the address of the wormhole service to make data procedure calls to it. It can set up a proxy NAT traversal that uses the HTTP CONNECT based SSL connection tunneling paradigm and establish a full duplex channel. The wormhole client can perform a handshake with the wormhole service including creating a session and setting up the per session encryption. In other implementations the wormhole client and wormhole service can expose authenticated user interfaces using authentication service and API endpoints for viewing the link status and other monitoring and administration metrics.

In some implementations the wormhole service can be identified by a URL such as sfdc endpoint name and the wormhole client can identified by another URL such as remote site id org id endpoint name. Data transported through the tunnel can carry a destination URL that specifies the application protocol and content object address. In some implementations it can also be an application specific header.

The wormhole endpoints can enable a routing mechanism for delivering data. In some implementations the data can be unframed and delivered to custom adapters that are used to hook RMI and other socket layers to the wormhole client.

The wormhole endpoints and can use a journal log for transmitting data. In some implementations the data to be delivered can be first appended to a journal while another thread can keep reading on journal entries and sending them over to the peer endpoint as frames. On receiving a frame the receiver can save them to an incoming journal and deliver them using a delivery thread. In other implementations a high throughput can be provided using a high performance messaging library such as Disruptor.

The wormhole endpoints and can be registered using an internet service daemon and can include watchers that monitor them. In some implementations the wormhole endpoints can be restarted upon a termination to start sourcing the events from a journal and recover the previous state.

In some implementations the wormhole can be an SSL connection using the provisioning service including a secret shared token based authentication. The remote connector service can handle Internet protocol block whitelisting and connection access control. Furthermore sessions can be secured via pre session adhoc session encryption key. Storage and handling of credentials required for firewall or proxy can be made via password vaults such as OEM or Linux Wallet .

Virtual objects can reference files content and data on external sources like SharePoint Documentum Google Docs Google Drive Box.net Dropbox etc. In some implementations a virtual object can be created using a ContentVersion object provided by the Relational Content S Object API . The ContentVersion represents content files and content library files. In some implementations it can be used to query a specific document in the external content repositories. It can include multiple fields that be specified at design time. Examples of fields include ContentpocumentID ContentLocation ContentUrl Description ExternalpataSOurceId ExternalpocumentInfo1 ExternalpocumentInfo2 FirstPublishLocationID Origin OwnerID ReasonForChange TagCsv Title and VersionData.

The code above can create a virtual object referred to as third party chatter file TPCF for a cloud based social application called Chatter . The TPCF references a document in SharePoint . The URL of the document is https sharepoint.fisker.com sites sfdc sandbox Shared Documents Fiskermarketingguidelines.docx. The server URL of the external data source is https sharepoint.fisker.com.

In the code var cv new sforce.SObject ContentVersion and cv.Origin H indicate that virtual object is a Chatter file cv.ContentLocation E indicates that the Chatter file is an external TPCF. Furthermore cv.ExternalDataSourceId 0XCD0000000005z is the ID of the external data source which is scraped from the browser URL bar when the data source is viewed. The remainder of the URL to the document is placed in cv.ExternalDocumentInfo1 sites sfdasandbox Shared 20Documents Marketing 20 brochure.docx and cv.PathOnClient https sp.marketing.fisker.com sites sfdc sandbox SharedDocuments Marketingbrochure.docx is used to identify the original source of the document and provide the document s extension. The document title cv.Title Fisker Marketing Guidelines can be any test field. Finally the command sforce.connection.create cv creates the TPCF.

In some implementations the user interface as a dashboard interface can be a hosted software service accessible via an Internet web browser and function as a primary interface used by the users to monitor analyze and engage with content repositories . The dashboard interface can allow users to interact with content stored in content repositories using screen based objects and or widgets such as set up . In other implementations the user interface as an engagement console can be a computer desktop application primarily used for team based workflow of social media content engagement.

The user interface can provide an interface or dashboard for users to set up and host multiple legacy content repositories within the social application . In some implementations users can click on the set up widget next to the name of the external content repository they desire to host. For example a user can select the set up widget to host SharePoint in the social application .

Referring to users can provide their credentials for the content repository they desire to host in window using the username tab and password tab . In some implementations users can provide the domain address of the content repository they desires to host in the domain tab .

In some implementations the user interface as a dashboard interface can be a hosted software service accessible via an Internet web browser and function as a primary interface used by the users to create virtual objects and embed them in the social feed of social application as feed items. The dashboard interface can allow users to interact with content stored in content repositories using screen based objects and or widgets. In other implementations the user interface as an engagement console can be a computer desktop application primarily used for team based workflow of social media content engagement.

In some implementations once virtual objects or TPCFs are created according to the process described above in this application they can be viewed in the social application . Referring to when the user accesses Chatter Files tab and clicks the My Files filter the user can view the file Fisker Branding Guidelines.pdf . In some implementations the file can be identified as a SharePoint file by the orange icon to the right of the file name .

Referring to user can select the file Fisker Branding Guidelines.pdf 736 to share it on the social application . In some implementations a controlled access preview of the file can provided through the window along with metadata describing it. In other implementations a screen object can be used to identify SharePoint as the content repository storing the file Fisker Branding Guidelines.pdf .

In some implementations the user interface as a dashboard interface can be a hosted software service accessible via an Internet web browser and function as a primary interface used by the authors to share third party chatter files with other users of the social application referred to as recipients. Subject to recipients access the dashboard interface can allow recipients of third party chatter files to further share the files with other users. In other implementations the user interface as an engagement console can be a computer desktop application primarily used for team based workflow of social media content engagement.

In some implementations an author can select the FirstCall.ppt file from the window described in and post it in the group of . In some implementations file can appear to other users of the group as a feed item in the content feed. When other users or recipient with authorized access to FirstCall.ppt file select the file they can view a preview of the file along with associated metadata and an icon identifying the source of the file as described in .

In some implementations when a user or recipient not authorized to access the file selects the file the user may not be provided the preview of the file . In other implementations such a user can only be provided the metadata associated with the file and the icon of the original source. In yet other implementation users can be supplied a link to request authors or system administrators to grant them access to the file .

In some implementations a user can search a content object like a document in the search bar and receive results and from various data sources such as SharePoint Google Docs Dropbox Contacts Accounts Volunteering Leads and Sessions . The number matches found in a document can be provided by a number representation next to the data sources names.

In some implementations search results and can include multiple virtual objects assorted in screen panes based on the data sources they are stored in. In other implementations the name of the owners of the virtual objects can be displayed using screen text objects along with last modification data as widget .

In one implementation a method is described for providing flyweight access within a cloud based environment to a content object stored in an external content repository. The method includes receiving a content object identifier for a content object that a user or a system has selected to access from a cloud or web based software system wherein the content object is stored on an external content repository.

The method further includes passing the content object identifier to a content hub that identifies the data source from the object identifier and uses a repository specific connector to access the content repository and the content object.

The method further includes traversing one or more firewalls or security layers between the content hub and the content repository using a secure transport tunnel that forwards authentication requests and authentication credentials to the content repository.

The method further includes accessing the content object using the repository specific connector. It further includes creating a virtual object that includes at least an access controlled preview representing the content object and the content object identifier. It further includes embedding the virtual object in the content feed.

This method and other implementations of the technology disclosed can each optionally include one or more of the following features and or features described in connection with additional methods disclosed. In the interest of conciseness the combinations of features disclosed in this application are not individually enumerated and are not repeated with each base set of features. The reader will understand how features identified in this section can readily be combined with sets of base features identified as implementations.

The method further includes the content object identifier including at least a title description origin URL and or unique ID of the content object.

The method further includes the content hub converting the content object identifier to a data type that can be interpreted by the content repository.

The method further includes the virtual object including metadata describing the content object and an icon identifying the content repository.

The method further includes the transport tunnel establishing a full duplex connection between the content hub and the content repository.

The method further includes allowing the user to manipulate the metadata wherein the manipulation is based on user s access rights.

The method further includes providing user based access to the virtual object including determining whether the user is authorized to view the preview representing the content object and the content object identifier. If the user is not authorized to view the preview then determining whether the user is authorized to view the metadata and the icon identifying the external content repository. If the user is authorized to view the metadata and the icon then selecting the metadata and the icon for display and if the user is not authorized to view the metadata and the icon sending a link to request access or automatically granting access based on user preferences.

Other implementations may include a non transitory computer readable storage medium storing instructions executable by a processor to perform any of the methods described above. Yet another implementation may include a system including memory and one or more processors operable to execute instructions stored in the memory to perform any of the methods described above.

In another implementation a method is described for providing an author flyweight access within a social application to a document stored in an external data source. The method includes receiving from an author a document identifier for a document that the author has selected to share or post in a social feed wherein the document is stored on an external data source.

The method further includes accessing the author s credentials for access to the external data source and sending the document identifier to a content hub that identifies the data source from the document identifier.

The method further includes the content hub using a secure transport tunnel to traverse one or more firewalls or security layers and uses source specific connectors to access the data source.

The method further includes creating a virtual object that includes at least an access controlled preview representing the document and the document identifier. It further includes embedding the virtual object in the social feed.

This method and other implementations of the technology disclosed can each optionally include one or more of the following features and or features described in connection with additional methods disclosed.

The method further includes the document identifier including at least a title description origin URL and or unique ID of the document.

The method further includes the virtual object including metadata describing the document and an icon identifying the external data source.

Other implementations may include a non transitory computer readable storage medium storing instructions executable by a processor to perform any of the methods described above. Yet another implementation may include a system including memory and one or more processors operable to execute instructions stored in the memory to perform any of the methods described above.

In yet another implementation a method is described for providing a recipient flyweight access within a social application to a document stored in an external data source. The method includes a response to a recipient request to view a social feed including a feed item inspecting a virtual object in the feed item that an author has selected to share or post wherein the virtual object represents a document residing on an external data source.

The method further includes accessing the recipient s credentials for access to the external data source. It further includes sending the virtual object to a content hub that identifies the data source from the virtual object

The method further includes the content hub using a secure transport tunnel to traverse one or more firewalls or security layers and uses source specific connectors to access the data source. It further includes supplying the recipient s credentials to the data source for authentication checking.

The method further includes subject to the recipient s access providing metadata describing the document an icon identifying the data source and a preview of the document in the social feed. It further includes when the recipient does not have access providing only the metadata describing the document and the icon identifying the content repository or automatically granting access based on user preferences.

This method and other implementations of the technology disclosed can each optionally include one or more of the following features and or features described in connection with additional methods disclosed.

The method further includes when the recipient does not have access supplying a link to request the preview of the document in the social feed.

Other implementations may include a non transitory computer readable storage medium storing instructions executable by a processor to perform any of the methods described above. Yet another implementation may include a system including memory and one or more processors operable to execute instructions stored in the memory to perform any of the methods described above.

In yet another implementation a method is described for performing federated search of content across fragmented data sources from a social application. The method includes receiving content identifiers for content that a user desires access to from the social application wherein the content is stored in at least one of the fragmented data sources.

The method further includes sending the content identifier to a content hub that uses a secure transport tunnel to traverse one or more firewalls or security layers and uses source specific connectors to access the fragmented data sources.

The method further includes identifying the content in at least one of the fragmented data sources. It further includes creating one or more virtual objects that include at least an access controlled preview representing the content in at least one of the fragmented data sources.

The method further includes presenting the virtual objects in a user interface responsive to user selection. It further includes embedding the virtual objects in a social feed as feed items upon user selection.

This method and other implementations of the technology disclosed can each optionally include one or more of the following features and or features described in connection with additional methods disclosed.

The method further includes the content hub converting the content identifiers to data types that can be interpreted by any of the fragmented data sources. It further includes the virtual objects including metadata describing the content and an icon identifying at least one of the fragmented data sources.

While the technology disclosed is disclosed by reference to the preferred embodiments and examples detailed above it is to be understood that these examples are intended in an illustrative rather than in a limiting sense. It is contemplated that modifications and combinations will readily occur to those skilled in the art which modifications and combinations will be within the spirit of the invention and the scope of the following claims.

