---

title: Apparatus and method for processing an interactive service
abstract: A method of processing an interactive service and an apparatus thereof are disclosed. The present invention includes sending a discovery message to a second screen application, receiving a request for descriptions of the second screen support services, sending a response with the descriptions, receiving a trigger, and delivering the trigger to the second device using a trigger service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08887223&OS=08887223&RS=08887223
owner: LG Electronics Inc.
number: 08887223
owner_city: Seoul
owner_country: KR
publication_date: 20131017
---
This application claims the benefit of U.S. Provisional Application No. 61 715 317 filed on Oct. 18 2012 U.S. Provisional Application No. 61 718 679 filed on Oct. 25 2012 and U.S. Provisional Application No. 61 721 007 filed on Oct. 31 2012 which are hereby incorporated by reference as if fully set forth herein.

The present invention relates to a method and apparatus for providing receiving and processing a broadcast service and more particularly to a method and apparatus for providing a supplementary service related to broadcast content.

TVs first appeared at the end of the 19th century and have become the most popular information delivery apparatus since the end of the 20th century as a screen display method or design thereof has been continuously developed. However TVs generally enable viewers to receive unidirectional information from a broadcast station. Such TV limitations have become problematic as personal computers PCs and the Internet have come into widespread use since the 1990s. Therefore TVs have been developed to be able to provide an interactive service.

However currently there is no system for providing an interactive service between a content provider and a viewer. In particular in order to provide such an interactive service there is a need for a method of executing an application related to broadcast content which is currently being broadcast at a specific time and providing related information to a viewer through special information processing.

Accordingly the present invention is directed to an apparatus and method for processing an interactive service that substantially obviates one or more problems due to limitations and disadvantages of the related art.

An object of the present invention devised to solve the problem lies on supplementary information related to broadcast content at an appropriate time during a period when the broadcast content is played back.

Additional advantages objects and features of the invention will be set forth in part in the description which follows and in part will become apparent to those having ordinary skill in the art upon examination of the following or may be learned from practice of the invention. The objectives and other advantages of the invention may be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

To achieve these objects and other advantages and in accordance with the purpose of the invention as embodied and broadly described herein a method of processing an interactive service at a first device according to the present invention includes sending a discovery message to a second screen application running in a second device wherein the discovery message advertises second screen support services that the first device can provide receiving a request for descriptions of the second screen support services from the second screen application sending a response with the descriptions to the second screen application receiving a trigger from a broadcast stream or an internet server and delivering the trigger to the second device using a trigger service wherein the trigger service is one of the second screen support services wherein the trigger service is for delivering the trigger wherein the trigger is a signaling element whose function is to identify signaling and establish timing of playout of interactive events targeted to applications for a segment described by an application parameter table wherein the trigger is one of a time base trigger an activation trigger an interaction trigger or a channel change trigger wherein the time base trigger is used to establish a time base for the event wherein the activation trigger sets an activation time for the event wherein the interaction trigger is used for interaction models other than a Triggered Declarative Object interaction model wherein the channel change trigger is delivered whenever a channel is changed.

Preferably the method further comprising receiving a searching message for searching devices including the first device that offer the second screen support services before the sending the discovery message.

Preferably the trigger service offers an unfiltered stream option and the unfiltered stream option is an option that delivering all types of the trigger.

Preferably the first device delivers the all types of the trigger as soon as the trigger is received by the first device.

Preferably the delivering the trigger includes combining information from the activation trigger with information from the application parameter table to generate an augmented activation trigger and sending the generated augmented activation trigger to the second screen application.

Preferably the trigger service offers a filtered stream option and the filtered stream option is an option that delivering the trigger which is one of the augmented activation trigger the interaction trigger or the channel change trigger.

Preferably the augmented activation trigger includes an application URL information having same value with an URL element of an application element in the application parameter table the URL element identifies a file which is part of the application and the application element is identified by the activation trigger.

Preferably the augmented activation trigger further includes an event information representing an event element in the application parameter table wherein the event element identified by the activation trigger represents the event for the application wherein the event information includes an action information having same value with an action attribute of the event element identified by the activation trigger and wherein the action attribute indicates type of an action to be applied when the event is activated.

Preferably the first device delivers the augmented activation trigger at the activation time of the augmented activation trigger wherein the first device delivers the interaction trigger when the interaction trigger is received by the first device and wherein the first device delivers the channel change trigger when the channel is changed.

In another aspect of the present invention a method of processing an interactive service at a second screen application running in a second device according to the present invention includes receiving a discovery message from a first device wherein the discovery message advertise second screen support services that the first device can provide sending a request for descriptions of the second screen support services to the first device receiving a response with the descriptions from the first device accessing a trigger service using information given in the descriptions and receiving a trigger from the first device using the trigger service wherein the trigger service is one of the second screen support services wherein the trigger is a signaling element whose function is to identify signaling and establish timing of playout of interactive events targeted to applications for a segment described by an application parameter table wherein the trigger is one of a time base trigger an activation trigger an interaction trigger or a channel change trigger wherein the time base trigger is used to establish a time base for the event wherein the activation trigger sets an activation time for the event wherein the interaction trigger is used for interaction models other than a Triggered Declarative Object interaction model wherein the channel change trigger is delivered whenever a channel is changed.

Preferably the method further comprising multicasting a searching message for searching devices including the first device that offer the second screen support services before the receiving the discovery message.

Preferably the trigger service offers an unfiltered stream option and the unfiltered stream option is an option that delivering all types of the trigger.

Preferably the receiving the trigger includes receiving an augmented activation trigger generated by combining information from the activation trigger with information from the application parameter table.

Preferably the trigger service offers a filtered stream option and the filtered stream option is an option that delivering the trigger which is one of the augmented activation trigger the interaction trigger or the channel change trigger.

Preferably the augmented activation trigger includes an application URL information having same value with an URL element of an application element in the application parameter table wherein the URL element identifies a file which is part of the application and wherein the application element is identified by the activation trigger.

Preferably the augmented activation trigger further includes an event information representing an event element in the application parameter table wherein the event element identified by the activation trigger represents the event for the application wherein the event information includes an action information having same value with an action attribute of the event element identified by the activation trigger and wherein the action attribute indicates type of an action to be applied when the event is activated.

Preferably the augmented activation trigger is delivered at the activation time of the augmented activation trigger the interaction trigger is delivered as soon as possible and the channel change trigger is delivered when the channel is changed.

In another aspect of the present invention provided herein is an apparatus for processing an interactive service as a first device according to the present invention includes a first module configured to receive a trigger from a broadcast stream or an internet server and a second module configured to send a discovery message to a second screen application running in a second device wherein the discovery message advertises second screen support services that the first device can provide receive a request for descriptions of the second screen support services from the second screen application send a response with the descriptions to the second screen application and deliver the trigger to the second device using a trigger service wherein the trigger service is one of the second screen support services wherein the trigger service is for delivering the trigger wherein the trigger is a signaling element whose function is to identify signaling and establish timing of playout of interactive events targeted to applications for a segment described by an application parameter table wherein the trigger is one of a time base trigger an activation trigger an interaction trigger or a channel change trigger wherein the time base trigger is used to establish a time base for the event wherein the activation trigger sets an activation time for the event wherein the interaction trigger is used for interaction models other than a Triggered Declarative Object interaction model wherein the channel change trigger is delivered whenever a channel is changed.

Preferably the second module further configured to receive a searching message for searching devices including the first device that offer the second screen support services before sending the discovery message.

Preferably the trigger service offers an unfiltered stream option and wherein the unfiltered stream option is an option that delivering all types of the trigger.

Preferably the second module delivers the all types of the trigger as soon as the trigger is received by the first module.

Preferably the second module further configured to combine information from the activation trigger with information from the application parameter table to generate an augmented activation trigger and send the generated augmented activation trigger to the second screen application.

Preferably the trigger service offers a filtered stream option and wherein the filtered stream option is an option that delivering the trigger which is one of the augmented activation trigger the interaction trigger or the channel change trigger.

Preferably the augmented activation trigger includes an application URL information having same value with an URL element of an application element in the application parameter table wherein the URL element identifies a file which is part of the application and wherein the application element is identified by the activation trigger.

Preferably the augmented activation trigger further includes an event information representing an event element in the application parameter table wherein the event element identified by the activation trigger represents the event for the application wherein the event information includes an action information having same value with an action attribute of the event element identified by the activation trigger and wherein the action attribute indicates type of an action to be applied when the event is activated.

Preferably the second module delivers the augmented activation trigger at the activation time of the augmented activation trigger the second module delivers the interaction trigger when the interaction trigger is received by the first module and the second module delivers the channel change trigger when the channel is changed.

In another aspect of the present invention provided herein is an apparatus for processing an interactive service as a second screen application running in a second device according to the present invention includes a first module configured to receive a discovery message from a first device wherein the discovery message advertise second screen support services that the first device can provide send a request for descriptions of the second screen support services to the first device and receive a response with the descriptions from the first device and a second module configured to access a trigger service using information given in the descriptions and receive a trigger from the first device using the trigger service wherein the trigger service is one of the second screen support services wherein the trigger is a signaling element whose function is to identify signaling and establish timing of playout of interactive events targeted to applications for a segment described by an application parameter table wherein the trigger is one of a time base trigger an activation trigger an interaction trigger or a channel change trigger wherein the time base trigger is used to establish a time base for the event wherein the activation trigger sets an activation time for the event wherein the interaction trigger is used for interaction models other than a Triggered Declarative Object interaction model wherein the channel change trigger is delivered whenever a channel is changed.

Preferably the first module further configured to multicast a searching message for searching devices including the first device that offer the second screen support services before receiving the discovery message.

Preferably the trigger service offers an unfiltered stream option and wherein the unfiltered stream option is an option that delivering all types of the trigger.

Preferably the second module further configured to receive an augmented activation trigger generated by combining information from the activation trigger with information from the application parameter table.

Preferably the trigger service offers a filtered stream option and wherein the filtered stream option is an option that delivering the trigger which is one of the augmented activation trigger the interaction trigger or the channel change trigger.

Preferably the augmented activation trigger includes an application URL information having same value with an URL element of an application element in the application parameter table wherein the URL element identifies a file which is part of the application and wherein the application element is identified by the activation trigger.

Preferably the augmented activation trigger further includes an event information representing an event element in the application parameter table wherein the event element identified by the activation trigger represents the event for the application wherein the event information includes an action information having same value with an action attribute of the event element identified by the activation trigger and wherein the action attribute indicates type of an action to be applied when the event is activated.

Preferably the augmented activation trigger is delivered at the activation time of the augmented activation trigger wherein the interaction trigger is delivered as soon as possible and wherein the channel change trigger is delivered when the channel is changed.

It is to be understood that both the foregoing general description and the following detailed description of the present invention are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

Although the terms used in the present invention are selected from generally known and used terms terms used herein may be variable depending on operator s intention or customs in the art appearance of a new technology or the like. In addition some of the terms mentioned in the description of the present invention have been selected by the applicant at his or her discretion the detailed meanings of which are described in relevant parts of the description herein. Furthermore it is required that the present invention is understood not simply by the actual terms used but by the meanings of each term lying within.

In the present specification the term media time stands for a parameter referencing a point in the playout of an audio video or audio content item. ACR stands for Automatic Content Recognition. AMT stands for Activation Messages Table. API stands for Application Programming Interface. DAE stands for Declarative Application Environment. DO stands for Declarative Object. FLUTE stands for File Delivery over Unidirectional Transport. GPS stands for Global Positioning System. HTTP stands for Hypertext Transfer Protocol. IP stands for Internet Protocol. IPTV stands for Internet Protocol Television. iTV stands for Interactive Television. MIME stands for Internet Media Type. NDO stands for NRT Declarative Object. NRT stands for Non Real Time. SMT stands for Service Map Table. SSC stands for Service Signaling Channel. TDO stands for Triggered Declarative Object. TPT stands for TDO Parameters Table. UDO stands for Unbound Declarative Object. UPnP stands for User Plug and Play. URI stands for Uniform Resource Identifier. URL stands for Uniform Resource Locator. XML stands for eXtensible Markup Language. TFT stands for Text Fragment Table. Details thereof will be described below.

DO Declarative Object can be a collection constituting an interactive application. For example HTML JavaScript CSS XML and multimedia files 

The term Triggered Declarative Object TDO is used to designate a Declarative Object that has been launched by a Trigger in a Triggered interactive adjunct data service or a DO that has been launched by a DO that has been launched by a Trigger and so on iteratively.

The term NRT Declarative Object NDO is used to designate a Declarative Object that has been launched as part of an NRT service that is not a Triggered interactive data service.

The term Unbound Declarative Object UDO is used to designate a Declarative Object that is not bound to a service such as a Packaged App or a DO launched by a Link or a DO that has been launched by such a DO and so on iteratively.

The Link is a broadcaster provided URL that points to a web site which provides on line information or functionality related to the current TV programming or NRT service.

The Packaged App is a broadcaster provided Declarative Object DO that provides information or functionality which the broadcaster wants to offer viewers and that is packaged up into a single file for viewers to download and install.

In this specification a time base message includes a time base trigger and an equivalent thereof. Accordingly the term time base message may be used interchangeably with the term time base trigger .

In this specification an activation message includes all information delivery causing activation such as an activation element in an AMT and or an activation trigger.

A typical broadcast stream includes a sequence of TV programs. Each TV program includes an underlying show which is typically broken up into blocks separated by ads and or other interstitial material.

In Segment of Show A Ad1 Ad2 Segment of Show B etc. are sequentially included in the broadcast stream. Segments configuring each show may be referred to as show content and Ads may be referred to as interstitial content.

Each show or piece of interstitial material might or might not have an interactive adjunct data service associated with it.

The term interactive service segment or just segment will be used in this specification to refer to a portion of an interactive adjunct service that is treated by the broadcaster as an integrated unit. An interactive service segment is typically but not necessarily associated with a single show or a single piece of interstitial material.

In order to execute such an interactive adjunct data service there are two models Direct execution model and triggered declarative object TDO model.

In the direct execution model a declarative object DO can be launched automatically as soon as the virtual channel is selected. It can communicate over the Internet with a backend server to get detailed instructions for providing interactive features creating displays in specific locations on the screen conducting polls launching other specialized DOs etc. all synchronized with the audio video program.

In the TDO model signals can be delivered in the broadcast stream or via the Internet in order to initiate TDO events such as launching a TDO terminating a TDO or prompting some task by a TDO. These events can be initiated at specific times typically synchronized with the audio video program. When a TDO is launched it can provide the interactive features it is programmed to provide.

A basic concept behind the TDO model is that the files that make up a TDO and the data files to be used by a TDO to take some action all need some amount of time to be delivered to a receiver given their size. While the user experience of the interactive elements can be authored prior to the broadcast of the content certain behaviors must be carefully timed to coincide with events in the program itself for example the occurrence of a commercial advertising segment.

The TDO model separates the delivery of declarative objects and associated data scripts text and graphics from the signaling of the specific timing of the playout of interactive events.

The information about the TDOs used in a segment and the associated TDO events that are initiated by Triggers is provided by a data structure called the TDO Parameters Table TPT .

Trigger is a signaling element whose function is to identify signaling and establish timing of playout of interactive events.

The trigger includes a time base trigger which serves to indicate a media time of a segment related to an interactive service and an activation trigger which serves to indicate an event occurrence time of an application related to an interactive service.

Triggers can perform various timing related signaling functions in support of interactive services. Triggers can be multi functional depending on their structure a particular Trigger instance can perform one or more of the following functions 

1. Signal the location of a TPT accessible via a FLUTE session in the emission stream via an Internet server or both 

4. Reference a particular interactive event in a TPT and signal that the event is to be executed now or at a specified future Media Time 

5. Indicate that accesses to an Internet server are to be spread out randomly over a specified time interval in order to avoid a peak in demand.

As shown a short time prior to the occurrence of programming segment 1 a pre load Trigger can be delivered to allow receivers an opportunity to acquire the TPT and interactive content associated with programming segment 1. If a pre load Trigger is not transmitted receivers can be expected to use the first Trigger they see within the segment to acquire the content.

Triggers can be sent throughout segment 1 as shown to indicate the current Media Time labeled m in the figure relative to the segment. Periodic delivery of Media Time Triggers can be necessary to allow receivers who are just encountering the channel to synchronize and acquire the interactive content.

In the case of pre produced content non live the TPT that the receiver can acquire after processing the first Trigger can define the timing of all elements of the interactive experience for that segment. All that is needed for the receiver and TDO to play out the interactive elements can be the knowledge of the media timing the TPT can describe interactive events relative to Media Time.

For the case of live content the TPT still contains data and information pertinent to different interactive events however the timing of playout of those events cannot be known until the action in the program unfolds during the broadcast. For the live case the event timing function of the Trigger is utilized. In this mode the Trigger can signal that a specified interactive event is to be re timed to a specified new value of Media Time. Alternatively the Trigger can indicate that a certain event is to be executed immediately.

A third trigger is an event re timing trigger and indicates that the event with eventID 2 in the TPT is to be re timed to occur at Media Time . The hatched area indicates the time interval prior to 240 over which Trigger 3 may be delivered to receivers.

A fifth trigger is an event re timing trigger and indicates that the event with eventID 5 in the TPT is to be re timed to occur at Media Time .

An eighth trigger is an event Trigger and indicates that the event with eventID 12 in the TPT is to be executed immediately.

A ninth trigger is an event re timing Trigger and indicates that the event with eventID 89 in the TPT is to be re timed to occur at Media Time .

A TDO can exist in four different states Released Ready Active and Suspended. A number of different factors can cause a transition from one state to another trigger user action changing channels etc. .

The TDO may include the following four states. The four states are Ready Active Suspended and Released. Ready state means that TDO is downloaded and prepared for execution but not yet executing. Active state means that TDO is executing. Suspended state means that TDO is temporarily suspended from execution with its state saved. Released state means that TDO is not Ready Active or Suspended.

1. Trigger prepare Device receives a trigger in the currently selected primary virtual channel which requests that the TDO be prepared to execute allocate resources load into main memory etc. 

2. Trigger execute Device receives a trigger in the currently selected primary virtual channel which requests that the TDO be activated

3. Trigger suspend Device receives a trigger in the currently selected primary virtual channel which directs that the TDO be suspended

4. Trigger kill Device receives a trigger in the currently selected primary virtual channel which directs that the TDO be terminated

Both Activation messages and Time Base messages can have the general Trigger format under certain delivery circumstances.

The syntactic definition here is described using the Augmented Backus Naur Form ABNF grammar except that the vertical bar symbol is used to designate alternatives. Rules are separated from definitions by an equal indentation is used to continue a rule definition over more than one line literals are quoted with parentheses and are used to group elements optional elements are enclosed in and brackets and elements may be preceded with to designate n or more repetitions of the following element n defaults to 0. And elements may be preceded with designate n or more repetitions and m or less repetitions of the following element.

This Trigger syntax is based on the Uniform Resource Identifier URI Generic Syntax excluding the and portion with additional restrictions.

The trigger may include locator part and terms. Terms may be omitted. If terms are present locator part and terms may be connected by .

The hostname may include domainlabel and toplabel and domainlabel may be repeated 0 times or more along with . . That is hostname may include repeated domainlabel connected with toplabel or include only toplabel.

domainlabel may include one alphanum or include alphanum or repeatedly inserted between alphanum and alphanum 0 times or more.

toplabel includes one alpha or include alphanum or repeatedly inserted between alpha and alphanum 0 times or more.

path segments includes one segment which is followed by segment repeated 0 times or more. At this time segments may be connected by .

Terms may include one of event time or media time which may be followed by spread or others. Spread and others may be omitted. If spread and others are present may be placed ahead of spread and others and spread and others may be placed after event time or media time.

Event time may include digit repeated once or more after e or include hexdigit repeated once or more or seven times or less after t . t and the back part thereof may be omitted.

The length of the trigger may not exceed 52 bytes. In addition the hostname portion of the Trigger can be a registered Internet domain name.

The can reference a registered Internet domain name. The can be an arbitrary character string identifying a directory path under the control and management of the entity who owns rights to the identified domain name.

In the TDO model the combination of and can uniquely identify a TPT that can be processed by a receiver to add interactivity to the associated content.

The combination of and can be the URL of an Internet location where the TPT for the current segment can be obtained.

That is the trigger may identify the TPT using and . Through and it is possible to confirm the TPT to which the trigger applies. The role performed by applying the trigger to the TPT depends on .

The event time term can be used in an Activation trigger to identify the targeted event e term and the time the event should be activated t term . When the t term is absent that means the event should be activated at the time the trigger arrives.

That is e which is an interactive event ID term can reference the appID in the associated TPT of the TDO targeted by the event the eventID of the specific event and the dataID of the Data element to be used for this event activation.

 t which is an optional timing value term can indicate a new media timing for the designated event. If the t part is not present that can mean the timing for the designated event is the arrival time of the Trigger.

The media time term m term can be used in a Time base trigger to identify the current time relative to the time base represented by the Time base trigger. Content identifier information c term for identifying currently displayed content may be further included in media time. For c term the direct execution model will be described below.

That is m which is a media timestamp term followed by a character string of 1 to 8 characters in length representing a hexadecimal number can indicate the current Media Time.

The spread term can be used to indicate that any action taken in response to a Time base trigger such as retrieving a TPT from a server or an Activation trigger such as causing a TDO to access a server should be delayed a random amount of time to spread out the workload on the server.

 s term can indicate the number of seconds of time over which all receivers should attempt to access the Internet server identified in the Trigger. Each individual receiver can be expected to derive a random time within the designated interval and delay the access request by that amount thereby spreading in time the peak in demand that might otherwise occur at the first appearance of a Trigger at the receiver.

A Trigger containing a parameter can be called a Time base trigger since it is used to establish a time base for event times.

A Trigger containing an parameter can be called an Activation Trigger since it sets an activation time for an event.

A TDO Parameters Table TPT contains metadata about the TDOs of a segment and the Events targeted to them.

Hereinafter fields included in the table will be described. The sizes of the fields and the types of the fields included in the table may be added or changed according to designer s intention.

TDO parameter table TPT may include majorProtocolVersion minorProtocolVersion id tptVersion expireDate updatingTime serviceID baseURL attributes Capabilities LiveTrigger and or TDO element.

TPT is the root element of the TPT. One TPT element describes all or a portion in time of one programming segment.

MajorProtocolVersion which can be 4 bit attribute can indicate the major version number of the table definition. The major version number can be set to 1. Receivers are expected to discard instances of the TPT indicating major version values they are not equipped to support.

When present MinorProtocolVersion which can be 4 bit attribute can indicate the minor version number of the table definition. When not present the value defaults to 0. The minor version number can be set to 0. Receivers are expected to not discard instances of the TPT indicating minor version values they are not equipped to support. In this case they are expected to ignore any individual elements or attributes they do not support.

 id which is URI can uniquely identify the interactive programming segment which This TPT element pertains to. id serves as an identifier of a segment. Accordingly after a receiver parses the TPT a trigger an AMT etc. related to one segment may match the TPT having id for identifying the segment using id information. Accordingly a segment to which the trigger and the AMT will apply may be found. The details of the AMT will be described below.

 tptVersion which can be 8 bit integer can indicate the version number of the TPT element identified by the id attribute. The tptVersion can be incremented whenever any change is made to the TPT.

When present expireDate attribute of the TPT element can indicate the date and time of the expiration of the information included in this TPT instance. If the receiver caches the TPT it can be re used until the expireDate.

When present updatingTime which can be 16 bit element can indicate that the TPT is subject to revision and it gives the recommended interval in seconds to download the TPT again and check whether the newly downloaded TPT is a new version.

When present serviceID which can be 16 bit integer can indicate the NRT service id associated with the interactive service described in this TPT instance. This is needed for receivers to get FLUTE parameters from the Service Map Table when files for this interactive service are delivered in the broadcast stream.

When present baseURL attribute can give a base URL which when concatenated onto the front of any relative URLs that appear in this TPT. It can give the absolute URLs of the files.

When present Capabilities element can indicate capabilities that are essential for a meaningful presentation of the interactive service associated with this TPT. Receivers that do not have one or more of the required capabilities are expected not to attempt to present the service.

LiveTrigger element presents if and only if delivery of Activation Triggers via Internet is available. When present it can provide information needed by a receiver to obtain the Activation Triggers. The child element and attribute of LiveTrigger will be described below.

TDO which is a child element of the TPT element can represent an application for example a TDO that provides part of the interactive service during the segment described by this TPT instance. The child element and attribute of TDO will be described below.

As described above LiveTrigger element presents if and only if delivery of Activation Triggers via Internet is available. When present it can provide information needed by a receiver to obtain the Activation Triggers.

 URL which is an attribute of the LiveTrigger element can indicate the URL of a server that can deliver Activation Triggers via Internet. Activation Triggers can be delivered via Internet using HTTP short polling HTTP long polling or HTTP streaming at the option of the interactive service provider.

When present pollPeriod which is an attribute of the LiveTrigger element can indicate that short polling is being used to deliver Activation Triggers and the value of the pollPeriod attribute can indicate the recommended time in seconds for the receiver to use as a polling period.

If LiveTrigger element is present the receiver may parse the TPT and obtain information used to deliver the activation trigger using the Internet. The URL of the server which may receive the activation trigger may be used using URL information. Through pollPeriod information or information indicating that pollPeriod attribute is not present a method of delivering the activation trigger via the Internet and information about the polling period may be obtained. pollPeriod will be described in detail below.

TDO element may include appID appType appName globalID appVersion cookieSpace frequencyOfUse expireDate testTDO availInternet availBroadcast attribute URL Capabilities Contentitem and or Event element.

As described above TDO which is a child element of the TPT element can represent an application for example a TDO that provides part of the interactive service during the segment described by this TPT instance.

 appID which can be 16 bit integer can identify the application uniquely within the scope of the TPT. An Activation Trigger identifies the target application for the Trigger by means of a reference to the appID. appID is an identifier of an application. One TPT may include several applications such as TDO . Accordingly after parsing the TPT the application may be identified using appID information. The trigger AMT etc. which will apply to one application may match an application having appID for identifying the application. Accordingly the application to which the trigger and the AMT will apply may be found. The AMT will be described in detail below.

 appType which can be 8 bit integer can indicate the application format type. The default value can be 1 which can represent a TDO. Other values can represent other formats.

 appName which is attribute of the TDO element can be a human readable name which can be displayed to a viewer when a viewer s permission is sought to launch the application.

 globalID which is attribute of the TDO element can be a globally unique identifier of the application. In many cases a receiver will cache an app that is going to be used again before too long. In order for this to be useful the receiver must be able to recognize the app the next time it appears. A globalID is needed for the receiver to be able to recognize the app when it appears again in a new segment.

 appVersion which is attribute of the TDO element can be the version number of the application. The appVersion value can be incremented whenever the application as identified by the globalID changes. The appVersion attribute cannot be present if the globalID attribute is not present.

 cookieSpace which can be 8 bit integer can indicate how much space the application needs to store persistent data between invocations.

 frequencyOfUse which can be 4 bit integer can indicate approximately how frequently the application will be used in the broadcast to provide guidance to receivers on managing their application code cache space. frequencyOfUse will be described in detail below.

 expireDate which is attribute of the TDO element can indicate a date and time after which the receiver can safely delete the application and any related resources.

When present with value true testTDO which is Boolean attribute can indicate that the application is for testing purposes only and that it can be ignored by ordinary receivers.

The value true for availInternet attribute can indicate that the application is available for downloading over the Internet. The value false can indicate that the application is not available for downloading over the Internet. When the attribute is not present the default value can be true .

The value true for availBroadcast attribute can indicate that the application is available for extraction from the broadcast. The value false can indicate that the application is not available for extraction from the broadcast. When the attribute is not present the default value can be true .

Each instance of URL a child element of the TDO element can identify a file which is part of the application. URL element may include entry attribute. entry an attribute of the URL element has value true that can indicate that the URL is an entry point for the application i.e. a file that can be launched in order to launch the application. When it has value false that can indicate that the URL is not an entry point for the application. The default value when the attribute does not appear can be false . The URL element which is the child element of the TDO element identifies a file configuring the application as described above. The receiver parses the TPT to obtain URL information accesses the server using the URL information and downloads an application indicated by the URL information.

When present Capabilities which is child element of the TDO element can indicate capabilities that are essential for a meaningful presentation of this application. Receivers that do not have one or more of the required capabilities are expected not to attempt to present launch the application.

ContentItem a child element of the TDO element can indicate a content item including one or more data files that are needed by the application. ContentItem element has information about data files required by an application indicated by the TDO element to which this element belongs. The receiver may download data files required by the application using URL information etc. of ContentItem if the ContentItem element is present after parsing. The child element and attribute of ContentItem will be described below.

Event a child element of the TDO element can represent an event for the application. Event element indicates an event of an application to which this element belongs. The event element contains information indicating which events are present which data is present which action is present etc. The receiver may parse the event element to obtain information about the event of the application. The child element and attribute of the event will be described below.

The receiver may receive and parse the TPT to obtain the child element of the TDO and the information about attributes.

ContentItem element which is the child element of the TDO element may include updateAvail pollPeriod size availInternet availBroadcast attribute and or URL element.

Here URL element may include entry attribute. Each instance of URL a child element of the ContentItem element can identify a file which is part of the content item. URL element may include entry attribute. entry an attribute of the URL element has value true that can indicate that the URL is an entry point for the content item i.e. a file that can be launched in order to launch the content item. When it has value false that can indicate that the URL is not an entry point for the content item. The default value when the attribute does not appear can be false . The receiver may download data files required by the application using URL information of ContentItem after parsing. In this process the information such as the above described other attributes may be used.

 updatesAvail which is a boolean attribute of the ContentItem element can indicate whether or not the content item will be updated from time to time i.e. whether the content item includes static files or whether it is a real time data feed. When the value is true the content item will be updated from time to time when the value is false the content item will not be updated. The default value when this attribute does not appear can be false.

 pollPeriod which is an attribute of the ContentItem element may be present only when the value of the updatesAvail attribute is true . The presence of the pollPeriod attribute can indicate that short polling is being used to deliver Activation Triggers and the value of the pollPeriod attribute can indicate the recommended time in seconds for the receiver to use as a polling period.

The value true for availInternet attribute can indicate that the content item is available for downloading over the Internet. The value false can indicate that the content item is not available for downloading over the Internet. When this attribute is not present the default value can be true. 

The value true for availBroadcast attribute can indicate that the content item is available for extraction from the broadcast. The value false can indicate that the content item is not available for extraction from the broadcast. When this attribute is not present the default value can be true. 

The event element contains information about the event of the application indicated by the TDO element to which the event element belongs. The receiver may parse the event element to obtain information about the event.

The event element which is the child element of the TDO element may include eventID action destination diffusion attribute and or Data element. Here the data element may include dataID attribute.

 eventID which can be a 16 bit integer attribute of the Event element can identify the event uniquely within the scope of the TDO element containing it. An Activation Trigger or activation element in AMT can identify the target application and event for the Trigger by the combination of appID and eventID. When an event is activated receivers pass the event in to the application. eventID serves as an identifier of an event. Using eventID information a trigger AMT etc. for activating the event may match an application having eventID for identifying the event. That is an Activation Trigger or activation element in AMT can identify the target application and event for the Trigger by the combination of appID and eventID. When an event is activated receivers pass the event in to the application. The AMT will be described in detail below.

 action which is an attribute of the Event element can indicate the type of action to be applied when the event is activated. Allowed values can be prep exec susp and kill .

 prep can correspond to the Trig prep action. If the state of the targeted application is Released this action can cause a state change to Ready. 

 exec can correspond to the Trig exec action. The state of the targeted application can become Active upon reception of this trigger.

 susp can correspond to the Trig susp action. If the state of the targeted application is Active the state can change to Suspended upon reception of this trigger otherwise there is no change.

 kill can correspond to the Trig kill action. The state of the targeted application can become Released upon reception of this trigger.

 destination which is an attribute of the Event element can indicate the target device for the event. destination will be described in detail below.

When present diffusion which can be an 8 bit integer attribute of the Event element can represent a period T of time in seconds. The purpose of the diffusion parameter is to smooth peaks in server loading. The receiver can be expected to compute a random time in the range 0 T in increments of 10 milliseconds and delay this amount before accessing an Internet server to retrieve content referenced by URLs in the TPT.

When present Data which is a child element of the Event element can provide data related to the event. Different activations of the Event can have different Data elements associated with them. The data element may include dataID attribute. dataID which is a 16 bit integer attribute can identify the Data element uniquely within the scope of the Event element containing it. When an activation of an event has data associated with it the Activation Trigger can identify the Data element by the combination of AppID EventID and DataID. The data element indicates data used for the event. One event element may have several data elements. Data is identified using dataID attribute of the data element. In the receiver if the event related to the data is activated the Activation Trigger or activation element in AMT can identify the Data element by the combination of AppID EventID and DataID. AMT will be described in detail below.

The Meaning column indicates the frequency of occurrence of segments that contain this application. An attribute can appear multiple times within a single segment of course. The frequencyOfUse attribute cannot be present if the globalID attribute is not present. If the app is going to be cached and used again later the receiver needs to recognize that it is the same app when it appears again. This requires the globalId attribute.

As shown in the destination attribute value of 0 indicates reserved the destination attribute value of 1 indicates primary device only the destination attribute value of 2 indicates one or more secondary devices only 2 and the destination attribute value of 3 indicates Primary device and or one or more secondary devices.

This is the binary format of the above described TPT structure. This structure is a format necessary when the TPT is transmitted in NRT and is made such that the XML structure of the TPT is suitably transmitted in NRT.

The following elements and or attributes contained in the XML version of the TPT can be omitted from the binary version since they can be provided by the encapsulation header for delivering the binary table in the broadcast stream protocolVersion major minor serviceID and or tptVersion.

The semantics of the fields are as follows. Fields of the binary format of TDO parameter table of and will be sequentially described.

expire date included which can be 1 bit field can indicate whether the expire date field is included. The value 1 can mean it is included the value 0 can mean it is not included.

segment id length which can be a 5 bit field can indicate the length in bytes of the segment id field.

segment id which is a variable length field can contain the bytes of the segment id which can have the same semantics as the id attribute of the TPT XML format.

base URL which is a variable length field can contain the bytes of the base URL which can have the same semantics as the baseURL attribute of the TPT XML format.

When present expire date which can be a 32 bit field can indicate the date and time of the expiration of the information included in this TPT instance. If the receiver caches the TPT it can be re used until the expireDate. The unsigned integer can be interpreted as the number of GPS seconds since 00 00 00 UTC 6 Jan. 1980 minus the GPS UTC offset. The GPS UTC offset can be an 8 bit unsigned integer that defines the current offset in whole seconds between GPS and UTC time standards.

trigger server URL length which can be an 8 bit field can indicate the length in bytes of the trigger server URL field. When the value of this field is 0 it can indicate that internet delivery of individual Activation Triggers is not available.

trigger server URL when the value of the trigger server URL length field is not 0 can contain the bytes of the Trigger Server URL which can have the same semantics as the URL attribute of the LiveTrigger element of the TPT XML format.

trigger delivery type which can be a 1 bit field can indicate the delivery mode of individual Activation Triggers over the Internet. The value 0 can indicate that HTTP short polling is being used the value 1 can indicate that either HTTP long polling or HTTP streaming is being used.

poll period which can be an 8 bit integer can indicate the recommended number of seconds between polls when HTTP short polling is being used.

num apps in table which can be an 8 bit field can indicate the number of applications TDOs described in this TPT instance.

app id which can be a 16 bit field can contain an identifier for this application the application described in this iteration of the num apps in table loop . It can be unique within this TPT instance.

app type included which can be a 1 bit field can indicate whether the app type field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

app name included which can be a 1 bit field can indicate whether the app name field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

global id included which can be a 1 bit field can indicate whether the global id field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

app version included which can be a 1 bit field can indicate whether the app version field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

cookie space included which can be a 1 bit field can indicate whether the cookie space field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

frequency of use included which can be a 1 bit field can indicate whether the frequency of use field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

expire date included which can be a 1 bit field can indicate whether the expire date field is included for this application. The value 1 can mean it is included the value 0 can mean it is not included.

When present app type which can be an 8 bit field can indicate the format type of this application. The value 0 can indicate that the application is a TDO. If this field is not present the value can default to 0. Other values can represent other formats.

When present app name length which can be an 8 bit field can indicate the length in bytes of the app name field immediately following it. The value 0 for this field can indicate that no app name field is present for this application.

When present app name which is a variable length field can have the same semantics as the appName attribute of the TDO element in the TPT XML format.

When present global id length which can be an 8 bit field can indicate the length in bytes of the global id field immediately following it. The value 0 for this field can indicate that no global id field is present for this application.

When present global id which is a variable length field can have the same semantics as the globalld attribute of the TDO element in the TPT XML format.

When present app version which can be an 8 bit field has the same semantics as the appVersion attribute of the TDO element in the TPT XML format.

When present cookie space which can be an 8 bit field can have the same semantics as the cookieSpace attribute of the TDO element in the TPT XML format.

When present frequency of use which can be an 8 bit field can have the same semantics as the frequencyOfUse attribute of the TDO element in the TPT XML format.

When present expire date which can be an 8 bit field can have the same semantics as the expireDate attribute of the TDO element in the TPT XML format.

test app which can be a 1 bit field can indicate whether or not this application is a test application intended to be ignored by ordinary receivers. The value 1 can mean it is a test application the value 0 can mean it is not a test application.

available on internet which can be a 1 bit field can indicate whether or not this application is available via the Internet or not. The value 1 can mean it is available via the Internet the value 0 can mean it is not available via the Internet.

available in broadcast which can be a 1 bit field can indicate whether or not this application is available via the broadcast or not. The value 1 can mean it is available via the broadcast the value 0 can mean it is not available via the broadcast. number URLs which can be a 4 bit field can indicate the number of files that comprise this application.

URL which is a variable length field can have the same semantics as the URL attribute of the TDO element in the TPT XML format.

number content items which can be an 8 bit field can indicate the number of content items that are to be downloaded for use by this application.

updates avail which can be a 1 bit field can indicate whether this content item will be updated from time to time i.e. whether it a set of static files or a real time data feed. The value 1 can indicate that it will be updated the value 0 can indicate that it will not be updated.

avail internet which can be a 1 bit field can indicate whether the file s that comprise this content item can be downloaded via the Internet or not. The value 1 can mean that they are available for downloading via the Internet the value 0 can mean they are not available.

avail broadcast which can be a 1 bit field can indicate whether the file s that comprise this content item can be downloaded via the broadcast or not. The value 1 can mean that they are available for downloading via the broadcast the value 0 can mean they are not available.

content size included which can be a 1 bit field can indicate whether or not the content size field is included or not for this application. The value 1 can mean it is included the value 0 can mean it is not included.

number URLs which can be a 4 bit field can indicate the number of files that comprise this content item.

URL which is a variable length field can have the same semantics as the URL attribute of the ContentItem child element of the TDO element in the TPT XML format.

content size which can be a 24 bit field can have the same semantics as the contentSize attribute of the ContentItem child element of the TDO element in the TPT XML format.

num content descriptors which can be an 8 bit field can indicate the number of content descriptors in the descriptor loop immediately following it.

content descriptor which is a variable length field can be a descriptor conforming to the MPEG 2 descriptor format tag length data . It can provide additional information about this content item. Among the descriptors that may be included in this descriptor loop can be the Capabilities descriptor indicating receiver capabilities needed for a meaningful presentation of this content item.

event id which can be a 16 bit field can contain an identifier for this event the event described in this iteration of the number events loop . It can be unique within the scope of this application. The event can be referenced within Activation Triggers by the combination of app id and event id.

action which can be a 5 bit field can have the same semantics as the action attribute of the Event child element of the TDO element in the TPT XML format.

destination included which can be a 1 bit field can indicate whether or not the destination field is included for this event. The value 1 can indicate that it is included the value 0 can indicate that it is not included.

diffusion included which can be a 1 bit field can indicate whether or not the diffusion field is included for this event. The value 1 can indicate that it is included the value 0 can indicate that it is not included.

data included which can be a 1 bit field can indicate whether or not the data size and data bytes fields are included for this event. The value 1 can indicate that they are included the value 0 can indicate that they are not included.

When present the semantics of destination field can be the same as the semantics of the destination attribute of the Event child element of the TDO element in the TPT XML format.

When present the semantics of diffusion field can be the same as the semantics of the diffusion attribute of the Event child element of the TDO element in the TPT XML format.

When present the data size field can indicate the size of the data bytes field immediately following it.

When present the data bytes field can provide data related to this event. Whenever the event is activated the target application will be able to read the data and use it to help carry out the desired action. The content of this field can be identical to the content of the corresponding Data child element of the corresponding Event child element of the corresponding TDO element in the TPT XML format except that this field can contain the raw binary value and the Data element in the TPT XML format can contain a base64 encoding of the binary value.

num app descriptors which can be an 8 bit field can indicate the number of descriptors in the descriptor loop immediately following it.

app descriptor which is a variable length field can be a descriptor conforming to the MPEG 2 descriptor format tag length data . It can provide additional information about this application TDO . Among the descriptors that may be included in this descriptor loop is the Capabilities descriptor indicating receiver capabilities needed for a meaningful presentation of this application.

num TPT descriptors which can be an 8 bit field can indicate the number of descriptors in the descriptor loop immediately following it.

TPT descriptor which is a variable length field can be a descriptor conforming to the MPEG 2 descriptor format tag length data . It can provide additional information about this TPT. Among the descriptors that may be included in this descriptor loop is the Capabilities descriptor indicating receiver capabilities needed for a meaningful presentation of the interactive service represented by this TPT.

An Activation Messages Table AMT can contain the equivalent of the Activation Triggers for a segment. Under certain circumstances it can be delivered to receivers in lieu of Activation Triggers. A trigger can be delivered in the closed caption stream by ACR servers by a live trigger server and via AMT.

An Activation Messages Table AMT may include majorProtocolVersion minorProtocolVersion segmentId beginMT attribute and or Activation element.

 majorProtocolVersion which can be a 4 bit attribute of the AMT element can indicate the major version number of the AMT definition. The major version number can be set to 1. Receivers can be expected to discard instances of the AMT indicating major version values they are not equipped to support.

When present minorProtocolVersion which can be a 4 bit attribute of the AMT element can indicate the minor version number of the AMT definition. When not present the value can default to 0. The minor version number can be set to 0. Receivers can be expected to not discard instances of the AMT indicating minor version values they are not equipped to support. In this case they can be expected to ignore any individual elements or attributes they do not support.

 segmentID which is an identifier of the AMT matches the identifier of the TPT which contains the applications and events to which the Activations in this AMT apply. segmentId may serve as an identifier of the AMT. Accordingly the receiver may receive and parse the AMT to identify the AMT via segmentId information. segmentId contains information indicating to which segment the AMT applies matches id of the TPT related to the segment and serves to connect the AMT and the TPT. Further the segment may be identified to provide basic information necessary to identify the target TDO and the event of the activation element of the AMT.

When present beginMT which is an attribute of the AMT element can indicate the beginning Media Time of the segment for which this AMT instance provides activation times. beginMT may indicate beginning of the media time with respect to a segment to which the AMT will apply. Therefore it is possible to decide a criterion of a time when activation indicated by the activation element occurs. Accordingly if beginMT is present startTime attribute in the activation element may be influenced by the beginning of the media time indicated by beginMT.

Each instance of Activation element of the AMT can represent a command to activate a certain event at a certain time with certain data associated with the event. A plurality of activation elements may be present in the AMT. Each activation element performs a role similar to that of the activation trigger. The activation element may apply to the segment indicated by segmentId in the AMT. Attributes of the activation element may contain information about in which application activation occurs in which event activation occurs when activation occurs etc. Attributes of the activation element will be described in detail below.

The activation element may include targetTDO targetEvent targetData startTime and or endTime attribute.

 targetTDO which is an attribute of the Activation element can match the appID attribute of a TDO element in the TPT with which the AMT is associated thereby identifying the target application for the activation command. targetTDO may contain information to which application the activation element of the AMT applies. The receiver may receive and parse the AMT to obtain targetTDO and find appID in the TDO element of the matching TPT to identify the application to which the activation element will apply.

 targetEvent which is an attribute of the Activation element can match the eventID attribute of an Event element contained in the TDO element identified by the targetTDO attribute thereby identifying the target event for the activation command. targetEvent may contain information to which event of which application the activation element of the AMT applies. The receiver may receive and parse the AMT to obtain targetEvent and find eventID in the TDO element of the matching TPT to identify the event to which the activation element will apply.

 targetData which is an attribute of the Activation element can match the dataID attribute of a Data element contained in the Event element identified by the targetTDO and targetEvent attributes thereby identifying the Data that is to be associated with the target event when the activation command applies. targetData may identify data related to the target event when the activation command applies. The receiver may receive and parse the AMT to obtain targetData and find dataID in the event element of the TPT.

 startTime which is an attribute of the event element can indicate the start of the valid time period for the event relative to Media Time. Receivers can be expected to execute the command when Media Time reaches the value in startTime or as soon thereafter as possible. startTime may indicate a start time when the event occurs. This start time is based on the media time. The receiver may parse the AMT to obtain startTime information and confirm the time when the event occurs using startTime. The receiver may activate the event if the media time reaches the startTime based on the media time of the segment identified by segmentId. If startTime has been already elapsed the event may be activated as soon as possible.

When present endTime which is an attribute of the event element can indicate the end of the valid time period for the event relative to Media Time. The receiver can be expected to not execute the command when Media Time is past the value in endTime. endTime may indicate the end time of the event. If the media time reaches the endTime the receiver may not perform the event.

When a receiver is activating events according to the Activations in an AMT it can be expected to apply each activation at its startTime or as soon thereafter as possible for example in the case when a receiver joins the service and receives the AMT at some time after the startTime and before the endTime . If the action attribute of the event element in TPT is exec then the receiver can be expected to pass a TriggerEvent in to the target application. TriggerEvent will be described below in the part related to the API.

A URL List can contain certain URLs of potential use to a receiver. The URL list may include the following URLs etc.

2. URL of an NRT Signaling Server from which information about stand alone NRT services in the broadcast stream can be retrieved allowing a receiver to access those services even if it does not have access to delivery of NRT service signaling in the broadcast stream.

3. URL of a Usage Reporting Server to which usage reports can be sent for a virtual channel allowing a receiver to send in such reports even if it does not have access to delivery of this URL in the broadcast stream.

4. URL of the PDI Q Table for a virtual channel allowing a receiver to personalize the viewing experience even if it does not have access to the PDI Q Table delivered in the broadcast stream. The PDI Q Table is related to personalization for providing a service customized for the user in provision of the interactive service. It is possible to inquire the user about personalization via the PDI Q table. 

Among others the URL list may be made with respect to the UrsUrl element so as to further indicate the URL of the server for usage reporting in order to use preferred data and the type of content viewed and consumed currently through the receiver in business. The UrsUrl element included in the URL list may be variously interpreted as follows.

First in case of a usage reporting server the receiver may perform the usage reporting function of the receiver by a predetermined protocol e.g. data structure XML file etc. with the URL of the usage reporting server.

Second there may be a TDO executed on the web browser of the receiver. In this case this indicates the location of the Usage Reporting TDO. In this case the TDO may directly collect and report information about content stored in the receiver or consumed currently using the API e.g. file APIs or usage reporting APIs of the web browser of the receiver. The TDO may transmit the collected data using Javascript API called XMLHttpRequest.

URLlist may include UrlList TptUrl UrsUrl and or PdiUrl. The semantics of these elements is as follows.

TptUrl which is an element of the UrlList element can contain the URL of a TPT for a future segment in the current interactive adjunct service. When multiple TptUrl elements are included they can be arranged in order of the appearance of the segments in the broadcast.

NrtSignalingUrl which is an element of the UrlList element can contain the URL of a server from which receivers can obtain NRT signaling tables for all the virtual channels in the current transport stream.

UrsUrl which is an element of the UrlList element can contain the URL of a server to which receivers can send usage audience measurement reports for the current virtual channel.

PdiUrl which is an element of the UrlList element can contain the URL of the PDI Q table for the current virtual channel.

A description will be given of a delivery mechanism for delivering a trigger a TPT etc. Output from Interactive Service Creation Delivery of Triggers in the Broadcast Stream Delivery of Time base triggers via the Internet Delivery of Activation Triggers via Internet ACR Scenario Delivery of TPTs in Broadcast Stream Delivery of TPTs via Internet Moving TDOs and Content Items Combining Multiple Segments into One Segment will be sequentially described.

The process of service creation for a segment can result in folder containing all TDOs and other content items TPT file in XML format and AMT file in XML format. The other results may be created.

When delivered in the broadcast stream Triggers can be delivered in the DTV Closed Caption channel in Service 6 in the URLString command.

If the Trigger is less than or equal to 26 characters in length it can be sent non segmented Type 11 . If the Trigger is 27 to 52 characters in length it can be sent in two segments the first segment in a Type 00 segment and the second segment in a Type 10 segment .

For interactive services using the TDO model the URI type of the URI data structure can be set to 0 Interactive TV Trigger for TDO model . This delivery mechanism includes both Time base triggers and Activation Triggers.

In the case in which the time base trigger is delivered via a broadcast stream in closed caption service 6. if m term is absent Time base triggers can simply deliver URL of Signaling Server. And if m term is absent then t term must be absent from Activation triggers.

In the case in which the activation trigger is delivered via a broadcast stream in closed caption service 6. that is in the case of Trigger format with e term with or without t term if t term is present activation time can be the timestamp relative to a time base. And if t term is absent activation time can be the arrival time of the message.

In the case in which the time base trigger and the activation trigger are delivered via CC service 6 there can be three possible ways for broadcasters to handle Time Base and Activation triggers. The three ways are Segment mode without explicit time base Segment mode with explicit time base and Service mode with explicit time base .

In segment mode without explicit time base Activation messages include no time stamp so that the activation time of each message can be the delivery time of the message and Time Base messages also include no time stamp so that their only purpose can be to provide the URL of the Signaling Server that can deliver TPT files. Time Base messages can even be omitted entirely in this mode relying on the URL in the Activation messages to provide the URL of the Signaling Server but then receivers will not be able to retrieve a TPT and start downloading TDOs until after the first Activation message appears delaying the response to the first Activation message by quite a bit.

In this case Time Base messages that can appear in CC service 6 can contain the locator part of the Trigger format and possibly the spread term but no media time term and Activation messages that can appear in CC service 6 can contain the locator part of the Trigger format the event time term and possibly the spread term but with no t part in the event time term. The locator part of both Time Base and Activation messages can be the current segmentId. This URL can also be used to retrieve the TPT for the segment via the Internet.

In segment mode with explicit time base Time Base messages include a time stamp to define a time base and Activation messages might include a time stamp to define the activation time relative to the time base or they might include no time stamp indicating that the activation time is the arrival time of the message.

In this case Time Base messages that can appear in CC service 6 can contain the locator part of the Trigger format the media time term and possibly the spread term and Activation messages that can appear in CC service 6 can contain the locator part of the Trigger format the event time term and possibly the spread term with or without the t part in the event time term. The locator part of both Time Base and Activation messages can be the current segmentId and the time base is specific to the segment. This URL can also be used to retrieve the TPT for the segment via the Internet.

In service mode with explicit time base Time Base messages include a time stamp to define a time base and Activation messages might or might not include a time stamp. The time base can extend across multiple segments rather than being specific to a single segment. The locator part of the Time Base messages can be an identifier of the time base and also a URL that can be used to retrieve TPTs for the service via the Internet.

In any case the Trigger Insertion Server that inserts the triggers into CC service 6 should work from the AMT translating the Activation messages from the XML format in the AMT into the trigger format specified for delivery in CC service 6. In the case of an Activation element with no endTime attribute a single trigger can be inserted with activation time equal to the startTime attribute. In the case of an Activation element with both startTime and endTime elements a sequence of triggers can be inserted with same target. The first trigger in the sequence can have activation time equal to the startTime attribute the last trigger in the sequence can have activation time equal to the endTime attribute and there can be a fixed time interval between the activation times of the triggers in the sequence except that the interval between the next to last and last trigger in the sequence can be shorter . The length of this fixed time interval can be configurable.

When the Time Base and Activation messages are in segment mode the time base can be specific to the segment. It can start with the beginMT value at the beginning of the segment and run through the segment. The startTime and endTime values of individual Activations can be relative to the beginMT value. When the Time Base and Activation messages are in service mode the time base can span segments and the beginMT value for each segment can be adjusted to take account of the service time base and the broadcast schedule.

Internet delivery of Time base triggers can be useful in so called Automatic Content Recognition ACR situations where the recipient of the Time base triggers has no access to Closed Caption service 6. In these situations the receiver needs to use ACR in order to recognize video frames and synchronize the time base with them. In ACR situations Time Base messages can be obtained from watermarks or from ACR servers. In case of reception from the ACR server the Time Base messages are delivered as responses from an ACR server.

Activation messages can be delivered via short polling long polling or streaming but all of these can impose a lot of overhead on the receivers and the server. Activation messages can also be delivered in the form of an AMT but this can provide a good deal of information about the length of segments facilitating ad killers. There might be other alternatives.

In the case in which the activation message is delivered in the form of the activation trigger that is in case of Trigger format with e term with or without t term this may be delivered via HTTP short polling long polling or streaming.

When delivered via Internet Activation messages can be delivered using either or both of the mechanisms Individual Activation Trigger Delivery mechanism and Bulk Activation Trigger Delivery mechanism.

As described above when individual Activation Triggers are delivered via the Internet they can be delivered using HTTP short polling long polling or streaming. The format of the Activation Trigger can be exactly the same as when they are delivered via DTVCC service 6.

In case of short polling the polling period must be specified. In this period a short polling operation may be set using pollPeriod included in the TPT as described below.

When Internet delivery of Activation Triggers is available the URL attribute of the LiveTrigger element in the TPT can indicate the Activation Trigger Server which can deliver activation trigger. If the pollPeriod attribute of the LiveTrigger element is present in the TPT this can indicate that HTTP short polling is being used and it can indicate the polling period a receiver should use. If the pollPeriod attribute of the LiveTrigger element is not present in the TPT this can indicate that either HTTP long polling or HTTP streaming is being used.

Regardless of which protocol is being used the receiver can be expected to issue an HTTP request to the Activation Trigger Server with the query term 

If short polling is being used the response from the Activation Trigger Server can contain all the Triggers that have been issued within the time interval of length pollPeriod ending at . If more than one Activation Trigger is returned they can be separated by one or more white space characters. If no Activation Triggers are returned the response can be empty.

If HTTP long polling or HTTP streaming is being used the Activation Trigger Server can wait to return a response until the media time when an Activation Trigger would be delivered in the broadcast stream. At this time it can return the Activation Trigger.

If HTTP long polling is being used the Activation Trigger Server can close the session after returning an Activation Trigger. The receiver can be expected to immediately issue another request with an updated media time.

If HTTP streaming is being used the Activation Trigger Server can keep the session open after returning each Activation Trigger and it can deliver additional Activation Triggers over the session as the time arrives for them to be delivered.

In all cases the HTTP response can contain an HTTP Response Header Field of one of the following forms to signal the delivery mode 

The parameter can indicate the recommended interval between polls for the succeeding polls. The can be omitted.

When Activation Triggers are delivered via the Internet in bulk the Activation Triggers for a segment can be delivered via HTTP along with the TPT for the segment in the form of a multi part MIME message with the TPT as the first part of the message and an Activation Messages Table AMT as the second part of the message.

When delivered in the broadcast stream TPTs can be translated from their XML format into an equivalent binary NRT style signaling table format and encapsulated in NRT style private sections one TPT per table instance. The TPT for the current segment is always present. TPTs for one or more future segments may also be present. The TPT instance is defined by the value of its segment id field. For reference the binary format of the TDO parameter table was described above. Here NRT style private section may correspond to tpt section of .

In summary in order to transmit the binary structure of the TPT in NRT the TPT may have a section structure suitable for NRT transmission. Hereinafter this process will be described in detail.

Each TPT can be encapsulated in NRT style private sections by dividing each TPT into blocks and inserting the blocks into the tpt bytes fields of sections that have a common value of table id protocol version TPT data version and sequence number fields. The blocks can be inserted into the sections in order of ascending section number field values. The private sections can be carried in the Service Signaling Channel SSC of the IP subnet of the virtual channel to which the TPT pertains. Here Service Signaling Channel is defined in the ATSC NRT standard and means a channel having a specific IP address and a port number. The sequence number fields in the sections can be used to distinguish different TPT instances carried in the same SSC.

The private section tpt section may include table id protocol version sequence number TPT data version current next indicator section number last section number service id and or tpt bytes information.

table id which can be an 8 bit field can identify this table section as belonging to a TDO Parameters Table instance.

protocol version may be divided into two parts. The high order 4 bits of this 8 bit unsigned integer field can indicate the major version number of the definition of this table and the TPT instance carried in it and the low order 4 bits can indicate the minor version number. The major version number can be set to 1. Receivers can be expected to discard instances of the AMT indicating major version values they are not equipped to support. The minor version number can be set to 0. Receivers can be expected to not discard instances of the AMT indicating minor version values they are not equipped to support. In this case they can be expected to ignore any descriptors they do not recognize and to ignore any fields that they do not support.

sequence number can be an 8 bit field. The value of sequence number can be the same as the sequence number of all other sections of this TPT instance and different from the sequence number of all sections of any other TPT instance in this Service Signaling Channel. Accordingly this field may perform a role different from that of the other TPT instance. sequence number field may indicate an IP subnet associated with a service signaling channel in this section. The values of the sequence number fields of the different TPT instances can reflect the order in which the segments appear in the broadcast stream.

TPT data version which can be a 5 bit field can indicate the version number of this TPT instance where the TPT instance can be defined by its segment id. Since the TPT version is known in advance in order to determine whether the received TPT section data is a new version TPT the TPT data version field may be present in the section table. The version number can be incremented by 1 modulo 32 when any field in the TPT instance changes.

current next indicator which can be a 1 bit indicator can always be set to 1 for TPT sections indicating that the TPT sent is always the current TPT for the segment identified by its segment id.

section number which can be an 8 bit field can give the section number of this TPT instance section where the TPT instance can be identified by its segment id. The section number of the first section in an TPT instance can be 0x00. The section number can be incremented by 1 with each additional section in the TPT instance.

last section number which can be an 8 bit field can give the number of the last section i.e. the section with the highest section number of the TPT instance of which this section is a part.

service id which can be a 16 bit field can specify the service id associated with the interactive service offering the content items described in this table instance.

tpt bytes which is a variable length field can include a block of the TPT instance carried in part by this section. When the tpt bytes fields of all the sections of this table instance are concatenated in order of their section number fields the result can be the complete TPT instance.

That is after the binary format of the TPT is used or the XML format is changed to a binary format the TPT may be divided to be suitable for NRT transmission included in tpt bytes field of the private section and transmitted in NRT. At this time if one TPT is divided into several private sections the private section may have the same table id protocol version TPT data version and sequence number value. The divided TPT blocks may be inserted in order of section number field values.

The receiver may parse the received private sections. In order to combine the private sections into one TPT again the private sections having the same table id protocol version TPT data version and sequence number values may be used. At this time order information capable of being obtained from section number and last section number information may be used. If tpt bytes of all private sections having the same table id protocol version TPT data version and sequence number values are sequentially connected one TPT may be created.

Networks and stations will often need to provide their own HTTP servers for delivering TDOs and content items files used by TDOs. When this is done the baseURL in the TPT can be adjusted to reflect the location of the server.

In order to thoroughly obfuscate boundaries between segments the TPTs and AMTs for multiple segments can be combined into a single TPT and AMT. The following steps may be performed.

3. If any of the segments being combined have live activations provide a relay server that provides access to all of them and put the parameters for this server in the LiveTrigger element.

4. Apply the baseURL for each segment as needed to get the full TDO and ContentItem URLs. It may be possible to identify a shorter baseURL that is common to all the segments being combined and retain that as a baseURL for the combined segment. 

9. Adjust the targetId values of all the Activation elements in the AMT files for the segments being combined to reflect any changes in appId values.

10. Adjust the startTime and endTime values of all the Activation elements in the AMT files for the segments being combined to reflect the new beginMT value and the broadcast schedule for the segments being combined.

When delivered over the Internet TPTs can be delivered via HTTP. The URL of the TPT for the current segment can be the in Time Base messages. The response to a request for a TPT can include just the TPT or it can include a 2 part MIME message with the requested TPT in the first part and a list of URLs in the second part encoded as an XML document. The response to a request will always include the TPT for the current segment. It may include TPTs for one or more future segments as well. 

 TptUrl can contain the URL of a TPT for a future segment. When multiple TptUrl elements are included they can be arranged in order of the appearance of the segments in the broadcast.

 NrtSignalingUrl can contain the URL of a server where receivers can obtain NRT signaling tables for all the virtual channels in the current broadcast stream.

In order to support synchronization of Declarative Object actions to broadcast programming additional methods can be supported for the video broadcast object.

If the TPT is received via the DTVCC or the Internet several events for executing the TDO may be present in the TPT and these events may be activated by the activation trigger.

In order to process this event a Listener function may be registered on a per eventID basis. Accordingly as the above described additional methods the two functions addTriggerEventListener and removeTriggerEventListener for registering the Listener function may be present.

addTriggerEventListener function can register a callback function listener function for processing an event generated on a per eventId basis. The addTriggerEventListener function may receive the listener of EventListener type and eventId of Number type as argument. The eventListener type will be described below. The addTriggerEventListener function may not have a return value void . Here eventId argument may be event ID in the event element of the TPT. Here listener argument may be a listener for the event.

The trigger processing module of the receiver may register the listener function on a per eventId basis using the addTriggerEventListener function as soon as the activation message is received. If the event is activated the registered listener function may be called. At this time the object of TriggerEvent type may be delivered to the listener function. TriggerEvent type will be described below.

The removeTriggerEventListener function can cancel registration of a callback function listener function for processing an event generated on a per eventId basis. The removeTriggerEventListener function may receive the listener of EventListener type and eventId of Number type as argument. The eventListener type will be described below. The removeTriggerEventListener function may not have a return value void . Here eventId argument may be event ID in the event element of the TPT. Here listener argument may be a listener for the event.

In the javascript program if the event which may be generated on a per eventId basis is desired to be no longer received or if the program DestroyWindow is finished the listener function registered using removeTriggerEventListener may be cancelled.

Here the definition of the EventListener type conforms to Web Interface definition Language Weg IDL . Web IDL can be used to describe interfaces that are intended to be implemented in web browsers. Web IDL is an IDL variant with a number of features that allow the behavior of common script objects in the web platform to be specified more readily.

EventListener may be an interface object. EventListener type may have an event of TriggerEvent type as an argument.

TriggerEvent type may have eventId data and status as properties. Here eventId may be eventID in the event element of the TPT. Here data may be data for this activation of the event. Here data may be hexadecimal. Here status may mean the status of the event. Here if the status value is trigger this means a status in which the event is activated by the activation trigger. If the status value is error this means a status in which error occurs.

In the Direct Execution model a Declarative Object DO can be launched automatically as soon as the virtual channel is selected. It can communicate over the Internet with a backend server to get detailed instructions for providing interactive features creating displays in specific locations on the screen conducting polls launching other specialized DOs etc. all synchronized with the audio video program.

In the direct execution model an application is launched automatically as soon as the virtual channel is selected. Application can communicate over the Internet with a backend server via a Synchronized Content Protocol . The server can give detailed instructions for providing interactive feature which is all synchronized with the audio video program.

In case of the direct execution model since an application is immediately executed information may be delivered to the currently executed application as a time base trigger is delivered. In this model the application needs to continuously deliver information about currently broadcast content to the server for synchronization. To this end the time base trigger may further include special information different from that of the TDO model. This special information may be an identifier of currently broadcast content.

Similarly the content identifier may be present in the parameter part of the trigger in the form of a parameter.

Similarly the content identifier may be present in media time of the trigger in the form of one term. The content identifier term which can be called content id which can be designated by c followed by a character string can represent an identifier for the content currently being viewed.

The content id term can be intended to support the Direct Execution model of interactive service implementation.

As described above in this model Time base triggers with content id term can be passed in to the application after it is launched and the application can deliver the content id to the backend server in order to identify the context for the interaction. Detailed operation thereof will be described below.

The delivery mechanism of the trigger in the direct execution module is equal to that described above.

However in case of Delivery of Triggers in the Broadcast Stream Triggers can be delivered in the DTV Closed Caption channel in Service 6 in the URLString command. And for interactive services using the Direct Execution model the URI type field can be set to 2 Interactive TV Trigger for Direct Execution model .

As one model for executing interactive service in the direct execution model an application can be launched automatically as soon as the virtual channel is selected. The application can communicate over the Internet with a backend server via a Synchronized Content Protocol. The server can give detailed instructions for providing interactive features creating displays in specific locations on the screen conducting polls launching other specialized DOs etc. all synchronized with the audio video program.

First of all an application can be launched. Then a time base trigger is received. The time base trigger is delivered to the application after the application has been executed. The content id term of the time base trigger may include content identification information of currently displayed content. The application can deliver the content id to the backend server in order to identify the context for the interaction and in order to identify the content currently being viewed.

Protocols and architecture enabling acquisition of an interactive service in environments for example as received from a cable or satellite set top box in which only uncompressed video and audio are accessible are defined. The architecture and protocols can be designed for use by receivers that have Internet connections and that only have access to the uncompressed audio and video from the broadcast stream. Of course the architecture and protocols can be used successfully if the interactive service provider chooses to support the same.

The architecture can be designed to support two basic approaches to identifying the content being viewed so that any associated interactive service data enhancements can be delivered via Internet. Two basic approaches can be watermarking and fingerprinting.

In both the watermarking and fingerprinting approaches the intent can be to allow receivers to find out what programming is currently being watched and obtain a URL that can be used as the starting point to get additional information about interactive services for the programming.

In an architecture for a WM approach the architecture may include a broadcaster a watermark inserter an MVPD an STB a receiver a WM client a TPT server and or a content server .

The broadcaster may be a source outputting audio video streams and interactive services related to the audio video streams. A TV station may be an example of the broadcaster . The broadcaster may be a broadcast content producer or distributor. The broadcaster can deliver broadcast streams audio video content interactive data broadcast schedules or AMT.

The watermark inserter can insert watermarks into broadcast audio video frames. The watermark inserter may be integrated with the broadcaster or may be a separate module. Watermarks may be information necessary for receivers. Watermarks may be information such as URL. Watermarks will be described in detail later.

The MVPD is an abbreviation for multiprogram video program distributor. The MVPD may be a cable operator a satellite operator or an IPTV operator. The MVPD can receive the broadcast stream from the Broadcaster Watermark Inserter with the watermarks inserted by the Watermark Inserter in the case of a watermarking ACR system. MVPD often strips out all the program elements other than audio and video tracks and sends the resulting stream to set top boxes STBs in customer premises.

The STB typically decodes decompresses the audio and video and sends the same to a TV set for presentation to viewers. The STB can send uncompressed audio video content to the receiver . The STB may be an external decoding unit according to an embodiment of the present invention.

The receiver may include the WM client . The WM client may be disposed outside the receiver . Here the receiver may be watermark capable. The structure of the receiver will be described later.

The WM Client can obtain Activation Triggers from the ACR Server not shown and passes the same into the main receiver code using an API provided for such purpose. Normally the WM Client would be built into the receiver but other configurations are possible. The WM client can extract inserted watermarks from uncompressed audio video content. Watermarks may be information such as a URL.

The TPT server may be a server capable of downloading an application such as a TPT. The receiver transmits the extracted watermarks to the ACR server. When the watermarks are matched to watermarks stored in a database not shown the receiver can receive a trigger or triggers as a response. When the received trigger or triggers have the above described new locator part or a TPT or application parameter table of a new version is discovered the receiver may request the TPT server to download a new TPT or application parameter table.

The content server may provide applications and TDO necessary to provide interactive services. When a new application or TDO is needed the new application can be downloaded using a URL in a TPT or application parameter table.

In the watermarking WM approach the broadcaster watermark inserter can insert watermarks into the broadcast audio or video frames. These watermarks can be designed to carry a modest amount of information to receivers while being imperceptible or at least minimally intrusive to viewers. Such watermarks might provide directly the information that receivers need or they might only provide a code value that receivers can send via an Internet connection to a remote server in order to get the information they need.

In the architecture for FP approach the architecture may include a broadcaster an MVPD an STB a receiver an FP client a TPT server a content server a signature extractor and or an FP server .

The broadcaster may be a source outputting audio video streams and interactive services related to the audio video streams. A TV station may be an example of the broadcaster . The broadcaster may be a broadcast content producer or distributor. The broadcaster can deliver broadcast streams audio video content interactive data broadcast schedules or AMT.

The MVPD is the abbreviation for multiprogram video program distributor. The MVPD may be a cable operator a satellite operator or an IPTV operator. The MVPD often strips out all the program elements other than audio and video tracks and sends the resulting stream to set top boxes STBs on customer premises.

The STB typically decodes decompresses the audio and video and sends the same to a TV set for presentation to viewers. The STB can send uncompressed audio video content to the receiver . The STB may be an external decoding unit according to an embodiment of the present invention.

The receiver may include the FP client . The FP client may be disposed outside the receiver . Here the receiver may be fingerprint capable. The structure of the receiver will be described later.

The FP Client can obtain Activation Triggers from the FP Server and passes them into the main receiver code using an API provided for such purpose. Normally the FP Client would be built into the receiver but other configurations are possible. The FP client can extract a fingerprint from uncompressed audio video content. The fingerprint will be described in detail later.

The TPT server may be a server capable of downloading an application such as a TPT. The receiver transmits the extracted fingerprint to the FP server . When the fingerprint is matched to a signature of the signature extractor the receiver can receive a trigger or triggers as a response. When the received trigger or triggers have the above described new locator part or a TPT or application parameter table of a new version is discovered the receiver may request the TPT server to download a new TPT or application parameter table.

The content server may provide applications and TDO necessary to provide interactive services. When a new application or TDO is needed the new application can be downloaded using a URL in a TPT or application parameter table.

The signature extractor may receive metadata from the broadcaster . The signature extractor may extract the signature of a frame from the received metadata. When the fingerprint transmitted to the FP server matches the signature of the signature extractor the signature extractor can deliver the metadata related to the signature to the FP server .

The FP server may perform signature matching operation with the signature extractor . The FP server can match the signature to the fingerprint received from the receiver . When the signature is matched to the fingerprint the FP server can receive the metadata related to the signature from the signature extractor . The FP server can transmit the metadata to the receiver .

In the fingerprinting FP approach the FP Client can extract fingerprints also can be called signatures from audio or video frames and check the fingerprints against a database of fingerprints of broadcast frames from multiple broadcasters in the area to find the information the receivers need. Such checks can be done by signatures to a remote server and getting back a record with the desired information or in some cases they can be done by checking against a database of signatures that has been downloaded into the receiver . Here the remote server may be the FP server .

Although watermarking and fingerprinting can be distinct technologies they are not necessarily exclusive of one another. Using a combination of the two technologies is quite conceivable. The term automatic content recognition ACR can be used to refer to either of these technologies separately or to any combination thereof.

An environment in which a receiver only has access to the uncompressed audio and video from the broadcast stream is called an ACR environment. 

In both WM and FP cases receivers can use the URL as a starting point to obtain interactive service content including triggers.

In both WM and FP cases the timing information can be in the form of a timestamp relative to a broadcast side clock that is used for specification of the timing of time critical events for the channel such as activation timestamps in triggers delivered over the Internet.

It is assumed that broadcasters can typically support delivery of interactive services directly in the broadcast stream for the benefit of receivers that get TV signals from antennas and also support delivery of interactive services over the Internet as described above for the benefit of receivers that get uncompressed audio and video but have an Internet connection. However broadcasters can support either one of these two delivery mechanisms without the other.

A typical architecture for the watermarking approach in the case when the watermark provides only a code value would look something like a combination of the two architectures in and . There would be a Watermark Inserter as in but it would insert a code rather than the information needed by receivers. There would also be a WM Server playing much the same role as the FP Server in . Receivers would send it codes rather than signatures and they would get back the information they need.

Description of the accessing interactive services includes descriptions of Direct Execution Model TDO Model with Activations Independent of ACR Server TDO Model with Activations received from ACR Server. While the models are not shown the models are not limited to the descriptions and may be changed according to the intention of a designer.

There are a number of different ways for a receiver in an ACR environment to access interactive services depending on broadcaster choices and the nature of the ACR system. The interactive service model can be the Direct Execution model or the TDO model and Activation In the case of the TDO model Triggers can be delivered independently of the ACR Server or they can be delivered by the ACR Server.

An ACR process for a virtual channel that contains an interactive service which has the Direct Execution Model can provide to receivers viewing that channel the equivalent of Time Base Triggers that include the media time m term and the content id c term. These Triggers can be identified as Triggers for an interactive service with the Direct Execution model.

When a receiver first receives such a Trigger with a new locator part it can be expected to load into its browser the Declarative Object DO pointed to by the locator part of the Trigger. Typically the DO will have been pre installed or previously downloaded and cached. Otherwise the receiver can be expected to download the same using an HTTP GET request.

Then the DO can contact the appropriate back end server and provide the interactive service as directed by the back end server.

The receiver can be expected to make that initial Trigger and subsequent Triggers available to the DO as they are obtained until such time as it gets a Trigger from the ACR server that has a new locator part and or that is identified as a Trigger for an interactive service with the TDO model either of which typically indicates a channel change .

An ACR process for a virtual channel that can contain an interactive service which has the TDO model and which provide event activations independently of the ACR Server can provide to receivers viewing that channel the equivalent of Time Base Triggers that can include the media time m term. These Triggers can be identified as Triggers for an interactive service with the TDO model.

When a receiver first receives such a Trigger with a new locator part it can be expected to retrieve the current TDO Parameters Table TPT from the TPT Server can be pointed to by the locator part of the Trigger and to use the media time in that Trigger and subsequent Triggers to establish a reference time base for event activations relative to the audio or video frames can be identified by the ACR process.

If an Activation Messages Table AMT is delivered along with the TPT the receiver can be expected to use the individual Activation elements in the table to activate events at the correct times relative to the time base established by the media time terms in the Triggers. These events can include loading and executing a TDO causing a TDO to take a particular synchronized action suspend a TDO etc. 

If a LiveTrigger element is included in the TPT the receiver can be expected to retrieve Activation Triggers from the Live Trigger Server identified by the URL in the LiveTrigger element using the polling method signaled in the LiveTrigger element and to use these Activation Triggers to activate events at the correct times relative to the time base established by the media time terms in the Triggers.

Both an AMT and a Live Trigger Server can be used for the same service typically with the former providing static activations and the latter providing dynamic activations. Alternatively an AMT can be used alone when all activations for the segment are static or a Live Trigger Server can be used alone to deliver both static and dynamic activations.

How activation triggers for a TDO interactive service model are delivered without a separate trigger server in an ACR environment is described.

Fingerprinting ACR systems can include an ACR server. Receivers can send frame signatures to an ACR server and the ACR server can identify the frame represented by the signature and send back the information needed by the receivers. Watermarking ACR systems can include an ACR server in the case when the watermarks include no more that codes that can be sent to an ACR server to get the information needed by receivers. Watermarking ACR systems may not include an ACR server in the case when the watermarks themselves contain the information needed by receivers. In those ACR systems that include an ACR server two different models can be used for communication between the ACR servers and receivers a request response model and an event driven model.

Three cases of an ACR server using a request response model an ACR server using an event driven model and a watermarking ACR system inserting information directly may be assumed.

In the case of an ACR server the ACR method could be fingerprinting in which case receivers compute some sort of signature or fingerprint of audio or video frames and submit the same to an ACR server for identification or it could be watermarking in which case receivers extract codes in the form of watermarks from the audio or video frames and submit the codes to an ACR server for identification.

Terms of fingerprinting signatures are described for convenience. However the system operates in the same manner as the case of watermarking codes and the present invention is not limited to fingerprinting.

In the request response ACR model the receiver can be expected to generate signatures of the content periodically e.g. every 5 seconds which is merely exemplary and can be changed by a designer and send requests containing the signatures to the ACR server. When the ACR server gets a request from a receiver it can return a response. The communications session may not kept open between request response instances. In this model it may not be feasible for the ACR server to initiate messages to the client.

For an ACR server that is using this request response model and is delivering Activation Triggers to receivers each response from the ACR server can be one of Null Time Base Trigger and Activation Trigger.

A Null response can indicate that the signature is not recognized or if the ACR Ingest Module includes signatures for frames in program segments with no interactive service that the signature represents a frame which belongs to a segment that does not have an interactive service associated therewith. The ACR ingest module will be described below.

A Time Base Trigger response can indicate that no event activation is scheduled to take place before the client s next request. The client can be expected to use the Time Base Triggers to maintain a media time clock.

An Activation Trigger response can indicate that an activation is due to take place soon with the time of the activation indicated by the t term in the Trigger.

Whenever a receiver gets a Trigger with a new locator part it can be expected to download the new TPT immediately unless it has already retrieved the same using a URLList delivered with a previous TPT.

Whenever a receiver obtains an Activation Trigger it can be expected to activate the event at the time indicated by the t term in the Trigger relative to the media time clock.

In the receiver can send signatures for frames which the ACR server determines to have media times MT1 MT2 and MT3. For the frame with media time MT1 the receiver simply obtains a response that contains a Time Base Trigger. For the frame with media time MT2 a static activation is due at media time MTa so the receiver obtains a response that contains an Activation Trigger which has a t MTa term. For the frame with media time MT3 the receiver just obtains a response that contains a Time Base Trigger.

It can happen that a receiver receives more than one Activation Trigger for the same event activation. However the media times for each of them will be the same so the receiver can identify them as duplicates and only apply one of them.

In the receiver can be sending signatures for frames viewed at local clock times LC1 LC2 LC3 etc. The media time for the frame viewed at local clock time LC1 can be determined by the ACR server to be MT1 and the receiver just gets a response that contains a Trigger with no media time or event time. The media time for the frame viewed at local clock time LC2 can be determined by the ACR server to be MT2 and the ACR server knows that a static activation is due at media time MTa so the ACR server sends a response that contains an Activation Trigger which has a d term meaning that the media time MTa for the activation is time units after MT2. The receiver then adds the to time LC2 and gets LCa as the local time it should activate the event.

A description will be given of a case in which dynamic activation occurs in the request response ACR case.

For dynamic activations in situations when the ACR System does not learn of the event activation until it is too late to send the Trigger to the receiver ahead of time the ACR Server needs to wait until the next request and then sends an Activation Trigger. illustrates this case. The effect of this is that dynamic activations can be delayed by as much as one request interval.

In the receiver can be sending signatures for frames that the ACR server determines to have media times MT1 MT2 and MT3. For the frames with media times MT1 and MT2 the receiver just gets a response that contains a Time Base Trigger. When a dynamic activation with activation time MTa shows up at or shortly before media time MTa the ACR server cannot notify the receiver about it until the next request from the receiver which occurs for the frame with media time MT3. At that time the ACR server response contains an Activation Trigger with activation time MTa which is a little in the past . In this situation the receiver can be expected to apply the Activation Trigger as soon as it arrives.

Here again it is possible that a receiver receive more than one Activation Trigger for the same event activation. However the media time for each of them will be the same so the receiver can identify them as duplicates and only apply one of them.

A description will be given of a case in which dynamic activation occurs in the request response ACR case.

In the receiver can send signatures for frames viewed at local clock times LC1 LC2 LC3 etc. The media time for the frame viewed at local clock time LC1 can be determined by the ACR server to be MT1 and the receiver just gets a response that contains a Trigger with no media time or event time. The media time for the frame viewed at local clock time LC2 can be determined by the ACR server to be MT2 and the ACR server does not know that a dynamic activation will show up at media time MTa so the receiver just gets a response that contains a Trigger with no media time or event time. When a dynamic activation shows up at media time MTa the ACR server cannot notify the receiver about it until the next request from the receiver which occurs at local time LC3. At that time the ACR server response can contain an Activation Trigger with a negative value or contains a do it now activation trigger.

In the event driven ACR model the receiver can be expected to initiate a permanent connection to the ACR server generate signatures of the content periodically e.g. every 5 seconds and submit the signatures over the connection. The ACR server does not respond to each signature. It can send a message to the receiver when a new segment is detected or when an event activation needs to be communicated to the receiver. In this model it is possible for the ACR server to initiate messages to the client at any time.

For an ACR server that is using this event driven model and is delivering activations to receivers the following rules can apply for messages from the ACR server.

First of all when the ACR server receives a signature from a receiver that corresponds to a new segment the ACR server can send a Time Base Trigger to the receiver immediately just to enable the receiver to obtain the associated TPT.

Second of all whenever an event is due to be activated the ACR server can send an Activation Trigger to the receiver. If possible it can send the Activation Trigger slightly ahead of the time when the receiver needs to apply the same. This is very similar to the behavior in the request response model. If the ACR server learns of the activation so late that it cannot send an Activation Trigger very much ahead of time which can happen in the case of a dynamic event activation it still can send an Activation Trigger as soon as it can. In this latter case it is possible that the client will get the message slightly after the activation time because of message delays in which case the receiver can be expected to activate the event immediately upon receipt of the message.

Whenever a receiver gets a Trigger with a new locator part it can be expected to download the new TPT immediately unless it already retrieved it using a URLList delivered with a previous TPT.

A description will be given of a watermarking ACR system inserting information directly. While the watermarking ACR system is not shown the watermarking ACR system is not limited to the following description and may be changed by a designer.

In the case of a watermarking system that inserts the information receivers need directly the watermark associated with a frame can follow the same rules as stated above for what a request response ACR server would return for that frame as follows. The request response ACR server can return one of Null Time Base Trigger and Activation Trigger.

A Null response can indicate that the signature is not recognized or if the ACR Ingest Module includes signatures for frames in program segments with no interactive service that the signature represents a frame which belongs to a segment that does not have an interactive service associated with it.

A Time Base Trigger response can indicate that no event activation is scheduled to take place before the client s next request. The client can be expected to use the Time Base Triggers to maintain a media time clock.

An Activation Trigger response can indicate that an activation is due to take place soon with the time of the activation indicated by the t term in the Trigger.

In the case of a watermarking ACR system that is delivering the information receivers need by including the same directly in the watermarks so that no ACR server is needed an Ingest Module can follow the same rules as described for the request response server model above to determine the Trigger to associate with each frame but then include the Trigger in the watermark for the frame rather than associate the Trigger with the frame in a Database. The ingest module and database will be described later.

A description will be given of support of stand alone NRT services. This is not shown but the present invention is not limited to the following description and may be changed by a designer.

In order for a receiver in an ACR environment to obtain access to stand alone NRT services the broadcaster may need to support Internet access to the NRT services and the receiver may need to obtain the SMT and the NRT IT instances for the services.

A description will be given of a query protocol for obtaining PSIP tables and NRT tables over the Internet.

If a broadcaster supports this protocol for a particular broadcast stream then a receiver that knows the URL of the broadcaster s Signaling Server for that broadcast stream can take the following steps.

First the receiver can issue a query for the Basic NRT Set of tables for the broadcast stream for a specified future time interval for example the next 12 hours .

Second This will produce the SMT and ILT for each of the stand alone NRT virtual channels and the NRT IT and TFT instances covering the specified time interval.

One way a receiver can discover the URL of the Signaling Server for a broadcast stream can be that the provider of an interactive service segment in the broadcast stream can choose to provide the Signaling Server URL in a URLList element delivered along with the TPT.

Another way a receiver can discover URLs of Signaling Servers can be by pre configuration. In the same way that a DTV receiver manufacturer can pre configure a DTV receiver to know how to find an ACR Server covering any particular broadcast area a DTV receiver manufacturer can pre configure a DTV receiver to know how to find an NRT Discovery Server covering any particular broadcast area. Such an NRT Discovery Server would be able to give the receiver a list of the broadcast streams that contain stand alone NRT services along with the Signaling Server URL for each one.

Some ACR systems include an ACR server and some ACR systems do not. In fingerprinting ACR systems receivers can compute and send frame signatures to an ACR server and the ACR server can send back the information needed by the receivers. Thus fingerprinting ACR systems include an ACR server. In watermarking ACR systems the watermarks may contain only codes that uniquely identify the frames or the watermarks may contain the full information needed by receivers. When the watermarks contain only codes receivers can extract the codes and send the same to an ACR server and the ACR server sends back the information needed by the receivers. In the case when the watermarks include the full information receivers can just extract the information they need directly from the watermarks and no ACR server is needed.

In those ACR systems that include an ACR server two different models can be commonly used for communication between the ACR servers and receivers a request response model and an event driven model.

In the request response ACR server model the receiver can be expected to compute signatures of or extract codes from the content periodically e.g. every 5 seconds and send requests containing the signatures or codes to an ACR server. When an ACR server gets a request from a receiver it can return a response. The communications session is not kept open between request response instances. In this model it may not feasible for an ACR server to initiate messages to a receiver.

It is assumed that the broadcaster of the channel being processed is supporting the TDO interaction model.

There can be two general type of event activations static activations in which the activation time is known before the broadcast of the segment begins and dynamic activations in which the activation time in determined dynamically as the segment is being broadcast. In pre recorded segments all of the event activations can be static. In segments that are broadcasting live shows some or all of the event activations can be dynamic. Static activations are typically listed in the Activation Messages Table AMT although they might be delivered to receivers in the form of Activation Triggers. Dynamic activations can be delivered in the form of Activation Triggers since their timing is not known at the time the AMT is generated.

In the architecture to support ACR systems that use an ACR server the architecture may include a broadcast source an ACR ingest module an MVPD an STB a receiver an ACR client an ACR configuration server an ACR server and or a database .

The Broadcast Source can be a point from which the A V stream and associated interactive services are transmitted for example a network distribution point or a TV station.

The ACR Ingest Module can compute signatures fingerprints of frames in the case of a fingerprinting ACR system or insert watermarks including codes into frames in the case of a watermarking ACR system that is based on codes. It can store in the database the media time of each frame associated with a signature or code together with other metadata. The ACR Ingest Module could handle a single channel in a broadcast stream or an entire broadcast stream or multiple broadcast streams or any combination thereof. For the purposes it is assumed that the ACR Ingest Module processes frames for program segments that contain an interactive service. However it is possible to have ACR systems in which all frames are processed but those that are not part of a segment with an interactive service have an indication in their database entry that they are not part of a segment with an interactive service.

A Multiprogram Video Program Distributor MVPD is typically a cable operator satellite operator or IPTV operator. It can receive the broadcast stream from the Broadcast Source in some way with the watermarks inserted by the ACR Ingest Module in the case of a watermarking ACR system such a system often strips out all the program elements other than audio and video tracks and sends the resulting stream to set top boxes STBs on customer premises.

The STB typically decodes decompresses the audio and video and sends the same to a TV set for presentation to viewers. We are assuming that DTV Closed Caption service 6 which contains interactive service Triggers is not available to the TV Set.

The receiver may include the ACR client . The ACR client may be disposed outside the receiver . The structure of the receiver will be described later.

The ACR Client in the receiver can obtain Activation Triggers from the ACR Server and pass the same to the main receiver code using an API provided for that purpose. Normally the ACR client would be built into the receiver but other configurations are possible.

The ACR Configuration Server can provide a way for ACR clients to determine the location of a suitable ACR Server . This discovery process can be achieved in other ways.

The ACR Server can obtain signatures or codes from receivers and return Activation Triggers at appropriate times.

The database can be a data store of some kind not necessarily a database in the strict sense of the term in which information about audio or video frames or both is stored for the use of ACR servers .

The architecture of an ACR system that uses direct delivery of information in watermarks could have no Database and no ACR Server. The ACR Ingest Module could insert information directly into the frames in the broadcast stream in the form of watermarks instead of inserting into a database records that contain identifiers of frames and the information associated with the same. Receivers could then extract this information from the frames in the broadcast instead of obtaining the same from an ACR server.

A description will be given of delivery of activation triggers via request response ACR servers step by step. This is an embodiment of the present invention and a step may be omitted or new steps may be added or a sequence may be changed.

An efficient way to implement this ACR Server behavior is to follow the process described below where the numbers of the actions in the process correspond to the numbers in the architecture diagram above as shown in .

1 The broadcast schedule for the interactive service segments and the AMTs or their equivalents for each segment can be delivered to the ACR Ingest Module ahead of the time the segments are broadcast. The broadcast schedule can contain the segment ID GPS start time and GPS end time of each segment that can contain an interactive service associated with it. If there are any last minute changes to the broadcast schedule the ACR Ingest Module can be notified of these changes immediately. The broadcast schedule could also contain the version number of the TPT for each segment and the ACR Ingest Module could get notification in real time of any unscheduled changes in a TPT version so that it can insert version v terms into Triggers when needed. The Ingest Module could also be configured to insert spread s terms into Triggers at suitable times such as during a specified interval at the beginning of each segment when many receivers are likely to be requesting new TPTs at the same time .

2 If there are any dynamic activations links can be set up from sources of dynamic activations to the ACR Ingest Module.

4 The ACR Ingest Module can extract signatures from the frames in the case of a fingerprint ACR system or insert codes into the frames in the case of a watermark ACR system for all frames contained in segments that have an interactive service associated with them. The ACR Ingest Module can determine whether a frame is in such a segment by using a GPS clock and the start times and end times of segments in the broadcast schedule. For each such frame the ACR Ingest Module can insert a record in the Database that can include a Trigger and the signature or code associated with the frame. The rules for what Trigger gets inserted are described at the end of this list of actions in the process.

6 MVPD can route the Broadcast Stream to the STB at a subscriber s location typically stripping out all of the interactive content first .

8 When the receiver is first turned on it can send its location to an ACR Configuration Server. The URL of the ACR Configuration Server can be built into the receiver. 

10 The ACR Client in the receiver can start extracting fingerprint signatures or watermark codes and sending them to the ACR Server.

12 If the signature or code does not match any signature or code in the Database then the ACR Server can get back a no match indicator. If the signature or code does match a signature or code in the Database then the ACR Server can get back the record for the frame that has the matching signature or code. In the latter case the record in the Database can contain a Time Base Trigger and or it can contain one or more Activation Triggers depending on what was inserted into the record for the frame by the ACR Ingest Module.

13 If the ACR Server gets back a no match indicator from the Database it can return a NULL response to the ACR Client. Otherwise the ACR Server can return to the ACR Client the Trigger or Triggers it obtained.

The following rules can be used to determine what Trigger or Triggers the ACR Ingest Module inserts into each frame record in the Database.

It can be assumed that there is some upper bound L1 on the length of the request intervals used by individual ACR clients in receivers. It is not important whether the ACR clients know what this bound is as long as they operate within it in practice. Let L2 be the length of time it takes a typical ACR client to compute the signature or extract the watermark associated with a frame counting from the time the frame arrives at the receiver. Let L3 be the typical round trip time for a message to go from an ACR client to an ACR server and back. Let M L1 L2 L3. A slightly larger value of M could also be used the advantage of a slightly larger value is that receivers get a little extra time to react to Activation Triggers the disadvantage is that receivers are a little more likely to get multiple Activation Triggers for the same Event activation which is not much of a problem since they will be able to detect that they are duplicates as explained below and only apply the activation once. 

The ACR Ingest Module can insert only a Time Base Trigger in the record associated with a frame unless at least one of the following three conditions holds 

 a There is an Activation element in the AMT such that the media time of the frame is in the time interval beginning at time span M before the startTime of the Activation element and ending at the endTime of the Activation element. If an Activation has no endTime the endTime is considered equal to the startTime. 

 b A dynamic Activation Trigger was received by the Ingest Module before the time interval of time span M immediately preceding the activation time of the Trigger t and the frame lies within that interval.

 c A dynamic Activation Trigger was received by the Ingest Module later than the beginning of the interval of time span M immediately preceding the activation time of the Trigger and the media time of the frame is in the interval of time span L1 immediately following the receipt of the Trigger.

If any of the conditions a b or c holds then an Activation Trigger can be included in the record with an e term to identify the Event to be activated and a t term to indicate the startTime of the Activation element in the AMT for condition a or the event time of the dynamic Trigger for condition b . The Trigger can also contain a version v term.

The reason for continuing to associate Activation Triggers with frames throughout the interval from the startTime to the endTime in case a is to accommodate receivers that join the channel partway through the interval.

Note that this approach requires no extra intelligence on the part of the ACR Server. It simply returns to the ACR Client the information it finds in the Database. All the intelligence can reside in the ACR Ingest Module. Moreover the computations the ACR Ingest Module needs to do can be very simple.

With this scheme it is possible that a receiver can get more than one Activation Trigger associated with different frames for the same event activation. However a receiver can easily see from the t values that they all have the same activation time so the receiver can determine that they are duplicates and activate the event only once.

In two of the situations above the t term in the Activation Trigger can have an event time earlier than the media time of the frame with which it is associated. In situation a if the endTime of the Activation element is significantly later than the startTime then a receiver can typically get multiple Activation Triggers throughout the interval between the startTime and the endTime and they can all have the startTime as activation times. In situation c the Activation Triggers for the activation can get inserted into frame records so late that the Activation Trigger a receiver gets can come in response to a request with a signature for a frame that has media time after the activation time. When a receiver gets an Activation Trigger with an event time earlier than the media time of the frame with which it is associated it can be expected to activate the event immediately unless it recognizes it as a duplicate of an Activation Trigger it has already seen and used to activate the event.

The purpose of using event time values in the past rather than do it now Triggers for the situation when the frame media time is later than the event activation time is because a receiver can get more than one of these after the fact Activation Triggers. The t values allow the receiver to determine that they all have the same activation time and to activate the event only once.

Four circled vertical arrows may represent an example when a typical receiver sends a request. In this example the receiver would get two Activation Triggers for the same event activation but they would have the same event activation times so the receiver would recognize them as duplicates and only apply the first one. Because the interval between receiver requests is less than L1 the receiver is guaranteed to make at least one request with a signature for a frame in the L1 interval shown in the diagram. This gives it time to compute the signature send the request to the ACR server and get the Activation Trigger back in response all before the activation time. In this example the first Activation Trigger the receiver gets would be delivered well ahead of time the second Activation Trigger the receiver gets would barely arrive in time it is a duplicate .

Four circled vertical arrows may represent an example when a typical receiver sends a request. In this example the receiver would get two Activation Triggers for the same event activation but the activation times computed by adding the value to the receiver s local time for frame f1 or adding the value to the receiver s local time of frame f2 both give the same result so the receiver would recognize them as duplicates and only apply the first one. Because the interval between receiver requests is less than L1 the receiver is guaranteed to make at least one request with a signature for a frame in the L1 interval shown in the diagram. This gives it time to compute the signature send the request to the ACR server and get the Activation Trigger in response all before the activation time. In this example the second Activation Trigger received by the receiver would arrive after the activation time.

The figure shows an event activation startTime and endTime above the time line with an interval of length M preceding the startTime. The arrows below the time line show the times of individual frames. Each frame preceding the beginning of the interval of length M or following the event activation endTime would have associated with it in the Database a Time Base Trigger. Each frame inside the interval of length M or between the startTime and endTime of the event activation would have an Activation Trigger associated with it in the Database in the form shown by the three examples at the bottom of the figure. The t term for each frame would indicate the event activation time relative to the media time line indicated by circled f1 f2 and f3 .

Three circled vertical arrows may represent an example when a typical receiver sends a request. In this case the receiver would get three Activation Triggers for the same event activation but the activation times would all be the same so the receiver would recognize the same as duplicates and only apply the first one.

Of course the first two Activation Triggers shown in the diagram would not be seen at all by a receiver that joins the channel after the startTime and sends the signature of frame f3 with its first request.

The figure shows an event activation startTime and endTime above the time line with an interval of length M preceding the startTime. The arrows below the time line show the times of individual frames. Each frame preceding the beginning of the interval of length M or following the event activation endTime would have associated with it in the Database a Trigger with no or terms. Each frame inside the interval of length M would have an Activation Trigger in the Database in the form shown by the two examples at the bottom of the figure. The d term for each frame would indicate the length of time between that frame and the event activation time indicated by circled vertical arrows .

Circled vertical arrows may represent an example when a typical receiver sends a request. In this case the receiver would get three Activation Triggers for the same event activation but the activation times computed by adding the value to the receiver s local time for frame f1 or adding the value to the receiver s local time of frame f2 or adding the negative value to the receiver s local time of frame f3 all give the same result such that the receiver would recognize the same as duplicates and only apply the first one.

Of course the first two Activation Triggers shown in the diagram would not be seen at all by a receiver that joins the channel after the startTime and sends the signature of frame f3 with its first request.

In the event driven ACR model the receiver can be expected to initiate a persistent connection to the ACR server generate signatures associated with frames at regular intervals e.g. every 5 seconds and submit the signatures over the connection. The ACR server does not respond to each signature. It can send a message to the receiver when a new segment is detected or when an event activation needs to be communicated to the receiver. In this model it is possible for the ACR server to initiate messages to the client at any time over the persistent connection.

Moreover it is straightforward for the server to maintain a certain amount of information about each receiver such as the segment ID of a Trigger corresponding to the most recent submission from the receiver and the recent Activation Triggers sent to the receiver.

For an ACR server that is using this event driven model and is delivering activations to receivers the following rules can apply for messages from the ACR server.

First of all when the ACR server receives a signature from a receiver that corresponds to a frame in a new segment the ACR server can send a message to the receiver with a Time Base Trigger immediately to enable the receiver to obtain the associated TPT.

Second when the ACR server receives a signature from a receiver that corresponds to a frame in a part of a segment that has a new version number for the TPT different from the most recent version the receiver has seen the ACR server can send a message immediately to the receiver with a Time Base Trigger that has a v term to enable the receiver to obtain the new version of the associated TPT.

Third when an event is due to be activated the ACR server can send an Activation Trigger to the receiver. If possible it can send the Activation Trigger slightly ahead of the time when the receiver needs to apply it with a t term in the Activation Trigger to indicate the activation time relative to the media time line. This is very similar to the behavior in the request response model. If the ACR server learns of the activation so late that it cannot send an Activation Trigger as far ahead of time as usual it can send an Activation Trigger as soon as it does learn of the activation. In this latter case the receiver could get the Activation Trigger after its activation time in which case it can be expected to activate the event as soon as it gets the Activation Trigger. 

The architecture for the Request Response case shown in is also suitable for this Event Driven case with one difference. The difference is that for the Event Driven case there can be a new action 2a . If there are any dynamic Activation Triggers then connections can be set up between the ACR Ingest Module and all ACR Servers that use the Database populated by the ACR Ingest Module so that the ACR Ingest Module can send selected dynamic Activation Triggers to the ACR Servers.

The numbered actions for the Event Driven case can be similar to those for the Request Response case. Besides the new action 2a action 4 is a little different action 13 is a little different and a new action 14 is added.

In action 4 the ACR Ingest Module can extract signatures from the frames in the case of a fingerprint ACR system or insert codes into the frames in the case of a watermark ACR system for all frames contained in segments that have an interactive service associated with them. The ACR Ingest Module can determine whether a frame is in such a segment by using a GPS clock and the start times and end times of segments in the broadcast schedule. For each such frame the ACR Ingest Module can insert a record in the Database that can include the signature or code associated with the frame and a Trigger. The Trigger included in the record by the ACR Ingest Module can be a Time Base Trigger unless at least one of the following two conditions holds 

 a There is an Activation element in the AMT such that the media time of the frame is in the time interval beginning at time span M before the startTime of the Activation element and ending at the endTime of the Activation element. If an activation has no endTime the endTime is considered equal to the startTime. Same as condition a for the Request Response ACR model 

 b A dynamic Activation Trigger was received by the Ingest Module before the time interval of time span M immediately preceding the activation time of the Trigger t and the frame lies within that interval. Same as condition b for the Request Response ACR model 

If either of the conditions a or b holds then an Activation Trigger can be included in the record with an e term to identify the Event to be activated and a t term to indicate the startTime of the Activation element in the AMT for condition a or the event time of the dynamic Trigger for condition b .

If a dynamic Activation Trigger is received by the Ingest Module during the interval of time span M immediately preceding the activation time of the Trigger where M has the same meaning as in the request response server case then the Ingest Module can pass the Activation Trigger on to all the ACR Servers that are using the Database into which the Ingest Module can be inserting records without putting anything in the Database concerning that dynamic Activation Trigger. Variations on this architecture are possible in which dynamic Activation Triggers are passed directly from the dynamic Activation Trigger sources to the ACR servers without going through the Ingest Model but the ACR servers get the dynamic Activation Triggers that arrive later than M time units ahead of the activation time so that it can send a message to the relevant receivers immediately. It might be too late if it waits until the next receiver submissions. 

In action 13 if the ACR Server gets back a no match indicator from the Database after not receiving one for the immediately preceding submission it can send a NULL message to the receiver. If it gets back a Trigger with a that is different from the it got back for the immediately preceding submission it can send the Trigger to the receiver In both cases this can tell the receiver that either the channel being viewed has been changed or the segment being viewed has come to an end so the receiver can terminate any TDO that is currently executing and if necessary download a new TPT. If the ACR Server gets back one or more Activation Triggers it can send them to the receiver discarding any that are duplicates of Activation Triggers it has already sent to the receiver. Otherwise the ACR Server may do nothing.

In a new action 14 if an ACR Server receives a dynamic Activation Trigger it can compare the of the dynamic Activation Trigger with the current for each of its ACR clients where the current for a client is the of the Trigger that the ACR Server got from the Database for the most recent submission from the ACR client. For each client where the matches the ACR Server can send the Activation Trigger to the client.

The figure Dynamic Activation Triggers Delivered at Last Minute shows a dynamic event activation time above the time line and a time shortly preceding the event activation time when the ACR Ingest Module learns of the event actuation. The arrows below the time line show the times of individual frames. As soon as the ACR Server receives the Activation Trigger from the ACR Ingest Module it can send the Activation Trigger to all receivers that are currently viewing the segment associated with the Activation Trigger as identified by the of the Trigger . For each receiver it adjusts the event time of the Trigger to a relative to the frame corresponding to the most recently submitted signature from the receiver.

An exemplary operation of the request response model in the order of request and response will now be described.

The sequence diagram between the ACR client and other servers in a request response ACR case may include ACR request 1 S ACR response 1 S ACR request 2 S ACR response 2 S HTTP request 1 S HTTP response 1 S HTTP request 2 S HTTP response 2 S ACR request 3 S ACR response 3 S ACR request 4 S and or ACR response 4 S .

ACR request 1 S is a step in which the receiver transmits the signature of a currently viewed program to a server. The server may be the above described ACR server. The signature may be a fingerprint signature or a watermark.

ACR response 1 S is a step in which the ACR server returns NULL when the signature is not recognized or a related interactive service is not present. This may be a case corresponding to the above mentioned case in which a NULL response is returned.

ACR request 2 S is a step in which when the channel or program is changed the receiver transmits the signature of the changed program to the ACR server.

ACR response 2 S is a step in which the ACR server returns a trigger e.g. xbc.com tpt504 including an address by which an interactive service related to the corresponding program can be obtained. This step may correspond to a case in which the signature is recognized and a related interactive service is present unlink ACR response 1 S . That is a trigger is available in this step. In this case the returned trigger may be a time based trigger having no information about media time.

HTTP request 1 S is a step in which the receiver requests the TPT server e.g. http xbc.com tpt504 to provide a corresponding TPT using the address received in ACR response 2 S through the http protocol.

HTTP response 1 s is a step in which the TPT server transmits the TPT represented in XML at the request of the receiver.

HTTP request 2 S is a step in which the receiver requests the content server to provide an application such as TDO using the http protocol. The receiver can parse TDO related information included in the TPT. The TDO related information may be the URL of the content server through which a TDO can be downloaded. A request can be sent using the URL of the content server.

HTTP response 2 S is a step in which the content server transmits the corresponding TDO at the request of the receiver.

ACR request 3 S is a step in which the receiver sends the signature of a frame of the currently viewed program to the ACR server.

ACR response 3 S is a step in which the ACR server returns a trigger e.g. xbc.com tpt504 including an address through which an interactive service related to the corresponding program can be obtained. In this case the signature is recognized and the related interactive service is present unlike ACR response 1 S . That is a trigger is available in this step.

ACR request 4 S is a step in which the receiver transmits the signature of a frame of the currently viewed program to the ACR server.

ACR response 4 S is a step in which the ACR server transmits an activation trigger related to the interactive service related to the signature transmitted from the receiver. A specific event can be activated at a specific time according to the activation trigger.

An exemplary operation of the event driven model in the order of request response to the request and event will now be described.

The sequence diagram between the ACR client and other servers in an event driven ACR case may include ACR request 1 S ACR request 2 S ACR event 1 S HTTP request 1 S HTTP response 1 S HTTP request 2 S HTTP response 2 S ACR request 3 S ACR event 2 S and or ACR response 4 S .

ACR request 1 S is a step in which the receiver transmits the signature of a currently viewed program to a server. The server may be the above described ACR server. The signature may be a fingerprint signature or a watermark. Here when the signature is not recognized or a related interactive service is not present the ACR server may send no response to ACR request 1 without returning NULL unlike the sequence of .

ACR request 2 S is a step in which when the channel or program is changed the receiver transmits the signature of the changed program to the ACR server.

ACR event 1 S is a step in which the ACR server returns a trigger e.g. xbc.com tpt504 including an address by which an interactive service related to the corresponding program can be obtained. This step may correspond to a case in which the signature is recognized and a related interactive service is present. That is a trigger is available in this step. In this case the returned trigger may be a time based trigger having no information about media time.

HTTP request 1 S is a step in which the receiver requests the TPT server e.g. http xbc.com tpt504 to provide a corresponding TPT using the address received in ACR event 1 S through the http protocol.

HTTP response 1 s is a step in which the TPT server transmits the TPT represented in XML at the request of the receiver.

HTTP request 2 S is a step in which the receiver requests the content server to provide an application such as TDO using the http protocol. The receiver can parse TDO related information included in the TPT. The TDO related information may be the URL of the content server through which a TDO can be downloaded. A request can be sent using the URL of the content server.

HTTP response 2 S is a step in which the content server transmits the corresponding TDO at the request of the receiver.

ACR request 3 S is a step in which the receiver sends the signature of a frame of the currently viewed program to the ACR server.

ACR event 2 S is a step in which the ACR server transmits an activation trigger related to the interactive service related to the signature transmitted from the receiver. A specific event can be activated at a specific time according to the activation trigger.

ACR request 4 S is a step in which the receiver transmits the signature of a frame of the currently viewed program to the ACR server.

Second screen support relates to a method of at a receiver providing a service of a broadcaster or supplementary service suitable for a program provided by the broadcaster to a second screen device. Supplementary content may be provided via an application and the application may be displayed on a TV screen such that a user utilizes the supplementary content by manipulating a remote controller. However recently via personalized information instruments smartphones smart pads and downsized laptops supplementary services may be displayed on the second screen device while displaying content played back on the TV screen. Therefore the user can personally utilize the supplementary services without interrupting broadcast content. If such supplementary data or information is displayed and processed on the second screen device when several persons watch TV together only a person interested in a supplementary service may obtain the supplementary content without interrupting TV viewing of the other persons. Second screen support may be variously used in addition to the above described effects.

For connection and control of one device to other devices first which devices are included in a home network should be determined. Accordingly one or more devices periodically transmit messages to the home network so as to notify that the devices are present in the home network. If one device is newly connected to the home network the device may ask which devices are present in the home network before notifying that the device is newly connected. Such connection methods may aid in easily and rapidly recognizing the presence of the devices. UPnP device discovery is one method of achieving this. If a device is detected other devices interesting in the detected device may require information about which services may be provided to that device. Electronic apparatuses in which a UPnP framework is installed may confirm mutual functions and supported function ranges. This information may be defined in a UPnP Device Profile such that the devices confirm attributes of mutually provided services. A device for providing a specific service may be always waited for. If the device for providing the specific service is detected it is possible to ask which services are included in the detected device. If a desired service is present in the detected device the detected device may be immediately connected to perform communication. As defined in the UPnP Service Descriptor services may be defined and exchanged.

Since one device has a single service or a plurality of services the service s may be controlled and utilized by other devices. If the device has one or more functions a plurality of services corresponding to the functions are included and controlled by other devices. Definition of the device may have unique information about the device. For example the unique information about the device may include information such as Model Name Serial Number Model Number CE Manufacturer Name and Web Site. This information may have a unique value for each device and may not be generally changed. The service is an operation performed by a device which is referred to as an action and each device may have one or more actions. The action has a parameter value such as a function and may have one or more parameter values. The action is performed by a service of a device and a return value defined as necessary may be returned after performing the action.

As an example of an action shows types of actions of a UPnP RemoteUI Client service and a description thereof. Connection disconnection may be an action for returning current connection states. GetCurrentConnection may be an action for returning a current connection list. GetDeviceProfile may be an action for returning a device profile as expressed in XML. GetUIListing may be an action for returning a compatible UI list as expressed in XML. AddUIListing RemoveUIListing may be an action for adding a URL of a remote UI to a UI list or removing the URL of the remote UI from the UI list. ProcessInput may be an action for sending data to a RemoteUI Client service. DisplayMessage may be an action for displaying a message on a device including a RemoteUI Client service.

In UPnP an XML message format such as SOAP may be used to transmit the above described actions and necessary parameter values and SOAP may be used to remotely perform a remote procedure. These messages may be transmitted using a HTTP.

The actions of the above described RemoteUI Client may be performed as shown in . The actions shown in are only examples of the above described actions.

One embodiment of the UPnP RemoteUI Client Service may be divided into a UPnP Discovery Process and RemoteUI Client Actions.

The UPnP Discovery Process may include executing a UPnP application for a second screen service s finding UPnP devices s finding a RemoteUIClient s requesting a device description s receiving a device description s requesting a service control description s and or receiving a service control description s .

RemoteUI Client Actions may include requesting a device profile s receiving a device profile s putting a URL of a Remote UI s sending a response1 s sending a message to the RemoteUI Client Service s sending a response2 s and or user clicking the button on the screen s .

Executing a UPnP application for a second screen service s may include executing a UPnP application in a second screen device RemoteUI Client .

Finding UPnP devices s may include a primary device multicasting a discovery message to applications which are being executed in the second screen device. By this step the second screen device in the network may be found. The primary device may indicate a second screen support service provided thereby via the discovery message.

Finding a RemoteUIClient s may include the second screen device receiving the discovery message and sending a notification message to the primary device.

Requesting a Device Description s may include the primary device requesting a device description for the second screen device from the second screen device.

Receiving a device description s may include the primary device receiving the device profile of the second screen device when the second screen device transmits the device profile of the second screen device in response to requesting the Device Description s .

Requesting a service control description s may include the primary device requesting a service control description from the second screen device.

Receiving a service control description s may include the primary device receiving the requested service control description from the second screen device.

The primary device and the second screen device present on the network may find and recognize each other via the UPnP Discovery Process. In addition the primary device and the second screen device may be connected to each other.

Requesting a device profile s may include requesting the device profile of the second screen device. The above described GetDeviceProfile action may be utilized.

Receiving a device profile s may include the primary device receiving the requested device profile of the second screen device. A device second screen device and RemoteUI Client having the RemoteUI Client Service may be responsible for finding and displaying a URL address of a UI on the screen if a remote device primary device sends the URL address of the UI. In addition the device having the RemoteUI Server Service may multicast the URL address of the UI to notify interested devices of the URL address. However in this case since the remote UIs are made for a specific device the remote UI suitable for the specific device should be provided. Accordingly device profile information also needs to be transmitted and requesting the device profile s and receiving the device profile s may be necessary.

Putting a URL of a Remote UI s may include notifying the second screen device of the URL address of the Remote UI. The above described AddUIListing action may be utilized. The second screen device may add the URL address of the remote UI to UIListing.

Sending a response1 s may include sending the result of putting the URL of the Remote UI s . According to circumstance a response such as HTTP 1.1 200 OK the request is successfully processed HTTP 1.1 501 Method Not Implemented A function necessary to process the request is not implemented and HTTP 1.1 400 Not Found The requested files resources are not present may be sent.

Sending a message to the RemoteUI Client Service s may include the primary device transmitting a display message to the second screen device. The display message may include information such as a message type. The above described DispalyMessage action may be utilized. The second screen device may display the message on the second screen according to the display message.

Sending a response2 s may include sending a result of sending the message to the RemoteUI Client Service s . Similarly to sending the response1 s a response such as HTTP 1.1 200 OK may be sent.

User clicking the button on the screen s may include the user performing selection according to the message displayed on the second screen.

RemoteUI Client Actions describe the process of operating the RemoteUI Client service via the above described actions.

In the description of the remote user interface functions which may be used in an existing PC system may be simplified in consideration of resources of an electronic apparatus the function of which is added or restricted such that an HTML based application may be used in the electronic apparatus. This description largely includes two viewpoints applying an HTML displayed on a screen to consumer electronics and defining a browser API which is applicable to consumer electronics. The browser API may be called and used from JavaScript which is a widely used scripting language. As a result the API called from the JavaScript calls a function of a receiver.

Among others the above described UPnP device and services may be executed by JavaScript executed in the browser. There is a need for a new API for delivering other parameters to UPnP devices in browser.

As described above the above described trigger may be transmitted using a digital TV closed caption service DTVCC . The trigger may have one URL string value and may be received as DTVCC service series 6. An MPEG 2 Transport processor may receive the trigger as DTVCC Service Series 6 and transmit the trigger to a DTV CC module via a transport processor driver . At this time user data may pass through a buffer . The DTV CC module may serve as a DTVCC Decoder. The DTV CC module may send the trigger having a URI String value to an adjunct service module . The adjunct service module is a trigger module which may detect a URI String value so as to acquire the above described TPT TDO Parameters Table . As described above it is possible to provide an adjunct service using the trigger TPT and TDO.

For second screen support there may be several requirements. 1 The receiver may be connected to one or more second screen devices. 2 The second screen device may be a portable device such as a laptop tablet smartphone or PDA. 3 The primary content of the second screen may be HTML Text Video Audio etc. 4 The content played back on the second screen may be designed so as not to interrupt a broadcast program of the primary device receiver . 5 The second screen may be connected to an ATSC 2.0 receiver directly or indirectly via a 3GPP network. 6 The provider may signal specific content to be displayed only on the second screen. 7 According to circumstance content played back by the receiver may be designed for playback by the second screen. 8 The second screen subjected to authentication and authorization may use a second screen service. 9 Audience usage of second screen content may be measured. In this case in order to obtain such information user consent must be obtained and a function for such information may be necessary and 10 This may be provided via a device capable of enhancing secondary language or content.

This specification may describe services that can be provided by a Receiver to support the display of content related to an A V broadcast by applications running on second screen devices smart phones tablets laptops etc. including content synchronized with the programming being broadcast. The service is described based on the UPnP Device Architecture.

In this specification the ATSC 2.0 Receiver may be a TV receiver or a normal receiver. In addition the ATSC 2.0 Receiver may be a receiver in DVB ATSC etc.

The UPnP Device Architecture defines protocols for communication in an IP network between controlled devices that provide services and control points that utilize those services. In the second screen scenario a TV receiver can play the role of a controlled device and a second screen device can play the role of a control point and vice versa.

The UPnP Device Architecture specifies discovery protocols for control points to discover controlled devices of interest description protocols for control points to learn details about controlled devices and services control protocols for control points to invoke actions methods on controlled devices and eventing protocols for controlled devices to deliver asynchronous notifications to control points. The actions and events may be provided by the device services.

When an UPnP controlled device joins a network it can multicast discovery messages to a well known IP multicast address and port. These messages can identify the device type and the service types offered by the device and they can give URLs where descriptions of the device and services can be obtained.

When an UPnP control point joins a network it can multicast a search message asking controlled devices to announce themselves. The search message can specify the device types and or service types of interest. Relevant devices can respond by sending unicast discovery messages to the control point.

Once a control point gets discovery messages about devices and services of interest it can use the URLs in the messages to request descriptions of the devices and services. These descriptions can include the URLs that can be used to invoke actions and subscribe to events for the services.

Typical Second Screen Discovery Scenarios may be largely divided into Scenario A and scenario B. In case of Scenario A the user has a second screen app running in his her second screen device when the TV receiver joins the network which perhaps happens when the TV receiver is turned on or perhaps when its network interface is enabled . In case of Scenario B the user does not have a second screen app running in his her second screen device when the TV receiver joins the network.

Scenario A may be as follows. 1 A TV receiver that provides second screen support joins the network. 2 The TV receiver multicasts its discovery messages that advertise its second screen support services. 3 The second screen app running in the second screen device receives the multicast discovery messages and sends the TV receiver a request for descriptions of its services. 4 The TV receiver responds with descriptions of its services. 5 The second screen app uses the information given in the descriptions to access the appropriate services and provide an interactive experience synchronized with the TV programming.

Scenario B may be as follows. 1 The TV programming being viewed on the TV receiver enters a program segment that offers second screen support. This could be as soon as the TV set is turned on or when a channel change goes from a channel that does not offer an interactive data service with second screen support to one that does offer it or when the channel being viewed goes from a program segment that does not offer an interactive data service with second screen support to a segment that does offer it. 2 This causes the TV receiver to inform viewers in some way that second screen support is available for example by a small icon in a corner of the screen. 3 The viewer decides to take advantage of the second screen support and activate a second screen app on his her second screen device. The second screen app then multicasts a message searching for devices that offer second screen support. The TV receiver responds to this message with its discovery messages. 4 When the second screen app receives the discovery messages it sends the TV receiver a request for descriptions of its services. 5 The TV receiver responds with descriptions of its services. 6 The second screen app uses the information given in the descriptions to access the appropriate services and provide an interactive experience synchronized with the TV programming.

Scenario A may be also as follows. 1 A TV set that provides second screen support joins the network. This could be when the TV set is turned on or when its network interface is enabled. 2 This causes the TV receiver to multicast its discovery messages that advertise itself and its second screen support services. 3 If a user has a Second Screen App running is his her second screen device at this time the app receives the multicast discovery messages and proceeds to step 7 . 4 The TV programming being viewed on the TV receiver enters a program segment that offers second screen support. This could be as soon as the TV set is turned on or when a channel change goes from a channel that does not offer an interactive data service with second screen support to one that does offer it or when the channel being viewed goes from a program segment that does not offer an interactive data service with second screen support to a segment that does offer it. . 5 This causes the TV receiver to inform viewers in some way that second screen support is available for example by a small icon in a corner of the screen. 6 If a viewer does not already have an Second Screen App running in his her second screen device the viewer can decide to take advantage of the second screen support and activate an Second Screen App on his her second screen device. The Second Screen App then multicasts a message searching for devices that offer second screen support. The TV receiver responds to this message with its discovery messages. 7 When the Second Screen App receives the discovery messages it sends the TV receiver a request for descriptions of its services. 8 The TV receiver responds with descriptions of its services. These will be a Trigger service and optionally an HTTP Proxy Server service. 9 The Second Screen App will subscribe to the eventing feature of the Trigger service. If the interaction model of the interactive data service being offered is the Direct Execution model the Trigger service will send all Triggers to the second screen device as they are received by the TV receiver. If the interaction model of the interactive data service is the TDO model the Trigger service will send an Activation Trigger to the Second Screen App whenever the activation time of a new Activation Trigger arrives. 10 The Second Screen App will act on the Triggers downloading TDOs and other files as needed either from an Internet link or from the HTTP Proxy Server service offered by the TV receiver and providing the interactive service to the second screen device user. 11 Whenever the TV programming on the TV receiver goes to a segment that does not offer an interactive data service with second screen support the Trigger service will send a null Trigger to the Second Screen App to notify it that an interactive data service for the second screen device is no longer available. 12 The user of the second screen device can then close the Second Screen App or leave it running to resume the interactivity whenever the programming on the TV receiver enters another segment that offers second screen support.

In either scenario it can be possible that the household has more than one TV receiver on the home network. It this case the second screen app would receive discovery messages from multiple different receivers. If that happens the second screen app can ask the user which one to interact with displaying information from the description messages to help the user decide .

A TV receiver that provides second screen support can offer several UPnP services for the use of second screen apps. The UPnP services can be Trigger delivery service from the receiver to a second screen app Two way communications service between Declarative Objects DOs running in the receiver and a second screen app and HTTP proxy server service . These services can be optional depends on configuration.

These services can be designed to support a wide variety of different types of second screen applications obtained from a wide variety of different sources running in a wide variety of different operating environments in a wide variety of different types of second screen devices.

A typical second screen packaged apps scenario is as follows. 1 A control point on a second screen device subscribes to a Packaged Apps service on a first screen device. 2 A consumer starts a Packaged App on the first screen device. 3 The Packaged App makes the name of a second screen app and the URL of the second screen app available to the Packaged App service. 4 The control point on the second screen device receives the companion app name and URL. 5 The control point sets a marker on the second screen indicating consumer action needed. 6 The consumer reviews the second screen app name and selects it. 7 The control point launches indicated second screen app.

A first screen device that provides second screen support can offer several UPnP service for the use of second screen apps. One of the UPnP service is Application URL service which is providing the name and URL of the companion second screen app to be executed on the second screen device.

The system architecture for second screen scenario may include a broadcasting system an ACR server a broadcaster ATSC 2.0 iTV server an ATSC 2.0 receiver and or second screen devices .

The broadcasting system may be a normal broadcast system and may deliver triggers A V TPTs and or other data files via a broadcast network. The trigger may be transmitted via the DTVCC as described above.

The ACR server is a server for managing ACR related data of broadcast content and may transmit a trigger to the ATSC 2.0 receiver such that the ATSC 2.0 receiver acquires an interactive service as requested or necessary. This may be equal to the above described ACR server.

The broadcaster ATSC 2.0 iTV server is a server for generating and managing an interactive service and may manage associated TDO files and generate and manage a TDO parameter table TPT including information about the associated TDO files.

The ATSC 2.0 Receiver may receive the trigger related to broadcast A V and interactive service and acquire and provide the interactive service on the screen using the trigger. This may be equal to the above described receiver.

The second screen devices may include a mobile phone a tablet a laptop etc. which are the second screen devices. This may be equal to the above described second screen device.

Triggers can be delivered to the ATSC 2.0 receiver via the DTVCC channel or via an ACR process or from a Broadcaster interactive TV iTV Server . In all cases Triggers are passed from the ATSC 2.0 receiver to the second screen devices at the appropriate times. This specification describes mechanisms for Triggers to be passed to second screen devices . It also describes mechanisms for DOs running on an ATSC 2.0 receiver to establish two way communications with second screen devices .

Apps and other files that are available via Internet can be retrieved by second screen devices via the home network via a separate 3GPP network or via an HTTP Proxy Server not shown on the ATSC 2.0 receiver if it offers that service. Apps executing on first screen devices may be Packaged Apps downloaded from the Internet or apps transmitted through the broadcast.

Apps and other files that are only available via FLUTE sessions in the broadcast can be retrieved by second screen devices only if ATSC 2.0 receiver offers an HTTP Proxy Server that will deliver the FLUTE files when requested assuming the second screen device does not include a TV receiver .

This specification also describes a mechanism for Packaged Apps running on an ATSC 2.0 receiver to support launching of applications on second screen devices .

The embodiment of topology between the ATSC 2.0 receiver and the second screen Direct Connection may include a broadcasting system a broadcaster ATSC 2.0 server an ATSC 2.0 receiver and or second screen devices .

The ATSC 2.0 receiver may be connected to a broadcast network to directly receive a terrestrial broadcast. Accordingly the ATSC 2.0 receiver may extract the URL string of the iTV message transmitted via the DTVCC from DTVCC Service Number 6. In addition the ATSC 2.0 receiver may be connected to a home gateway to access the Internet as necessary. The ATSC 2.0 receiver may communicate with devices connected in other home networks using home networking technology UPnP .

The second screen devices are all connected to the home gateway to communicate with the devices and to freely access the Internet. The home gateway may include all functions for supporting Ethernet and Wi Fi.

A broadcaster may provide a supplementary service via an Internet server for an interactive service. The ATSC 2.0 receiver or the second screen devices may access the server to download a TDO or web page for a mobile device. In case of the ATSC 2.0 receiver a web page may be rendered to the resolution of a TV and in case of the second screen devices a web page may be rendered to resolution and APIs different from those of the TV.

The embodiment of topology between the ATSC 2.0 receiver and the second screen Indirect Connection may include a broadcasting system a broadcaster ATSC 2.0 server a broadcaster session management device an ATSC 2.0 receiver and or second screen devices .

The broadcaster session management device may serve to manage indirect connection between the second screen device and the ATSC 2.0 receiver .

Indirect connection of does not indicate that the second screen devices are connected to the ATSC 2.0 receiver via the home gateway but indicates that the second screen devices are directly connected to the 3GPP network to be connected to the ATSC 2.0 receiver over the home network. In this case it is difficult to connect the second screen devices to the home network or a network interface supporting the home network may not be present.

In this case the second screen devices may require information about the ATSC 2.0 receiver stored on an external Internet server. In addition the ATSC 2.0 receiver reports the access address to the external Internet server upon operation.

The second screen devices generally execute applications using OSs. In general some functions of OSs for mobile devices may not be included for the purpose of lightweight. Accordingly the functions which are not supported by the OSs need to be included in the applications.

The software layer of shows the software structure of a second screen service application necessary for the second screen service. may show the case in which the receiver manages the lifecycle of the second screen application.

Since the second screen device may play Internet content back the OS may provide an environment in which a web application may be executed to programmers using a platform SDK. The environment may be provided in the form of the SDK such that the application executed by the OS directly displays the Internet content.

In Second Screen Service Application can be running on Second Screen Device. This application can be downloaded from an AppStore or some kind of application market . Second Screen Service Application can include ACR Client and use the microphone and camera to capture the video and audio data from TV set. Moreover the ACR client can sample video and audio data and send a media signature to the ACR server. Second Screen Service Application may run on the OS and include a protocol such as HTTP SSDP or Multicast Event according to which a UPnP Framework may operate and a browser module may be included in order to perform and display a web application.

The browser module can be a module to render Internet web pages. The browser module is a core part of the web browser engine to render the Web application e.g. ECMAScript HTML and XHTML . In addition the browser module may mean a software module for providing a function equal or similar to a browser provided by the OS. The method of utilizing the browser and the controllable functions differ between OSs.

Second Screen Application can be a web application that is designed for Second Screen devices. Second Screen Application may be a web application for calling functions according to ECMAScript or a web application the size of which is controlled to be executed in the browser module provided by a mobile OS. This web application may be executed in the Second Screen Service Application.

The operating system for the mobile device may be composed of drivers supporting hardware and include drivers for a kernel specific service. Fundamentally it is possible to support only IP TCP and UDP protocols. A network protocol stack is present above the OS. In case of UPnP a HTTP may be transmitted using a UDP.

An SSDP Simple Service Discovery Protocol may search for one or more services according to the device connected to the network in the home network.

The software layer of shows the software structure of the second screen service application necessary for the second screen service. may show the case in which the second screen service application manages the lifecycle of the second screen application.

The ATSC 2.0 Trigger Client may mean a module for receiving and processing the above described trigger TPT AMT etc. This module may be included in the second screen device according to circumstance. If this module is included in the second screen device this module may directly process the TPT and AMT to directly check the lifecycle of the application.

The receiver may directly receive the TPT and the AMT using the DTVCC over the broadcast network or download the TPT and the AMT over the Internet network and process the TPT and the AMT. As described above the TPT includes event information and the event information may include EventId Action Destination and Data information. Event Destination may indicate for which device this event information is generated. For example the destination may be a receiver or a second screen device. If the destination is set to the second screen device the receiver should deliver the event information to the second screen device.

Accordingly there is a need for a method of delivering this information to the second screen device. The lifecycle of the second screen application may be managed by the receiver or the second screen service application.

The table of shows summary of information delivery methods depending on which entity manages the lifecycle of the second screen application.

The first row may be a summary of a description of the below described case of and a detailed description thereof will be given below.

A second row may be a summary of a description of the case in which the receiver manages the lifecycle of the second screen application and a detailed description thereof will be given below.

A third row may be a summary of a description of the case in which the receiver filters augments and delivers trigger information necessary for the second screen device and a detailed description thereof will be given below.

A fourth row may be a summary of a description of the below described case of and a detailed description thereof will be given below.

A fifth row may be a summary of a description of the below described case of and a detailed description thereof will be given below.

A method of efficiently delivering an interactive service to a second screen device may include a centralized execution model and a distributed execution model.

As shown in the diagram showing the operational concept of the centralized execution model a TV set may generate and update an RUI to be displayed on each second screen device using an RUI mechanism of UPnP and transmit the RUI over a network. Each second screen device may receive the RUI via an RUI client in real time and display the RUI on a screen. Unlike the distributed execution model a DAE may be present in the primary device.

The flow of may be an operation when a centralized execution model mechanism is applied in an environment in which a receiver is capable of acquiring an interactive service via a broadcast network and interworks with a second screen device in the embodiment of the operational concept of the centralized execution model.

The embodiment of the flow of interworking between the centralized execution model based receiver and the second screen may include sending a time base trigger s requesting a TPT s transmitting a TPT as a response s parsing a TPT s sending an execute trigger for the second screen s downloading TDOs Files s generating an RUI s sending an RUI via a RUI protocol s displaying a UI on the screen s user clicking a link for a new page s sending input data s downloading a new TDO file s updating an RUI s sending an RUI via a RUI protocol s and or displaying a UI on the screen s .

Sending a time base trigger s may include the receiver receiving the time base trigger via a DTVCC or ACR server. The time base trigger was described above.

Requesting a TPT s may include the receiver interpreting the received trigger acquiring a URL of a server capable of acquiring the TPT and requesting the TPT.

Transmitting a TPT as a response s may include transmitting the TPT in response to the request in requesting TPT S .

Sending an execute trigger for a second screen s may include the receiver receiving the execute trigger for the second screen via the DTVCC or ACR server. The execute trigger may be equal to the above described activation trigger.

Downloading TDOs Files s may include the receiver acquiring the information about the TDOs and files associated with the time base trigger or the execute trigger from the received TPT and downloading the TDOs and files indicated by the trigger from a content server.

Sending RUI via a RUI protocol s may include the receiver transmitting the RUI generated on the second screen using the RUI protocol.

User clicking a link for a new page s may include clicking a specific link on the RUI by selection of the user on the second screen.

Sending input data s may include delivering input information of the user to the receiver if a clicked specific link is connected to another page.

Downloading a new TDO file s may include the receiver downloading TDOs and files associated with user input.

Sending an RUI via a RUI protocol s may include the receiver transmitting the updated RUI to the second screen using the RUI protocol.

This process may include receiving a trigger for a receiver s receiving a trigger for a second screen service s sending notification about updated UI information s requesting updated UI information s transmitting compatible UI information as a response s and receiving another trigger for the receiver s .

Receiving a trigger for a receiver s may include the primary device receiving the trigger for the receiver that is the primary device from the broadcaster via the broadcast stream.

Receiving a trigger for a second screen service s may include the primary device receiving the trigger for the second screen service from the broadcaster via the broadcast stream.

Sending notification about updated UI information s may include notifying about updated UI. As described above if the trigger is received while viewing a broadcast program the receiver may check whether the trigger is for the second screen device or the primary device. At this time if the trigger is for the second screen device all UPnP devices or only a specific UPnP device may be notified of new UI information update. This may correspond to the case in which the second screen device subscribes using the UPnP protocol.

Requesting updated UI information s may include the second screen device requesting updated UI information from the primary device.

Transmitting compatible UI information as a response s may include the primary device transmitting compatible UI information to the second screen device.

Receiving another trigger for the receiver s may be equal to receiving a trigger for the receiver s . That is the above described operation may be performed again.

Since the receiver may include a trigger module the receiver may receive an XML file such as TPT and AMT over a broadcast network or an Internet network parse the XML file and perform an appropriate operation. If the second screen device is found Action TDO URL and Data delivered to the second screen device may be recognized using an Event Destination field. The second screen device may not directly receive the XML file such as TPT or AMT and thus may not include the trigger module. If a RemoteUI Client Service is included the receiver may manage the lifecycles of all second screen applications. In contrast if several second screen devices are connected data for controlling the second screen application should be transmitted several times.

Unlike shows the case in which all UI information for the second screen device which is determined to be suitably used for the second screen device is directly delivered. That is TDO URLs for the second screen device may be transmitted.

This process may include receiving a trigger for the receiver s receiving a trigger for the second screen service s notifying about UI information s sending a response ok s receiving a trigger for the receiver s receiving a trigger for the receiver s receiving a trigger for the second screen service s notifying about UI information s and or sending a response ok s .

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s .

Sending a response ok s may include transmitting a message indicating that UI notification has been received.

Receiving a trigger for the receiver s and receiving a trigger for the receiver s may be equal to receiving a trigger for the receiver s . That is the above described operation may be performed again.

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s . That is the above described operation may be performed again.

Notifying about UI information s may be equal to notifying about UI information s . That is the above described operation may be performed again.

Sending a response ok s may be equal to sending a response ok s . That is the above described operation may be performed again.

In the method of the receiver should know which UPnP device is a second screen device and which device profile is included. In particular the receiver should know whether the second screen device supports the second screen service.

The method the case of of notifying about UI information after determining whether the trigger is for the second screen device or the primary device and the method the case of of delivering all UI information for the second screen device which is determined to be suitably used for the second screen device may be equal in that the receiver processes the TPT and the trigger and delivers only the TDO URL to the second screen device. These two methods may differ in that the receiver indirectly delivers the TDO to the second screen device or the receiver directly records the device profile of each device and notifies only the second screen device of the location of the second screen application.

One embodiment of broadcast signaling for RemoteUI Server Service may include UPnP device and service discovery s requesting UIListing s sending UIListing s subscribing to an event s returning an HTTP message s sending a UIListingUpdate message s requesting UIListing s and or returning UIListing s .

UPnP device and service discovery s may include discovering the receiver and the second screen device. A device newly connected to the home network or a device already connected to the home network the receiver or the second screen device may multicast a message for discovery. At this time a desired service may be searched for using multicasting and all services may be searched for with respect to a plurality of unspecific UPnP devices. This may be changed depending on which service is provided by the device. In this step the second screen device may be aware of the device profile of the primary device. The primary device can process the device profile and build the appropriate UIListing. The RemoteUI Server can give the second screen device the CompatibleUIs XSD schema. This schema can include the URL of Application unique id for this UI uiID name protocolInfo and so on.

Requesting UIListing s may include the second screen device transmitting the device profile thereof and requesting UIListing. A GetCompatibleUIs action capable of obtaining a compatible UI may be used. The UIFilter can be optional A detailed description thereof will be given below.

Sending UIListing s may include the primary device transmitting appropriate UI listing to the second screen device according to the request. A detailed description thereof will be given below.

Subscribing to an event s can include subscribing to a proper exposed Event of the primary device. Subscribing to an event s may be selectively performed in order to receive UIListingUpdate which is event information provided by the RemoteUI Server Service. In returning UIListing s the second screen device may be notified that the address of RemoteUI has been changed or the UI has been changed. That is since the second screen device is notified only that the UI has been changed if detailed location or additional information is required the GetCompatibleUIs Action should be transmitted to the receiver to obtain the UIListing value.

Returning an HTTP message s may include sending a result of subscribing to an event s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

Sending a UIListingUpdate message s may include transmitting a UIListingUpdate message to subscribers.

Requesting UIListing s may include the second screen device transmitting the device profile thereof and requesting UIListing. A GetCompatibleUIs action capable of obtaining a compatible UI may be used. Sending a UIListingUpdate message s and requesting UIListing s may include performing time setting such that the second screen application is not changed and are selectively possible only when supported by the server. This step is optional. This method may be a method of at the receiver notifying all second screen devices that the second screen service is present using the UPnP event. That is all second screen devices in the home network may be notified that the UI has been changed in association with the second screen service. If all second screen devices are notified of a UIListingUpdate variable using the UPnP event the second screen devices may confirm that the UI has been newly updated. Thereafter the second screen device may perform the GetCompatibleUIs Action select a UI suitable for the hardware device and execute the UI by referring to the device profile.

Returning UIListing s may include the primary device transmitting appropriate UI listing to the second screen device according to the request. As described above returning UIListing s may include notifying the subscribing second screen device that the address of RemoteUI has been changed or the UI has been changed. That is since the second screen device is notified only that the UI has been changed if detailed location or additional information is required a GetCompatibleUIs Action should be transmitted to the receiver to obtain the UIListing value.

When the RemoteUI Server Service operates the receiver should provide remote UI information according to the device profile of the requesting device. From the viewpoint of backward compatibility the device profile DeviceInfo is exchanged and the URL sent by the RemoteUI Server Service may be changed according to the profile of the requesting client when requesting GetCompatibleUIs action from the receiver later. If the legacy UPnP device requests the GetCompatibleUIs action from the RemoteUI Server a UI suitable for DeviceInfo of the legacy UPnP device should be provided. However if the device supporting the second screen service requests the GetCompatibleUIs action the RemoteUI Server Service device should also transmit URL information.

The receiver may obtain trigger information via the DTVCC and obtain media time and event time information from the trigger information. At this time appID URL TDO URL eventID action and optionally Data for TDO or an execution time may be confirmed using the t media time syntax. If the receiver manages the lifecycle of the second screen application the amount of information to be processed by the second screen service application may be reduced. In contrast if the second screen service application directly manages the lifecycle of the second screen application necessary information may be increased.

As a method of efficiently delivering the interactive service to the second screen device the distributed execution model will be described.

As shown in the diagram showing the operational concept of the Distributed Execution model a TV set may deliver information such as a trigger to the second screen device using UPnP etc. Each second screen device has a trigger handler and may process information such as a trigger received via the trigger handler in real time. The browser may execute an interactive service associated therewith.

A process of delivering an interactive service to a second screen device based on Distributed Execution model may be performed in the following order. 1. Receiver is presenting segment with 2nd screen support. 2. Receiver displays some indication that 2nd screen support is available. 3. User launches 2nd Screen app on 2nd screen device. 4. Receiver and 2nd Screen device discover each other via UPnP mechanisms performed by native code on receiver and 2nd Screen app on device . 5. TV set gets Trigger from DTVCC stream or ACR to launch TDO on 2nd Screen device. 6. TV set combines Trigger with info from TPT and sends to 2nd Screen device at activation time. 7. 2nd screen device downloads TDO one or more files and executes it in browser. 8. User interacts with TDO which may cause TDO to download additional files. 9. Receiver gets Trigger to generate Event for TDO on 2nd Screen device. 10. Receiver combines Trigger with info from TPT and sends to 2nd screen device at activation time. 11. 2nd screen device generates TriggerEvent like DVB StreamEvent for TDO in browser. 12. TDO carries out action requested by TriggerEvent which may cause it to download data file s 

The flow of the distributed execution model may be a data flow in the case in which the receiver transmits the information received via the DTVCC or ACR server to the second screen without change. The detailed flow will now be described.

The embodiment of the flow for interworking between the distributed execution model based receiver and the second screen may include sending a time base trigger s sending a time base trigger s requesting a TPT s transmitting a TPT as a response s parsing a TPT s sending an execute trigger for a second screen s sending an execute trigger s downloading TDOs Files s executing a TDO in browser s user clicking a link for a new page s downloading a new TDO file s and or executing a new TDO in browser s .

Sending a time base trigger s may include the receiver transmitting the received trigger to the second screen without change.

Requesting TPT s may include the second screen interpreting the received trigger acquiring a URL of a service capable of acquiring a TPT and requesting the TPT.

Transmitting a TPT as a response s may include transmitting the TPT in response to the request in requesting TPT s .

Sending an execute trigger for a second screen s may be equal to sending an execute trigger for a second screen s .

Sending an execute trigger s may include the receiver transmitting the received trigger to the second screen without change.

Downloading TDOs files s may include the second screen acquiring TDOs files associated with the trigger from the TPT and downloading the TDOs files from the content server.

User clicking a link for a new page s may include the user clicking a specific link on the executed TDO.

Downloading a new TDO file s may include downloading the associated TDO file if a specific link to another TDO is established.

The flow of the distributed execution model may be a data flow in the case in which the receiver does not transmit the information received via the DTVCC or ACR server to the second screen without change but inserts necessary information according to a trigger suitable for the second screen changes the information to an expanded trigger and transmits the information to the second screen. The detailed flow will now be described.

The embodiment of the flow for interworking between the distributed execution model based receiver and the second screen may include sending a time base trigger s requesting a TPT s transmitting a TPT as a response s parsing TPT s sending an execute trigger for a second screen s generating an expanded trigger s sending an expanded trigger s downloading TDOs Files s executing a TDO in browser s user clicking a link for a new page s downloading a new TDO File s and or executing a new TDO in browser s .

Sending an execute trigger for a second screen s may be equal to sending an execute trigger for a second screen s .

Generating an expanded trigger s may include the receiver acquiring information about TDOs and files associated with the trigger from the TPT and generating an expanded trigger including the same.

Sending an expanded trigger s may include the receiver transmitting the generated expanded trigger to the second screen.

This process may include receiving a trigger for the receiver s receiving a trigger for the second screen service s translating a TPT and a trigger and generating event information s sending TDO and event information s sending a response ok s receiving a trigger for the receiver s receiving a trigger for the receiver s receiving a trigger for the second screen service s translating a TPT and a trigger and generating event information s sending TDO and event information s and or sending a response ok s .

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s .

Translating a TPT and a trigger and generating event information s may include interpreting the TPT and the trigger and generating event information. The generated information may be used to combine the information included in the TPT and trigger for generation of a new data structure and may include information about which TDO was generated or when the TDO was generated. This data structure will be described below. If the new data structure is decided a variety of necessary information may be transmitted in addition to the TDO URL.

Sending TDO and event information s may include transmitting the generated event information and TDO to the second screen device.

Sending a response ok s may include transmitting a message indicating that the received TDO and event information have been received.

Receiving a trigger for the receiver s and receiving a trigger for the receiver s may be equal to receiving a trigger for the receiver s .

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s .

Translating a TPT and a trigger and generating event information s may be equal to translating a TPT and a trigger and generating event information s .

Receiving a trigger for the receiver s receiving a trigger for the receiver s receiving a trigger for the second screen service s translating a TPT and a trigger and generating event information s sending TDO and event information s and sending a response ok s may be equal to the above described operations.

The second screen device is an independent device which may directly execute the second screen application if the receiver receives the XML file such as TPT and AMT or knows the TPT and AMT server address via the Internet. In this case the trigger module is included in the second screen device. The second screen device may receive the URI string for an iTV message received by the receiver. This message is applicable to both 1 the method of transmitting the URI string for the iTV message trigger in case of RemoteUI Server Service and 2 the method of transmitting the URI string for the iTV message trigger in case of RemoteUI Client Service.

First the method of transmitting the URI string for the iTV message trigger in case of RemoteUI Server Service will be described.

This process may include receiving a trigger for the receiver s receiving a trigger for the second screen service s sending notification about updated UI information s requesting updated UI information s transmitting UI information as a response s requesting a TPT XML file s returning a TPT XML file s receiving a trigger for the second screen service s sending notification about updated UI information s requesting updated UI information s transmitting UI information as a response s receiving a trigger for the second screen service s sending notification about updated UI information s requesting updated UI information s transmitting UI information as a response s requesting a second screen application s and or returning a second screen application s .

Receiving a trigger for the receiver s may be equal to receiving a trigger for the receiver s . Since the first trigger is not for the second screen device the receiver does not deliver the trigger to the second screen device.

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s . The trigger may have information about a media time for the second screen service. The second trigger may serve as the above described pre load trigger.

Sending notification about updated UI information s may include notifying about updated UI information. The receiver may transmit the received URIString to the second screen device because the second trigger is for the second screen service. At this time the second screen device may be informed that new information is present and may be enabled to directly read this information.

Transmitting UI information as a response s may include the primary device transmitting UI information to the second screen device. At this time the second trigger may be transmitted.

Requesting a TPT XML file s may include the second screen device parsing the information second trigger received from the primary device and requesting a TPT XML file from the TPT server.

Returning a TPT XML file s may include the second screen device downloading the requested TPT XML file from the TPT server.

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s . The third Trigger is associated with the second screen device and may have information regarding a media time. The third trigger is a media time trigger which may perform the same function as the above described time base trigger.

Sending notification about updated UI information s may include notifying about updated UI information. Since it is determined that the third trigger is associated with the second screen device the receiver may notify the second screen device about the third trigger.

Transmitting UI information as a response s may include the primary device transmitting UI information to the second screen device. At this time the third trigger may be transmitted. However since the third trigger is a media time trigger it is possible to control only the media time of the second screen device. Therefore it is possible to perform media time synchronization between the second screen device and the receiver.

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s . The fourth trigger is associated with the second screen device and may have information about an event time. The fourth trigger is an event time trigger which may perform the same function as the above described activation trigger.

Sending notification about updated UI information s may include notifying updated UI. Since it is determined that the fourth trigger is associated with the second screen device the receiver may notify the second screen device of the fourth trigger.

Transmitting UI information as a response s may include the primary device transmitting UI information to the second screen device. At this time the fourth trigger may be transmitted.

Requesting a second screen application s may include the second screen device checking information about the fourth trigger and requesting the second screen application from the application server in order to download the second screen application of the location of the TDO URL.

Returning a second screen application s may include downloading the second screen application according to the request. The second screen application may be downloaded to perform Event Action. At this time since the application server is informed of the information about the browser of the second screen device the application server may easily check which second screen device is connected. Accordingly the application may be automatically selected and downloaded from the server.

In summary if the URI string for the iTV message is received via the DTVCC the receiver may transmit to the found second screen device an event indicating that a new UI has been updated. The second screen devices may check the event information and send a GetCompatibleUIs Action in order to obtain new UI information. The receiver may send the received URI information of the TPT server. By this method the second screen device may receive the URI information directly process the TPT and AMT information and directly control the second screen application.

This process is possible if the ATSC 2.0 Trigger Client is included in the second screen service application.

Between the above described two methods the method of transmitting the URI string for the iTV message Trigger in case of RemoteUI Client Service will be described.

This process may include receiving a trigger for the receiver s receiving a trigger for the second screen service s notifying about a trigger s sending a response ok s requesting a TPT XML file s returning a TPT XML file s receiving a trigger for the second screen service s notifying about a trigger s sending a response ok s receiving a trigger for the second screen service s notifying a trigger s sending a response ok s requesting a second screen application s and or returning a second screen application s .

Receiving a trigger for the receiver s may include the primary device receiving the trigger for the receiver that is the primary device from the broadcaster via the broadcast stream. Since the first trigger is for the receiver the first trigger is not delivered to the second screen device.

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s . The second trigger is a trigger for the second screen service and may have information about a media time. The second trigger may serve as the above described pre load trigger.

Notifying about a trigger s may include the receiver immediately transmitting the trigger to the second screen device unlike . If URI string for the iTV message is received via the DTVCC the receiver may deliver the URI value received by the receiver to the second screen device using the AddUIListing Action.

Sending a response ok s may include transmitting a message indicating that the trigger has been received.

Requesting a TPT XML file s may be equal to requesting a TPT XML file s . The trigger module included in the second screen device may access the TPT server using the received URI value download the TPT and AMT file and directly control the second screen application.

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s . The third trigger is associated with the second screen device and may have information about a media time. The third trigger is a media time trigger which may perform the same function as the above described time base trigger.

Notifying about a trigger s may include delivering the trigger similarly to notifying about a trigger s .

Receiving a trigger for the second screen service s may be equal to receiving a trigger for the second screen service s . The fourth trigger is associated with the second screen device and may have information about an event time. The fourth trigger is an event time trigger which may perform the same function as the above described activation trigger.

Notifying about a trigger s may include delivering the trigger similarly to notifying about a trigger s .

That is the receiver may always deliver the trigger having the event information associated with the second screen service to the second screen device and the second screen device may immediately operate using the downloaded TPT information. Since the media time trigger is periodically delivered using the DTVCC the receiver should continuously deliver this information.

Since the primary device or the second screen device has the TPT XML the AMT may also be received when the event trigger is received from the Live Trigger server in real time.

The above described two methods may be differently performed depending on which URL value is applied and the operation of the receiver or the structure and operation of the second screen service application may be changed.

The second screen service may be signaled using two methods a first method of at the receiver notifying that the second screen service is present and a second method of searching for a device and service in order to detect an electronic apparatus for providing the second screen service when the second screen device is connected to the home network. Alternatively the receiver may confirm a device descriptor of a new electronic apparatus and request a service descriptor.

In case of Broadcast Signaling the second screen device detects the RemoteUI server service confirms the device descriptor and requests a DeviceInfo profile compatible with the second screen service. An event may be received and a URL of a TDO interactive application changed according to a program viewed via the receiver may be received.

In contrast in case of Unicast Signaling the receiver may confirm whether DeviceInfo of the second screen device is compatible and transmit a compatible TDO URL. The RemoveUIListing Action may be transmitted to terminate the currently executed second screen application so as to support actions such as display message and to terminate a currently executed UI. Supplementary Event data parsed and processed by the receiver may be delivered to the second screen service application by the ProcessInput Action.

In broadcast signaling if the receiver is first connected to the home network the receiver may notify all electronic apparatuses of the device descriptor and service descriptor thereof or receive a request from another control point and transmit the device descriptor and service descriptor thereof.

Another embodiment of the broadcast Signaling for the RemoteUI Server Service may include UPnP device and service discovery s sending UIListing s sending UIListing s requesting UIListing s and or returning UIListing s .

Sending UIListing s may include transmitting a UIListingUpdate message to all UPnP devices. The primary device can send announcement of the UIListingUpdate to UPnP Devices on a unique uiID list. The second screen device may receive this message and check uiID. However due to mismatching with a specific uiID the second screen device may not perform UI update.

Sending UIListing s may include transmitting a UIListingUpdate message to all UPnP devices. Unlike sending UIListing s matching uiID may be present.

Requesting UIListing s may include the second screen device transmitting the device profile thereof and requesting UIListing because the matching uiID is present in sending UIListing s . The GetCompatibleUIs action capable of obtaining a compatible UI may be used.

Returning UIListing s may include the primary device transmitting appropriate UI Listing to the second screen device according to the request.

As described above if the receiver is first connected to the home network the receiver may notify all electronic apparatuses of the device descriptor and service descriptor thereof or receive a request from another control point and transmit the device descriptor and service descriptor thereof.

Each UPnP devices connected to the home network which receive the device descriptor and service descriptor of the receiver may send the location of the device descriptor thereof using the LOCATION header of the HTTP. That is the UPnP device may transmit the location of the UPnP device descriptor. If an HTTP GET request is made using LOCATION an XML file including information about the device may be received.

In the UPnP device and service discovery a method of at the primary device detecting the second screen device capable of providing the second screen service will be introduced. This method may be largely divided into two methods. As a first method the second screen device prepares two device profiles and notifies about an XML file of the device profiles using an HTTP header. Assume that an incompatible primary device ignores an uncomprehended HTT header. As a second method in the device profile information called the second screen device for providing the second screen service may be included in Protocol Info .

One embodiment of device discovery and device capability exchange for the second screen service may include executing a UPnP application for the second screen service s finding UPnP devices s finding a RemoteUIClient s requesting a device description s receiving a device description s requesting a service control description s receiving a service control description s requesting a device profile s receiving a device profile s putting a URL of a remote UI s sending a response1 s sending a message to the RemoteUI Client Service s sending a response2 s and or user clicking the button on the screen s .

Executing a UPnP application for the second screen service s finding UPnP devices s finding a RemoteUIClient s requesting a device description s receiving a device description s requesting a service control description s receiving a service control description s requesting a device profile s receiving a device profile s putting a URL of a remote UI s sending a response1 s sending a message to the RemoteUI client service s sending a response2 s and user clicking the button on the screen s may be equal to executing a UPnP application for the second screen service s finding UPnP devices s finding a RemoteUIClient s requesting a device description s receiving a device description s requesting a service control description s receiving a service control description s requesting a device profile s receiving a device profile s putting a URL of a remote UI s sending a response1 s sending a message to the RemoteUI Client Service s sending a response2 s and user clicking the button on the screen s respectively.

In the first method as shown in after finding UPnP devices s notification about the location of the device profile supporting the second screen service using X ATSC COMPANION LOCATION obtained from the HTTP Header may be performed. The part represented by X ATSC COMPANION LOCATION http 10.177.56.36 37900 ATSC2ndScreenRemoteUIClient1.xml r n is an X ATSC COMPANION LOCATION . The receiver may ignore the LOCATION header and instead obtain the device profile of the second screen device which is desired by the receiver.

Among the method of the primary device detecting the second screen device capable of providing the second screen service in the above described second method the device profile may be obtained at the location of the LOCATION header and the value of the Protocol Info of the second screen device may be parsed and processed within the device profile. This may be performed in requesting UIListing s of the embodiment of broadcast signaling for RemoteUI Server Service 1.

In the device descriptor of a specific UPnP device a list of providable services is present and one or a plurality of services may be provided. Each service of the UPnP device may be controlled by another remote UPnP device and an event may be received. The event may be received only when notifying about the provided service using the event. It is possible to notify about the URL such that the services provided by the UPnP device are controlled and an event is generated.

In the embodiment of broadcast signaling for RemoteUI Server Service 1 requesting UIListing s will be additionally described. This step may include the second screen device asking the receiver having the RemoteUI server service whether a UI suitable for the second screen device is present. The InputDeviceProfile should be in the format of an XSD file shown in .

Accordingly the second screen device should transmit information about the device profile thereof to the receiver in the format of .

In the embodiment of broadcast signaling for RemoteUI Server Service 1 requesting UIListing s will be additionally described. shows an example of a device profile. In requesting UIListing s the information such as the shown device profile may be sent to the receiver.

By determining whether the second screen service of the device profile which is desired to be detected by the second screen device is present in the receiver the shown information may be stored in the InputDeviceProfile variable and may be transmitted. The receiver may confirm the InputDeviceProfile information so as to define service type to be provided version resolution of the second screen device a receivable image encoding method etc.

In the embodiment of broadcast signaling for RemoteUI Server Service 1 requesting UIListing s and Sending UIListing s will be additionally described.

As described above the receiver may confirm the InputDeviceProfile information so as to define service type to be provided version resolution of the second screen device a receivable image encoding method etc. One embodiment of A description of Protocolnfo for Second Screen Service may be one embodiment of InputDeviceProfile information.

When the shown information is delivered to the receiver requesting UIListing s UILising information in XML is transmitted to the second screen device sending UIListing s .

If the RemoteUI server service does not support the desired second screen device in sending UIListing s error information may be returned to indicate that the RemoteUI server service cannot support the second screen service.

In the embodiment of broadcast signaling for RemoteUI Server Service 1 requesting UIListing s and Sending UIListing s will be additionally described.

After requesting UIListing s the receiver may detect and deliver compatible RemoteUI information to the requesting second screen device sending UIListing s . The information received in sending UIListing s is shown in .

When the received information may be transmitted from the receiver to the second screen the TPT and the AMP may be processed to insert the TDO URL. Accordingly the second screen device may obtain only the information about the remote UI from the receiver and the second screen application may be downloaded and executed from the Internet application server outside the home network. At this time the application may be executed by the second screen service application.

The broadcaster may transmit the second screen application for the second screen device to the receiver over the broadcast network. In this case the receiver may store the application for the second screen service and directly provide the application. In this case the web server may operate in the receiver and associated image and data may be downloaded from an external application server instead of the receiver or the home network. If the DO is an NDO NDO and associated resource files may be transmitted over the broadcast network in ATSC NRT and the second screen service may be provided.

In case of broadcast signaling the lifecycle of the second screen application may be managed by the receiver or the second screen service application.

First the method of at the receiver managing the lifecycle of the second screen application will be described.

The receiver may process information about the media time trigger transmitted using the DTVCC and then immediately notify all devices in the home network of the UIListingUpdate variable when the event associated with the second screen is present and this event is executed. The devices that subscribe to the event may check that UI information has been updated and perform the GetCompatibleUIs action in order to obtain necessary information. At this time the RemoteUI server of the receiver may immediately deliver the TDO address.

Second the method of at the second screen service application managing the lifecycle of the second screen application will be described.

In this case the receiver may deliver the received information to the second screen device and the second screen service application may be executed. In case of broadcasting if the client for the second screen service requests the GetComaptibleUIs action the receiver may directly return the URIString of an iTV message Trigger received via the DTVCC and the second screen device may download the TPT file using the received URIString and interpret the TPT to operate similarly to the receiver. The receiver may immediately change the UIListingUpdate variable and transmit the changed variable to all devices whenever the media time trigger or the event time trigger is received using the DTVCC such that the devices perform the GetCompatibleUIs action so as to receive the new URIString of the iTV message Trigger .

In this method RemoteUIClient service is included in the second screen device. If the UPnP device is first connected to the home network the UPnP device notifies the other devices that the new device has been connected to the home network. As another method if a message requesting periodic notification about a new device is delivered to all devices connected to the home network all the devices connected to the home network may send a NOTIFY message to all the devices in response to this information. First whether the second screen device supports the second screen service should be determined.

One embodiment of unicast Signaling for the RemoteUI client service may include UPnP device and service discovery s requesting a device profile s returning a device profile s sending TDO URL information s returning an HTTP message s sending a display message s and or returning an HTTP message s .

Requesting a device profile s may include the receiver transmitting StaticDeviceInfo information to the newly detected second screen device in order to determine whether the second screen device supports the second screen service.

Returning a device profile s is a response to requesting a device profile s which obtains the device profile of the second screen device. If it is determined that the device profile sent by the newly detected second screen device does not match Static DeviceInfo or the newly detected second screen device does not support the second screen service the second screen service may not start. StaticDeviceInfo may be equal to the above defined DeviceInfo . The receiver may determine whether StaticDeviceInfo matches DeviceInfo. If the number of second screen devices newly detected in the home network is one or more this process is repeated. Even when the detected second screen device does not support the second screen service this process is continuously performed. One or more pieces of software may be installed in or deleted from the second screen device and the result value of this process may be changed depending on whether the user executes software. If the second screen service application has been performed sending TDO URL information s may be performed.

Sending TDO URL information s may include the receiver transmitting TDO URL information which is the result of parsing the TPT and AMT. AddUIString defined in the UPnP RemoteUI client service may be used. AddUIString may be an action executed if the second screen device satisfies DeviceInfo of the second screen service. The TDO URL may include one or more URLs. In case of one or more URLs the URL for immediate execution may be transmitted. At this time sending a display message s may be selectively performed.

Returning an HTTP message s may include sending the result of sending TDO URL information s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

Sending a display message s may include transmitting the display message to the second screen device. Since the RemoteUI client service has a DisplayMessage Action capable of displaying a message on the screen of the second screen device the TDO URL may be transmitted to the second screen device and a message indicating that the second screen application associated with the currently viewed broadcast program is present may be displayed using the DisplayMessage Action. If the user confirms this message the second screen application may be immediately executed.

Returning an HTTP message s may include transmitting the result of sending a display message s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

Whenever the URL of a new UI is added to UIListing of the second screen device the second screen service application may provide an environment in which the new second screen application is executed.

One embodiment of unicast Signaling for the RemoteUI client service of shows the process of terminating the executed second screen application and executing the new second screen application.

One embodiment of unicast Signaling for the RemoteUI client service may include sending a RemoveUIListing action s returning an HTTP message s sending a display message s returning an HTTP message s sending TDO URL information s returning an HTTP message s sending a display message s and or returning an HTTP message s .

Sending a RemoveUIListing action s may include terminating the second screen application which is being executed in the second screen service application using the RemoveUIListing action defined in the RemoteUI client service. The second screen service application may be aware that the RemoveUIListing action is sent when the receiver terminates use of the currently executed application of the UI. Accordingly the second screen service application should immediately terminate the currently executed second screen application if the second screen device receives the RemoveUIListing action.

Returning an HTTP message s may include sending the result of sending a RemoveUIListing action s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

Sending a display message s may include sending a display message to the second screen device. After sending a RemoveUIListing action s a message indicating execution termination may be displayed on the screen of the second screen device. In this case an appropriate message may be displayed on the screen using the DisplayMessage Action.

Returning an HTTP message s may include sending the result of sending a display message s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

Sending TDO URL information s may include performing the AddUIListing action such that the receiver transmits the TDO URL of the UI to be newly performed. When the new second screen application is executed the second screen service application may be executed as soon as the TDO URL is added to UIListing. For reference the TDO URL relates to the second screen application which may be directly downloaded and executed from the receiver or only some resource data may be downloaded from the Internet server. In addition the TDO URL may indicate an external Internet server address. If the TDO URL indicates the external Internet server address the second screen application and all data necessary for execution may be downloaded from the Internet server.

Returning an HTTP message s may include sending the result of sending TDO URL information s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

Sending a display message s may include sending the display message to the second screen device. After sending TDO URL information s a message indicating that a new second screen service is provided may be displayed on the screen of the second screen device. Similarly to sending a display message s an appropriate message may be displayed on the screen using the DisplayMessage Action.

Returning an HTTP message s may include sending the result of sending display message s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

In case of unicast signaling the lifecycle of the second screen application may be managed by the receiver or the second screen service application.

First the method of at the receiver managing the lifecycle of the second screen application will be described.

The second screen service application may be aware of only URL TDO URL information. Accordingly the receiver may perform the AddUIListing action with respect to the RemoteUI client service in the second screen device and execute the second screen application in the second screen device at a predetermined time. If the second screen application is terminated the RemoveUIListing action may be performed to terminate the second screen application within a predetermined time.

If media time information for performing a TDO is provided in addition to a URL for detailed timing the second screen service application may be executed at a predetermined time. However since the media time is a relative time of media which is currently being played back by the receiver this time needs to be changed to an absolute time understood by each device. Network time protocol NTP or other time information may be used and a time when the action is performed may be obtained by adding the media time having future time information to the NTP or the other time information. In the second screen device since the action includes execution and termination this may be changed according to implementation of the AddUIListing and RemoveUIListing action.

Second the method of at the second screen service application managing the lifecycle of the second screen application will be described.

The second screen service application should be aware of information regarding an event or a time when the second screen application is executed and terminated in the second screen device. Therefore as described above the second screen service application includes the trigger client and the receiver may transmit the URIString of the iTV message Trigger information received using the DTVCC according to DeviceInfo Device Profile of the receiver.

The transmission method may be largely divided into two methods a first method of transmitting a trigger message transmitted using the DTVCC and processed by the receiver without change and a second method of at the receiver collecting only information necessary for the second screen device and delivering only necessary information and data in XML.

First the method of at the receiver delivering the trigger to the second screen device without change will be described.

This method may be finished by performing the AddUIListing action with respect to the received trigger. The RemoteUI Client Service may deliver this information to the trigger client and the trigger client may download and process a TPT as in the receiver. The receiver should deliver the media time trigger to the second screen device whenever the media time trigger is received using the DTVCC. The receiver may confirm appID eventID and event destination and may not deliver the trigger to the second screen device if the second screen device does not need to receive the trigger.

Second the method of at the receiver filtering and delivering the trigger information necessary for the second screen device will be described.

In this method the receiver may process the TPT file and the trigger and generate and deliver data to be processed by the second screen device. This method may be performed even when the trigger client does not operate in the second screen service application and the XML file may be transmitted and processed via the ProgressInput action. That is the second screen service application does not process the overall TPT and process only data necessary for current or future processing which is filtered by the receiver. This method is advantageous in that the Event Data field may also be delivered.

One embodiment of unicast signaling for the RemoteUI client service may include sending event 1 information s returning an HTTP message s sending event 2 information s returning an HTTP message s sending event 3 information s and or returning an HTTP message s .

Sending event 1 information s may include the receiver sending the received event information to the second screen. As described above the receiver may process the TPT file and the trigger and generate and deliver data to be processed by the second screen device. In the second screen service application the trigger client may not operate and the XML file may be received and processed via the ProgressInput action.

Returning an HTTP message s may include sending the result of sending event 1 information s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

Sending event 2 information s may include sending information about the event similarly to sending event 1 information s . As in TPT XML data may be delivered to the TDO according to event. In this step information about event 2 may be delivered.

Returning an HTTP message s may include sending the result of sending event 2 information s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

Returning an HTTP message s may include sending the result of sending event 3 information s . Similarly to sending a response1 s a response such as HTTP 1.1 200 OK may be sent according to circumstance.

In the above described second method the receiver may manage the lifecycle of the second screen application. The lifecycle of the second screen application may mean the process of parsing and processing the TPT and the AMT information of the second screen device.

That is if the receiver manages the lifecycle of the second screen application the event information may be delivered to the RemoteUI client via the XML file having the data structure of using the processInput action. Even when the receiver receives the live trigger similarly the live trigger may be processed and only information about an execution time and a TDO URL may be delivered to the second screen device.

In the table of appID URL Event eventID action and Data may be equal to the information about the trigger or AMT received by the receiver. However mediaTime startTime and endTime should be specially processed by the receiver. According to mediaTime the information of time syntax or beginMT information of the AMT of the trigger transmitted using the DTVCC may be processed to determine startTime and endTime again. Since the receiver and the second screen device may not use the same absolute time information wall clock time the second screen device may operate according to the media time of the content. That is if it is assumed that the time information such as an execution start time and end time of the action are set between the receiver and the second screen device according to the actual NTP a conversion operation may be performed by the receiver before transmission.

As described above since startTime and endTime are relatively created and transmitted based on a current mediaTime value when being transmitted from the receiver to the second screen device time loss generated upon transmission may be the Date value of the HTTP header and the HTTP response. Using a difference in arrival time value the second screen device may find a more accurate time value. Since the difference between the current media time and mediaTime is a transmission delay time the current media time may be obtained by the following equation. current media time transmission delay time time value upon reception HTTP header Date value mediaTime

The configuration between the receiver and the second screen device is shown. The receiver can be a Controlled Device Server . A second Screen Device can be a Control Point Client .

In the discovery step the receiver may multicast a service list and join a network and the second screen app may multicast a request for the service list and start up.

In the present invention a new UPnP device and service may be defined in order to via the second screen device acquire an interactive service associated with A V broadcast content received via a TV set that is a receiver based on UPnP.

A Receiver can support a Trigger service a Two Way Communication service and an AppURL service. It may also support an HTTP Proxy Server service. Service types and service IDs are shown in .

The two way communication service can allow second screen devices to determine whether there is a DO being executed by the primary device that is prepared to engage in two way communication with applications in second screen devices.

The trigger delivery service may mean a service for via the second screen device acquiring the interactive service associated with the A V broadcast content received via the TV receiver based on UPnP.

Whenever the trigger is changed the trigger or the expanded trigger should be transmitted from the receiver to the second screen device in real time.

The expanded trigger expanded activation trigger may be generated by combining the trigger acquired from the DTVCC stream or the ACR Server and the information in the TPT. The expanded trigger may be generated by combining the TDO ID and Event ID Data ID and Activation time included in the trigger and TDO URL TDO attributes Event Action Diffusion and data in the TPT. The information in the TDO may be information about TDO and event associated with the information in the trigger.

The Trigger service can deliver Triggers. Triggers can be acquired by the TV set from a ACR process b DTV CC service 6 of the channel currently being viewed c Remote live trigger server or d Activation Messages Table AMT . It can depend on the circumstances.

The Trigger Service can also deliver a special channel change Trigger whenever the channel is changed. The channel change trigger will be described below. There can be basically four types of Triggers to be delivered 1 Time Base Triggers for TDO interactive service model 2 Activation Triggers for TDO interactive service model 3 Triggers for Direct Execution interactive service model and 4 Special channel change Triggers.

For maximum flexibility it can be desirable to have the option of delivering all types of Triggers to second screen devices and to deliver them as soon as they arrive at the Receiver.

However for second screen applications that are designed to provide interaction in much the same way as receivers provide interaction it can be desirable to omit the Time Base Triggers for the TDO interaction model and to deliver each Activation Trigger for the TDO interaction model at its activation time This can save these second screen applications from the need to maintain time bases and calculate activation times. It can be also desirable to augment each Activation Trigger by combining information from the Trigger with information from the TPT about the TDO element and its Event child element referenced in the Trigger thereby saving these second screen applications from the need to deal with the TPT.

Therefore the Trigger service can offer two options for Trigger delivery. One of them can be a Unfiltered stream option that receiver delivers all Triggers with no augmentation . And the other can be Filtered stream option that delivers only Augmented Activation Triggers for the TDO interaction model All triggers for interaction models other than the TDO interaction model and Special channel change Triggers.

The target delivery time for each Augmented Activation Trigger for the TDO interaction model can be its activation time. The target delivery time for all other Triggers including Activation Triggers delivered without augmentation in the unfiltered stream option can be the time they are received by the Receiver. The target delivery time of each special channel change Trigger can be the time of the channel change.

The trigger delivery format of the trigger service may be divided into the delivery format for an Augmented Activation Trigger and the delivery format for all other Triggers.

The delivery format for an Augmented Activation Trigger may include interactionModel appURL and or cookieSpace attributes and Capabilities and or Event element.

The value of the interactionModel attribute can be the numerical code for the interaction model associated with the Trigger using the same coding as for the cmdID field in the SDOPrivateData command in Service 6 of the DTVCC channel used to deliver the Trigger.

The value of the appURL attribute can be the value of first URL child element of the TPT TDO element that is identified by the event e term in the Trigger.

The cookieSpace attribute can be present whenever the TPT TDO element that is identified by the event e term in the Trigger contains a cookieSpace attribute and it can have the same value as that attribute.

The Capabilities element can be present whenever the TPT TDO element that is identified by the event e term in the Trigger contains a Capabilities element and it can be identical to that element.

The Event element can represent the Event element identified by the event e term in the Trigger. Strictly speaking the event term in the Trigger identifies a TDO element in the TPT and an Event child element of that TDO element. This is referred to here as the Event element identified by the event term in the Trigger. 

The value of the action attribute can be the same as the value of the action attribute of the Event element identified by the event e term in the Trigger.

The destination can be present whenever the Event element that is identified by the event e term in the Trigger contains a destination attribute and it can have the same value as that attribute.

The diffusion attribute can be present whenever the Event element that is identified by the event e term in the Trigger contains a diffusion attribute and it can have the same value as that attribute.

The data attribute can be present whenever a Data child element of the Event element is identified by the e term in the Trigger and it can have the same value as that element.

As described above the augmented trigger may be generated by combining the information in the TPT and the trigger acquired from the DTVCC stream or the ACR Server.

This may be an XML format of the trigger which is not augmented. The above described special channel change Trigger may also follow this format.

One embodiment of XML Schema Description for Triggers that are not augmented may include interactionModel attribute and or triggerString attributes.

The interactionModel attribute cannot be present for a special channel change trigger. For other Triggers the interactionModel can be present and its value can be the numerical code for the interaction model associated with the Trigger using the same coding as for the cmdID field in the SDOPrivateData command in the DTVCC channel. The interactionModel for a Trigger acquired from a live trigger server or derived from an AMT can be deemed to be the TDO model.

The value of triggerString attribute can be the string representation of the Trigger. The string representation of the Trigger was described in the trigger syntax. However special channel change trigger may be different. The triggerString attribute for a special channel change trigger can have value . where the can be the original major channel number of the new channel as it was broadcast by the TV station and can be the original minor channel number of the new channel as it was broadcast by the TV station . If the channel number is not known then the and values can both be 0 .

 activationTime tdoURL cookieSpace Capabilities Event action destination diffusion and data were described above.

 availInternet and availBroadcast can be from TPT. availInternet and availBroadcast were described above.

 activationTime tdoURL cookieSpace Capabilities Event action destination diffusion and data ware described above.

ContentItem element updatesAvail pollPeriod size availInternet and availBroadcast attributes may be equal to the elements and attributes of the TPT when generating the augmented trigger. ContentItem element updatesAvail pollPeriod size availInternet and availBroadcast were described above.

 cookieSpace availInternet availBroadcast Capabilities ContentItem updatesAvail pollPeriod size availInternet availBroadcast Event action destination and data were described above.

 appID appType appName globalId appVersion frequencyOfUse expireDate testTDO URTL in the TDO element and the URL in the ContentItem element may be equal to the elements and attributes of the TPT when generating the augmented trigger. appID appType appName globalId appVersion frequencyOfUse expireDate testTDO the URL in the TDO element and the URL in the ContentItem element will be described below.

One embodiment of trigger service state variables may define the shown trigger service state variables. The Trigger service can have the state variables listed in .

The value of the LatestUnfilteredTrigger state variable can represent the Trigger in the unfiltered stream with the most recent target delivery time. The format of this state variable can be an XML document conforming to the schema described in .

The value of the LatestFilteredTrigger state variable can represent the Trigger in the filtered stream with the most recent target delivery time. When it is an Activation Trigger it can be augmented by combining information in the Activation Trigger with information in the TPT to produce an XML document conforming to the XML schema represented by Table described in . When it is a Trigger with interaction model other than TDO it can have the form of an XML document conforming to the schema described in . When it is a special channel change Trigger the format can be . as described before.

The value of the UnfilteredTriggerDeliveryTime state variable can be the delivery time of the Trigger in the unfiltered stream with the most recent target delivery time.

The value of the FilteredTriggerDeliveryTime state variable can be the delivery time of the Trigger in the filtered stream with the most recent target delivery time.

The value of the CurrentTrigger state variable can depend on which of the following three situations is in effect. 1 There is no interactive adjunct data service associated with the programming currently being viewed on the primary screen. 2 There is an interactive adjunct data service associated with the programming currently being viewed on the primary screen and it has the Direct Execution interaction model. 3 There is an interactive adjunct data service associated with the programming currently being viewed on the primary screen and it has the TDO interaction model.

In case 2 the value of the CurrentTrigger state variable can be the most recent Trigger that has been received by the TV set for the programming currently being viewed on the primary screen.

In case 3 the value of the CurrentTrigger state variable can be an augmented form of the most recently activated Activation Trigger among the Activation Triggers that have been received by the TV set for the programming currently being viewed on the primary screen. i.e. an Activation Trigger can become the basis for the CurrentTrigger state variable when its activation time arrives and it can remain the basis until another Activation Trigger reaches its activation time. The augmented form of the Activation Trigger can be obtained by combining information in the Activation Trigger with information in the TPT. The augmented form may be equal to one of the above described augmented trigger formats.

The definition of the CurrentTrigger state variable can imply that for the TDO interaction model Activation Triggers are delivered to UPnP clients at the Trigger activation times.

In another embodiment of the trigger service state variables whenever the trigger is changed in order to transmit the trigger or the expanded trigger from the receiver to the second screen device in real time ATSCTrigger and ATSCExpandedTrigger may be defined as the state variable.

ATSCTrigger state variable can contain a reference in the form of a URI to the trigger received from DTVCC stream or ACR server. This variable can include a URL for TPT TDO parameters table TDO ID Event ID Data ID media time content ID an activation time for the targeted event and so on.

ATSCExpandedTrigger state variable can contain the metadata in the form of an XML Fragment associated with TDO for the second screen device. This metadata could have been extracted from both TPT and trigger received from DTVCC stream or ACR server. This variable may have the same XML schema as the embodiment of .

The changed value of the above defined ATSCTrigger and ATSCExpandedTrigger may be acquired in real time when the receiver changes the state variable based on the Eventing mechanism of UPnP.

The actions may be defined such that the second screen device or the receiver arbitrarily reads the value of the trigger service state variable.

One embodiment of the trigger service actions may define the GetLatestUnfilteredTrigger and GetLatestFilteredTrigger action.

The value of the LatestUnfilteredTrigger output argument can be the value of the LatestUnfilteredTrigger state variable.

The second screen application may obtain the value of the LatestUnfilteredTrigger state variable that is the trigger in the unfiltered stream with the most recent target delivery time using the GetLatestUnfilteredTrigger Action.

The value of the LatestFilteredTrigger output argument can be the value of the LatestFilteredTrigger state variable.

The second screen application may obtain the value of the LatestFilteredTrigger state variable that is the Trigger in the filtered stream with the most recent target delivery time using the GetLatestFilteredTrigger Action.

In another embodiment of the above described trigger service state variables in which the ATSCTrigger and ATSCExpandedTrigger are defined as the state variable trigger service actions will be described.

Even in this embodiment the action may be defined such that the second screen device or the receiver arbitrarily writes or reads the value of ATSCTrigger and ATSCExpandedTrigger.

SetExpandedTrigger action may enable use of the value of ATSCExpandedTrigger. CurrentTrigger may be augmented.

GetExpandedTrigger may enable reading of the value of ATSCExpandedTrigger. CurrentTrigger may be argument.

How the second screen device operates according to action information included in the trigger or expanded activation trigger received from the second screen device via the trigger delivery service may be shown.

The second screen device may acquire the trigger of the execution termination action via the trigger delivery service and deliver the URL of the target TDO and associated information from the acquired trigger to the DAE browser. The browser may perform the action included in the trigger such as execution or termination.

How the second screen device operates according to action information included in the trigger or expanded activation trigger received from the second screen device via the trigger delivery service may be shown.

The second screen device may acquire the trigger of the trigger event action via the trigger delivery service and then extract information such as Data ID from the acquired trigger. Thereafter the data may be delivered to the currently executed TDO using AJAX. The TDO may perform an appropriate operation according to the received data.

In another embodiment of the above described trigger service state variables in which ATSCTrigger and ATSCExpandedTrigger are defined as the state variable the operational concept of the trigger delivery service will be described.

In this embodiment in case of Direct Execution Model if the content id that is c is included in the trigger received via the DTVCC stream or the ACR server the receiver may set the received time base trigger value to the value of the ATSCTrigger state variable. When the time base trigger arrives at the receiver the value of the state variable may be immediately changed or may be delivered to the second screen device via the SetTrigger action.

In the present embodiment in case of TDO Model if the content id that is c is not included in the trigger received via the DTVCC stream or the ACR server the receiver receives the activation trigger and then extract and combine associated information from the TPT and the trigger information to generate the expanded trigger. Thereafter at or before the activation time of the expanded trigger the value of the ATSCExpandedTrigger state variable may be set or delivered to the second screen device via the SetExpandedTrigger action.

The AppURL service can allow second screen devices to determine the base URL and the name of the second screen application associated with the currently executing DO.

The value of the AppURL state variable can be the base URL of the second screen application associated with the currently executing DO. When there is no DO with associated second screen application executing on the first screen device the value of the AppURL state variable can be the null string.

The value of the AppName state variable can be the name of the second screen application associated with the currently executing DO. When there is no DO with associated second screen application executing on the first screen device the value of the AppName state variable can be the null string.

The AppURL output argument can be the current value of the AppURL state variable. And the AppName output argument can be the current value of the AppName state variable.

Accordingly it is possible to obtain the current value of the AppURL state variable and the current value of the AppName state variable via the GetAppURL action.

A Receiver can support Proxy HTTP Server service. The proxy HTTP server service may mean a service for acquiring TDOs files via a TV receiver if the second screen device transmits the TDOs files via a broadcast network.

The diagram showing the operational concept of the proxy HTTP Server service may include a broadcasting system an ACR server a broadcaster ATSC 2.0 iTV server an ATSC 2.0 receiver and or second screen Devices .

The ATSC 2.0 receiver may receive the trigger associated with the broadcast A V and the interactive service acquire the interactive service using the trigger and provide the interactive service on the screen. This may be equal to the above described receiver. The proxy HTTP server service may enable the ATSC 2.0 receiver to perform the function similar to that of the proxy server in order to efficiently provide the file requested by the second screen device to the second screen device.

The proxy HTTP server service may enable the receiver to access the broadcast stream or the file over the Internet via the second screen device and enable the second screen device to access the content transmitted via the broadcast stream. If a plurality of second screen devices accesses the same file over the Internet it is possible to minimize access of the second screen devices to the same file.

The UPnP Proxy Server service can provide an HTTP proxy server to allow second screen devices to access files that are delivered to the TV receiver in the broadcast via FLUTE sessions and to make the retrieval of files from Internet servers by second screen devices more efficient in cases when multiple second screen devices in a household are retrieving the same files simultaneously.

The value of the ProxyServerURL state variable can be the URL of the HTTP Proxy Server i.e. the URL to which HTTP requests are to be directed in order to route the requests through the proxy server.

Accordingly it is possible to obtain the current value of the ProxyServerURL state variable via the GetProxyURL action.

In another embodiment of the UPnP HTTP Proxy Server service state variable the UPnP HTTP Proxy Server service State Variable called ATSCProxySeverURL may be defined. In addition in this embodiment the action called GetProxyServerURL may be defined.

ATSCProxySeverURL state variable can contain a reference in the form of a URI to the proxy server in receiver. The proxy server gets the HTTP request for a file from a second screen device and retrieves the file from FLUTE sessions in the broadcast stream or the Internet. Then the proxy server sends the retrieved file to the second screen device as HTTP response.

GetProxyServerURL may be an action enabling reading of the value of ProxySeverURL. ProxySeverURL may be included as an argument.

In another embodiment of the UPnP HTTP proxy server service state variable UPnP HTTP proxy server service state variable called ATSCFileList may be defined. In addition in this embodiment the action called RequestFiles may be defined.

The file included in the broadcast stream may be acquired only by the receiver capable of receiving broadcast content. Therefore in order to enable the second screen device which cannot receive the broadcast content to access the file included in the broadcast content necessary UPnP state variables and actions may be defined. That is ATSCFileList which is a file list to be downloaded via a FLUTE session is set as the UPnP state variable or the second screen device may be enabled to acquire a specific file or a plurality of files via the RequestFiles action requesting the files from the receiver.

The ATSCFileList state variable can contain the CSV list of requested files to the proxy server in receiver.

RequestFiles may be an action requesting to download a specific file included in the broadcast stream over the Internet. In particular in case of a file included in the broadcast stream the requested file may be downloaded via FLUTE session.

There can be two modes of operation one where a triggered application TDO executes on the TV receiver and the other where a non triggered application Packaged App executes on the TV receiver.

In the case of the triggered application executing on the TV receiver when the programming currently being viewed on a TV receiver has an associated interactive data service with second screen support a user of a second screen device can activate an appropriate application on the device. This application can go through the UPnP discovery and description process to discover the Trigger service Two Way Communications service and Proxy Server service on the TV receiver.

The second screen application can then subscribe to UPnP eventing for the Trigger service to get notifications of Triggers ready for delivery and it can use the GetLatestUnfilteredTrigger or GetLatestFilteredTrigger Action to get the Triggers it is designed to use. The result of this is that the second screen application can obtain the appropriate Triggers at the appropriate times. The application can then act on these Triggers in whatever manner it is designed to use.

The second screen application can also subscribe to UPnP eventing for the Two Way Communications service to get notification of the TCP IP address and port to use to request a connection for two way communications and notifications of when there is a DO executing in the primary device that is prepared to communicate. The application can then engage in two way communications with any DO that supports such communications.

The actions caused by Triggers and or two way communications can often require the second screen application to download files. These files might be available from HTTP servers on the Internet or they might be available from a d session in the TV broadcast or both .

If all the desired files are available via the Internet and if the second screen device has good connectivity to the network the application can simply retrieve the files directly.

If some or all of the desired files are available only via the TV broadcast and if the Receiver offers an HTTP Proxy Server service then the application can get the proxy server URL with the GetProxyURL Action and retrieve the desired files via the proxy server. The application could also choose to use the proxy server in other situations where it might be more convenient to retrieve the files that way rather than directly.

In the case of the non triggered application executing on the TV receiver Regardless of the programming currently being viewed a user can activate a DO on the TV receiver which among other things makes available the name and location of a companion application to be launched on a second screen device through the AppURL service.

A control point on the second screen device can subscribe to UPnP eventing associated with the AppURL service to get notification of changes to the AppURL and AppName variables. The control point would then indicate to the user of the second screen device that an available service is pending. Subsequently the user would view the AppName and select the service resulting in the companion second screen application being launched on the second screen device.

Second screen applications may be associated with a DO executing on the ATSC 2.0 receiver even when that DO is a broadcaster provided Packaged App previously downloaded to the receiver whose life cycle is controlled by the consumer instead of by the broadcaster. In the absence of triggers to identify a companion second screen application the receiver offers an AppURL service that allows a control point on the second screen device to use a GetAppURL action to access a published second screen application URL and launch it on the second screen device.

One embodiment of the second screen device architecture shows the second screen application and the second screen device interworking with the receiver.

One embodiment of the second screen device architecture may include a remote content server a TV receiver and or a second screen device .

The remote content server may provide content. The content may be provided to the receiver or the second screen device .

The TV receiver may provide the UPnP trigger service and the UPnP proxy server service. This receiver may be equal to the above described receiver.

The second screen device may have a second screen application ATSC 2.0 App and the second screen application may have a UPnP Control Point CP module in the trigger handler. The UPnP Control Point CP module handles all UPnP communications between the Second Screen Application ATSC 2.0 App and the Trigger service and Proxy Server service on the TV Receiver . It can manage the discovery process obtain the proxy server URL and subscribe to the Trigger service eventing.

Triggers that arrive from the UPnP Trigger service can be turned over to the Trigger Handler. If a Trigger indicates that a new Declarative Object DO is to be downloaded and executed in the DAE Declarative Application Environment i.e. browser the Trigger Handler can take care of that. If a Trigger indicates that the DO already executing in the browser should take some action the Trigger Handler can pass the Trigger in to the DO. The user of the second screen device can interact with the DOs. The Trigger Handler can be invisible to the user.

The Second Screen App can perform the following functions as needed. 1 Use the UPnP discovery and description protocols to find the Trigger service and if available the Proxy Server service on the TV receiver. 2 Use the UPnP SUBSCRIBE protocol to subscribe to the Trigger service eventing. 3 Invoke the GetProxyURL Action of the Proxy Server service to get the URL of the HTTP proxy server if available . 4 Receive Triggers delivered via the Trigger service events. 5 If a Direct Execution Trigger is received and the DO identified in the Trigger is not already running in the DAE start it running in the DAE downloading if first if needed . 6 Pass each received Direct Execution Trigger in to the DO identified in the Trigger after downloading and starting the DO if needed . 7 If a TDO Trigger is received and if the Action attribute of the Trigger is anything other than TriggerEvent perform the Action e.g. prepare to run a TDO run a TDO terminate a TDO etc. . 8 If a TDO Trigger is received and if the Action attribute of the Trigger is TriggerEvent pass the Trigger in to the TDO identified as the target of the Trigger. If the TDO is not already running in the DAE discard the Trigger. 9 Download files including TDOs as needed either via a direct Internet connection or via the Proxy Server service on the TV receiver.

Direct Execution Triggers and TDO Trigger can be acted on immediately when received unless they contain a spread or diffusion attribute. When a Trigger contains a spread or diffusion attribute the action can be delayed for a random interval.

The diagram showing the simplified structure of the receiver may include an antenna rcvr a tuner rcvr an EPG rcvr a VSB or DVB Demodulator rcvr a channel manager rcvr an SI module rcvr a MPEG 2 TS system decoder rcvr a caption module rcvr a trigger module rcvr a web browser rcvr a UPnP framework rcvr a network protocol stack rcvr a network interface rcvr a UI module rcvr an audio decoder rcvr a video decoder rcvr speakers rcvr a display module rcvr a graphic processor rcvr a remote controller receiver rcvr and or a remote controller rcvr .

Antenna rcvr may receive a broadcast signal according to a broadcast stream. Here the antenna rcvr may be one generally used in the technical field.

Tuner rcvr may seek or tune to a channel of the receiver and may include a radio frequency amplifier a local oscillator a frequency conversion and input circuit a seeker etc. The Tuner rcvr may be one generally used in the technical field.

The EPG rcvr may be a broadcast program guide service for providing a TV program broadcast time content and actor information using an empty frequency of a TV broadcast or supplementary channel Electronic program guide . The received EPG data is stored and the viewer manipulates the EPG using the remote controller to select and reserve a program thereby performing pay per view program order program search per subject or type video recording etc. The received EPG may also be delivered to the UI module.

VSB or DVB Demodulator rcvr may modulate a VSB signal or a DVB signal. VSB or DVB Demodulator rcvr may restore the modulated VSB or DVB e.g. OFDM modulated signal to an original signal. The demodulation process of VSB or DVB Demodulator rcvr may be one generally used in the technical field.

The channel manager rcvr may perform channel management using the received EPG. The EPG processed by the SI module may be delivered. The channel manager may serve as a general channel manager.

The SI module rcvr may confirm program specific information if the broadcast stream is received via the MPEG 2 TS System Decoder rcvr . Using the confirmed information how many captions are present in the broadcast program and presence of the trigger in service 6 may be determined.

MPEG 2 TS System Decoder rcvr can decode the transport stream TS of the demodulated signal. The MPEG 2TS System Decoder rcvr may obtain and deliver a caption stream from the transport stream to the caption module rcvr. The MPEG 2TS System Decoder rcvr may send the decoded audio and video signal to the audio video decoder.

Caption Module rcvr may receive the caption stream. The caption module rcvr may monitor service 6 or other services and determine whether service 6 or services for transmitting the trigger is selected and sent to the trigger module rcvr or whether caption text is processed and displayed on a screen. Trigger data may be delivered to the trigger module rcvr. Other caption services may be subjected to caption text processing and sent to the graphic processor rcvr. The caption module rcvr delivers the trigger to the trigger module rcvr via the confirmed information if the trigger is included in the currently received digital caption.

Trigger Module rcvr may parse trigger TPT and or AMT information and process the parsed data. The trigger module rcvr may access the network via the network protocol stack rcvr using the URI information value of the trigger. The URI information value may be the address of the HTTP server. The trigger module rcvr may analyze the TPT file content to obtain the TDO URL. In addition the trigger module rcvr may parse the AMT to process data. Other information may be obtained through parsing. After the AMT message has been received the TDO URL corresponding to the web browser is delivered according to a predetermined time and operation or the currently operating TDO may be stopped at a predetermined time. This corresponds to a TDO action and the trigger module rcvr may send a command to the web browser to operate. The operation of the trigger module rcvr related to the present invention will be described in detail below. The trigger module rcvr may directly or indirectly access the Internet server via the network protocol stack rcvr . The trigger module rcvr may immediately interpret the trigger received via the DTVCC and download and process the TPT file from the Internet via the network interface rcvr as necessary. The TPT file may be immediately processed after downloading thereby performing a necessary operation. At this time if the trigger associated with the second screen and the associated event are present as described above communication with the second screen device may be performed using various methods. Such communication may be performed by the below described UPnP Framework rcvr .

Web Brower rcvr may receive the command from the trigger module rcvr a browser key code from the UI module rcvr and a browser key code from the remote controller receiver rcvr and communicate with the network protocol stack rcvr.

The UPnP Framework rcvr may detect the second screen device and transmit the trigger or regenerate and transmit information necessary for the second screen device. As described above when the trigger is received via the network interface rcvr if the trigger associated with the second screen and the associated event are present the UPnP Framework rcvr may perform communication with the second screen device.

Network Protocol Stack rcvr may communicate with the trigger module rcvr and the web browser to access the server via the network interface rcvr.

Network Interface rcvr performs common connection of several other apparatuses or connection of a network computer and an external network. The network interface may be connected to the server to download a TDO a TPT an AMT etc. Here operation of the network interface rcvr may be operation of the network interface rcvr one generally used in the technical field. Operation of the network interface rcvr related to the present invention will be described in detail below.

UI Module rcvr may receive information input by a viewer using the remote controller rcvr through the remote controller receiver rcvr. If the received information is related to a service using the network the browser key code may be delivered to the web browser. If the received information is related to currently displayed video the signal may be delivered to the display module rcvr via the graphic processor rcvr.

Audio Decoder rcvr may decode the audio signal received from the MPEG 2TS System Decoder rcvr. Thereafter the decoded audio signal may be sent to the speaker and output to the viewer. Here the audio decoder rcvr may be one generally used in the technical field.

Video Decoder rcvr may decode the video signal received from the MPEG 2TS System Decoder rcvr. Thereafter the decoded video signal may be sent to the display module rcvr to be output to the viewer. Here the video decoder rcvr may be one generally used in the technical field.

Speakers rcvr may output the audio signal to the viewer. The speaker may be one generally used in the technical field.

Display Module rcvr may output the video signal to the viewer. The display module rcvr may be one generally used in the technical field.

Graphic Processor rcvr may perform graphic processing with respect to the caption text received from the caption module rcvr and the viewer input information received from the UI module rcvr. The processed information may be delivered to the display module rcvr. The graphic processor rcvr may be one generally used in the technical field.

Remote Controller Receiver rcvr may receive information from the remote controller rcvr. At this time the key code may be delivered to the UI module rcvr and the browser key code may be delivered to the web browser.

Remote Controller rcvr delivers the signal input by the viewer to the remote controller receiver rcvr. The remote controller rcvr may receive viewer input for changing a virtual channel. In addition the remote controller may receive information selected by the viewer with respect to the application. The remote controller rcvr may deliver the received information to the remote controller receiver rcvr. At this time the information may be remotely delivered using infrared IR light at a distance out of a predetermined range.

One embodiment of the structure of the second screen device may include an IO subsystem a file system a network protocol subsystem and basic modules .

The IO subsystem may be connected with all devices which may be mounted in the second screen device for external connection. The IO subsystem may be connected with a keypad a display a microphone a speaker a stereo jack a motion sensor a light sensor a GPS and a camera. Each I O device may be controlled by a key module a display control module an audio control module a sensor control module and or a camera control module. Each I O device is controlled by a device driver and each sensor or camera may access any program if a function is called by the IO subsystem in the form of an SDK. In some cases a function may be restricted such that access is possible only in a native application.

The file system may read and write a file for an external SD card and may be connected to a USB to perform data communication. A device such as an SD card a flash memory or a USB may be connected. This may be controlled by SD Interface Flash Memory Control or USB BUS Control.

The basic modules may be included in the second device. A battery manager may manage the battery amount of the second screen device and a notification module may be used when a communication provider or a manufacturer provides a notification to the second screen device. In addition a store module may be used to purchase applications for a second screen made using an open SDK provided by the second screen device. An application manager may manage an application installed using the store module and notify about application upgrade. In addition a web module may be included such that the second screen device performs Internet access. Various functions of the second screen may be set according to personal preference and a user preference program may be used.

The basic modules have various functions and may be programs installed in the second screen device. However the modules denoted by dotted lines may be selectively software modules installed by the user

For example the UPnP framework module may not be supported by the second screen device or may be installed in the second screen device. If the UPnP framework module is installed a native application is also installed to easily perform a UPnP operation. However in the structure of the receiver the UPnP framework may enable the user to install a second screen service application or an application supporting the UPnP framework. It is possible to find a receiver capable of receiving a terrestrial wave via the UPnP framework module.

One embodiment of the second screen service scenario may include receiving a trigger s requesting a TPT s transmitting a TPT as a response s requesting a TDO s transmitting a TDO as a response s executing a TDO s sending a scanDeviceList message s calling a discovery function s executing a UPnP application s multicasting a searching message s notifying a UPnP Framework s returning a device list s returning a device handle s sending a scanServiceList message s calling a service list function s sending a GetServiceDescription message s sending an HTTP message s returning a service list s returning a list of service handle s sending a hnHandle message s calling a service list function s sending a GetDeviceProfile message s sending an HTTP message s returning a soap response s returning a soap response XML s parsing a soap response s sending a hnHandle message s calling a service List function s sending a InputUIListing message s sending an HTTP message s returning a soap response s returning TimeToLive s sending a hnHandle message s calling a service List function s sending a DisplayMessage s sending an HTTP message s returning Null s returning Null s and or executing a second screen application s .

Receiving a trigger s may include receiving the trigger from the broadcaster using a DTVCC iTV message via a broadcast stream.

Requesting a TPT s may include parsing and interpreting the received trigger and requesting the TPT related to the broadcaster Internet server.

Requesting a TDO s may include requesting the TDO from the broadcaster Internet server if the related TDO needs to be downloaded.

Sending a scanDeviceList message s may include the executed DO or TDO sending a message for requesting device list scan.

Calling a discovery function s may include calling the discovery function of the UPnP framework for device discovery.

Executing a UPnP application s may include the second screen device executing a UPnP application for a second screen service launcher. This step is independent of the primary device and may be performed before executing a UPnP application s .

Multicasting a searching message s may include the UPnP framework multicasting the searching message for searching for the second screen device in the home network.

Notifying a UPnP Framework s may include the second screen device which receives the searching message transmitting a notifying message to the primary device. Thus it is possible to notify about presence of the second screen device.

Returning a device list s may include the UPnP framework returning the device list after device discovery.

Sending a scanServiceList message s may include the executed DO or TDO transmitting a message for requesting service list scan.

Calling a service list function s may include calling the service list function of the UPnP framework for service discovery.

Sending a GetServiceDescription message s may include requesting the service description of the second screen device from the second screen device.

Sending an HTTP message s may include sending the result of sending a GetServiceDescription message s . As described above a message such as HTTP 1.1 200 OK success may be sent. The service description may be received in XML.

Returning a service list s may include returning the service list after the UPnP framework receives the service description.

Calling a service list function s may include calling a service list function of the UPnP framework for service discovery.

Sending a GetDeviceProfile message s may include requesting the service description of the second screen device from the second screen device. Sending an HTTP message s may include sending the request result in sending a GetDeviceProfile message s . As described above a message such as HTTP 1.1 200 OK success may be sent. A device profile may be received.

Sending a hnHandle message s may include sending a message in order to notify the second screen device of the URL address of the second screen service.

Calling a service List function s may include calling the service list function of the UPnP framework.

Sending a InputUIListing message s may include notifying the second screen device of the URL address of the second screen service. The above described AddUIListing action may be used. The second screen device may add the acquired URL to UIListing.

Sending an HTTP message s may include sending the request result in sending an InputUIListing message s . As described above a message such as HTTP 1.1 200 OK success may be sent.

Returning a soap response s may include a returning a message indicating that the URL has been transmitted.

Returning TimeToLive s may include sending the request result in sending an InputUIListing message s similarly to sending an HTTP message s .

Sending a hnHandle message s may include sending a message in order to deliver a display message to the second screen device.

Calling a service List function s may include calling the service list function of the UPnP framework.

Sending a DisplayMessage s may include transmitting the display message to the second screen device. The display message may include information such as message type. The above described DispalyMessage action may be used. The second screen device may display the message on the second screen according to the display message.

Sending an HTTP message s may include sending the result of sending a DisplayMessage s . As described above a message such as HTTP 1.1 200 OK success may be sent.

Executing a second screen application s may include the second screen device executing the second screen application.

One embodiment of a method of processing an interactive service at a first device may include sending a discovery message s receiving a request for descriptions s sending a response with the descriptions s receiving a trigger s combining information to generate an augmented activation trigger s and or sending the generated augmented activation trigger s .

Sending a discovery message s may include sending the discovery message to a second screen application running in a second device. The discovery message may indicate the second screen support service provided by the first device. Here the first device may be the above described primary device or TV receiver. Here the discovery message may not be transmitted to a single second screen device but may be multicasted to a plurality of second screen devices. Here the second screen support service may be the above described second screen service. Sending a discovery message s may be included in the above described device discovery step.

Receiving a request for descriptions s may include receiving a request for descriptions of the second screen support service provided by the first device. The second device may be above described second screen device. The second screen application which is being executed in the second screen device may request descriptions of the second screen support service provided by the first device from the first device. Receiving a request for descriptions s may include the first device receiving the request. This may be included in the above described device discovery step.

Sending a response with the descriptions s may include the first device transmitting the descriptions to the second screen application in response to the request in receiving a request for descriptions s . This response may include other information in addition to the descriptions. This may be included in the above described device discovery step.

Receiving a trigger s may include the first device receiving the above described trigger via a broadcast stream or an internet server. The broadcast stream may be received via the DTVCC as described above. If the broadcast stream is received via the Internet server as described above this may be received in the form of an iTV message or via an ACR process. This trigger may be delivered to the second screen application by the above described trigger service. As described above the trigger service may be one of second screen support services. As described above the trigger can be a signaling element whose function is to identify signaling and establish timing of playout of interactive events targeted to applications for a segment described by an application parameter table. The received trigger may be any one of a time base trigger an activation trigger an interaction trigger and or a channel change trigger. The interaction trigger may be a trigger for an interaction model other than a TDO interaction model. For example the trigger may have a content id term in the direct execution model. The channel change trigger may be the above described special channel change trigger which may be received when the channel is changed.

Combining information to generate an augmented activation trigger s may include extracting and combining the information in the activation trigger and the information in the TPT among the received triggers. This may be equal to the step of generating the augmented trigger the augmented activation trigger and the expanded trigger. The format in or after the process of generating the augmented activation trigger was described above.

Sending the generated augmented activation trigger s may include transmitting the generated augmented activation trigger to the second screen application. This may be the above described filtered stream option among the trigger services.

In one embodiment of the present invention the step of receiving a searching message may be performed before sending the discovery message. The searching message may be used to find a device for providing a second screen support service. The searching message may be transmitted using a unicasting or multicasting method. By this step the second screen device may detect the first device.

In another embodiment of the present invention a trigger service may deliver a trigger as an unfiltered stream option. The unfiltered stream option may deliver all types of triggers to the second screen device as described above.

In another embodiment of the present invention in the unfiltered stream option the first device may transmit all triggers to the second screen application as soon as the triggers is received.

In another embodiment of the present invention the trigger service may provide a filtered stream option. As described above the filtered stream option may deliver an augmented activation trigger an interaction trigger and or a channel change trigger.

In another embodiment of the present invention the augmented activation trigger includes application URL information having same value with an URL element of an application element in the application parameter table. The URL element identifies a file which is part of the application and the application element is identified by the activation trigger. The application parameter table may be the above described TPT. The application may be a TDO. Here the application URL information may be appURL of the above described augmented activation trigger. Here the URL element may be a URL element in a TDO element of the TPT. The augmented activation trigger may be obtained from a URL element value in the TDO element of the TPT associated with the activation trigger in a generation process and the application URL information and the URL element may have the same value.

In another embodiment of the present invention the augmented activation trigger further includes an event information representing an event element in the application parameter table the event element identified by the activation trigger represents the event for the application the event information includes an action information having same value with an action attribute of the event element identified by the activation trigger and the action attribute indicates type of an action to be applied when the event is activated. The application parameter table may be the above described TPT. The application may be a TDO. Here the event information may be the event element of the above described augmented activation trigger. Here the event element may be an event element in a TDO element of the TPT. The action information may be action of the above described augmented activation trigger. Here the action attribute may be action of the event element of the TPT. The augmented activation trigger may be obtained from an event element value and action value in the TDO element of the TPT associated with the activation trigger in a generation process and the action information and the action attribute may have the same value.

In another embodiment of the present invention the first device delivers the augmented activation trigger at the activation time of the augmented activation trigger the first device delivers the interaction trigger when the interaction trigger is received by the first device and the first device delivers the channel change trigger when the channel is changed. The augmented activation trigger may be delivered at or before the activation time as described above interaction trigger may be delivered to the second screen application as soon as being received by the first device and the channel change trigger may be delivered when the channel is changed.

One embodiment of a method of processing an interactive service at a second screen application running in a second device may include receiving a discovery message s sending a request for descriptions s receiving a response with the descriptions s accessing a trigger service s and or receiving a trigger from the first device s .

Receiving a discovery message s may include receiving the discovery message from the first device. As described above the first device may be a primary device or a TV receiver. The second device may be the above described second screen device. The discovery message may serve to indicate the second screen support service provided by the first device. The first device may send the discovery message to only the second device or may multicast the discovery message to all devices in the home network. This step may be included in the above described device discovery step. This step may be the second device receiving the discovery message from the first device. Sending a discovery message s may be described from the viewpoint of the second screen application.

Sending a request for descriptions s may include requesting descriptions of the second screen support service provided by the first device from the first device. Receiving a request for descriptions s may be described from the viewpoint of the second screen application. This step may be included in the above described device discovery.

Receiving a response with the descriptions s may include receiving the descriptions of the service as a response to the request sent in the step of sending a request for descriptions s . The first device may transmit the description of the service thereof to the second screen application. Sending a response with the descriptions s may be described from the viewpoint of the second screen application. This step may be included in the above described device discovery step.

Accessing a trigger service s may include accessing the trigger service which is one of the second screen support services. The first device may be used to receive the trigger from the broadcast stream or the Internet server. Accessing to the trigger service may be performed based on the descriptions received in the step of receiving a response with the descriptions s . Among the descriptions received in the step of receiving a response with the descriptions s the description of the trigger service may be used.

Receiving a trigger from the first device s may include receiving the trigger from the first device using the accessed trigger service. Here the trigger service may be one of the second screen support services. The trigger can be a signaling element whose function is to identify signaling and establish timing of playout of interactive events targeted to applications for a segment described by an application parameter table. Here the trigger may be one of a time base trigger an activation trigger an interaction trigger and or a channel change trigger. The interaction trigger may be a trigger for an interaction model other than a TDO interaction model. For example the trigger may have a content id term in the direct execution model. The channel change trigger may be the above described special channel change trigger and may be received when the channel is changed.

In one embodiment of the present invention a step of multicasting a searching message may be further included. This step may be performed before receiving the discovery message. The searching message may be used to detect a device for providing a second screen support service. According to the embodiment the searching message may be unicasted. By this step the second device may detect the first device.

In another embodiment of the present invention the trigger service may deliver the trigger as an unfiltered stream option. The unfiltered stream option may deliver all types of triggers to the second screen application as described above.

In another embodiment of the present invention in the unfiltered stream option all triggers may be delivered to the second screen application as soon as being received by the first device.

In another embodiment of the present invention receiving augmented activation trigger from the first device may be further included. The augmented activation trigger may be generated by extracting and combining the information in the activation trigger and the information in the TPT at the first device. This may be equal to a process of generating the above described augmented trigger augmented activation trigger and expanded trigger. The process of generating the augmented activation trigger and the format thereof after generation were described above.

In another embodiment of the present invention the trigger service may provide a filtered stream option. As described above the filtered stream option may deliver the augmented activation trigger the interaction trigger and or the channel change trigger.

In another embodiment of the present invention the augmented activation trigger includes application URL information having same value with an URL element of an application element in the application parameter table. The URL element identifies a file which is part of the application and the application element is identified by the activation trigger. The application parameter table may be the above described TPT. The application may be a TDO. Here the application URL information may be appURL of the above described augmented activation trigger. Here the URL element may be a URL element in the TDO element of the TPT. The augmented activation trigger may be obtained from a URL element value in the TDO element of the TPT associated with the activation trigger in a generation process and the application URL information and the URL element may have the same value.

In another embodiment of the present invention the augmented activation trigger further includes an event information representing an event element in the application parameter table the event element identified by the activation trigger represents the event for the application the event information includes an action information having same value with an action attribute of the event element identified by the activation trigger and the action attribute indicates type of an action to be applied when the event is activated. The application parameter table may be the above described TPT. The application may be a TDO. Here the event information may be an event element of the above described augmented activation trigger. Here the event element may be an event element in the TDO element of the TPT. Here the action information may be action of the above described augmented activation trigger. Here the action attribute may be action in the event element of the TPT. The augmented activation trigger may be obtained from an event element value and action value in the TDO element of the TPT associated with the activation trigger in a generation process and the action information and the action attribute may have the same value.

In another embodiment of the present invention the augmented activation trigger is delivered at the activation time of the augmented activation trigger the interaction trigger is delivered as soon as possible and the channel change trigger is delivered when the channel is changed. The augmented activation trigger may be delivered at or before the activation time as described above the interaction trigger may be delivered to the second screen application as soon as being received by the first device and the channel change trigger may be delivered when the channel is changed.

One embodiment of an apparatus for processing an interactive service as a first device may include a first module and or a second module .

The first module can be configured to receive a trigger from a broadcast stream or an Internet server. Here the first module is a trigger receiving module in the first device and may be the above described network interface when receiving the broadcast stream from the above described tuner or Internet server. The broadcast stream may be received via the DTVCC as described above. If the broadcast stream is received via the Internet server as described above the broadcast stream may be received in the form of an iTV message or via an ACR process. This trigger may be delivered to the second screen application later by the above described trigger service. As described above the trigger service may be one of the second screen support services. As described above the trigger can be a signaling element whose function is to identify signaling and establish timing of playout of interactive events targeted to applications for a segment described by an application parameter table. The received trigger may be one of a time base trigger an activation trigger an interaction trigger and or a channel change trigger. The interaction trigger may be a trigger for an interaction model other than a TDO interaction model. For example the trigger may have a content id term in the direct execution model. The channel change trigger may be the above described special channel change trigger and may be received when the channel is changed.

The second module may send the discovery message receive a request for service descriptions and send a response thereto. In addition the second module may send the trigger to the second device. The second module may be the above described UPnP framework module.

The second module can be configured to send a discovery message to a second screen application running in a second device. The discovery message may serve to indicate the second screen support service provided by the first device. Here the discovery message may not be transmitted to a single second screen device but may be multicasted to a plurality of second screen devices. Here each of the second screen support services may be the above described second screen service. This operation is performed for device discovery.

The second module can be configured to receive a request for descriptions of the second screen support services from the second screen application. The second module may receive the request for descriptions of the second screens support service provided by the first device. The second screen application executed by the second screen device may request the descriptions of the second screen support service provided by the first device from the first device. This request may be received. This operation may be performed for device discovery.

The second module can be configured to send a response with the descriptions to the second screen application. As a response to the received request the descriptions may be transmitted to the second screen application. This response may include other information in addition to the descriptions. This operation may be performed for device discovery.

The second module can be configured to deliver the trigger to the second device using a trigger service. The trigger service can be one of the second screen support services.

In one embodiment of the present invention the second module may receive the searching message. This operation may be performed before sending the discovery message. The searching message may be used to detect a device for providing the second screen support service. The searching message may be transmitted using a unicasting or multicasting method. Therefore the second screen device may detect the first device.

In another embodiment of the present invention the trigger service may deliver the trigger as the unfiltered stream option. The unfiltered stream option may deliver all types of triggers to the second screen device as described above.

In another embodiment of the present invention the second module may deliver all triggers to the second screen application as soon as the first module receives the triggers in the unfiltered stream option.

In another embodiment of the present invention the second module may generate and deliver the augmented activation trigger to the second screen application. The second module may extract and combine the information in the activation trigger and the information in the TPT among the received triggers. This may be equal to the operation for generating the above described augmented trigger augmented activation trigger and expanded trigger. The process of generating the augmented activation trigger and the format thereof after generation were described above.

In another embodiment of the present invention the trigger service may provide a filtered stream option. As described above the filtered stream option may deliver the augmented activation trigger the interaction trigger and or the channel change trigger.

In another embodiment of the present invention the augmented activation trigger includes application URL information having same value with an URL element of an application element in the application parameter table. The URL element identifies a file which is part of the application and the application element is identified by the activation trigger. The application parameter table may be the above described TPT. The application may be a TDO. Here the application URL information may be appURL of the above described augmented activation trigger. Here the URL element may be a URL element in a TDO element of the TPT. The augmented activation trigger may be obtained from a URL element value in the TDO element of the TPT associated with the activation trigger in a generation process and the application URL information and the URL element may have the same value.

In another embodiment of the present invention the augmented activation trigger further includes an event information representing an event element in the application parameter table the event element identified by the activation trigger represents the event for the application the event information includes an action information having same value with an action attribute of the event element identified by the activation trigger and the action attribute indicates type of an action to be applied when the event is activated. The application parameter table may be the above described TPT. The application may be a TDO. Here the event information may be the event element of the above described augmented activation trigger. Here the event element may be an event element in a TDO element of the TPT. The action information may be action of the above described augmented activation trigger. Here the action attribute may be action of the event element of the TPT. The augmented activation trigger may be obtained from an event element value and action value in the TDO element of the TPT associated with the activation trigger in a generation process and the action information and the action attribute may have the same value.

In another embodiment of the present invention the second module delivers the augmented activation trigger at the activation time of the augmented activation trigger the second module delivers the interaction trigger when the interaction trigger is received by the first module and the second module delivers the channel change trigger when the channel is changed. The augmented activation trigger may be delivered at or before the activation time as described above interaction trigger may be delivered to the second screen application as soon as being received by the first device and the channel change trigger may be delivered when the channel is changed.

One embodiment of an apparatus for processing an interactive service as a second screen application running in a second device may include a first module and or a second module .

The first module may receive a discovery message request service descriptions and receive a response thereto. Here the first module may be the UPnP framework module of the above described second screen device.

The first module can be configured to receive a discovery message from a first device. The discovery message may serve to indicate the second screen support service provided by the first device. The first device may send the discovery message to only the second device or may multicast the discovery message to all devices in the home network. This operation may be performed for device discovery.

The first module can be configured to send a request for descriptions of the second screen support services to the first device. The first module may request the descriptions of the second screen support service provided by the first device from the first device. This operation may be performed for device discovery.

The first module can be configured to receive a response with the descriptions from the first device. The first module may receive the descriptions of the service as a response to the transmitted request. The first device may transmit the descriptions of the service thereof to the second screen application. The descriptions may be received. This operation may be performed for device discovery.

The second module may access the trigger service and receive the trigger. The second module may be the above described network protocol subsystem.

The second module can be configured to access a trigger service using information given in the descriptions. The second module may access the trigger service which is one of the second screen support services. The first device may receive the trigger from the broadcast stream or the internet server. Access to trigger service may be performed based on the descriptions received from the first device. Among the received descriptions the description of the trigger service may be used.

The second module can be configured to receive a trigger from the first device using the trigger service. The second module may receive the trigger from the first device using the trigger service. Here the trigger service may be one of the second screen support services. The trigger can be a signaling element whose function is to identify signaling and establish timing of playout of interactive events targeted to applications for a segment described by an application parameter table. Here the trigger may be one of a time base trigger an activation trigger an interaction trigger and or a channel change trigger. The interaction trigger may be a trigger for an interaction model other than a TDO interaction model. For example the trigger may have a content id term in the direct execution model. The channel change trigger may be the above described special channel change trigger and may be received when the channel is changed.

In one embodiment of the present invention the first module may also multicast the searching message. Multicasting may be performed before receiving the discovery message. The searching message may be used to detect a device for providing a second screen support service. According to the embodiment the searching message may be unicasted. By this step the second device may detect the first device.

In another embodiment of the present invention the trigger service may deliver the trigger as an unfiltered stream option. The unfiltered stream option may deliver all types of triggers to the second screen application as described above.

In another embodiment of the present invention in the unfiltered stream option all triggers may be delivered to the second screen application as soon as being received by the first device.

In another embodiment of the present invention the first module may also receive the augmented activation trigger from the first device. The augmented activation trigger may be generated by extracting and combining the information in the activation trigger and the information in the TPT at the first device. This may be equal to a process of generating the above described augmented trigger augmented activation trigger and expanded trigger. The process of generating the augmented activation trigger and the format thereof after generation were described above.

In another embodiment of the present invention the trigger service may provide a filtered stream option. As described above the filtered stream option may deliver the augmented activation trigger the interaction trigger and or the channel change trigger.

In another embodiment of the present invention the augmented activation trigger includes application URL information having same value with an URL element of an application element in the application parameter table. The URL element identifies a file which is part of the application and the application element is identified by the activation trigger. The application parameter table may be the above described TPT. The application may be a TDO. Here the application URL information may be appURL of the above described augmented activation trigger. Here the URL element may be a URL element in the TDO element of the TPT. The augmented activation trigger may be obtained from a URL element value in the TDO element of the TPT associated with the activation trigger in a generation process and the application URL information and the URL element may have the same value.

In another embodiment of the present invention the augmented activation trigger further includes an event information representing an event element in the application parameter table the event element identified by the activation trigger represents the event for the application the event information includes an action information having same value with an action attribute of the event element identified by the activation trigger and the action attribute indicates type of an action to be applied when the event is activated. The application parameter table may be the above described TPT. The application may be a TDO. Here the event information may be an event element of the above described augmented activation trigger. Here the event element may be an event element in the TDO element of the TPT. Here the action information may be action of the above described augmented activation trigger. Here the action attribute may be action in the event element of the TPT. The augmented activation trigger may be obtained from an event element value and action value in the TDO element of the TPT associated with the activation trigger in a generation process and the action information and the action attribute may have the same value.

In another embodiment of the present invention the augmented activation trigger is delivered at the activation time of the augmented activation trigger the interaction trigger is delivered as soon as possible and the channel change trigger is delivered when the channel is changed. The augmented activation trigger may be delivered at or before the activation time as described above the interaction trigger may be delivered to the second screen application as soon as being received by the first device and the channel change trigger may be delivered when the channel is changed.

The present invention relates to a method of interworking with a second screen device while receiving a broadcast service. If a UPnP framework is mounted in a receiver and an additional module capable of a second screen service while being compatible with the UPnP framework is mounted in the second screen device it is possible for a broadcaster to simply to implement the service screen service.

The UPnP framework may be provided by connecting electronic apparatuses to a home network and serving functions according to electronic apparatuses. The present invention relates to extension of an existing UPnP RemoteUI Client Service and UPnP RemoteUI Server Client. Accordingly it is possible to receive the second screen service while being compatible with existing UPnP apparatuses.

According to the present invention it is possible to provide supplementary information related to broadcast content using a conventional broadcast system.

According to the present invention it is possible to detect a time at which supplementary information related to broadcast content needs to be displayed and provide the supplementary information to a user at an appropriate time.

According to the present invention it is possible to provide supplementary information related to broadcast content to a second screen device.

It will be apparent to those skilled in the art that various modifications and variations can be made in the present invention without departing from the spirit or scope of the invention. Thus it is intended that the present invention cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

