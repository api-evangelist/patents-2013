---

title: Method of linking to and monitoring machining devices through a cloud service
abstract: A method of linking to and monitoring machining devices through the cloud service enables a user to use a cloud app on the cloud to link to machining device at a specific client through a cloud service. The cloud service has API function commands for the cloud app to call and use. The client has an integrated execution module to connect to the machining device. The integrated execution module on the client links to the cloud service through a cloud connection module.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09363307&OS=09363307&RS=09363307
owner: Precision Machinery Research & Development Center
number: 09363307
owner_city: Taichung
owner_country: TW
publication_date: 20130802
---
The invention relates to a connection method of machining device and in particular to a method of linking to and monitoring machining device through the cloud service.

With the development of information technology remote monitoring and control of certain popularity nowadays have been applied to CNC machining devices. With the popularization of Internet network transmission has become a primary feature of controllers for various brands of machining devices. One can use a computer or the equivalent to remotely monitor or control the device by using a controller with such a function.

At the present stage however manufacturers have production facilities at different regions in order to provide consumers immediate services and to reduce transportation or labor costs. It is then a common problem for the manufacturers to concurrently monitor in real time machining devices at different production facilities. Furthermore factories of most manufacturers usually have a variety of different brands of machining devices each of which has a corresponding API Application Programming Interface . They cannot communicate with each other. This further causes great troubles in integration and control for manufacturers.

An objective of the invention is to provide a method of linking to and monitoring machining devices via a cloud service and having the effect of monitoring operating in real time machining devices located at different production facilities.

Another objective of the invention is to provide a method of linking to and monitoring machining devices via a cloud service that utilizes the advantages of cloud computing to process and analyze a huge amount of data within a short time.

A further objective of the invention is to provide a method of linking to and monitoring machining devices via a cloud service that utilizes an integrated execution module integrated with API s for machining devices of different brands to connect simultaneously to those machining devices.

To achieve the above mentioned objectives the disclosed method of linking to and monitoring machining devices via a cloud service enables a user to use a cloud app to connect to machining devices of a specific client via a cloud service. The cloud service includes API function commands for the cloud app to call and use. Each client has an integrated execution module for connections with machining devices. The integrated execution module of each client connects to the cloud service via a cloud connection module. The method includes the following steps. A user uses the cloud app to call and use the API function command of the cloud service. The cloud connection module connected with the cloud service also receives the API function command of the cloud service. The cloud connection module follows the API function command to obtain corresponding machining device information via the integrated execution module. The information is transmitted back to the cloud app via the cloud connection module and the cloud service.

Moreover the cloud app and the cloud connection module of the integrated execution module of the client are linked to the cloud service via the Internet.

Besides the cloud service has a registration table that establishes identification ID information of the integrated execution module of at least one client and information of users that are allowed to the link to the integrated execution module. Before the integrated execution module of the client links to the cloud service via the cloud connection module the cloud service first uses the registration table to check whether the ID information carried by the cloud connection module has been established in the registration table. If it is already established then the connection is granted otherwise the link is disallowed. Before the user uses the cloud app to link to the cloud service the user has to first enter user information via the cloud app to the cloud service. The cloud service uses the registration table to check whether the user information has been registered. If it is already registered then the connection is granted otherwise the link is disallowed.

Preferably the ID information includes a hardware lock ID and an integrated execution module ID code. The user information includes a cloud app ID and an integrated execution module ID code. After the cloud app or the integrated execution module of the client is verified in the registration table of the cloud service it can link to the integrated execution module or cloud app of the same integrated execution module ID code via the cloud service.

Furthermore the cloud has a cloud database connected to the cloud service. The cloud database provides space for the cloud app so that the cloud app can use the cloud to process and analyze a huge amount of data within a short time. The integrated execution module of each client is further connected to a host database. When a huge amount of data is extracted they can be first saved in the host database. After the extraction is over the data are sent to the cloud database.

The integrated execution module of each of the clients integrates multiple sets of API s for connections with machining devices of particular brands. The integrated execution module generates a command thread according to the API s required by a machining device. The command thread is used to extract required information from the corresponding machining device.

Preferably the integrated execution module is connected with a common function runtime module. After the integrated execution module integrates the app interfaces it further establishes a common app interface and puts it in the common function runtime module. The common function runtime module has a plug in interface for defining the function names and data structure thereof. The developer can add it to their references and establish a naming space for calling to use.

The present invention will be apparent from the following detailed description which proceeds with reference to the accompanying drawings wherein the same references relate to the same elements.

Please refer to . The disclosed method of linking to and monitoring machining devices via a cloud service is implemented on a cloud service system. The cloud service system includes at least one cloud app a cloud service and a plurality of clients .

The cloud apps are stored on the cloud for a user to operate thereon. The cloud service links to the cloud apps via the Internet. The cloud service further has API function commands for the cloud apps to call and use. Each of the clients consists of at least one machining device and has an integrated execution module to connect to the machining devices thereof. The integrated execution module of each of the clients is connected to the cloud service via a cloud connection module and the Internet.

Besides the cloud service has a registration table that establishes identification ID information of the integrated execution module of at least one client and information of users that are allowed to the link to the integrated execution module of the client . Therefore the cloud apps and the integrated execution module of the client have to pass the privilege check of the registration table before connecting to the cloud service . Preferably the ID information includes a hardware lock ID and an integrated execution module ID code. The user information includes a cloud app ID and an integrated execution module ID code. After the cloud app or the integrated execution module of the client is verified in the registration table of the cloud service it can link to the integrated execution module or cloud app of the same integrated execution module ID code via the cloud service .

Furthermore the cloud has a cloud database connected to the cloud service . The cloud database provides the cloud app with buffer space so that the cloud app can use the cloud to process and analyze a huge amount of data within a short time. Thus the invention enjoys the advantages of cloud computing. The integrated execution module of each of the clients is further connected with a host database . When a huge amount of data is extracted they are first saved in the host database . After the extraction is over the data are transmitted again to the cloud database to overcome the issue of network speed between the cloud and the client .

As shown in the integrated execution module of each of the clients integrates multiple app interfaces for distinct brands of machining devices. The integrated execution module generates a command thread for the app interface of each machining device so as to extract necessary information from the corresponding machining device . The integrated execution module is further connected with a common function runtime module . After the integrated execution module integrates all of the app interfaces it further establishes a common app interface in the common function runtime module . The common function runtime module has a plug in interface for defining the function names and data structure thereof. Developers can add the plug in interface to their references and establish naming space for calling to use.

With the above mentioned features a developer can write or expand a micro app by himself. This is because of the common routine runtime module and the plug in interface allows the developer to use the function names and data structure defined by the plug in interface. The developer does not need to understand the app interface for the app interface of each individual brand. This greatly reduces the amount of codes and largely facilitates the development of apps. In view of different needs one can also build various customized apps for users.

Please refer to for the disclosed method of linking to and monitoring machining devices through a cloud service. The method involves the following steps 

Step The integrated execution module of a client links to the cloud service . After the integrated execution module of the client is turned on the cloud connection module immediately links to the cloud service via the Internet.

Step Verify the validity of the integrated execution module of the client . Before the integrated execution module of the client links to the cloud service via the cloud connection module the cloud service uses the registration table thereof to verify whether the ID information carried by the cloud connection module hardware lock ID and integrated execution module ID code has been established in the registration table . If it has been established then the connection is granted otherwise the connection is disallowed.

Step The cloud app connects to the cloud service . After a user uses the cloud app to enter specific user information cloud app ID and integrated execution module ID code the cloud app transmits the user information via the Internet to the cloud service .

Step Verify the validity of the cloud app . The cloud service uses the registration table thereof to verify whether the user information has been established therein. If it has been established then the connection is granted otherwise such as an attempt by a hacker the connection is disallowed.

After the above mentioned steps are completed the connection relation between the cloud app and the cloud connection module of the integrated execution module is shown in .

Please refer to . After the cloud app and the cloud connection module of the integrated execution module link to the cloud service as described above the action operation further involves the following steps 

Step The cloud service transmits the API function command being called to the cloud connection module of a specific integrated execution module.

Step After the cloud connection module receives the API function command the cloud connection module follows the API function command to obtain or write the corresponding machining device information via the integrated execution module .

Step After the cloud connection module completes the above mentioned obtaining or writing step the result is transmitted back to the cloud service .

Step After the cloud service receives the result returned by the cloud connection module it is sent to the corresponding cloud app according to the internal relations of the cloud service .

The invention enables a user to use the cloud app on the cloud to link to the machining device of a specific client . This allows the user to monitor control machining devices at different locations in real time through the cloud. With the registration table of the cloud service the user can bundle different cloud apps with the cloud connection modules of the corresponding clients so that different users can simultaneously monitor the machining devices of their own region via the cloud service without any conflict. The cloud apps are kept on the cloud for users to purchase or rent. The developers and cloud service provider can therefore profit from such services.

Moreover the invention uses the cloud apps to connect to the cloud connection module of the cloud service . Therefore the cloud apps are not limited by network settings. The invention directly uses the API function commands of the cloud service to rapidly obtain the machining device data of various clients . It does not need to worry about the problems of passing information back and forth between the clients and the server. Using the advantages of cloud computing the invention can finish the processing and analysis of a huge amount of data. The integrated execution module of each of the clients further connects to a host database . When a huge amount of data is accessed they are first saved in the host database . After the data access they are further sent to the cloud database thereby overcoming the problem of network speed between the cloud service and the clients .

Besides the integrated execution module of each of the clients integrates app interfaces of different brands of machining devices. Thus the invention can communicate simultaneously with different brands of machining devices. Operations of machining devices at different clients become simpler and quicker.

Although the invention has been described with reference to specific embodiments this description is not meant to be construed in a limiting sense. Various modifications of the disclosed embodiments as well as alternative embodiments will be apparent to people skilled in the art. Therefore it is contemplated that the appended claims will cover all modifications that fall within the true scope of the invention.

