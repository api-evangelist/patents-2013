---

title: Information processing system, information processing apparatus, and authentication method
abstract: An information processing system, which is implemented by one or more information processing apparatuses, includes a first receiving unit configured to receive a first user identifier and a first organization identifier via a network from an external apparatus and a first authentication unit configured to perform authentication based on the first user identifier and the first organization identifier by referring to a storage unit storing one or more second user identifiers in association with second organization identifiers. The first authentication unit performs authentication by identifying an organization identifier matching the first organization identifier within the second organization identifiers and identifying a user identifier matching the first user identifier within the second user identifiers associated with the matching organization identifier.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09455970&OS=09455970&RS=09455970
owner: Ricoh Company, Ltd.
number: 09455970
owner_city: Tokyo
owner_country: JP
publication_date: 20130130
---
The present application is based upon and claims the benefit of priority of Japanese Patent Application No. 2012 020251 filed on Feb. 1 2012 Japanese Patent Application No. 2012 111681 filed on May 15 2012 and Japanese Patent Application No. 2013 001609 filed on Jan. 9 2013 the entire contents of which are incorporated herein by reference.

An aspect of this disclosure relates to an information processing system an information processing apparatus and an authentication method.

2. Description of the Related Art Japanese Laid Open Patent Publication No. 2008 182699 for example discloses a printing system where print jobs received from terminals such as personal computers PC are not immediately printed but stored in an information processing apparatus such as a print server and a logged in user selects a print job from a list of the stored print jobs and prints the selected print job on an image forming apparatus such as a multifunction peripheral. Such a printing system or method is called a pull printing system or method see for example Japanese Laid Open Patent Publication No. 2008 182699 .

In the related art pull printing system as described above user authentication is normally performed to maintain information security when a user prints a print job stored in an information processing apparatus e.g. print server on an image forming apparatus e.g. multifunction peripheral . For example a user ID and a password are used to authenticate the user.

In the related art pull printing system however if the user ID and the password are stolen by a third party the third party can execute print jobs stored in the image processing apparatus on any image forming apparatus which is installed for example in a company of the third party or a public environment such as a convenience store using the stolen user ID and password.

Thus with the related art pull printing system it is difficult to prevent leakage of information to a third party impersonating an authorized user using a stolen user ID and password and therefore it is difficult to maintain security.

In an aspect of this disclosure there is provided an information processing system implemented by one or more information processing apparatuses. The information processing system includes a first receiving unit configured to receive a first user identifier and a first organization identifier via a network from an external apparatus and a first authentication unit configured to perform authentication based on the first user identifier and the first organization identifier by referring to a storage unit storing one or more second user identifiers in association with second organization identifiers. The first authentication unit performs authentication by identifying an organization identifier matching the first organization identifier within the second organization identifiers and identifying a user identifier matching the first user identifier within the second user identifiers associated with the matching organization identifier.

Preferred embodiments of the present invention are described below with reference to the accompanying drawings. In the embodiments a printing system supporting pull printing is used as an example of an output system.

The reverse proxy is provided at a node between the network and the external network e.g. the Internet and relays access from the external network to the inside of the network . The firewall is provided at a node between the network and the external network and relays access from the inside of the network to the external network.

The network provides a cloud service and includes one or more information processing apparatuses that provide various functions via for example Web applications and server applications. The network may include an authentication service unit a print job management service unit an asynchronous conversion service unit an authentication database DB a job management database DB and a print file storage that are functional units implemented by the information processing apparatuses.

The network is for example an internal network of a company and may include at least one terminal and at least one image forming apparatus . The terminal may be implemented by any apparatus such as a smartphone a cell phone a personal computer PC a tablet PC or a projector that can enter or output a print job. The image forming apparatus may be implemented by any apparatus such as a multifunction peripheral or a printer that can execute a print job.

In the printing system after being authenticated by the authentication service unit of the network the terminal sends a print job to the print job management service unit of the network and thereby enters the print job. Meanwhile after being authenticated by the authentication service unit of the network the image forming apparatus receives print data from the print job management service unit of the network and executes the corresponding print job.

The firewall is provided to maintain the security of the network . The terminal generates data e.g. application data to be printed according to user operations and sends or enters a print job including the generated data to the network .

The image forming apparatus displays a print job list that is a list of print jobs receivable from the network and allows the user to select a print job from the print job list. When a print job is selected by the user from the print job list the image forming apparatus receives print data of the selected print job from the network and prints the print data. The print data is obtained by converting or rendering data to be printed which is hereafter referred to as print target data into a format that the image forming apparatus can print.

The reverse proxy functions as a proxy for the print job management service unit and relays a request to the print job management service unit . With this configuration the terminal and the image forming apparatus can access the print job management service unit only via the reverse proxy . Accordingly it is possible to improve the security of the printing system by incorporating a security function in the reverse proxy .

The authentication service unit performs authentication of the image forming apparatus users operating the terminal and the image forming apparatus and applications installed in the image forming apparatus . The authentication service unit performs authentication using the authentication DB.

When the user operating the terminal is successfully authenticated the authentication service unit sends an authentication ticket to the terminal . When the image forming apparatus the user operating the image forming apparatus and an application installed in the image forming apparatus are all successfully authenticated the authentication service unit sends an authentication ticket to the image forming apparatus .

The print job management service unit manages print jobs sent from or entered by the terminal using the job management DB. The asynchronous conversion service unit converts renders or translates print target data into print data that the image forming apparatus can print. More specifically the asynchronous conversion service unit converts print target data into a print file with a format of for example a page description language that the image forming apparatus can print. The asynchronous conversion service unit converts data into a print file asynchronously with the reception of a conversion request from the print job management service unit .

In the printing system configured as described above the authentication ticket is not sent from the authentication service unit to the image forming apparatus unless the image forming apparatus the user operating the image forming apparatus and an application installed in the image forming apparatus are all successfully authenticated. With this configuration even if a user ID and a password are stolen by a third party authentication of an image forming apparatus which is installed for example in a company of the third party or a public environment such as a convenience store used by the third party fails and the third party cannot obtain and print a print job. Thus in the printing system of the present embodiment image forming apparatuses that can perform pull printing are limited by authentication. This configuration makes it possible to prevent leakage of information to a third party impersonating an authorized user and thereby improve the security of the printing system .

The network private environment A may include the reverse proxy an authentication apparatus a print job management apparatus and an asynchronous conversion apparatus . The network private environment B may include the terminal the image forming apparatus and the firewall .

The authentication apparatus implements the authentication service unit and the authentication DB of . The print job management apparatus implements the print job management service unit and the job management DB of . The asynchronous conversion apparatus implements the asynchronous conversion service unit and the print file storage of .

The authentication apparatus the print job management apparatus and the asynchronous conversion apparatus may be implemented by one computer or two or more computers. Also the authentication DB the job management DB and the print file storage may instead be implemented by database apparatuses and a file storage apparatus that are provided separately from the authentication apparatus the print job management apparatus and the asynchronous conversion apparatus .

The terminal generates print target data e.g. document data image data etc. to be printed using software or applications . The terminal may also store print target data that is received from another apparatus not shown . After being authenticated by the authentication apparatus the terminal sends a print job including print target data to the print job management apparatus . When receiving the print job the print job management apparatus sends a conversion request to the asynchronous conversion apparatus to request conversion of the print target data into a format that the image forming apparatus can print.

The asynchronous conversion apparatus converts the print target data into a format that the image forming apparatus can print asynchronously with the reception of the conversion request from the print job management apparatus . For example the asynchronous conversion apparatus reads the print target data from the print file storage and converts or renders the print target data into a print file that the image forming apparatus can print.

The image forming apparatus receives a print job list which is a list of receivable print jobs from the print job management apparatus after the image forming apparatus the user operating the image forming apparatus and an application installed in the image forming apparatus are all successfully authenticated. Then the image forming apparatus displays the print job list on for example an operations panel and requests the user to select a print job from the print job list. When a print job is selected the image forming apparatus requests a print file corresponding to the selected print job from the print job management apparatus .

The print job management apparatus obtains the requested print file from the asynchronous conversion apparatus and sends the obtained print file to the image forming apparatus . The image forming apparatus receives and prints the print file. Here the asynchronous conversion apparatus may convert print target data into a print file asynchronously with the request for the print file from the image forming apparatus to the print job management apparatus i.e. before the print file is requested .

In the printing system configured as described above the authentication ticket is not sent from the authentication apparatus to the image forming apparatus unless the image forming apparatus the user operating the image forming apparatus and an application installed in the image forming apparatus are all successfully authenticated. With this configuration it is possible to prevent leakage of information to a third party impersonating an authorized user using a stolen user ID and password and thereby maintain the security of the printing system .

Each of the authentication apparatus the print job management apparatus and the asynchronous conversion apparatus may be implemented by an information processing apparatus having a hardware configuration as illustrated in . is a block diagram illustrating an exemplary hardware configuration of the information processing apparatus .

As illustrated in the information processing apparatus may include an input unit a display unit an external I F a random access memory RAM a read only memory ROM a central processing unit CPU a communication I F and a hard disk drive HDD that are connected to each other via a bus B.

The input unit includes for example a keyboard and a mouse and is used to input instructions or operation signals to the information processing apparatus . The display unit displays for example processing results of the information processing apparatus .

The communication I F is an interface for connecting the information processing apparatus to a network. The information processing apparatus can perform data communications with other apparatuses via the communication I F .

The HDD is a non volatile storage device for storing various programs and data. For example the HDD stores basic software or an operating system OS for controlling the entire information processing apparatus and application software for providing various functions on the OS. The HDD may manage the stored programs and data using a file system and or a database DB .

The external I F is an interface between the information processing apparatus and an external device such as a storage medium . The information processing apparatus can read and write data from and to the storage medium via the external I F . The storage medium may be implemented by for example a flexible disk a compact disk CD a digital versatile disk DVD a secure digital SD memory card or a universal serial bus USB memory.

The ROM is a non volatile semiconductor memory storage unit that can retain programs and data even when power is turned off. For example the ROM stores programs and data such as a basic input output system BIOS that is executed when the information processing apparatus is turned on and system and network settings of the information processing apparatus . The RAM is a volatile semiconductor memory storage unit for temporarily storing programs and data.

The CPU processor loads programs and data from storage units e.g. the HDD and the ROM into the RAM and executes the loaded programs to control the information processing apparatus and to implement various functional units of the information processing apparatus .

With the hardware configuration described above the authentication apparatus the print job management apparatus and the asynchronous conversion apparatus can perform processes as described later. Although the hardware configurations of the reverse proxy the terminal the image forming apparatus and the firewall are omitted here these apparatuses may also have a hardware configuration similar to that illustrated in .

For example an administrator having administrative rights of the network accesses a uniform resource locator URL of the authentication apparatus by using for example a browser of the terminal and registers tables as illustrated in in the authentication DB.

The company IDs are identification information for uniquely identifying companies or other types of organizations. The company names are names of companies. The user IDs are identification information for uniquely identifying users. The user names are names of users. The passwords are secret identification information. The device IDs are identification information e.g. serial numbers for uniquely identifying image forming apparatuses . The basic authentication code is used for basic authentication. For example the basic authentication code may be identification information for uniquely identifying an application installed in the image forming apparatus .

With the table of registered in the authentication DB the user of the terminal and the image forming apparatus can be authenticated by entering a company name a user name and a password. With the table of registered in the authentication DB the image forming apparatus can be authenticated. With the table of registered in the authentication DB an application of the image forming apparatus can be authenticated.

In the printing system of the present embodiment as illustrated in companies and users belonging to the companies are associated with each other. Also as illustrated in companies and devices such as the image forming apparatuses installed in the companies are associated with each other.

A URL for accessing the authentication apparatus from the image forming apparatus is different from a URL for accessing the authentication apparatus from the terminal located in the same company as the image forming apparatus . The image forming apparatus establishes a secure socket layer SSL connection with the reverse proxy . Then the reverse proxy requests the image forming apparatus to submit a client certificate. The client certificate may be set in the image forming apparatus before the factory shipment or obtained by the image forming apparatus after the factory shipment.

By submitting the client certificate the image forming apparatus is authenticated or certified as a device that is located in the same company as the terminal . Meanwhile the user of the terminal and the image forming apparatus is authenticated by the authentication apparatus by sending a user ID and a password to the authentication apparatus or by using a pre registered card ID.

Thus the image forming apparatus is certified as a device located in the same company as the terminal by establishing an SSL connection and submitting a client certificate obtained in advance. In the SSL connection if the client certificate has been issued from an authentication apparatus that is not trusted by the network the image forming apparatus cannot access the network . In the printing system it is determined whether the image forming apparatus has a client certificate issued by the authentication apparatus trusted by the network .

Before using the cloud service of the network an organization such as a company or a university needs to subscribe to the cloud service so that an administrator account e.g. a company ID a user ID and a password for the organization is registered at the network . Also it is necessary to install in the image forming apparatus a dedicated application for connecting to an application providing the cloud service and make connection settings e.g. proxy information setting for connection to the application. By making the connection settings a device ID is registered in association with the organization and a user ID and a password user account are also registered in association with the organization in a database provided at the network providing the cloud service. The company ID is an example of an organization ID.

When the login is successful the terminal is redirected to a screen of the print job management service unit of the network . In other words the terminal is directed to a different URL.

In step S the user uploads a print target file or print target data to be printed from the terminal to the print job management service unit . In this step the user or the terminal may also upload printing conditions together with the print target file to the print job management service unit . The printing conditions may include for example duplex or single side printing and the number of copies. The user may upload plural print target files from the terminal to the print job management service unit .

In step S the print job management service sends a conversion request including the file name of the uploaded print target file and the printing conditions to the asynchronous conversion service unit .

Also the print job management service unit associates the uploaded print target file the company ID and the user ID using the job management DB with each other to manage print jobs.

In step S the asynchronous conversion service unit converts the print target file indicated by the conversion request based on the printing conditions in the conversion request into a print file that the image forming apparatus can print. Step S is performed asynchronously with the reception of the conversion request. The asynchronous conversion service unit stores the print file obtained by converting the print target file in for example the print file storage.

In step S the authentication service unit performs authentication of the application installed in the image forming apparatus . When the application ID sent from the image forming apparatus is registered in the authentication DB as the basic authentication code see the authentication service unit determines that the application is valid and the authentication is successful.

In step S the authentication service unit performs authentication of the image forming apparatus . When the image forming apparatus has a valid client certificate and the combination of the device ID and the company ID sent from the image forming apparatus is registered in the table of or the authentication DB the authentication service unit determines that the image forming apparatus is valid and the authentication is successful.

Thus the image forming apparatus is recognized as a valid device based on the client certificate. Also since the image forming apparatus is associated with a company ID as illustrated in it is determined in step S that the image forming apparatus belongs to a company indicated by the company ID.

In step S the authentication service unit performs authentication of the user of the image forming apparatus . The authentication service unit performs authentication of the user by referring to the table of based on the user ID the password and the company ID sent from the image forming apparatus . When the combination of the user ID the password and the company ID sent from the image forming apparatus is registered in the table of or the authentication DB the authentication service unit determines that the user is an authorized user and the authentication is successful. When the authentication is successful the image forming apparatus receives an authentication ticket from the authentication service unit .

In step S the image forming apparatus requests a print job list from the print job management service unit by using the authentication ticket. The validity of the authentication ticket is confirmed for example by a policy agent Web agent provided in the reverse proxy . A company ID and a user ID associated with the authentication ticket may be sent to the print job management service unit together with the request for the print job list. Here the policy agent is a component that obtains policy information and sends the obtained policy information to another component that needs the policy information to provide a security service.

The print job management service unit requests the asynchronous conversion service unit to send a conversion completion list which indicates format conversion status i.e. whether print target files have been converted into print files based on a print job list of print jobs that are associated with the print target files the company ID and the user ID. When receiving the conversion completion list the print job management service unit sends the print job list including the format conversion status to the image forming apparatus . Then the image forming apparatus displays the print job list on the operations panel.

In step S the user selects one or more print files or print jobs from the displayed print job list and requests printing of the selected print files. The image forming apparatus may be configured to display the print job list such that print files of printable or receivable print jobs are displayed as selectable items and print files of non printable or non receivable print jobs are displayed as non selectable items. Also the image forming apparatus may be configured to display the print job list such that all print files of printable print jobs are selected by default to reduce user operations.

In step S the image forming apparatus requests the selected print files from the print job management service unit . The print job management service unit obtains the requested print files from the asynchronous conversion service unit and sends the obtained print files to the image forming apparatus . The image forming apparatus receives and prints the print files.

In the printing process of the authentication ticket is not sent from the authentication service unit to the image forming apparatus unless the image forming apparatus the user of the image forming apparatus and the application of the image forming apparatus are all successfully authenticated. With this configuration it is possible to prevent leakage of information to a third party impersonating an authorized user using a stolen user ID and password and thereby maintain the security of the printing system .

In the example of application authentication of step S device authentication of step S and user authentication of step S are performed in this order. However the order of these authentication steps may be changed. Also the application authentication of step S may be omitted.

In step S the terminal tries to access the print job management service unit via the reverse proxy . However since the terminal has no authentication ticket the reverse proxy redirects the terminal to a login screen of the authentication service unit in steps S and S.

In step S the terminal receives the login screen. The user performs a login operation on the login screen. In step S the terminal sends a company ID a user ID and a password to the authentication service unit . The authentication service unit performs authentication of the user by referring to the table of in the authentication DB.

When the combination of the company ID the user ID and the password entered via the terminal is registered in the table of authentication DB the authentication service unit determines that the user is an authorized user and the login is successful. When the login is successful the authentication service unit sends an authentication token cookie which is an example of an authentication ticket to the terminal in step S.

In step S since the terminal has the authentication token the terminal is redirected to a print job registration screen of the print job management service unit . In step S the print job management service unit sends the print job registration screen to the terminal . The terminal receives and displays the print job registration screen. The user specifies a print target file e.g. a document on the print job registration screen. The user can also specify printing conditions on the print job registration screen.

In step S the terminal sends the print target file and the printing conditions to the print job management service . In step S the print job management service unit sends a conversion request to the asynchronous conversion service to request conversion of the print target file into a format that the image forming apparatus can print. In step S the asynchronous conversion service returns a request reception report to the print job management service unit . In step S the print job management service unit sends to the terminal a print job registration report indicating that a print job has been successfully registered.

When receiving the conversion request the asynchronous conversion service unit converts the print target file indicated by the conversion request into a print file with a format that the image forming apparatus can print. The asynchronous conversion service converts the print target file asynchronously with the reception of the conversion request at step S. For example the asynchronous conversion service unit stores the print file obtained by converting the print target file in the print file storage.

After registering the print job the user operating the terminal moves to a location where the image forming apparatus is installed. The user starts an application of the image forming apparatus and enters a user ID and a password.

In step S the image forming apparatus establishes an SSL connection with the reverse proxy using a client certificate. In step S the image forming apparatus sends a company ID a user ID a password a device ID and an application ID to the authentication service unit . The authentication service unit confirms the validity of the application application authentication the validity of the company and the validity location or presence of the image forming apparatus device authentication .

When the validity of the application and the image forming apparatus is successfully confirmed i.e. when the application authentication and the device authentication are successful the authentication service unit performs user authentication. The authentication service unit performs user authentication by referring to the table of authentication DB based on the user ID the password and the company ID sent from the image forming apparatus .

When the authentication is successful in step S the authentication service unit sends an authentication token to the image forming apparatus . In step S the image forming apparatus requests a print job list from the print job management service using the authentication token and also sends the device ID to the print job management service unit .

The validity of the authentication token is confirmed for example by a policy agent provided in the reverse proxy . When the validity of the authentication token is confirmed the reverse proxy sends the company ID and the user ID associated with the authentication token to the print job management service together with the request for the print job list.

In step S the print job management service unit requests the asynchronous conversion service unit to send a conversion completion list indicating format conversion status i.e. whether print target files have been converted into print files. In step S the asynchronous conversion service unit sends the conversion completion list to the print job management service .

In step S the print job management service unit sends the print job list including the format conversion status to the image forming apparatus . The image forming apparatus displays the print job list on the operations panel. Then the user selects one or more print files i.e. documents the user needs to print from the displayed print job list and requests printing of the selected print files e.g. by pressing a print button .

In step S the image forming apparatus requests the selected print files or documents to be printed from the print job management service unit and also sends the device ID to the print job management service unit .

In step S the print job management service unit requests the asynchronous conversion service unit to send the print files requested by the image forming apparatus . In step S the asynchronous conversion service unit sends the requested print files or documents to be printed to the print job management service unit . In step S the print job management service unit sends the requested print files or documents to be printed to the image forming apparatus . The the image forming apparatus receives and prints the print files.

The authentication unit performs authentication using the authentication DB . The authentication unit may be implemented for example by OpenAM. OpenAM is authentication platform software that provides a single sign on SSO architecture. The authentication unit performs authentication based on company IDs user IDs and passwords stored in the authentication DB which is an example of a user data store and also performs authentication based on client certificates.

The user API is an application programming interface that receives requests to confirm the validity of authentication tokens from Web applications such as the print job management service unit and other applications and returns confirmation results to those applications.

In step S the terminal establishes an SSL connection with the reverse proxy . In step S the terminal tries to access the print job management service unit via the reverse proxy . The reverse proxy confirms whether a request which may be referred to as an access request from the terminal to access the print job management service includes an authentication token.

When the access request to the print job management service includes no authentication token the reverse proxy redirects the terminal to the login UI of the authentication service unit in steps S and S.

In step S the login UI sends a login screen to the terminal and the terminal receives the login screen. The user performs a login operation on the login screen. In step S the terminal sends a company ID a user ID and a password to the login UI of the authentication service unit .

In step S the login UI requests the authentication unit to authenticate the user based on the company ID the user ID and the password received from the terminal . In step S the authentication unit performs authentication by referring to the authentication DB . For example when the combination of the company ID the user ID and the password sent from the terminal is registered in the table of in the authentication DB the authentication unit determines that the user is an authorized user.

When the user is successfully authenticated the authentication unit sends an authentication token to the login UI in step S. In step S the login UI sends the authentication token received from the authentication unit to the terminal .

In step S the terminal tries to access the print job management service unit via the reverse proxy . The reverse proxy confirms whether the access request from the terminal to access the print job management service includes an authentication token.

In this case since the access request includes the authentication token the reverse proxy queries a Web agent whether the authentication token is in a cache. When the authentication token is not in the cache the Web agent in step S requests and receives contents of the authentication token from the authentication unit .

Then the Web agent stores the received contents of the authentication token in the cache. The contents of the authentication token cached by the Web agent may include for example a company ID a user ID and an accessible destination. After the validity of the authentication token is confirmed the reverse proxy in step S redirects the terminal to a print job registration screen of the print job management service unit . In this step the reverse proxy also sends the company ID and the user ID associated with the authentication token to the print job management service unit .

In step S the print job management service unit requests the user API of the authentication service unit to confirm the validity of the received authentication token. In step S the user API requests the authentication unit to confirm the validity of the authentication token and receives the confirmation result.

In step S the print job management service unit receives the confirmation result of the validity of the authentication token from the user API . When the validity of the authentication token is confirmed the print job management service unit in steps S and S sends the print job registration screen to the terminal . The terminal receives and displays the print job registration screen.

In step S the image forming apparatus establishes an SSL connection with the reverse proxy using a client certificate. In step S the image forming apparatus sends an authentication request including a company ID a user ID a password a device ID and an application ID to the relay API of the authentication service unit .

In step S when the application ID sent from the image forming apparatus is registered in the authentication DB as the basic authentication code see the relay API determines that the application is valid and the application authentication is successful.

When the combination of the device ID and the company ID sent from the image forming apparatus is registered in the table of in the authentication DB the relay API determines that the image forming apparatus is valid and the device authentication is successful.

In step S the relay API requests the authentication unit to authenticate the user based on the user ID the password and the company ID sent from the image forming apparatus . In step S when the combination of the user ID the password and the company ID sent from the image forming apparatus is registered in the table of in the authentication DB the authentication unit determines that the user is an authorized user and the user authentication is successful.

When the user is successfully authenticated the authentication unit sends an authentication token to the relay API in step S. In step S the relay API sends the authentication token received from the authentication unit to the image forming apparatus .

In step S the image forming apparatus tries to access the print job management service unit via the reverse proxy to request a print job list. The reverse proxy confirms whether the access request to the print job management service includes an authentication token.

In this case since the access request includes the authentication token the reverse proxy queries the Web agent whether the authentication token is in a cache. When the authentication token is not in the cache the Web agent in step S requests and receives contents of the authentication token from the authentication unit .

Then the Web agent stores the received contents of the authentication token in the cache. The contents of the authentication token cached by the Web agent may include for example a company ID a user ID and an accessible destination. After the validity of the authentication token is confirmed the reverse proxy in step S requests a print job list from the print job management service unit and also sends the device ID to the print job management service unit . Also in this step the reverse proxy sends the company ID and the user ID associated with the authentication token to the print job management service unit .

In step S the print job management service unit requests the user API of the authentication service unit to confirm the validity of the received authentication token. In step S the user API requests the authentication unit to confirm the validity of the authentication token and receives the confirmation result.

In step S the print job management service unit receives the confirmation result of the validity of the authentication token from the user API . When the validity of the authentication token is confirmed the print job management service unit can proceed to step S.

As described above in the printing system of the first embodiment devices used for printing e.g. the image forming apparatuses are registered in association with companies and only documents registered as print jobs of the companies are printed from the registered devices. In other words a print file registered as a print job of a company cannot be output from a device e.g. the image forming apparatus of another company.

Here when authentication is performed using a card it is necessary to register a card ID and user information in association with each other. However if user authentication is performed at the network which provides a cloud service using a card ID print jobs may be stolen by a malicious third party who impersonates an authorized user using a stolen card ID.

With the configuration of the first embodiment device authentication is performed before user authentication so that the user authentication is performed only when it is requested from a valid device. Accordingly this configuration makes it possible to prevent leakage of print jobs to a third party impersonating an authorized user.

Also with the printing system of the first embodiment a user can obtain a print file and print the print file on an image forming apparatus only when the user the image forming apparatus and an application installed in the image forming apparatus are all successfully authenticated. In other words in the printing system of the first embodiment a print file of a user can be printed only on an image forming apparatus that is associated with the company ID of a company to which the user belongs. Accordingly this configuration makes it possible to prevent leakage of information to a third party impersonating an authorized user using a stolen user ID and password and thereby makes it possible to improve security.

With the configuration of the first embodiment user IDs and passwords are sent via the public network such as the Internet. In a second embodiment a printing system is configured such that user IDs and passwords are not sent via the public network such as the Internet.

In the second embodiment an authentication system of the network providing a cloud service using a Security Assertion Markup Language SAML collaborates with an authentication system of the network e.g. an internal network of a company to provide a single sign on architecture.

In step S the user logs into the IdP which provides an authentication platform and manages IDs via a terminal such as a PC. In step S the IdP authenticates the user and issues authentication information called assertion . The user sends the authentication information issued by the IdP to the SP .

The Web application of the SP supports SAML. SAML is a framework for exchanging authentication information via the Extensible Markup Language XML . The SP receives the authentication information and provides a service to the user .

Thus with the above described architecture the user can access the Web application of the SP without performing an additional login operation. This indicates that a relationship of trust is built beforehand between the IdP and the SP . The IdP and the SP share the account information of the user and use the same authentication information to enable single sign on.

Assuming that the IdP is an authentication apparatus in the network and the SP is the print job management apparatus of the network the user can log into the print job management apparatus of the network by just logging into the authentication apparatus of the network using a user ID and a password.

In the second embodiment device authentication is performed to guarantee that a requesting device is associated with an appropriate company ID and transmission of user IDs and passwords is kept within the network i.e. an internal network to improve security. Also in the second embodiment a single sign on architecture is employed to improve the convenience of the user .

The network is for example an internal network of a company and may include at least one terminal at least one image forming apparatus and the IdP . The IdP may be implemented by one or more information processing apparatuses.

In the printing system of the second embodiment the IdP of the network authenticates the terminal and issues an authentication ticket which may be referred to as assertion for the terminal . The terminal sends a print job to the print job management service unit of the network i.e. enters the print job by using the authentication ticket. The IdP of the network also authenticates the image forming apparatus and issues an authentication ticket assertion for the image forming apparatus . The image forming apparatus receives a print job or print data from the print job management service unit of the network by using the authentication ticket and executes the print job.

The authentication service unit performs user authentication by using the authentication tickets sent from the terminal and the image forming apparatus . The authentication service unit also performs authentication of the image forming apparatus and an application installed in the image forming apparatus by using the authentication DB. When the user operating the terminal is successfully authenticated the authentication service unit sends an authentication ticket to the terminal . When the image forming apparatus the user operating the image forming apparatus and an application installed in the image forming apparatus are all successfully authenticated the authentication service unit sends an authentication ticket to the image forming apparatus .

Thus in the printing system of the second embodiment the IdP provided in the network authenticates a user based on a user ID and a password and issues an authentication ticket when the user is successfully authenticated. Also in the printing system instead of user IDs and passwords authentication tickets are sent and received between the network and the network . In other words transmission of user IDs and passwords is kept within the network .

As illustrated in the network private environment B may include the terminal the image forming apparatus the firewall and the IdP . The IdP authenticates the user of the terminal and issues an authentication ticket assertion for the terminal . The terminal sends a print job including data to be printed to the print job management apparatus by using the authentication ticket.

The IdP also authenticates the user of the image forming apparatus and issues an authentication ticket for the image forming apparatus . At the network the authentication apparatus authenticates the user of the image forming apparatus based on the authentication ticket. The authentication apparatus also authenticates the image forming apparatus and an application installed in the image forming apparatus based on a device ID and an application ID.

After the user operating the image forming apparatus the image forming apparatus itself and the application installed in the image forming apparatus are authenticated the image forming apparatus receives a print job list which is a list of receivable print jobs from the print job management apparatus .

Processes performed after the print job list is received by the image forming apparatus are substantially the same as those described in the first embodiment and their descriptions are omitted here. In the printing system authentication based on user IDs and passwords is performed by the IdP provided in the network and the user IDs and the passwords are transmitted only in the network . Similarly to the first embodiment the second embodiment makes it possible to prevent leakage of information to a third party impersonating an authorized user and thereby maintain the security of the printing system .

Exemplary processes performed by the printing system are described below. Below descriptions of processes in the printing system that are substantially the same as those in the printing system of the first embodiment may be omitted.

For example an administrator having administrative rights of the network accesses a uniform resource locator URL of the authentication apparatus by using for example a browser of the terminal and registers tables as illustrated in in the authentication DB. Meanwhile the table of is registered in an authentication DB not shown in the network .

With the table of registered in the authentication DB in the network the user of the terminal and the image forming apparatus can be authenticated by the IdP .

With the table of registered in the authentication DB in the network the image forming apparatus can be authenticated by the authentication apparatus . With the table of registered in the authentication DB in the network the application of the image forming apparatus can be authenticated by the authentication apparatus .

A print job registration process and a printing process according to the second embodiment are substantially the same as those in the first embodiment except that authentication by the IdP of the network is performed before authentication by the authentication service unit . Therefore overlapping descriptions may be omitted here.

In step S the terminal tries to access the print job management service unit via the reverse proxy . However since the terminal has no authentication ticket the reverse proxy redirects the terminal to a login screen of the IdP in steps S and S.

In step S the terminal receives a login screen. The user performs a login operation on the login screen. In step S the terminal sends a user ID and a password to the IdP . The IdP performs user authentication by referring to the table in the authentication DB provided in the network . When the combination of the user ID and the password entered via the terminal is registered in the table of the authentication DB the IdP determines that the user is an authorized user and the login is successful. When the login is successful the IdP sends an authentication ticket assertion to the terminal in step S.

In step S the terminal with the authentication ticket is automatically forwarded to the authentication service unit . The authentication service unit performs user authentication based on the authentication ticket. When the user of the terminal is successfully authenticated the authentication service unit sends an authentication token to the terminal .

Since steps S through S are substantially the same as steps S through S of their descriptions are omitted here.

Next the user operating the terminal moves to a location where the image forming apparatus is installed. The user starts an application of the image forming apparatus and enters a user ID and a password.

In step S the image forming apparatus sends the user ID and the password to the IdP . The IdP performs user authentication by referring to the table in the authentication DB provided in the network .

When the combination of the user ID and the password entered via the image forming apparatus is registered in the table of the authentication DB the IdP determines that the user is an authorized user and the login is successful. When the login is successful the IdP sends an authentication ticket assertion to the image forming apparatus in step S.

In step S the image forming apparatus establishes an SSL connection with the reverse proxy using a client certificate. In step S the image forming apparatus sends a company ID the authentication ticket assertion a device ID and an application ID to the authentication service unit .

The authentication service unit confirms the validity of the authentication ticket user authentication the validity of the application application authentication the validity of the company and the validity location or presence of the image forming apparatus apparatus authentication .

When the authentication is successful in step S the authentication service unit sends an authentication token to the image forming apparatus . Since step S and the subsequent steps are substantially the same as step S and the subsequent steps of their descriptions are omitted here.

In the printing system of the second embodiment authentication based on user IDs and passwords is performed by the IdP provided in the network e.g. an internal network of a company and authentication tickets are sent and received between the network which provides a cloud service and the network instead of user IDs and passwords.

In other words in the printing system of the second embodiment transmission of user IDs and passwords is kept within the network . Similarly to the first embodiment the second embodiment makes it possible to prevent leakage of information to a third party impersonating an authorized user and thereby makes it possible maintain the security of the printing system .

With the configurations of the first and second embodiments when a user uses an image forming apparatus having a company ID that is different from a company ID associated with the user authentication of the user fails and the user cannot print a print file even if the image forming apparatus is located in a company to which the user belongs or a company in the same corporate group.

For example when different company IDs are used at Japanese headquarters of a company A and at a US branch of the company A a user belonging to the Japanese headquarters cannot print an uploaded print file by using an image forming apparatus located in the US branch of the company A. A third embodiment makes it possible to print a print file on an image forming apparatus having a company ID that is different from a company ID associated with the user.

The printing system of is similar to the printing system of except that the terminal and the image forming apparatus are provided separately in the networks and having different company IDs. Therefore overlapping descriptions are omitted here.

In the printing system the terminal of the network private environment B and the image forming apparatus of the network private environment B are authenticated by the authentication apparatus of the network . As described later in more detail the authentication apparatus manages company IDs of the same company or the same corporate group by associating them with a corporate group ID.

For example when authentication of a user operating an image forming apparatus with a company ID 1235 fails the authentication apparatus determines whether other company IDs are associated with a corporate group ID that is associated with the company ID 1235 .

Here it is assumed that a company ID 1234 is also associated with the corporate group ID associated with the company ID 1235 . In this case the authentication apparatus performs user authentication using the company ID 1234 instead of the company ID 1235 . When the user is associated with the corporate ID 1234 the user is successfully authenticated.

Thus according to the third embodiment a user can be successfully authenticated and can print a print file even when the company ID e.g. 1234 of the user is different from the company ID e.g. 1235 of the image forming apparatus being operated by the user as long as the company IDs are associated with the same corporate group ID.

Processes other than a user authentication process performed in the printing system of the third embodiment are substantially the same as those performed in the printing system of the first embodiment and their descriptions are omitted here. In the printing system a user can print a print file using an image forming apparatus or any other device that is located in a company to which the user belongs or a company in the same corporate group even if the company ID of the image forming apparatus is different from the company ID of the user.

Here even in the printing system a user is not successfully authenticated if the company ID e.g. 1234 of the user is different from the company ID e.g. 1235 of the image forming apparatus being operated by the user and the company ID of the user e.g. 1234 is not associated with the same corporate group ID associated with the company ID e.g. 1235 of the image forming apparatus . Thus similarly to the first embodiment the third embodiment also makes it possible to prevent leakage of information to a third party impersonating an authorized user and thereby maintain the security of the printing system .

Exemplary processes performed by the printing system are described below. Below descriptions of processes in the printing system that are substantially the same as those in the printing system of the first embodiment may be omitted.

For example an administrator having administrative rights of the network accesses a uniform resource locator URL of the authentication apparatus by using for example a browser of the terminal and registers tables as illustrated in .

In the example of company IDs 1234 1235 and 1236 are associated with a corporate group ID G01 . With the table of registered in the authentication DB for example a user having the company ID 1234 and operating an image forming apparatus with the company ID 1235 can be successfully authenticated.

A print job registration process of the third embodiment is substantially the same as the print job registration process of the first embodiment and therefore its description is omitted here. A printing process of the third embodiment is different from the printing process of the first embodiment in step S user authentication process of . Other steps are substantially the same and their descriptions are omitted here.

In step S when the combination of the user ID the password and the company ID sent from the image forming apparatus is registered in the table of or the authentication DB the authentication apparatus determines that the user is an authorized user. When the user is an authorized user the authentication apparatus determines in step S that the authentication is successful.

For example when a user with a company ID 1235 requests authentication from an image forming apparatus with a company ID 1235 the authentication apparatus determines that the user is an authorized user and the authentication is successful.

Meanwhile when the combination of the user ID the password and the company ID sent from the image forming apparatus in the descriptions below this company ID may be referred to as a reported company ID is not registered in the table of in step S the authentication apparatus proceeds to step S.

For example when a user with a company ID 1234 requests authentication from an image forming apparatus with a company ID 1235 the authentication apparatus proceeds to step S. In step S the authentication apparatus refers to the table of to determine whether a company ID other than the reported company ID is registered in association with a corporate group ID associated with the reported company ID i.e. whether another company ID is registered in the same record as the reported company ID .

For example when the reported company ID is 1235 that is associated with the corporate group ID G01 the authentication apparatus determines that the company ID 1234 is also associated with the corporate group ID G01 . When there is another company ID associated with a corporate group ID that is associated with the reported company ID the authentication apparatus replaces the reported company ID with the other company ID in step S and returns to step S to perform user authentication again.

For example the authentication apparatus replaces the reported company ID 1235 with another company ID 1234 associated with the same corporate group ID G01 in step S and performs user authentication again in step S. When the company ID of the user is 1234 the user is successfully authenticated.

Step S may also be performed in a different manner. For example when there is another company ID associated with the same corporate group ID as the reported company ID the authentication apparatus may be allowed to switch to another authentication DB including the other company ID and perform user authentication using the other authentication DB.

If no other company ID associated with the same corporate group ID as the reported company ID is found in step S the authentication apparatus determines that the user is not an authorized user and the authentication is not successful. Steps following the user authentication are substantially the same as those described with reference to in the first embodiment and therefore their descriptions are omitted here.

In the printing system of the third embodiment a user can print a print file on an image forming apparatus with a company ID different from the company ID of the user if those company IDs are associated with the same corporate group ID. Thus the printing system of the third embodiment allows the user to print or process files on devices with different company IDs by associating the company IDs with each other.

For example even when different company IDs are used at Japanese headquarters of a company A and at a US branch of the company A a user belonging to the Japanese headquarters can print an uploaded print file by using an image forming apparatus located in the US branch of the company A.

A fourth embodiment employs a method or mechanism different from the third embodiment to achieve substantially the same effect. In the fourth embodiment the printing system used in the third embodiment is also used and therefore descriptions of the system configuration are omitted.

Exemplary processes performed by the printing system according to the fourth embodiment are described below. Below descriptions of processes in the printing system of the fourth embodiment that are substantially the same as those in the printing system of the third embodiment may be omitted.

An information registration process according to the fourth embodiment is substantially the same as the information registration process in the first embodiment. That is in the fourth embodiment it is not necessary to register the table of that stores company IDs of companies belonging to corporate groups in association with the corresponding corporate group IDs.

A print job registration process of the fourth embodiment is substantially the same as the print job registration process of the first embodiment and therefore its description is omitted here. A printing process of the fourth embodiment is different from the printing process of the first embodiment in step S of . Other steps are substantially the same and their descriptions are omitted here.

In step S in the printing process of the fourth embodiment the image forming apparatus sends a company ID for device authentication a company ID for user authentication a user ID a password a device ID and an application ID to the authentication service unit . Thus in the fourth embodiment different from the first embodiment two company IDs for device authentication and user authentication are sent from the image forming apparatus .

The authentication service unit confirms the validity of the company and the validity location or presence of the image forming apparatus device authentication based on the company ID for device authentication. The authentication service unit also performs user authentication based on the company ID for user authentication. More specifically the authentication service unit performs user authentication by referring to the table of authentication DB based on the user ID the password and the company ID for user authentication sent from the image forming apparatus .

The company ID for user authentication may be entered by the user for example on the same screen of the image forming apparatus for entering the user ID and the password. In this case however even a user with a company ID that is the same as the company ID of the image forming apparatus may also need to enter the company ID for user authentication on the screen of the image forming apparatus for entering the user ID and password.

In the printing system of the fourth embodiment to improve the convenience of the user a screen for a user with a company ID that is the same as the company ID of the image forming apparatus is provided separately from a screen for a user with a company ID that is different from the company ID of the image forming apparatus .

Alternatively one screen may be shared by a user with a company ID that is the same as the company ID of the image forming apparatus and a user with a company ID that is different from the company ID of the image forming apparatus . In this case whether a user has a company ID that is the same as the company ID of the image forming apparatus is determined based on whether a company ID for user authentication is entered by the user.

Steps following step S are substantially the same as those in the first embodiment and therefore their descriptions are omitted here.

The printing system of the fourth embodiment allows a user to print or process a file on an image forming apparatus with a company ID different from the company ID of the user by sending both of the company IDs for device authentication and user authentication from the image forming apparatus .

In a fifth embodiment a mechanism for determining whether a company ID for device authentication and a company ID for user authentication are associated with the same corporate group ID is added to the mechanism of the fourth embodiment. In the fifth embodiment the printing system used in the third embodiment is also used and therefore descriptions of the system configuration are omitted.

Exemplary processes performed by the printing system according to the fifth embodiment are described below. Below descriptions of processes in the printing system of the fifth embodiment that are substantially the same as those in the printing system of the fourth embodiment may be omitted.

An information registration process according to the fifth embodiment is substantially the same as the information registration process in the third embodiment. That is in the fifth embodiment the table of which stores company IDs of companies belonging to corporate groups in association with the corresponding corporate group IDs is registered in the authentication DB.

A print job registration process of the fifth embodiment is substantially the same as the print job registration process of the fourth embodiment and therefore its description is omitted here. A printing process of the fifth embodiment is different from the printing process of the fourth embodiment in the user authentication process performed in step S of . Other steps are substantially the same and their descriptions are omitted here.

In the printing process of the fifth embodiment a user authentication process is performed as illustrated in . is a flowchart illustrating an exemplary user authentication process according to the fifth embodiment.

In step S of the authentication apparatus performs user authentication by referring to the table of based on a user ID a password and a company ID for user authentication sent from the image forming apparatus .

In step S when the combination of the user ID the password and the company ID for user authentication sent from the image forming apparatus is registered in the table of or the authentication DB the authentication apparatus determines that the user is an authorized user. When the user is an authorized user the authentication apparatus proceeds to step S.

In step S the authentication apparatus determines whether the company ID for user authentication and a company ID for device authentication sent from the image forming apparatus are associated with the same corporate group ID by referring to the table of .

When the company ID for user authentication and the company ID for device authentication are associated with the same corporate group ID the authentication apparatus determines in step S that the authentication is successful.

Meanwhile when it is determined in step S that the combination of the user ID the password and the company ID for user authentication sent from the image forming apparatus is not registered in the table of the authentication apparatus determines in step S that the user is not an authorized user and the authentication is not successful.

Also when the company ID for user authentication and the company ID for device authentication are not associated with the same corporate group ID in step S the authentication apparatus determines in step S that the user is not an authorized user and the authentication is not successful.

In the printing system of the fifth embodiment a company ID for device authentication and a company ID for user authentication are sent from the image forming apparatus to the authentication apparatus and the authentication apparatus determines whether the company ID for device authentication and the company ID for user authentication are associated with the same corporate group ID. This configuration improves the security in a case where a user tries to print or process a file on an image forming apparatus with a company ID different from the company ID of the user.

The present invention is not limited to the specifically disclosed embodiments and variations and modifications may be made without departing from the scope of the present invention.

In the printing systems of the above embodiments the authentication service unit the print job management service unit and the asynchronous conversion service unit are implemented respectively as the authentication apparatus the print job management apparatus and the asynchronous conversion apparatus i.e. by separate information processing apparatuses . However the present invention is not limited to the above described configurations.

For example two or more of the authentication service unit the print job management service unit and the asynchronous conversion service unit may be implemented by one information processing apparatus .

Also in the above embodiments the image forming apparatus is used as an example of a device. However the present invention may also be applied to any other device such as a projector or a scanner that inputs and outputs image data. The image forming apparatus may be configured to output or print an image on various media in addition to or other than paper.

A company ID may be referred to as an organization ID an organization identifier or organization identification information . That is a company ID or an organization ID an organization identifier or organization identification information is not limited to identification information for identifying a company but may also represent identification information for identifying any other type of organization or group. Here an organization is not limited to a company or a university but may indicate a group of users or devices of any type. Further identification information for identifying a contract for a group of users or devices may be used as a company ID or an organization ID an organization identifier or organization identification information .

In the above embodiments each of the printing systems basically includes the terminal for requesting registration of a job the image forming apparatus for outputting the job and the information processing apparatus that are connected to each other for communications. The information processing apparatus basically includes a function for converting electronic data i.e. data to be processed in a job sent from the terminal into a format e.g. print data for a printer or display data for a display that the image forming apparatus or any other device can process. The present invention may be applied to but is not limited to any system having such a basic configuration.

Company codes IDs organization identification information or first second organization identifiers user IDs user identification information or first second user identifiers and passwords are registered in advance by a user such as an administrator. For example an administrator sends company codes user IDs and passwords from an administrator terminal to the authentication service unit or the authentication apparatus to request their registration. A registration unit not shown of the authentication service unit registers the company codes the user IDs and the passwords in the authentication DB. The registration unit is configured to not register plural sets of the same combination of a user ID and a password in association with one company code.

For example when receiving a new registration request the registration unit determines whether a matching combination which matches the combination of a company code a user ID and a password in the new registration request which may be referred to as a requested combination is present in the already registered combinations or records in the authentication DB. When a matching combination is found in the authentication DB the registration unit reports it to the administrator terminal without registering the requested combination in the authentication DB.

Alternatively the registration unit may be configured to display a confirmation screen to ask the administrator whether to overwrite the matching combination with the requested combination. When the administrator chooses to overwrite the matching combination the registration unit overwrites the matching combination with the requested combination.

Meanwhile when receiving an overwrite registration request the registration unit determines whether a matching combination that matches the requested combination is present in the already registered combinations or records in the authentication DB. When a matching combination is found the registration unit overwrites the matching combination with the requested combination. Meanwhile when no matching combination is found the registration unit displays a confirmation screen to ask the administrator whether to register the requested combination as a new record or registers the requested combination without displaying the confirmation screen.

In the meantime the same combination of a user ID and a password may be registered in association with different company codes. For this reason the registration unit is preferably configured to first identify an already registered company code that matches a received company code and then determine whether a received combination of a user ID and a password is present in already registered combinations of user IDs and passwords associated with the identified company code.

This configuration makes it possible to more efficiently determine the presence of a matching combination compared with a configuration where the registration unit first identifies already registered combinations of user IDs and passwords that match the received combination of a user ID and a password and then determines whether the company codes associated with the identified combinations match the received company code.

In the present application external apparatuses may correspond to the terminal and the image forming apparatus an information processing system may correspond to any one of the printing systems first and second receiving units may correspond to the print job management apparatus first and second authentication units may correspond to the authentication apparatus a storage unit may correspond to the authentication DB and an output data receiving unit an output data recording unit and first and second output data transmitting units may correspond to the print job management apparatus .

An aspect of this disclosure provides an information processing system an information processing apparatus and an authentication method that make it possible to improve security.

