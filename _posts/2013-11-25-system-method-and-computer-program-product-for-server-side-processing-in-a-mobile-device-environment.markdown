---

title: System, method, and computer program product for server side processing in a mobile device environment
abstract: Described herein are systems, methods, computer program products, and combinations and sub-combinations thereof, for enabling web content (as well as other objects) to be loaded on mobile devices (as well as other types of devices), and for users of mobile devices to operate with such web content on their mobile devices in an interactive manner while in an off-line mode.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09456048&OS=09456048&RS=09456048
owner: IANYWHERE SOLUTIONS, INC.
number: 09456048
owner_city: Dublin
owner_country: US
publication_date: 20131125
---
This application is a continuation of U.S. Non Provisional application Ser. No. 09 705 914 filed Nov. 6 2000 now allowed which is a continuation in part application of U.S. Non Provisional application Ser. No. 09 559 964 filed Apr. 28 2000 now U.S. Pat. No. 6 779 042 issued Aug. 17 2004 which is a continuation in part application of U.S. Non Provisional application Ser. No. 09 393 390 filed Sep. 10 1999 and claims the benefit of U.S. Provisional Application No. 60 173 807 filed Dec. 30 1999 now expired and U.S. Provisional Application No. 60 189 969 filed Mar. 17 2000 now expired all of which are incorporated by reference herein in their entireties.

The present invention relates generally to mobile communications and more particularly relates to technology for using interactive applications while on line and off line on mobile devices.

A variety of mobile devices such as personal data assistants or PDAs exist. Such mobile devices include ones based on the Palm operating environment and the Windows CE operating environment.

What does not exist prior to the invention are software applications for enabling web content as well as other objects to be loaded on mobile devices and for users of mobile devices to operate with such web content on their mobile devices in an interactive manner while in an off line mode.

Briefly stated the invention includes systems methods computer program products and combinations and sub combinations thereof for enabling web content as well as other objects to be loaded on mobile devices as well as other types of devices and for users of mobile devices to operate with such web content on their mobile devices in an interactive manner while in an off line mode.

These and additional features and advantages of the present invention will become more apparent from the detailed description set forth below when taken in conjunction with the drawings in which like reference characters generally identify corresponding elements throughout.

It should be understood that these figures depict embodiments of the invention. Variations of these embodiments will be apparent to persons skilled in the relevant art s based on the teachings contained herein. For example the flow charts contained in these figures depict particular operational flows. However the functions and steps contained in these flow charts can be performed in other sequences as will be apparent to persons skilled in the relevant art s based on the teachings contained herein.

Briefly stated the invention is directed to placing objects such as but not limited to Internet or Web content on data processing devices such as but not limited to mobile devices. Table 1 lists examples of such Internet content although the invention is not limited to these examples.

The invention includes technology for using applications on mobile devices that interact with the Internet or with intranets. The invention enables applications available via a network or via an Internet intranet to download and to run on mobile devices. Consequently the invention includes software and methods for administering a server that manages the variables relevant to a mobile device server environment.

Mobile devices to operate in conjunction with a Web server even when the mobile devices are not coupled directly to the PC using portable on device servers Web pages are loaded viewed cached and deleted even when the device is not coupled to any network.

Mobile devices to operate in conjunction with the Web Internet or intranet via a connection mechanism and then in disconnected mode or with the Web Internet or intranet in wireless mode with a continuous or a discontinuous connection mechanism.

Fleet management for centrally administering information in a handheld network environment that includes but is not limited to user data user groups group channels channel data personal channels commercial channels user accounts corporate account software groupings personal information management form delivery form management device configuration device databases device contents and devices parameters.

Obtaining updated Web pages and other network objects for use when the mobile device is not communicating with the PC.

To improve efficiency of data exchange between mobile devices and networked content the invention includes an improved communication protocol that collects requests and responses for network objects into a smaller number of protocol such as HTTP requests and responses. The server also determines the nature and the resources of the mobile device. This protocol is represented for example in .

Downstream the data is encoded in a data format called content stream tokenized version of the data and sent to the device. The content stream format creates a tokenized codification of HTML pages that is sent to the device. The device receives the content stream and presents the material on the device. 

The HTML page is encoded into the content stream and sent to the device. The encoding is a mapping of parent and child HTML elements and or resources to alphanumeric values.

The sync operation of the invention includes various synchronization processes that can collect information from the Internet to a server and to the client. In embodiments the usage of the term sync refers to the overall operation of connecting a client to a server for the exchange interaction creation and removal of data.

In one embodiment syncing can be defined as mirroring data on a client and a server such that the data is the same on client and server. In other embodiments syncing can be defined as overwriting data on a client or on a server such that the data on either a client replaces the data on a server and vice versa.

In one embodiment a sync operation involves a user placing a mobile device into an adapter that includes a sync button. The adapter is connected to a server. Upon pressing the sync button the user initiates the sync operations of the present invention which include various synchronization processes specific delivery modes . Thus the term sync is meant to refer to the overall operation of linking a client to a server. Synchronization is meant to refer to the specific process of copying adding filtering removing updating and merging the information between a client and a server. Any number of synchronization processes can be executed during a sync.

Before being sent downstream the data is compared to the data that is known to be on the client and then the client is updated all at once in a one up one down synchronization method which is represented in . The server sets the client to preemptively prepare all device information necessary during the sync. Then the server receives the set of information in a one up fashion. The server collates the information and sends the information in a one down fashion. This optimizes the sync s efficiency and speed. The sync process according to embodiments of the invention is represented in .

When Web content and other network objects pass through the server they are processed to minimize their size and to optimize their delivery to mobile devices for presentation for ease of use for efficiency for size etc.

The invention uses server logic to optimize content. The server assesses the mobile device to optimize web content for the particular device. Factors that the server logic considers when performing this optimization include but are not limited to it is noted that the server may consider subsets of the following depending on the application and implementation 

On the server the graphic is optimized per the state information of the device. If the device sends down the need for the graphic on a page for a device with a display that is 27 cm wide and in grayscale the server sends its best version of a graphic optimized for that environment.

The technology of the invention is extended by tags on HTML pages that identify content that is designed for additional modifications. Any and all bytes processed by the server are potentially examined for compression optimization. The server detects the tag and executes the necessary logic.

The invention is extended by the coupling of devices to the content available at the server web site see the example shown in .

Generally the server maintains a collection of channels. In an embodiment a channel comprises a collection of objects. An object is any entity that can be transferred to a client such as but not limited to content applications services images movies music links etc.

A channel includes a number of properties. At least some of these properties define the objects that the channel includes. Such properties include but are not limited to the following properties of channels may vary depending on the application and or implementation 

A location of a root object such as but not limited to a URL . In an embodiment this root object is included in the channel. An indication of the number of levels below the root object for which to include objects in the channel. For example in an embodiment if this property is equal to 1 level then all objects that are 1 level down from the root object reached by traversing links in the root object are included in the channel. If this property is equal to 2 levels then all objects that are 1 level down from the root object reached by traversing links in the root object and all objects that are 1 level down from those objects reached by traversing links in those objects are included in the channel. Embodiments of the invention allow uneven trees where some branches of the tree extent to a greater number of levels than other branches of the tree. In other embodiments the trees are even or balanced.

A maximum size of the channel. For example if this is set to 500 Kbytes then the aggregate size of the objects in the channel cannot be greater than 500 Kbytes. If the aggregate size of the objects in the channel is greater than this value then embodiments of the invention may delete objects from the channel and or delete portions of objects in the channel.

An indication of whether or not images are to be included in or excluded from objects in the channel and

It is noted that the properties associated with channels may vary from implementation to implementation. Also implementations may employ combinations of the above properties and or properties in addition to the following as will be appreciated by persons skilled in the relevant art s .

The invention includes processes for managing channels including but not limited to adding channels to the collection of channels maintained by the server .

The server offers channels to clients . A user associated with or on behalf of a client may access the server and view the collection of channels. The client via the user for example may then select any combination of the channels in the collection. The server maintains a list of the channels associated with each of the clients .

During a synchronization process the server loads a device with the channels associated with the client . Generally the server does this by obtaining from providers the objects defined by the channels and causing those objects to be stored on the client . Thus during the synchronization process the server will load the client with the selected channels. More particularly the server will load the client with the objects associated with the channels.

The client may process and use those objects when not connected to the server . The invention enables the client to actively interact with the objects and channels.

In one embodiment the client A directly interacts with the server via some transmission medium B which may be any wired or wireless medium using any communication protocol.

In another embodiment the client B indirectly interacts with the server via an adapter . For example the client B may be a mobile device such as a Palm device and the adapter may be a cradle and a computer coupled to the cradle the mobile device is inserted into the cradle . In this instance the adapter presents itself to the server as a client B via client communications module C . When the server sends objects to the adapter the adapter interface module writes those objects to client B. In embodiments adapter interface module can be a Hot Sync Manager an Active Sync etc. It is noted that the invention is not limited to any of the implementation examples discussed herein.

The server includes an administration module a database module a user interface a web synchronization module a server extension module a fleet management module a notification module and a server communication module . Other embodiments of server may include a subset of these modules and or may include additional modules.

The administration module controls and manages the states of the server and the clients . For example the administration module manages and controls groups of clients permissions assigned to clients groups and channels. For example the administration module administers the users clients assigned to groups and the channels associated with users. These and additional functions performed by the administration module are described herein.

The database module controls access to databases associated with the server . The database module maintains information relevant to the clients as well as information relevant to the modules contained in the server . The database module manages information on the collection of channels maintained by server . These and additional functions performed by the database module are described herein.

The user interface is in an embodiment a graphical user interface GUI that enables users and clients to access functions and modules offered by the server . More generally the user interface within server provides access to server and the modules and resources contained therein.

The invention supports various server web sites that are available through any communication medium such as but not limited to the Internet intranets direct dial up links etc. The UI enables such web sites.

The web synchronization module is an application instance of server extension module and controls synchronization of web content to client . The invention may include other synchronization modules which are application instances of server extension module that control synchronization of other types of objects to clients . For example the server may administer a calendar that may be installed on clients . The synchronization of appointments events and or dates on this calendar between clients and the server may be performed by a calendar synchronization module. These and additional functions performed by the server extension module are described herein.

The fleet management module performs functions associated with fleets of clients which are groups of clients . For example fleet management module may perform global or mass operations on groups fleets of clients such as loading or updating an application on groups fleets of clients . Another example of a mass operation is retrieval of information on clients in a fleet such as the free memory in clients in a fleet this would help an organization determine if its clients need a memory upgrade . These and additional functions performed by the fleet management module are described herein.

The server extension interface module enables modules such as third party modules to operate in or work with the server and modules contained in the server . The server extension module presents an API application programming interface . Modules in the server may operate with other devices in the server by conforming to the server API.

For example the web synchronization module and the fleet management module as well as other types of synchronization modules not shown in may interact with databases on the server via the database module by going through the server extension module . The web synchronization module and the fleet management module may not be able to interact directly with the database module for a number of reasons. For example they may support different data formats or simply speak different languages. However they can interact via the server extension module as well as other server modules as long as they conform to the API of the server extension module . This is true of any modules in the server or that interact with the server .

Server communication module enables communication between the server and entities external to the server such as clients adapters providers work stations etc. The server communicates with these entities via communication mediums which may be any type of wireless or wired communication using any protocol. It is noted that multiple server communication modules may execute in a single server . For example in one embodiment server communication module is a TCP IP stack. In another embodiment server communication module is a secure socket layer stack or a compression stack. The invention is not limited to any implementation examples discussed herein. These and additional functions performed by the server communication module are described herein.

The notification module sends objects to clients beyond objects related to channels associated with clients . Such objects could be requested by client in advance. For example a client could ask for a notification when an event happens such as when a stock reaches a target price. When the event occurs the notification module would cause an appropriate notification s object s to be sent to the client . Alternatively the notification module may send objects to clients without any prior explicit request from the client . For example the notification module might send channels to clients when such channels are identified to be similar to those already selected by the clients . Also the notification module might send appropriate notifications objects to the clients when such clients receive email or faxes at the server . In embodiments the notification module transmits such objects to the client immediately when the event occurs during the next synchronization with the client or at some other future synchronization.

An alternative representation of server is shown in . illustrates for example that messages from entities outside of server are received by server extension interface module via server communications modules . Generally such messages represent requests for the server to perform various functions. The server extension module conceptually operates as a dispatcher who routes such messages to other modules contained in the server such as web synchronization module who handles requests to synchronize with web content notification module fleet management module who handles fleet related requests and or third party modules such as other synchronization modules . Thus the invention supports modules generated by third parties to perform various functions. Such modules plug in to the server via the server extension module .

Referring again to the devices may be any type of data processing device. In embodiments of the invention the devices are mobile computing devices although the invention is not limited to these embodiments. In such example embodiments the devices may include but are not limited to handheld computers cellular phones internet enabled phones pagers radios tvs audio devices car audio systems recorders text to speech devices bar code scanners net appliances mini browsers personal data assistants PDAs etc.

In embodiments of the invention the devices include software hardware and or combinations thereof related to client functionality such client functionality is described herein . When a device includes such software hardware and or combinations thereof the device is referred to herein as a client . Accordingly it can be said that the data processing environment includes one or more clients .

Clients each may include a layout and rendering module a forms module a control module a user interface a client extension interface a client interface module a client communications module a JavaScript engine and a database module . Other embodiments of clients may include a subset of these modules and or may include additional modules.

Layout and rendering module controls the processing of data objects on client such as the layout and rendering of data objects on client . For example the layout portion of module obtains information from databases of the client via the database manager and determines where such information should be rendered on the display of the client . Such information may include anything that can be rendered such as but not limited to images text links etc. The rendering portion of module is responsible for drawing items on the display drawing bits to the screen . These and additional functions performed by the layout and rendering module are described herein.

The forms module controls and manages forms. For example in embodiments the forms module manages aspects of off line forms such as HTML forms and or multi page forms. The forms module enables access to and user interaction with forms in some embodiments the forms module via UI enables users of client to directly access forms . The forms module maintains the status of forms. Forms module can also include a forms manager not shown to provide added functionality. These and additional functions performed by the forms module are described herein.

The user interface is preferably a graphical user interface that enables users to interact with client and functions and modules provided by the client . More generally UI controls how functions presented by modules of the client are presented to users. The UI controls how users interact with such functions and modules. It is noted that the functionality of the UI may be distributed. For example portions of the UI may reside in the forms module as well as other modules of client . These and additional functions performed by the user interface are described herein.

The client extension interface enables modules such as third party modules to operate in or work with the client and modules contained in the client . The client extension interface also known as an on device server presents an API application programming interface that is in embodiments common to clients on many architectures.

Modules in the client can work together via the client extension interface . For example the JavaScript engine may decide that it wishes to display a message to the user. To do this the JavaScript engine would work through the client extension interface to cause the UI to display the message to the user. The JavaScript engine may not know how to directly interact with the UI . However as long as both the JavaScript engine and the UI conform to the API of the client extension interface then they can operate together.

Similarly the control module may decide that it needs to store some data in a database. The control module would do this by working with the client extension interface to access the database module to effect such a modification to the databases in the client . These and additional functions performed by the client extension interface are described herein.

The JavaScript engine executes objects written in the JavaScript language that operate on client . As noted the JavaScript engine conforms to the API of the client extension interface and works with the client extension interface to work with other modules in client . These and additional functions performed by the JavaScript engine are described herein.

Although not shown in embodiments of the invention include other engines for executing other types of scripts on client . These other engines can interact with other modules on client as long as the engines conform to the API of the client extension interface .

The database module controls access to databases associated with client . More generally the database manager controls access to resources on the client . For example the control module may interact with the database manager to open an address book in the databases and to write a record to the address book. Alternatively the forms module can interact with the database module to access forms that are stored in the databases. These and additional functions performed by the database module are described herein.

Client communications module enables the client to interact with external entities such as server . In embodiments the client communications module enables TCP IP traffic although the invention is not limited to this example. More generally the client communications module enables communication over any type of communication medium such as wireless wired etc. using any communication protocol such as a pager protocol. These and additional functions performed by the client communications module are described herein. The client interface module enables the client to communicate with adapters . Client interface module optionally links to client communications module in some embodiments to provide functionality for example when the client communications module uses a wireless modem s drivers which are accessed via client interface module . In embodiments the client interface module may be Hot Sync Manager in the Palm operating environment or Active Sync in the Windows CE operating environment or Pilot Link in the Unix operating environment. It is noted that these implementation examples are provided for illustrative purposes only. The invention is not limited to these examples. These and additional functions performed by the client interface module are described herein.

The control module coordinates the activities of the other modules in client so that all the modules share resources properly. For instance control module can determine priorities for shared resources such as processing time accessing memory etc.

Providers are sources of various types of objects such as but not limited to content content providers A applications application providers B services service providers C etc. Providers may also include servers similar to server which may provide objects such as but not limited to content applications services etc. For example and without limitation the application providers B may provide objects relating to without limitation operating system updates changes system upgrades application updates changes etc.

Adapters include an adapter interface module a user interface a database module an adapter synchronization module and a client communications module . Other embodiments of adapters may include a subset of these modules and or may include additional modules.

The adapter synchronization module is involved with synchronization operations between server and clients .

The database module controls access to databases associated with adapter . The database module manages information needed for clients to remain in sync with server . In some embodiments the adapter does not include the database module or the UI i.e. in embodiments where the adapter operates essentially as a pipe as in some embodiments on Unix .

FIG. B illustrates a block diagram of a data processing unit A that can be used to implement the entities shown in . It is noted that the entities shown in may be implemented using any number of data processing units A and the configuration actually used is implementation specific.

Data processing unit A may represent laptop computers hand held computers lap top computers and or any other type of data processing devices. Which type of data processing device used to implement entities shown in is implementation specific.

Data processing unit A includes a communication medium B such as a bus for example to which other modules are attached.

Data processing unit A includes one or more processor s C and a main memory D. Main memory D may be RAM ROM or any other memory type or combinations thereof.

Data processing unit A may include secondary storage devices E such as but not limited to hard drives F or computer program product interfaces G. Computer program product interfaces G are devices that access objects such as information and or software stored in computer program products . Examples of computer program product interfaces G include but are not limited to floppy drives ZIP drives JAZ drives optical storage devices etc. Examples of computer program products H include but are not limited to floppy disks ZIP and JAZ disks memory sticks memory cards or any other medium on which objects may be stored.

The computer program products H include computer useable mediums in which objects may be stored such as but not limited to optical mediums magnetic mediums etc.

Control logic or software may be stored in main memory D secondary storage device s E and or computer program products H.

More generally the term computer program product refers to any device in which control logic software is stored so in this context a computer program product could be any memory device having control logic stored therein. The invention is directed to computer program products having stored therein software that enables a computer processor to perform functions of the invention as described herein.

The data processing unit A may also include an interface J which may receive objects such as data applications software images etc. from external entities N via any communication mediums including wired and wireless communication mediums. In such cases the objects L are transported between external entities N and interface J via signals K M. In other words such signals K M include or represent control logic for enabling a processor or computer to perform functions of the invention. According to embodiments of the invention such signals K M are also considered to be computer program products and the invention is directed to such computer program products.

As described above the technology uses a cross platform strategy for serving and obtaining content requests on and across platforms and processors available to mobile devices. In some embodiments the client enables desktop personal computer PC functionality on mobile devices. For example the client can support dynamic hypertext mark up language DHTML on mobile devices it can support device side interpretation of JavaScript and it can provide secure client secure protocol secure server interaction. It is noted that these examples are mentioned for illustrative purposes only and are not limiting. Addition functions and capabilities are within the scope and spirit of the present invention as will be appreciated by persons skilled in the relevant art s based on the teachings contained herein.

Additionally the client of the invention enables per channel and or per page username and password authentication for transactions e.g. in e commerce applications and or channels digital notarization content hold and deliver technology in connected and disconnected modes and bookmarks. Furthermore the clients i.e. client A and B of the invention enable support for multiple protocols such as mailto and dialto interfaces and DHTML. It is noted that these examples are mentioned for illustrative purposes only and are not limiting. The invention is applicable to other protocols as will be appreciated by persons skilled in the relevant art s based on the teachings contained herein.

In an embodiment the client of the invention integrates with other mobile device applications through methods such as but not limited to cut and paste domain integration of Find and or Search methods and mobile device communication between on device applications and their separate tables of data. For example the client of the invention can invoke a vector graphics display or a word processor or spreadsheet file synced to the device. In one embodiment these features correspond and extend the functionality of pluggable MIME types on server .

In embodiments the client is designed to support the additional Internet document standards HTML 4.0 XHTML 1.0 CSS Cascading Style Sheets and the W3C DOM Document Object Model . It is noted that these examples are mentioned for illustrative purposes only and are not limiting. The invention is applicable to other standards as will be appreciated by persons skilled in the relevant art s based on the teachings contained herein.

Referring to a block diagram illustrating additional modules according to an embodiment of the invention is shown.

Server can include parser module A layout module B and or proxy rendering module C. Modules A C can be implemented in server alone or in combination with other elements or modules such as in combination with clients such functionality can also be performed completely by clients . It is noted that the functionality associated with modules may vary from implementation to implementation. The specific functionality and implementation described herein represent an example embodiment of the invention. Other embodiments will be apparent to persons skilled in the relevant art s based on the teachings contained herein.

Also implementations may employ combinations of the above modules and or employ the functionalities of the above modules as sub modules to other modules of server as will be appreciated by persons skilled in the relevant art s .

In one embodiment parser module A reads the objects on a page such as a Web page. The parser module A separates out the description of each object on the page and generates a tree of objects based on their descriptions and the inherent relationship defined by the descriptions. In one embodiment the tree of objects is compatible with the W3C DOM. Thus in the case of HTML the Web page is a description of content objects using tags attributes and styles. In the case of WML the page is a description of content object using binary data.

In one embodiment layout module B maps the parsed objects of a page and determines how the objects can be positioned and sized or laid out in order to provide a page with similar substance on the mobile device to which it is going to be transmitted. As with the other embodiments of the layout module described herein the layout module B receives display font color and other device configuration information from the proxy render module C.

In a server side layout embodiment layout module B receives the display configuration of the mobile device from proxy render module C. Proxy render module C provides server with the functionality of layout and rendering module in this case either of modules A or B for any number of clients . In one embodiment the proxy render module C provides configuration information from a database which stores previously obtained configuration information. In embodiments described herein the server receives the configuration information from the client . For example server receives the configuration information from layout and rendering module . From this information server is able to operate proxy render module C accordingly and provide data in the proper format. For example in one embodiment the proxy render module C is able to produce byte code in the form of a content stream compatible with the display hardware of device .

As such proxy rendering module C determines the display capabilities of the device to which the content stream is going to be transmitted. Furthermore in one embodiment proxy rendering module C determines information about how particular objects can appear i.e. are positioned on the display of a mobile device from device information stored in database module rather than for a specific device from information provided by client .

Furthermore the functionality of these modules can be implemented on clients . For example the rendering functionality of layout and rendering module can provide the configuration information directly to the layout functionality of the same module. In embodiments modules implemented on the client are designed to operate on relatively small computers and or mobile devices such as those described herein as well as those similarly designed. The combination of functionalities in one module is for illustrative purposes. The combination may be separated and implemented in two separate modules as discussed with respect to server above. These implementations are discussed in more detail below.

Referring to FIG. B a block diagram illustrating an additional module according to an embodiment of the invention is shown.

Client A can include client parser module A. Client parser module A provides functionality similar to parser module A as described herein.

Referring to FIG. B a block diagram illustrating additional modules according to an embodiment of the invention is shown.

Client B can include client parser module B and client interface module B. Client parser module B provides functionality similar to parser module A as described herein. Client interface module B is capable of connecting with providers via communication medium E. Providers as described herein are content providers such as Web sites. Communications medium E may be implemented to augment the connection with server via adapter . For example communications medium E as shown could connect directly to providers via a wireless link in order to obtain updated content from providers or to transmit data to providers .

In one embodiment the parsing functionality added to client via client parser modules A and B allows clients to obtain content directly from providers without server transformation. Some embodiments of this distribution of functionality is discussed below with respect to .

Referring to a diagram illustrating some processing components according to embodiments of the invention is shown.

Content A from a page in the form of objects is parsed by parser module B laid out by layout module C rendered by rendering module D and sent to mobile devices for display in the form of pixel data E. These objects can include but are not limited to tags attributes and style information.

The modules B C and D are similar to the modules discussed in B and B. illustrates the feature of the invention where the method system and computer program product can be configured such that the operations of modules can be performed on server and or clients as well as on adapter as well as combinations thereof.

In the examples of the operational processes of each of modules B C and D are delineated by marker F for parser module B. Similarly marker G delineates the operational processes of layout module C. Marker H shows the operational processes for rendering module D.

In embodiments of the invention the operational processes of these modules as well as the modules themselves can be implemented on either or both the server or the client or adapter . This flexibility allows the invention to optimize the transformation and delivery of content to mobile devices based on the capabilities of the devices and or requirements of users.

Line I illustrates an example implementation where modules B and C are operating on server to perform the functions of parsing and layout. The asterisk of line I shows the transition to client or adapter and thus the operations of module D are performed on client .

Similarly lines J K and L illustrate other possible apportioning of the operational tasks. The markers between the arrows of lines J K and L similarly showing the transition from one of the server to client and or adapter .

In additional embodiments modules on both server and client and adapter can operate in parallel or series on the objects of content A.

Referring to FIG. D an example flowchart relating to structuring interactive content according to an embodiment of the invention is shown.

In step B server receives mobile device and client information describing the capabilities of the client and the device . In one embodiment client sends information regarding the display and memory specifications of the mobile device upon which it is operating.

In step C server parses the pages into a mutable document of content according to the device and client information of step B. In one embodiment parser module A parses the pages into discrete objects.

In step D server determines the rendering parameters of the client and mobile device according to the information obtained in step B. In one embodiment proxy rendering module C provides the rendering parameters of the client and mobile device.

In step E server lays out the document content according to the rendering parameters determined in step D. In one embodiment the parsed objects of a page are assembled and formatted such that the page displayed by the client on the mobile device has the same functional display or presentation as on any other device. In an embodiment layout module B provides common layout services for the server . Similarly layout and rendering module A of provides these services on client A.

In step F server determines the document table and document content to be sent to client so that the client can use the content of the page s . The structure and format of the document table and document content according to embodiments are discussed below.

In step G server compresses the document content preferably on a discrete object by object basis although other embodiments are possible . For example the discrete objects obtained from the parsing of step C are compressed individually in step G.

In step H server encrypts the document content preferably on a discrete object by object basis. For example the discrete objects obtained from the parsing of step C are encrypted individually in step H.

In step I server serializes the document content according to the discrete basis. For example the document content is placed in ordered blocks or sections. In one embodiment the discrete basis may prioritize index or home pages and place them in places in the serialized chain of objects so that they may be readily recalled.

In step J server serializes the document attributes related to the document content according to the discrete basis. In one embodiment the document attributes are placed in a similar order as the document objects in step I. In another embodiment the document attributes are serialized based on the type of objects they respectively identify.

In step K server transmits the serialized document to client A and or adapter for delivery to client B. In one embodiment the serialized document is a content stream transmitted to the device for client . The serialized document can provide an optimized format for delivering content to mobile devices that may not be designed to accommodate the relatively large file formats which PCs are used to handling.

In the above description server is discussed as performing the operations of flowcharts . This is just one embodiment of the invention. Variations of this embodiment will be apparent to persons skilled in the relevant art s based on the teachings contained herein. For example client can perform some or all of the operations of flowchart as discussed below.

Referring to FIG. D an example flowchart M relating to structuring interactive content according to another embodiment of the invention is shown

In step N client as discussed above client is used to refer generically to client A and or client B unless stated otherwise sends a request for pages.

In step Q client receives the requested pages. In one embodiment client B receives the pages directly from providers as shown in FIG. B. In another embodiment client receives the requested pages from the server .

In step R client parses the pages into a mutable document of content. As described above the mutable document allows for better access and storage for the client.

In step S client determines the rendering parameters according to the local render module such as layout and rendering module .

In step T client lays out the document of content according to the rendering parameters determined by the local render module such as layout and rendering module . Such parameters include for example colors supported device screen size font characteristics etc.

In step U client displays the data on the screen. In one embodiment the render module of client puts the pixel data on the screen.

For example the client communications module A receives the pages from server . Client parser module A parses the pages. Layout and rendering module A determines the rendering and layout parameters and forwards the pixel data to the screen. Other examples and embodiments are discussed in detail below.

Similar to the PODS described herein the document data object assembled through the steps of flowcharts and M includes a structure that is advantageous for mobile devices. The document object models DOM of an embodiment of the invention supports Copy On Write which is usually only implemented in hardware. This enables the creation of discretely compressed read only documents for example the pre processed content stream as described herein that can be modified and saved and then loaded and modified incrementally on a discrete basis.

This embodiment allocates data in its final form. In an embodiment read only data in the content stream is as best can be achieved in its final usable form. The data does not have to be duplicated for use as with other types of models. This aspect of the invention is important given the relatively limited resources of mobile devices.

Furthermore this model has a tight memory allocation scheme. In an embodiment memory is allocated in Pools and Arenas that are scoped to the lifetime of the object being allocated. For example documents have a memory scope. When an object whose lifetime is that of a document is allocated it is allocated from the owner document s memory scope.

When the document is destroyed the associated memory scope can be freed immediately. Objects that will exist for the life of a memory scope will be allocated from the scope Arena in an embodiment arena allocated objects cannot be individually freed . In an embodiment objects whose lifetimes are more volatile will be allocated from the scope pool where they can be later freed . This allocation is but an example and others can be implemented depending on the device s memory structure and also possibly depending on other factors as one skilled in the relevant art would recognize. As in the above example when both arena and pool memory types exist content can be stored in a read only arena and or in a writeable pool . Further embodiments using this type of memory allocation are discussed below.

Referring to a diagram illustrating an example of content formatting according to an embodiment of the invention is shown. In this embodiment an example button is shown within the document A. The button object includes a header B and the parameter information stored as data C. Header B can include type information which provides a mechanism whereby there is a pointer or pointers to the type of functions which operate on the data C.

Referring to a diagram illustrating an object model related to those shown in FIGS. F and F is shown. shows a button object A that includes object pointers K. Object pointers K comprise a vtable pointer B and a data object C. Vtable pointer B points to a vtable D that contains function pointers F for accessing instance methods H.

Button object A and data C can be placed in writeable memory. Qualitative data can be read and written thus modified by instance methods H which are designed to read and manipulate data C.

1 Data C is in writeable memory. Data C is relatively large. If data C is first available in read only form then it must first be copied into writeable memory.

3 Data C cannot easily be maintained in compressed form as the size of data C will change as it is modified. This requires additional writeable memory.

Additionally the lack of a document table effectively means that any changes to the data C or the type information in header B requires a change to the vtable D which is used to operate on data C. These changes have to be made globally so that the entire document is recreated.

FIGS. F and F illustrate content instantiation architectures according to embodiments of the invention.

Referring to FIG. F a diagram illustrating the content instantiation architecture according to an embodiment of the invention is shown. FIG. F differs from in that data K is separated from object A. The addition of attribute pointer C which points to data K serves as a link so that changes do not have to be made globally as in .

Referring to FIG. F a diagram illustrating the content instantiation architecture according to an embodiment of the invention is shown. FIG. F is differs from FIG. F in that data K can be read only and compressed. Instance methods H are designed to read the compressed data.

The architectures of FIGS. F and F have advantages over the architecture of . Unlike the architecture of data does not have to be decompressed or copied to writeable memory for initial use. Data can be read and or displayed immediately. The architectures of FIGS. F and F are very efficient for mobile devices as well as other devices which can have relatively limited memory or processing capabilities because they use compressed read only data. Additionally the architectures of FIGS. F and F are useful for applications where memory and processing requirements need to be optimized as well as for other applications as will be appreciated by persons skilled in the relevant art s based on the teachings contained herein.

Referring to FIG. F for example document table A provides two pointers Vtable pointer B and attribute pointer C. Vtable pointer B points to a vtable D which includes header F and function pointers G. Header F includes information pertaining to the class and type of functions being called. Function pointers G includes global user and low level function pointers that provide access to the instance methods H of functions E.

Attribute pointer C points to the specific object in the content stream I similar to that discussed with respect to . Header J and data K provide specific information about how to perform the functions pointed to in the vtable.

The use of document table A allows the entire document to be incrementally altered as may be required without having to totally restructure the document.

It is noted that the data K can be compressed. Content stream I header J and data K can be in read only memory. Instance methods H can be designed to interpret the compressed data K so that instance methods H can read display and process data K properly.

According to embodiments of the invention modifications to data K are possible but any modified data K objects are stored in writeable memory. Attribute pointer C is updated to reflect the modification so that future use of the specific data K object is directed to the modified object. The embodiments of FIGS. F and F therefore provide for relatively less use of writeable memory on the mobile device.

The embodiments of FIGS. F and F offer important advantages to browsers. For example mobile devices typically are designed around several different operating systems and or hardware standards. The use of a client that enhances access helps to assure compatibility. Furthermore the general features of mobile devices are relatively limited compared to their PC counterparts. As such mobile devices benefit from enhanced content storage retrieval and modification techniques.

In an embodiment data can be transformed as shown in FIGS. F and F. In an example embodiment the objects A in FIGS. F and F share the same form i.e. a compressed read only form. The read only objects A of FIG. F can be transformed by instance method H into the writeable form shown in FIG. F. In one embodiment when instance method H is called a software exception similar to a hardware exception occurs.

Referring to FIG. F a flowchart P relating to an enhanced data modification process according to an embodiment of the invention is shown. For illustrative purposes FIG. F is described with reference to FIG. F. However the operations of FIG. F are applicable to other embodiments such as the example embodiment of FIG. F.

In step Q client accesses an object pointer L in a document object table A. The object pointer is an element of the document table which in one embodiment is placed at the beginning of the content stream.

In step T client uses the vtable pointer B to read function pointers G for access to instance methods H.

In step V client determines the requirements for the data K. In one embodiment client determines the amount of writeable memory that the data K will take up.

In step X client decompresses and copies the data K into writeable memory. In one embodiment the client access portions of hardware and operating system software of device to decompress and copy the decompressed data. In another embodiment the client internalizes the decompression and copying step.

In step Z client updates vtable pointer B to point to instance methods H for non compressed writeable data.

For example referring also to FIG. F a routine can allocate writeable memory for data K. It decompresses the data K and copies the data K into writeable memory shown as data K. The method then changes the attribute pointer C to point to data K. It also changes the vtable pointer B to point to the non compressed writeable instance functions vtable D.

With the modification complete the instance method H calls an equivalent instance method H to actually perform the required write operation of the data K.

A feature of this embodiment is that the operations of FIGS. F and F occur invisibly transparently to the application calling the pointers. An additional feature is that the operation is performed once on a per object basis. Once performed the object stays in writeable memory for the life of the document s object s .

A result of these embodiments is that object pointer L is preserved. This is important as many other objects may already have a reference to object A via object pointer L.

In an example application of the embodiment of FIG. F every object in the tree has an 8 byte two pointers entry in the Document Object Table DOT . The entry consists of a pointer to the object s class vtable table of function pointers for instance methods and a pointer to the object s data. In the case of content stream formatted documents the object s data pointer points into the content stream. It is noted that the invention is not limited to this example embodiment.

Inter object references are via Object Identifiers OID which are unique 16 bit identifiers for each object in the document. Unlike pointers OIDs support relocation and transmission between server and client. Entries in the DOT are ordered in OID order. That is the OID is also the index into the DOT. Thus an OID can quickly be translated into an Object pointer which is desirable at runtime by performing array arithmetic object dot oid . By using OIDs and pointers in the DOT approach a number of advantages are achieved relocatability and transmittability from the OIDs and ease of use and a rational runtime model from the Object model.

The DOT is created when the document is being loaded as shown in FIGS. F and F. An example scenario is as follows The content stream is interrogated to see how many objects are in the document. A DOT large enough to accommodate that number of objects is created. An application quickly scans through the content stream which has objects in OID order. For each object the application checks the type ensures that the class and vtable D for that type is created writes the vtable pointer B in the DOT entry then writes in the data pointer C pointing back to the content stream data K. Then the application skips to the next object in content stream each entry has a length prefix stored in header J . When the application is done it has a fully populated DOT with a number of objects that are writeable. If more objects are added to the document via scripting requests they are dynamically added to the end of the DOT in the form of FIG. F for example.

Like the PODS object model the invention s Object Model while implemented in C is compatible with C . Objects can be represented as abstract classes pure virtual member functions where the base class has no data slots. On most C compilers this will guarantee that the C vtable entry will be forced to offset zero in the class. The benefit both C i.e. ADOM setValue object xxx and C i.e. object setValue xxx bindings APIs to the same object are provided.

Referring to a diagram illustrating content structure according to an embodiment of the invention is shown.

Document stream A illustrates at a high level the structure of the document that includes header B string table C and object table D. Header B includes the document table information which can include object size number of objects and string sizes. String table C includes string identifiers SIDs E that are ordered based on the SID in a manner similar to OIDs as discussed above. String identifiers E include lists of word identifiers F which are ordered word tables G. Each word table contains characters H that are represented by a certain code I.

The structure embodied in stream A provides the compressed and ordered nature described herein. Object table D includes the type and size and other attribute information for each object in the document as in . String objects in these objects are string identifiers referring to C.

Style Sheets represent a mechanism for setting and holding style attributes. HTML elements have a number of attributes that are stylistic in nature dimensions colors font information list bullet styles etc. . Style Sheets are just a formalized scheme of setting getting and most importantly sharing these attributes. An advantage of Style Sheets is that they make it very easy to make global or semi global stylistic changes to a document.

For example if one wants all the image borders to be 4 pixels wide one can do that easily in one place. An advantage of supporting styles is it will make it easier for the content developer to share HTML between desktop and mobile devices without recoding the HTML.

Also style sheets represent a useful abstraction for attribute information. In an embodiment the HTML Element super class of HTML DOM is aware of style sheets. HTML Element provides the interface to get all attribute information for each object in the document. In one embodiment HTML Element obtains most of this information from the style sheet that is associated with the object. As style sheets tend to be shared by like objects the memory hit is not substantial.

In FIGS. I and I note the borders around Product List. The top and left borders are lighter while the bottom and right borders are darker than the background creating a stand out 3D effect.

The tree is made up of a three element list where each item is a title label and an embedded list. The embedded list is hidden by setting the top level display property to none then shown again by setting the property to block.

According to an embodiment the architecture of the invention is designed so that a majority of the code is in the cross platform core pieces. A component that cannot be easily made cross platform is graphics code that draws bits on the screen. According to an embodiment an approach is to break this component out as the Render abstraction define a strict interface between Render and the rest of the code and then utilize platform specific graphics subsystems capable of plugging back into the rest of the system.

The Draw code module deals with the semantic and programmatic level of graphics leaving the Render module with only the responsibility of putting bits on the screen such as bits in the form of strings rectangles border frames etc. By keeping the abstraction level low more functionality is maintained in the cross platform code leaving the platform specific Render engine author with less code to write and maintain.

The relationship between the render modules and the rest of the system is defined by a render interface. In one embodiment an example header file can be implemented. Such an example header file can includes one or more of three interfaces ARenderMgr ADrawCtx and ARenderFont.

In one embodiment ARenderMgr is the render engine. In a given executable based on this technology one can have 0 1 or N objects that implement an ARenderMgr interface. In order to do a layout or draw on a DOM tree one must have an ARenderMgr instance actually one needs a DrawCtx which is created by a RenderMgr object see the discussion below . The render engine for a given platform s graphics subsystem is created by a factory method on the object subclass implemented by that platform.

In one embodiment ARenderFont is a font in the world of this technology. ARenderFont basically defines a logical abstraction of the kinds of questions the core code especially layout needs to ask of a font without locking down to the very platform specific details of any platform s font subsystem. ARenderFont only defines font metrics such as in one font how many pixels wide is this string but most platform specific render engines may sub class and add drawing behavior to the ARenderFont class.

In one embodiment ADrawCtx is a drawing context and includes many rendering and drawing capabilities. ADrawCtx provides methods for getting bits on the screen drawString drawRectangle etc it provides the abstraction for the logical drawing surface the Window Form or Port that drawing occurs on and also acts as memo pad for coordinate information during drawing.

Cross platform Construction Layout and Rendering Technology for DOM Application Browsers or Viewers for Mobile Devices and DHTML Layout and Cascading Style Sheets

According to an embodiment of the invention the cross platform construction layout and rendering technology first parses HTML and then constructs a document object model based on HTML tags. It then lays out those objects in the tree that represent those tags in their logical pattern relative to their parent and children including details such as an x y location and width and height attributes. After the layout is complete the invention serializes the data and transmits it to the client in the case of the client server browser embodiment.

FIGS. D and D described above illustrate example diagrams showing an embodiment of the rendering of the client and or server.

Rendering functionality can reside on device or on the server. All of the processes can be present on the server leaving only the device specific reader to complete the pixelation of the objects or all of the processes can be present on the device including the parser. Thus in some embodiments the device can receive HTML and parse it appropriately.

The diagram includes server and device . As discussed above content A in the form of HTML CSS wireless markup language WML or other format enters the system.

Parser module B receives the content and formats it into discrete objects. Parser B assembles the objects into DOM F. Here DOM F is simply a placeholder for the content stream as it is being assembled. Layout module C reads configuration information from proxy render module E. Proxy render module E obtains this information from the device shown here as device configuration D.

Once the content stream has been assembled emitter and compressor module G forwards the content stream via communications medium H to client .

The client receives the content stream in DOM L. Loader J forwards the content stream to render module M for display on screen N.

Additionally client can also include optional parser module I and optional layout module K. In embodiments that include these modules client is capable of receiving content A and parsing it into a content stream. Furthermore layout module K can provide the proper configuration information directly from the device on which it is operating.

In an embodiment the above described processes begin with a user account and device specific sync to server where the server preemptively gathers enough information to represent the requirements of device .

If the device is capable of layout i.e. includes a layout and rendering module then the server may sync to the device only the DOM in content stream format. Layout operations are then performed on the device for the document.

If the device does not have a layout module or if the server is configured to perform the layout operations then the server will layout the document and then sync the document content and layout information to the device.

Another feature of this embodiment is that HTML is sent to the server. There a parser communicates with the document object model that creates a collection of objects including the ability to generate objects based on invalid HTML . From these objects a tree of objects is generated that includes their layout attributes such as x y coordinates and their width and height. This layout is based on a proxy of the device on the server.

Another feature is that the level of the technology that is synced or loaded to the device can be preemptively determined. The device known or unknown to the server will sync a proxy or map of the device requirements to the server. At the server objects are rendered to the specifications of that proxied device before the device syncs. This involves parsing rendering and laying out of document objects using the proxy map of the device.

For example suppose that a future device syncs to a current server. The invention enables the device to inform the server of enough information to represent its requirements. In other words the device provides enough information to enable the server to create a proxy of the device. The server then proxy renders the objects to the device based on the proxy of the device. Then the server may send the parsed and laid out objects or the parsed only objects to the device. In the case of raw HTML being sent to the device the server may not need to participate in the parsing process or other processes performed by the client.

On device pages are not necessarily created in their entirety although they can be . They may be viewed as instantiated objects as they are needed. The content stream is rendered based on the need for the elements on a page. Compressed in content stream format objects are instantiated based on deltas against a default set of attributes such as found in HTML coded into the client application.

For example if a document sent to the device needs to be viewed it is quickly rendered as a set of objects rather than as a rebuilt page of HTML.

In addition if the page needs to change the relevant objects are incrementally decompressed from the content stream as described above with respect to FIGS. F and F. Thus the decompressed versions of only the required objects are created. When a value in an attribute is changed by a user for example the name of a button is lengthened or a paragraph of text is added to the page only the objects that must be changed are decompressed.

For each instance of these objects there is a table of objects providing an efficient way of making a byte stream into a data model. The tables are heuristic tables for matching calls to data. The objects viewed are seen through the laid out objects. When the objects are changed a duplicate is created or morphed from the original object or set of objects and thus expanded based on a set of deltas. The result is a fully rendered copy of the object that is now writeable. A key to this functionality is how small the viewable objects are as they need to be on mobile devices until they need to be writeable. They become writeable when they are uncompressed or inflated to a fully rendered version.

The document object table that enables the content stream to be rendered by the invention is variable and customizable. The table may map to a function that calls data as easily as it maps to tables of data as easily as it maps to strings of code.

Another feature is that of on device HTML authoring. Rendered HTML and resources can be redrawn and the HTML can be sent back in a content stream via a sync for storage in a database or posting on a network intranet or Internet.

Another feature is that the proxy rendered nature of the invention enables a sync process to take over a device. The result may be a single function device with a browser or application lock that can only be reset by another sync to the server based on new server preferences. This means the client in conjunction with the object renderer and via a sync or other install mechanism can take over a device for a use as a single function single application device.

3.0 Server Side Preparation of Data HTML and Other Network Resources and Objects for Ease of Use on Mobile Devices

As previously stated in embodiments the invention uses server logic to optimize content for delivery on mobile devices. Server also stores optimized content in a cache. The optimized content is based on the type of mobile device that requested the content. Thus the invention stores device specific versions of content requested by mobile devices. For example suppose a first Palm device requests document A from provider A. Provider A controls page caching using relative or absolute date time stamps. Server may optionally override the page caching from Provider A. Document A is retrieved from provider A and optimized by web synchronization module for use on the first Palm device. The optimized content is then cached for the first Palm device. Next a Windows CE device requests document A from provider A. Document A is retrieved from provider A optimized for use by the Windows CE device and cached for the Windows CE device. If sometime later a second Palm device with identical or similar characteristics depending on the implementation as the first Palm device requests document A from provider A document A specific to the first Palm device is immediately retrieved from the cache. The web synchronization module does not have to retrieve document A from provider A for the second Palm device. As the number of users increases the cache hit ratio increases resulting in fewer fetches from providers . As the need for web synchronization module to retrieve an object from provider decreases server bandwidth requirements also decrease.

In step web synchronization module checks to see if the data object specific or applicable to the requesting mobile device is found in the cache associated with the server. If the data object specific or applicable to the requesting mobile device is found in the cache and is still valid the process proceeds to step .

In step web synchronization module retrieves the optimized data object from cache. The process then proceeds to step .

Returning to step if the data object specific or applicable to the requesting mobile device is not found in the cache or is no longer valid the process proceeds to step .

In step web synchronization module retrieves the data object from provider . The retrieved data object may include a date time stamp and or other information indicating when the data object will expire. The process then proceeds to step .

In step web synchronization module transforms the data object to a form suitable for use and or display on the requesting mobile device. For example an address book entry will differ for Palm and Windows CE devices. The process then proceeds to step .

In step the transformed data object is stored in the cache with device specific information along with information on how long the data object can remain in the cache such information may include the date time stamp information of step . Note that the transformed data object is only stored in the cache if information retrieved from provider A indicates that the data object is cacheable or if server is set to override the information from provider A. The process then proceeds to step .

In one embodiment negative caching is implemented. Negative caching involves caching errors that result when web synchronization module is unable to retrieve the requested data object from provider . This eliminates the need to subsequently access the provider . For example if provider is down negative caching may lessen the number of negative hits that would otherwise result if attempts were made to retrieve data objects from provider . When web synchronization module subsequently checks the cache for the irretrievable requested data it will see the cached error message and will make no attempt to retrieve the data from provider .

For example suppose device A requests a page. The web synchronization module requests the page from provider . However when web synchronization module requests the page from provider an error is returned indicating that the page is unavailable. Web synchronization module caches the error setting configurable expiration information. Later another device device B with characteristics similar to device A requests the same page. Web synchronization module will see the cached error assuming that this cached error is still valid indicating that the page is irretrievable. Therefore web synchronization module will not have to make an attempt to retrieve the page from provider .

In step web synchronization module checks to see if the data object specific or applicable to the requesting mobile device is found in the cache associated with the server. If the data object specific or applicable to the requesting mobile device is found in the cache the process proceeds to step .

In step web synchronization module retrieves the optimized data object from the cache. The process then proceeds to step .

Returning to step if the data object specific or applicable to the requesting mobile device is not found in the cache the process proceeds to step .

In step web synchronization module attempts to retrieve the data object from provider . The retrieved data object may include a date time stamp and or other information indicating when the data object will expire. The process then proceeds to decision step .

In decision step it is determined whether an error indicating that the requested data object was irretrievable occurred as a result of step . If an error message occurred the process proceeds to step . If no error message occurred the process proceeds to step .

In step web synchronization module transforms the retrieved data object to a form suitable for use and or display on the requesting mobile device. The process then proceeds to step .

Returning to decision step if an error message occurred web synchronization module in step transforms the error message to a form suitable for display on the requesting mobile device. The process then proceeds to step .

In step the transformed data object or the error message is stored in the cache with device specific information which may include an indication of how long such information may be cached as explained above . Note that the transformed data object or error message is only stored in the cache if information retrieved from provider A indicates that the data object is cacheable or if server is set to override the information from provider A. Server may provide special overrides for negative caching of error messages. The process then proceeds to step .

Normally when a large group of users sync daily at least some of the users are syncing the same version of a set of pages all of which will expire at the same time. For example if server has a million users with a page on each user s device that expires at 12 midnight on Sep. 9 2000 every single device connected to server at that moment which in a wireless world may be all of the mobile devices will request server to provide those pages.

An example diagram illustrating all hits on a server occurring at the same time is shown in for the above example. As seen in the diagram shows all of the hits on server occurring at once that is 12 midnight. This causes slow serving of new pages to all devices and puts excess stress on server and provider .

To prevent the above scenario from occurring an embodiment of the invention randomizes the expiration of the objects. This results in fast serving of new objects to all devices and puts less stress on server and provider .

Server sets a freshness lifetime for each object or in some embodiments for groups of objects stored in the cache. If the age of an object stored in the cache is within some of the freshness lifetime e.g. if it is about to expire otherwise known as Server FL or server freshness lifetime then server will vary the expiration of the cached object to determine whether the cached object should expire. The of the freshness lifetime is usually set at the startup of server using server preferences set by an administrator. Alternatively the of the freshness lifetime may be configurable.

Server uses freshness lifetime for determining whether or not to modify the expiration of the cached object. Server determines whether the cached object is close to expiring and then in an embodiment it uses a stochastic function to determine whether or not to expire the cached objects. The stochastic function is used if the current age of the cached object is within some percentage of the freshness lifetime.

In step server determines the cached object s age. The cached object s age is the total time that the object has been stored in the cache. The cached object s age is Object s Age now Tin cache 2 where Tnow is the current time. The process then proceeds to step .

In step server determines the of the object s freshness lifetime. The of the object s freshness lifetime is the object s age divided by the object s freshness lifetime. The of the object s freshness lifetime is of the Object s FL Object s Age Object s FL 3 The process then proceeds to decision step .

In step the object is retrieved from the cache and processed in an implementation or application dependent manner.

Returning to decision step if it is determined that the of the Object s FL is greater than or equal to the of the Server FL then the process proceeds to step .

In step in an embodiment a random number is generated using a random number generator. In one embodiment the random number generator may be normally distributed. In another embodiment the random number generator may be uniformly distributed. One skilled in the relevant arts would know that other distributions may be used without departing from the scope of the present invention. The process then proceeds to decision step .

In decision step it is determined whether the random number generated in step is less than the of the Object s FL. If the random number is greater than or equal to the of the Object s FL then the process proceeds to step where the object is determined not to have expired and is then retrieved from the cache in step .

Returning to decision step if it is determined that the random number generated in step is less than the of the Object s FL then the process proceeds to step .

The following is an example of how the above method works according to an embodiment of the invention. As previously stated if the of the Object s FL is within the of the FL set by the server the stochastic process is implemented. If for example an object s age is 190 and the object s freshness lifetime is 200 the object s age is 95 of the object s freshness lifetime. Suppose server was set for a threshold of 90 of the freshness lifetime. When a decision is made to vary the expiration for determining whether the object is fresh or expired the probability that the object is expired is determined by figuring out what percentage of the vary range 90 100 the current age of the object has covered. The vary range is 90 100 percent and since the age of the object is 95 50 is the probability that the object is expired. If the age were 92 of the freshness lifetime the probability would be 20 if 98 80 etc. Similarly if the range were 80 100 and the age is 95 the probability would be 75 . Then the random number is generated and compared to the probability in order to determine if the object is fresh or expired. Table 3 shows the age of the object the object s of freshness lifetime and the probability that the object will expire for the above example.

Server enables a single account profile user to sync multiple devices and obtain device specific content on each device. is an example block diagram illustrating a single account profile having multiple devices. Block diagram comprises a user account profile a first mobile device a second mobile device a third mobile device server and providers . First mobile device may be a Palm device. Second mobile device may be a cell phone. Third mobile device may be Windows CE device. Although shows three mobile devices associated with a single account profile one skilled in the relevant art s would know that more devices or one less device could be added or subtracted respectively without departing from the scope of the invention. User account profile is associated with each mobile device . Each mobile device interacts with server via a transmission medium which may be any wired or wireless medium using any communication protocol. Server may also connect to providers .

When any one of mobile devices initially connects to server each device will provide its device characteristics to server . Server will store the device characteristics in database module and send the device characteristics to web synchronization module and or server extension module . For subsequent connections with server each mobile device will identify itself to server and server will retrieve the device s characteristics from database module . In one embodiment as long as the user continues to sync devices with server server will maintain each device s information on database module . If any one of devices are not synced within some predetermined period server may optionally delete that device s information from database module . If a user syncs devices one right after the other each device will have the same content but the content will be optimized for each specific device .

An embodiment of the invention also provides a common link to share and sync data objects between disparate user devices. For example if user account profile has a personal digital assistant and a cell phone neither the PDA nor the cell phone may have the ability to communicate directly with each other. Assume an address book exists on both the cell phone and the PDA. The address book must be separately updated since the two devices do not have the ability to communicate with each other. However by using server of the present invention the PDA and the cell phone may sync up with server to provide the same information on both devices. In this example the address book of both devices may sync up with server to enable the address book on both the PDA and cell phone to contain the same information. Thus the invention syncs disparate user devices by providing server as a common link to share and sync data objects.

The invention also enables a single device to connect to multiple servers. shows an example screen shot for enabling a user to add multiple servers. is an exemplary block diagram representing a single mobile device that connects to multiple servers. Diagram comprises single user account profile connected to mobile device which in turn can be connected to a plurality of servers and that may be connected to any variety of providers such as the Web a database such as LOTUS Notes or a network respectively. Although shows three servers one skilled in the relevant art s based on the teachings contained herein would know that more servers or less servers could be implemented without departing from the scope of the invention. When a user initiates a sync in an embodiment device will be synced to each enabled server on device one at a time.

In step a list of sync servers and accounts per server are retrieved. The process then proceeds to step .

The invention also allows multiple devices for a single user account profile to be connected to a plurality of servers. A multiple device multiple server scenario is shown in . Although three mobile devices and three servers are shown in one skilled in the art would know that more or less devices and servers could be used without departing from the scope of the invention. In one embodiment user account profile can cache a variety of device characteristics and used to access a variety of servers and . In one embodiment the user can store the device profiles on a desktop and store the multi server connections on devices and . When the user initiates a sync for any one of devices and a list of sync servers and accounts per server is retrieved for the device and the device is synced to each server in the list one at a time. The user may then sync the next device as described above in section 3.2.1.

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example only and not limitation. It will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the invention as defined in the appended claims. Thus the breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

