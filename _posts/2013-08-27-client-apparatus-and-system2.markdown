---

title: Client apparatus and system
abstract: A data processing apparatus connected to an output apparatus and a service providing apparatus via a network, includes a destination setting storing unit that stores a setting of the destination for sending the output data; an output request accepting unit that accepts an output request of the output data from a user; and a sending control unit that controls to send the output data to the destination in accordance with the determined setting of the destination, wherein when the destination of the output data is the service providing apparatus, the sending control unit sends the output data to the service providing apparatus after having a log-in requesting unit perform a log-in to the service providing apparatus in accordance with the determined setting of the destination.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09648077&OS=09648077&RS=09648077
owner: Ricoh Company, Ltd.
number: 09648077
owner_city: Tokyo
owner_country: JP
publication_date: 20130827
---
A system is known in which a client terminal a print server and a multifunction device are connected via a network see Patent Document 1 for example .

In the known system print data is generated in the client terminal. Then the client terminal sends the generated print data to the print server and the print server stores the print data. The multifunction device obtains the print data from the print server when printing the print data.

Recently embodiments have been widely disseminated in which the client terminal uses various services typically a cloud service. In such embodiments the functions of the conventional print server and the multifunction device are provided as a print service so that a similar function as the print server is provided by the print service and it is unnecessary for a user to prepare a print server.

However in the conventional system user interfaces for a method in which the print data is sent from the client terminal to the image forming apparatus to have the print data printed and for a method in which the print data is printed by the print service are different and this was inconvenient for the user.

Further while not limited to printing this problem exists for an embodiment in which user interfaces are different for a method in which a process is executed by an apparatus such as an image forming apparatus a projector or the like and a method in which the process is executed by a service based on an instruction from a client terminal.

The present invention is made in light of the above problems and provides a data processing apparatus and a system capable of accepting execution of different processes via a common user interface.

According to an embodiment there is provided a data processing apparatus connected to an output apparatus that outputs output data and a service providing apparatus that provides a service related to the output data via a network including a destination setting storing unit that stores for a destination to which the output data is capable of being sent a setting of the destination for sending the output data an output request accepting unit that accepts an output request of the output data for which the destination is selected from a user and a sending control unit that determines the setting of the destination to which the output data is to be sent based on the output request of the output data for which the destination is selected and the setting of the destination stored in the destination setting storing unit and controls to send the output data to the destination in accordance with the determined setting of the destination wherein when the destination of the output data is the output apparatus the sending control unit sends the output data to the output apparatus in accordance with the determined setting of the destination and wherein when the destination of the output data is the service providing apparatus the sending control unit sends the output data to the service providing apparatus after having a log in requesting unit perform a log in to the service providing apparatus in accordance with the determined setting of the destination.

According to another embodiment there is provided a system in which a data processing apparatus that sends output data an output apparatus that outputs output data and a service providing apparatus that provides a service related to the output data are connected with each other via a network including a destination setting storing unit that stores for a destination to which the output data is capable of being sent a setting of the destination for sending the output data an output request accepting unit that accepts an output request of the output data for which the destination is selected from a user at the data processing apparatus and a sending control unit that determines the setting of the destination to which the output data is to be sent based on the output request of the output data for which the destination is selected and the setting of the destination stored in the destination setting storing unit and controls to send the output data to the destination in accordance with the determined setting of the destination wherein when the destination of the output data is the output apparatus the sending control unit sends the output data to the output apparatus in accordance with the determined setting of the destination and wherein when the destination of the output data is the service providing apparatus the sending control unit sends the output data to the service providing apparatus after having a log in requesting unit perform a log in to the service providing apparatus in accordance with the determined setting of the destination.

Note that also arbitrary combinations of the above described elements and any changes of expressions in the present invention made among methods devices systems recording media computer programs and so forth are valid as embodiments of the present invention.

The invention will be described herein with reference to illustrative embodiments. Those skilled in the art will recognize that many alternative embodiments can be accomplished using the teachings of the present invention and that the invention is not limited to the embodiments illustrated for explanatory purposes.

It is to be noted that in the explanation of the drawings the same components are given the same reference numerals and explanations are not repeated.

The system includes networks in companies A and B for example and a service providing system that provides a service such as a cloud service. The networks in the companies A and B are similar and thus the network in the company A is explained in the following.

In the company A a client terminal an image forming apparatus and a firewall FW that are connected to a private network N1 such as an in company network or the like are provided. The service providing system includes an access control apparatus and one or more service providing apparatus es such as a print service providing apparatus a scan service providing apparatus and a predetermined service providing apparatus that are connected to a network N2.

The network N1 and the network N3 are connected via the firewall FW provided at the network N1 side. The firewall FW is provided at a connecting point between the network N1 and the network N3 to relay a communication between the network N1 to the network N3.

The network N2 and the network N3 are connected via the access control apparatus provided at the network N2 side. The security of the network N2 is ensured by the access control apparatus .

The client terminal is an example of a terminal device. The client terminal may be a data processing apparatus computer system on which a general OS or the like is mounted. The client terminal has a wireless or wired communication function. The client terminal is a tablet PC a notebook PC or the like capable of being operated by a user.

The image forming apparatus has an image forming function and may be a multifunction device a copying machine a scanner a printer a laser printer or the like for example. The image forming apparatus has a wireless or wired communication function.

Although a single client terminal and a single image forming apparatus are exemplified in for each of the companies each of the companies may have a plurality of client terminals and a plurality of image forming apparatuses .

The print service providing apparatus provides a print service. The scan service providing apparatus provides a scan service. The predetermined service providing apparatus provides a predetermined service. The access control apparatus controls an access to the services such as the print service the scan service the predetermined service or the like provided by the print service providing apparatus the scan service providing apparatus the predetermined service providing apparatus or the like respectively.

The access control apparatus the print service providing apparatus the scan service providing apparatus and the predetermined service providing apparatus are actualized by a computer system including one or more data processing apparatus es .

The print service providing apparatus the scan service providing apparatus and the predetermined service providing apparatus of the system illustrated in may be actualized by a single computer or dispersedly actualized by a plurality of computers. Further a part of the functions of the service providing system may be provided at the company side the network N1 side in the system and the client terminal or the image forming apparatus may be provided on a network other than the network N1.

When a user wants to send print data from the client terminal which includes a printer driver to the image forming apparatus to have the image forming apparatus perform a printing operation the user may set the image forming apparatus as a destination to send the print data via a print setting screen or the like of application having a printing function which is mounted on the client terminal .

Similarly when the user wants to send the print data from the client terminal including the printer driver to the print service providing apparatus included in the service providing system to have the print data printed using the print service provided by the print service providing apparatus the user may set the print service providing apparatus as a destination to send the print data via the print setting screen or the like of the application having the printing function which is mounted on the client terminal .

Here when the access to the print service providing apparatus is controlled for example by the access control apparatus it is necessary for the client terminal to request a log in and send the print data to the print service providing apparatus after the log in is succeeded as will be explained later.

As such when it is necessary to perform a log in process in accordance with the destination to send the print data the client terminal appropriately performs a necessary process for sending the print data. The client terminal is configured to perform an appropriate process in accordance with the destination to send the print data print data as will be explained later.

In this embodiment a user can use a common user interface which is the print setting screen of the application having the printing function for a case when the print data is sent to the image forming apparatus to be printed and for a case when the print data is sent to the print service providing apparatus so that the print data is printed using the print service provided by the print service providing apparatus from the client terminal including the printer driver. Thus inconvenience for the user can be prevented.

The client terminal the access control apparatus the print service providing apparatus the scan service providing apparatus and the predetermined service providing apparatus illustrated in are actualized by a computer system having a hardware structure illustrated in for example. is a view illustrating an example of the hardware structure of the computer system of the first embodiment.

The computer system includes an input device a display device an external I F a Random Access Memory RAM a Read Only Memory ROM a Central Processing Unit CPU a communication I F a Hard Disk Drive HDD and the like that are connected with each other via a bus B.

The input device includes a keyboard a mouse a touch panel or the like and is used for the user to input various operation signals. The display device includes a display or the like and displays a processed result by the computer system .

The communication I F is an interface that connects the computer system to the network N1 N2 or N3. With this configuration the computer system is capable of performing data communication via the communication I F .

The HDD is a non volatile storing device that stores a program or data. The program or data stored in the HDD may be for example an Operating System OS which is basic software that controls the entirety of the computer system application software that provide various functions on the OS or the like. The HDD manages the stored program or data by a predetermined file system and or a data base DB .

The external I F is an interface for an external device. The external device may be a recording medium or the like. With this configuration the computer system is capable of reading and writing data on the recording medium via the external I F . The recording medium may be a flexible disk a Compact Disk CD a Digital Versatile Disk DVD an SD Memory card a Universal Serial Bus memory USB memory or the like.

The ROM is a non volatile semiconductor memory storing device capable of retaining a program or data even when a power source is not supplied. The ROM stores a program or data such as a Basic Input Output System BIOS that is executed when initiating the computer system OS setting network setting or the like. The RAM is a volatile semiconductor memory storing device that temporarily stores a program or data.

The CPU is an arithmetic apparatus that controls the entirety of the computer system or actualize functions of the computer system by reading the program or data from the storing device such as the ROM the HDD or the like to the RAM and executing processes.

The client terminal the access control apparatus the print service providing apparatus the scan service providing apparatus and the predetermined service providing apparatus illustrated in actualize various processes which will be explained later by the hardware structure of the computer system respectively.

The controller includes a CPU a RAM a ROM an NVRAM a HDD and the like. The ROM stores a program or data. The RAM temporarily stores a program or data. The NVRAM stores setting data or the like for example. The HDD stores a program or data.

The CPU controls the entirety of the image forming apparatus or actualizes the functions of the image forming apparatus by reading the program or data the setting data or the like from the ROM the NVRAM the HDD or the like to the RAM to execute processes.

The operation panel includes an input unit that accepts an input from a user and a display unit that displays various information. The external I F is an interface with an external device. The external device may be a recording medium or the like. With this configuration the image forming apparatus is capable of reading and writing data on the recording medium via the external I F . The recording medium may be an IC card a flexible disk a CD a DVD an SD memory card a USB memory or the like.

The communication I F is an interface that connects the image forming apparatus to the network N1. With this configuration the image forming apparatus is capable of performing data communication via the communication I F .

The printer has a function to print print data on a paper or the like. The scanner has a function to read image data from a document. The image forming apparatus of the embodiment actualizes various processes which will be explained later by the above described hardware structure.

The functions of the client terminal are actualized by components illustrated in for example. is a functional block diagram illustrating an example of a software structure of the client terminal of the first embodiment.

The client terminal includes an application a printer driver an input accepting unit which is an example of an output request accepting unit a sending unit a port monitor and a destination setting storing unit .

The application is software having a printing function such as software for word processing a spreadsheet program or the like. The printer driver is an example of a device driver that controls the image forming apparatus the print service providing apparatus or the like.

The printer driver includes actualizes an output data generating unit and an output setting unit . The output data generating unit generates print data as an example of output data. The output setting unit accepts a print setting as an example of an output setting.

The input accepting unit accepts an input of a user operation such as a contacting operation to a touch panel an input operation of a keyboard or the like. The sending unit sends the print data for example to the image forming apparatus or the print service providing apparatus of the service providing system .

The port monitor controls an I O port of the image forming apparatus or the service providing system side. The port monitor includes a destination registration unit an output data sending control unit which is an example of an output data sending control unit and a log in requesting unit .

The destination registration unit accepts a setting of a destination of the print data from the user via the port and registers the setting of the destination in the destination setting storing unit . The output data sending control unit controls the destination to send the print data based on the setting of the destination registered in the destination setting storing unit . The log in requesting unit requests log in to the print service providing apparatus for example to the service providing system using input authentication information such as user name a password or the like. The destination setting storing unit stores a setting of a destination of the print data for example.

The functions of the image forming apparatus are actualized by components illustrated in for example. is a functional block diagram illustrating an example of a software structure of the image forming apparatus of the first embodiment.

The image forming apparatus includes an input accepting unit an output unit a setting data storing unit and application for using print service .

The input accepting unit accepts an input of a user operation such as a contacting operation to a touch panel an input operation of a keyboard or the like. The output unit outputs a received job. For example the output unit prints received print data. The setting data storing unit stores a company code and device authentication information that are previously determined which will be explained later.

The application for using print service is software for using the print service provided by the print service providing apparatus . The application for using print service includes actualizes a log in requesting unit and a data process requesting unit .

The log in requesting unit requests log in to the print service providing apparatus for example to the service providing system using authentication information input by a user operation such as user name a password or the like. The data process requesting unit requests the print service providing apparatus to perform data processing such as sending a print data list or print data.

The functions of the service providing system of the first embodiment are actualized by components illustrated in for example. is a functional block diagram illustrating an example of a software structure of the service providing system of the first embodiment.

The service providing system includes service application a platform a management data storing unit and platform application programming interface platform API .

The service application includes print service application scan service application and one or more predetermined service application for example. The print service application is application that provides the print service. The scan service application is application that provides the scan service. The predetermined service application is application that provides the predetermined service.

The platform API is an interface for the service application such as the print service application the scan service application the predetermined service application or the like to use the platform . The platform API is an interface previously defined for the platform to receive a request from the service application and is composed of a function a class or the like for example. When the service providing system is dispersedly composed of a plurality of data processing apparatuses the platform API may be a Web API that is available via a network for example.

The platform includes an authentication process unit a device communication unit a data process unit and a session control unit for example.

The authentication process unit performs an authentication based on a log in request from the client terminal or the image forming apparatus . The device communication unit communicates with the client terminal or the image forming apparatus . The data process unit performs data processing based on a request from the service application . The session control unit controls a session between the client terminal or the image forming apparatus .

The management data storing unit includes a company management data storing unit a user management data storing unit a device management data storing unit a data management data storing unit and a data storage for example. The company management data storing unit stores company management data which will be explained later. The user management data storing unit stores user management data which will be explained later. The device management data storing unit stores device management data which will be explained later. The data management data storing unit stores data management data which will be explained later. The data storage stores other data or the like.

The print service application of the service providing system illustrated in is actualized by process blocks illustrated in . is a functional block diagram illustrating an example of the print service application of the first embodiment. The print service application includes a data analyzing unit an output data management unit a process requesting unit and an output data management data storing unit .

The data analyzing unit determines whether a data conversion is necessary for data sent from the client terminal by analyzing the data. For example when the data sent from the client terminal is application data web data or the like the data analyzing unit determines that it is necessary to convert the received data to print data.

The output data management unit manages the print data for example sent from the client terminal by output data management data which will be explained later. The process requesting unit requests the data process unit of the platform to perform the data processing. The output data management data storing unit stores the output data management data which will be explained later.

The company code specifies a group such as a company an organization or the like. The company code is unique to each company.

Although the word company is used here the company code is not limited to a code to identify a company. The company code may be information for specifying a set of one or more user s or one or more image forming apparatus es . The company code may be identification information or the like that identifies a contract to a group of user s or the image forming apparatus es .

The user management data manages data for each of the company codes. The user name and the password are data for specifying a user at the service providing system side. The user name may be user ID for example. The password may be optional.

Further for the user name information for identifying an electronic medium IC card for example possessed by the user the client terminal or the image forming apparatus card ID serial ID of the image forming apparatus or the like telephone number or the like may be used instead or used with combination with the user name. Further the user name corresponding to the same company code should be unique to each other however for the different company codes the same user name may be used.

In step S a port monitor A which will be the port monitor is installed in the client terminal in order to add a port of the print service providing apparatus as a usable port to the client terminal . By the port monitor A the client terminal becomes capable of registering the port of the print service providing apparatus as the usable port. In step S the port provided by the port monitor A is registered in a port list such as a printer port list of an OS.

In step S a printer driver A is installed in the client terminal in order to add a printer driver A cloud print of the print service providing apparatus as the usable printer driver. By installing the printer driver A the client terminal becomes capable of registering the printer driver A of the print service providing apparatus as the usable printer driver. In step S the printer driver A is registered in a printer driver list of the OS.

In step S when registering the print service providing apparatus as a destination to send the print data a user operates the client terminal to open a destination registration screen as illustrated in and select the printer driver A cloud print from the printer driver list of the destination registration screen .

Further in step S the user operates the client terminal to select a port print service of the print service providing apparatus provided by the port monitor A from the printer port list of the destination registration screen .

When the printer driver A cloud print and the port print service of the print service providing apparatus provided by the port monitor A are selected by the user the OS and the port monitor see perform the process as illustrated in a sequence diagram of .

In step S the OS notifies the port monitor that the port provided by the port monitor port monitor A is selected from the printer port list.

In step S the destination registration unit of the port monitor instructs the OS to display an input dialog as illustrated in . is an image diagram illustrating an example the input dialog of the company code. In step S the OS displays the input dialog . The user inputs the company code in the input dialog and presses a registration button .

When the registration button is pressed after the company code is input the OS sends the company code input in the input dialog to the destination registration unit of the port monitor in step S. In step S the destination registration unit of the port monitor stores the received company code in the destination setting storing unit in association with the port print service provided by the port monitor port monitor A . In step S the port monitor notifies the fact that a necessary process is completed to the OS and the company code inputting process is finished.

An example of a process to input print data from the client terminal is as illustrated in for example. is a sequence diagram illustrating an example of an output data inputting process.

In step S the input accepting unit of the client terminal accepts a print request to the application having the printing function by a user operation. In step S the client terminal accepts a print setting which is an example of an output setting by a user operation. The print setting includes a setting of a destination to send the print data. For example the user sets the destination to send the print data from a print setting screen of the application having the printing function.

In step S the output setting unit receives the print setting from the input accepting unit . In step S the output setting unit updates a print setting held by the output setting unit by the received print setting.

In step S the client terminal accepts a request to send print data by a user operation. In step S the input accepting unit of the client terminal requests the application to send data application data to be printed. In step S the application requests the output data generating unit to generate output data by sending application data.

In step S the output data generating unit requests the output setting unit to send the print setting. In step S the output data generating unit receives the print setting from the output setting unit . In step S the output data generating unit generates print data as an example of the output data from the application data based on the print setting received from the output setting unit .

In step S the output data sending control unit receives the print data generated by the output data generating unit . In step S the output data sending control unit determines the destination setting of the destination as will be explained later based on the destination to send the print data included in the print setting and the setting of the destination stored in the destination setting storing unit .

When the destination to send the print data is the print service providing apparatus the output data sending control unit determines that the print service providing apparatus is access controlled and requests the log in requesting unit to perform a log in operation in step S. The log in requesting unit displays a log in data input screen which will be explained later for having the user input log in data authentication information including user name a password or the like.

In step S the input accepting unit of the client terminal accepts an input of the log in data from the user. In step S the log in requesting unit receives the log in data from the input accepting unit . In step S the log in requesting unit requests the authentication process unit of the service providing system to log in as will be explained later. At this time the company code the user name the password or the like are sent to the authentication process unit .

In step S the authentication process unit of the service providing system performs an authentication as will be explained later. In step S the authentication process unit sends an authentication result as a log in response to the log in requesting unit of the client terminal . When the authentication result is a success authentication is OK the authentication process unit sends a token cookie with the authentication result to the log in requesting unit . The service providing system stores the token in association with the user name and the company code of the authenticated user.

In step S the log in requesting unit sends the authentication result as the log in response to the output data sending control unit . When the authentication result is a success the log in requesting unit sends the token to the output data sending control unit as well.

Here in the following it is assumed that the authentication result is a success authentication is OK . In step S the output data sending control unit sends the token and the print data to the service providing system to request inputting of the print data.

In step S the session control unit of the service providing system determines whether a token that is the same as that received in step S exists among the stored tokens. When the token that is the same as that received in step S exists the session control unit sends the user name and the company code that are stored in association with the respective token and the print data to the print service application in step S.

In step S the print service application adds output data ID to the print data and stores in the data storage . The print service application stores the output data management data of the print data to which the output data ID is added in the output data management data storing unit .

On the other hand when the destination to send the print data is the image forming apparatus in step S the process proceeds to step S. In step S the output data sending control unit sends the print data to the image forming apparatus . In step S the image forming apparatus prints the received print data.

The client terminal sends the print data as illustrated in . is a flowchart illustrating an example of a process of sending the print data.

In step S the client terminal accepts the print setting which is an example of the output setting by the user operation. In step S the client terminal accepts the request to send the print data a request to print by the user operation.

In step S the client terminal determines whether the destination to send the print data to which the print data is to be sent is the port print service of the print service providing apparatus . When the destination to send the print data is not the port print service of the print service providing apparatus NO in step S the process proceeds to step S and the client terminal sends the print data to the image forming apparatus .

On the other hand when the destination to send the print data is the port print service of the print service providing apparatus YES in step S the process proceeds to step S. In step S the client terminal determines whether there exists cached log in data. When the cached log in data does not exist NO in step S the client terminal displays a log in data input screen as illustrated in in step S.

When the cached log in data exists in step S the client terminal uses the cached log in data without displaying the log in data input screen .

In step S the client terminal sends the log in data to the service providing system to request log in. The service providing system performs an authentication as will be explained later and sends an authentication result to the client terminal .

In step S the client terminal receives the authentication result from the service providing system . When the authentication result indicates failure NO in step S the process returns back to step S and the client terminal displays the log in data input screen as illustrated in . On the other hand when the authentication result indicates success YES in step S the client terminal sends the token and the print data to the service providing system .

In step S the authentication process unit of the service providing system receives the log in request including the company code the user name and the password as the log in data from the client terminal .

In step S the authentication process unit performs a company authentication that determines whether a company code that is the same as that included in the log in data exists in the company management data stored in the company management data storing unit as illustrated in . When the company code that is the same as that included in the log in data exists in the company management data illustrated in the authentication process unit determines that the company authentication is a success authentication OK and the process proceeds to step S.

In step S the authentication process unit performs a user authentication that determines whether user name and a password that are the same as those included in the log in data exist in the user management data corresponding to the authenticated company code among the user management data stored in the user management data storing unit as illustrated in .

When the user name and the password that are the same as those included in the log in data exist the authentication process unit determines that the user authentication is a success authentication OK and the process proceeds to step S. In step S the authentication process unit determines the authentication result in response to the log in request from the client terminal as a success authentication OK .

When the company code that is the same as that included in the log in data does not exist in step S the authentication process unit determines the authentication result in response to the log in request from the client terminal as a failure authentication NG in step S.

Similarly in step S when the user name and the password that are the same as those included in the log in data do not exist the authentication process unit determines the authentication result in response to the log in request from the client terminal as a failure authentication NG in step S.

In step S the input accepting unit of the image forming apparatus accepts an input of the log in data from the user. In step S the log in requesting unit receives the input log in data from the input accepting unit . Then in step S the log in requesting unit sends the log in request to the authentication process unit of the service providing system as will be explained later.

In step S the authentication process unit of the service providing system performs an authentication as will be explained later. In step S the authentication process unit sends an authentication result as a log in response to the log in requesting unit of the image forming apparatus .

When the authentication result is a success authentication OK the authentication process unit sends a token cookie with the authentication result to the log in requesting unit . The service providing system stores the token in association with the user name and the company code of the authenticated user.

Here in the following it is assumed that the authentication result is a success authentication is OK .

In step S the log in requesting unit sends the token and a request to obtain the data list to the service providing system . The session control unit of the service providing system performs a process similar to step S illustrated in and determines whether a token that is the same as that received in step S exists among the stored tokens.

When the token that is the same as that received in step S exists the session control unit sends the user name and the company code that are stored in association with the respective token to the print service application in step S.

In step S the print service application refers to the output data management data stored in the output data management data storing unit illustrated in and and confirms the conversion status of the output data management data of the output data with which the received user name and the company code are associated. When there is the conversion status being converted for the output data management data of the output data with which the received user name and the company code are associated the print service application determines to update the data list because there is a possibility that the status has been changed.

Here it is assumed that the data list is to be updated here and the explanation is continued. In step S the print service application sends the job ID corresponding to the received user name and the company code in the output data management data to the data process unit and requests to obtain the conversion status of the data management data corresponding to the job ID. In step S the data process unit refers to the data management data stored in the data management data storing unit illustrated in and obtains the conversion status of the data management data corresponding to the received job ID.

In step S the data process unit sends the conversion status of the data management data corresponding to the received job ID to the print service application . In step S the print service application updates the output data management data based on the conversion status of the data management data corresponding to the job ID received from the data process unit . The data list is updated as a result.

Then in steps S and S the print service application sends the data list based on the updated output data management data to the data process requesting unit of the image forming apparatus via the session control unit . Here the print service application includes a job whose conversion status of the data management data is completed in the data list.

When it is determined that the data list is not to be updated in step S the print service application sends the data list based on the current output data management data without updating the output data management data to the image forming apparatus .

With this configuration the image forming apparatus is capable of displaying the data list of the print data for which the conversion process is completed based on the conversion status that varies in accordance with the process by the data process unit .

In step S the authentication process unit of the service providing system receives the log in request including the company code the device authentication information the user name and the password as the log in data from the image forming apparatus .

In step S the authentication process unit performs the company authentication that determines whether a company code that is the same as that included in the log in data exists in the company management data stored in the company management data storing unit illustrated in . When the company code that is the same as that included in the log in data exists in the company management data illustrated in the authentication process unit determines that the company authentication is a success authentication OK and the process proceeds to step S.

In step S the authentication process unit performs a device authentication that determines whether device authentication information that is the same as that included in the log in data exists in the device management data corresponding to the authenticated company code among the device management data stored in the device management data storing unit illustrated in . When the device authentication information that is the same as that included in the log in data exists the authentication process unit determines that the device authentication is a success authentication OK and the process proceeds to step S.

In step S the authentication process unit performs the user authentication that determines whether user name and a password that are the same as those included in the log in data exist in the user management data corresponding to the authenticated company code among the user management data stored in the user management data storing unit illustrated in .

When the user name and the password that are the same as those included in the log in data exist the authentication process unit determines that the user authentication is a success authentication OK and the process proceeds to step S. In step S the authentication process unit determines the authentication result in response to the log in request from the image forming apparatus as a success authentication OK .

When the company code that is the same as that included in the log in data does not exist in step S the authentication process unit determines the authentication result in response to the log in request from the image forming apparatus as a failure authentication NG in step S.

Similarly in step S when the device authentication information that is the same as that included in the log in data does not exist in step S the authentication process unit determines that the authentication result in response to the log in request from the image forming apparatus as a failure authentication NG in step S.

Similarly when the user name and the password that are the same as those included in the log in data do not exist in step S the authentication process unit determines the authentication result in response to the log in request from the image forming apparatus as a failure authentication NG in step S.

The process of step S illustrated in in which the conversion status is determined may be performed in accordance with a flowchart illustrated in .

In step S the print service application refers to the user management data stored in the user management data storing unit as illustrated in and determines whether a role of the log in user who requested to obtain the data list is an administrator based on the user management data corresponding to the received user name and the company code.

When the role of the log in user is the administrator YES in step S the print service application refers to the output data management data stored in the output data management data storing unit illustrated in and in step S and obtains the conversion status of the data management data corresponding to the received company code. On the other hand when the role of the log in user is an ordinary user NO in step S the print service application refers to the output data management data stored in the output data management data storing unit illustrated in and in step S and obtains the conversion status of the data management data corresponding to the received company code and also the user name user information .

Then the process proceeds to step S. In step S the print service application determines whether the conversion statuses of the data management data obtained in step S or S are all completed . When the conversion statuses obtained in step S or S are all completed YES in step S as there is no possibility that the conversion statuses are changed it is determined that the data list is not updated. Then the process is finished.

On the other hand when not all of the conversion statuses confirmed in step S or S are completed NO in step S as there is a possibility that the conversion statuses are changed it is determined that the data list is updated step S. Then the process is finished.

Processes of steps S to S illustrate a case when the authentication result is a success and the print data is output from the image forming apparatus . In step S the input accepting unit of the image forming apparatus accepts an output request of the print data from the user.

In step S the input accepting unit requests the data process requesting unit to obtain print data data to be output for which the output request is accepted. In step S the data process requesting unit sends the token and a request to obtain data to be output to the service providing system .

The session control unit of the service providing system determines whether a token that is the same as that received in step S exists in the stored tokens. When the token that is the same as that received in step S exists in the stored tokens the session control unit sends the user name and the company code stored in association with the respective token to the print service application in step S.

In step S the print service application sends the job ID of the output data management data corresponding to the received user name and the company code to the data process unit and requests to obtain the print data corresponding to the job ID. In step S the data process unit refers to the data management data stored in the data management data storing unit illustrated in and obtains the print data corresponding to the received job ID. In step S the data process unit sends the print data corresponding to the received job ID to the print service application .

In steps S and S the print service application sends the received print data to the data process requesting unit of the image forming apparatus via the session control unit . In step S the data process requesting unit sends the received print data to the output unit . In step S the output unit prints the received print data.

Processes of steps S to S illustrate a case when the authentication is a success and the print data is deleted from the service providing system . In step S the input accepting unit of the image forming apparatus accepts a delete request of the print data from the user.

In step S the input accepting unit requests the data process requesting unit to delete the print data. Upon receiving the request to delete the print data from the input accepting unit the data process requesting unit sends the token and a request to delete the print data to the service providing system .

The session control unit of the service providing system determines whether a token that is the same as that received in step S exists in the stored tokens.

When the token that is the same as that received in step S exists in the stored tokens the session control unit sends the user name and the company code stored in association with the respective token to the print service application in step S.

In step S the print service application sends the received user name and the company code to the data process unit and requests to delete the print data. In step S the data process unit deletes the print data based on the request to delete the print data.

In the system of the first embodiment the client terminal sends the print data to the image forming apparatus when the destination to send the print data is the image forming apparatus and sends the print data to the print service providing apparatus which is on the network N2 having an access control function when the destination to send the print data is the print service providing apparatus after performing a log in operation to the print service providing apparatus .

According to the system of the first embodiment a common user interface can be provided to a user for a case when the print data is sent to the image forming apparatus to be printed and a case when the print data is sent to the print service providing apparatus so that the print data is printed using the print service provided by the print service providing apparatus from the client terminal .

In the second embodiment an output log is sent from the client terminal to the service providing system and is stored. Components that are the same as those in the first embodiment are given the same reference numerals and explanations are not repeated. The system structure and the hardware structure of the second embodiment are the same as those of the first embodiment.

For a software structure the client terminal and the service providing system are different from those of the first embodiment. The client terminal of the second embodiment includes components as illustrated in for example. is a functional block diagram illustrating an example of the client terminal of the second embodiment.

The client terminal illustrated in further includes an output log sending control unit and an output log generation unit an example of a log generation unit in addition to the components of the client terminal illustrated in .

The output log generation unit generates an output log to be sent to the service providing system . The output log sending control unit controls sending of the output log to the service providing system .

The functions of the service providing system of the second embodiment are actualized by components illustrated in for example. is a functional block diagram illustrating an example of a software structure of the service providing system of the second embodiment. The service providing system illustrated in further includes a log registration unit and a log storing unit in addition to the components of the service providing system illustrated in .

The log registration unit stores an output log received from the client terminal in the log storing unit . The log storing unit stores the output log which will be explained later.

Further as illustrated in the service providing system may include a log registration unit and an output log storing unit in the print service application instead of the log registration unit and the log storing unit illustrated in . is a functional block diagram illustrating an example of the print service application of the embodiment. The print service application illustrated in further includes the log registration unit and the output log storing unit in addition to the components of the print service application illustrated in .

The log registration unit stores the output log received from the client terminal in the output log storing unit . The output log storing unit stores the output log which will be explained later.

The log storing unit of the service providing system or the output log storing unit of the print service application stores the output log as illustrated in and for example. and are views illustrating an example of the output log.

The output log illustrated in includes data items such as output data ID company code user information bibliographic data job ID status and the like. The status indicates a status already output deleted or the like of the print data corresponding to the output log. The output log illustrated in further includes a data item fixed value or input value in addition to the data items of the output log illustrated in . The fixed value or input value indicates whether a fixed value is used or an input value input by the user is used as ID when sending the output log.

In the system of the second embodiment the user sets a setting of a sending log using a setting of a sending log screens illustrated in and . and are respective image diagrams illustrating an example of the setting of the sending log screen. In the setting of the sending log screens illustrated in and one of sending conditions for the output log to the service providing system such as not to send send logs of all direct prints and send logs of direct prints of selected multifunction devices can be selected. Further in the setting of the sending log screens illustrated in and whether to use the fixed value or the input value input by the user as the ID when sending the output log can be selected.

An example of a process to input print data from the client terminal is as illustrated in for example. is a sequence diagram illustrating an example of an output data inputting process. The flowchart illustrated in is similar to the flowchart illustrated in except a part and the same process is not repeated.

Processes of steps S to S illustrated in are the same as the processes of steps S to S illustrated in . When it is determined that the destination to send the print data is the image forming apparatus the output data sending control unit requests the output log sending control unit to determine whether to send the log in step S.

In step S the output log sending control unit determines whether to send an output log based on the setting of sending output log. When not to send as illustrated in is selected for example the output log sending control unit determines that it is unnecessary to send the output log.

Further when send logs of direct prints of selected multifunction devices as illustrated in is selected for example the output log sending control unit determines it is necessary to send the output log when the selected multifunction device is the destination to send the print data.

Further when send logs of all direct prints as illustrated in is selected the output log sending control unit determines that it is necessary to send the output log.

When it is determined that the output log is to be sent the output log sending control unit requests the log in requesting unit to perform a log in operation in step S. The log in requesting unit displays a log in data input screen for having the user input log in data authentication information including user name a password and the like.

Processes of steps S to S are the same as the processes of steps S to S illustrated in . In step S the log in requesting unit sends the authentication result as the log in response to the output log sending control unit . When the authentication is a success the log in requesting unit sends a token as well to the output log sending control unit .

In step S the output log sending control unit requests the output log generation unit to generate an output log. In step S the output log generation unit generates the output log as illustrated in and . In step S the output log generation unit sends the output log to the output log sending control unit .

In step S the output log sending control unit requests the output data sending control unit to send the print data. When the authentication is a success the output log sending control unit sends the token as well to the output data sending control unit . The process proceeds to step S and the output data sending control unit sends the print data to the image forming apparatus . The image forming apparatus prints the received print data. Then in step S the output log sending control unit sends the output log to the service providing system .

When it is determined not to send the output log the output log sending control unit requests the output data sending control unit to send the print data in step S. Here when the authentication is a success the output log sending control unit sends the token as well to the output data sending control unit in step S. The process proceeds to step S and the output data sending control unit sends the print data to the image forming apparatus .

The client terminal sends an output log as illustrated in for example. is a flowchart illustrating an example of a process of sending the output log. The flowchart illustrated in is similar to the flowchart illustrated in except a part.

Processes of steps S to S are similar to the processes of step S to S illustrated in . In step S when the destination to send the print data is not the port print service of the print service providing apparatus NO in step S the process proceeds to step S.

In step S the client terminal determines whether to send an output log based on a setting of sending output log. When it is not a log sending mode in which the output log is to be sent NO in step S the process proceeds to step S and the client terminal sends the print data to the image forming apparatus .

When it is the log sending mode in which the output log is to be sent in step S YES in step S the client terminal determines whether the destination of the print data is the destination for which the output log is to be sent the multifunction device selected in in step S. When the destination to output the print data is not the destination for which the output log is to be sent NO in step S the process proceeds to step S and the client terminal sends the print data to the image forming apparatus .

When the destination to output the print data is the destination for which the output log is to be sent YES in step S the client terminal determines whether the fixed value is selected as the ID when sending the output log in step S.

When the fixed value is not selected as the ID when sending the output log NO in step S the client terminal displays the log in data input screen as illustrated in in step S. In step S the client terminal accepts an input of the log in data to the log in data input screen from the user.

In step S the client terminal sends the log in data to the service providing system to request log in. The service providing system sends the authentication result to the client terminal .

In step S the client terminal receives the authentication result from the service providing system . When the authentication result is not success NO in step S the process returns back to step S and the client terminal displays the log in data input screen as illustrated in . On the other hand when the authentication result is a success YES in step S the client terminal sends the token and the print data to the destination. Then in step S the client terminal sends the output log to the service providing system .

In step S when the fixed values is selected as the ID when sending the output log YES in step S the process proceeds to step S and the client terminal accepts the fixed value registered from the fixed value registration screen illustrated in as the log in data.

In step S the client terminal sends the log in data to the service providing system to request log in. The service providing system sends the authentication result to the client terminal .

In step S the client terminal receives the authentication result from the service providing system . When the authentication result is not success NO in step S the process returns back to step S and the client terminal displays the log in data input screen as illustrated in . On the other hand when the authentication result is a success YES in step S the client terminal sends the token and the print data to the destination. Then in step S the client terminal sends the output log to the service providing system .

According to the system of the second embodiment the output log of the direct print whose destination to send is the image forming apparatus can be sent from the client terminal to the service providing system . Thus according to the system of the second embodiment the output log of the direct print whose destination to send is the image forming apparatus can be registered in the service providing system in addition to the output log whose destination to send is the print service.

Although the print data is exemplified as the output data the output data is not so limited. For example a projector may be used instead of the image forming apparatus and a projection service may be used instead of the print service.

In the projection service projection data output data to be displayed sent from the client terminal is received and the projection data is sent to the projector in response to a request from the projector. The client terminal may set the projection service or the projector as a destination to output the projection data. In such a case as well by applying the present embodiment the same effect obtained in the first embodiment or the second embodiment can be obtained.

The individual constituents of the system may be embodied by arbitrary combinations of hardware and software typified by a CPU of an arbitrary computer a memory a program loaded in the memory so as to embody the constituents illustrated in the drawings a storage unit for storing the program such as a hard disk and an interface for network connection. It may be understood by those skilled in the art that methods and devices for the embodiment allow various modifications.

According to the embodiment a data processing apparatus and a system capable of accepting execution of different processes via a common user interface are provided.

Although a preferred embodiment of the data processing apparatus and the system has been specifically illustrated and described it is to be understood that minor modifications may be made therein without departing from the spirit and scope of the invention as defined by the claims. The output apparatus the service providing apparatus and the data processing apparatus defined in the claims may correspond to the image forming apparatus the service providing system and the client terminal respectively.

The present invention is not limited to the specifically disclosed embodiments and numerous variations and modifications and modifications may be made without departing from the spirit and scope of the present invention.

The present application is based on and claims the benefit of priority of Japanese Priority Application No. 2012 196952 filed on Sep. 7 2012 the entire contents of which are hereby incorporated by reference.

