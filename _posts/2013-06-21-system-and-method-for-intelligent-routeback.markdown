---

title: System and method for intelligent routeback
abstract: An intelligent routeback mechanism that may inter alia receive from an entity (such as for example a wireless carrier) aspects of the entity's messaging traffic, data, etc. with the intelligent routeback mechanism aiding the (1) return (optionally augmented, optionally transformed, etc.) to the entity of that portion of the traffic, data, etc. that the entity is able to deliver itself and (2) delivery of that portion of the traffic, data, etc. that the entity is unable to deliver itself. Such an intelligent routeback mechanism may reside in inter alia a Messaging Inter-Carrier Vendor.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09226216&OS=09226216&RS=09226216
owner: Sybase 365, Inc.
number: 09226216
owner_city: Reston
owner_country: US
publication_date: 20130621
---
This application is a continuation of U.S. application Ser. No. 13 231 186 filed on Sep. 13 2011 which claims the benefit of U.S. Provisional Patent Application Ser. No. 61 382 991 filed on 15 Sep. 2010 both of which are incorporated herein by reference in their entireties.

The present invention relates generally to telecommunications services. More particularly the present invention relates to capabilities that enhance substantially the value and usefulness of various communication and data exchange paradigms including inter alia Short Message Service SMS Multimedia Message Service MMS Internet Protocol IP Multimedia Subsystem IMS Wireless Application Protocol WAP the transfer of various forms of data such as inter alia signaling and command and control data data from to software applications such as games etc. Electronic Mail E Mail Instant Messaging IM etc.

As the wireless revolution continues to march forward through various flavors of 2G 3G 4G and beyond the importance to a Mobile Subscriber MS for example a user of a Wireless Device WD that is serviced by possibly inter alia a Wireless Carrier WC of their WD grows substantially. Examples of WDs include possibly inter alia mobile telephones handheld computers Internet enabled phones pagers radios TVs audio devices car audio and other systems recorders text to speech devices bar code scanners net appliances mini browsers personal data assistants PDAs etc.

One consequence of such a growing importance is the resulting ubiquitous nature of WDs i.e. MSs carry them at almost all times and use them for an ever increasing range of activities. For example MSs employ their WDs to possibly inter alia 

1 Exchange e.g. SMS MMS etc. messages content such as inter alia pictures and other static images songs and other quanta of audio data movies streaming video and other quanta of video data data from software applications such as games etc. with other MSs e.g. Let s meet for dinner at 6 etc. through Peer to Peer or P2P messaging.

2 Secure information such as for example weather updates travel alerts news updates sports scores etc. participate in voting initiatives such as for example with the television show American Idol exchange content such as for example pictures and other static images songs and other quanta of audio data movies streaming video and other quanta of video data games and other software applications etc. interact with social networking sites etc. through various of the available Application to Peer or A2P based service offerings.

3 Engage in Mobile Commerce which broadly speaking encompasses the buying and selling of merchant supplied products goods and services through a WD and Mobile Banking which broadly speaking encompasses performing various banking activities through a WD .

As just one usage example around the world during 2009 there were over five trillion SMS messages exchanged and in North America during just the first half of 2010 over one trillion SMS messages were exchanged.

Coincident with the rapid growth of WDs has been the desire of WCs and other entities within a mobile ecosystem to among other things 1 offer to MSs a continuing stream of new and interesting products and services that possibly inter alia attract new MSs and retain existing MSs leverage or exploit the continually increasing features and capabilities of new WDs incrementally increase the volume of traffic and the revenue that is associated with same that flows through a mobile ecosystem and 2 establish and manage their inter WC connections and administer the traffic that traverses same in ways that among other things minimizes various factors including for example cost administrative burdens operational challenges etc. and maximizes various factors including for example utilization etc. .

Attaining the different desires or goals that were referenced above may raise a host of for example and inter alia connectivity communication processing routing performance billing etc. issues which may impact or preclude the attainment of such goals.

As just one example a hypothetical WC ABC will likely establish and maintain bilateral agreements encompassing among other things the particulars governing the exchange of e.g. SMS MMS etc. traffic and data billing constraints etc. with some number of other WCs based on for example and possibly inter alia various criteria such as geographic operating region MS population size etc. . Such agreements are typically expensive e.g. time consuming to establish logistically and technically challenging to implement and to maintain etc. and thus WC ABC will frequently limit based on various constraints such as for example geographic reach etc. the number of agreements that it will pursue.

Such a limitation by WC ABC leaves WC ABC at a disadvantage vis vis the many hundred of other WCs that exist. For example a MS of WC ABC would be unable to interact e.g. exchange SMS MMS etc. messages etc. with the MSs of one or more of the other WCs and a MS of any of the other WCs such as for example WC XYZ would be unable to interact e.g. exchange SMS MMS etc. messages etc. with a MS of WC ABC.

It would be desirable to have a single entity a Messaging Inter Carrier Vendor MICV that inter alia operates as a trusted intermediary that any entity such as for example WCs like WC ABC WC XYZ etc. may connect to and exchange traffic data etc. with where the MICV inter alia 

1 Establishes and maintains all of the various business e.g. bilateral agreements etc. technical e.g. communication protocols security etc. operational e.g. Quality of Service QoS constraints Service Level Agreement SLA requirements routing rules etc. etc. arrangements that yield a fully interconnected ecosystem with the MICV at the center or hub of such an ecosystem and

2 Performs comprehensive authoritative etc. routing and switching operations thus freeing each of the connected entities e.g. WC ABC WC XYZ etc. from among other things needing to individually address all of the business technical operational etc. challenges that naturally arise were each entity to pursue connecting directly with any number of other entities.

Aspects of the present invention fill the lacuna that was noted above by 1 providing within inter alia a MICV an intelligent routeback capability to expeditiously process and route a wide range of information including inter alia SMS MMS IMS etc. messages Session Initiation Protocol SIP addressed artifacts application data WAP based exchanges E Mail messages signaling command and control application etc. data IM messages etc. while 2 addressing in new and innovatory ways various of the not insubstantial challenges that are associated with same.

The intelligent routeback mechanism may inter alia support an entity such as for example a WC sending for example all of their out of network e.g. SMS MMS etc. traffic data etc. to a MICV with the intelligent routeback mechanism aiding the 

1 Return optionally augmented with various indicators and or other data elements optionally with various data elements transformed or manipulated etc. to the entity of that portion of the traffic data etc. that was received from the entity that the entity is able to deliver itself e.g. where the entity has in place a bilateral agreement with a particular destination entity for subsequent delivery by the entity and

2 Delivery by the MICV of that portion of the traffic data etc. that was received from the entity that the entity is unable to deliver itself e.g. where the entity has no bilateral agreement with a particular destination entity .

Through such a capability an entity such as a WC immediately gains the benefit of a MICV s extended network of entities e.g. other WCs without inter alia any of the associated business operational etc. costs and challenges and among other things the enhanced revenue that comes along with such an extended network.

One embodiment of the present invention offers a server based method for directing a quanta of data involving at least 1 receiving a quanta of data from a sending entity the quanta of data comprising a destination address and content 2 identifying from the content a type indicator 3 using at least routing data and aspects of the destination address to identify a receiving entity 4 based on at least a a set of rules comprising delivery routes available to the sending entity b the receiving entity and c the type indicator either a returning aspects of the quanta of data to the sending entity or b delivering aspects of the quanta of data towards the receiving entity.

Another embodiment of the present invention offers a processor based system for directing a quanta of data including at least 1 a first gateway configured to receive a quanta of data from a sending entity the quanta of data comprising a destination address and content 2 workflow modules configured to a identify from the content a type indicator b identify using at least routing data and aspects of the destination address a receiving entity c based on at least i a set of rules comprising delivery routes available to the sending entity ii the receiving entity and iii the type indicator either i return via a second gateway aspects of the quanta of data to the sending entity or ii deliver via a third gateway aspects of the quanta of data towards the receiving entity 3 a repository configured to preserve aspects of the results of the different processing steps and 4 an administrator.

These and other features of the embodiments of the present invention along with their attendant advantages will be more fully appreciated upon a reading of the following detailed description in conjunction with the associated drawings.

The present invention will now be described with reference to the accompanying drawings. In the drawings generally like reference numbers indicate identical or functionally similar elements. Additionally generally the left most digit s of a reference number identifies the drawing in which the reference number first appears.

In the discussion below aspects of the present invention are described and illustrated as residing within a centrally located full featured MICV facility. Reference is made to U.S. Pat. No. 7 154 901 entitled INTERMEDIARY NETWORK SYSTEM AND METHOD FOR FACILITATING MESSAGE EXCHANGE BETWEEN WIRELESS NETWORKS and its associated continuations for a discussion of the concept of a MICV a summary of various of the services functions etc. that may be performed by a MICV and a discussion of the numerous advantages that may arise from same.

In the discussion below aspects of the present invention are described and illustrated as being offered by a Service Provider SP . A SP may for example be realized through any combination of possibly inter alia any one or more of 1 an element of a WC an element of a landline carrier an element of a MICV or multiple such elements working together 2 a Third Party 3P such as possibly inter alia a merchant a Content Provider CP such as for example a news organization an advertising agency a brand etc. or a financial institution 3 multiple 3P entities working together 4 a 3P service bureau etc.

As illustrated in and reference numeral under one particular arrangement a MICV may be disposed between possibly inter alia multiple WCs WC WC WC and multiple SPs SP SP and thus bridges all of the connected entities. A MICV thus as one simple example may offer various routing formatting delivery value add etc. capabilities that provide possibly inter alia 

1 A WC and by extension all of the MSs that are serviced by the WC with ubiquitous access to a broad universe of SPs and other entities that may be connected to the MICV and

2 A SP and other entities that may be connected to the MICV with ubiquitous access to a broad universe of WCs and by extension to all of the MSs that are serviced by the WCs .

Generally speaking a MICV may have varying degrees of visibility e.g. access etc. to the MS MS MS SP etc. messaging traffic 

1 A WC may elect to route just their out of network messaging signaling data etc. traffic to a MICV. Under this approach the MICV would have visibility e.g. access etc. to just the portion of the WC s traffic that was directed to the MICV by the WC.

2 A WC may elect to route all of their messaging signaling data etc. traffic to a MICV. The MICV may possibly among other things subsequently return to the WC that portion of the traffic that belongs to i.e. that is destined for a MS of the WC. Under this approach the MICV would have visibility e.g. access etc. to all of the WC s traffic.

For purposes of illustration and reference numeral depict a possible logical implementation of aspects of a MICV under one particular arrangement. The figures depict among other things Gateways and that for example provide information data receipt and dispatch capabilities across possibly inter alia different application level communication protocols Queues and that for example provide interim storage and buffering capabilities a Message or Data Highway DH that for example provides interconnection capabilities and DPEs .

A dynamically updateable set of one or more Receivers Rx Rx in the diagram get messages from a MICV DH and deposit them on an intermediate or temporary Queue Q Q in the diagram for subsequent processing.

A dynamically updateable set of one or more Queues Q Q and Q Q in the diagram operate as intermediate or temporary buffers for incoming and outgoing messages.

A dynamically updateable set of one or more WorkFlows WorkFlow WorkFlow in the diagram remove incoming messages from an intermediate or temporary Queue Q Q in the diagram perform all of the required operations on the messages and deposit the processed messages on an intermediate or temporary Queue Q Q in the diagram . The WorkFlow component will be described more fully below.

A dynamically updateable set of one or more Transmitters Tx Tx in the diagram remove processed messages from an intermediate or temporary Queue Q Q in the diagram and put the messages on a MICV DH.

An Administrative Engine provides a linkage to all of the different components of a DPE so that a DPE along with all of the different components of a DPE may be fully and completely administered or managed .

While portions of the discussion below will reference a MICV it will be readily apparent to one of ordinary skill in the relevant art that numerous other arrangements are equally possible and indeed are fully within the scope of the present invention.

Aspects of a MICV may plug into different layers levels of legacy current and or future technology and among other things may for example facilitate interoperation between such technologies.

For example from a traditional messaging context an entity such as for example a WC a 3P such as a CP etc. may direct their Short Message Service Center SMSC complexes their Multimedia Message Service Center MMSC complexes etc. to connect to a single simple consolidated etc. interface mechanism that is exposed by a MICV and subsequently seamlessly exchange message traffic.

For example from a traditional wireless context an entity such as a WC etc. may direct aspects of their infrastructure to connect to a single simple consolidated etc. interface mechanism that is exposed by a MICV and subsequently seamlessly exchange SS7 based and or IP based signaling data General Packet Radio Service GPRS Roaming Exchange GRX data location and presence data etc.

a Services Plane . For example one or more Application Server AS instances Billing facilities Reporting facilities etc.

b Control Plane . For example a Home Subscriber Server HSS capability a Call Session Control Function CSCF capability one or more Media Gateway MG instances etc.

c Network or Transport Plane . Support interfaces etc. for possibly inter alia Voice over IP VoIP WiFi Public Land Mobile Network PLMN Public Switched Telephone Network PSTN etc.

2 and reference numeral depict how the different functional elements of an entity e.g. carriers such as C C 3Ps such as CPs and others etc. within an ecosystem may plug into a MICV s single access connection point e.g. elements of carrier Ca s Control Plane and Network or Transport Plane may plugin to a MICV s single access connection point elements of carrier Cb s Services Plane may plug into a MICV s single access connection point . Similar access points may be realized at .

3 and reference numeral illustrate how the single access connection point serves much like a fa ade behind which connected entities e.g. carriers such as C C 3Ps such as CPs and others etc. may access one or more of the virtual implementations of a MICV s logical planes .

Thus for example as a carrier s environment grows and changes as a carrier s business needs and models change and evolve as a carrier deploys new service offerings etc. it can possibly among other things plug into and thus take advantage of the features and functions that are offered by different combinations of the virtual implementations of a MICV s logical planes all through the single access communication point.

Additionally placing the virtual planes behind a single fa ade allows for possibly among other things ongoing and dynamic changes updates etc. to the physical implementation of a plane without any impact on or interruptions to any of the connected entities.

4 and reference numeral depict one particular IMS centric arrangement that is possible through aspects of the present invention Networks A B and C represent hypothetical IMS enabled or IMS capable carriers Network D represents a hypothetical non IMS enabled carrier that offers possibly inter alia MMS services and Network E represents a hypothetical fixed e.g. landline carrier that offers possibly inter alia Digital Subscriber Line DSL services. A MICV may among other things tie together the different disparate natively incompatible etc. environments. The depicted arrangement is illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other arrangements are easily possible and indeed are fully within the scope of the present invention.

Central to the operation of a MICV is the unit of information within a MICV that is received manipulated or otherwise operated on dispatched etc. Unlike prior environments that might operate just on and thus potentially be limited just to an SMS message or a MMS message the unit of information within a MICV is a more general quanta of data. Accordingly a MICV is natively capable of operating on inter alia an SMS message a MMS message an IMS message an E Mail message a VoIP data stream a video data stream e.g. a movie a video conference call etc. a voice telephone call signaling and other command and control data an audio data stream e.g. a song etc. IM data games and other software applications pictures and other static images data from software applications such as games etc.

Within a MICV a flexible extensible and dynamically configurable IMO see for example and reference numeral and reference numeral and may be employed as an internal representation of a received quanta of data. An IMO and may logically contain possibly inter alia one or more headers and a body and etc. within which for example aspects of a received quanta of data may be preserved and . An IMO may physically be realized through any combination of possibly inter alia proprietary data structures Java Message Service JMS messages or objects flat files database entries in memory constructs etc.

For purposes of illustration within an SMS context a MICV may support the receipt and dispatch of information through possibly inter alia Short Message Peer to Peer SMPP via Transmission Control Protocol TCP IP and Mobile Application Part MAP via SS7. Under such a context 

1 and reference numeral depict an exemplary incoming SMS message received via for example SMPP with for example the data elements associated with the SMS message encapsulated within a SMPP Protocol Data Unit PDU encapsulated within a TCP Segment encapsulated within an IP Packet .

2 and reference numeral depict an exemplary incoming SMS message received via for example MAP with for example the data elements associated with the SMS message encapsulated within a Message Signal Unit MSU 

3 and reference numeral depict a hypothetical IMO that is possible in support of an SMS message received via for example SMPP and

4 and reference numeral depict a hypothetical IMO that is possible in support of an SMS message received via for example MAP.

It will be readily apparent to one of ordinary skill in the art that numerous alternative arrangements in connection with for example different contexts such as inter alia MMS VoIP a voice call signaling data command and control data software application data etc. and different communication protocols are easily possible.

A MICV includes among other elements a vertically and horizontally scalable Protocol Engine PE layer see for example reference point in through which information may be received and or transmitted using any combination of one or more of the supported communication protocols including inter alia SS7 TCP IP User Datagram Protocol UDP IP Really Simple Syndication RSS SMPP Simple Mail Transfer Protocol SMTP HyperText Transfer Protocol HTTP Extensible Messaging and Presence Protocol XMPP MM4 MM7 SIP GRX etc.

A PE layer may house a dynamically updateable set of one or more PEs PE PE in the . A PE may for example leverage a body of flexible extensible and dynamically updateable configuration information as it completes its tasks including possibly inter alia 

A Receiving incoming and sending outgoing traffic using any combination of the supported communication protocols paradigms etc.

B Performing various extraction validation editing formatting conversion etc. operations on the elements of an incoming and or outgoing data stream e.g. source address destination address encoding indicators or flags payload or body etc. The specific elements that were just described are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other elements are easily possible and indeed are fully within the scope of the present invention.

C Encapsulating various elements of an incoming data stream within an IMO and or un encapsulating various elements of an outgoing data stream from an IMO.

The catalog of PE processing steps that was described above is illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other processing steps are easily possible and indeed are fully within the scope of the present invention.

A PE layer may be quickly and easily scaled either vertically to for example add additional capacity in response to increases in demand e.g. message volume horizontally to for example add support for a new application level communication protocol or both.

A MICV includes among other elements a flexible extensible and dynamically configurable WorkFlow based PRS layer see reference numeral in . The WorkFlow elements of the PRS layer may be glued together by a Message Routing Language MRL a full featured scripting language that is based in part on the disclosures found in U.S. Pat. No. 6 735 586 entitled System and Method for Dynamic Content Retrieval and U.S. Pat. No. 7 240 067 entitled System and Methodology for Extraction and Aggregation of Data from Dynamic Content and may support among other things 

1 Processing. For example the automatic and dynamic determination of the type of content e.g. an SMS message a VoIP data stream a voice telephone call signaling data etc. in a received quanta of data and the preservation of same in for example an IMO content transcoding operations billing activities including possibly pricing rating events data logging and collection in support of reporting the generation of a Feature Tag etc.

2 Routing. For example the authoritative resolution of destination and or source addresses the examination of available routes and the application of various criteria possibly including for example MS WD location information least cost routing rules MS profile and preference information route loadings attributes of a received quanta of data e.g. data type size etc. QoS constraints billing and revenue constraints etc. to available routes to arrive at a specific route selection etc.

3 Switching. For example directing switching based on a selected route data to an appropriate outbound delivery channel see for example reference number in .

The catalog of activities that was described above is illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other activities are easily possible and indeed are fully within the scope of the present invention.

For purposes of illustration and reference numeral depict aspects of a WorkFlow environment wherein possibly inter alia 

1 A dynamically adjustable number of threads Thread Thread Thread . . . Thread may be inter alia created started allowed to operate or execute quiesced stopped destroyed etc. under control of for example the WorkFlow environment . Among other things one or more threads may for example realize aspects of one or more elements of a MICV such as for example portions of a PE layer portions of a PRS layer etc. and or a single thread may for example realize aspects of one or more elements of a MICV such as for example portions of a PE layer portions of a PRS layer etc. .

2 Different elements of a MICV such as for example portions of a PE layer portions of a PRS layer etc. may communicate interact etc. with various of the threads Thread Thread see for example and .

3 Various of the threads Thread Thread may among themselves communicate interact etc. see for example .

4 Various of the threads Thread Thread may communicate interact etc. with inter alia a Shared Memory Region see for example .

The billing activities within the PRS layer may among other things yield a billing transaction. A billing transaction may take any number of forms and may involve different external entities e.g. a carrier billing system a carrier billing system service bureau a credit or debit card clearinghouse a financial institution etc. . A billing transaction may include possibly inter alia 

The Routing portion of a PRS layer may leverage a comprehensive flexible scalable etc. lookup facility indicated albeit at a very high level as Routing Data in to support possibly inter alia its routing operations. Such a lookup facility may provide authoritative answers to inquiries like At this moment in time what carrier services the Telephone Number TN 1 703 555 1212 What entity services the SIP address sip john.doe bigcompany.com etc. Among other things such a lookup facility may address 1 the complexities that are associated with all of the different TN numbering plans schemes etc. that exist around the world 2 the complexities that arise with worldwide Mobile Number Portability MNP regimes etc. A more detailed depiction of such a lookup facility is presented in and reference numeral . Such a lookup facility may consist of possibly inter alia 

A An Electronic Numbering ENUM fa ade through which possibly inter alia various PRSEs E E in may connect submit routing inquiries receive routing responses etc.

B A dynamically updateable set of one or more In Memory Databases In Memory Database In Memory Database in the diagram that optionally house or host selected data including possibly inter alia data from a Composite Routing Database CRD to provide as one example optimal performance.

C A Real Time Query Facility RTQF through which inquiries may be dispatched real time to authoritative bodies such as for example TN assignment administrators around the world. A RTQF may support multiple communication channels paradigms protocols etc. such as possibly inter alia SS7 TCP IP UDP IP SMPP etc. .

D A CRD containing comprehensive routing information for possibly inter alia TNs within all of the different TN numbering plans schemes etc. that exist around the world. A CRD may receive updates e.g. dynamically on a scheduled basis etc. from any number of sources or feeds including possibly inter alia domestic such as for example from a Local Exchange Routing Guide LERG from one or more Number Portability Administration Centers NPACs etc. and international such as for example from Hong Kong from the United Kingdom etc. .

A lookup facility as described above may support a wide range of address types including among others a TN such as 703 555 1234 a Short Code SC such as 46625 a SIP Uniform Resource Identifier URI such as sip mark mydomain.com a Tel URI such as tel 19257652333 a Uniform Resource Locator URL etc.

The Routing portion of a PRS layer may include a flexible extensible and dynamically configurable intelligent routeback mechanism. Such a mechanism may inter alia support an entity such as for example a WC sending for example all of their out of network e.g. SMS MMS etc. traffic data etc. to a MICV with the intelligent routeback mechanism aiding in the 

1 Return optionally augmented with various indicators and or other data elements optionally with various data elements transformed or manipulated etc. to the entity of that portion of the traffic data etc. that was received from the entity that the entity is able to deliver itself e.g. where the entity has in place a bilateral agreement with a particular destination entity for subsequent delivery by the entity.

2 Delivery by the MICV of that portion of the traffic data etc. that was received from the entity that the entity is unable to deliver itself e.g. where the entity has no bilateral agreement with a particular destination entity .

An intelligent routeback mechanism may leverage inter alia aspects of a lookup facility as described above.

By way of hypothetical example involving an SMS message sent from one MS whose WD has the TN 703 555 1234 and is serviced by WC ABC to another MS whose WD has the TN 301 555 9876 and is serviced by WC XYZ an intelligent routeback mechanism may encompass inter alia the following activities 

1 Extracting one or more destination addresses from a received quanta of data. In the instant example the destination address i.e. TN 301 555 9876 would be extracted from the received SMS message.

2 Authoritatively identifying the entity e.g. the WC that services supports etc. each destination address. In the instant example WC XYZ would be identified as servicing the destination address i.e. TN 301 555 9876. This activity may involve inter alia one or more internal and or external repository lookup operations such as for example against a CRD one or more queries through for example a RTQF against for example one or more WC HLRs a combination of internal and or external repository lookup operations and queries etc.

For example in connection with the processing of an SMS message a MICV may during this activity inter alia leverage a RTQF to a dispatch a SendRoutingInformation SRI preparatory message to for example a WC s HLR and receive back a SRI Response message containing possibly among other things an International Mobile Subscriber Identity IMSI value and b dispatch a ForwardShortMessage FSM message containing inter alia the returned IMSI value to actually transfer exchange etc. the SMS message and receive back a FSM Response message. The SRI message sequence and the FSM message sequence may take any number of forms including inter alia an American National Standards Institute ANSI LocationRequest etc. as defined in the Telecommunications Industry Association TIA Electronic Industries Alliance EIA 41 D specification or an International Telecommunication Union ITU MAP SEND ROUTING INFO etc. as defined in the Q.771 Q.775 specifications .

3 Consulting a flexible extensible and dynamically configurable set of rules to determine inter alia whether to 

A Route a received quanta of data back to the entity from which it was received optionally augmented with various indicators and or other data elements optionally with various data elements transformed or manipulated etc. for possibly inter alia delivery by that entity to an appropriate destination.

B Deliver a received quanta of data optionally augmented with various indicators and or other data elements optionally with various data elements transformed or manipulated etc. to an appropriate destination.

The set of rules may take any number of forms and may among other things range from simple associations such as for example 

In the instant example the above simple association would result in possibly among other things delivery by the MICV of the SMS message optionally augmented with various indicators and or other data elements optionally with various data elements transformed or manipulated etc. to WC XYZ.

The set of rules may be physically realized as any combination of one or more of inter alia flat files such as for example text files Comma Separated Values CSV files etc. databases specialized data structures etc. with any one or more of same residing inside of and or outside of computer memory.

The set of rules may optionally include a range of other information logic parameters etc. including inter alia 

1 Informational error status etc. codes. For example logic rules data etc. associated with the format structure content etc. of one or more informational error status etc. code values that may be generated modified etc. and which may optionally augment a received quanta of data. For example 

A When routing a received quanta of data back to the entity from which it was received a MICV may include one or more error or other informational codes that may among other things be customizable based on inter alia various of the needs of the entity various of the needs of the MICV or a combination of same.

B When delivering a received quanta of data a MICV may include one or more error or other informational codes that may among other things be customizable based on inter alia various of the needs of the destination entity various of the needs of the MICV or a combination of same.

Such codes may take any number of forms including simple numeric alphanumeric textual etc. values composite values etc. For example a hypothetical composite value might comprise four separate elements Protocol User Error Provider Error Delivery Failure Cause and Network Result and be organized in any number of ways such as 50 0 0 0 50 0 0 0 50000000 etc.

2 Data Transformations. For example any portion of e.g. any data element in a received quanta of data may be manipulated transformed mapped replaced altered etc. Illustrative portion data element examples include inter alia an IMSI value a Mobile Subscriber Integrated Services Digital Network Number MSISDN value a Mobile Switching Center MSC value etc.

As just one simple example consider an IMSI value. Among other things a real IMSI value may be received by a MICV in for example a SRI Response message and following various processing steps may subsequently be included in for example other e.g. FSM etc. messages that are dispatched by the MICV. Alternatively an artificial IMSI value comprising inter alia static dynamic etc. values for each of a Mobile Country Code MCC a Mobile Network Code MNC and a Mobile Subscriber Identity Number MSIN with for example any or all of the values selected from based on derived from etc. internal MICV equipment numbers lookup tables counters index values pointers offsets etc. may be dynamically generated by a MICV and following various processing steps may subsequently be included in for example other e.g. FSM messages that are dispatched by a MICV.

3 Delivery channel. For example one or more delivery channels may be identified by inter alia type such as for example SS7 IP etc. by sub type e.g. MAP SMPP EMI UCP etc. by absolute or relative address by link port etc. by alias etc.

The set of rules may be dynamically administered 1 through any number of channels including inter alia WWW based interfaces APIs etc. and 2 by any combination of inter alia MICV representative s external entity e.g. WC representative s etc.

For purposes of illustration and reference numeral capture various of the interactions or exchanges that might take place during the processing of an SMS message sent from MS A whose WD has the TN 703 555 1234 and is serviced by WC ABC Source Operator in the diagram to MS B whose WD has the TN 301 555 4567 and is serviced by WC PQR Destination Operator in the diagram . Of interest and note in are 

1 A repository that may a be physically realized as any combination of one or more of inter alia flat files such as for example text files CSV files etc. databases specialized data structures etc. b contain inter alia a flexible extensible and dynamically configurable set of route deliver rules such as those described above static and or dynamic data etc. and c be populated administered etc. through any combination of one or more means including inter alia manual automatic programmatic etc. via any combination of one or more channels including inter alia WWW based interfaces APIs etc.

3 After completing various processing activities including possibly among other things extracting a destination address the TN 301 555 4567 from the MAP Send Routing Info For SM preparatory message and authoritatively identifying the WC WC PQR that services the destination address the MICV dispatches a MAP Send Routing Info For SM preparatory message see to the destination WC WC PQR and receives back a MAP Send Routing Info For SM Response message see containing possibly among other things an IMSI value for the destination WD the WD that has the TN 301 555 4567 and an address of the MSC that currently services the destination WD.

4 After consulting a set of rules including inter alia the MICV returns to the source WC WC ABC a MAP Send Routing Info For SM Response message containing possibly among other things 

A A custom error code the IMSI value and the address of the MSC that currently services the destination WD see for the route back case where WC ABC will subsequently deliver the SMS message or

B An OK error code the IMSI value and the address of a physical virtual etc. node network element etc. within the MICV for the deliver case where the MISC will deliver the SMS message .

While depicts an ITU oriented set of exchanges or interactions it will be readily apparent to one of ordinary skill in the relevant art that other types styles protocol etc. of exchanges or interactions including inter alia an ANSI oriented set an IP oriented set etc. are easily possible. For example and reference numeral depict various of the interactions or exchanges that might take place during the processing of an SMS message where aspects of the environment are IP based.

The hypothetical examples that were presented above focused on an SMS message. It will be readily apparent to one of ordinary skill in the relevant art that numerous other paradigms are easily possible including inter alia MMS messages IMS messages SIP addressed artifacts application data WAP based exchanges E Mail messages signaling command and control application etc. data IM messages etc.

For purposes of illustration the flowchart that is presented in and reference numeral depicts various of the activities that may take place under a hypothetical PRS layer that is possible through aspects of the present invention with for example steps and steps capturing aspects of the various activities that may be carried out by an intelligent routeback mechanism .

The Databases that are depicted in are a logical representation of the possibly multiple physical repositories that may be implemented to support inter alia configuration routing profile monitoring logging reporting etc. information. The physical repositories may be implemented through any combination of conventional Relational Database Management Systems RDBMSs through Object Database Management Systems ODBMSs through in memory Database Management Systems DBMSs or through any other equivalent facilities.

The Administrator that is depicted in provides management or administrative control over all of the different components of an environment through as one example a World Wide Web WWW based interface. It will be readily apparent to one of ordinary skill in the relevant art that numerous other interfaces e.g. a data feed an Application Programming Interface API etc. are easily possible.

A MICV may maintain one or more repositories e.g. and in into which selected details of all administrative analytical processing routing etc. activities Transaction Detail Records TDRs the results of Extraction Transformation Load ETL operations etc. may be recorded. Among other things such repositories may be used to support 

1 Scheduled e.g. daily weekly etc. and or on demand reporting with report results delivered through SMS MMS etc. messages through E Mail through a WWW based facility etc.

2 Scheduled and or on demand data mining initiatives possibly leveraging or otherwise incorporating one or more external data sources with the results of same presented through Geographic Information Systems GISs visualization etc. facilities and delivered through SMS MMS etc. messages through E Mail through a WWW based facility etc.

Various aspects of the present invention can be implemented by software firmware hardware or any combination thereof. illustrates an example computer system in which the present invention or portions thereof such as described above under paragraphs 47 155 can be implemented as computer readable code. Various embodiments of the invention are described in terms of this example computer system . After reading this description it will become apparent to a person skilled in the relevant art how to implement the invention using other computer systems and or computer architectures.

Computer system includes one or more processors such as processor . Processor can be a special purpose processor or a general purpose processor. Processor is connected to a communication infrastructure for example a bus or a network .

Computer system also includes a main memory preferably Random Access Memory RAM containing possibly inter alia computer software and or data .

Computer system may also include a secondary memory . Secondary memory may include for example a hard disk drive a removable storage drive a memory stick etc. A removable storage drive may comprise a floppy disk drive a magnetic tape drive an optical disk drive a flash memory or the like. A removable storage drive reads from and or writes to a removable storage unit in a well known manner. A removable storage unit may comprise a floppy disk magnetic tape optical disk etc. which is read by and written to by removable storage drive . As will be appreciated by persons skilled in the relevant art s removable storage unit includes a computer usable storage medium having stored therein possibly inter alia computer software and or data .

In alternative implementations secondary memory may include other similar means for allowing computer programs or other instructions to be loaded into computer system . Such means may include for example a removable storage unit and an interface . Examples of such means may include a program cartridge and cartridge interface such as that found in video game devices a removable memory chip such as an Erasable Programmable Read Only Memory EPROM or Programmable Read Only Memory PROM and associated socket and other removable storage units and interfaces which allow software and data to be transferred from the removable storage unit to computer system .

Computer system may also include an input interface and a range of input devices such as possibly inter alia a keyboard a mouse etc.

Computer system may also include an output interface and a range of output devices such as possibly inter alia a display one or more speakers etc.

Computer system may also include a communications interface . Communications interface allows software and or data to be transferred between computer system and external devices. Communications interface may include a modem a network interface such as an Ethernet card a communications port a Personal Computer Memory Card International Association PCMCIA slot and card or the like. Software and or data transferred via communications interface are in the form of signals which may be electronic electromagnetic optical or other signals capable of being received by communications interface . These signals are provided to communications interface via a communications path . Communications path carries signals and may be implemented using wire or cable fiber optics a phone line a cellular phone link a Radio Frequency RF link or other communications channels.

As used in this document the terms computer program medium computer usable medium and computer readable medium generally refer to media such as removable storage unit removable storage unit and a hard disk installed in hard disk drive . Signals carried over communications path can also embody the logic described herein. Computer program medium and computer usable medium can also refer to memories such as main memory and secondary memory which can be memory semiconductors e.g. Dynamic Random Access Memory DRAM elements etc. . These computer program products are means for providing software to computer system .

Computer programs also called computer control logic are stored in main memory and or secondary memory . Computer programs may also be received via communications interface . Such computer programs when executed enable computer system to implement the present invention as discussed herein. In particular the computer programs when executed enable processor to implement the processes of aspects of the present invention such as the steps discussed above. Accordingly such computer programs represent controllers of the computer system . Where the invention is implemented using software the software may be stored in a computer program product and loaded into computer system using removable storage drive interface hard drive or communications interface .

The invention is also directed to computer program products comprising software stored on any computer useable medium. Such software when executed in one or more data processing devices causes data processing device s to operate as described herein. Embodiments of the invention employ any computer useable or readable medium known now or in the future. Examples of computer useable mediums include but are not limited to primary storage devices e.g. any type of random access memory secondary storage devices e.g. hard drives floppy disks Compact Disc Read Only Memory CD ROM disks Zip disks tapes magnetic storage devices optical storage devices Microelectromechanical Systems MEMS nanotechnological storage device etc. and communication mediums e.g. wired and wireless communications networks local area networks wide area networks intranets etc. .

In the discussion above mention reference was made on several occasions for purposes of illustration to SMS MMS etc. message traffic. Such references were not intended to be exhaustive or to limit the invention to the specific forms disclosed. It will be readily apparent to one of ordinary skill in the relevant art that numerous other quanta of data including inter alia IMS message an E Mail message a VoIP data stream a video data stream e.g. a movie a video conference call etc. a voice telephone call signaling and other command and control data an audio data stream e.g. a song etc. IM data games and other software applications pictures and other static images data from software applications such as games etc. are easily possible and indeed are fully within the scope of the present invention.

It is important to note that the hypothetical examples that were presented above which were described in the narrative and which were illustrated in the accompanying figures are exemplary only. They are not intended to be exhaustive or to limit the invention to the specific forms disclosed. It will be readily apparent to one of ordinary skill in the relevant art that numerous alternatives to the presented examples are easily possible and indeed are fully within the scope of the present invention.

