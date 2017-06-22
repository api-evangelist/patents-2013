---

title: Information processing apparatus and computer-readable medium storing information processing program
abstract: Data processing unit produces first access target information. Location information obtaining unit obtains first location information indicating the identifier of a data storage device specified by a user, as well as indicating the location of a user-specified directory within the data storage device. Location information producing unit produces second location information indicating the location of a directory that is placed below the user-specified directory and uniquely assigned to the data processing unit. Access target information producing unit produces second access target information, using the location indicated by the second location information as a reference location. Access unit makes access to the target data file in the data storage device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09619510&OS=09619510&RS=09619510
owner: FUJITSU LIMITED
number: 09619510
owner_city: Kawasaki
owner_country: JP
publication_date: 20130605
---
This application is a continuation application of International Application PCT JP2010 072212 filed on Dec. 10 2010 which designated the U.S. the entire contents of which are incorporated herein by reference.

The embodiments discussed herein relate to an information processing apparatus and a computer readable medium storing information processing program.

Cloud computing is known as a type of services allowing users to utilize computing resources available on a network of servers as needed with their terminal devices and network connections. The available computer resources include for example data processing functions that are realized by executing application programs on a computer. Such data processing functions are referred to herein as applications . A variety of applications are provided by many servers on the Internet. The users make access to different servers from their terminal devices depending on what application services to use to achieve their respective purposes.

In relation to the provision of services to users the servers may be configured to hold personal data of the users so as to allow an application to use such data during its execution. One of the benefits of letting servers manage users personal data is that the users can receive personalized services wherever they are. The personal data of users may include for example documents that they edited attribute data e.g. name and residence address of individuals and information about the environment in which they use applications e.g. mail server name mail address password .

The servers on the network manage such personal data of users and various useful techniques may be applied for this purpose. For example one proposed system is designed to deliver data files to a requesting client terminal in encrypted form by using a cryptographic key associated with that client terminal. In this system the client terminal can decode encrypted data files with a decryption key only if the client terminal is authenticated as the rightful destination of the files. Another proposed technique permits an application system to use a plurality of different databases in a unified manner.

Some users may use a plurality of applications provided in different servers. This means however that their personal data is distributed across a plurality of servers. The users are more burdened with the management of their personal data in those servers.

According to an aspect of the embodiments to be discussed herein there is provided an information processing apparatus which includes a processor configured to perform a process including executing data processing operations requested by a user and producing first access target information in order to make access to personal data of the user the first access target information indicating a path and a name of a target data file containing the personal data the path pointing to the target data file by following a directory structure from a reference location obtaining first location information indicating an identifier of a data storage device specified by the user as well as indicating a location of a user specified directory within the data storage device producing based on the first location information second location information indicating a location of a directory that is placed below the user specified directory and uniquely assigned to the data processing operations producing based on the first access target information and the second location information second access target information indicating a storage location and name of the target data file wherein the location indicated by the second location information is used as the reference location and making access to the target data file in the data storage device based on the second access target information.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention.

Several embodiments will be described below with reference to the accompanying drawings. These embodiments may be combined with each other as long as there are no contradictions between them.

The first embodiment described in this section is designed to manage personal data of a user centrally in a single place specified by the user while allowing him or her to use applications provided in a plurality of servers. This feature of the first embodiment makes it easier for the user to manage his or her personal data despite the use of applications in multiple servers.

The services provided in the Internet and the like are expected to have a continuing growth. This means in general that the personal data of a single user is managed separately in a plurality of servers that he or she uses.

That is private information of a single person may be distributed across so many places that the management of such data could get out of hand because of its increased burden on the person. People have to search all the servers they are using when they happen to forget which server stores a particular piece of their personal data. Further most servers on a wide area network such as the Internet implement a user authentication procedure to confirm the authenticity of users before accepting their requests. This feature may degrade the usability of servers because the users have to go through the authentication procedure at each server from which they are trying to retrieve desired data. The users have also to bear a burden of managing varieties of authentication data e.g. different pairs of user name and password to use servers.

In view of the above the first embodiment provides features for managing personal data of users centrally at a single server to alleviate their burden. When a user uses a plurality of applications and if those applications store their respective data in a single directory the shared use of the directory could lead to a conflict of data storage locations. That is one application may overwrite an existing data location e.g. files created by some other application. This kind of conflict could arise when two or more applications happen to create files with the same name. The first embodiment therefore provides a function of preventing such conflict of data storage locations. This function realizes unified management of personal data with a single data storage device while allowing a plurality of applications to use the data.

The data processing unit performs data processing operations requested by the user . For example the user may enter a data processing request to the data processing unit through an input device . The data processing unit may also make access to personal data of the user . To this end the data processing unit produces first access target information that indicates a path and name of a target data file containing the personal data where the path points to the target data file by following the directory structure from a specific reference location.

It is noted here that the term file used in this description does not only refer to an individual data file in a file system. Rather the term file may broadly refer to a data resource or a single segment of storage areas for writing or reading data such as a row of data in a database system.

It is also noted that the terms directory and directory structure used in this description does not only refer to a location of files in the file system of a single computer. Rather the terms directory and directory structure broadly refer to information representing a hierarchical arrangement and reference structure of files as in the Uniform Resource Locator URL or the identifier indicating the global location of a file in a multiple computer environment.

The location information obtaining unit obtains first location information indicating an identifier of a data storage device specified by the user and the location within the data storage device of a user specified directory specified by the user. For example the location information obtaining unit receives first location information that the user enters through the input device .

Based on the first location information the location information producing unit produces second location information indicating the location of a directory that is placed below the user specified directory and uniquely assigned to the data processing unit . For example the location information producing unit gives a unique name to the data processing unit and appends the produced unique name to the first location information . Here the unique name serves as the directory name of a directory placed below the user specified directory. By appending the unique name of the data processing unit to the first location information the location information producing unit produces second location information . The location information producing unit enters this second location information in the storage unit for example.

The access target information producing unit produces second access target information based on the first access target information and second location information . Here the location indicated by the second location information is used as the reference location mentioned above. The second access target information indicates the storage location and name of the target data file. For example the access target information producing unit retrieves the second location information from the storage unit and then appends the first access target information to the retrieved second location information thereby producing second access target information . The access target information producing unit passes the produced second access target information to the access unit

Based on the second access target information the access unit makes access to the target data file in the data storage device and passes its access result back to the data processing unit . For example what the data processing unit is doing to the personal data may be a data write operation or a data read operation. In the case of a data write operation the access unit executes it by writing new data to the target data file in the data storage device and returns a write completion notice to the data processing unit as an access result . In the case of a data read operation the access unit executes it by reading data from the target data file in the data storage device and passes the read data to the data processing unit as an access result .

 Step S It is supposed that the user has specified a data storage device and a particular directory in the data storage device . The location information obtaining unit obtains first location information that indicates the identifier of the user specified data storage device and the location of the user specified directory. In the example of the location information obtaining unit obtains api.data.example user1 as the first location information . This first location information is formed from api.data.example and user1 the former part being the identifier of the user specified data storage device and the latter part being the location of the user specified directory.

 Step S Based on the first location information the location information producing unit produces second location information that indicates the location of a directory placed below the user specified directory. This directory is uniquely assigned to the data processing unit . In the foregoing example of the second location information reads api.data.example user1 app1 . This second location information has been produced by appending a directory name app1 to the first location information obtained above.

 Step S The data processing unit determines whether the data processing operations requested by the user have been finished. For example the end of data processing operations may be indicated explicitly by the requesting user . The data processing unit may also recognize the end of data processing operations when all scheduled operations are finished. This is applied to a class of data processing that can be executed without the need for interaction with the user . The process of is terminated when the requested data processing operations are found to be done. When the requested operations are still under way the data processing unit advances the process to step S.

 Step S The data processing unit determines whether there is a need for access to personal data of the user . When there is such a need for access the data processing unit produces first access target information that indicates a path and name of a target data file containing desired personal data so that the file is reached by following the directory structure from a specific reference location. The produced first access target information reads data file1 in the example of which indicates that the access is directed to a target data file named file1 in a directory named data . The process of then proceeds to step S. When there is no need for access to the user s personal data the data processing unit goes back to step S.

 Step S The access target information producing unit produces second access target information based on the first access target information and second location information . For example the access target information producing unit appends the first access target information to the second location information thereby producing second access target information . Referring again to the example of the resulting second access target information reads api.data.example user1 app1 data file1 .

 Step S Based on the second access target information produced above the access unit makes access to the target data file in the data storage device and passes its access result back to the data processing unit . The access unit goes back to step S.

The above described steps permit the information processing apparatus to make access to personal data of the user which resides in a directory that is located below the directory specified by the first location information and uniquely associated with the data processing unit . The user may use a plurality of data processing unit by entering the same first location information to them. The personal data of the user in the data storage device is managed separately in different directories uniquely associated with different data processing unit so that those data processing unit refer to their respective sets of personal data.

For example the user may use a plurality of applications provided by many servers on the network. Each of those applications acts as the data processing unit discussed in which uses personal data of the user managed in the data storage device .

The above features enable the user to handle his or her own personal data easily because the data is consolidated and managed in a single data storage device .

The above described data processing unit location information obtaining unit location information producing unit access target information producing unit and access unit may be implemented as functions performed by a central processing unit CPU in the information processing apparatus . The storage unit on the other hand may be implemented as a data storage medium such as random access memory RAM or hard disk drive HDD in the information processing apparatus .

The above described first and second location information may take the form of URLs for example. Accordingly the following description uses the terms user root URL and application specific URL to refer respectively to the first location information and second location information discussed in the first embodiment. The following description also uses the terms application local path and access target URL to denote the first access target information and second access target information respectively.

For example a single application may be provided to embody the data processing unit location information obtaining unit location information producing unit storage unit access target information producing unit and access unit in the information processing apparatus of . This application may be executed in for example one of the following three modes.

In the first application execution mode a terminal device downloads an appropriate program from a server to a terminal device each time a need arises for some functions of a particular application. The terminal device executes the application with the downloaded program.

In the second application execution mode applications are executed on servers. For example a server sends drawing commands e.g. commands for displaying a HyperText Markup Language HTML document to browser software running on a terminal device so that a page is displayed on the terminal screen. The user may do some operations on the displayed screen which causes the browser to transmit a HyperText Transfer Protocol HTTP request to the server. The application running on the server executes data processing operations in response to the HTTP request from the terminal device and transmits drawing commands back to the terminal device to display the execution result.

In the third application execution mode applications are previously installed in terminal devices. The user sets up an application program in a storage medium of his or her terminal device so that the application is ready to run. For example the user interacts with the terminal device to install an application in an executable state.

Applications are executed in one of the above three execution modes. Such applications may obtain a user root URL by using one of the following four methods.

The first method provides a display screen to prompt the user to enter his or her user root URL and obtains a URL entered through the screen.

The second method permits the user to enter his or her user root URL at a convenient time and stores the entered URL in an appropriate storage space for future reference by the applications. This method actually use the above first method to obtain a user root URL for the first time. The obtained user root URL is then stored in an appropriate storage space.

The third method obtains a user root URL from a server simultaneously with downloading of an application program. For example a server prepares endpoint URLs corresponding to individual users so that the users receive a document personalized for them when they make access to their corresponding endpoint URLs. The endpoint URL prepared for a user by the server may also be accessed from the terminal device of the user when he or she wishes to use an application on the server. In response the server sends a relevant application program back to the requesting terminal device together with a user root URL that is previously associated with the endpoint URL.

The fourth method utilizes OpenID an identifier for authentication applicable to multiple websites to obtain user root URLs. A single OpenID enables its owner to be authenticated at a plurality of websites. For one example of the fourth method a website managing OpenID notifies an application of a user root URL. An OpenID may include information on the user root URL of a user and the user logs in to an application by using such an OpenID. The application obtains the user root URL from the log in OpenID that the user has used.

An application specific URL is determined by obtaining a path directory names etc that uniquely identifies an application under a given user root URL. This operation may be achieved with for example one of the following three methods.

The first method determines an access target URL according to a rule base. For example a rule base is defined as a set of rules for generating directory names that uniquely identify each different application. The application produces an application specific URL for a specific application by appending such directory names of the application to the given user root URL in accordance with the rule base.

The second method relies on an application specific URL list prepared in a server corresponding to a user root URL. This application specific URL list is a collection of application specific URLs associated with the identifiers of applications. When a specific user root URL is given its corresponding server provides an application specific URL list to the application. The application then obtains its own application specific URL from the application specific URL list. Such application specific URL lists may be access restricted. For example the server may request transmission of an authentication token from applications each time they try to use the server s application specific URL list. Authentication tokens may comply with for example the OAuth protocol which transfers authentication of Application Programming Interface API access. The server performs user authentication based on the received authentication token.

The third method involves querying from an application to a server corresponding the given user root URL as to an application specific URL relevant to the application. The third method may also use the aforementioned authentication tokens or the like for a server to restrict queries about application specific URLs.

The above described three application execution modes four methods for obtaining user root URLs and three methods for determining application specific URLs may be combined in various ways. It is therefore possible to provide a variety of embodiments based on such combinations. The following sections will describe in detail some of those possible embodiments.

This section describes a second embodiment. The second embodiment implements a combination of the foregoing first application execution mode third method for obtaining user root URLs and second method for determining application specific URLs.

The application servers and are computers configured to offer services with their own applications. Using his or her terminal device the user makes access to one of those application servers and to request and receive a desired service.

The data storage server is a computer configured to store personal data of the user . Specifically the data storage server stores personal data of the user which may be used by different applications that the application servers and provide.

In the illustrated network the application servers and and data storage server are distinguished from each other by their domain names. In the example of the three application servers and have domain names of app1.example.com app2.isv1.example and app3.a soft.example respectively. The data storage server has a domain name of api.data service.example .

The above devices on the network communicate with each other according to for example the HTTP or the HTTP over Secure Socket Layer HTTPS .

The RAM serves as primary storage of the terminal device . Specifically the RAM is used to temporarily store at least some of the operating system OS programs and application programs that the CPU executes in addition to other various data objects that the CPU manipulates at runtime.

Other devices on the bus are a hard disk drive HDD a graphics processor an input device interface an optical disc drive and a communication interface .

The HDD writes and reads data magnetically on its internal platters. The HDD serves as secondary storage of the terminal device to store program and data files of the operating system and applications. Flash memory and other semiconductor memory devices may also serve as secondary storage.

The graphics processor coupled to a monitor produces video images in accordance with drawing commands from the CPU and displays them on a screen of the monitor . The monitor may be for example a cathode ray tube CRT display or a liquid crystal display.

The input device interface is connected to input devices such as a keyboard and a mouse and supplies signals from those devices to the CPU . The mouse is a pointing device which may be replaced with other kinds of pointing devices such as touchscreen tablet touchpad and trackball.

The optical disc drive reads out data encoded on an optical disc by using laser light. The optical disc is a portable data storage medium the data recorded on which can be read as a reflection of light. The optical disc may be a digital versatile disc DVD DVD RAM compact disc read only memory CD ROM CD Recordable CD R or CD Rewritable CD RW for example.

The communication interface is connected to a network and exchanges data with other computers over the network .

The above described hardware platform may be used to realize the processing functions of the embodiments discussed in this description. While only depicts a terminal device as an example of hardware configuration the same hardware configuration may similarly be used to implement the application servers and and data storage server as well as the foregoing information processing apparatus according to the first embodiment discussed in .

The browser parses an HTML document and displays its content on a screen of the monitor . If a given structured document contains a script for execution of an application the browser downloads a relevant application program from the application server and stores it in RAM or HDD of the terminal device . Here the browser extracts a user root URL of the user from the HTML document as it includes a script for execution of an application . The extracted user root URL points to a specific storage space in the data storage server in which data of the user is stored. The browser includes this user root URL as a parameter of a start command when issuing it to launch the application .

The application performs data processing operations requested by the user . When launched the application makes access to the data storage server by using the above noted parameter of the user root URL to obtain an application specific URL list for the user . This application specific URL list is a collection of application specific URLs associated with various applications that the user may use. The application finds its own associated application specific URL from the obtained application specific URL list . The application produces an access target URL when a need arises for access to personal data of the user during the course of data processing. For example the obtained application specific URL points to a specific place in the directory structure which the application regards as the reference location. The application produces an access target URL by appending additional location information to the application specific URL where the additional location information points to the location of intended data by following the directory structure from the reference location. The application uses this access target URL to execute a data access to the data storage server .

The application server includes a storage unit a document serving unit and a root URL determination unit .

The storage unit contains a plurality of HTML documents . . . an application program and a root URL management table . The application program is a program code describing what data processing operations the application is supposed to execute. The root URL management table is a collection of user root URLs of different users.

The document serving unit transmits an HTML document or an application program to the terminal device when so requested from the browser in the terminal device . The document serving unit has an endpoint URL associated with the user and an authentication procedure may be implemented to grant access to this endpoint URL. When there is an access request from the browser to the endpoint URL the document serving unit sends the terminal device an HTML document that is associated with the requesting user . This HTML document includes a script for execution of the application program . The document serving unit obtains a user root URL of the user from the root URL determination unit and inserts the user root URL into the HTML document to be transmitted. The document serving unit may also transmit an application program to the browser in the terminal device when the browser requests it.

Upon request from the document serving unit the root URL determination unit consults the root URL management table to find a user root URL of the user who wishes to use the application program . The root URL determination unit then informs the document serving unit of the user root URL that is found.

The data storage server includes a storage unit an application specific URL management unit and a data management unit .

The storage unit stores files . . . and an application specific URL list . The files . . . contain personal data of the user . The application specific URL list is a collection of application specific URLs each indicating the location of a data file used by a specific application. As the user may use a plurality of applications the application specific URL list includes a plurality of such application specific URLs.

The application specific URL management unit sends an application specific URL list upon request from the application . For example the application specific URL management unit may be configured to send an application specific URL list only if the user of the application is successfully authenticated in advance.

The data management unit makes access to a specified file upon receipt of an access request from the application . In one case the access request asks for retrieval of a specific file. The data management unit thus reads and transmits the requested file to the application . Here the location of the requested file is specified by an access target URL. In another case the access request specifies a file to be written. The data management unit then writes the specified file to the specified location in the storage unit .

The user ID field contains an identifier user ID for uniquely identifying each user of the application server .

The endpoint URL field is associated with a specific user ID to indicate the endpoint URL of a user identified by that user ID.

The user root URL field is also associated with a specific user ID to indicate the user root URL of a user identified by that user ID.

The root URL determination unit determines the user root URL of a user in question by consulting this root URL management table . Suppose for example that the user makes access to an endpoint URL corresponding to his or her user ID of AB1234. In this case the root URL determination unit extracts a user root URL associated with the user ID AB1234 and informs the document serving unit of the extracted user root URL as being relevant to the requesting user .

The exemplary endpoint URL seen in is http app1.example userUrl http 253A 252F 252Fdata.example 252Fshimono for user ID AB1234 . This endpoint URL indicates that a document serving unit identified by the URL http app1.example is supposed to receive a user root URL of http api.data.example user1 as the value of a parameter named userUrl . When there is a request specifying the above endpoint URL the document serving unit returns a response including the received URL http api.data.example user1 as a user root URL for configuration of the application .

The determination method executed by the root URL determination unit involves a logic to produce a user root URL from a given endpoint URL. One possible logic is to use a table for looking up such URLs. Another possible logic is to produce a URL by parsing query parameters.

Although the above described root URL determination unit finds a user root URL by consulting a table with the endpoint URL corresponding to a user ID the embodiment of the root URL determination unit is not limited to that specific method. For example another possible method is to produce a user root URL by manipulating character strings from the endpoint URL corresponding to a user ID. Yet another possible method is to determine a user root URL by consulting a table with a user ID submitted in the preceding user authentication.

Also the above described processing may use other tables than the one illustrated in . The exemplary table of is formed from three associated data fields of user ID endpoint URL and user root URL. One variation of this table may only combine two of those data fields e.g. user ID and user root URL or endpoint URL and user root URL.

The above described second embodiment uses a root URL management table to manage user root URLs. Alternatively it is also possible to embed a user root URL in HTML documents before they are provided to users. For example a user root URL corresponding to an endpoint URL is previously written in the HTML document so that the user root URL will be transmitted as part of the document in response to an access request to the endpoint URL. This implementation eliminates the need for the root URL determination unit and root URL management table .

Located below the user1 directory are a directory named app1 a directory named app2 and a directory named app3. The app1 directory is for storing personal data of the user which the application provided in one application server may use. The app2 directory is for storing personal data of the user which the application provided in another application server may use. The app3 directory is for storing personal data of the user which the application provided in yet another application server may use.

A plurality of files . . . are stored in the app1 directory . One file is named file1 . Another file is named file2 . Yet another file is named file3 .

A file named url list is stored in the user1 directory . This url list file contains an application specific URL list .

For example an application specific URL http api.data service.example user1 app1 is associated with a domain name app1.example.com . Another application specific URL http api.data service.example user1 app2 is associated with another domain name app2.isv1.example . Yet another application specific URL http api.data service.example user1 app3 is associated with yet another domain name app3.a soft.example .

The data processing unit responsive to a start request from the browser executes data processing operations according to commands or the like from a user . When the data processing operations use personal data of the user the data processing unit sends an access request to the access target URL generation unit together with an application local path pointing to the personal data by following the directories from a specific reference location. More specifically this application local path is a combination of a relative path of a personal data file with respect to the reference location in the directory structure and the name of the personal data file. The data processing unit also receives the result of the access request from the accessing unit .

The user root URL obtaining unit obtains location information from the browser . For example the user root URL obtaining unit obtains a user root URL specified as a parameter in the activation request from the browser and enters the obtained user root URL in the user root URL storage unit .

The user root URL storage unit stores the user root URL. For example the user root URL storage unit may be implemented as part of storage space of the RAM or HDD .

The application specific URL determination unit determines an application specific URL based on the user root URL stored in the user root URL storage unit . For example the application specific URL determination unit makes access to the data storage server to request a file named url list residing immediately below the user root URL. In response to this file request the data storage server returns an application specific URL list . The application specific URL determination unit determines its application specific URL by consulting this application specific URL list . Suppose that for example that the application specific URL determination unit is previously informed of a specific domain name that indicates the application server providing the application . In this case the application specific URL determination unit selects an application specific URL associated with the given domain name as being relevant to the application itself. The application specific URL determination unit stores the selected application specific URL in the application specific URL storage unit .

The application specific URL storage unit holds the application specific URL. For example the application specific URL storage unit may be implemented as part of storage space of the RAM or HDD .

The access target URL generation unit produces an access target URL based on the application specific URL stored in the application specific URL storage unit and the foregoing application local path in the access request from the data processing unit . The access target URL generation unit passes the produced access target URL to the accessing unit .

The accessing unit makes access to the access target URL over the network . The access target URL produced by the application actually points to a particular file in the data storage server . The accessing unit thus submits an access request to the data storage server and receives a response indicating the result from the data storage server depending on the type of access request. In the case of a data read request the response contains data read out of the access target. In the case of a data write request the response indicates the result of the requested write operation.

The above described functions of devices enable the data storage server to manage personal data of the user in a consolidated way while the data may be used by a plurality of applications provided by applications servers and . The next section will describe a procedure up to a data access assuming that the application provided by the application server uses data in the data storage server .

 Step S The user enters an application start command to the browser in his or her terminal device specifying a URL associated with himself or herself. For example the user selects a shortcut icon associated with a particular URL by using a pointing device thus entering an application start command.

 Step S Upon receipt of the GET request the document serving unit in the application server retrieves an HTML document from the specified location in the storage unit . The document serving unit submits a user root URL determination request to the root URL determination unit .

 Step S In response to the user root URL determination request the root URL determination unit determines what user root URL corresponds to the user . Suppose for example that the user has been authenticated with his or her user ID of AB1234 and has issued an application start command specifying an endpoint URL corresponding to that user ID. In this case the root URL determination unit consults the root URL management table to extract therefrom a user root URL associated with the user ID AB1234 thus determining what user root URL corresponds to the user .

 Step S The root URL determination unit sends the determined user root URL to the document serving unit as its response.

 Step S The document serving unit sends an HTML document containing the received user root URL to the terminal device as its response.

 Step S The browser in the terminal device evaluates the HTML document received from the application server . That is the browser analyzes what is written in the HTML document and detects for example a tag that indicates an embedded object.

 Step S When the object embedding tag detected in the HTML document specifies an application program the browser sends a request to the application server to get that application program .

 Step S In the application server the document serving unit retrieves the application program from its storage unit and sends the retrieved application program back to the terminal device as its response.

 Step S Upon receipt of the application program from the application server the browser in the terminal device stores the application program in its local RAM for example. The browser then sends the OS an execution command for the application program with a parameter specifying the user root URL thus launching an application .

 Step S The launched application issues a query for application specific URL list to the data storage server specifying the user root URL.

 Step S In response to the query from the terminal device the application specific URL management unit in the data storage server returns an application specific URL list to the terminal device .

 Step S In the terminal device the application searches the received application specific URL list to find out which application specific URL is relevant to the application itself. The application then stores its own application specific URL in the application specific URL storage unit .

 Step S The application sends data for an initial screen to the browser . The browser displays the HTML document received at step S on the monitor embedding an initial screen of the application see in the resulting view.

 Step S Viewing the screen on the monitor the user operates his or her keyboard and mouse to enter a command for the application to execute data processing operations.

 Step S The application executes data processing operations requested by the user . To use personal data of the user the application produces an access target URL of the personal data by appending its application local path to the application specific URL.

 Step S The application makes access to the data storage server specifying the produced access target URL.

 Step S In the data storage server the data management unit executes access to the specified access target URL and returns its result to the terminal device .

 Step S The application in the terminal device continues the data processing operations according to the access result received from the data storage server . The application then sends data indicating the result of data processing operations back to the browser . The browser produces a screen on the monitor to display what the application has done see .

The above steps permit the application to execute data processing operations using personal data of the requesting user which is stored in the data storage server . It is noted that the application obtains a user root URL from the HTML document supplied from the application server .

This HTML document causes the browser to obtain an application program from the application server according to what is designated in the data attribute in the tag . With the obtained application program the browser starts execution of an application specifying the user root URL in the value attribute of a tag as a parameter for the execution.

Upon startup of the application the terminal device outputs an initial screen of the application on the monitor .

To display schedules in a specified month the application has to retrieve relevant personal data of the user . To this end the application produces an access target URL by appending an application local path to the application specific URL and sends a request to the access target URL to get desired data.

In response the data storage server sends the terminal device a file describing a single month schedule of the user . The application then takes schedule data out of the file received from the data storage server and displays it on a monitor screen.

As can be seen from the above example the application provided by the application server obtains personal data of the user from the data storage server . The same applies to other applications provided by other application servers and . In other words the personal data of the user can be managed only in one data storage server .

This section describes a third embodiment. The third embodiment implements a combination of the foregoing first application execution mode third method for obtaining user root URLs and third method for determining application specific URLs. The third embodiment assumes the same system configuration illustrated in for the second embodiment. While the third embodiment uses the same components of each device discussed in for the second embodiment at least some of those components operate differently from the second embodiment. The following description is directed to such dissimilar features of the third embodiment while using same reference numerals of the components seen in .

 Step S The started application issues a query for an application specific URL to the data storage server specifying the user root URL and the identifier of the application itself. The application identifier may be for example a character string e.g. http app1.example.com that contains the domain name of the application server hosting the application .

 Step S In response to the query from the terminal device the application specific URL management unit in the data storage server determines an application specific URL. For example the application specific URL management unit consults the application specific URL list for the user to find an application specific URL corresponding the identifier of the application that is specified in the query.

 Step S The application specific URL management unit sends the found application specific URL to the terminal device as its response.

 Step S In the terminal device the application stores the received application specific URL in the application specific URL storage unit .

The above steps of the third embodiment enable the data storage server to determine which application specific URL corresponds to the application . According to the foregoing second embodiment the data storage server returns a whole list of application specific URLs to the terminal device . In contrast the data storage server in the third embodiment only returns a part of the list i.e. a single application specific URL that is found to be relevant thus reducing the amount of communication data.

This section describes a fourth embodiment. The fourth embodiment implements a combination of the foregoing first application execution mode third method for obtaining user root URLs and first method for determining application specific URLs. The fourth embodiment assumes the same system configuration illustrated in for the second embodiment. While the fourth embodiment uses the same components of the terminal device and application servers discussed in for the second embodiment at least some of those components of the fourth embodiment operate differently from the second embodiment.

Another difference is that the fourth embodiment includes no application specific URL management unit in its data storage server whereas the storage unit and data management unit remain as in the second embodiment. The data storage server stores in its storage unit a plurality of files including a personal data file of the user . The fourth embodiment however does not include application specific URL lists.

As can be seen from the above the components of the fourth embodiment are a subset of those discussed in for the second embodiment. The following description is directed to unlike features of the fourth embodiment while using same reference numerals of the components seen in .

 Step S The started application sends data of an initial screen to the browser without issuing queries for an application specific URL list to the data storage server . The browser displays the HTML document received at step S on the monitor after embedding an initial screen of the application .

 Step S Viewing the screen on the monitor the user operates his or her keyboard and mouse to enter a command for the application to execute data processing operations.

 Step S The application produces an access target URL according to a rule base. For this purpose the application is configured with a predefined set of rules for generation of access target URLs. For example the rules may define a procedure that produces first a unique character string identifying an application forms a path that includes the produced character string as a directory name and appends the path to the given user root URL. The unique character string for an application may include for example the domain name of the application server hosting the application .

As can be seen from the above the fourth embodiment uses a rule base to determine application specific URLs thus eliminating the need for configuring the data storage server to manage application specific URLs. The fourth embodiment also eliminates query and response interactions about application specific URL list between the terminal device and data storage server before launching an application thus reducing the burden of communication.

This section describes a fifth embodiment. The fifth embodiment implements a combination of the foregoing first application execution mode fourth method for obtaining user root URLs and second method for determining application specific URLs.

The illustrated application server includes a storage unit and a document serving unit . The storage unit stores a plurality of HTML documents . . . and an application program describing what the application is supposed to execute. The document serving unit transmits an HTML document and the application program upon request from the terminal device

The illustrated data storage server includes a storage unit an application specific URL management unit a data management unit and an authentication unit . The storage unit application specific URL management unit and data management unit function in the same way as their respective counterparts in the data storage server discussed in for the second embodiment.

The authentication unit provides a user authentication mechanism based on the OpenID standard. The authentication unit authenticates a user based on for example a combination of ID and password received as a credential of the user. The authentication unit returns an affirmative response to the sender of the credential when it proves the sender s identity as an authorized user.

 Step S The user enters an application start command to the browser in his or her terminal device specifying URL of an application server

 Step S Upon receipt of the GET request the document serving unit in the application server retrieves an HTML document from the specified location in the storage unit . The document serving unit transmits this HTML document back to the requesting terminal device

 Step S The browser in the terminal device evaluates the HTML document received from the application server

 Step S When an object embedding tag is detected in the HTML document and if the tag specifies an application program the browser sends a request to the application server to get that application program .

 Step S The document serving unit in the application server retrieves the requested application program from the storage unit and transmits it to the requesting terminal device

 Step S The browser in the terminal device stores the received application program in its local RAM for example. The browser then sends the OS an execution command for the application program thus starting an application

 Step S The started application sends data of an OpenID entry screen to the browser . The browser produces a screen on the monitor to prompt the user to enter his or her OpenID see .

 Step S The application requests the browser to produce a new pop up window. For example the User Experience UX Extension an authentication technique of OpenID may be used for this pop up window.

 Step S In response to the OpenID screen request the authentication unit in the data storage server sends an HTML document to the terminal device for login operation. Based on this HTML document the browser in the terminal device produces a pop up log in window see .

Afterwards the browser produces a pop up window for login operation in response to a request from the application

 Step S The user enters a credential in the login window to prove his or her legitimacy. For example the user enters his or her ID into one text box in the login window . This ID is supposed to have been registered with the data storage server . The user also enters his or her password into another text box . The entered ID password pair serves as the login credential of the user .

 Step S In the data storage server the authentication unit executes authentication of the user based on the received credential.

 Step S When the user is authenticated properly the authentication unit sends the terminal device a redirect response indicating the successful authentication.

 Step S In the terminal device the browser informs the application of the event of successful authentication.

 Step S Because of the successful authentication the application is sure that what the user has entered as an OpenID at step S is his or her genuine user root URL. Accordingly the application sends a query for an application specific URL list to the data storage server specifying the confirmed user root URL of the user .

The above described steps permit an application to obtain a correct user root URL proved through an OpenID authentication. The use of OpenID enables the user to have access to a plurality of applications with a single credential. What this means to the user is a reduced burden of credential management.

This section describes a sixth embodiment. The sixth embodiment implements a combination of the foregoing third application execution mode second method for obtaining user root URLs and third method for determining application specific URLs. It is noted that no application servers are used in the sixth embodiment unlike the foregoing second to fifth embodiments.

The data storage server includes a storage unit an application specific URL management unit and a data management unit . These components of the data storage server function in the same way as their respective counterparts in the data storage server according to the second embodiment discussed in .

 Step S If no application specific URL is present the application displays a user root URL entry screen on the monitor see .

 Step S The started application in the terminal device issues a query for an application specific URL list to the data storage server based on the user root URL entered by the user .

 Step S In response to the query from the terminal device the application specific URL management unit in the data storage server returns an application specific URL list to the terminal device

 Step S In the terminal device the application searches the received application specific URL list to find out which application specific URL is relevant to the application itself. The application then stores its own application specific URL locally.

 Step S The user operates his or her keyboard and mouse to enter a command for the application to execute data processing operations.

 Step S The application executes data processing operations requested by the user . To use personal data of the user the application produces an access target URL of the personal data by appending its application local path to the application specific URL.

 Step S The application makes access to the data storage server specifying the produced access target URL.

 Step S In the data storage server the data management unit executes access to the specified access target URL and returns its result to the terminal device

 Step S The application in the terminal device continues the data processing operations according to the access result received from the data storage server . The application displays the result of data processing operations on a screen of the monitor .

As can be seen from the above the sixth embodiment enables the data storage server to manage personal data of the user for use by a pre installed application in the terminal device

This section describes a seventh embodiment. The seventh embodiment implements a combination of the foregoing second application execution mode second method for obtaining user root URLs and second method for determining application specific URLs.

The storage unit stores a root URL management table . The application functions in the same way as the application discussed in for the second embodiment except that it is configured to communicate with the browser via a network . The application obtains a user root URL from the root URL management table in the storage unit

The illustrated data storage server includes a storage unit an application specific URL management unit and a data management unit . These components of the data storage server function in the same way as their respective counterparts in the data storage server discussed in for the second embodiment.

 Step S The user logs in to an application through a login screen produced by the browser in the terminal device see . Here the user specifies the application by entering its URL.

 Step S The browser sends a credential to the application server . This credential may be for example a combination of the user s ID and password.

 Step S In the application server the application performs user authentication upon receipt of the credential. When the user is authenticated properly the application consults the root URL management table to find a user root URL associated with user ID of the user .

 Step S The application issues a query for an application specific URL list to the data storage server specifying the above user root URL.

 Step S In response to the query from the application server the application specific URL management unit in the data storage server returns an application specific URL list to the requesting application server

 Step S In the application server the application searches the received application specific URL list to find out which application specific URL is relevant to the application itself.

 Step S The application stores its own application specific URL associating the URL with the current communication session with the terminal device

 Step S The application sends the terminal device an HTML document having a session cookie. In the terminal device the browser displays a screen for the application on the monitor .

 Step S Viewing the screen on the monitor the user operates his or her keyboard and mouse to enter a command to the application via the browser

 Step S In response to the command from the user the browser sends the application server an HTTP request with a session cookie.

 Step S The application in the application server executes requested data processing operations. During this course the application may use personal data of the user . In that case the application obtains an application specific URL associated with its current communication session with the terminal device

 Step S The application produces an access target URL by appending an application local path to the obtained application specific URL.

 Step S The application makes access to the data storage server specifying the produced access target URL.

 Step S In the data storage server the data management unit executes access to the specified access target URL and returns its result to the application server

 Step S The application in the application server continues the data processing operations according to the access result received from the data storage server . The application then sends data indicating the result of data processing operations back to the terminal device . In response the browser in the terminal device produces a screen on the monitor to display what the application has done.

As can be seen from the above the seventh embodiment enables the data storage server to manage personal data of the user for access from an application running on an application server

While the first method for obtaining user root URLs is not explained in the above described embodiments the first method is actually used as part of the procedure of the second method for obtaining user root URLs. Referring to for example the sequence diagram of what is done at steps S and S of the sixth embodiment corresponds to the first method for obtaining user root URLs.

The functions of the above described embodiments may be implemented as a computer application. That is computer programs are provided for each of the terminal device application server and data storage server to implement the functions that these devices are supposed to do. Computers execute such programs to realize the processing functions discussed in the preceding sections. The programs may be encoded in a computer readable storage medium. Computer readable storage media include magnetic storage devices optical discs magneto optical storage media semiconductor memory devices and others. Magnetic storage devices include hard disk drives HDD flexible disks FD and magnetic tapes for example. Optical disc media include DVD DVD RAM CD ROM CD RW and others. Magneto optical storage media include magneto optical discs MO for example.

Portable storage media such as DVD and CD ROM are used for distribution of program products. Network based distribution of programs may also be possible in which case several master program files are made available on a server computer for downloading to other computers via a network.

For example a computer stores programs in its local storage device which have previously been installed from a portable storage medium or downloaded from a server computer. The computer executes programs read out of the local storage device thereby performing the programmed functions. Where appropriate the computer may execute a program read out of a portable storage medium without installing them in its local storage device. Another alternative method is that the computer executes a program upon downloading from a server computer.

It is further noted that the above processing functions may be executed wholly or partly by a digital signal processor DSP application specific integrated circuit ASIC programmable logic device PLD or other electronic circuits.

The proposed techniques make it easier to manage personal data of a user in a user specified data storage device for use in data processing operations.

All examples and conditional language provided herein are intended for the pedagogical purposes of aiding the reader in understanding the invention and the concepts contributed by the inventor to further the art and are not to be construed as limitations to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although one or more embodiments of the present invention have been described in detail it should be understood that various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

