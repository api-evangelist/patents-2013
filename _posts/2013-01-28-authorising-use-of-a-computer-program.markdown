---

title: Authorising use of a computer program
abstract: A method of authorizing use of a computer program only able to be used when an authorized message is received from an authorizing system includes providing an authorization system, making a request to use a computer program, signalling the request to the authorization system, the authorization system recording the use of the computer program and providing the authorization message to the computer program upon receipt of the authorization message the computer program may be used.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08799667&OS=08799667&RS=08799667
owner: Optimiser Pty Ltd
number: 08799667
owner_city: Osborne Park WA
owner_country: AU
publication_date: 20130128
---
This application is a continuation of U.S. Ser. No. 12 730 679 filed 24 Mar. 2010 which is a continuation of U.S. Ser. No. 10 240 207 filed 23 Apr. 2003 which is a national stage application of PCT AU2001 00350 filed 28 Mar. 2001 which claims benefit of PQ 6544 filed 28 Mar. 2000 in Australia and which applications are incorporated herein by reference. To the extent appropriate a claim of priority is made to each of the above disclosed applications.

The present invention relates to authorising use of a computer program in particular the present invention relates to a method of authorising use of a computer program a computer configured to authorise the use of a computer program and a computer readable media on which is stored computer software for authorising use of a computer program.

There is an increasing need for securing and protection of computer programs and other digital products. This is reflected in an increasing demand for a pay as you use payment arrangement for licensed use of computer software. It is known for a server to provide application software to a plurality of client s machines. Under this model it is possible to provide a pay as you use method of software licensing. Current pricing models used for the payment of software applications are based on per user and seat licensing agreements that are complex restrictive and inefficient especially for client server and application service provider software delivery. Pay as you use pricing is demanded by software users for its simplicity cost effectiveness and flexibility.

There is therefore a need for an alternative method of providing a software licensing system that allows for each user of the software to correspond a payment for that use. The licensed software needs to be able to be prevented from use unless authorised to allow for inter alia payment for using the software.

An object of the present invention is to provide a method of authorising use of a computer program in a manner suitable for implementing inter alia a pay as you use licensing system.

According to the present invention there is provided a method of authorising use of a computer program said method including the steps of 

Preferably the authorisation system records whether the user is verified whether the user is authorised to use the computer program and a time stamp.

Preferably the computer program may be a software application or a sub component of a software application.

Preferably a rate of charging usage units for the use of the computer program is recorded in the authorisation system. A different rate of charge may be applied to different computer programs.

Preferably the usage units are charged by the authorisation system upon receipt of the request to charge for the use of the computer program.

Preferably the request to the authorisation system for charge of usage units is sent once per use of the computer program. Alternatively the request to the authorisation system to charge usage units is sent once per specified period during the use of the computer program.

Preferably the user purchases usage units in advance of use of the computer program the usage unit total being reduced by each charge use being authorised only while there are a positive number of usage units left.

Preferably the authorisation message is encrypted. Preferably the communication between the interface program and the authorisation system is encrypted. Preferably messages to and from the authorisation system includes a unique component that is only valid for a single use so that the message can t be duplicated and used again.

Preferably the user identification is obtained from the user by providing the user with a login prompt the user entering the login identification provided by the authorisation system the entered user identification being included in the login request.

Preferably an interface program signals the login request to the authorisation system. Preferably the interface program is a separate program called by the computer program being authorised as part of the initialisation of the authorised computer program. In one embodiment the interface program forms part of the computer program and is started when a user attempts to use the computer program. In another alternative embodiment the interface program is part of an operating system and is started when a user attempts to use the computer program.

Preferably the authorisation system is at a location remote from a computer running the activated computer program. More preferably the computer running the activated computer program also runs the interface program the interface program communicates with the authorisation system over a computer network.

Preferably the authorisation system is configured to record and authorise a plurality of computer programs. Typically the authorisation system is configured to record and authorise a plurality of uses of the same computer program.

In one embodiment the authorisation is provided for each activation of the computer program. Typically a charge is generated for each use of the computer program. In another embodiment the authorisation is required periodically wherein at the end of a period of time specified in the computer program from the last authorisation a request to charge the usage units is sent to the authorising system for a further authorisation the authorisation system sends each further authorisation and records the use for each period whereby a charge is generated for each authorisation message sent.

In yet another embodiment when the computer program is finished a terminate message is sent to the authorisation system the authorisation system records the duration of the use of the computer program between when the authorisation message is sent to the computer program until the terminate message is received whereby a charge in PUs is generated for use of the computer program corresponding to the recorded duration.

According to another aspect of the present invention there is provided a distributed system for authorising use of a computer program said system comprising at least 

Preferably the computer is configured to sending a request to the authorisation system to record a charge or the use of the computer program against the identified user for use of the computer program.

Preferably the authorisation system records a charge against the user upon receipt of the request to charge for use of the computer program.

Preferably the computer is configured to send a request to the authorisation system to charge the user once per use of the computer program.

Preferably the computer is configured to send a request to the authorisation system to charge the user is sent once per specified period during the use of the computer program.

Preferably the computer is the communication between the computer program and the authorisation system is encrypted.

Preferably the computer and authorisation system are configured to include a unique component in the encrypted messages communicated therebetween.

Preferably the authorisation system is at a location remote from a computer running the activated computer program.

Preferably the computer running the activated computer program also runs the interface program an interface program that communicates with the authorisation system over a computer network.

Preferably the authorisation system is configured to record and authorise a plurality of computer program.

Referring to a system is shown for authorising use of a computer program such as a software application on a computer . The computer program may be a sub component of a larger software application. A user activates the software application for execution on the computer . The software application calls an interface program known as a Software Application Interface Library program SAIL . The SAIL communicates with an on line server via a network such as the Internet . An authorisation system is running on the server . The authorisation system is called a Software Application Licence Manager Over Networks SALMON system. It is noted that the computer platform need not be the same as the server likewise operating systems of the computer and the server need not be the same. The SALMON system is able to handle many software applications on a plurality of computers each having a SAIL interfacing with the SALMON system via a communication network such as the Internet . The SALMON system communicates with the SAIL to determine whether the user is authorised to use the software application . There is a one to one relationship between the user and the instance of the software application. This allows for each user to be charged for each use of the software application.

The SAIL is provided to a software vendor that wishes to use the system of the present invention. The software vendor incorporates calls to the SAIL in the vendor s computer program.

The computer program or software application is written to be disabled from use until the user is identified to the SALMON system using a login routine of the SAIL and receives an authorisation message from the SALMON system . The authorisation message operates as a once off run time licence. The SAIL sends another authorisation message to the software application when it receives the authorised message from the SALMON system .

Specifically when the software application is started it calls a login sub routine of the SAIL . The application waits for the SAIL login sub routine to return a message indicating that the user is logged in. A software vendor wanting to charge for use of the software can decide the price of use. It may be free parts of the software may be charged for or all of the software may be charged for. The cost may be charged on each start up of the application on a time basis or on a per function basis. Different users may be charged different rates. A user is charged for using a program use run time licence unit RTL . The SAIL once logged in can send a message to the SALMON system to record usage of the computer program software application according the payment scheme desired.

Referring to which shows the operation of the present invention in the form of a flow chart. The flow chart starts at where a user wishes to run a software application. The user activates the software application in the normal manner at . The software application interfaces with the SAIL to validate the user at via a login request message which is encrypted with a public key at by the SAIL . The encrypted login request message is communicated over a network such as the internet and is then decrypted with a private key at in a server running the SALMON system . The SALMON system validates the user name password and the status of the application at . If the user is valid and authorised to use the software application a logged in confirmation message is encrypted with a public key at and sent across the network . It is decrypted at with a private key by the SAIL .

If the validation is successful as indicated by the application continues at . If the software vendor wishes the user to pay for the use of the software application the steps from take place. The account creditability is validated at . The SAIL sends a public key encrypted allocate a charge message at over the network . The message is then decrypted with a private key at . The account is checked to determine whether sufficient RTLs are available. If so the required number of RTLs are debited at . A charged confirmation message is encrypted with a public key and sent at across the network and decrypted at with a private key. If the validation is successful the application continues at otherwise it terminates at .

The method of encryption of transmitted messages involves the inclusion of a unique component so that a message is valid only once. Each message is in the form of a binary number to be sent between the SAIL and the SALMON system . A random number is added to the message. A digestion routine takes the data from the message and the random number to produce a digestion value. The digestion value is computed in such a way that finding an input that will exactly generate a given digest is computationally infeasible. The message data the random number and the digestion value are then encrypted using a public key. The message is then transmitted. The received message is then decrypted using a private key. The decrypted message is then separated in to individual components. The message can be validated by using the same digestion formula on the message and random number components to check the digestion result calculated against the digestion value received. If the values are the same the message is considered valid otherwise it is considered invalid. This process provides a different data sequence for each message even if the same acknowledgment message is sent each time. In this way each message includes a unique value which can only be used once. Thus if the message is duplicated it will no longer by valid and will be rejected.

The SALMON system may be configured to allow many users to be authorised at the same time for one or more software application. The software vendor may allow up to a predetermined number of users to login for a particular software application. For each authorised user allowed a login a login resource is allocated in the SALMON system . Each available login resource a login daemon process will be waiting for a user to login.

Referring to until a login is received each of the login daemon processes remains in a not logged in state . Once a login is received the SALMON system enters a logged in state . A routine Can consume RTL checks to see whether RTLs may be consumed until the user logs out at whereupon the login resource of the SALMON system re enters the not logged in state .

Thus checking that sufficient funds in the form of RTLs are available can be a criterion for authorisation.

A user of the software application using the on line pay as you use model must first be registered with the on line SALMON system . They will be provided with a user name and password so that the SALMON system can identify them and the login details verified.

The login of the user is to verify that the user is logged with the on line SALMON system before being able to proceed with use of the software. The software application logs out from the SALMON system in order to provide a clean exit. Generally only one login session per user should be active a previous session must be logged out before another login session can begin.

Referring to the passing of messages is now described. A user activates a software application thereby creating an instance of the software application . The software application then creates an instance of the SAIL . The software application requests details from the user at . The user enters a user name and password at . The software application calls a SAIL login routine of the SAIL at . The SAIL then establishes a connection via the Internet to the SALMON system . The SAIL login routine then passes the user name password and an identification of the software to the SALMON system . Once confirming that the login details are correct the SALMON system sends a login OK message at to the SAIL which then at sends an OK message to the software application .

Depending on the model that the software vendor wishes to use the charge for use of the software an appropriate scheme of using RTLs will be used. The scheme described in relation to is for a one off charge for use of the software application. Other schemes will be described below.

The software application then sends a one off request to consume an RTL at . This request is a SAIL consume RTL call. The SAIL consume RTL sends a consume RTL message to the SALMON system at . The SALMON system records the request to consume RTL and sends an authorisation message at to the SAIL . The SAIL then passes the OK message at to the software application . The software application then begins to log out of the SAIL at . The logout message is then passed from the SAIL to the SALMON system at . A Logout confirmation message is then passed from the SALMON system to the SAIL at . The logout confirmation message is then sent from the SAIL to software application at . The software application may then terminate the SAIL program at . The user may proceed with use of the software application at . Once the user has finished with the software application it may then be terminated at .

The recording of the consumption of a one off consumption of an RTL creates a charge for the one off use of the software application . This charge may be deducted from an amount of RTLs held in credit for the user or may be billed to the user .

Different software applications may request the consumption of different numbers of RTLs. For example a word processing application may consume five RTLs whereas a spreadsheet may consume . As mentioned above the software being authorised need only be a sub component of a large software application. For example a print function may be regarded as the computer program being authorised. For each use of the print function a charge is accrued. A user may also be entitled to a discount such as for example if they are a high volume user. The number of RTLs may then be multiplied by a user discount to produce a final number of RTLs deducted from the user s account.

Referring to the periodic consumption of RTLs is described. Periodic consumption of RTLs may be consumed at a different rate to one off consumption of RTLs. Like numerals depict like actions from . Again the user starts the software application which creates the instance of the SAIL at . Login is requested at and login details are provided to the SAIL at . The login details are then passed from the software application to SAIL at and then onto the SALMON system at . The confirmation of login is passed from the SALMON system to the SAIL at and from the SAIL to the software application at . The user may proceed with the normal use of the application at . In the meantime the software application makes periodic requests to the SAIL for the consumption of an RTL at . The SAIL passes the request to the SALMON system at . The confirmation of the recording of the consumption of the RTL occurs in the SALMON system and the confirmation of this is then passed from the SALMON system to the SAIL at and then from the SAIL to software application at .

At the end of each period a further RTL is consumed as indicated by and . When the user has finished with the application a command is sent to exit from the application at . The software application then sends the logout message to the SAIL at which is the sent on at to the SALMON system . Confirmation of the logout is sent from the SALMON system to the SAIL at and then from the SAIL to the software application at whereupon the software application may end the instance of the SAIL at and then shut itself down.

As an alternative the software application may specify the period to the SAIL and the SAIL handles the operation of sending consume RTL messages to the SALMON system for deduction RTLs from the users account.

The number of periodic RTLs consumed is recorded and a corresponding charge generated. The total charge for the session is deducted from an account or billed out. RTLs may use currency units the consumption of RTLs is in itself payment. The charge for the consumption of each RTL can be arranged by agreement between the software vendor and the system operator.

The SALMON system may be configured to allow many users to be authorised at the same time for one or more software applications. shows a flow chart setting out the establishment of a pay as you use registration according to the present invention. The flow chart begins at where a user wishes to use a software application utilising the system of the present invention. If the user is registered with the administrators of the authorisation SALMON system they proceed down path otherwise they need to register with the administrator in this case OPTIMISER at . An on line registration site is made available over the Internet at where the user can register to use a single software application or a range of software applications . A subscription fee is paid at or depending on whether the user selects a single software application or general use. A rate of for example US 10 per annum is paid if a single application is to be used. An annual subscription of for example US 120 per annum is charged for general use of software. Once this payment is made to the administrator the process continues at as if the person was previously registered.

If the user wishes to use an application that is not pay as you use enabled as indicated at the software vendor will need to register the system with the administrators. If the software is registered it will proceed as indicated by . The software vendor may download website software as indicated by . If the software vendor is not registered with the administrator as indicated by the vendor must register at . Once the vendor is registered the SAIL interface program can be downloaded at and integrated into the vendor s software at .

Once the user is registered the user must have credit available with the administrator. This is checked at . If they don t as indicated by they must purchase RTLs. If they have paid the vendor for usage as indicated by the vendor must pass on the usage payment at to the administrator which will be credited as RTLs. Once the user has RTLs credited as indicated by the user may use the software according to the present invention. When the software application is started the SAIL is activated at as described above with being equivalent to in . The authorisation of the user is indicated by being the equivalent of the OK message in . On line usage reporting indicated by is equivalent to the recording of the logging in and consumption of RTLs. The user may then view their access usage and RTL consumption at a later stage. Even if the software is not charged for use the software can be recorded and tracked.

The SAIL interface may provide a heart beat function that periodically sends the SALMON system a message to check that a connection between the two still exists. If the connection has dropped out it may be re established or the application terminated depending on the security desired by the software vendor.

A list of SAIL Application Program Interface API system calls is listed in appendix 1. A more preferred list of SAIL API system calls is listed in appendix 2. A set of example scenarios showing the use of the SAIL is included in appendix 3.

The SAIL interface as implemented as an Application Programmable Interface API library able to interface with the programming language of the software application. Programming methodologies like ActiveX or CORBA can be used to provide class wrappers around the system API library.

Now that the preferred embodiments have been described it will be clear to the skilled addressee that it has at least the following advantages. A locked software application may be provided to each user that is only able to be unlocked and used where the user purchases run time licences which are consumed on a per use or time basis. This means that software does not need to be downloaded and may be provided on for example a floppy disk CD ROM or DVD ROM. The user only receives use of the software that they pay for and the user only has to pay for the actual use of the software.

It will be clear that modifications and variations can be made to the present invention such as the implementation need not be exactly as described in the above mentioned example the computer language that the underlying software is programmed in may be any suitable language such as Java C or Visual BASIC. The method of charging and or billing for use of the run time licences for the software may vary from those described above. It is also envisages that the present invention may be applicable to authorise specified users to access a program rather than for payment of RTLs. Such a security measure to only allow certain personnel to access sensitive software applications and is able to track their use.

Such modifications and variations are intended to be within the scope of the present invention the nature of which is to be determined from the foregoing description.

Establishes a login and connection to the Optimiser Online Server. It verifies the user and application for a login with the Optimiser Online Server.

The application should exit or prevent the user to continue if the return code is not SAIL SUCCESSFUL

This function should be called before the application exit or when all Run Time Licence RTL consumptions are completed.

Determines whether the current login session has sufficient number of RTLs in the user s Optimiser Online Server account to warrant further consumption by the calling software application.

This operation will debit the currently logged in user s Optimiser Online Server account with the appropriate amount of RTLs based on the name of the calling software application.

A single RTL charge is debited from the user s account for the execution lifetime of the software application being used by the user. This function login connect consume one RTL and close the connection to the Optimiser Online Server.

int Return an error code or SAIL SUCCESSFUL if the was successful. Use GetErrorMessage to return a message string from the error code.

The application should exit or prevent the user to continue if the return code is not SAIL SUCCESSFUL.

int GetDLLVersion int iBufferSize char const clpszVersionString int const clpiVersionMajor int const clpiVersionMinor int const clpiVersionRevision 

Returns the version number of this SAIL to the calling software application. The software application can use this number to keep track and act accordingly of any interface changes to this system if this system is being used in a dynamic environment.

Returns the maximum number of milliseconds to wait for a reply from the Optimiser Online Server before a timeout condition is to be flagged.

Sets the maximum number of milliseconds to wait for a reply from the Optimiser Online Server before a timeout condition is to be flagged.

This operation establishes a connection to the Optimiser Online Server and attempts to authenticate the user of the software application and the version number of the Software Application.

Two worker threads could also be created with this operation. The first thread periodically consumes a single RTL see parameter uiConsumeRTLFrequency for details . The other thread maintains a heartbeat to keep the connection alive see the Remarks section below for details .

Returns an error code or SAIL SUCCESSFUL if the operation was successful. Use SAIL GetErrorMessage to return a textual representation of the error code.

The Software Developer should consider any other errors returned by this operation as serious failures. The Software Application should report the error to the user and then exit cleanly.

The Software Application should not proceed further in its execution until one of the following conditions has been satisfied 

Once a successful connection to the Optimiser Online Server has been established and the user authorised then this operation will create up to two worker threads. One thread maintains a heartbeat to keep alive a connection to the server and the other to periodically consumes RTLs from the logged in user s account.

The frequency of the heartbeat can be set with the operation SAIL SetHeartBeatFrequency . The operation SAIL GetHeartBeatFrequency can be used to determine the current heartbeat frequency. If this frequency is set to zero then the worker thread that performs the heartbeat will not be created.

The period of the RTL consumption is set through the uiConsumeRTLFrequency parameter. At every period a single RTL is consumed and the transaction is recorded with the comment specified in the szConsumeRTLFrequencyComment parameter.

Returns an error code or SUCCESSFULSAIL  if the operation was successful. Use SAIL GetErrorMessage to return a textual representation of the error code.

This logs the user out from the Optimiser Online Server. The invocation of this operation should be called to exit cleanly from the Optimiser Online Server and free any resources SAIL has been allocated with by the underlying operating system.

Returns an error code or SAIL SUCCESSFUL if the operation was successful. Use SAIL GetErrorMessage to return a textual representation of the error code.

The Software Developer should consider any other errors returned by this operation as serious failures. The Software Application should report the error to the user and then exit cleanly.

This operation allows the software developer to retrieve a textual representation of the specified error number.

Returns the maximum size required to be able to store the corresponding textual representation of the specified SAIL error in its entirety.

Determines whether the current login session has sufficient number of RTLs in the user s Optimiser Online Server account to warrant further consumption by the calling Software Application.

Returns an error code or SAIL SUCCESSFUL if the operation was successful. Use SAIL GetErrorMessage to return a textual representation of the error code.

The Software Developer should consider any errors returned by this operation other than SAIL SUCCESSFUL as serious failures. The Software Application should report the error to the user and then exit cleanly.

This operation will debit the currently logged in user s Optimiser Online Server account with the appropriate amount of RTLs based on the name of the calling software application.

Returns an error code or SAIL SUCCESSFUL if the operation was successful. Use SAIL GetErrorMessage to return a textual representation of the error code.

The Software Developer should consider any other errors returned by this operation as serious failures. The Software Application should report the error to the user and then exit cleanly.

The szComment parameter should contain a brief comment about the RTL transaction being performed. The size of the network packets generated by this operation to the Optimiser Online Server is dependent upon the length of this parameter. These network packets should be kept to a minimum size and it is the responsibility of the Software Developer to adopt and maintain this philosophy when invoking this operation.

For this operation to complete successfully the Software Application should be registered with Optimiser Online. The user should also have sufficient RTLs in their Optimiser Online account. Registration and crediting a user s account is beyond the scope of this document. Please contact Optimiser for further information regarding these matters

A single RTL charge is debited from the user s account for the execution lifetime of the software application being used by the user. This operation attempts the following SAIL operations in order 

In addition a worker thread could also be created with this operation. The worker thread periodically consumes a single RTL see parameter uiConsumeRTLFrequency for details .

Returns an error code or SAIL SUCCESSFUL if the operation was successful. Use SAIL GetErrorMessage to return a textual representation of the error code.

The Software Developer should consider any other errors returned by this operation as serious failures. The Software Application should report the error to the user and then exit cleanly.

The szComment parameter should contain a brief comment about the RTL transaction being performed. The size of the network packets generated by this operation to the Optimiser Online Server is dependent upon the length of this parameter. These network packets should be kept to a minimum size and it is the responsibility of the Software Developer to adopt and maintain this philosophy when invoking this operation.

The Software Application should not proceed further in its execution until one of the following conditions has been satisfied 

This operation can create a worker thread. The working thread periodically consumes RTLs from the logged in user s account.

The period of the RTL consumption is set through the uicConsumeRTLFrequency parameter. At every period a single RTL is consumed and the transaction is recorded with the comment specified in the szConsumeRTLFrequencyComment parameter.

Returns the version number of the SAIL library to the calling Software Application. The Software Application can use this number to keep track and act accordingly of any interface changes to this system if this system is being used in a dynamic environment.

Returns the maximum size required to be able to store the SAIL version string into the buffer in its entirety.

Returns the maximum number of milliseconds to wait for a reply from the Optimiser Online Server before a timeout condition occurs.

The default timeout period of 15000 milliseconds is returned if the timeout period has not been previously set by the SAIL SetTimeOutPeriod operation.

Sets the maximum number of milliseconds to wait for a reply from the Optimiser Online Server before a timeout condition is to be flagged.

The default timeout period is 15000 milliseconds if this operation is not invoked to set another timeout period.

Returns an error code or SAIL SUCCESSFUL if the operation was successful. Use SAIL GetErrorMessage to return a textual representation of the error code.

Sets the frequency to signal the server that the application is still active. This signal prevent the disconnection of the network connection.

The HeartBeat is a separate thread that initiates a message on time intervals. This HeartBeat thread will not be created if the SAIL SetHeartBeatFrequency is set to 0 before the SAIL Login function call.

The default frequency of 5 minutes is returned if the frequency has not been previously set by the SAIL SetHeartBeatFrequency operation.

Returns an error code or SAIL SUCCESSFUL if the operation was successful. Use SAIL GetErrorMessage to return a textual representation of the error code.

Having more than one copy of the run time libraries in a process can cause problems because static data in one copy is not shared with the other copy. To ensure that your process contains only one copy avoid mixing static and dynamic versions of the run time libraries. The linker will prevent you from linking with both static and dynamic versions within one .EXE file but you can still end up with two or more copies of the run time libraries. For example a dynamic link library linked with the static non DLL versions of the run time libraries can cause problems when used with an .EXE file that was linked with the dynamic DLL version of the run time libraries.

SAIL can be configured through the setting environment variables prior to executing a SAIL enabled Software Application. The environment variables that SAIL uses are as follows 

If the HTTP PROXY environment variable has not been set then SAIL will determine from the Registry whether an enabled HTTP proxy has been entered for the current user. These settings can be configured through the Internet applet found in Control Panel.

If the registry settings do not exist or the proxy setting has been found disabled then SAIL will not use a proxy to establish a connection to the Optimiser Online Server. SAIL will establish a connection to the Optimiser Online Server directly.

The return codes are listed in the SAIL.H file. The most common error codes and their meanings are listed as follows 

MicroSoft could say that people should pay them 1 for every hour someone uses the MS Word. They could also say that every time one uses the Table functionality they should pay two dollars. The implementation of SAIL would be as follows 

