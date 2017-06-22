---

title: Conversion tracking and context preserving systems and methods
abstract: When a server receives a request for an information payload from a remote device, the server may determine the device's type and identify an optionally-installable application that can be used to access the information payload on devices of that type. When the optionally-installable application is not installed on the remote device, the server may store a identifier for the remote device and send the device a redirection message via which the device can obtain and install the application. Subsequently, when the server receives an installation indication from the application executing on a remote device, the server may identify the device as having recently been redirected to install the application and store or update a record indicating that an application-installation event occurred.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09363337&OS=09363337&RS=09363337
owner: Yahoo! Inc.
number: 09363337
owner_city: Sunnyvale
owner_country: US
publication_date: 20130813
---
This application is a continuation in part of U.S. patent application Ser. No. 13 855 649 filed Apr. 2 2013 titled REMOTE APPLICATION INVOCATION SYSTEM AND METHOD and naming inventor Jesse Chor. U.S. patent application Ser. No. 13 855 649 is a continuation of U.S. patent application Ser. No. 12 852 730 now U.S. Pat. No. 8 438 245 filed Aug. 9 2010 titled REMOTE APPLICATION INVOCATION SYSTEM AND METHOD and naming inventor Jesse Chor. This application is also a continuation in part of U.S. patent application Ser. No. 13 855 641 filed Apr. 2 2013 titled SMART LINK SYSTEM AND METHOD and naming inventor Jesse Chor. U.S. patent application Ser. No. 13 855 641 is a continuation of U.S. patent application Ser. No. 13 036 950 now U.S. Pat. No. 8 433 800 filed Feb. 28 2011 titled SMART LINK SYSTEM AND METHOD and naming inventor Jesse Chor. The above cited applications are hereby incorporated by reference in their entireties for all purposes.

This disclosure is directed to software and more particularly to systems and methods by which a server device can track and provide context for application installations on remote client devices.

An application store also commonly referred to as an app store app marketplace or the like is a type of digital distribution platform for application software that users may opt to install on devices of a particular type. In recent years application stores have become a common component on personal computers smartphones tablets and the like.

Application providers typically write an optionally installable application for a given type of device and submit the application to an application store provider which makes the application available for users to purchase and or download via an application store.

Once a user has installed such an application on a given device the device may be able to use the application to access information payloads provided by the application provider and or by third parties. In many cases an application provider may also provide a website that can be used to access at least some of the same information payloads that can be accessed by an optionally installable application.

For example a content provider such as a blogging platform social network news portal or the like may provide a website by which posts articles or other information payloads may be accessed by web browser software executing on remote devices. That content provider may also provide an optionally installable application that can be obtained from an application store and once installed used to access some or all of the same posts articles or other information payloads.

In many cases such a content provider may wish to promote its optionally installable application for various reasons e.g. a native application may provide a superior user experience than a website the content provider may earn revenue when users obtain and use its optionally installable application or the like . To that end many content providers detect when a visiting device is of a type for which an optionally installable application is available so that their websites may notify the visitor that an optionally installable application is available and or encourage the visitor to obtain an optionally installable application.

However such app promotion activities can detract from the user s experience with a given content provider. For example in one common scenario a user may encounter a link that purports to identify an information payload e.g. an amusingly captioned photograph of an adorable kitten that the user wishes to view or otherwise consume. Upon following the link to a content provider s website the user is presented not with an amusing and adorable kitten photograph but with a notification indicating that the content provider has published an application available on the user s device.

If the user decides not to install the application then the user may proceed to view the desired photograph in the device s web browser being thereby amused by the cleverness of the caption and or the adorableness of the kitten but being deprived of whatever benefits the native application may provide.

On the other hand if the user decides to obtain and install the application the application typically does not know that the user was trying to access a particular photograph or other resource often forcing the user to search for or independently navigate to the desired photograph from within the application. This is but one common scenario in which a content provider s application promotion may hinder a user s ability to consume a desired information payload.

In an effort to address some of the shortcomings of previous application promotion methods in recent versions of the iOS operating system provided by Apple Inc. of Cupertino California the Safari web browser includes a Smart App Banner feature. When the user visits a given page that has an apple itunes app meta tag a Smart App Banner will automatically determine whether an indicated application is available for and installed on the user s device. When the indicated application is not installed on the user s device tapping on the banner will opens the application s entry in the iOS App Store.

After the application is installed if the user returns to the same page in the Safari web browser tapping the banner will open the installed application and the Safari web browser will pass to the application an URL indicated in the apple itunes app meta tag of the page that the application can use to present an appropriate resource to the user.

However if the user launches the application from the iOS App Store from the iOS Home Screen from the iOS Spotlight Search or via any other means the application has no previously known method to determine for example that the user installed the application while attempting to access a particular web page.

In various embodiments as discussed below various systems and methods may be employed to track and provide context for application installations on remote client devices.

The phrases in one embodiment in various embodiments in some embodiments and the like are used repeatedly. Such phrases do not necessarily refer to the same embodiment. The terms comprising having and including are synonymous unless the context dictates otherwise.

Reference is now made in detail to the description of the embodiments as illustrated in the drawings. While embodiments are described in connection with the drawings and related descriptions there is no intent to limit the scope to the embodiments disclosed herein. On the contrary the intent is to cover all alternatives modifications and equivalents. In alternate embodiments additional devices or combinations of illustrated devices may be added to or combined without limiting the scope to the embodiments disclosed herein.

In various embodiments network may include the Internet a local area network LAN a wide area network WAN and or other data network.

In various embodiments additional infrastructure e.g. cell sites routers gateways firewalls and the like as well as additional devices may be present. Further in some embodiments the functions described as being provided by some or all of installation detection server application provider and or application store may be implemented via various combinations of physical and or logical devices. However it is not necessary to show such infrastructure and implementation details in in order to describe an illustrative embodiment.

In various embodiments installation detection server may comprise one or more physical and or logical devices that collectively provide the functionalities described herein. In some embodiments installation detection server may comprise one or more replicated and or distributed physical or logical devices.

In some embodiments installation detection server may comprise one or more computing services provisioned from a cloud computing provider for example Amazon Elastic Compute Cloud Amazon EC2 provided by Amazon.com Inc. of Seattle Wash. Sun Cloud Compute Utility provided by Sun Microsystems Inc. of Santa Clara Calif. Windows Azure provided by Microsoft Corporation of Redmond Wash. and the like.

Installation detection server includes a bus interconnecting several components including a memory a network interface an optional display and a central processing unit .

Memory generally comprises a random access memory RAM a read only memory ROM and a permanent mass storage device such as a disk drive. The memory stores program code for a routine for generating a unique URL see discussed below a routine for processing a resource request see discussed below and a routine for processing an application installation indication see discussed below . In addition the memory also stores an operating system

These and other software components may be loaded into memory of installation detection server using a drive mechanism not shown associated with a non transient computer readable medium such as a floppy disc tape DVD CD ROM drive memory card or the like.

Memory also includes database . In some embodiments installation detection server may communicate with database via network interface a storage area network SAN a high speed serial bus and or via the other suitable communication technology.

In some embodiments database may comprise one or more storage services provisioned from a cloud storage provider for example Amazon Simple Storage Service Amazon S3 provided by Amazon.com Inc. of Seattle Wash. Google Cloud Storage provided by Google Inc. of Mountain View Calif. and the like.

Beginning the illustrated sequence of communications client computing device sends to installation detection server a request for a resource identified by a unique URL that was previously generated by installation detection server according to a routine such as routine shown in . In many cases the request may be sent by a web browser application executing on client computing device .

In many embodiment request may conform to the Hypertext Transfer Protocol HTTP application protocol according to which request may include metadata values associated with several HTTP header fields.

Installation detection server determines a device type of the requesting device and identifies the requesting device. In the illustrated scenario installation detection server identifies the requesting device via a fingerprint identifier based at least in part on metadata associated with the resource request that is likely to distinguish the requesting device from most or all other devices.

As discussed above the request may conform to the HTTP protocol which defines many standard HTTP header fields and many other non standard request headers are commonly employed. In various embodiments some or all of the HTTP header field values provided when the client computing device makes a request may be processed along with additional request metadata to create a fingerprint of the request. Such fingerprint identifiers are discussed further in relation to block of below.

Installation detection server processes the request including identifying a destination URL associated with the unique URL and identifying an installable application associated with the previously generated unique URL and the destination device type.

Installation detection server determines that the installable application is not installed on the requesting device. For example in one embodiment installation detection server may provide to client computing device a piece of executable code e.g. a JavaScript function for execution on client computing device that may report to installation detection server whether the device can handle a URL or URI scheme that is associated with the installable application in question.

The generic syntax for URI schemes is defined in Request for Comments RFC memorandum published by the Internet Engineering Task Force IETF . According to RFC 3986 a URI including a URL consists of four parts 

A URI begins with a scheme name that refers to a specification for assigning identifiers within that scheme. The scheme name consists of a letter followed by any combination of letters digits and the plus period . or hyphen characters and is terminated by a colon .

The hierarchical portion of the URL is intended to hold identification information that is hierarchical in nature. Often this part is delineated with a double forward slash followed by an optional authority part and an optional path.

The optional query portion is delineated with a question mark and contains additional identification information that is not necessarily hierarchical in nature. Together the path part and the query portion identify a resource within the scope of the URI s scheme and authority. The query string syntax is not generically defined but is commonly organized as a sequence of zero or more pairs separated by a semicolon or ampersand for example 

Much of the above information is taken from RFC 3986 which provides additional information related to the syntax and structure of URIs. RFC 3986 is hereby incorporated by reference for all purposes.

Installation detection server records contextual metadata associated with the request including information such as some or all of the following the identified destination URL a date and or time at which the request was received the requesting device fingerprint an application identifier associated with the installable application and the like.

Installation detection server assembles a redirection message that will allow the requesting device to obtain the installable application. There are many well known methods of providing a redirection message including using HTTP redirection status codes e.g. and the like using a Refresh meta tag or HTTP refresh header using a JavaScript redirect and the like.

A typical redirection message that will allow the requesting device to obtain the installable application may include an application identifier that identifies the installable application in question to application store .

In some embodiments the redirection message may include a compound URL such as described in U.S. Pat. No. 8 433 800 incorporated herein . See also subroutine shown in discussed below .

Acting upon the redirection message client computing device sends to application store a request for the installable application.

Application store processes the request and sends to client computing device the installable application .

When the installable application is run after being installed it is configured to cause client computing device to send to installation detection server an installation indication indicating that the installable application was installed on client computing device . In the illustrated scenario the installation indication further requests a context to present to the user such as a resource that the user has recently evidenced a desire to consume.

Installation detection server determines a device type of the requesting device and identifies the requesting device. In the illustrated scenario installation detection server identifies the requesting device via a fingerprint identifier based at least in part on metadata associated with the resource request that is likely to distinguish the requesting device from most or all other devices.

As discussed above the request may conform to the HTTP protocol which defines many standard HTTP header fields and many other non standard request headers are commonly employed. In various embodiments some or all of the HTTP header field values provided when the client computing device makes a request may be processed along with additional request metadata to create a fingerprint of the request. Such fingerprint identifiers are discussed further in relation to block of below.

Installation detection server matches the just determined fingerprint with the recently recorded fingerprint discussed above.

Having received an installation indication from a device that can be matched to a recent unique URL request and that was recently redirected to application store installation detection server infers that the installable application was installed in response to the redirection and records e.g. in database an application installation event associated with client computing device and or the previously generated unique URL.

Installation detection server obtains the recently recorded destination URL that is associated with the recent unique URL request sent by client computing device .

Installation detection server assembles a redirection message that will allow the installable application executing on client computing device to obtain the resource identified by the destination URL.

Client computing device sends to application provider a request for the resource identified by the destination URL.

Application provider processes the request and sends to client computing device the requested resource .

The installable application executing on client computing device presents the resource that is associated with the unique URL that client computing device requested e.g. via a web browser application before the installable application was installed on client computing device .

Installation detection server sends to application provider a report indicating that client computing device or a device of client computing device s type installed the installable application after requesting the unique URL.

In block routine obtains an identifier e.g. a URL identifying an information payload such as a web page media content or the like. In some cases the identifier may be obtained from a content provider and the information payload may be an asset provided by that content partner.

In block routine determines one or more device types to which the information payload may be delivered. In some cases a different payload or a differently formatted payload may be delivered to different device types. Additional disclosure about generating a unique URL that can be used to access device type specific information payloads may be found in U.S. Pat. No. 8 438 245 incorporated herein .

In decision block routine determines whether an optionally installable application can be used to access the information payload on the current device type. Typically the content provider or other entity that provided the information payload as obtained in block may provide an identifier identifying an optionally installable application that can be used to access the information payload on the current device type. If such an identifier was provided routine proceeds to block . Otherwise routine proceeds to ending loop block .

In block routine associates the optionally installable application determined in decision block with the information payload as obtained in block e.g. by storing or updating a record in database .

In ending loop block routine iterates back to opening loop block to process the next device type as determined in block if any.

In block routine stores e.g. in database the information payload and or an identifier identifying the information payload.

In block routine stores the unique URL as generated in block and provides it for exposure to remote computing devices. As discussed further in U.S. Pat. No. 8 438 245 incorporated herein in various embodiments the previously generated unique URL may be exposed to remote computing devices in a number of forms including as a 2 d barcode or other machine scannable code as a link published via a web site or otherwise included in an HTML or similar document or the like.

In block routine receives from a remote computing device a request for a unique URL that was previously generated according to a method such as that shown in discussed above. In some embodiments the request may conform to the HTTP protocol.

In block routine identifies a device type of the remote computing device. For example in one embodiment metadata associated with an HTTP request such as a User Agent header or the like may be used to determine a device type of the remote computing device.

In subroutine block routine calls subroutine see discussed below to determine an identifier that can be used to distinguish the requesting remote computing device from some or all other remote computing devices that may interact with routine .

In block routine identifies an information payload associated with unique URL. For example in one embodiment routine may locate a record in database that was previously keyed to or otherwise associated with the previously generated unique URL such as described in connection with block of above .

In block routine identifies an optionally installable application that can be used to access the information payload on the requesting device. For example in one embodiment routine may locate a record in database that was previously keyed to or otherwise associated with the unique URL such as described in connection with block of above .

In decision block routine determines whether the optionally installable application as identified in block is installed on the requesting remote computing device. For example in one embodiment routine may provide to the remote computing device a piece of executable code e.g. a JavaScript function for execution on the remote computing device that may report to routine whether the device can handle a URL or URI scheme that is associated with the optionally installable application as identified in block .

If the optionally installable application is determined to be installed routine proceeds to block . Otherwise routine proceeds to block .

In block routine obtains an identifier by which the remote computing device may launch the optionally installable application that was determined in decision block to be installed to access the information payload.

In block routine obtains an identifier by which the remote computing device may obtain and install the optionally installable application that was determined to be not installed on the requesting remote computing device.

In either case routine may obtain an appropriate identifier by locating a record in database that was previously keyed to or otherwise associated with the unique URL such as described in connection with block of above .

In subroutine block routine calls subroutine see discussed below to generate a redirection message by which the remote computing device can launch and or install the optionally installable application according to the application identifier obtained in block or block .

In block routine provides to the remote computing device the redirection message as generated in subroutine block .

In block routine stores and or updates a record e.g. in database indicating that at the current date and or time the remote computing device as identified in subroutine block requested the information payload as identified in block and was redirected according to the redirection message as generated in subroutine block .

In various embodiments various methods may be available to identify a given remote computing device to at least some degree of certainty. Three common methods are described below in an alternative decision tree. However in many cases a given embodiment may be configured to use a particular method without evaluating whether the other alternatives are available.

In some embodiments a given remote computing device may be configured to provide a unique serial number or other device identifier to subroutine upon request. In decision block subroutine determines whether the remote computing device will provide such a unique identifier. If so subroutine proceeds to block .

In block subroutine requests and obtains a unique serial number or other device identifier from the given remote computing device. In many embodiments such a unique serial number or other device identifier may definitively distinguish the given remote computing device from all other devices.

In some embodiments subroutine may be configured to integrate with a third party entity such as a mobile network operator wireless service provider wireless carrier or the like that is able to identify the given remote computing device using an identifier such as an International mobile Subscriber Identity IMSI International Mobile Station Equipment Identity IMEI MSISDN or the like. In decision block subroutine determines whether such a third party will identify the given remote computing device. Or alternately in some embodiments subroutine may be executing on a device operated by such an entity. If so then subroutine proceeds to block .

In block subroutine obtains the third party provided unique identifier. In many embodiments such an identifier may definitively distinguish the given remote computing device from all other devices.

Otherwise if no definitive identifier is obtainable in block subroutine obtains metadata associated with the given remote computing device and or the given request.

In many embodiments the given request may conform to the HTTP protocol which defines many standard HTTP header fields. Additionally many non standard request headers are commonly employed. In such embodiments subroutine may obtain metadata values provided via HTTP header fields as well as additional metadata such as a current date and or time.

In block subroutine determines a non necessarily unique device fingerprint identifier based on metadata as obtained in block . In various embodiments some or all of the HTTP header field values provided when the given remote computing device makes the given request may be processed possibly along with additional request metadata e.g. a current date and or time to create a fingerprint of the request.

For example in one embodiment an IP address associated with the client computing device may be combined with the value of a User Agent HTTP request header to create a request fingerprint that while it may not uniquely identify the client computing device may distinguish requests made by the client computing device from requests made by most other devices.

To combine metadata into a request fingerprint subroutine may employ techniques such as concatenating the metadata values and or processing the metadata values via a cryptographic hash function.

Subroutine ends in ending block returning to the caller the identifier obtained or determined in block block or block .

In block subroutine determines a resource URL associated with the given information payload. In some embodiments the resource URL may be suitable for accessing the information payload via a general purpose web browsing application. In other embodiments the resource URL may be suitable for accessing the information payload via the given optionally installable application on one or more computing platforms.

In block subroutine determines an application URL associated with a given optionally installable application that can be used to access the information payload. In some cases the application URL may include a URL scheme that is associated with the given optionally installable application on one or more types of computing devices such that resolving the application URL on such a device will invoke the optionally installable application to access the information payload.

In other cases the application URL may identify the given optionally installable application within an application store on a particular computing platform such that resolving the application URL on a certain type of device will invoke an application store application to obtain and install the optionally installable application.

In block subroutine designates either the application URL or the resource URL as a host URL and the other as a alternative URL. Generally providing a compound URL may allow a remote device to access the information payload via an optionally installable application if the optionally installable application is installed or to obtain the optionally installable application if it is not installed.

In some embodiments when processing a compound URL a computing device may be configured to attempt to resolve the alternative URL first falling back to the host URL if the alternative URL cannot be resolved e.g. because an optionally installable application is not installed . In other embodiments a computing device may be configured to attempt to resolve the host URL first falling back the alternative URL if the host URL cannot be resolved.

In some embodiments subroutine may designate the host URL and the alternative URL such that a computing device of a certain type will first attempt to resolve the resource URL to invoke the optionally installable application to access the information payload falling back to the application URL to obtain and install the optionally installable application if invoking the optionally installable application fails.

In block subroutine obtains a predetermined alternative URL key. As discussed further in U.S. Pat. No. 8 433 800 incorporated herein in various embodiments subroutine may obtain a key such as appURI or altURI to indicate the presence of a alternative URL within a compound URL.

In block subroutine inserts a alternative URL key value pair into the host URL to form a compound URL. In various embodiments inserting the alternative URL key value pair may include percent encoding the alternative URL or otherwise encoding the alternative URL such that it can be validly represented within the query portion of the host URL according to the scheme named in the host URL.

In various embodiments an optionally installable application may be configured to contact installation detection server when the optionally installable application is launched after being installed on a remote computing device. In block routine receives such an installation indication from an optionally installable application installed and executing on a remote computing device. In various embodiments receiving the installation indication may include receiving a request for a first run resource identified by a predetermined URL receiving a message and or data via a web application programming interface or the like.

In subroutine block routine calls subroutine see discussed above to determine an identifier that can be used to distinguish the installation indicating remote computing device from some or all other remote computing devices that may interact with routine .

In decision block routine determines whether the remote computing device as identified in subroutine block recently requested an information payload via a unique URL as described in connection with block see discussed above .

For example in one embodiment routine may locate a record in database that was previously keyed to or otherwise associated with the remote computing device as identified in subroutine block such as described in connection with block see discussed above .

If in decision block routine determines that the remote computing device as identified in subroutine block recently requested such an information payload then routine proceeds to decision block . Otherwise routine proceeds to ending block .

In decision block routine determines whether upon requesting the information payload the remote computing device as identified in subroutine block was redirected with a message enabling the remote computing device to obtain and install the optionally installable application as described in connection with block see discussed above .

For example in one embodiment routine may locate a record in database that was previously keyed to or otherwise associated with the remote computing device as identified in subroutine block such as described in connection with block see discussed above .

If in decision block routine determines that it has received an installation indication from a device that can be matched to a recent unique URL request and that was recently redirected to application store routine may infer that the optionally installable application was installed in response to the redirection in which case routine proceeds to block . Otherwise routine proceeds to block .

In block routine records e.g. in database an application installation event associated with some or all of the remote computing device as identified in subroutine block its device type the information payload and or the unique URL.

In block routine provides the previously requested information payload for presentation on the remote computing device via the installed and executing optionally installable application.

Although specific embodiments have been illustrated and described herein it will be appreciated by those of ordinary skill in the art that alternate and or equivalent implementations may be substituted for the specific embodiments shown and described without departing from the scope of the present disclosure. This application is intended to cover any adaptations or variations of the embodiments discussed herein.

