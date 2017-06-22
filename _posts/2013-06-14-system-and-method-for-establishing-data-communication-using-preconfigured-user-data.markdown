---

title: System and method for establishing data communication using pre-configured user data
abstract: Call party details of a telephone call involving first and second telephony user devices are received. The call party details include first and second identities associated with the first and second telephony user devices respectively. A client-server connection request is received from, and a client-server connection is established with, one of the user devices. A session for the communication of data to and/or from the user devices is established separately from the telephone call on the basis of the first and second identities. The receipt of pre-configured user data by the one of the user devices is enabled via the client-server connection. The pre-configured user data has been specified by a user of another of the user devices prior to the establishment of the telephone call as data for receipt by other user devices during telephone calls conducted by the user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08938055&OS=08938055&RS=08938055
owner: Metaswitch Networks Ltd
number: 08938055
owner_city: Enfield
owner_country: GB
publication_date: 20130614
---
This application is a continuation of International Application No. PCT GB2011 052477 filed Dec. 14 2011 and designating the U.S. which claims priority to Great Britain Patent Application No. 1104613.3 filed Mar. 18 2011 and claims priority to U.S. provisional patent application No. 61 423 055 filed on Dec. 14 2010 both of which are incorporated herein by reference in their entirety.

The present invention relates to the communication of data. In particular but not exclusively the present invention relates to the communication of data between user devices during telephone calls.

Communication between parties in a telecommunications network can be carried out in a number of ways. Most commonly communication is carried out by a calling party dialling the telephone dialling number of a called party telephony device on a calling party telephony device. The dialling of the telephone number causes a call set up process to be carried out in the network which results in the telephone of the called party ringing. If the called party chooses to answer their telephone a telephone call can ensue between the calling party and the called party. The telephone call allows audio data such as speech data to be transferred along an audio channel created between the calling party telephony device and the called party telephony device.

Some telephony devices have enhanced capabilities which allow transfer of video data along a video channel created between the calling party telephone and the called party telephone. A video call may not be possible unless both the calling and called party telephone devices support video call functionality.

Audio or video conferencing may be carried out between three or more remote telephony devices allowing communication of audio and or video data between parties to the conference.

Web conferencing is also possible between multiple remote parties using devices with combined data processing display and telephony capabilities. Web conferencing allows online meetings to be conducted for viewing and or collaborating on common multimedia content.

Parties may also exchange text data by use of text messaging services such as the Short Message Service SMS . Enhanced messaging services such as the Multimedia Messaging Service MMS allow parties to exchange image and video data in addition to text data.

The exemplary methods of communication described above provide a wide range of options for remote parties to communicate with each other. However each method typically has different requirements in terms of device and or network capability and interchanging between the different methods is either not possible or requires use of inconvenient set up or configuration processes.

It would therefore be desirable to provide improved methods for communicating data between remote parties including communication of data in a manner convenient to the parties.

According to a first aspect of the invention there is provided a method of establishing a communications session for communication of data with respect to at least two user devices in a data communications network the method comprising 

receiving call party details of a telephone call the telephone call involving at least a first telephony user device and a second telephony user device said call party details including a first identity associated with said first telephony user device and a second identity associated with said second telephony user device 

receiving a client server connection request from and establishing a client server connection with at least one of said at least two user devices 

establishing on the basis of said first and second identities received in said call party details a separate communications session separate from said telephone call for the communication of data to and or from said at least two user devices and

enabling the receipt of pre configured user data by said at least one of said at least two user devices via said client server connection said pre configured user data having been specified by a user of one other of said at least two user devices prior to the establishment of said telephone call as data for receipt by other user devices during telephone calls conducted by said user.

In accordance with a second aspect of the invention there is provided server apparatus arranged to establish a communications session for communication of data with respect to at least two user devices in a data communications network the server apparatus being arranged to 

receive call party details of a telephone call the telephone call involving at least a first telephony user device and a second telephony user device said call party details including a first identity associated with said first telephony user device and a second identity associated with said second telephony user device 

receive a client server connection request from and establish a client server connection with at least one of said at least two user devices 

establish on the basis of said first and second identities received in said call party details a separate communications session separate from said telephone call for the communication of data to and or from said at least two user devices and

enable the receipt of pre configured user data by said at least one of said at least two user devices via said client server connection said pre configured user data having been specified by a user of one other of said at least two user devices prior to the establishment of said telephone call as data for receipt by other user devices during telephone calls conducted by said user.

In accordance with a third aspect of the invention there is provided a telephony user device for establishing a communications session for communication of data with respect to at least one other user device in a data communications network the telephony user device comprising a processor configured to 

transmit call party details of a telephone call the telephone call involving at least said telephony user device said telephony user device being a first telephony user device and a second telephony user device said call party details including a first identity associated with said first telephony user device and a second identity associated with said second telephony user device 

transmit a client server connection request to and establishing a client server connection with a server 

establish on the basis of said first and second identities received in said call party details a separate communications session separate from said telephone call for the communication of data to and or from said at least one other user device and

transmit pre configured user data to said at least one other user device via said client server connection said pre configured user data having been specified by a user of said telephony user device prior to the establishment of said telephone call as data for transmittal to other user devices during telephone calls conducted by said user.

In accordance with a fourth aspect of the invention there is provided a telephony user device capable of establishing a communications session for communication of data with respect to at least one other user device in a data communications network the telephony user device comprising a data store and a processor configured to 

transmit call party details of a telephone call the telephone call involving at least said telephony user device said telephony user device being a first telephony user device and a second telephony user device said call party details including a first identity associated with said first telephony user device and a second identity associated with said second telephony user device at least one of said first and second identities comprising a telephone dialling number 

transmit a client server connection request to and establish a client server connection with a server 

establish on the basis of said first and second identities received in said call party details a separate communications session separate from said telephone call for the communication of data to and or from said at least one other user device 

present the user of said telephony user device with an option to update said data store with at least a part of said received data.

Further features and advantages of the invention will become apparent from the following description of preferred embodiments of the invention given by way of example only which is made with reference to the accompanying drawings.

PLMN A and PLMN B contain mobile telephony network infrastructure including one or more mobile switching centres one or more base station controllers and one or more base transceiver stations the function of such entities is well known in the art and will not be described in detail here.

PLMN A and PLMN B are connected via a telecommunications network comprising one or more Public Switched Telephone Networks PSTNs and or packet networks. Telecommunications network comprises one or more media and or signalling gateway entities not shown for performing conversion between the various protocols and data formats used to transfer media and signalling data within and between the different networks. Server has an associated data store and is connected to telecommunications network via a packet network .

Although server is depicted as a single entity in server may be a single device a cluster of servers or servers distributed throughout the data communications network.

MS A has an associated identity in the form of a telephone dialling number TDN TDN A. MS B has an associated identity in the form of a telephone dialling number TDN B. MS A has communication session application software running on it with an associated application identifier AppID A. MS B also has communication session application software running on it with an associated application identifier AppID B.

In some embodiments of the invention during installation of the application software on MS A server may be informed of AppID A and creates a record for MS A in data store containing AppID A stored in association with TDN A. Similarly in some embodiments of the invention during installation of the application software on MS B server may informed of AppID B and creates a record for MS B in data store containing AppID B stored in association with TDN B.

In this and subsequent flow diagrams solid arrows denote transfer of control messaging or signalling data whereas dashed arrows denote transfer of media or payload data.

A voice call is currently in progress between MS A in PLMN A and MS B in PLMN B as shown by item . The voice call will typically be a circuit switched voice call the set up and control for which is known in the art.

Application software running on MS A detects that there is a call in progress between MS A and MS B and notifies server of call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with MS A and TDN B associated with MS B in step . Similarly application software running on MS B detects the call in progress between MS B and MS A and notifies server of call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with MS A and TDN B associated with MS B in step

Application software running on MS A may detect that the call is in progress by registering with the operating system of MS A to be notified upon start of a call involving MS A. This could for example involve registering with an application programming interface API of the operating system of MS A associated with start and end of call events. A similar call detection process may occur on MS B.

In these embodiments the user of MS A could be the calling or the called party for the call. Call party details are received from both telephony apparatus acting on behalf of the calling party and telephony apparatus acting on behalf of the called party for the call e.g. telephony device MS A and telephony device MS B.

Server identifies that the notification of step from MS A and notification of step from MS B have call party details TDN A and TDN B in common and establishes a separate communications session separate from the telephone call for the communication of data between MS A and MS B. The separate communications session is established on the basis of the received call party details TDN A and TDN B. The separate communications session is established whilst the telephone call is in progress and is continued in parallel with the telephone call such that voice call data is transmitted via the telephone call and other data may be transmitted via the communications session after the establishment of the separate communications session.

Server updates the records for MS A and MS B in data store to indicate that a call is in progress between MS A and MS B and that a communications session between MS A and MS B separate to the voice call between MS A and MS B has been established in step

Server may respond not shown to the notifications of steps and by responding with respective acknowledgements to MS A and MS B.

If MS A wants to communicate data to e.g. share data with MS B it transmits the data to server in step . Server performs a lookup in data store using TDN A for MS A in step and identifies that a communications session has been established between MS A and MS B. Server retrieves TDN B for MS B in step and transmits the data received from MS A to MS B using the retrieved TDN B in step

In embodiments of the invention the lookup in data store of step may also result in AppID B being retrieved. The data may then be transmitted to MS B using both TDN B and AppID B with TDN B being used to locate MS B and AppID B being used to direct the data to the communications session application software running on MS B. The data may be transmitted by means of a push notification directed to AppID B of the communication session application on MS B. In the case of MS B being an Apple iPhone the push notification could employ use of the Apple Push Notification Service APNS .

If MS B wants to send data to MS A it sends the data to server in step . Server performs a lookup in data store using TDN B for MS B in step and identifies that a communications session has been established between MS B and MS A. Server retrieves TDN A for MS A in step and transmits the data received from MS B to MS A using the retrieved TDN A in step

In embodiments of the invention the lookup in data store of step may also result in AppID A being retrieved. The data may then be transmitted to MS A using both TDN A and AppID A with TDN A being used to locate MS A and AppID A being used to direct the data to the communications session application software running on MS A. The data may be transmitted by means of a push notification directed to AppID A of the communication session application on MS A.

In embodiments of the invention the communication session is established in the form of a client server relationship with server acting as the server and each of MS A and MS B acting as clients. One connection is created between server and MS A and another connection is created between server and MS B. The two connections together create a channel between MS A and MS B through which data can be communicated in either direction.

In embodiments of the invention server establishes client server connections with MS A and MS B in response to receiving one or more client server connection requests.

In embodiments of the invention a client server connection request is transmitted in response to the telephone call being established between MS A and MS B. In other embodiments a client server connection request is transmitted in response to initiation of a data communications service on MS A or MS B after the telephone call is established between them.

Each of the connections could be HyperText Transfer Protocol HTTP or HyperText Transfer Protocol Secure HTTPS connections.

To avoid loss of the channel between MS and MS B the connections can be maintained by maintenance messages heartbeats transmitted from server to MS A and MS B for example transmitted at periodic intervals sufficiently short to prevent time out of the connections due to inactivity e.g. a client server connection can be maintained by transmitting a message to keep the connection alive if the telephone call lasts more than a connection threshold period.

The data communicated via the session may comprise server receiving data identifying a downloadable resource selected from the group consisting of a photographic image data file a word processing document data file a spreadsheet document data file a presentation document data file a video image data file and streaming video from one of MS A and MS B during the separate communications session and transmitting the data to the other of MS A and MS B for example via the client server connection.

In embodiments of the invention the communications session between MS A and MS B can be maintained after the voice call is terminated allowing the users of MS A and MS B to continue communicating data between their user devices.

In alternative embodiments of the invention the separate communications session is established via server and data is transmitted via a data communication path between MS A and MS B which is established on the basis of information received from said server but with server not being including in the data communication path.

Server may receive a service data object from MS A or MS B during the separate communications session and transmit the service data object to the other of MS A and MS B.

Server may receive a service data object from MS A or MS B during the separate communications session process the service data object in combination with additional service data to generate derived service data and transmit the derived service data to the other of MS A and MS B.

Application software running on MS A detects that there is a call in progress between MS A and MS B and notifies server of call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with MS A and TDN B associated with MS B in step . Here however MS B does not have application software or any other capability which can detect the call with MS A and notify server of such. Instead server notifies MS B of the receipt of call party details for the call from MS A by transmitting a separate communication session initiation request to MS B in step . The communication session initiation request may cause a message such as Do you want to establish a data communication session with the party you are speaking to or such like. If the user of MS B accepts the request by appropriate user input MS B transmits a separate communication session initiation response to server in step indicating that a communication session between MS B and MS A separate to the voice call should be established.

In these embodiments the user of MS A could be the calling or the called party for the call. Call party details are received from either telephony apparatus acting on behalf of the calling party or telephony apparatus acting on behalf of the called party e.g. MS A.

Once the response of step is received server updates the records for MS A and MS B in data store in step to indicate that a call is in progress between MS A and MS B and that a separate communications session between MS A and MS B should be established.

Similarly to described above server establishes a separate communications session separate from the telephone call for the communication of data between MS A and MS B. The separate communications session is established on the basis of the received call party details e.g. TDN A and TDN B whilst the telephone call is in progress and is continued in parallel with the telephone call such that voice call data is transmitted via the telephone call and other data can be transmitted via the communications session after the establishment of the separate communications session.

Communication of data from MS A to MS B can now occur in steps to by a similar process to that described above for steps to in relation to . Further communication of data from MS B to MS A can now occur in steps to in a similar process to that described above for steps to in relation to .

The embodiments of however involve an analogue telephone sometimes referred to as a Plain Old Telephone Service POTS telephone or a black phone denoted POTS A located in PSTN A and a mobile station MS B located in PLMN B. PSTN A and PLMN B are connected via a telecommunications network comprising one or more PSTNs and or packet networks. Further the user of POTS A also has an associated personal computer PC A connected to packet network .

In these embodiments of the invention the user of POTS A cannot conduct communications sessions separate to voice calls conducted via POTS A just using POTS A alone. The user of POTS A therefore additionally employs PC A through which separate communications sessions can be conducted. To provide both voice calls via POTS A and separate communication sessions via PC A POTS phone and PC A are coupled together logically.

POTS A has an associated telephone dialling number TDN A and MS B has an associated telephone dialling number TDN B. PC A has an associated network address in the form of an Internet Protocol IP address IP A in packet network . MS B has communications session application software running on it with an associated identifier AppID B.

PSTN A includes a network element in the form of a call switching element sometimes referred to as a Service Switching Point SSP which is capable of detecting whether a query should be raised in relation to calls to from particular telephone dialling numbers by analysing in call signalling information for the calls. Network element acts on behalf of the user of POTS A and PC A and is configured to trigger a query e.g. hand call control to a service control point SCP network node when it detects a predetermined call state for a call to from TDN A associated with POTS A for example by use of an Intelligent Network IN or Advanced Intelligent Network AIN call origination termination trigger. SCP is a network node responsible for deciding upon how such queries should be dealt with and acting accordingly for example responding to network element with appropriate instructions. The query from network element to SCP may pass via one or more Signalling Transfer Points STPs not shown .

Upon receipt of in call signalling information relating to a query from network element SCP is configured to trigger notification of such to server . Any such notification to server will include call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with POTS A and TDN B associated with MS B.

Configuration of SCP may involve storing an IP address for server in association with TDN A such that when in call signalling information relating to a call to from POTS A is received notification to server at the stored IP address is triggered.

In the embodiments of POTS A has no communication session application software running on it. Further POTS A has no capability to generate notifications when a call is outgoing from or incoming to POTS A.

Instead PC A has communication session application software running on it for facilitating communication sessions according to embodiments of the invention.

During installation of the communication session application software on PC A server is informed that PC A and POTS A are to be coupled together logically. PC A sends IP A and TDN A to server which creates a record for the user of POTS A and PC A in data store containing IP A stored in association with TDN A. Similarly during installation of the application software on MS B server is informed of AppID B and creates a record for MS B in data store containing AppID B stored in association with TDN B.

In the case of an outgoing call being made by POTS A to MS B network element receives in call signalling information for the call including TDN A for which an AIN call origination trigger is configured. This triggers notification of call party details for the call to server in step

In the case of an incoming call being received by POTS A from MS B network element receives in call signalling information for the call including TDN for which an AIN call termination trigger is configured. This triggers notification of call party details for the call to server in step

A call termination origination trigger relating to a call to from POTS A will include call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with POTS A and TDN B associated with MS B.

Application software running on MS B detects the call in progress between MS B and POTS A and notifies server of call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with POTS A and TDN B associated with MS B in step

In these embodiments the user of POTS A could be the calling or the called party for the call. Call party details are received from telephony apparatus acting on behalf of the calling party and telephony apparatus acting on behalf of the called party e.g. network element and MS B.

Server identifies that the notification of step from network element and the notification of step from MS B have call party details TDN A and TDN B in common e.g. server matches the call party details received on behalf of each respective party to the call.

Server maps the identity TDN A of POTS A to the network address for PC A e.g. IP A by reference to data store . Alternatively IP A may be received during the call along with the call party details.

Server establishes a communications session separate from the telephone call between POTS A and MS B for the communication of data between PC A and MS B. The separate communications session is established on the basis of the received call party details e.g. TDN A and TDN B. Once the separate communications session is established voice call data is transmitted via the telephone call and other data can be transmitted via the separate communications session.

Server notifies PC A via IP A that a call has been detected between POTS A and MS B and that a separate communications session has been established between PC A and MS B in step

Server updates the records for POTS A PC A and MS B in data store in step to indicate that a call is in progress between POTS A and MS B and that a separate communications session between PC A and MS B has been established.

If the user of POTS A and PC A wants to communicate data to MS B the user sends the data using PC A to server in step . Server performs a lookup in data store using IP A for PC A in step and identifies that a communications session has been established between PC A and MS B separately to the call taking place between POTS A and MS B. Server retrieves TDN B for MS B in step and transmits the data received from PC A to MS B using the retrieved TDN B in step

In embodiments of the invention the lookup in data store of step may also result in AppID B being retrieved. The data may then be transmitted to MS B using both TDN B and AppID B with TDN B being used to locate MS B and AppID B being used to direct the data to the communications session application software running on MS B.

If the user of MS B wants to send data to the user of POTS A and PC A the user of MS B sends the data to server in step . Server performs a lookup in data store using TDN A for POTS A in step and identifies that a communications session has been established between PC A and MS B separately to the call taking place between MS B and POTS A. Server retrieves IP A for PC A in step and transmits the data received from MS B to PC A using the retrieved IP A in step

In alternative embodiments of the invention instead of both call party detail notifications being sent to server in steps and server may instead notify MS B of the request from PC A to initiate establishment of a separate communications session in a similar manner to step described above in relation to . Similarly to step MS B will then transmit a communication session initiation response in response to user input on MS B indicating acceptance of the request to server indicating that a communication session separate to the voice call between POTS A and MS B should be established between MS B and PC A.

Similarly to embodiments of the invention described above in relation to the communication session is established in the form of a client server relationship with server acting as the server and each of PC A and MS B acting as clients. One connection is created between server and PC A and another connection is created between server and MS B. The two connections together create a channel between PC A and MS B through which data can be communicated in either direction.

In some embodiments of the invention establishing the session comprises receiving a client server connection request from PC A and establishing a client server connection with PC A. In other embodiments of the invention establishing the session comprises receiving a client server connection request from MS B and establishing a client server connection with MS B.

In embodiments of the invention the client server connection request is transmitted in response to the telephone call between POTS A and MS B being established. In other embodiments of the invention the client server connection request is transmitted in response to initiation of a data communications service on PC A after the telephone call between POTS A and MS B is established.

If the call between POTS A and MS B is terminated at any stage and server receives an indication of such a notification message may be transmitted to PC A to inform it of a change of state of the separate communication session.

In alternative embodiments of the invention network element is a call initiating element for example configured to initiate the establishment of the telephone call between POTS A and MS B in response to a remote click to dial website action by a user.

Configuration of SCP may involve storing an IP address IP A for PC A in association with TDN A such that when a call is received to from POTS A PC A can be notified at the stored IP address.

In the embodiments of when network element detects the call being conducted between POTS A and MS B it transmits call party details for the call TDN A and TDN B to PC A in step . PC A forwards the call party details notification including TDN A and TDN B to server in step

Application software running on MS B detects the call in progress between MS B and POTS A and notifies server of call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with POTS A and TDN B associated with MS B in step

In these embodiments the user of POTS A could be the calling or the called party for the call. Call party details are received from telephony apparatus acting on behalf of the calling party and telephony apparatus acting on behalf of the called party e.g. PC A and MS B.

In the embodiments of MS A has communication session application software running on it with an associated identifier AppID A. However MS A does not have application software or any other capability for detecting calls to from MS A and notifying server of such.

MS B has communication session application software running on it with an associated identifier AppID B. In addition MS B has application software running on it which is capable of detecting calls to from MS B and notifying server of such.

During installation of the communication session application software on MS A server is informed of AppID A and creates a record for MS A in data store containing AppID A stored in association with TDN A. Similarly during installation of the communication session application software on MS B server is informed of AppID B and creates a record for MS B in data store containing AppID B stored in association with TDN B.

PLMN A includes a network switching element for example an SSP capable of generating queries in response to triggers configured for calls to from MS A. Network element of generates queries to SCP in a similar manner to network element described above in relation to . The network element of generates queries in relation to wireline network triggers for example Advanced Intelligent Network AIN triggers generated within PSTN of . In however the queries are generated in relation to wireless network triggers such as Customised Applications for Mobile networks Enhanced Logic CAMEL or Wireless Intelligent Network WIN triggers.

Network switching element is configured to trigger a query including in call signalling information to a service control point SCP network node when it detects a call to from TDN A associated with MS A. Upon receipt of in call signalling information relating to a query from network element SCP is configured to trigger notification of such to server . Any such notification to server will include call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with POTS A and TDN B associated with MS B.

Configuration of SCP may involve SCP storing an IP address for server in association with TDN A such that when in call signalling information relating to a call to from POTS A is received notification to server at the stored IP address is triggered.

In the case of an outgoing call being made by MS A to MS B network element receives in call signalling information for the call including TDN A for which a wireless call origination trigger is configured. This triggers notification of call party details for the call to server in step

In the case of an incoming call being received by MS A from MS B network element receives in call signalling information for the call including TDN A for which a wireless call termination trigger is configured. This triggers notification of call party details for the call to server in step

A call termination origination trigger relating to a call to from MS A will include call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with MS A and TDN B associated with MS B.

Application software running on MS B detects the call in progress between MS B and MS A and notifies server of call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with MS A and TDN B associated with MS B in step

In these embodiments the user of POTS A could be the calling or the called party for the call. Call party details are received from telephony apparatus acting on behalf of the calling party and telephony apparatus acting on behalf of the called party e.g. network element and MS B.

Server identifies that the notification of step from network element and the notification of step from MS B have call party details TDN A and TDN B in common and establishes a communications session separate from the telephone call between MS A and MS B for the communication of data between MS A and MS B. The separate communications session is established on the basis of the received call party details e.g. TDN A and TDN B. Once the separate communications session is established voice call data is transmitted via the telephone call and other data can be transmitted via the separate communications session.

Server notifies MS A that a call has been detected between MS A and MS B and that a separate communications session has been established between MS A and MS B in step

Server updates the records for MS A and MS B in data store in step to indicate that a call is in progress between MS A and MS B and that a separate communications session between MS A and MS B has been established.

Communication of data from MS A to MS B can now occur in steps to by a similar process to that described above for steps to in relation to . Further communication of data from MS B to MS A can now occur in steps to in a similar process to that described above for steps to in relation to .

In alternative embodiments of the invention instead of both call party detail notifications being sent to server in steps and server may instead notify MS B of the request from MS A to initiate establishment of a separate communications session in a similar manner to step described above in relation to . Similarly to step MS B will then transmit a communication session initiation response in response to user input on MS B indicating acceptance of the request to server indicating that a communication session separate to the voice call between MS A and MS B should be established between MS B and MS A.

Similarly to steps to described above in relation to steps to of depict detection of a voice call between POTS A and MS B by network element and notification of such to server detection of the call between POTS A and MS B by MS B and notification of such to server establishment of a separate communications session between PC A and MS B and notification of such to PC A and updating of data store .

In these embodiments the user of POTS A and PC A wishes to use a software component in the separate communications session with MS B and transmits from PC A an identifier for the software component for example an application name file name or Uniform Resource Locator URL to server in step . The software component may for example comprise a plug in relating to the communications session application software installed on MS B and PC A.

Server performs a lookup in data store using IP A for PC A in step and identifies that a communications session separate to the voice call between POTS A and MS B has been established between PC A and MS B. Server retrieves TDN B for MS B in step and proceeds to enable download of the software component by MS B.

Server enables the download by transmitting the identifier for the software component received from PC A to MS B in step . The identifier could be transmitted to MS B embedded in a text message such as an SMS message.

Using the received software component identifier MS B sends a download request for the software component to content server in step . Content server then provides the software component to MS B in step

If the user of MS B wants to communicate data relating to use of the software component to the user of POTS A and PC A MS B transmits such data to server in step . When server receives the data from MS B in step it performs a lookup in data store using TDN B for MS B in step and identifies that a separate communications session has been established between PC A and MS B. Server retrieves IP A for PC A in step and transmits the data received from MS B to PC A in step . Data may be communicated from PC A to MS B in a similar manner as per steps to described above in relation to .

When server receives the software component identifier in step it may identify that further information is required for downloading the software component for example if only an application name is supplied by PC A. The further information could include an IP address domain name or URL for locating content server in packet network such further information may be stored locally to server or could be obtained via a search or query process carried out by server within packet network or beyond. In such a case server will additionally provide such further information to MS B in step

In alternative embodiments of the invention when server receives the software component identifier in step it performs a lookup in data store and identifies that that a separate communications session has been established between PC A and MS B. Server then downloads the software component from content server itself using the software component identifier received from PC A and transmits the software component directly to MS B.

In further alternative embodiments of the invention instead of PC A transmitting an identifier for the software component to server as per step PC A transmits the software component itself to server . Server performs a lookup in data store and identifies that that a separate communications session has been established between PC A and MS B and transmits the software component received from PC A to MS B.

In embodiments of the invention before download of the software component to MS B or PC A is enabled a capability check is conducted to determine whether MS B or PC A is initially enabled with the software component. If the capability check indicates that the respective user device is not initially enabled with the software component then enabling of the download may proceed.

In some embodiments capability data for one or more user devices is stored in data store and server may carry out a capability check by reference to data store . In other embodiments the capability check involves transmitting a capability query to a user device and receiving a response indicating whether said the device is initially enabled with the software component.

In embodiments of the invention the separate communications session is established using a session establishment software application or operating system function on the user device to which the software component is being downloaded to and the software component is a software application which interoperates with the session establishment software application or operating system function.

In embodiments of the invention a client server connection request is transmitted by the user device to which the software component is being downloaded to server and a client server connection is established between server and that device. The software component is transmitted via the established client server connection. The client server connection request could be transmitted in response to the telephone call being established or in response to a notification received during the telephone call after the telephone call is established.

Steps to of depict detection of a voice call between POTS A and MS B by network element and notification of call party details for such to server detection of the call between POTS A and MS B by MS B and notification of call party details for such to server as well as notification of the detected call to PC A.

When server receives the call party details for the call between POTS A and MS B in steps and it performs a lookup in data store for the TDNs of MS A and MS B in step . From the lookup information received in step server identifies that MS B is an initially non enabled user device that does not currently have a capability associated with participating in a communication session separate to the voice call between POTS A and MS B.

For example a data record for MS B in data store may indicate that MS B does not have communications session software installed on it or there may be no data record at all for MS B in data store which also indicates that MS B does not have communications session software installed on it.

In these embodiments in order to provide the initially non enabled user device MS B with the capability associated with participating in the session server enables the download of a software application to the initially non enabled user device MS B.

Server enables the download of the software application by transmitting an identifier for the software application to MS B in step . The identifier could be transmitted to MS B embedded in a text message such as an SMS message.

Using the received software application identifier MS B sends a download request for the software application to content server in step . Content server then provides the software application to MS B in step

MS B proceeds to install the software application which when installed sends an installation confirmation message to server in step . Server is now able to establish a communications session between PC A and MS B which is separate to the voice call being conducted between POTS A and MS B.

Once the separate communications session between MS B and PC A is established MS B may communicate data to PC A as shown in steps to in a similar manner to steps to as described above in relation to . Further communication of data from MS B to MS A can now occur not shown in a similar process to that described above for steps to in relation to .

In embodiments of the invention establishment of the separate communications session may be initiated by the user of POTS A and PC A for example by user input on PC A. The user input causes communications session software installed on PC A to transmit a communications session initiation request message to server which then proceeds to establish a separate communications session as described above.

Similarly to steps to described above in relation to steps to of depict detection of a voice call between POTS A and MS B by network element and notification of call party details for such to server detection of the call between POTS A and MS B by MS B and notification of such to server establishment of a separate communications session between PC A and MS B and notification of such to PC A and updating of data store accordingly.

In these embodiments the user of POTS A and PC A transmits from PC A an identifier identifying a feature of the communications session separate to the voice call between POTS A and MS B that requires authorisation for use by MS B in step . The feature could for example be a software component or media data and the identifier could be a URL or other network address at which the feature can be located.

Upon receipt of the feature identifier server transmits an authorisation requirement query containing the feature identifier to authorisation server in step . The authorisation requirement query has the effect of asking the authorisation server whether authorisation for use of the identified feature by MS B in the separate communications session is required. Authorisation server performs any appropriate checks for example with reference to a copyright records database not shown and transmits an authorisation requirement response back to server in step . In this case the authorisation requirement response of step indicates that authorisation for use of the identified feature by MS B is required for example A copyright fee of xx must be paid for use of the identified feature in the separate communications session.

Server now requests authorisation from the user of PC A and POTS A to authorise the use of the identified feature by MS B in the separate communications session in step for example asking the user of POTS A and PC A whether they are willing to accept the xx copyright charge. The user of POTS A and PC A accepts the charge by appropriate input via PC A which results in an indication of authorisation being transmitted from PC A to server in step

When server receives the authorisation indication of step from PC A server enables the use of the feature by MS B in the separate communications session. Server contacts authorisation server in step requesting that authorisation for the identified feature be granted. Server responds to server with an authorisation grant in step

Granting authorisation may involve authorisation server contacting a payment server of an appropriate financial institution on behalf of the user device in question for example to pay a copyright fee for use of the feature. The charge will generally be passed on to a an account associated with the user of POTS A and PC A because it is that user who is requesting use of the identified feature by the user of MS B in the separate communications session.

The user of PC A is informed that authorisation of the feature has been granted by a message transmitted from server to PC A in step for example including confirmation of the amount charged to their account.

Server enables use of the feature for MS B by transmitting an identifier for the feature along with an authorisation token proving that use of the feature by MS B has been authorised. The user of MS B can then download not shown or otherwise access the feature using the feature identifier and authorisation token received from server without having to request authorisation or pay for such . Download of the feature may involve contacting a content server such as item in .

The authorisation token may include a purchase token proving that a copyright fee or suchlike has already been paid for use of the feature.

In some embodiments of the invention the feature may involve using a service application which requires authorisation in order to process service data transmitted during the separate communications session. In alternative embodiments of the invention the feature may involve accessing data which requires authorisation in relation to which an identifier is transmitted during the separate communications session.

Network element receives in call signalling information for the call between MS A and MS B which triggers notification of call party details including TDN A and TDN B for the call to server in step

Application software running on MS B detects the call in progress between MS B and MS A and notifies server of call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with MS A and TDN B associated with MS B in step

Server identifies that the notification of step from network element and the notification of step from MS B have call party details TDN A and TDN B in common and establishes a communications session separate from the telephone call between MS A and MS B for the communication of data between MS A and MS B. The separate communications session is established whilst the telephone call is in progress on the basis of the received call party details e.g. TDN A and TDN B. Once the separate communications session is established voice call data is transmitted via the telephone call and other data can be transmitted via the separate communications session.

Server notifies MS A that a call has been detected between MS A and MS B and that a separate communications session has been established between MS A and MS B in step

Server updates the records for MS A and MS B in data store in step to indicate that a call is in progress between MS A and MS B and that a separate communications session between MS A and MS B has been established.

In these embodiments the user of MS A wishes to obtain geographical location data for MS B for example to use in relation to a map creation application running on MS A. MS A transmits a geographical location capability check message to server in step the capability check message is for checking the capability of MS B to provide geographical location data relating to its physical location for example checking if MS B has a map creation application running on it.

Server forwards the geographical location capability check message on to MS B in step . Mobile station MS B responds by sending a geographical location capability response message to server in step which forwards this on to MS A in step the capability response message includes information as to whether MS B can provide geographical location data relating to its physical location.

In this embodiment of the invention the capability response message informs MS A that MS B is able to provide geographical location data by use of its geographical location module so MS A transmits a request for geographical location data for MS B to server in step . Server forwards the request from MS A to MS B in step

When MS B receives the request for geographical location data from server in step MS B instructs its geographical location module to carry out a geographical location process and provide geographical location data relating to the physical location of MS B in step . The geographical location data resulting from step is transmitted to server in step . Server then transmits data including or derived from the geographical location data received in step to MS A in step

The map creation application of MS A can use the geographical location data received from server in step to create a map which incorporates a representation of the physical location of MS B. For example the received geographical location data may include a grid reference or longitude and latitude parameters which can be processed by the map creation application to plot the location of MS B within a map stored or accessible by MS A. Such embodiments could for example be useful for the user of MS A to give directions to MS B verbally during the telephone call being conducted via MS A and MS B with reference to the created map and indication of the location of MS B thereon.

In embodiments of the invention steps to are repeated allowing display of a dynamically updating map on MS A that shows changes in the physical location of MS B as they happen. Alternatively steps to can be repeated allowing updating of the map on MS A without further requests as per steps and being required.

In embodiments of the invention where MS B is not able to provide geographical location data for example because MS B has no geographical location module or other such capability the capability response message of step will state so thus informing MS A that communication of geographical location data from MS B is not possible. In alternative embodiments of the invention where MS B is not able to provide geographical location data MS B may not send any capability response message and after a predetermined period with no response being received MS A might conclude that communication of geographical location data from MS B will not be possible.

In further alternative embodiments of the invention the geographical location capability check message of step can be combined with the request for geographical location data of step and the geographical location capability response message of step can be combined with the transmittal of geographical location data of step

Embodiments of the invention involve MS A checking the capability of MS B to process and or display geographical location data by transmitting a geographical location capability check message to server in step . Server forwards the geographical location capability check message on to MS B in step . Mobile station MS B responds by sending a geographical location capability response message to server in step which forwards this on to MS A in step

In this embodiment of the invention the capability response message informs MS A that MS B is able to process geographical location data by use of its map creation application so the user of MS A triggers generation of appropriate geographical location data by appropriate input to the mapping application of MS A. Alternatively generation of geographical location data could occur upon receipt of the capability response message of step without any input from the user of MS A being required.

MS A instructs its geographical location module to carry out a geographical location process and provide geographical location data relating to the physical location of MS A in step . The geographical location data resulting from step is transmitted to server in step . Server then transmits data including or derived from the geographical location data received in step to MS B in step

The map creation application of MS B can use the geographical location data received from server in step to create a map which incorporates a representation of the physical location of MS A. Such embodiments could for example be useful for the user of MS B to give directions to the user of MS A verbally during the telephone call being conducted via MS A and MS B with reference to the created map and indication of the location of MS A thereon.

In embodiments of the invention steps to can be repeated allowing display of a dynamically updating map on MS B that depicts changes in the physical location of MS A as they occur.

In alternative embodiments of the invention MS B has no map creation application for creating maps for display on MS B but does have the capability to display images such information being indicated in the location capability response message of step . In such embodiments the MS A itself plots a map containing a physical representation of its physical location and creates an map image for example a screenshot from the map creation application depicting this information for transmittal to MS B via server in steps and these steps would therefore involve transmittal of media image data. Upon receipt of the image data MS B is able to display the image of the map created and provided by MS A thus allowing the user of MS B to view a representation of the physical location of MS A even though MS B has no map creation capability itself.

In further alternative embodiments of the invention where MS B has no map creation application for creating maps for display on MS B but does have the capability to display images a network link such as a URL for an online mapping service such as Google Maps is transmitted to MS B. The network link contains information relating to the physical location of MS A and can be created by MS A and transmitted to server for transmittal on to MS B or can be derived from the geographical location data received from MS A by server and transmitted on to MS B. When MS B receives the network link it accesses the mapping service using the received network link. The mapping service uses the information in the network link relating to the physical location of MS A to generate a map image including a representation of the physical location of MS A and transmits the map image to MS B. Once MS B has downloaded the map image it displays the map image to the user of MS B thus allowing the user of MS B to view a representation of the physical location of MS A even though MS B has no map creation capability itself.

In embodiments of the invention the geographical location data is received by server in the form of a data object including geographical coordinate data. A capability check can then be carried out by server in relation to whether the respective user device is capable of processing the geographical coordinate data during the separate communications session. If the capability check indicates that the respective user device is capable of processing the geographical coordinate data server will transmit the geographical coordinate data during the separate communications session.

Establishing the separate communication session may comprise receiving a client server connection request from and establishing a client server connection with the appropriate user device and transmitting the data including or derived from the received geographical location data via the client server connection.

Embodiments of the invention described below in relation to involve enabling the receipt of pre configured user data by user devices during telephone calls conducted between the user devices. The pre configured user data is specified by a user of a user device prior to establishment of a telephone call as data for receipt by other user devices during telephone calls conducted by the user.

The separate communication session is used to receive user data other than the call party details such as the telephone dialling numbers of a call without the participants to the call having to explicitly transmit the user data themselves. In embodiments of the invention enabling of the receipt of the pre configured user data occurs during a call between user devices and is triggered by establishment of a separate communications between the user devices.

The pre configured user data is specified by a user of a user device as data for receipt by other user devices during telephone calls between the user and other users e.g. the user can choose certain user data prior to making a telephone call which will be received by the other user device of the other party or parties in the case of a teleconference to the telephone call via the separate communication session. The pre configured user data may comprise data other than the first and second identities received in the call party details of a call.

A user may specify their user data for receipt by other user devices during telephone calls via their telephony user device for example using personal information manager PIM application software on their telephony user device. A user may configure their pre configured user data by linking to a record in the PIM. A user may also specify their pre configured user data for transmittal during telephone calls directly to server for example via a web interface.

In these embodiments of the invention the user of MS A has specified prior to establishment of telephone calls conducted by the user pre configured user data for receipt by other user devices during telephone calls conducted using MS A the user s pre configured user data is stored on memory associated with MS A.

Similarly the user of MS B has specified prior to establishment of telephone calls conducted by the user pre configured user data for receipt by other user devices during telephone calls conducted using MS B the user s pre configured user data is stored on memory associated with MS B.

These embodiments of the invention involve enabling the receipt of pre configured user data configured by the user of MS A by MS B via a separate communications session and also involve enabling the receipt of pre configured user data configured by the user of MS B by MS A via a separate communications session during a call conducted using MS A and MS B.

Similarly to described above a voice call is currently in progress between MS A in PLMN A and MS B in PLMN B as shown by item . Application software running on MS A detects the call in progress between MS A and MS B and notifies server of call party details for the call e.g. the TDNs of telephones involved in the call TDN A associated with MS A and TDN B associated with MS B in step . Similarly application software running on MS B detects the call in progress between MS B and MS A and notifies server of call party details for the call e.g. the TDNs of telephones involved in the call TDN B associated with MS B and TDN A associated with MS A in step

Server identifies that the notification of step from MS A and the notification of step from MS B have call party details TDN A and TDN B in common and establishes a communications session separate from the telephone call between MS A and MS B for the communication of data between MS A and MS B. The separate communications session is established on the basis of the received call party details e.g. TDN A and TDN B. Once the separate communications session is established voice call data is transmitted via the telephone call and other data can be transmitted and received via the separate communications session.

Some embodiments comprise receiving client server connection request from and establishing a client server connection with one or both of MS A and MS B.

Server updates the records for MS A and MS B in data store in step to indicate that a call is in progress between MS A and MS B and that a separate communications session between MS A and MS B has been established.

Once the separate communications session between MS A and MS B has been established MS A retrieves pre configured user data from its memory and transmits this to server in step . Server performs a lookup in data store using TDN A for MS A in step and identifies that a communications session has been established between MS A and MS B.

Server retrieves TDN B for MS B in step and conducts a check to determine whether MS B already has pre configured user data for the user of MS A stored locally. Conducting the check involves server transmitting a query to MS B in step . Upon receiving the query of MS B checks its memory to see whether it has pre configured user data for the user of MS A stored locally in step and transmits a response to server in step . In this case the response of step indicates that at least a part of the pre configured user data for the user of MS A is not stored locally to MS B so server transmits pre configured user data for MS A to MS B in step

In step MS B updates its local memory according to the pre configured user data received in step . Server updates data store in step to indicate which pre configured user data was received by MS B via the separate communications session in step

MS B retrieves pre configured user data from its memory and transmits this to server in step . Server performs a lookup in data store using TDN B for MS B in step identifies that a communications session has been established between MS A and MS B and retrieves TDN A for MS A in step

A check is conducted to determine whether MS A already has pre configured user data for the user of MS B stored locally. Conducting the check involves server transmitting a query to MS A in step . Upon receiving the query of MS A checks its memory to see whether it has pre configured user data for the user of MS B stored locally in step and transmits a response to server in step . In this case the response of step indicates that at least a part of the pre configured user data for the user of MS B is not stored locally to MS A so server transmits the pre configured user data for MS B to MS A in step

In step MS A updates its local memory according to the pre configured user data received in step . Server updates data store in step to indicate which pre configured user data was received by MS A via the separate communications session in step

In alternative embodiments of the invention server stores pre configured user data for a plurality of user devices in data store . Data store will include data indicating which user devices have received pre configured user data in relation to which other user devices and also which data fields and which versions of pre configured user data have been transmitted from and received by which user devices. In such embodiments of the invention checks can be carried out at server with reference to data store without the need to query MS B in step or MS A in step

In the description of the embodiments of A and B above enabling of the receipt of pre configured user data by MS B is carried out if the check indicates that MS B does not have at least a part of the pre configured user data for the user of MS A stored locally. In other embodiments of the invention the configured user data comprises a plurality of data fields and the check involves determining whether current versions of the data fields in data stored locally to MS B require updating to more recent versions. In such embodiments server will include indications of the values and or versions of data fields of the pre configured user data received in step in the query of step

MS B compares the received data field values and or versions received in step with data field values and or versions stored locally to MS B in step . The response of step includes an indication as to which data fields for MS A user data are missing and which require updating. Server transmits the appropriate data field values and or versions of pre configured user data for MS A in step . Such embodiments can help avoid receipt of the entire pre configured user data received in step to MS B in step e.g. only pre configured user data required to update MS B can be received and not pre configured user data which MS B already has. This could for example be particularly useful if the pre configured user data includes a file having a relatively large file size such as an image where repeated transmission reception of such could have an impact on limited bandwidth resources to from MS B in PLMN B.

In these embodiments of the invention the user of MS A has specified prior to establishment of telephone calls conducted by the user pre configured user data for receipt by other user devices during subsequent telephone calls conducted using MS A. The user s pre configured user data has previously been stored in data store associated with server for example transmitted to server from MS A or entered directly to server via a web interface.

Similarly the user of MS B has specified prior to establishment of telephone calls conducted by the user pre configured user data for receipt by other user devices during subsequent telephone calls conducted using MS B. The user s pre configured user data has previously been stored in data store associated with server for example transmitted to server from MS B or entered directly to server via a web interface.

Pre configured user data in data store may be updated via a synchronisation process between MS A and server . Synchronisation may involve periodic update requests being sent from server to MS A with MS A responding with any updates to the pre configured user data. Alternatively MS A may send a pre configured user data update to server whenever the user of MS A makes an update to pre configured user data within the memory of MS A.

These embodiments of the invention involve enabling the receipt of pre configured user data configured by the user of MS A by MS B via a separate communications session and also enabling the receipt of pre configured user data configured by the user of MS B by MS A via a separate communications session during a call conducted between MS A and MS B.

Similarly to described above a voice call is being conducted between MS A and MS B and steps and occur similarly to steps and as described above.

Server identifies that the notification of step from MS A and the notification of step from MS B have call party details TDN A and TDN B in common and establishes a communications session separate from the telephone call between MS A and MS B for the communication of data between MS A and MS B. The separate communications session is established on the basis of the received call party details e.g. TDN A and TDN B. Once the separate communications session is established voice call data is transmitted via the telephone call and other data can be transmitted and received via the separate communications session.

Once the separate communications session between MS A and MS B has been established server accesses data store to update the records for MS A and MS B in step to indicate that a call is in progress between MS A and MS B and that a separate communications session between MS A and MS B has been established.

Step also involves server performing a lookup in data store to retrieve pre configured user data specified for reception by other user devices including MS B in relation to MS A and pre configured user data specified for reception by other user devices including MS A in relation to MS B in step

When server receives pre configured user data specified for transmittal in relation to MS B in step it transmits the pre configured user data to MS A in step . In step MS A updates its local memory according to the pre configured user data received in step

When server receives pre configured user data specified for receipt by other user devices in relation to MS A in step it transmits the pre configured user data to MS B in step . In step MS B updates its local memory according to the pre configured user data received in step

Server updates data store in step to indicate which pre configured user data was received by MS A in step and which pre configured user data was received by MS B in step

The embodiments of may include conducting checks for MS A and MS B respectively either at server or by querying MS A and MS B in a similar manner as described above for .

In these embodiments of the invention the user of MS A has specified prior to establishment of telephone calls conducted by the user pre configured user data for reception by other user devices during subsequent telephone calls conducted using MS A. The user s pre configured user data has previously been stored at network location for example in a database accessible via a web server. The user s pre configured user data may have been transmitted to network location from MS A or entered directly to network location via a web interface using a personal computer or similar computing device.

These embodiments of the invention involve enabling the receipt of pre configured user data configured by the user of MS A by MS B via a separate communications session during a call conducted using MS A and MS B.

Similarly to described above a voice call is being conducted between MS A and MS B and steps and occur similarly to steps and as described above.

Once the separate communications session between MS A and MS B has been established MS A retrieves an identifier from its memory which identifies pre configured user data for reception by other user devices during telephone calls conducted by the user of MS A. The pre configured user data identifier is transmitted to server in step

Server performs a lookup in data store using TDN A for MS A in step identifies that a communications session has been established between MS A and MS B and retrieves TDN B for MS B in step

In step server locates and accesses pre configured user data for the user of MS A at network location on the basis of the identifier received from MS A in step . The pre configured user data is transmitted from network location to server in step

Server uses the retrieved TDN B for MS B to conduct a check to determine whether MS B already has pre configured user data for the user of MS A stored locally. Conducting the check involves server transmitting a query to MS B in step . Upon receiving the query of MS B checks its memory to see whether it has pre configured user data for the user of MS A stored locally in step and transmits a response to server in step . In this case the response of step indicates that at least a part of the pre configured user data for the user of MS A is not stored in memory in MS B so server transmits pre configured user data for MS A to MS B in step

In step MS B updates its local memory according to the pre configured user data received in step . Server updates data store in step to indicate which pre configured user data was transmitted to and received by MS B in step

The identifier could be a network address from which the pre configured user data can be downloaded for example a Uniform Resource Locator URL . As an example the pre configured user data identifier could be a URL for an online user account such as a social network account e.g. a user identity associated with a Facebook profile the pre configured user data could correspond to a public profile of a user s online account. A user can pre configure within their profile which user data is to be received by other user devices during telephone calls and the URL identifier can be set to point to such. Server can use the URL identifier to contact the appropriate network address in step and download the appropriate pre configured user data in step

In the embodiments of the invention described above in relation to the identifier transmitted to server in step is used by server in step to retrieve pre configured user data from network location in step . In alternative embodiments of the invention the identifier could comprise an identifier for use in retrieving the pre configured user data from data store in such embodiments the user of MS A will have previously stored pre configured user data in data store either transmitted from MS A or entered directly via a web interface using a personal computer or similar computing device.

In alternative embodiments of the invention the notification of step and the identifier transmittal of step are combined into a single step. Similarly the data store updating of step and data store lookup of step could be combined into a single step.

In these embodiments of the invention the user of MS A has specified prior to establishment of telephone calls conducted by the user pre configured user data for reception by other user devices during subsequent telephone calls conducted using MS A. The user s pre configured user data has previously been stored at network location identified by a pre configured user data identifier for example a network address in packet network .

These embodiments of the invention involve enabling the reception of pre configured user data configured by the user of MS A by MS B via a separate communications session during a call conducted using MS A and MS B.

Similarly to described above a voice call is being conducted between MS A and MS B and steps to occur similarly to steps to as described above.

Once the separate communications session between MS A and MS B has been established MS A retrieves an identifier from its memory which identifies pre configured user data for reception by other user devices during telephone calls conducted by the user of MS A. The pre configured user data identifier is transmitted to server in step

Server performs a lookup in data store using TDN A for MS A in step identifies that a communications session has been established between MS A and MS B and retrieves TDN B for MS B in step

Server transmits the pre configured user data identifier received in step to MS B in step . MS B locates and accesses pre configured user data for the user of MS A at network location on the basis of the identifier received from MS A in step . The pre configured user data is transmitted from network location to server in step . In step MS B updates its local memory according to the pre configured user data received in step

In other embodiments of the invention the pre configured user data identifier is stored in data store and can be retrieved from data store by server for example in combination with steps and without requiring transmittal of the pre configured user data identifier from MS A to server in step

Download of the pre configured user data by MS B may include conducting a check in a similar manner as described above for .

In alternative embodiments of the invention the notification of step and the identifier transmittal of step are combined into a single step. Similarly the data store updating of step and data store lookup of step could be combined into a single step.

Embodiments of the invention involve server instructing a user device to display one or more parts of pre configured user data received during a call. Instructing a user device to display pre configured user data could be combined with transmittal of the pre configured user data or an identifier for the pre configured user data to a user device or could involve a distinct instruction step. Such functionality could be particularly useful if for example the pre configured user data includes a name for a user associated with the pre configured user data displaying the name or user identity associated with a user of one user device on another user device involved in a call provides a convenient way to identity a user involved in a telephone call.

The pre configured user data could comprise a variety of different types of user data such as one or more of a user s name a social network user identity an email address a date an image file and a postal or street address.

Transmittal of pre configured user data in the form of a name or user identity could be useful in identifying a user conducting a call to one or more other parties to the call. If the image is a photo of a calling party then a similar effect can be achieved.

Transmittal of pre configured user data in the form of a postal or street address or email address could be useful in identifying how to contact a user by a different communication means after the telephone call is terminated.

Transmittal of pre configured user data in the form of a date could be useful in highlighting a date of interest to users such as the date of a user s birthday or other such event date.

Embodiments of the invention described above involve enabling receipt of pre configured user data associated with the user of a user device to one or more other devices during a call between the user devices. In other embodiments a user specifies different pre configured user data for receipt by one or more pre defined user devices during calls with those user devices. When a user configures their user data they can pre define one or more subsets of their pre configured user data for receipt during calls with one or more pre defined user devices of their choosing.

Configuration could for example involve associating one or more user devices into different groups such as a family group a work group etc. Different pre defined user data can then be received during a call with a user device in the family group than pre defined user data received during a call with a user device in the work group.

Embodiments of the invention involve identifying that a call is being conducted with a pre defined user device on the basis of received call party details for the call for example a telephone dialling number associated with a user device pre defined by a user. When a call with such a pre defined user device is identified the subset of pre configured user data can be received the pre defined user device instead of or in addition to the pre defined user data received by other non pre defined user devices.

Embodiments of the invention involve a telephony user device capable of establishing a communications session for communication of data with respect to at least one other user device in a data communications network the telephony user device comprising a data store and being capable of 

transmitting call party details of a telephone call the telephone call involving at least the telephony user device the telephony user device being a first telephony user device and a second telephony user device the call party details including a first identity associated with the first telephony user device and a second identity associated with the second telephony user device at least one of the first and second identities comprising a telephone dialling number 

establishing on the basis of the first and second identities received in the call party details a separate communications session separate from the telephone call for the communication of data to and or from the at least one other user device 

presenting the user of the telephony user device with an option to update the data store with at least a part of the received data.

In such embodiments the received data need not be user data and need not have been have been specified by a user of a user device prior to the establishment of the telephone call as data for receipt by other user devices during telephone calls conducted by the user.

In such embodiments of the invention upon receipt of data at a user device the user device may carry out a search of a local data store or internal memory to see if data corresponding to the received data or part thereof is already stored with the data store. If the search of a user device s data store does not find data corresponding to at least a part of the received data in its store then the data store can be updated with one or more parts of the received data accordingly.

When the data is received at a user device one or more parts of the received data may be displayed by the user device during the call for example the name of the other party to the call could be displayed during the call. The display may occur in response to receipt of a display instruction from server and may include giving the user the option to allow display of the data or not.

Displaying the received data may involve overlaying the display of the received data over other data displayed during the call. The received data may for example be overlaid over other data already displayed in association with an in call screen application or call dialling application running on the user device and operable via a touch screen interface such an application will typically involve display of a number of touch sensitive icons for inputting telephone dialling number digits and facilitating operations such as dial number end call hold call etc. The other data may also include a telephone number or other identifier associated with a calling or called party for the call. Overlaying the received data may involve displaying the received data in a translucent manner such that other data displayed during the call can also be seen through the displayed received data. Alternatively overlaying the received data may involve displaying the received data in a non translucent manner to replace data already displayed during the call for example the display of the telephone dialling number of the other party to the call could be replaced by the name of the other party to the call.

When the data is received at a user device the user device may present the user with an option to update the user device data store with the received data for example by appropriate output on a display of the user device. The user can authorise updating of the data store by user input via a telephony device user input interface.

The option to update the data store of a user device with received data may be presented when the users are still conducting a telephone call. Alternatively or in addition the update option is presented to a user after termination of the call.

Termination of the call may be detected by application software on the telephony user device which is capable of detecting termination of calls made by the telephony user device.

Alternatively the telephony user device may receive notification of termination of the call from the data communications network for example from a network entity such as server network element or SCP .

The telephony user device may temporarily update its data store with all or a part of the data received via the separate communication session for the duration of the call. The user can then be presented with the option to confirm the temporary in call updating of the data store after termination of the call.

In alternative embodiments of the invention the data store of the telephony user device is updated in response to receipt of data via the separate communications session without the user being presented with the option to accept the update s or not.

Embodiments of the invention allow the user of the telephony user device to choose if and to what extent the data store of their telephony user device is updated with data received via the separate communication session. Such embodiments may for example involve allowing the user to configure settings such that any updates for data received from a particular contact in the telephony user device address book are rejected or data received from a particular contact are only used to update the data store a single time or data received from contacts contained in the telephony user device address book are used to update the date store without requiring confirmation from the user. Another embodiment might involve allowing a user to create a black list of a number of contacts from which received data are not to be used to update the data store.

Various measures for example a method server apparatus telecommunications network computer software and a computer program product comprising a non transitory computer readable storage medium for establishing a communications session for communication of data with respect to at least two user devices in a data communications network are provided. Call party details of a telephone call are received. The telephone call involves at least a first telephony user device and a second telephony user device. The call party details include a first identity associated with the first telephony user device and a second identity associated with the second telephony user device. A client server connection request is received from and a client server connection is established with at least one of the at least two user devices. A separate communications session is established on the basis of the first and second identities received in the call party details for the communication of data to and or from the at least two user devices. The separate communications session is separate from the telephone call. The receipt of pre configured user data is enabled by the at least one of the at least two user devices via the client server connection. The pre configured user data is specified by a user of one other of the at least two user devices prior to the establishment of the telephone call as data for receipt by other user devices during telephone calls conducted by the user.

In some embodiments at least one of the first and second identities comprises a telephone dialling number.

In some embodiments the enabling is carried out in response to establishment of the separate communications session.

In some embodiments the pre configured user data is received and the received pre configured user data is transmitted to at least one of the at least two user devices.

In some embodiments the pre configured user data is received prior to the call and stored in a data store. In response to establishment of the separate communications session the pre configured user data is retrieved from the store and the pre configured user data is transmitted for receipt.

In some embodiments the pre configured user data is received from the one other of the at least two user devices after establishment of the separate communications session.

In some embodiments the pre configured user data is configured by linking to a record in a personal information manager PIM on the one other of the at least two user devices.

In some embodiments an identifier identifying the pre configured user data is received from the one other of the at least two user devices the pre configured user data is retrieved on the basis of the received identifier and the retrieved pre configured user data is transmitted to at least one of the at least two user devices.

In some embodiments an identifier identifying the pre configured user data is received from the one other of the at least two user devices and the received identifier is transmitted to at least one of the at least two user devices.

In some embodiments the identifier comprises a network address from which the pre configured user data can be downloaded.

In some embodiments the at least one of the at least two user devices is instructed to display one or more parts of the pre configured user data during the call.

In some embodiments the pre configured user data comprises data other than the first and second identities.

In some embodiments a check is conducted to determine whether the at least one of the at least two user devices already has pre configured user data for the user stored locally wherein the enabling is carried out if the check indicates that the at least one of the at least two user devices does not have at least a part of the pre configured user data for the user stored locally.

In some embodiments the conducting a check comprises transmitting a query to the at least one of the at least two user devices and receiving at least one response indicating whether the at least one of the at least two user devices has pre configured user data for the user stored locally.

In some embodiments pre configured user data for a plurality of user devices is stored in a data store accessible by a server. The check is conducted at the server.

In some embodiments the pre configured user data comprises a plurality of data fields and the check comprises determining whether current versions of the data fields in data stored locally to the at least one of the at least two user devices require updating to more recent versions.

In some embodiments the pre configured user data comprises one or more of a user identity a user s name a social network user identity an email address a date an image file and a postal or street address.

In some embodiments the receipt of a subset of the pre configured user data by one or more pre defined user devices via the separate communications session is enabled. The subset of the pre configured user data is specified by the user of the one other of the at least two user devices as data for receipt by the one or more pre defined user devices during telephone calls conducted by the user.

In some embodiments the call is identified as being conducted with the one or more pre defined user devices on the basis of the received call party details wherein the enabling of receipt of the subset of pre configured user data is carried out in response to the call identification.

In some embodiments the pre configured user data is transmitted via the client server connection established with the one of the at least two user devices.

In some embodiments establishing the session comprises receiving a further client server connection request from and establishing a client server connection with the another of the at least two user devices.

In some embodiments the client server connection request and or the further client server connection request is transmitted in response to the telephone call being established.

In some embodiments the client server connection request and or the further client server connection request is transmitted in response to a notification received after the telephone call is established.

Various measures for example a telephony user device computer software and a computer program product comprising a non transitory computer readable storage medium for establishing a communications session for communication of data with respect to at least one other user device in a data communications network are provided. Call party details of a telephone call are transmitted. The telephone call involves at least the telephony user device the telephony user device being a first telephony user device and a second telephony user device. The call party details include a first identity associated with the first telephony user device and a second identity associated with the second telephony user device. A client server connection request is transmitted to and a client server connection is established with a server. A separate communications session is established on the basis of the first and second identities received in the call party details for the communication of data to and or from the at least one other user device. The separate communications session is separate from the telephone call. Pre configured user data is transmitted to the at least one other user device via the client server connection. The pre configured user data is specified by a user of the telephony user device prior to the establishment of the telephone call as data for transmittal to other user devices during telephone calls conducted by the user.

In some embodiments at least one of the first and second identities comprises a telephone dialling number.

Various measures for example a telephony user device computer software and a computer program product comprising a non transitory computer readable storage medium for establishing a communications session for communication of data with respect to at least one other user device in a data communications network is provided. Call party details of a telephone call are transmitted. The telephone call involves at least the telephony user device the telephony user device being a first telephony user device and a second telephony user device. The call party details include a first identity associated with the first telephony user device and a second identity associated with the second telephony user device. At least one of the first and second identities comprises a telephone dialling number. A client server connection request is transmitted to and a client server connection is established with a server. A separate communications session is established on the basis of the first and second identities received in the call party details for the communication of data to and or from the at least one other user device. The separate communications session is separate from the telephone call. Data is received from the at least one other user device via the client server connection. The user of the telephony user device is presented with an option to update the data store with at least a part of the received data.

In some embodiments the processor is further configured to receive notification of termination of the call from the data communications network.

In some embodiments the processor is further configured to upon receipt of the data search the data store for data corresponding to the received data wherein presenting the option occurs in response to not finding at least a part of the received data in the store.

In some embodiments the processor is further configured to update the data store with the at least part of the received data in response to user input on the telephony user device.

In some embodiments the processor is further configured to display one or more parts of the received data during the call.

In some embodiments the processor is further configured to overlay the display of the one or more parts of the received data over other data displayed during the call.

In some embodiments the processor is further configured to temporarily update the data store with the at least part of the received data for the duration of the call.

In some embodiments the processor is further configured to present the user of the telephony user device with an option to confirm the temporary updating of the data store after termination of the call.

In some embodiments the received data comprises pre configured user data specified by the user of the at least one other user device as data for receipt by other user devices during telephone calls conducted by the user of the least one other user device.

The above embodiments are to be understood as illustrative examples of the invention. Further embodiments of the invention are envisaged.

The above described embodiments primarily relate to telephony devices having associated identities in the form of telephone dialling numbers. In other embodiments of the invention one or more or all of the identities could be non telephone dialling numbers for example usernames email addresses etc. Where non telephone dialling number identities are employed mappings between non telephone dialling number identities and telephone dialling number identities may be stored in data store and used by server for converting from non telephone dialling number identities to telephone dialling numbers after receipt of the call party details

The personal computer PC A described above could alternatively be another device or combination of devices with corresponding data processing display and data input capabilities for example a television a smart television a general purpose desktop computer terminal a general purpose laptop computer terminal a general purpose tablet computer terminal an in car computing and communications system a satellite navigation system games console or any combination thereof.

In embodiments of the invention described above telephone calls to from mobile stations and POTS phones are detected either by application software running on the mobile stations or by a telephony apparatus configured accordingly. In alternative embodiments of the invention during a voice call a party to the call uses a computing terminal to enter in call party details for example the calling and called party telephone dialling numbers for the call via a web server interface. The web server interface passes the call party details to server which can then establish a communications session separate to the voice call on the basis of the calling and called party telephone dialling numbers received from the web server interface.

The logical coupling between user devices for a user may be temporary or more permanent. If for example a user has a POTS phone and a PC as their user devices in their home then these devices will tend to be used by the user on a fairly permanent basis so the logical coupling would tend to be more permanent. If for example a user has a mobile phone and a satellite navigation system in their car then the logical coupling between the two devices may only be valid when the user is in or near their car so the logical coupling would only be maintained temporarily when the two devices are within close enough proximity of each other.

The logical coupling between a user s devices can be activated or otherwise triggered by a variety of different processes. One example could involve communication between a smartphone and a satellite navigation system via a short wave radio interface such as a Bluetooth interface in order to couple the two devices together locally along with subsequent registration of details of such with server . Another example could be registration of device details via a website. A further example might involve registration by a service engineer when installing a telephone and set top box combination. Alternatively registration could be carried out over the telephone verbally to an administrative operator or via an Interactive Voice Response IVR system.

The above embodiments of the invention describe telephone calls and establishment of communications sessions for user devices of two parties. All embodiments of the invention can be applied to user devices of multiple parties numbering more than two. When the multiple parties are conducting a multi leg teleconference a communications session can be created between all of their user devices allowing communication of data not just between two user devices but between many different combinations of user devices i.e. multi branch data communication.

The connections between server and the user devices are described above as being HTTP or HTTPS connections. In alternative embodiments of the invention the connections could be peer to peer connections such that data is communicated between the user devices through a number of peer to peer nodes. Creating the peer to peer connections may involve use of processes for traversing firewalls for example using protocols such as the Simple Traversal of User Datagram Protocol UDP Through Network Address Translators NATs STUN protocol.

Further alternatively the connections could initially be created as HTTP or HTTPS connections between server and the user devices but then could be migrated to peer to peer connections according to network topography and or current network load.

Embodiments of the invention described above involve communication of different types of data during a communication session for example software component identifiers software applications feature identifiers authorisation requests authorisation indications geographical location data etc. Any of these different types of data may be communicated between the various combinations of devices in the above described embodiments including mobile station to mobile station and mobile station to PC both with or without use of telephony apparatus for call detection.

In the above described embodiments both call parties transmit either from the telephony device or an associated device call party identifiers for each party to the server in the process of setting up the separate data communications session. These call party identifiers are in the embodiments described both telephony dialling numbers TDNs . In alternative embodiments of the invention one party or both parties may be identified by another form of call party identifier using for example one or more lookup mechanisms which map a telephony dialling number to a different unique identifier and or vice versa examples of such alternatives are described in further detail below. However such lookup mechanisms may increase latency and may introduce unexpected errors e.g. if a lookup database such as an address book is not kept up to date. Hence whilst it is not indeed necessary for either party to transmit a telephony dialling number of either party since either party may be identified by other mechanisms it is preferred that at least one of the devices includes the telephony dialling number of the other party.

Indeed whilst it is again not necessary it is preferred that both parties transmit the telephony dialling number of the other party if available to the server during the session setup. Furthermore in order at least to reduce latency at the server and or to reduce the need to maintain a separate store of identities and or to reduce the need to implement a registration mechanism it is preferred that both parties transmit both their own telephony dialling number and the telephony dialling number of the other party if available to the server during the session setup. If a call party is identifiable using an additional identifier such as an extension number or a conference call ID the additional identifier is preferably transmitted in association with both of the telephony dialling numbers if available by one or each party to the call.

As mentioned above in alternative embodiments of the invention one or each of the call parties may transmit either from the telephony device or an associated device a unique identifier in the form other than that of a telephony dialling number which is nonetheless recognisable by the server . A user device which interacts with the server may thus transmit the unique identifier to identify one party or both parties as a party to the call instead of a telephony dialling number. For example the server may have access to a data store which includes a set of unique identifiers for all subscribers registered to receive the service provided by the server along with a corresponding telephony dialling number for a telephony device associated with each respective unique identifier. Such unique identifiers may be allocated by the server during an initial registration procedure and notified to and stored by an application on the user device which interacts with the server during the registration procedure. Other globally unique identifiers such as email addresses Facebook IDs etc. may be used alternatively or in addition to such allocated unique identifiers.

In embodiments of the invention at least one of the two call parties may use a Voice over Internet Protocol VoIP enabled device or other device employing the session Initiation Protocol SIP . One or each party may be identified in the call setup procedures by means of a unique SIP user identifier which may include a telephone dialling number as a user identifier or a user identifier other than a telephony dialling number for example a SIP identifier in the form of username hostname. Thus a SIP user identifier can be transmitted to the server as a call party identifier identifying at least one or each participant in the call.

In embodiments of the invention a call party identifier may take the form of an Internet Protocol IP address which may be either a static or dynamically allocated IP address. This may for example be the IP address which a user device transmits to the server in a client server connection setup request for example an HTTP setup request when establishing a leg of the communications session. This may uniquely identify the call party associated with the device making the request. If for example a given party sends the telephony dialling number of only the other party to the server in the session setup procedure then that given party can nevertheless be identified as a party to the call using the IP address of that given party s device used in establishing the session leg. The supplied IP address may then be used to send data to that given party s device throughout the ensuing communications session even if the IP address is only temporarily allocated to the user device as a dynamic IP address. Hence a static or dynamic IP address may be used in some embodiments of the invention to identify a call party and may be one of the call party identifiers which forms part of the call party details transmitted to the server e.g. in a connection setup request during session establishment.

In embodiments of the invention a call party identifier may take the form of a session identifier or other unique identifier generated by the server and received from the server by a user device in a push notification message. Such a push notification message may be sent from the server in response to the server receiving call party details from the other party to the call in a first communication session leg. The push notification message is configured on receipt to trigger the user device to set up a second communication session leg with the server . The user device may be configured to include the identifier received in the push notification as a call party identifier in a client server connection setup request for example an HTTP setup request when establishing the communications session leg in response to the push notification message. This may uniquely identify the call party associated with the device making the request since such identifier may be mapped to the telephony dialling number or other call party identifier by the server . Hence an identifier received in a push notification message may be used in some embodiments of the invention to identify a call party and may be one of the call party identifiers which forms part of the call party details transmitted to the server e.g. in a connection setup request during session establishment.

A unique identifier in any of the various forms described above in a form other than that of a telephony dialling number may be used to identify a given party to the call in call party details transmitted by a user device associated with that given party. A unique identifier in any of the various forms described in a form other than that of a telephony dialling number may in addition or in the alternative be used to identify another party to the call in call party details transmitted by that given party. The server may supply the unique identifiers of other parties using e.g. a synchronization process for populating an address book locally stored on the user device with such identifiers. Alternatively such unique identifiers of other parties may already be stored by or manually added by a user of the device in the local address book. Further alternatively the unique identifiers may be stored in a global address book stored on a remote device. At least one of the two parties may have a user device which is configured to look up from a local data store e.g. a local address book or a remote data store e.g. a global address book a correspondence between the other party s telephone dialling number or other received unique identifier and a different unique identifier. The different unique identifier may then be used instead to identify the other party to the call in the call party details transmitted by at least one side of the call to the server .

In the above various forms of alternative call party identifiers are described. Whatever form the supplied unique identifier takes the server may have a corresponding database and lookup mechanism to map a supplied unique identifier to a different call party identifier such as a telephony dialling number whereby to match both session legs together as relating to a particular current telephone call using the information supplied in each respective one of the session legs. The server can then bridge the two session legs together or otherwise associate the two session legs to create a separate communications session between the participants in a currently ongoing call.

In the above described embodiments whilst a different form of call party identifier may be used in some cases in a generally accessible telephony system at least one of the two parties may have no access to identifying details other than the telephony dialling number of the other call party when the call is established. Hence it is preferable that the system is configured such that at least one of the two parties may transmit the call party identifier of the other party to the server in the form of a telephony dialling number and that the server is able to process one or more call party details in such a form in order to establish the separate communications session.

In alternative embodiments of the invention rather than both call parties transmitting both calling party and called party identifiers to identify the parties to a call at least one of the parties may transmit only one of the two call party identifiers to the server . This may be done according to a predetermined convention e.g. a convention which determines that the calling party should always transmit both identifiers but the called party need only transmit one identifier or vice versa . Again the server is nevertheless able to match both session legs together as relating to a particular current telephone call using the information supplied in both of the session legs. In this case it is sufficient that at least one common call participant namely that participant which is determined by convention to be identified by each party to the call has been identified in each session leg.

In some circumstances the telephony dialling number or other call party identifier of the other party may not be received at all during the call setup procedures. For example the other party may use a number withholding service. Hence an identifier for the other party may not be available to the user device. In this case the user device may be able during the setup of the separate communications session to identify only its associated call party and not the other call party to the server as a party to the call. However providing both sides of the call do not use a number withholding service the other party s device may be able identify both parties to the call and preferably transmits call party details identifying both call parties to the server during session establishment. Again the server is nevertheless able to match both session legs together as relating to a particular current telephone call using the information supplied in both of the session legs. Again in this case it is sufficient that at least one common call participant namely the participant not using a number withholding service has been identified in both session legs.

In the above described embodiments the mobile stations MS A MS B communicate via a PLMN. Such a PLMN may be any of a variety of different cellular communications network types including a 2G network such as a Global System for Mobile communications GSM network a 3G network such as a Universal Mobile Telecommunications System UMTS network or a 4G network such as a Long Term Evolution LTE or LTE Advanced network. Whilst the call setup and call data flow is preferably conducted via the PLMN the communications relating to the separate data communications session e.g. communications with the server may be conducted via a different radio access network RAN such as a wireless local area network WLAN based on the IEEE 802.11 standards.

In the above described embodiments the server is described as a single computing device located in a single network location. However it should be understood that the server may consist of a distributed set of computing devices or applications either co located in a single network location or dispersed in different network locations.

It is to be understood that any feature described in relation to any one embodiment may be used alone or in combination with other features described and may also be used in combination with one or more features of any other of the embodiments or any combination of any other of the embodiments. Furthermore equivalents and modifications not described above may also be employed without departing from the scope of the invention which is defined in the accompanying claims.

