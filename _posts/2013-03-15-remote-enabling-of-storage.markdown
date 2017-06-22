---

title: Remote enabling of storage
abstract: Techniques for enabling storage remotely are presented. A REpresentational State Transfer (REST) front-end interface is interfaced to a legacy file system via a backend interface that directly interacts with the native storage and protocols of the legacy file system. The REST interface is presented as the frontend interface to the legacy file system making the storage of the legacy file system available to web or network-enabled devices.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09141287&OS=09141287&RS=09141287
owner: Novell, Inc.
number: 09141287
owner_city: Provo
owner_country: US
publication_date: 20130315
---
Data is essential to all organizations. The data relevant to organizations includes data produced by the organizations data consumed by the organizations and data analyzed by the organizations. In many instances organizations have spent many years if not decades collecting and storing data on traditional file servers. Sometimes these file servers are identity controlled and include rigorous business processes set up around the servers to control and protect the data with antivirus software audit control software and backup and restore software.

Data is big business these days and one does not have to look very far to see evidence in this by the organizational heavy weights with a presence in the data storage business IBM Microsoft HP Oracle Google Facebook and others.

However to date storage services are generally only available via tightly coupled heavy weight protocols not directly accessible via lightweight clients such as mobile phones and tablets locked inside corporate firewalls and not inherently searchable not indexed . Evidence of this exists by the large amount of data that is currently just available via mounted or mapped drives NCP Netware Control Program CIFS Common Internet File System NFS Network File System FTP File Transfer Protocol etc. and not available via today s web oriented applications.

In fact today s web access for data is often optimized around technology that focuses on indexing searching alerting notifying sharing and collaborating. Still further today s data access focuses on generic interfaces to access the data which exists in the cloud rather then in legacy hierarchical file systems.

Many technologies exists today in the industry to make data access generic and location independent Amazon S3 Dropbox Sky Drive Google Drive iCloud etc. however these technologies all share one significant problem and that is they all work on new data and not with existing legacy data. As a result unless an enterprise wants to go through a significant data port years of knowledge represented in its legacy data remains largely inaccessible via modern platforms and devices.

Various embodiments of the invention provide techniques for remotely enabling a storage environment. In an embodiment a method for remote storage enablement is presented.

Specifically a storage operation is received that is directed to legacy storage the storage operation is in a first format that is unrecognized by a legacy Application Programming Interface API used by the legacy storage. Next the storage operation is translated from the first format to a second format associated with the legacy API. Finally the storage operation is sent in the second format to the legacy storage for processing.

A resource includes a user service system device directory data store groups of users file system combinations and or collections of these things etc. A principal is a specific type of resource such as an automated service or user that at one time or another is an actor on another principal or another type of resource. A designation as to what is a resource and what is a principal can change depending upon the context of any given network transaction. Thus if one resource attempts to access another resource the actor of the transaction may be viewed as a principal. Resources can acquire and be associated with unique identities to identify unique resources during network transactions.

An identity is something that is formulated from one or more identifiers and secrets that provide a statement of roles and or permissions that the identity has in relation to resources. An identifier is information which may be private and permits an identity to be formed and some portions of an identifier may be public information such as a user identifier name etc. Some examples of identifiers include social security number SSN user identifier and password pair account number retina scan fingerprint face scan etc.

A processing environment defines a set of cooperating computing resources such as machines processor and memory enabled devices storage software libraries software systems etc. that form a logical computing infrastructure. A logical computing infrastructure means that computing resources can be geographically distributed across a network such as the Internet. So one computing resource at network site X and be logically combined with another computing resource at network site Y to form a logical processing environment.

The phrases processing environment cloud processing environment and the term cloud may be used interchangeably and synonymously herein.

Moreover it is noted that a cloud refers to a logical and or physical processing environment as discussed above.

Also the techniques presented herein are implemented in machines as executable instructions the machines include a processor or processor enabled devices hardware processors . These machines are configured and their memories programmed to specifically perform the processing of the methods and systems presented herein. Moreover the methods and systems are implemented and reside within memory and or a non transitory computer readable storage media or machine readable storage medium and are processed on the machines configured to perform the methods.

Of course the embodiments of the invention can be implemented in a variety of architectural platforms devices operating and server systems and or applications. Any particular architectural layout or implementation presented herein is provided for purposes of illustration and comprehension only and is not intended to limit aspects of the invention.

It is within this context that embodiments of the invention are now discussed within the context of the .

In an embodiment the storage interface manager operates as a reverse proxy for a legacy storage environment. That is storage access requests originating over a network that is external to the legacy storage environment are intercepted and processed by the storage interface manager. In some cases the storage interface manager may exists in a cloud and be completely external to the legacy storage environment. The access requests can be made directly to the legacy storage environment in which case they are routed to the cloud that processes the storage interface manager or the access requests can be made directly to the storage interface manager in which case the storage interface manager resolves the proper legacy storage environment and directly interacts with it to resolve the access requests.

At the storage interface manager receives a storage operation directed to legacy storage. The storage operation is in a first format that in unrecognized by a legacy Application Programming Interface API used by the legacy storage. By legacy it is meant that the storage environment and the API of the storage already exist and are unchanged for purposes of the teachings presented herein. In other words to gain access to the legacy storage existing and new APIs can be used as described herein without changes to the legacy storage having to be made.

According to an embodiment at the storage interface manager recognizes the first format as a storage operation issued via a REpresentational State Transfer REST interface.

Continuing with the embodiment of and at the storage interface manager identifies a requesting device that provides the storage operation via the REST interface as a mobile device of a user such as but not limited to a phone a tablet a wearable device and the like.

At the storage interface manager translates the storage operation from the first format to a second format associated with the legacy API. In other words the storage interface manager includes a plug in to interact with the legacy storage via the legacy API of the legacy storage s environment.

According to an embodiment at the storage interface manager searches an index that is maintained separately from the legacy storage to at least partially resolve the storage operation. Also the storage interface manager uses data gathered from the index to translate the storage operation to the second format. So the storage interface manager can include other processes that monitor and index the legacy storage where the index can reside within the processing environment of the storage interface manager and does not have to reside in the legacy storage environment. This permits enhancements on the legacy storage as well that can be implemented and deployed by the storage interface manager independent of the legacy API of the legacy storage.

In another case at the storage interface manager integrates security procedures maintained by an environment of the legacy storage with the storage operation in the second format. So any security required by the legacy storage s environment can be provided for checking with the storage operation in the second format.

Similar to and at the storage interface manager integrates auditing procedures maintained by the legacy storage s environment with the storage operation in the second format. Thus auditing required by the legacy storage s environment can be represented in the storage operation within the second format.

In an embodiment at the storage interface manager recognizes the first format as a REST format and the second format as a particular format or API used to access traditional mounted or mapped storage drives. So the legacy storage can be associated with mounted or mapped storage and can use mapped and mounted APIs and protocols whereas the user provides storage commands in a mobile REST format and the storage interface manager acts as an intermediary to enable the legacy storage for remote network access.

At the storage interface manager sends the storage operation in the second format to the legacy storage for processing. The storage operation in the second format can be substantially different from the original storage operation provided in the first format. This is so because some of the processing can be done by the storage interface manager and some other processing may have to be added to the second format by the storage interface manager.

In an embodiment at the storage interface manager communicates the storage operation in the second format via a legacy storage protocol used by the legacy storage.

According to an embodiment at the storage interface manager receives results back associated with the legacy storage processing the storage operation in the second format.

Continuing with the embodiment of and at the storage interface manager translates the results to the first format and sends the translated results in the first format to an initial requestor that sent the storage operation in the first instance. This too can be achieved via a REST interface that the storage interface manager interacts with the requestor with.

In an embodiment at the storage interface manager indexes the legacy storage and maintains an index to the legacy storage from an environment associated with the legacy storage. This was discussed above at and is discussed below as well with the discussion of the .

The storage controller presents another and in some cases enhanced perspective of the storage interface manager presented above in detail with respect to the .

At the storage controller processes storage commands provided in a first format and associated with mobile devices. The storage commands are directed to a legacy storage environment that does not recognize and that cannot natively process the storage commands in the first format. The mobile devices can include phones tablets laptops wearable devices and the like.

At the storage controller interacts with the legacy storage environment while utilizing a second format to at least partially handle the storage commands.

At the storage controller communicates results from interacting with the legacy storage environment to the mobile devices in the first format.

According to an embodiment at the storage controller enhances features associated with the legacy storage environment. These enhanced features are not natively supported by the legacy storage environment. That is the storage controller uses a legacy API associated with the legacy storage environment to offload some processing and to interact with the legacy storage environment to enhance certain aspects of the legacy storage environment.

For example at the storage controller permits users via their mobile devices to publish and to subscribe to notifications associated with the legacy storage environment. In this case users can synch to files or subsets of storage via mobile devices via a notification mechanism provided by the storage controller but not natively provided by the legacy storage environment.

In another case at the storage controller implements custom authentication when processing the storage commands. The custom authentication not associated with the legacy storage environment. So enhanced security can be achieved via the storage controller acting as an intermediary to the legacy storage environment.

In yet another case at the storage controller implements custom auditing when processing the storage commands that are not associated with the legacy storage environment.

Also at the storage controller maintains an index for the legacy storage environment and provides via that index enhanced searching from the index that is not natively available from the legacy storage environment.

In an embodiment the storage enablement system implements inter alia the methods and of the respectively.

The storage enablement system includes memory configured with the storage interface manager . Processors of the storage enablement system executed the storage interface manager . Processing associated with the storage interface manager was described above with respect to the methods and of the respectively.

The storage interface manager is configured to act as an intermediary between client interfaces and legacy interfaces of legacy storage environments for purposes of providing remote access to the legacy storage environments. The client interfaces can include interfaces associated with mobile devices such as REST interfaces.

According to an embodiment the server that implements the storage interface manager is accessible via or as a cloud processing environment which is separate and remote from each of the legacy storage environments.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

