---

title: System and method for consistent embedded search across enterprise applications with an enterprise crawl and search framework
abstract: In accordance with an embodiment, described herein are systems and methods for providing an enterprise crawl and search framework, including features such as use with middleware and enterprise application environments, pluggable security, search development tools, user interfaces, and governance. The system includes an enterprise crawl and search framework which abstracts an underlying search engine, provides a common set of application programming interfaces for developing search functionalities, and allows the framework to serve as an integration layer between one or more enterprise search engine and one or more enterprise application. An application development framework allows an application developer to make searchable view objects that are associated with a plurality of enterprise applications. At runtime, a searchable object manager loads searchable objects from persistent storage, validates the searchable object definitions, and provides the searchable objects to the framework for use in searching across the plurality of enterprise applications.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09361330&OS=09361330&RS=09361330
owner: ORACLE INTERNATIONAL CORPORATION
number: 09361330
owner_city: Redwood Shores
owner_country: US
publication_date: 20130102
---
This application claims the benefit of priority to U.S. Provisional Patent Application No. 61 609 644 titled SYSTEM AND METHOD FOR PROVIDING AN ENTERPRISE CRAWL AND SEARCH FRAMEWORK filed Mar. 12 2012 U.S. Provisional Patent Application No. 61 609 684 titled SYSTEM AND METHOD FOR PROVIDING AN ENTERPRISE CRAWL AND SEARCH FRAMEWORK filed Mar. 12 2012 U.S. Provisional Patent Application No. 61 609 698 titled SYSTEM AND METHOD FOR PROVIDING AN ENTERPRISE CRAWL AND SEARCH FRAMEWORK filed Mar. 12 2012 U.S. Provisional Patent Application No. 61 621 405 titled SYSTEM AND METHOD FOR PROVIDING AN ENTERPRISE CRAWL AND SEARCH FRAMEWORK filed Apr. 6 2012 U.S. Provisional Patent Application No. 61 659 843 titled SYSTEM AND METHOD FOR PROVIDING AN ENTERPRISE CRAWL AND SEARCH FRAMEWORK USER INTERFACE filed Jun. 14 2012 and U.S. Provisional Patent Application No. 61 659 877 titled SYSTEM AND METHOD FOR PROVIDING AN ENTERPRISE CRAWL AND SEARCH FRAMEWORK SECURITY filed Jun. 14 2012 each of which above applications is herein incorporated by reference.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

Embodiments of the invention are generally related to enterprise applications and to systems and methods for providing an enterprise crawl and search framework including features such as use with middleware and enterprise application environments pluggable security search development tools user interfaces and governance.

Enterprise resource planning ERP or enterprise applications are commonly used by larger companies and organizations to run important aspects of their business. A typical enterprise application environment may include a database of business content combined with end user applications such as customer relationship management CRM human capital management HCM and business intelligence BI .

Examples of such environments include Oracle E Business Suite and Oracle Fusion Applications each of which is designed for handling complex business tasks within a large organization.

Organizations have become increasingly interested in greater integration of their business content with their business processes including the use of transaction processing systems or application servers such as Oracle WebLogic or Oracle Fusion Middleware to deliver a higher quality of service in today s increasingly complex business environment. Such organizations can benefit from a richer search experience within their enterprise which in turn requires rethinking traditional search methodologies. For example since those company employees seeking particular information are also likely to have the best knowledge regarding their particular situation it is important that they can obtain the information within that context. These are the general areas that embodiments of the invention are intended to address.

In accordance with various embodiments described herein are systems and methods for providing an enterprise crawl and search framework including features such as use with middleware and enterprise application environments pluggable security search development tools user interfaces and governance.

As described herein in accordance with an embodiment the system includes an enterprise crawl and search framework which abstracts an underlying search engine provides a common set of application programming interfaces for developing search functionalities and allows the framework to serve as an integration layer between one or more enterprise search engines and one or more enterprise application applications. An application development framework allows an application developer to make searchable view objects that are associated with a plurality of enterprise applications. At runtime a searchable object manager loads searchable objects from persistent storage validates the searchable object definitions and provides the searchable objects to the framework for use in searching across the plurality of enterprise applications.

As described above organizations have become increasingly interested in greater integration of their business content with their business processes including the use of transaction processing systems or application servers to deliver a higher quality of service in today s increasingly complex business environment.

In particular today s enterprise search specialists are looking to several important aspects of enterprise searching for use with their systems including 

To address this in accordance with an embodiment described herein are systems and methods for providing an enterprise crawl and search framework ECSF including features such as use with middleware and enterprise application environments pluggable security search development tools user interfaces and governance.

In accordance with an embodiment the enterprise crawl and search framework can be used with environments such as Oracle Fusion Applications and or Oracle WebLogic application server or other enterprise application and computing environments to consolidate business content information and enable transactional search in a business context.

In accordance with an embodiment the enterprise crawl and search framework includes an open architecture that supports different types of search engine in a plug and play manner e.g. the use of Oracle Secure Enterprise Search SES or another open source or proprietary search engine. An administrator can add define configure and change search engines define repositories to be supported and administer external repositories such as defining their location defining and configuring connectors indexing external data and defining parameters related to federated search.

In accordance with an embodiment the enterprise crawl and search framework can support features such as searching across different objects that have 1 1 1 M M 1 or M M relationships with each other as defined by the organization s business process and the use of searchable objects which allow users to control which objects can be exposed and made searchable.

In accordance with an embodiment which uses Fusion Applications the enterprise crawl and search framework can be provided as part of an integrated environment that includes the framework itself one or more search engines that provides the fundamental search capability that includes indexing querying and security and a source system such as a relational database which stores searchable business content or other information.

In accordance with various embodiments described herein some of the features and advantages of the enterprise crawl and search framework include 

In accordance with an embodiment the enterprise crawl and search framework includes a searchable object manager component a search designer component a runtime e.g. managed bean Mbean component a semantic engine component a command line administration utility component and one or more security service data service and query service . Each of the above components is described in further detail below.

In accordance with an embodiment the enterprise crawl and search framework integrates with an enterprise search engine e.g. SES which provides capabilities for crawling and indexing metadata and objects exposed by the framework. In accordance with an embodiment the enterprise search engine can include one or more security plugin component crawler plugin component and search federation component . Each of the above components are also described in further detail below.

In accordance with an embodiment each enterprise application can include a search user interface UI and an application repository .

In accordance with an embodiment the enterprise search environment including the enterprise crawl and search framework can be accessed by a developer or another user using an application development framework e.g. Oracle JDeveloper and by an administrator or another user using an administration system e.g. Oracle Fusion Applications Control or Oracle Enterprise Manager .

In accordance with an embodiment the searchable object manager component serves as a metadata manager manages searchable objects and provides the runtime interface for accessing these objects. At runtime the searchable object manager loads searchable objects from persistent storage validates the searchable object definitions and provides the searchable objects to a crawlable factory component of the data service. In accordance with an embodiment the searchable object manager is also responsible for the lifecycle management of the searchable objects which allows administrators to deploy customize and enable or disable searchable objects via the command line administration utility component or the administration system.

In accordance with an embodiment the search designer component can be provided e.g. as a page in JDeveloper including an interface for defining metadata that describes the business objects to be indexed. A developer or another user can use this design interface to specify the security mechanism to be used to protect the data and to define the searchable object search characteristics which include advanced search faceted navigation and actionable results.

In accordance with an embodiment the semantic engine component leverages the semantic information of searchable object definitions to create context around the search by interpreting searchable object definitions with relation to the runtime user information during both crawl and query time.

In accordance with an embodiment the administration system can be provided e.g. as an Enterprise Manager extension that provides a user interface for registering searchable objects in the framework schema of e.g. the Fusion Applications database as well as for administering the runtime parameters of the framework the target search engine and the configuration of parameters.

In accordance with an embodiment the command line administration utility component is a standalone command line interface that provides a user interface for registering searchable objects in the framework schema of e.g. the Fusion Applications database. A developer administrator or other user can also use the command line administration utility to configure and administer the framework without external dependencies on the administration system.

In accordance with an embodiment the security service component is responsible for providing security information to the search engine. During query time the security service retrieves the security keys of the user performing the search and passes those keys to the search engine where they are used to filter the query results.

In accordance with an embodiment the security service server component is also invoked during crawl time to add security information access control lists ACL to data before inserting or creating indexes on the search engine. An ACL identifies the users who can access an associated object and specifies the user s access rights to that object. The ACL values generated by the security service during crawl time should match the corresponding keys generated during query time.

In accordance with an embodiment the security service component is implemented as a security engine with a plug in interface. The security plug in determines the format of the ACL keys. For custom security models a new custom security plug in can be implemented. In accordance with an embodiment the security service can use e.g. Oracle Platform Security for Java to authenticate users and call the security plug in to retrieve security values for a given searchable object.

In accordance with an embodiment the data service component is the primary data interface between the enterprise crawl and search framework and the search engine. In accordance with an embodiment the data service can use a proprietary Really Simple Syndication RSS feed format. In addition to supporting the flow of metadata between the framework and the search engine the data service can support attachments batching and error handling.

In accordance with an embodiment the data service authenticates each search engine crawl request by using e.g. Platform Security for Java to validate the user credentials and permissions for crawling the data source. A crawlable factory component which is part of the data service determines how searchable objects are broken down and manages the construction of RSS feeds to the search engine.

In accordance with an embodiment the query service component provides a search interface for the enterprise application s search user interface UI and handles all search requests. In accordance with an embodiment the query service performs query rewrite parameter substitution and other preprocessing operations before invoking the underlying configured search engine. Search results are also serviced via this service. Hooks can be provided to preprocess and postprocess data which facilitates the capability to filter search results.

In accordance with an embodiment the search engine component e.g. SES enables a secure uniform search across multiple enterprise repositories. The enterprise crawl and search framework integrates with the search engine to provide full text search functionality in enterprise applications e.g. Fusion Applications .

Some search engines such as SES provide an API for writing security plug ins or connectors e.g. in Java which allows a developer to provide a security plug in to meet their requirements. In accordance with an embodiment the enterprise crawl and search framework can interface with this security plug in. The security plug in invokes the security service to retrieve keys to which the user has access for filtering the results that are delivered to the query service. In accordance with an embodiment a proxy user must be set up on the search engine in order to invoke the security service and must have security privileges for the enterprise applications e.g. Fusion Applications .

In accordance with an embodiment the crawler plug in component is a search engine module that implements the modified RSS feed format between the enterprise crawl and search framework and the search engine. In accordance with an embodiment the crawler plug in component deserializes data communicated by the framework via the data service component and interfaces with the search engine components that create the indexes.

In accordance with an embodiment the search federation component provides support for the user of federated search engine instances.

As shown in in accordance with an embodiment a business intelligence BI server environment such as an Oracle Business Intelligence environment using WebLogic application server can include a BI server and a web services component that provides access to a BI web catalog of business content data or other information .

In accordance with an embodiment one or more BI applications can include an enterprise crawl and search framework API which allows a developer or other user using an application development framework and or administration system to configure the BI application s to take advantage of the enterprise crawl and search framework including leveraging the enterprise search engine search instances and search engine database to provide full text search functionality across the applications.

In accordance with an embodiment a system including the enterprise crawl and search framework can include support for consistent embedded search across enterprise applications.

In accordance with an embodiment in addition to providing search against enterprise crawl and search framework data sources i.e. view object based data sources deployed via an ECSF administration utility and data sources that are crawled via ECSF the framework also supports search against registered data source groups that contain external data sources.

In accordance with an embodiment such external data sources can include data sources such as Intranet mail database and federated data sources data sources crawled in separate engine instances . Searchable data source groups can also contain federated ECSF data sources data sources created in different logical engine instances via the ECSF administration tools .

In accordance with an embodiment the ECSF synchronizes categories with the data source groups provided by the enterprise search engine the data sources themselves are not synchronized.

The above described process flows are provided for purposes of illustration. In accordance with other embodiments other process flows to support consistent embedded search across enterprise applications or support the use of an enterprise crawl and search framework with external data can also be provided.

At step an enterprise application e.g. Fusion Applications developer or other user uses an application development framework e.g. JDeveloper to create searchable objects.

At step an enterprise application administrator or other user deploys searchable objects to the ECSF runtime environment by registering them in an enterprise application database.

At step the search engine crawls the searchable objects in the enterprise application and indexes the searchable objects as documents.

At step upon receiving a search query from an enterprise application user the ECSF performs the query applies enterprise application specific rules sends the query to the search engine and applies post query security rules to construct search hits and render the search results as a UI to be returned to the user.

The present invention may be conveniently implemented using one or more conventional general purpose or specialized digital computer computing device machine or microprocessor including one or more processors memory and or computer readable storage media programmed according to the teachings of the present disclosure. Appropriate software coding can readily be prepared by skilled programmers based on the teachings of the present disclosure as will be apparent to those skilled in the software art.

In some embodiments the present invention includes a computer program product which is a non transitory storage medium or computer readable medium media having instructions stored thereon in which can be used to program a computer to perform any of the processes of the present invention. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs microdrive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs VRAMs flash memory devices magnetic or optical cards nanosystems including molecular memory ICs or any type of media or device suitable for storing instructions and or data.

The foregoing description of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Many modifications and variations will be apparent to the practitioner skilled in the art.

In particular it will be evident that although many of the examples described above illustrate the use of an enterprise crawl and search framework within an environment that includes an Oracle Fusion Applications enterprise application and an Oracle Secure Enterprise Search enterprise search engine in accordance with various embodiments the enterprise crawl and search framework and features and methods described can be used with other types of enterprise application and other types of enterprise search engine.

The embodiments were chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalence.

