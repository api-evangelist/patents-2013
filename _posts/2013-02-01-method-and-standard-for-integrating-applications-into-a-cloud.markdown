---

title: Method and standard for integrating applications into a cloud
abstract: An Application Packaging Standard (APS) is a specification defining application's life cycle in a cloud. The application's life cycle includes packaging, delivering to the cloud, verification of package, integrating (and unpacking) into the cloud, distributing to clients, licensing, functionality, updates and deletion. The APS has its own Application Programming Interface (API) for accessing the APS functions from a program code or by http/https requests. The APS provides for efficient integration of SaaS web applications into the cloud.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09455876&OS=09455876&RS=09455876
owner: INGRAM MICRO INC.
number: 09455876
owner_city: Irvine
owner_country: US
publication_date: 20130201
---
This invention relates to a method and a standard for application packaging and integration and more particularly to application resource integration and deployment into a cloud.

Computer systems present some challenges with regard to delivering and installing new applications. Software as Service SaaS web applications are integrated into systems by a vendor using special delivery and installation packages. However if the vendor needs to integrate deploy his application into a cloud he would have to repeat all integration operations for each host or hosting platform several times. The hosts and the hosting platforms have applications that control the host or the hosting platforms. These applications make it very difficult and expensive to integrate external third party applications or web services. However for the vendor to himself develop host specific applications is even more expensive.

Currently integration of applications into hosts and hosting platforms is implemented using two classes of applications a Control Panel and a Service Controller. In case of a cloud these programs are inefficient and have to be used several times by a vendor in order to integrate a single application into the cloud.

The clouds or cloud servers is a software hardware combination of a host provider which provides for functionality of external applications in its client s accounts.

Accordingly there is a need in the art for an efficient and inexpensive method for integration of applications into the clouds.

Accordingly the present invention is related to a method and a standard for application integration and deployment into a cloud that substantially obviates one or more of the disadvantages of the related art.

An Application Packaging Standard APS is specification defining application s life cycle in a cloud. The application s life cycle includes packaging delivering to the cloud integrating and unpacking deploying into the cloud distributing to clients licensing functionality updates and deletion.

The APS has its own Application Programming Interface API for accessing the APS functions from a program code or by http https requests. The APS provides for efficient integration of SaaS web applications into the cloud.

Additional features and advantages of the invention will be set forth in the description that follows and in part will be apparent from the description or may be learned by practice of the invention. The advantages of the invention will be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

Reference will now be made in detail to the preferred embodiments of the present invention examples of which are illustrated in the accompanying drawings.

According to an exemplary embodiment an Application Packaging Standard APS is a specification defining application s life cycle in a cloud. The application s life cycle includes packaging delivering to the cloud integrating and deploying into the cloud distributing to clients licensing functionality updates and deletion.

The APS has its own Application Programming Interface API for accessing the APS functions from a program code or by the http https requests. The APS provides for efficient integration of SaaS web applications into a cloud. According to the exemplary embodiment the APS applications can be divided into three types 

Web Applications a simple type of applications that are physically distributed among cloud clients. This means that one copy of the application files database configurations settings etc. belongs to one user. For example Content Management Software CMS applications are distributed to the cloud users.

Dedicated Applications complex type of applications that require close communications with the Operating System. The Dedicated Applications require virtualization for example in a form of containers . A container is a closed set or a collection of processes system resources users groups of users objects and data structures. Each container virtualizes a single instance of an operating system and has its own ID or some other identifier which distinguishes it from other containers.

According to the exemplary embodiment a vendor packages his application according to the APS. The format of the package depends on the receiver. If the receiver is a standard Windows desktop then the software can be packaged using standard installers and the file has a .exe or .msi extension. The installer includes unpacking rules that includes a user dialog writing into the registry checking for updates and so on. In the case of APS the packed file has a .app.zip extension and includes metadata scripts and software code itself.

An exemplary application type E is located in an external cloud . An application type H is located inside the hosting cloud . The APS module distributes the applications and to the clients . One application can be delivered to one client or to multiple clients as shown in .

As shown in the application becomes available to the clients through the hosting panel using the cloud and application package . The application package provides for installation of the application into the cloud . Update of the application to a next version for example v. 2.0 is performed via the APS module . Functionality of the application can be extended by adding services and add ons. A widget application can be integrated for example into the site or Control Panel of client .

According to the exemplary embodiment the APS module monitors resource usage by the application and provides this data to the provider . The application can be deleted from a list of available applications and from the hard drive.

The APS strictly defines a set of files in the package the file names and a structure and syntax in case of the metadata files . The APS package is a zip file having the extension .app.zip. The metadata includes 

According to the exemplary embodiment the control script files are located in a folder scripts . The control scripts are used for launch of the application on the server for the application update for extending the application and for the application deletion. The folder scripts also contains configuration files that define application parameters. The content is the actual application files icons and screenshots. An example of a package structure is provided in the appendix i.

According to the exemplary embodiment each package contains in its root directory a file APP META.xml where all package metadata is listed. An exemplary file APP META.xml in RELAX NG notation is provided in the appendix ii. The APP META.xml has to be valid according to the APS. If the APS package files change the APP META.xml has to change accordingly. Otherwise some collisions occur and the installation of the package cannot be performed partially or entirely .

Note that some elements and parameters of the RELAX NG notation of the APP META.xml see appendix ii are mandatory i.e. the package does not work without them and some are optional and can be omitted. Some of the identical elements with different values can be present in the file or in the parent element in several copies. Some other elements can be present only as one original copy in the file or parent element . For example in RELAX NG notation 

The optional parent element contains three child elements. The element itself can occur 0 or 1 times indicator . However if it does occur then it can contain three elements name required element and can occur 1 or more times indicator homepage optional element can occur 0 or more times indicator icon optional element can occur only 1 time indicator .

According to the exemplary embodiment the application is described in the APP META.xml as follows using special tags 

The APS specification is strict but flexible. The APS can extend the application functionality. For example a file can have some space reserved for it in the package by describing the file in the metadata but the file is not included into the current package. The APS can set an additional programming language for reading the configurations files. The APS supports add ons. Also a separate APS package can be an addition to another APS application.

The host gives resource usage quotas to the application . Tenants acquire different services from different applications from the provider see . The APS module receives data reflecting current state of resource usage based on execution of the services . Then the APS module provides resource usage data by each tenant to the host platform . Subsequently the host platform bills the tenants for resource usage.

According to the exemplary embodiment the APS supports a service hierarchy. In other words the service in the APS can be separated into the subservices so the host or the provider can use different rates for different sets of services. Any service can be included or excluded. Additionally a number of users of the service on the same account can be set as well. Note that the APS module extracts data reflecting applications execution which is not available to the host . For example the APS module can know an amount of a disk space occupied by a mail application while the host only knows the amount of space allocated for the mail application.

In connection 1 represents the weak connection of the type any. Connection 2 represents the strong connection of the type single. Connection 3 represents the weak connection of the type any. Connection 4 represents the weak connection of the type any. 

According to the exemplary embodiment the connections have different purposes. The connections unite the resources into one set or collection in order to rent the set as a single resource bill it separately and collect statistics. The connections can support a parent child hierarchy of the resources in order to define a separate functionality service within the application and rent it out separately from the parent application.

The connected resources can subscribe for notifications reflecting changes in the status of the connected resource. This is needed so after the changes occur in a monitored resource object the monitoring resource can make changes in its configuration.

In the APS system a user can associate two resources with one of the predefined types of relations after the verification that such a possibility is available. Relations vary on a logical parameter obligatory Strong and optional Weak and also by the quantitative parameter only 1 Single from 0 to infinity Any . See .

Typically each APS Resource implements one or more APS Types. APS Type declaration provides all needed information on the Resource API. It also contains general information on the following 4 sections Properties Operations Relations Structures.

In another embodiment the widget is a form with a text box s and a submit button. The press of the button triggers sending a POST request to the application. The APS controller calls a required script for execution. If the widget is a user authorization form the answer can be checking of the login and the password. If the check is successful unsuccessful the user is given an HTML welcome denial page.

A simple widget in sends a GET request to the application in order to receive the HTML content. The client clicks on an application hyperlink on a browser page . The browser sends the user GET request to a server where the request is received by the host panel . The host panel passes the GET request to the ASP controller . Subsequently the ASP controller makes the application to execute a particular widget method. As result the application returns an HTML code. The ASP controller sends the HTML code to the host panel . The panel sends the HTML code to the browser . The browser reflects the HTML code as a widget page.

The APS controller module sends the HTML code to the host panel . The host panel sends the HTML code with an http header for redirection to the browser . Since the HTML code contains a redirect header the browser requests a page at a new address. The host panel provides the new page to the browser . The client sees a new page with the data reflecting the fields to be filled out or an OK button or an OK button with a time out before next process.

After the client clicks the button again or after the time out a confirmation request goes to the host panel . The host panel passes the request to the APS controller module . The APS controller module calls the widget method corresponding to the request. The application executes the widget method and provides a message to the APS controller module . The APS controller module passes the message to the host panel . The host panel changes appearance of the page for the client based on the message. A new look of the host panel is provided to the browser . The browser reflects the new panel to the client .

According to the exemplary embodiment the APS has some roles and policies for its users. A user account i.e. a company account can be a provider a reseller or a customer. A user role i.e. a set of rights can be an owner a referrer or an administrator. A user privilege can be a permission for a certain action such as allow changing a type of an application and allow working with the APS controller.

The users communicating with the APS application must be in one of the roles a resource owner i.e. a user of the system that owns the APS resource or a resource referrer i.e. a user of the system that has an APS link to the APS resource but does not own it . Note that the resource administrator always has a full access to the APS resource. The predefined list of roles includes a provider a reseller an administrator and an end user. More roles are available if needed.

According to the exemplary embodiment the APS Application Programming Interface API can be divided into internal and external APIs. The internal API has a set of control parameters that are passed to the application for controlling it i.e. installation update deletion etc. . The external API is a set of parameters used by the application in order to perform operations requested by the end user. The parameters commands are passed via entry points IP or web addresses . The APS controller intercepts the parameters and makes the application react according to the parameters.

For example a request to the application to list its resources can be implemented by sending a request to the address https entry.application.com services where is an identifier of the application. In response to the request the application produces a JSON representation of the resource in the http response 

According to the exemplary embodiment a resource is an instance of an application packaged as a configuration file or database records which can be used in the context of the application. The configuration file specifies software hardware environment for launching the application allocated quotas clients for whom the current configuration is intended.

The application provisioning is depicted in . A client of a host cloud requests a resource to use. If the application which owns the resource is located on the server of the host cloud the APS controller sends the HTTP request containing work parameters of the resource to the application . Subsequently the application creates an instance of the resource with client parameters. For example the application forms and saves a file with the client configuration. The configuration file is called prior to accessing the client resource in order to configure the application before serving the client .

Then the resource becomes available to the client. If the application which owns a resource is located in the external cloud the APS controller calls the external application . The application creates a resource instance on the host could server. Then the resource becomes available to the client .

According to the exemplary embodiment the application provisioning can be used for provisioning of the resource if the resource is a special type of the application . The application provisioning includes the following steps 

2. Satisfy pre requisites for every mandatory prerequisite resource. For every resource find allocate resource of the required type and link the resource using provision method 

Note that if any of calls fails or if provision call fails all operations are rolled back i.e. the acquired resources is freed up or removed .

The application declares resource of the application type. The APS controller provisions the resource for each instance of the application. The resource can require one of the available environments. In this case the APS controller executes all code for provisioning of application s resources and the code for the resource of the application type via the end point of the environment. Note that for every new application resource which requires an environment the new environment has to be created.

According to one exemplary embodiment the application deployment workflow for the application requiring the environment is performed using the following stages 

1. The APS controller provisions the resource of the environment type as a pre requisite for the application type 

2. The APS controller creates a new application resource with a strong link to the environment resource 

3. The APS controller calls link method of the environment resource and the environment resource sends URI of a new resource location to controller indicating the APS package of the application 

4. The APS controller calls provisioning method of the application resource via the end point of the environment .

The resource of the application type can be upgraded when a new version of the APS package is available. The application upgrade is performed as follows 

1. The APS controller calls the upgrade method of the environment resource with URL of the APS package of the application 

According to the exemplary embodiment when the application calls the corresponding resource the application acquires the resource i.e. checks if the resource belongs to the client and launches the application files according to the configuration written in the resource file or a database . A resource in accordance with the exemplary embodiment can be any of 

Note that if the application is partitioned into an unknown software hardware environment of the host provider or the client requires a special configuration different from the server configuration the system can set up a virtual environment for running the application. In order to do this an environment resource is launched during the provisioning. A request with the required environment parameters in its header s is sent to the required address. The environment parameters can be an operating system a programming language required for interpreting the application code a size of an operating memory a processor architecture etc.

According to the exemplary embodiment an Environment type of resource allows to deploy an APS application inside the environment. The environment resource exposes application s resources via HTTP end point and executes provisioning scripts of these resources. The environment resource can be required based on the application type. The environment must be able to create an end point for application resources extract application files from the APS package and deploy the files at the end point. The environment can also upgrade files of existing application s .

According to the exemplary embodiment the environment declares preUpgrade and postUpgrade methods that accept a URL with APS package input address. When the preUpgrade method is called the environment downloads the package and deploys it in such a way that the end point of the environment resource is mapped to a script code folder of the package. When the postUpgrade method is called the environment downloads the package and deploys new files at the existing end point.

According to the exemplary embodiment the environment resource implements an APS resource interface i.e. an application API . Also the environment interface implements provisioning of an application workflow. An exemplary environment configuration structure is provided in the appendix iv.

The resource entry point URI is available as a part of the environment resource configuration where the deployed application serves as the environment s URI element as demonstrated in this example 

According to the exemplary embodiment security of the application entry point is ensured by an SSL certificate installed into the entry point. In order to get the SSL certificate the environment resource accesses the ASP controller and requests the SSL certificate. Upon accepting the request for a specific application the environment makes sure that the request sent by the APS controller using SSL certificate matches the SSL of the entry point. Here the only URL from which the application can be requested is one received through the APS controller. The APS controller encrypts the certificate using a secret key which means that anyone with a corresponding public key can decrypt it but can be certain of who encrypted it. Thus if a fake site sends a request it will be apparent that it is fake since it doesn t know the secret key.

According to the exemplary embodiment the environments perform the same operations for the applications as they do for the web applications 

The environment returns the address and request for APS package step . The package is delivered to the environment step . The APS package is unfolded and becomes a functioning application step . The environment returns OK and the address of the application in the virtual environment entry point step . The APS controller calls the application at the given address step . The application returns OK to the ABS controller step . The ABS controller returns OK to the owner of the APS step .

The application resource uses computer system resources. The resource usage is monitored and provided to the host platform which does not know about dynamic statistics of the application execution. The host platform only knows about allocated quotas that cannot be exceeded by the application. Additionally a usage of business quotas is monitored for each class of applications. For example for an application which performs a site backup the business quota can be a number of the backups performed over a billing cycle. Other examples of monitored application execution parameters are 

The Application ID is a URI formed unique application identifier. This string is used as the application identifier which cannot be changed in any consequent versions of the application packages. Otherwise the package upgrade and the patch from older versions cannot be implemented.

The Package Name is a free formed short string which specifies user visible name of application in the package. The Package Name can be changed during the upgrade. It should reflect packaged software name.

The Package Version consists of two parts an application version and a package release. The application version corresponds to the version of application packaged and the package release corresponds to the release of the package containing the same version of the application. Note that the packages can be released several times e.g. for fixing bugs in packaging or adding localizations generally there are common practices for numbering of release versions builds and revisions however each developer can follow his own rules if he wishes. Typically if all that is fixed are minor bugs then the version remains the same but the release number will be incremented. .

A version format and the algorithm for determining the chronological relationship between different package versions are specified by the version Policy. Note that the application version and the package release are separated to ease parsing.

If a package is an add on package for another APS application this definition provides a reference to the master package by the ID and the version release properties. Optional property is provided by a match XPath expression. The virtual node s version and release in the context of the expression represent the version and the release of the master package.

Before installation the APS controller must check availability of referenced APS package in a given context. Add on packages can access the global settings of the master package. Add on package has access to the same set of resources as the master package.

The Software Vendor Information property reflects characteristics of a software vendor whose application is packaged. The icon path attribute contains a full path in archive to the icon file. The icon is a 64 64 pixel image in PNG format using alpha transparency. JPEG and GIF formats can be used as well but their use is discouraged.

A Software Packager Information reflects characteristics of a package manufacturer. The icon path attribute contains a full path in archive to the icon file. The icon must be a 64 64 pixels image in JPEG PNG or GIF format. The URI element is an arbitrary URI unique for each packager. This URI is needed to distinguish packages with the same name but created by different packagers. Note that consequent versions of the same package must have the same URI. Otherwise package controllers might refuse to update package from one version to another.

The controllers allow for upgrade and patching of the package from a version which does not specify the URI to the version which specifies the URI in order to support smooth upgrade path for the packages that did not use the URI from the beginning.

The Icon can be provided to be displayed in a GUI for the application. The path attribute must contain a full path in the archive to the icon file. The icon is a 64 64 pixel image in PNG format using alpha transparency.

Several screenshots with descriptions can be provided. The path attribute contains a full path in the archive to the screenshot file. It must be JPEG PNG or GIF image.

The Changelog contains the human readable list of changes between consecutive package versions. An order of entries in the changelog is not specified the entries are sorted by the APS controller.

A package can include a set of categories. The category is a unicode string without attached semantics. The first category should be primary category in a sense that the first category is sufficient for sorting packages in the user interface. A list of pre defined categories is available in APS categories catalog. The specified categories names must be used. Other categories names can be used but handling them in the APS Controller is optional.

The package can declare a set of languages for the presentation purposes. The first language is a default language of the application. Languages are identifiers from ISO 639.

The application can declare versions of packages which can be updated to the current package. Two update strategies are supported 

A patch version change without major changes in application settings and without any changes in deployment logic. In particular all allocated resources are left as is and no changes in the application mapping scheme are allowed. Moderate changes in the application settings are allowed however several classes of changes that can lead to ambiguity are prohibited.

Such restrictions allow unattended update of all application instances thus making patches a preferable way to apply crucial changes such as security fixes. If a patch fixes security problem or problem that affects all software users it should declare the recommended element. Otherwise it is assumed that the patch fixes some specific problem or implements additional functionality and is intended to be installed only by those users who are experiencing the problem.

An upgrade a version change which allows complex changes in application settings and deployment logic. This operation may require a user attendance. A package can specify which versions it can update with a help of a match attribute. This attribute contains expression that is evaluated against a metadata of the installed packages with the same id or a name packager pair for older packages and a lower version release numbers.

The above specification means that the package can patch the installed version 2.0.1 or 2.0.2 and upgrade version 1.0.1.

If the installed version is greater than 2.0 patch is possible. Patch contains crucial fixes affecting all application users. If the installed version is greater than 1.0 and less or equal to 2.0 upgrade is possible.

According to the exemplary embodiment the application is supposed to provide services to its users or other applications. Complex applications can provide several services of a different nature and logic. Any service is a set of resources of a specified type provided by the application. In the simplest case a resource is an application instance itself. Distinct services are declared by service elements such as name settings presentation service type service resource etc.

The class attribute can be used to inform a control panel about the destination web resource. The following values of this attribute are predefined 

The APS controller can use this information when grouping the links or optionally displaying them. The APS controller ignores unknown values of the class attribute and treats it as unspecified.

4. A number of application business substances used by the client e.g. a number of mail boxes sent and received messages etc. 

The packaged application data can be filtered based on type or size occupied on the disk. The contents of the APS packet can be distributed to various virtual hosts based on the algorithm defined in the configuration file of the cloud server s software. For example if a client logs into his server s control panel for the first time using the address canada.hosting.com the authorization form will be presented in English with the Canadian flag. If the client logs into his control panel for the first time using the address turkey.hosting.com the form will be displayed in Turkish with the Turkish flag. Both sub domains are located on the same server and the configuration file includes the rules in the mod rewrite module.

The rules require that when the client uses the canada.hosting.com address the language settings are taken from the APS package in effect a package with skins and are copied to his home folder for the virtual host that belongs to the Canadian user. Similarly if the client used the address turkey.hosting.com Turkish language settings are taken from the APS package and the virtual host uses Turkish client settings and images. As such each virtual host and a typical production environment can have thousands of virtual servers on each physical server does not need to maintain all the local settings and configurations in its own file space while only a handful of them are typically used.

According to the exemplary embodiment the APS catalog can include both applications and plug ins. The application user knowing his own login password can download and install the plug in for his application directly from within the application. Another mechanism for user identification can be a token ID a unique identifier which is generated and sent from a server to a software client to identify an interaction session which the client usually stores as an HTTP cookie .

Note that if a buyer of the application is a host who distributes the application to its own subscribers then packet based installation can be used for one plug in to all the applications installed on all the clients.

Those skilled in the art will appreciate that the proposed method provides for an efficient integration of an application into a cloud server according to the application packaging standard APS .

With reference to an exemplary system for implementing the invention includes a general purpose computing device in the form of a host computer or a server or the like including a processing unit a system memory and a system bus that couples various system components including the system memory to the processing unit .

The system bus may be any of several types of bus structures including a memory bus or memory controller a peripheral bus and a local bus using any of a variety of bus architectures. The system memory includes a read only memory ROM and random access memory RAM . A basic input output system BIOS containing the basic routines that help to transfer information between the elements within the personal computer such as during start up is stored in ROM .

The computer may further include a hard disk drive for reading from and writing to a hard disk not shown herein a magnetic disk drive for reading from or writing to a removable magnetic disk and an optical disk drive for reading from or writing to a removable optical disk such as a CD ROM DVD ROM or other optical media.

The hard disk drive magnetic disk drive and optical disk drive are connected to the system bus by a hard disk drive interface a magnetic disk drive interface and an optical drive interface respectively. The drives and their associated computer readable media provide non volatile storage of computer readable instructions data structures program modules and other data for the personal computer .

Although the exemplary environment described herein employs a hard disk a removable magnetic disk and a removable optical disk it should be appreciated by those skilled in the art that other types of computer readable media that can store data that is accessible by a computer such as magnetic cassettes flash memory cards digital video disks Bernoulli cartridges random access memories RAMs read only memories ROMs and the like may also be used in the exemplary operating environment.

A number of program modules may be stored on the hard disk magnetic disk optical disk ROM or RAM including an operating system e.g. Microsoft Windows 2000 . The computer includes a file system associated with or included within the operating system such as the Windows NT File System NTFS one or more application programs other program modules and program data . A user may enter commands and information into the personal computer through input devices such as a keyboard and pointing device .

Other input devices not shown may include a microphone joystick game pad satellite dish scanner or the like. These and other input devices are often connected to the processing unit through a serial port interface that is coupled to the system bus and they may also be connected by other interfaces such as a parallel port game port or universal serial bus USB .

A monitor or other type of display device is also connected to the system bus via an interface such as a video adapter . In addition to the monitor personal computers typically include other peripheral output devices not shown such as speakers and printers.

The personal computer may operate in a networked environment using logical connections to one or more remote computers . The remote computer or computers may be another personal computer a server a router a network PC a peer device or other common network node and it typically includes some or all of the elements described above relative to the personal computer although here only a memory storage device is illustrated.

The logical connections include a local area network LAN and a wide area network WAN . Such networking environments are common in offices enterprise wide computer networks Intranets and the Internet. In a LAN environment the personal computer is connected to the local network through a network interface or adapter . When used in a WAN networking environment the personal computer typically includes a modem or other means for establishing communications over the wide area network such as the Internet.

The modem which may be internal or external is connected to the system bus via the serial port interface . In a networked environment the program modules depicted relative to the personal computer or portions thereof may be stored in the remote memory storage device. It will be appreciated that the network connections shown are merely exemplary and other means of establishing a communications link between the computers may be used.

Having thus described a preferred embodiment it should be apparent to those skilled in the art that certain advantages of the described method and apparatus have been achieved.

It should also be appreciated that various modifications adaptations and alternative embodiments thereof may be made within the scope and spirit of the present invention. The invention is further defined by the following claims.

The application packaging controller receives API instructions from users using http or https protocol and launches application scripts required for execution of the instructions. The URL Mapping for these instructions is as follows 

A deployed application has APIs that are required to be exposed from an Application Packaging Standard application 

