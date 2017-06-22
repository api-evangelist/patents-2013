---

title: Meter data management systems, methods, and software with outage management capabilities
abstract: The present inventors recognized a need to leverage the data from Advanced Metering Systems (AMIs) in the management of electrical outages. To address this and/or other needs, they present inventors devised, among other things, systems, methods, and software that not only intelligently filter and communicate AMI outage data to Outage Management Systems (OMSs), but also facilitate communications between OMSs and multiple types of AMI systems. One exemplary system includes an outage management module that receives AMI outage data in the form of “last gasp” messages from meters and determines whether the OMS is already aware of a power outage associated with those meters. If the OMS is already aware of an outage associated with these meters, the outage management module excludes the outage reports from its communications with the OMS, thereby preserving its capacity to handle new outage information and overcoming a significant obstacle to using AMI data within OMSs.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09103854&OS=09103854&RS=09103854
owner: Landis+Gyr Analytics, LLC
number: 09103854
owner_city: Bloomington
owner_country: US
publication_date: 20130607
---
This application is a continuation application of and claims priority to U.S. patent application Ser. No. 12 854 168 filed on Aug. 10 2010 now U.S. Pat. No. 8 462 014 which application claims priority to U.S. Provisional Patent Application 61 273 994 which was filed on Aug. 10 2009 both of which are incorporated herein by reference in their entirety. Additionally co owned U.S. patent application Ser. No. 12 496 224 which was filed on Jul. 1 2009 and which is a continuation of U.S. patent application Ser. No. 11 059 089 filed on Feb. 7 2005 now U.S. Pat. No. 7 557 729 is also incorporated herein by reference in its entirety. Co owned U.S. patent application Ser. No. 12 706 041 which was filed Feb. 16 2010 is also incorporated herein by reference in its entirety.

A portion of this patent document contains material subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent files or records but otherwise reserves all copyrights whatsoever. The following notice applies to this document Copyright 2009 2010 Ecologic Analytics LLC.

Various embodiments of the present invention concern advanced metering systems AMSs meter data management systems MDMSs and outage management systems OMSs for electric utility companies.

Electric utility companies regularly collect usage data from meters. Over the last few decades many public utilities have modernized their data collection using automated meter reading AMR to reduce the time and expense of collecting this data manually. More recently technology has evolved to more advanced metering systems generally referred to as Advanced Meter Infrastructure AMI that allows reliable two way communications with meters and utilities have responded to the dynamic pricing of electricity by shifting from once a month meter readings to daily hourly or even sub hourly meter readings.

To facilitate the management of the fantastic amounts of data generated from increased read frequency many utilities are now using meter data management systems MDMSs which not only manage and organize the incoming AMI data into a database but also validate it fill in missing data and generally ensure that utilities have sufficiently accurate data to bill their customers. One of the leading providers of MDMSs is Ecologic Analytics of Bloomington Minn. the employer of the present inventors.

One problem recognized by the present inventors concerns AMI systems and outage management systems OMSs . An OMS is a computer system used by utility operators to manage the restoration of electrical service in the event of a power outage. These systems typically receive telephone outage reports from customers through a call center and or Interactive Voice Response IVR system and plot them on a digital map or model of the electrical distribution network. The OMS also includes a rules engine that uses reported outage locations and the network model to determine the source and scope of the outage and thus provide valuable information for restoring electric power to outage areas.

Although it has been known for some time that AMI systems held the potential to provide outage reports in the form of last gasp messages from meters that had lost power little if anything at all has been achieved in actually taking advantage of this possibility. One problem is that AMI systems can generate orders of magnitude more call equivalent last gasp and restore messages in any given time span time than customers can and OMSs simply lack the capacity to handle this level of input.

Consider for example that AMI meters can report outages at any time of day or night whereas customers may have long periods of time such as while away at work or while sleeping when they are unaware of power outages and thus unlikely to report them. Moreover even when they are aware many customers rely on their neighbors to report outages or they simply assume that the utility will already know. In contrast all the AMI meters affected by an outage would attempt to automatically report the outage almost simultaneously regardless of time of day. Thus larger outages affecting thousands and or even millions of customers would easily overwhelm a conventional OMS.

Another issue is that larger utilities often have a diverse set of AMI meters and Head End systems from different manufacturers with those from one manufacturer communicating using proprietary protocols that are distinct from and incompatible with those of another. Conventional OMSs which rely on phoned in reports not only lack a way of communicating with AMIs but also have no mechanism for optimizing interactions with multiple types of AMI technologies.

Accordingly the present inventors have recognized a need for bridging the gap between the rich data available in AMIs and the ability of OMSs to actually use it.

To address this and or other needs the present inventors devised among other things meter data management systems methods and software that not only intelligently filter and communicate AMI outage data to OMSs but also facilitate communications between OMSs and multiple types of AMI systems. One exemplary MDMS includes an outage management module that receives AMI outage data in the form of last gasp messages from meters and determines whether the OMS is already aware of a power outage associated with those meters. If the OMS is already aware of an outage associated with these meters the outage management module excludes the outage reports from its communications with the OMS thereby preserving the OMS s capacity to handle new outage information.

Additionally the outage management module in the exemplary system helps verify restoration of power by intelligently communicating with meters in an AMR system. For example the exemplary system automatically collects meter data from meters that have been re energized and instead of contacting these meters in response to requests to verify restoration the system can generate a verification report based on the data it already has thereby not only rapidly responding to verification requests but also reducing communication traffic between the MDMS and the AMR system.

This document which incorporates the drawings and the appended claims describes one or more specific embodiments of an invention. These embodiments offered not to limit but only to exemplify and teach the invention are shown and described in sufficient detail to enable those skilled in the art to implement or practice the invention. Thus where appropriate to avoid obscuring the invention the description may omit certain information known to those of skill in the art.

As an aid to the reader the following exemplary definitions are offered. However the definitions are not intended to limit the scope of the claimed invention. Where there is a conflict between a meaning provided here and the meaning suggested or required by the contextual usage of the term in the description preference should be given to the meaning suggested by the context.

AMI systems include one or more meters or AMR automated meter reading headend data servers for one or more types of meters and or AMR systems. Exemplary systems include systems made or sold by DCSI Hexagram Cellnet Silver Spring Networks SSN and Landis Gyr. AMI systems are coupled or couplable via a two way wireless or wireline communications network for example Ethernet to provide meter read data as well as meter energization status outage status messages and communication device status messages to MDMS . Note that in some embodiments one way communications are used but these embodiments may be unable to support power status checking or other desirable interrogations of meters or other devices. 

MDMS which provides meter data management and outage management functionality includes a processor module a memory module a validation editing and estimation VEE module and an outage management module . In the provisional application referenced in the background the outage management module was referred to as OVE RE. 

Processor module includes one or more local or distributed processors controllers or virtual machines. In the exemplary embodiment processor module assumes any convenient or desirable form. In some embodiments one or more of the processors are incorporated into servers such as SQL database servers.

Memory module which takes the exemplary form of one or more electronic magnetic or optical data storage devices stores VEE module and outage management module .

In the exemplary embodiment VEE module which incorporates functions sometimes referred to in the provisional application and other applications referenced herein as WAVE and or iWAVE module includes one or more sets of machine readable and or executable instructions for receiving and processing daily and or interval meter read data from AMI systems and potentially other metering systems. The exemplary VEE processing is performed according to rules and procedures such as those described in U.S. Pat. No. 7 557 729 and co pending and co owned U.S. patent application Ser. No. 12 706 041 both of which are incorporated herein by reference. Results of this processing validated edited and or estimated daily and or interval meter read data is stored within VEE module . Note that some embodiments use meter read data as a proxy for the power up or restore messages at a given point in time. 

Outage management module OMM which is described in detail using the flow chart of includes one or more sets of machine readable and or executable instructions for receiving and processing end point meter energization status messages outage status messages from AMI systems or other enterprise systems outage status messages and related requests from OMS and anticipated outage related messages from external systems .

In general operation of this embodiment OMM uses JMS queues not shown to receive direct and indirect updates from designated or approved AMI head end systems within AMI systems . Direct updates include outage status notifications and responses to ping power status requests. Indirect updates include meter read data which can be used as proxy for the energized status of the meter at the observation time of the meter reading. In some embodiments OMM can optionally accept outage status notifications from other external systems like a CIS or IVR system. When available using the information from the AMI head end system s and other external systems OMM tracks what it deems to be the current energization status of each end point.

Also OMM accepts outage status notification messages from OMS for end points as well as distribution transformers. OMM uses these outage status notifications to track what OMS currently believes the energization status to be for each end point. Whenever OMS sends OMM the energization status of a distribution transformer OMM infers the same energization status to the end point s associated with that distribution transformer. In addition OMM can perform periodic proactive power status checks referred to as restoration scout function to identify end points that have transitioned to the energized state without that transition having been reported to OMM by the aforementioned direct and indirect update mechanisms. Typically the restoration scout function is enabled for metering systems that are not able to deliver restoration messages to OMM for a sufficiently high percentage of re energized end points however the restoration scout function may be used with any metering system technology.

OMM generally uses all of the energization state and energization state transition data at its disposal to best identify and scope outages and to verify outage restorations according to the particular business rules of each utility. OMM is a highly configurable system that can operate with or without a separate OMS. It can be proactive or reactive in scoping activities and in detecting and verifying restorations.

Configuration module stores OMM configuration parameters and machine readable and or executable instructions for providing a configuration GUI to an access device such as access device . The OMM configuration parameters support and define the specific functional and business flow requirements of each utility. A listing of the OMM configuration parameters along with default or recommended settings to achieve behaviors associated with an exemplary OMM installation is included as Appendix A. Notably one or more of the configuration parameters are representative or indicative of rules and or thresholds within OMS . For example one or more of the configuration parameters are based on threshold number of end point outages that the OMS uses to infer outage of the associated distribution transformer. OMM uses this type of configuration data to minimize the amount of end point status information that it communicates to the OMS to indicate a transformer outage. Conventional OMS is typically not designed to receive transformer outage information from customers. 

Many of the configuration parameters used to drive the OMM processing can be specified as a function of outage region outage mode and metering system. Outage modes are set individually by outage region and are normally determined automatically as a function of time of day time based outage mode and the percentage of de energized service points in a given Outage Region storm based or threshold based outage mode . Outage modes can also be switched manually by an authorized user using a graphical user interface such as Ecologic Analytics Navigator interface. In addition to configuration parameters there are Assumptions and Conventions associated with the behavior of the OMM. A listing of these is included in Appendix B.

OM data structures include data structures such as tables and relational databases containing the data used by OMM to function. Data structure which is generally representative of the data structures in the exemplary embodiment includes a meter or end point identification ID A which is logically associated with one or more data fields such as data fields B H. Data field B provides a technology indicator to indicate the AMI technology type of the end point. For example the technology indicator can indicate a system from one of the following manufacturers DCSI Hexagram Cellnet Silver Spring Networks SSN and Landis Gyr.

Data field C provides a geographic region indicator for a geographic region to which the corresponding end point is assigned. Data field D provides an indication of the outage mode that is currently in effect for the region. Data field E provides a distribution transformer XFRMR identifier which identifies a distribution transformer that feeds power to the corresponding end point. Data field F provides an identifier for a source side protective device such as fuse or breaker that is coupled to the end point.

Data field G provides energization status indicator indicative of the energization status currently held by OMS for the corresponding end point for example energized or de energized. Data field H provides energization status indicator indicative of the energization status currently held by OMM for the corresponding end point for example energized confirmed energized inferred de energized confirmed de energized inferred or indeterminate. Data fields G and H include time stamp information. Data field H provides event information for the corresponding end point indicating a historical record of each state change of the end point and when it occurred.

OMS can take a variety of computerized forms which rely on one or more processors and memory. In the exemplary embodiment OMS includes OMS data a rules engine and a network model .

External systems include one or more utility management related systems which may provide or require information related to outage management. In the exemplary embodiments these systems include customer information systems planned outage systems and service order processing systems one or more of which can provide information to OMM regarding anticipated outage events. With data regarding anticipated outage events for one or more end points OMM can avoid communicating outage reports regarding these points to OMS .

Access device provides a mechanism for defining the configuration parameters of OMM via a graphical user interface. In the exemplary embodiment access device takes the form of a personal computer workstation personal digital assistant mobile telephone or any other device capable of providing an effective user interface with a server or database. Specifically access device includes one or more processors or processing circuits a memory a display and input devices e.g. keyboard and mouse .

Processor module includes one or more processors processing circuits or controllers. In the exemplary embodiment processor module takes any convenient or desirable form. Coupled to processor module is memory .

Memory stores code machine readable or executable instructions for an operating system a browser and a graphical user interface GUI . In the exemplary embodiment operating system takes the form of a version of the Microsoft Windows operating system and browser takes the form of a version of Microsoft Internet Explorer. Operating system and browser not only receive inputs from keyboard and selector but also support rendering of GUI on display . Upon rendering GUI which is defined at least in part using applets or other programmatic objects or structures from MDMS presents data in association with one or more interactive control features or user interface elements . In the exemplary embodiment GUI includes an OMM dashboard interface A and an OMM configuration interface B.

The upper third includes regional counts for Outage enabled end points AMI enabled end points Transformers Network equipment which are visible in the figure and counts for de energized transformers De energized end points OMM or AMI De energized end points as reported by the OMS and De energized network equipment and Network equipment for which a communication down notification has been received. Selecting a particular Outage Region results in update of the middle third of the screen showing details on transformers end points and network equipment.

At block the exemplary method begins with defining configuration parameters for the outage management module of system . In the exemplary embodiment this entails defining one or more configuration parameters as outlined in Appendix A using configuration GUI B. show an exemplary implementation of GUI B.

More particularly interface includes three main interface tabs a dimensional editor tab a system wide default tab and a configurations tab . Dimensional editors tab allows users to view and define Outage Regions Outage Modes and AMI vendor metering systems via selection of respective control features for example radio buttons and . The parameter settings for outage regions outage modes and AMI vendor metering systems are viewed and defined on configurations tab . 

When region radio button is selected on the dimensional editors tab as depicted in interface allows users to add or edit Outage Regions in OMM. In addition the interface lets users specify the current Outage Mode for an Outage Region if OMM is running in manual mode determination as determined by the OMM IS AUTOMATED MODE DETERMINATION ENABLED parameter . Adding an outage region entails clicking on an add button A to display an add region window where a user can enter a Region ID Region Description and specify the desired mode determination. If system default is selected the parameter IS AUTOMATED MODE DETERMINATION ENABLED on the system wide defaults tab under the Mode Determination category will be used. If automatic is selected the IS AUTOMATED MODE DETERMINATION ENABLED to Y as a custom configuration on the Configurations tab under the Mode Determination category for the Outage Region being added. If manual is selected then a current mode drop down box is enabled allowing manual selection of the current Outage Mode for the Outage Region you are adding as explained below. Similar windows for editing and removing windows can be invoked using edit and remove buttons.

When modes radio button is selected interface screen is displayed. This screen allows users to add or edit Outage Modes used by OMM. And when metering systems radio button is selected interface screen or region is displayed allowing users to define all of the external metering systems with AMI systems and outage enable any of these metering system. When a meter is outage enable a row is created in the METERING SYSTEMS table. Interface screen also allows one to outage disable a metering system thereby removing the row in the METERING SYSTEM table as long as there are no dependent service points in an OUTAGE SERVICE POINT table used by the OMM. In the exemplary embodiment the AMI enabled status is informational only and cannot be changed.

Selection of system wide defaults tab results in display of interface screen as shown in . Interface screen allows users to view and change system wide defaults for all OMM parameters. OMM is initially configured with default values for all parameters for these system wide settings. There is one exception the mode determination rules parameter which specifies whether an outage mode is storm based or time based along with either a storm threshold or a start time these system wide defaults can be configured only by the client utility as explained below. In the exemplary embodiment some parameters can be set only at the system level these are noted with an X in the System Level column in the parameter table included within Appendix A. All system level default values can be changed by the client utility. In addition many parameters can also be customized by the client utility at the outage region outage mode and or AMI vendor metering system levels as indicated in Appendix A. Interface screen includes a parameter category display and selection region which shows that OMM parameters are grouped into eleven selectable categories 

Selection of configuration tab in results in display of interface screen as shown in . As noted earlier all OMM parameters have system level default values. Interface screen allows users to view and customize these parameter values at various levels outage region outage mode and or metering system depending on the dimensions applicable to each parameter as defined in Appendix A. Parameters can also be configured so that they apply to a particular combination of outage region outage mode and or metering system again according to the applicable dimensions of each parameter. The configuration screens automatically handle the level or levels at which a parameter can be set and it is possible to copy existing parameter sets.

In particular interface screen includes a parameter category display and selection region which shows that OMM parameters are grouped into the same eleven selectable categories used in screen for system wide defaults 

In addition there are mode determination rules that specify whether an outage mode is storm based or time based along with either a storm threshold or a start time. These are properties of each outage region that a client utility sets up and are set via the Mode Determination Rules for the Mode Determination category. Changing a parameter value on any of these screens entails typing in the desired value or selecting the appropriate radio button and then selecting the save option. Further information regarding the exemplary configuration interface is included in Appendix C.

In block MDMS receives energization status messages such as last gasp and restore messages and or daily and interval read data from AMI systems . Exemplary execution continues at block .

Block entails determining whether the outage data is known or unknown by the OMM based on the AMI status data it holds. In the exemplary embodiment when the MDMS receives a last gasp message from an end point meter it sends an outage status notification message to OMM with an energization status of de energized confirmed . When OMM receives this message it initially determines for example by checking a service or endpoint status table whether that end Point was already in a de energized confirmed or de energized inferred state. If it was OMM log the time of this latest notification but takes no further action to process the message or pass it to the OMS instead branching back to block to process other received data. However if the outage of this meter is unknown execution proceeds to block .

In block OMM waits a configurable amount of time for a restoration message for the same End Point. The duration of the wait period is determined by the configuration parameters defined at block . In some embodiments the wait period is a function of the geographic region associated with the end point and the outage mode in effect for that region. Outage mode can be function of the time of day or size of the outage. The wait time allows OMM to disregard momentary outages and prevent them from affecting distribution transformer energization status inferencing and or from being sent to the OMS. After the wait period execution continues at block .

Block entails checking if a restoration message for the end point has been received. If the restoration message has been received indicating that the outage condition no longer exists and the end point is operational execution branches back to block to process other messages. However if no restoration message for the end point has been received execution proceeds to block .

Block determines whether the end point outage represented by the outage message is associated with a larger outage such as a distribution transformer outage. In the exemplary embodiment this transformer outage determination is performed using two different methods. The first method entails determining whether a threshold minimum number of end points or threshold percentage of end points or both associated with the transformer. The threshold minimum and threshold percentage are configuration parameters defined in block . If the threshold minimum number or percentage is satisfied the outage management module will designate the distribution transformer associated with the end point as exhibiting an outage or more specifically as de energized inferred. The second method is based upon identification of simultaneous outage events on multiple distribution transformers having a common nearest source side protective device. If a configurable number of last gasp messages are received in a configurable time frame across multiple distribution transformers having a common nearest source side protective device OMM will also cause the energization state of these multiple distribution transformers to be set to de energized inferred.

If either of the two methods indicates that its condition for inferring the outage to the distribution Transformer level is satisfied OMM will infer the de energized state of the given transformer end point to other end points on the affected transformer s as indicated at block . Inferring the outage to the other end points entails updating the status of the end points in a state table OM data to indicate de energized confirmed along with a date stamp for the change. If inferring outage of the transformer is not possible execution branches to block .

In block the system if configured at block to do so initiates first level scoping which involves affirmatively determining whether the other end points associated with the distribution transformer for the de energized end point are energized or not. To this end the exemplary embodiment performs a power status check of each of the end points specifically requesting the metering system s to ping all of the AMI enabled end points on the respective distribution transformer.

In the exemplary embodiment the power status checking known as First Level Scoping can be controlled via a configuration parameter that is a function of Outage Region Outage Mode and Metering System. This allows the utility to optimize the use of AMI network bandwidth under a wide range of operational scenarios ranging from normal operations to large scale storms.

In block OMM again attempts to determine whether the there is a transformer level outage using the first inference method used at block . Specifically the OMM determines whether a threshold minimum number of end points or threshold percentage of end points associated with the transformer associated with the end point are also experiencing an outage. If the threshold minimum number or percentage is satisfied execution branches to block .

In block the OMM infers that all the end points associated with the distribution transformer for the end point message under consideration are exhibiting an outage. In the exemplary embodiment this inferring entails labeling or updating OMM status in OM data for the relevant end points as de energized inferred. Execution continues at block .

Block entails determining whether any of the inferred or determined end point outages is associated with an anticipated outage condition. This entails queuing the messages and then checking them against a listing of OMS Anticipated Outage Events. OMM may expect end points to have anticipated outage events based on information received from external systems such as a Customer Information System for locks and shut offs for non pay a Planned Outage System or a Service Order System. There are interfaces to the OMM system to create and delete these Anticipated Outage Events. Note If desired the filtering of Anticipated Outages can be disabled via a configuration parameter. 

At block OMM receives outage report data from OMS and updates the OMS status fields for the effected end points in OM data . Execution continues at block .

Block entails notifying OMS of the outage using a minimum number of energization status messages. In the exemplary embodiment this entails blocking any outage status messages that were deemed to be associated with an Anticipated Outage or that have are already indicated by their OMS status fields within OM data to be de energized This blocking is intended to lessen the burden on OMS by eliminating redundant or otherwise unwanted messages. However if an end point is already part of a known OMS outage but the outage event time for the new end point outage status notification message is later by more than a configurable parameter than the start time of the known OMS outage then the new outage event time will be retained by OMM for later use in restoration validation processing.

In block the utility handles the outage using OMS . In the exemplary embodiment this entails the utility declaring managing and restoring the outage using the OMS and other conventional systems. As repairs are made and power is restored repair crews and customers may phone in transformer and end point restorations.

In block OMM receives restoration power up messages from AMI systems . As these messages are received OMM will update the end point energization status with energized confirmed state indicators and record the time of the energization status change in the respective event logs for the end points. Execution continues at block .

In block OMM receives restoration messages from OMS . In the exemplary embodiment OMS send OMM unsolicited outage status notification messages whenever OMS deems that the energization state of an end point has changed. In response OMM updates the OMS status tables indicating OMS s view of the energization state of the relevant end points. In response to a restoration notification message of this type if OMM has previously received an Outage Status Notification from AMI indicating that the End Point is De Energized and the outage event time associated with that notification is later than the outage start time known to OMS by more than a configurable parameter then OMM will send a new Outage Status Notification Message to OMS to inform OMS that the End Point may be de energized. Execution continues at block .

In block OMM receives a restoration verification request from OMS . Exemplary execution advances to block .

At block OMM responds to the request by initiating a power status check of all the end points in the verification request that do not have an energized confirmed status in the OM data . In other words if any of the end points in the request are indicated as being de energized energized inferred or indeterminate the OMM communicates with the corresponding AMI systems within AMI systems requesting initiation of a power status check of those end points. However for those end points indicated by the OM data as being energized confirmed the OMM will not request initiation of the power status check thereby conserving bandwidth on the communications channels with AMI systems and between the headend servers within AMI systems and their associated end points.

In block OMM replies to the verification request with the results of any power status checks and or the confirmed energized data that was collected prior to the OMM s receipt of the verification request. If the Energization Status of one or more of the End Points could not be determined for any reason the reply will also contain an error message for each such End Point indicating the specific error that occurred. The OMS can then use the returned information to determine the existence of new or nested outages. In some embodiments the OMM also includes special logic to help identify the possible existence of Nested Outages.

In some embodiments the OMM also includes special logic to help identify the possible existence of Nested Outages following a Momentary Outage scenario. Restoration Messages that OMM receives from a Metering System for which there is no known outage in OMS will be recorded grouped by common Source Side Protective Device and analyzed. If the number of these messages received within a configurable time period for any group exceeds another configurable parameter then the corresponding list of restoration events will be sent to OMS using a special message type that indicates a potential Nested Outage.

In block the utility declares the outage condition over assuming that the reply to the verification request has indicated complete restoration. In the event of less than complete verification of the restoration the OMS may request scoping to be performed.

In the exemplary embodiment there are two additional ways that information concerning restoration events can be made known to OMM 1 via the receipt of meter readings that serve as an indication that the End Point was energized at the observation time of the meter reading and 3 via the Restoration Scout. The variety of methods by which OMM can be made aware of restoration events collectively is designed to minimize the probability that restoration events go undetected for significant periods of time. This in turn helps to improve the utility s outage statistics.

OMM also has a configuration parameter to control integration between OMM and VEE processing. If this function is enabled the outage state and outage event history tracked by OMM is made available to the MDMS VEE function allowing VEE to estimate zero consumption for known outage periods.

Whenever OMM receives an unsolicited message from a Metering System OMS or another external system for an End Point or Distribution Transformer that is not known to OMM the error will be logged and no further processing of the message will occur.

Whenever OMM receives from AMI OMS or another external system a message containing information associating an End Point to a Distribution Transformer OMM will attempt to validate the End Point to Distribution Transformer association before further processing the message. If the validation fails the error will be logged and in the case of a request reply message an error code indicting the failure will be returned to the calling system.

Listed below in alphabetical order are descriptions of the OMM parameters that affect operation of the exemplary OMM. These parameters as noted above can be readily configured using configuration GUI as described herein for example in Appendix C.

All OMM parameters are configured initially with system level default values except for MODE WINDOW START TIME and STORM MODE THRESHOLD which must be set by the client utility for each outage mode used by that client utility as described below in a section entitled Setting System wide Mode Determination Rules once the client utility has configured the outage modes it will use.

Notes regarding the table Parameters that can be set only at a system level have an X in the System Level Only column. Some embodiments may not be so limited. Parameters that can be customized by outage region outage mode and or metering system have a check in those columns. If a parameter can be customized at multiple levels then it is possible to set values for any or all combinations of those levels. For example one can set the RESTORATION SCOUT ENDPOINT PERCENTAGE parameter to 25 for a Big Storm Outage Mode in Region 1 for DCSI to 20 for a Big Storm Outage Mode in Region 1 for SSN to 20 for a Big Storm Outage Mode in Region 2 for DCSI and to 15 for a Big Storm Outage Mode in Region 2 for SSN.

In addition to the parameters listed below it is also possible to set outage enabled to Yes or No for each metering system whether AMI enabled or not. When a metering system is Outage enabled a row is inserted in the METERING SYSTEMS table when a metering system is Outage disabled the row is deleted. However a metering system cannot be Outage disabled if that metering system has dependent service points in the OUTAGE SERVICE POINT table. Furthermore as noted in the IS VEE INTEGRATION ENABLED parameter description the WAVE Outage Flag parameter controls whether WAVE uses the OUT estimation rule zero estimation on a full day outage day .

In addition to configuration parameters the following assumptions and conventions define the behavior of the outage management module in the exemplary embodiment 

The Configuration option on the Outage menu illustrated in in Navigator is used to set up OMM parameters. Described in the topics below are the Dimensional Editors System wide Defaults and Configurations tabs on the Outage Configuration screen 

Following the topics that describe these screen tabs is a topic that describes each of the OMM Parameters.

The Dimensional Editors tab on the Outage Configuration screen lets you view and define Outage Regions Outage Modes and AMI vendor s metering systems. The parameter settings for Outage Regions Outage Modes and AMI vendor s metering systems can be viewed and defined on the Configurations tab on the Outage Configuration screen. 

When the Regions radio button is selected on the Dimensional Editors tab on the Outage Configuration screen the screen shown in is displayed.

This screen lets you add or edit Outage Regions used in OMM. In addition it lets you specify the current Outage Mode for an Outage Region if you are running in manual mode determination as determined by the OMM IS AUTOMATED MODE DETERMINATION ENABLED parameter .

OMM is configured initially with just one Outage Region called SYSTEM WIDE DEFAULT . This is the only Outage Region that is currently valid in MDMS 2.6.1 as explained below.

In order to use Outage Regions in OMM the Electric Distribution System Network Equipment Synchronization process Interface or another DSE interface needs to be updated both by Ecologic Analytics and by the client utility to provide the Outage Region for all locations. This value will get populated in the OUTAGE REGION ID column in the LOCATION table. Until the OUTAGE REGION ID column is populated via a DSE interface the Outage Synchronization Process outage sync.ksh will set the Outage Region in the OMM tables to SYSTEM WIDE DEFAULT . When the Electric Distribution System Network Equipment Synchronization process Interface or other DSE interface is updated to provide Outage Region then the client utility will use this screen to add Outage Regions.

The grayed out Current Mode that is initially displayed is merely the alphabetically first of your existing Outage Modes.

To manually change an Outage Mode highlight the desired region its Mode Determination should be Manual and click on Edit to display the Edit Region window as illustrated in .

On the Edit Region window select the desired Outage Mode from the Current Mode drop down list. The modes that appear on this drop down list with the exception of the DEFAULT mode are defined by the client utility as explained in the next topic. See .

When the Modes radio button is selected on the Dimensional Editors tab on the Outage Configuration screen the screen shown in is displayed.

OMM is configured initially with just one Outage Mode called DEFAULT . Once the client utility adds its desired Outage Modes the DEFAULT Outage Mode should be deleted.

Type in a Mode Name and a Mode Description. It s a good idea to include wording that indicates whether the mode is time based or storm based. For a description of how these two types of outage modes are used see the Automated Outage Mode Determination AOMD Process topic under OMM Components later in this guide. Then click on OK.

Once you ve created modes you need to define mode determination rules which specify whether a mode is time based or storm based along with either a start time or storm threshold . These can be specified either at the mode level applicable across all regions or at the region level. See the Specifying Mode Determination Rules topic under Specifying Mode Determination Rules under Configurations Tab on Outage Configuration Screen below for specifics on how to these values.

When the Metering Systems radio button is selected on the Dimensional Editors tab on the Outage Configuration screen the screen shown in is displayed.

This screen displays all of the external metering systems defined in the MR PROVIDER table and lets you Outage enable any metering system. When you Outage enable a meter a row is created in the METERING SYSTEMS table. You can also Outage disable a metering system thereby removing the row in the METERING SYSTEM table as long as there are no dependent service points in the OUTAGE SERVICE POINT table. The AMI enabled status is informational only and cannot be changed.

To change the Outage enabled status for a metering system highlight the metering system and click on Edit to display the Edit Metering System window as illustrated in .

The Outage enabled checkbox is grayed out if the metering system is already Outage enabled and has records in the OMM system. Check or uncheck the box as appropriate and click OK.

The System wide Defaults tab on the Outage Configuration screen lets you view and change system wide defaults for all OMM parameters. OMM is initially configured with default values for all parameters for these system wide settings. There is one exception the Mode Determination Rules that specify whether an outage mode is storm based or time based along with either a storm threshold or a start time these system wide defaults can be configured only by the client utility as explained below. 

Some parameters can be set only at the system level these are noted with an X in the System Level column in the Descriptions of OMM Parameters topic later in this guide.

All system level default values can be changed by the client utility. In addition many parameters can also be customized by the client utility at the outage region outage mode and or AMI vendor s metering system levels as described in the Descriptions of OMM Parameters topic later in this guide as well as under the individual OMM component descriptions in the OMM Components topic later in this guide.

The parameters for each of these categories are displayed on a separate screen as shown in the topics below.

To change a system wide default parameter value on any of these screens type in the desired value or select the appropriate radio button and click Save.

When the AMI OSN Processing category is selected the settings for several technical OMM parameters are displayed as illustrated in .

When the CLX OSN category is selected the settings for parameters used by the Outage Status Notification Adapter from CLX DDD are displayed as illustrated in .

When the DEFAULT category is selected the setting for the LOG LEVEL parameter is displayed as illustrated in .

When the Filtering category is selected the settings for parameters that control how events are filtered during OMM processing as illustrated in .

When the Mode Determination category is selected the settings for parameters used by the Automated Outage Mode Determination AOMD process are displayed as shown in including whether automated mode determination is enabled or not 

This system level screen does not include the Mode Determination Rules option that appears on the version of this screen on the Configurations tab as explained in the topic below.

There are other mode determination rules that specify whether an outage mode is storm based or time based along with either a storm threshold or a start time. These are properties of a particular outage region and can only be configured on a system level by going to the Configurations tab selecting the Mode Determination category selecting Mode Determination Rules customizing the mode for that region and then using the Promote Rules To Defaults option to promote those rules to a system wide default mode.

See the Specifying Mode Determination Rules topic under Specifying Mode Determination Rules under Configurations Tab on Outage Configuration Screen below for specifics on how to specify system level values for these mode determination rules.

When the Nested Outage Processing category is selected the settings for parameters used by the Nested Outage Detection NOD Process are displayed as shown in .

When the OCDB category is selected the settings for parameters used by the Outage Status Notification Adapter from the Cellnet OCDB are displayed as shown in .

When the Outage Scoping and Restoration category is selected the settings for various scoping and restoration parameters used by the External Scoping Requests

Processor the First Level Scoping FLS Processor the Anticipated Outage Create Delete Processor AOCDP the Cellnet USC Power Status Check PSC Adapter Restoration Verification Application RVA Adapter the Restoration Verification Processor RVP and the Sustained Endpoint Outage Processor SEOP are displayed as shown in .

When the OVE RE Integration category is selected the settings for general enablement parameters are displayed as shown in . IS OVE RE ENABLED is used by all OMM processes. IS OMS INTEGRATION ENABLED is used by the Automated Outage Mode Determination AOMD Process the Nested Outage Determination NOD Process the OMS OSN Sender Process the OMS OSN Receipt Process the Restoration Notification Processor from Metering Systems the Restoration Verification Processor RVP the Sustained Endpoint Outage Processor SEOP and the Populate Outage History Process. IS VEE OUTAGE INTEGRATION ENABLED is used by the Populate Outage History Process.

When the Power Status Inferencing category is selected the settings for parameters used by the Restoration Notification Processor from Metering Systems and the Sustained Endpoint Outage Processor SEOP are displayed as shown in .

When the Restoration Scout category is selected the settings for parameters used by the Restoration Scout are displayed as shown in .

As noted earlier all OMM parameters have system level default values. The Configurations tab on the Outage Configuration screen lets you view and customize these parameter values at various levels Outage Region Outage Mode and or Metering System depending on the levels dimensions at which each parameter can be set see the Descriptions of OMM Parameters topic later in this guide .

Parameters can also be configured so that they apply to a particular combination of Outage Region Outage Mode and or Metering System depending on the levels dimensions at which each parameter can be set. The configuration screens automatically handle the level or levels at which a parameter can be set and it is possible to copy existing parameter sets as explained in the Automatic Handling of Parameter Levels topic below.

The parameters for each of these categories are displayed on a separate screen as shown in the topics below.

In addition there are mode determination rules that specify whether an outage mode is storm based or time based along with either a storm threshold or a start time. These are properties of each outage region that a client utility sets up and are set via the Mode Determination Rules option on the Outage Configuration screen for the Mode Determination category. This configuration is included in the topics that follow.

To change a parameter value on any of these screens type in the desired value or select the appropriate radio button and click Save.

The topics below contain examples of how the level or levels at which each parameter can be set are handled automatically as well as how to copy parameter sets 

For example the HONOR BOOT COUNT OVER EVENT TIME parameter is one of a handful of parameters that can be set only at the metering system level.

Because this parameter can be set only at the metering system level all of the customization options on the right side of the screen are grayed out when Configure Regions is selected as shown in only the system level default value is shown and it is grayed out because it cannot be changed here.

Because this parameter can be set only at the metering system level all of the customization options on the right side of the screen are also grayed out when Configure Modes is selected as shown in .

Because this parameter is configurable at the metering system level the New option is not grayed out when Configure Metering Systems is selected. See .

If you click on New the first row under Customizations is highlighted and the radio buttons for Value are now enabled as shown in .

To set this parameter select the desired value as noted above this parameter can only be set at the metering system level so the Region and Mode drop downs are disabled and click Save to save the desired setting. Once you save a setting it is displayed under Customizations as shown in .

To delete a setting select the row for the setting you wish to delete under Customizations and click on Delete as shown in .

The IS AUTOMATED MODE DETERMINATION ENABLED parameter can be set only on the region level so editing is enabled when Configure Regions is selected but the Mode and Metering System drop downs are disabled as shown in .

The ENDPOINT THRESHOLD ABSOLUTE parameter is an example of a parameter that can be set at the Outage Region Outage Mode or Metering System level or combinations of those levels. When New is selected for this parameter Mode and Metering System are both enabled as shown in .

The word is displayed initially for Mode and Metering System. If you wish to set this parameter at the region level only do not change these settings type in the desired value and click on Save.

If you wish to set this parameter for a region mode combination click on the Mode drop down and select the desired mode as shown in .

If you wish to set this parameter for a region mode metering system combination click on the Metering System drop down and select the desired metering system as shown in .

You can also set this parameter for a region metering system combination by leaving Mode unselected as shown in .

You can also set this parameter for a mode metering system combination by selecting Configure Modes selecting the desired mode and leaving Region unselected as shown in .

Once you have set up parameters for an Outage Region Outage Mode or Metering System you can copy those settings to another region mode or metering system. To do so select the region mode or metering system for which you want to set parameters select the region mode or metering system from which you want to copy in the Copy From drop down it automatically displays regions modes or metering systems as appropriate and click on Copy as shown in .

When the AMI OSN Processing category is selected the settings for several technical OMM parameters are as shown in .

When the CLX OSN category is selected the settings for parameters used by the Outage Status Notification Adapter from CLX DDD are displayed as shown in .

When the DEFAULT category is selected the setting for the LOG LEVEL parameter is displayed as shown in .

When the Filtering category is selected the settings for parameters that control how events are filtered are as shown in .

When the Mode Determination category is selected the settings for parameters used by the Automated Outage Mode Determination AOMD process are displayed including whether automated mode determination is enabled or not. See .

The first three Mode Determination parameters are grayed out on this screen because they can only be set as system level values on the System wide Defaults tab.

The Mode Determination Rules option described below lets you specify whether an outage mode is storm based or time based and specify either a storm threshold or a start time as described in the next topic.

When you select Mode Determination Rules for the Mode Determination category this option is displayed only if Configure Regions is selected at the top of the screen a special screen is displayed for entering mode determination rules. See .

If you want to use system wide default values for mode determination the easiest way to do so is to select the SYSTEM WIDE DEFAULT region. You can however use another region to perform this process.

Then perform the following steps for each of the modes for which you want to set system wide defaults. For example if you are going to use three storm based modes Small Storm Mode Medium Storm Outage Mode and Large Storm Outage Mode and two time based outage modes Day Outage Mode and Night Outage then you need to repeat these steps for each of those outage modes.

If you wish to use mode defaults only then select Use mode defaults after you have promoted all of your mode settings. When you do so the following Confirm window will display. See .

Click Yes to set the SYSTEM WIDE DEFAULT region or any other region you used for this default promotion effort to use the default settings you just promoted.

If you want to specify unique Outage Modes for each of your Outage Regions select a region and then select Customize region .

Then perform the following steps for each of the outage modes you want to use for the selected region. For example if you are going to use three storm based modes Small Storm Mode Medium Storm Outage Mode and Large Storm Outage Mode and two time based outage modes Day Outage Mode and Night Outage then you need to repeat these steps for each of those outage modes.

When the Nested Outage Processing category is selected the settings for parameters used by the Nested Outage Detection NOD Process are displayed as shown in .

When the OCDB category is selected the settings for parameters used by the Outage Status Notification Adapter from the Cellnet OCDB are displayed as shown in .

When the Outage Scoping and Restoration category is selected the settings for various scoping and restoration parameters used by the External Scoping Requests Processor First Level Scoping FLS Processor the Anticipated Outage Create Delete Processor AOCDP the Cellnet USC Power Status Check PSC Adapter Restoration Verification Application RVA Adapter the Restoration Verification Processor RVP and the Sustained Endpoint Outage Processor SEOP are displayed as shown in .

When the OVE RE Integration category is selected the settings for general enablement parameters are displayed. IS OVE RE ENABLED is used by all OMM processes. IS OMS INTEGRATION ENABLED is used by the Automated Outage Mode Determination AOMD Process the Nested Outage Determination NOD Process the OMS OSN Sender Process the OMS OSN Receipt Process the Restoration Notification Processor from Metering Systems the Restoration Verification Processor RVP the Sustained Endpoint Outage Processor SEOP and the Populate Outage History Process. IS VEE OUTAGE INTEGRATION ENABLED is used by the Populate Outage History Process. See .

When the Power Status Inferencing category is selected the settings for parameters used by the Restoration Notification Processor from Metering Systems and the Sustained Endpoint Outage Processor SEOP are displayed as shown in .

When the Restoration Scout category is selected the settings for parameters used by the Restoration Scout are displayed as shown in .

The embodiments described above are intended only to illustrate and teach one or more ways of practicing or implementing the present invention not to restrict its breadth or scope. The actual scope of the invention which embraces all ways of practicing or implementing the teachings of the invention is defined only by the following claims and their equivalents.

