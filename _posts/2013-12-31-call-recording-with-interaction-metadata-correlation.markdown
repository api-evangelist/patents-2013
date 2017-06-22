---

title: Call recording with interaction metadata correlation
abstract: Methods and systems are described for call recording, e.g. in a VoIP system. At least one endpoint may be configured to terminate a call. A recording system may be configured to record call content data from multiple endpointsA the controller may receive, from a call exchange, interaction metadata relating to calls starting and terminating at the endpoint; receive notifications relating to call content from the recording system; and match the interaction metadata to the notifications.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09197744&OS=09197744&RS=09197744
owner: NICE-SYSTEMS LTD.
number: 09197744
owner_city: Ra'anana
owner_country: IL
publication_date: 20131231
---
The present invention relates generally to the recording of information such as audio voice video and data information transmitted over a network. In particular embodiments of the invention relate to Voice over Internet Protocol VoIP recording.

Current developments of the Voice over Internet Protocol VoIP technology leverage a broad array of contact center applications and flexible call handling capabilities. In addition contact channels have expanded from voice to include other applications such as email web fax and the like. Computer telephony integration CTI allows integration and coordination of many customer contact channels e.g. voice email web and fax with computer systems.

It is typical for all CTI information to be provided by a central CTI server and certain CTI standards require knowledge of the entire call flow.

A call as used herein may be any communication for example between a customer and one or more agents over a communication network. The routing of a call may be controlled by a call exchange such as such as a Private Branch Exchange PBX may also be referred to as an interaction . A call may be for example a voice call e.g. VoIP but for the purpose of this description a call may also be a text or video call for example. It should be noted also that a call may be a one way interaction where there is a one way conversation or flow of RTP packets from a user endpoint to the recorder or a call may be a two way bi directional or multi path interaction between two or more parties where there is a multi path conversation or flow of RTP packets from each of the multiple user endpoints to the recorder.

 Data relating to a call as used herein may include content data and metadata . The content data may include for example the data that is exchanged between parties to a call such as but not limited to audio video and text. Metadata may be for example information other than content data which relates to the call and or content such as but not limited to start time stop time identities of parties route of call file name and filepath of location of content data IP addresses and more as will be described by reference to specific examples.

Embodiments of the invention provide a method of recording data relating to calls in a communication system the communication system including at least one endpoint configured to create or and terminate a call a recording system configured to record call content data from multiple endpoints and a controller the method including at the controller for at least one of said multiple endpoints receiving from a call exchange interaction metadata relating to calls starting and terminating at the endpoint receiving notifications relating to call content from the recording system and

The description that follows provides various details of exemplary embodiments. However this description is not intended to limit the scope of the claims but instead to explain various principles of the invention and the manner of practicing it.

Aspects of the invention are applicable to a communication system include at least one endpoint configured to initiate or terminate a call or both and a recording system configured to record call content data from multiple endpoints. Recording of content data may be initiated automatically at the recording system upon receipt of content data from the endpoint. This is particularly useful when the recording system is configured for total recording of content data sent to and from the endpoint. The recording system need not wait for a signal from a controller to initiate recording. Instead the receipt of call content e.g. a data packet with call content triggers the recording of call content by the recording system.

Content data relating to different calls to and from the endpoint may be separately recorded. One way of achieving this is through use of a file structure. However other methods of separating content data will be familiar to those skilled in the art. Content data relating to a call may be divided into sessions . There may be more than one session relating to a call. For example multiple sessions relating to a call may be separated by periods of silence. Thus the recording system may initiate a new session automatically upon a change of identification data such as a synchronization source SSRC identifier in the received call content data. Additionally or alternatively a new session may be initiated when content data is received after a predetermined period of not receiving call content data a silent period of minimum length e.g. by receiving no data packets or packets with no content. The recording system may hold a separate file relating to each session.

A call may have separate transmit and receive streams. According to some embodiments of the invention separate sessions may be recorded for the respective streams.

As noted above some embodiments may record content data relating to different calls in a file structure. Metadata relating to calls for which content is recorded may also be stored at the recording system. The metadata may be stored in a database structure. At least some of the metadata may be supplied to the recording system from a controller which in turn may have received it from a separate possibly third party source or device over a network e.g. from a call exchange such as a private branch exchange PBX which controls the establishment of calls between endpoints. This metadata may be in the form of CTI messages.

On the controller side the controller may receive e.g. from a call exchange metadata relating to calls establishing and terminating at the endpoint and notifications relating to call content from the recording system. The arrival of such data from two different sources may not be synchronized. The controller may then match the metadata to the notifications. The notifications may be sent by the recording system at the commencement and end of recording for a particular call. Since the metadata and the notifications may be received from different sources and since the recording may be executed autonomously without reliance on the metadata the content of the metadata and the notifications may not be helpful in matching the metadata to the notifications. Therefore according to one embodiment the controller may match the metadata to the notifications based on one or both of the absolute time of receipt of the notifications and or metadata and time intervals therebetween.

In the following discussion only one endpoint is discussed but it will be appreciated that both the controller and the recorder may in practice perform the same functions for multiple endpoints. It should also be noted that one controller may be associated with multiple recording systems.

The matching of interaction metadata to notifications may be initiated at a predetermined point in the flow of information to the controller or in response to a predetermined notification.

The interaction metadata received from the call exchange may include call start and or end notifications and the matching of interaction metadata to notifications may be initiated by the controller in response to receipt of a call start and or end notification. In the preferred embodiment to be described below the matching is done in response to receipt of an end notification.

It should be noted that the notifications sent to the controller from the recording system may also include metadata. They may include notifications on start and end of recording call content.

Both the PBX and the recording system may communicate with the recorder using Computer Telephony Integration CTI messages.

The controller preferably sends to the recording system metadata relating to call content data recorded at the recording system whereby metadata at the controller is congruous with metadata at the recording system. For example the controller may send to the recorder metadata that matches or corresponds to metadata held at the controller. This assists in the handling of requests for data sent from the controller to the recorder or vice versa.

The content of a call may be divided for example by a period of silence or a change in identification data e.g. RTP packet identification data. Therefore there may be more than one recording session associated with a call. On the controller side a recording may be created for each call and preferably for each session. The recording may comprise interaction and recording metadata relating to each session and no content. The interaction metadata may be reported to the controller by the call exchange without any content data the content data being routed directly to the recording system by the endpoint. Thus the content data is not routed to the controller at all.

Thus the creation of the recordings may be controlled by the controller and the creation of sessions may be controlled autonomously by the recorder at the recording system.

Each recording may comprises additional metadata related to each session which is not stored at the recording system.

Methods and systems according to embodiments of the invention are particularly suited to so called total recording in which all communications to and from an end point are recorded. Therefore the method may comprise configuring the recording system for recording of all content data exchanged in calls initiated at and or terminating at the endpoint i.e. content data sent to the endpoint and content data sent from the endpoint. This may require configuration of the endpoint under the control of the controller to copy all packets sent and received at the endpoint to the recording system.

Embodiments of the invention may provide a call recording system comprising a recording system configured to record call content data relating to calls to and from multiple endpoints and a controller configured to record metadata relating to the calls wherein the recording system is configured for total recording of content data sent to and from the endpoint and initiating recording automatically on receipt of content data from the endpoint.

The controller of a system according to embodiments of the invention may be configured to receive from a call exchange at least some of the metadata relating to calls to and from the endpoint receive notifications relating to call content from the recording system and match the metadata to the notifications.

With specific reference now to the drawings in detail it is stressed that the particulars shown are for the purpose of example and solely for discussing the preferred embodiments of the present invention and are presented in the cause of providing what is believed to be the most useful and readily understood description of the principles and conceptual aspects of the invention. In this regard no attempt is made to show structural details of the invention in more detail than is necessary for a fundamental understanding of the invention. The description taken with the drawings makes apparent to those skilled in the art how the several forms of the invention may be embodied in practice.

It is to be understood that the invention is not limited in its application to the details of construction and the arrangement of the components set forth in the following descriptions or illustrated in the drawings. The invention is applicable to other embodiments and may be practiced or carried out in various ways. Also it is to be understood that the phraseology and terminology employed herein is for the purpose of description and should not be regarded as limiting.

Reference is made to which illustrates the general flow of information in a call recording system such as might be used to operate a call center. Only one call center agent is shown for the purpose of this illustration although any number of call center agents may be used. The system comprises user communication network endpoints and private branch exchange PBX recording system and controller . The recording system comprises various components including recorder and storage or memory e.g. in the form of a database . The recording system includes memory not separately shown in addition to the database . This memory comprises a file structure for recording call content e.g. audio information in the case of audio calls. In practice a system of the kind shown in will be implemented in a communications network which may include enterprise infrastructure such as a wireless network as well as public infrastructure such as the internet. The components of the system shown in may communicate with each other via enterprise and or public communications network infrastructure. Alternatively some of them may be combined such as the controller and the PBX .

Controller may include one or more computer controllers or processors. Controller and other units herein may be configured to carry out all or part of the methods disclosed herein by for example including circuitry configured to perform certain operations and or by being connected to a non transitory memory or storage device including instructions which when executed carry out methods according to embodiments of the invention.

Recording system may include one or more computer controllers or processors for example comprised in recorder . The computer controllers or processors may be configured to perform certain operations.

In general the controller has various roles including the provision of initial data such as IP address and device identifiers IDs to initiate recording e.g. at start up time notification e.g. to different applications relating to ongoing interactions and recordings to allow monitoring and tagging of interactions and the halting of recording on demand e.g. for compliance purposes.

Communication network end point is operated by call center agent . End point will usually be in the form of an Internet Protocol IP telephone phone but could also be a computer e.g. desktop or laptop or tablet computing device with voice communications capability. Whether or not it is in the form of a telephone an endpoint with voice communications capability can be referred to as a telephony end point. It should be noted however that the methods to be described below are applicable to all kinds of communication sessions and are not limited to voice communications. As noted above other kinds of communication include video instant messaging e mail facsimile fax and the Internet or web. The invention is not limited to these examples.

In the illustration of the end point is an IP phone. IP phone or other end point may include a built in bridge to enable forking of information flows such as may be required for conferencing or as will be described below recording calls to and from the IP phone. The operation of IP phone is controlled by controller e.g. via the PBX . Communication network endpoint is shown in communicating with communication network end point operated by customer . Endpoint may be controlled by a different controller. However in some possible implementations of the method and system to be described endpoint may be controlled and content data from it recorded in the same manner using the same system components as endpoint . Thus in a communications system using the invention there may be agent endpoints and customer endpoints used by customer users and agent users.

Other network endpoints not illustrated in include smart media gateways Interactive Voice Response IVR servers Session Border Controllers SBCs and other end point devices of a communication network. The recording method to be described below with particular reference to a telephony endpoint is also applicable to other network end points in the communications system which route content and associated metadata to be recorded e.g. in a file structure.

Communication network end point may be in the form of an Internet Protocol IP phone a computer e.g. desktop or laptop or tablet computing device preferably with voice communications capability. End point need not be IP enabled and could be a conventional packet switched telephone network PSTN phone.

In order for a call to or from agent end point to be recorded the recording system is joined as a party to the call using the bridge in end point . The bridge is configured by the controller via the PBX . Each physical phone e.g. end point can have multiple lines which can be recorded independently in end point . Each line can be configured under the control of controller sending control signals via the PBX for 

In a typical set up there will be separate voice streams receive Rx and transmit Tx between agent end point and customer endpoint . Communications to and from an agent end point can be recorded and monitored at the same time. The monitoring and recording is done under the control of controller via PBX which instructs the agent end point to send data to recording system . Two streams one for transmit and one for receive are then established between the agent end point and the recording system . In an alternative embodiment one stream is established for both transmitted and received data.

It should be noted that the agent and or customer can be notified that they are being recorded by an audible tone. Usually recording has no effect on the agent s or customer s visual display if provided although a visual indication of recording is possible.

The methods to be described below are intended for a total or automatic recording although they may have other applications. It will be appreciated from the foregoing that total recording could be operated under the control of the controller . Thus a possible flow for total recording is as follows 

It should be noted that it is not always the case that separate transmit and receive streams are created and the methods described below are applicable to separate also known as stereo streams as well as combined transmit and receive streams also known as summed streams.

The controller also known as an interactions center may include a database storing interaction metadata.

Because the IP address has been provided by the recorder to the controller prior to recorder joining the call it is possible to correlate metadata relating to the call which is reported to the controller with the information stored at the recording system .

It will be appreciated that each call in the flow described above involves the exchange of messages between the elements for establishment. For VoIP calls audio data from the agent end point is conveyed in real time protocol RTP packets. The following description will describe flows using RTP packets by way of example but as noted above the method to be described is not limited to the recording of audio information. The RTP packets contain the call content such as the audio data.

In the flow just described all recording is done under the operation of the controller . This means that there may be interruptions in recording if there is any failure of controller or network failure between controller and recorder or between controller and PBX . Typically the recording system and the controller are in different locations. A network failure could be particularly problematic if public infrastructure is required to route messages between the controller and the recording system since the restoration of operation may be beyond the control of the operator of the controller and recorder of .

It would be advantageous to provide a system in which recording was possible independently of the controller so that for example recording would be possible even if the controller was off line for any reason. In the following there is described a method in which the recording system behaves independently of controller requests. This presents an additional problem in that information recorded at recording system needs to be correlated with interaction metadata provided to the controller .

The respective roles of the controller and the recording system are illustrated in . Here it is shown that a recording system comprises a recorder and associated storage . The recorder receives RTP packets and creates a data file for each session between an agent and a customer which is stored along with interaction metadata. The interaction metadata may be stored in a database at the recording system that is linked to the file structure.

As is known in the art the controller typically receives information relating to a call from the PBX . The controller has an associated database . This database stores only interaction metadata. Database does not store content of the RTP packets e.g. audio information. This content is stored in the recording system . More specifically database stores only full interaction metadata i.e. without the content of RTP packets for future application usage evaluation different queries etc. . Database is used also for storing part of the metadata allowing playback archiving moving the data file to final storage and other usage when the central database is not accessible.

One of the purposes of storing interaction metadata in database is to facilitate the searching of content data stored in files at the recording system .

The term session in the following is used to describe a data file created by a recorder based on data e.g. RPT packets received by the recorder. Thus the recorder stores a session or data file relating to each call. It is possible for more than one session to be associated with a call as will be explained in the following in which case each session comprises a subset of the content data sent to or from an endpoint during a call. It is possible to create separate sessions one for the transmit stream and one for the receive stream for example.

The term recording as a single noun is used in the following to denote a collection of metadata relating to a session such as might be stored in a controller operational database as described further below. As the following explanation will show it is possible for there to be more than one session corresponding to a single call or interaction. In the embodiments of the invention described below one recording is created for each session. Each recording and session will be associated with an interaction.

Where recording is used as a verb it usually refers to the accumulation of content data from a call such as audio information in the traditional sense of recording albeit that this will be in digital usually packetized form.

More generally a session is an object e.g. file on the recording system side and a recording is a corresponding object on the controller side. A recording has a reference to the corresponding session plus additional metadata e.g. status etc. .

However additional measures are required to match metadata in the respective databases and when the recording has taken place independently of the controller . In this situation the recording system needs to create one or more files sessions for each interaction call based on incoming data RTP packets . A problem which the methods describe below address is how to ensure metadata congruity between the operational database of controller and the database at recorder . In this connection it should be borne in mind that the controller needs to know about the data files sessions . This may be required for example because the data file path is part of reported metadata to operational database . On the other hand the recorder needs to know about the interactions so that interaction metadata on the recorder can be used for fetching playback archiving etc. . In other words the controller does not need the content of the sessions but it needs to know how to identify them and conversely the recorder needs to know what interaction data is available at the controller therefore the respective sets of metadata at the controller and the recorder must be correlated.

In one possible implementation of this system the session ID but not file path may be reported to the controller. The Session ID may be kept in the recorder database with the actual file path. Once a playback archiving request arrives at the recorder it performs resolution of the files path according to session ID. The method of recording to be described below allows changing of actual file path for example during an archiving process or moving to another location without the need to update the operational database at the controller .

Although the following description will focus on a single agent endpoint it will be appreciated that the PBX and controller will in practice control multiple endpoints and the recorder will receive information from those multiple endpoints.

In the following methods of operation of the recorder independently of the controller will firstly be described followed by a description of how congruity between metadata is ensured. Both are firstly described at a general level followed by a more detailed description.

It should firstly be noted that a communication channel is preferably established between the recorder and the IP endpoints for which the recorder is monitoring calls whereby the recorder can listen to all calls.

Since the recorder is operating independently of the controller the controller is merely listening for notifications in order to perform an update operation at the end of an interaction and may not be controlling a call set up for example.

Each of show two RTP streams receive RX and transmit TX. The time proceeds in the vertical downward direction.

As is known in the art each RTP packet has inserted into its header a list of synchronization source SSRC identifiers of the sources that contributed to the generation of that packet. In the method shown in the recorder creates files based on SSRC changes. In other words a new data file is created if the SSRC is changed in one of the RTP streams. This method may operate according to the following rules 

As shown in at time t a new session labelled session is opened. A first SSRC change is noted at time t in the transmit stream TX. This results in a new session session being opened and session being closed. A second SSRC change is noted in the receive stream RX at time t. Since t t is greater than the predetermined delay of X seconds session is closed and session is opened.

It should be noted that in the case of summed recording e.g. when there is only one stream per session from end point to recording system every change in SSRC will result in one session being closed and a new session being opened.

It will be seen from the foregoing that the recorder operates according to a deterministic algorithm for creating files based on data only SSRC or silence without the controller intervening. It should be noted that the session files data files can be closed in other circumstances than those given above such as when failures occur.

In the methods described below it is proposed that only the controller of all the components of the recording system is responsible for deciding on data e.g. audio content and metadata correlation. Thus one component in this example the controller updates all i.e. the controller triggers updating of the metadata on the recorder and the updating of the interactions database .

The controller performs correlation of metadata at the end of an interaction or during an interaction once it is able to decide if a recording relating to a session hereinafter a recording session or possibly a recording session that is still open belongs to a current interaction. In this case it simply updates the recorder by sending it a notification and recorder in its turn updates the local database to update the recording. Thus 

The operation of the controller and the recorder is illustrated by the timing diagram of . In the controller is shown as comprising call server CallSrvr and resource coordination manager RCM. The recorder is shown as comprising a capture module and file generator FG.

In at time t the caller receives a notification that a call has commenced from the PBX . This is noted as the start time of an interaction and an interaction with relevant metadata is created on the controller referred to as Interaction .

A time t the first RTP packet is received by the recorder. At this time the recorder opens a new session content file with ID. As noted above this is done autonomously by the recorder without any instruction from the controller .

At time t the controller receives an event notification from the recorder that the recorder has received an RTP packet i.e. a non null RTP packet and a new recording collection of metadata is created at the controller . The recorder notifies the controller that the corresponding session file has ID. It should be noted here that if the controller fails or is offline the delay between t and t will be greater than normal but recording by the recorder will not be affected and may for example be completed by an offline process.

At time t the recorder either ceases to receive RTP packets or ceases to receive RTP packets with content. The recorder closes the session according to the procedure described above with reference to and sends an event notification to the controller to notify the controller that the session ID is complete. At the recorder the first session is closed. The controller at this point will update the recording stop time and keep the recording in memory. However the controller will not close the recording until it receives the appropriate metadata from the PBX i.e. confirmation that the call to which the recording relates has ended at t see below .

At time t the flow of content containing RTP packets to the recorder recommences. The recorder opens session according to the procedure of and notifies the controller The controller opens a new recording corresponding to session . The controller attaches this recording to the current open interaction ID .

At time t the controller receives confirmation from the PBX that the first call has ended. At this point the controller has two recordings and the recorder has a closed session Session and an open session Session attached to the interaction ID. The controller checks all recordings attached to the interaction being closed and deduces that only one session the first one S is related to the interaction the second session is filtered out since its duration 

At time t the controller receives a notification of a new interaction commencing before receiving a stop notification corresponding to the second session. A new recording commences at the controller and is attached to interaction ID. Therefore the controller has one open recording S and a similar process to that described above continues at the end of each interaction.

At time t the recorder either ceases to receive RTP packets or ceases to receive RTP packets with content. The recorder closes the session according to the procedure described above with reference to and sends an event notification not shown in to the controller to notify the controller that the session ID is complete.

In the foregoing and the following there are several mentions of configurable time limits e.g. 1 second. This time period can be varied configured according to the implementation of the method or system. The actual time periods chosen may depend on customer site conditions for example.

It should be noted in the foregoing that the recorder sends notifications also known as update messages to the controller without being requested to do so by the controller. The recorder has its own internal management mechanism for the sending of such updates such as silence and SSRC events which the controller can match with information it holds.

At operation in the recorder receives RTP packets from end points or nodes in the communications network of which the components of form a part and creates data files sessions based on the content of the RTP packets. The files are structured such that one or more files are allocated to each IP address port or device.

Find the current stream for the same source and compare the SSRC in the current stream with the SSRC of newly captured packet operation .

If both SSRCs are the same the recorder continues processing of captured data to the same stream i.e. a file allocated to that stream operation .

Again a check is made to ensure that the packet is not from the same stream that caused the opening of the session 

It should be noted at this point that the recorder only holds metadata relating to sessions and streams. This is not held at the controller.

The following tables show examples of a session structure and a stream structure that may be used in the recording system. Note that these are held at the recorder only and not at the controller. One session may correspond to two streams which is one reason for having separate session and stream structures. These structures include a minimum amount of metadata for identifying the sessions and streams and associating them with each other. More metadata is held at the controller or operational database as will be described below.

It should be noted that these structures contain new fields to hold metadata received from the controller for example InteractionID AgentID DeviceID

Regular processing continues as shown at operation . It will be appreciated that if there are multiple sessions corresponding to a stream operation will be repeated for each open session.

The process for summed recording is simpler and is not illustrated. The session last packet time is determined when no RTP packet is captured for a stream related to a source 

The controller holds a data structure of all open calls and their sessions. Every call interaction has a start time and stop time. Every session file has a start time and stop time associated with it. A preferred method of operating the controller to create a recording is now described with reference to .

After the recorder has opened a new session it reports this to the controller . The session is created at the recording system when an agent customer start talking. A new session file is opened and this is reported to the controller at operation . At operation the controller finds the relevant interaction the commencement of which should have been notified to it by the PBX. Usually the notification of the interaction e.g. in the form of a CTI message comes before the metadata relating to the session from the recording system . However if session metadata comes before a CTI or other message relating to the interaction from the PBX the controller keeps it until an interaction is reported e.g. by the PBX and starts processing according to recording device identity information Session.DeviceID or Session. IPAdress attributes of the recorded source according to what was mapped in the system regular flow.

This processing will usually include the creation of a new recording metadata collection corresponding to the session.

Once the relevant interaction is found by or received by the controller the controller adds the recording to this interaction or associates the recording with the interaction e.g. using the database . It is not necessary for the operational database to be used at this point. For example interactions may be kept in the controller internal memory and reported to the database at a later stage. However it is possible to use database to hold open interactions.

A decision is next made at whether this is the first recording corresponding to a session in the interaction. If it is the first recording Interaction.Recordings null it creates a new recording at operation and adds the recording to this interaction. If this interaction already has recordings for this source e.g. domain name DN the last recording is closed and a new one is added at operation Interaction.Recordings Recording . Thus it is possible to have more than one session and corresponding recording per interaction e.g. due to silence during recording SSRC changing. On creation of a new recording the controller marks the current recording as closed Stop Time SessionStopTime and opens a new recording with new session ID.

It will be noted that the interaction metadata stored at the controller is more comprehensive than that stored at the recording system and includes such items as participants that are not identified in the recording system database .

During an interaction a list is compiled of all recordings that might be associated with it. At the point of operation the controller may not have received a Completion with SessionID notification see from the recorder in response to which a recording ends so the recordings searched in operation have not necessarily ended they may be ended within a few milliseconds . The controller goes over all recordings that might relate to the ended interaction notified at . The procedure commences with the next interaction recording being fetched from the list at operation . A decision is made at as to whether the recording is null i.e. there are no recordings to be fetched because they have already been processed.

The following is performed on every recording If the recording is not null a check is made at operation whether this is the first recording in the interaction it was reported to be the first by the recorder according to the start recording time If a recording overlaps in time with an interaction Rec.StopTime Interaction.StartTime it can be deduced that it belongs to this interaction. In real time the decision is even simpler. If an interaction exists when a recording session is reported or open it may relate to this interaction. If yes the recording will be discarded at operation if it is decided at operation that it is less than a minimum configurable duration. If no a check is also made at decision as to whether this is the last recording. This can be done for example by correlating start stop recording time with start stop interaction time. If yes the recording will also be discarded at operation if it is decided at operation that it is less than a minimum duration. If the recording is neither first nor last it will be added to a list of non discarded recordings at operation . If there is no recording to be fetched to an ended interaction the flow continues to operation where non discarded recordings are reported to interaction database and recorder .

It will be appreciated from the foregoing that permitting the recorder or recording system to operate independently of the controller ensures that total recording can take place even if the controller is offline or otherwise not available. The recorder creates files based on incoming data e.g. in the form of RTP packets only.

The proposed method of operation of the controller ensures that the controller knows about the data files sessions as well as the recorder knowing about the interactions.

The problems discussed above are solved by having one component in this example the controller responsible for all metadata updates. This ensures that the same metadata is associated with both controller and recorder. The association is done at one point in time in the examples this point is interaction end. At this point a decision as to which recording belongs to which interaction can be taken.

At the end of an interaction the controller has the whole picture history of the interaction which may be related to its recordings so the controller can take the decision.

The recorder operates according to a deterministic algorithm for creating files based on data only. The recorder continues recording data file creation even without controller.

The invention presents a new concept in which preferably the controller or optionally another component in a recording system is responsible for metadata association to both an operational database and the recorder database. It also presents a system with the ability for the recorder to act in independent way whereby even without the controller the recorder continues recording to files. In this connection it is particularly advantageous for the controller to update the metadata at the end of an interaction.

The controller is the presently preferred part of the system for this responsibility since it is responsible for updating the operational database which may or may not be part of the controller dealing with metadata sending events to different applications and controlling interaction flow. It may interface with or report to many other applications that need interaction metadata. In addition one controller may control multiple recorders. The recorder has only to make sure that an interaction is being recorded and the controller can take care of the metadata.

It will be appreciated that the use of a database at the recording system and or the controller may facilitate the examination of relationships between for example any of the interactions sessions streams and recordings. Such a database may comprise anything from a simple table to a complex relational database. The database held at the recording system may contain links to sessions files .

The methods and systems described above are particularly useful in file based recording where they can be used to create a robust file based recording structure for total recording environments. The files or other content storage structure are created in a real time manner rather than for example being created offline. However it should be noted that the methods and systems described above are not only applicable to file based recording and could for example be used in methods and systems where data is recorded in an unformatted stream e.g. on a disc for later analysis. It should be noted that the recorder data files may include complete metadata or at least sufficient metadata for the files on the recorder to be used even without central storage. The methods and systems described above are especially easy to maintain.

The methods and systems described above will be useful in any situation where there is a need to save data to files from multiple systems at high volume. The recording system is particularly useful for compliance where there is a need to save data to files attach metadata to data files.

As will be appreciated by one skilled in the art aspects of the present invention may be embodied as a system method or an apparatus. Accordingly aspects of the present invention may take the form of an entirely hardware embodiment an entirely software embodiment including firmware resident software micro code etc. or an embodiment combining software and hardware aspects that may all generally be referred to herein as a circuit module or system . Thus an embodiment of the invention may take the form of one or more computer readable media comprising instructions which when executed on one or more processors in a computing system cause the system to implement any of the methods described above.

The aforementioned flowcharts and block diagrams illustrate the architecture functionality and operation of possible implementations of systems and methods according to various embodiments of the present invention. In this regard each block in the flowchart or block diagrams may represent a module segment or portion of code which comprises one or more executable instructions for implementing the specified logical function s . It should also be noted that in some alternative implementations the functions noted in the block may occur out of the order noted in the figures. For example two blocks shown in succession may in fact be executed substantially concurrently or the blocks may sometimes be executed in the reverse order depending upon the functionality involved. It will also be noted that each block of the block diagrams and or flowchart illustration and combinations of blocks in the block diagrams and or flowchart illustration can be implemented by special purpose hardware based systems that perform the specified functions or acts or combinations of special purpose hardware and computer instructions.

In the above description an embodiment is an example or implementation of the inventions. The various appearances of one embodiment an embodiment or some embodiments do not necessarily all refer to the same embodiments.

Although various features of the invention may be described in the context of a single embodiment the features may also be provided separately or in any suitable combination. Conversely although the invention may be described herein in the context of separate embodiments for clarity the invention may also be implemented in a single embodiment.

Reference in the specification to some embodiments an embodiment one embodiment or other embodiments means that a particular feature structure or characteristic described in connection with the embodiments is included in at least some embodiments but not necessarily all embodiments of the inventions.

It is to be understood that the phraseology and terminology employed herein is not to be construed as limiting and are for descriptive purpose only.

It is to be understood that the details set forth herein do not construe a limitation to an application of the invention.

Furthermore it is to be understood that the invention can be carried out or practiced in various ways and that the invention can be implemented in embodiments other than the ones outlined in the description above.

It is to be understood that the terms including comprising consisting and grammatical variants thereof do not preclude the addition of one or more components features steps operations or integers or groups thereof and that the terms are to be construed as specifying components features steps operations or integers.

If the specification or claims refer to an additional element that does not preclude there being more than one of the additional element.

It is to be understood that where the claims or specification refer to a or an element such reference is not be construed that there is only one of that element.

It is to be understood that where the specification states that a component feature structure or characteristic may might can or could be included that particular component feature structure or characteristic is not required to be included.

Where applicable although flow diagrams may be used to describe embodiments the invention is not limited to those diagrams or to the corresponding descriptions. For example flow need not move through each illustrated box or state or in exactly the same order as illustrated and described.

The term method may refer to manners means techniques and procedures for accomplishing a given task including but not limited to those manners means techniques and procedures either known to or readily developed from known manners means techniques and procedures by practitioners of the art to which the invention belongs.

The descriptions examples methods and materials presented in the claims and the specification are not to be construed as limiting but rather as illustrative only.

Meanings of technical and scientific terms used herein are to be commonly understood as by one of ordinary skill in the art to which the invention belongs unless otherwise defined.

The present invention may be implemented in the testing or practice with methods and materials equivalent or similar to those described herein.

While the invention has been described with respect to a limited number of embodiments these should not be construed as limitations on the scope of the invention but rather as exemplifications of some of the preferred embodiments. Other possible variations modifications and applications are also within the scope of the invention. Accordingly the scope of the invention should not be limited by what has thus far been described but by the appended claims and their legal equivalents.

