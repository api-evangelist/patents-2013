---

title: Location information notification method, user equipment, and application service gateway
abstract: The present invention provides a location information notification method, a user equipment, and an application service gateway. The method includes: acquiring, by a user equipment UE, current camping location information through an application programming interface API; performing, by the UE, matching between the current camping location information and a preset location information configuration table; and sending out, by the UE, corresponding prompt information according to a matching result. In addition, a user equipment and an application service gateway are provided.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09319841&OS=09319841&RS=09319841
owner: HUAWEI TECHNOLOGIES CO., LTD.
number: 09319841
owner_city: Shenzhen
owner_country: CN
publication_date: 20131024
---
This application is a continuation of International Application No. PCT CN2011 073245 filed on Apr. 25 2011 which is hereby incorporated by reference in its entirety.

The present invention relates to the communications field and in particular to a location information notification method a user equipment and an application service gateway.

A uBro solution is provided in the prior art to meet a requirement for indoor coverage of network signals. In this solution outdoor coverage is performed by using a macro network and indoor coverage is performed by a femto Femto network thereby achieving the indoor coverage of the network signals.

In the uBro solution if a user equipment UE User Equipment used by a user is located indoors the user equipment may be covered by both the Femto network and the macro network. Because tariffs of using these two networks by the user are different considering the user s right to know an operator needs to notify the user of a type of a currently used network thereof.

In the prior art a location information notification method is mainly implemented by using a mobility management MM Mobility Management information technology or an information technology of general packet radio service GPRS General Packet Radio Service mobility management GMM GPRS Mobility Management . A specific process is roughly as follows 

When the UE enters a coverage area of the Femto network from a coverage area of the macro network or enters a coverage area of the macro network from a coverage area of the Femto network a location area changes and the UE initiates a location update process to a core network. In the location update process the core network delivers MM information or GMM information to the UE. After receiving the MM information or the GMM information the UE reads an identifier of a network on which the UE is currently located therefrom and displays the identifier of the network on a screen of the UE so that the user is capable of learning the type of the currently used network.

To use the MM information or the GMM information the UE needs to have an MM information interface or a GMM information interface. Currently there are various UEs and application layer software that they use greatly differs. In a practical application there is a relatively serious problem in compatibility of the MM information or the GMM information between different UEs.

Inventors of the present invention have performed a compatibility test on mobile phones of each mainstream mobile phone vendor on a current market. The test relates to 29 mobile phones of eight vendors. It can be seen from the test that 31.04 of the mobile phones do not support the MM information or the GMM information at all. In repeated test processes 6.9 of the mobile phones display the information with probabilities and 24.13 of the mobile phones have other problems such as a display delay.

Therefore in the prior art the solution in which location information notification is implemented by using the MM information or the GMM information has a poor reliability and cannot accurately and effectively notify the user of location information.

Embodiments of the present invention provide a location information notification method a user equipment and an application service gateway that are capable of accurately and effectively notifying a user of location information.

A location information notification method according to an embodiment of the present invention includes acquiring by a user equipment UE current camping location information of the UE through an application programming interface API performing by the UE matching between the current camping location information and a preset location information configuration table and sending out by the UE corresponding prompt information according to a matching result.

A location information notification method according to an embodiment of the present invention includes receiving by an application service gateway ASG a configuration table acquiring request sent by a user equipment UE and feeding back by the ASG a location information configuration table to the UE where the location information configuration table is used to indicate a camping location information range of a femto Femto network.

A user equipment according to an embodiment of the present invention includes a location information acquiring unit configured to acquire current camping location information of the user equipment UE through an application programming interface API a matching unit configured to perform matching between the current camping location information acquired by the location information acquiring unit and a preset location information configuration table and a prompting unit configured to send out corresponding prompt information according to a matching result obtained by the matching unit.

An application service gateway according to an embodiment of the present invention includes a receiving unit configured to receive a configuration table acquiring request sent by a user equipment UE and a responding unit configured to feed back a location information configuration table to the UE where the location information configuration table is used to indicate a camping location information range of a femto Femto network.

As can be seen from the preceding technical solutions the embodiments of the present invention have the following advantages 

In the embodiments of the present invention a UE may acquire current camping location information of the UE through an application programming interface API Application Program Interface and then the UE may determine according to a matching relationship between the camping location information and a preset location information configuration table a network on which it is located and send out corresponding prompt information. Almost all UEs having an operating system include an API and currently usage specifications and related standard protocols of the API are relatively mature. Therefore a process of acquiring the camping location information through the API interface is relatively reliable and various UEs are capable of accurately and effectively notifying a user of location information.

Embodiments of the present invention provide a location information notification method a user equipment and an application service gateway that are capable of accurately and effectively notifying a user of location information.

Referring to a location information notification method according to an embodiment of the present invention includes 

In this embodiment when the UE needs to prompt a user with a current camping network the UE may acquire the current camping location information of the UE through its own API.

It should be noted that in this embodiment the UE may locally acquire the current camping location information of the UE through the API and may also acquire the current camping location information of the UE from another network side device through the API.

After acquiring the current camping location information of the UE the UE may perform the matching between the camping location information and the preset location information configuration table.

In this embodiment the preset location information configuration table may be used to indicate a camping location information range of a first network and the UE may acquire the preset location information configuration table from an application service gateway ASG Application Service Gateway .

In this embodiment after the matching is completed the UE may send out the corresponding prompt information according to the matching result which may be specifically as follows 

If the matching succeeds the UE sends out first prompt information and if the matching fails the UE sends out second prompt information and

the first prompt information may be used to indicate that the UE currently camps on the first network and the second prompt information may be used to indicate that the UE currently camps on a second network.

In this embodiment a UE may acquire current camping location information of the UE through an API and then the UE may determine according to a matching relationship between the camping location information and a preset location information configuration table a network on which it is located and send out corresponding prompt information. Almost all UEs having an operating system include an API and currently usage specifications and related standard protocols of the API are relatively mature. Therefore a process of acquiring the camping location information through the API interface is relatively reliable and various UEs are capable of accurately and effectively notifying a user of location information.

The foregoing describes an implementation process of a location information notification method according to an embodiment of the present invention from the perspective of a UE. Referring to implementation of the location information notification method according to the embodiment of the present invention from the perspective of the UE the following describes an implementation process of a location information notification method of the present invention from the perspective of an ASG Referring to a location information notification method according to another embodiment of the present invention includes 

In this embodiment the ASG may receive the configuration table acquiring request sent by the UE where the configuration table acquiring request is used to request the ASG to feed back a location information configuration table and the location information configuration table may be used to indicate a camping location information range of a first network.

It should be noted that the UE in this embodiment may establish a communication connection with the ASG through various access devices for example the UE may establish the communication connection with the ASG through a base station or an access point AP Access Point . A specific networking structure is not limited herein.

After receiving the configuration table acquiring request from the UE the ASG may feed back a location information configuration table saved in the ASG to the UE. The first network in this embodiment may be a Femto network and the location information configuration table is used to indicate a camping location information range of the Femto network.

In this embodiment after receiving the configuration table acquiring request from the UE the ASG may feed back the location information configuration table saved in the ASG to the UE and then the UE may determine according to a matching relationship between camping location information of the UE and the location information configuration table a network on which it is located and send out corresponding prompt information.

For ease of understanding the following describes a location information notification method of the present invention from the perspective of an interaction between a UE and an ASG Referring to a location information notification method according to another embodiment of the present invention includes 

In this embodiment after the UE starts up and loads a widget Widget or an application Application for a first time the UE sends the configuration table acquiring request to the ASG so as to request acquiring of a location information configuration table.

After receiving the request of the UE the ASG feeds back a locally configured location information configuration table to the UE.

In this embodiment a location information configuration table is maintained on the ASG where the location information configuration table is used to indicate a location area code LAC Location Area Code range of a Femto network and the location information configuration table may be specifically as shown in table 1 

The meaning indicated in table 1 is as follows The Femto1 network includes areas corresponding to LACs ranging from 0x0110 to 0x01EF the Femto2 network includes areas corresponding to LACs ranging from 0x2555 to 0x28A4 and the Femto3 network includes areas corresponding to LACs ranging from 0x38D1 to 0x3993.

Table 1 is only an example in this embodiment. It can be understood that in a practical application specific content of the location information configuration table is not limited to the preceding data and specific data is not limited herein.

This embodiment is described by using an example in which an LAC is used as camping location information. It can be understood that in a practical application in addition to the LAC another identifier may also be used as the camping location information and this is not specifically limited herein.

It should be noted that one base station can be uniquely determined according to an LAC and a cell identity CELLID . However in a practical application the LAC range of the Femto network is different from an LAC range of a macro network and therefore the Femto network and the macro network can be distinguished simply by using the LAC in this embodiment.

In this embodiment whenever the UE accesses a network the UE may acquire a current LAC of the UE itself from a core network according to a network protocol used by the accessed network and save the acquired LAC locally.

It should be noted that because one base station can be uniquely determined according to the LAC and the CELLID when the UE accesses a network in addition to acquiring the LAC the UE may also acquire the CELLID and may save the acquired LAC and CELLID locally after the acquiring.

When a preset condition is met the UE may locally acquire the current camping location information that is the LAC and the CELLID of the UE through its own API.

It should be noted that meeting a preset condition in this embodiment may indicate that the UE needs to prompt a user with a current camping network or inform the user that a preset moment a preset period or the like is reached. This is not specifically limited herein.

In this embodiment if the UE accesses a network and saves the current LAC and CELLID in an update manner the UE may acquire the locally saved LAC and CELLID directly through the API. If the UE is capable of locally saving multiple LACs and CELLIDs the UE may acquire an LAC and a CELLID that are recently saved locally through the API. A specific manner is not limited herein.

It should be noted that UEs with different operating systems may specifically use different types of APIs when acquiring camping location information from their local memories but the acquiring manners are similar. The following takes the Windows Mobile operating system as an example for description.

Each time when a Windows Mobile terminal accesses a network to transmit data the Windows Mobile terminal may acquire current camping location information of the Windows Mobile terminal such as an LAC and a CELLID from a core network by using a current communications protocol such as the Wireless Application Protocol . The information is processed by a radio interface layer RIL Radio Interface Layer function of the Windows Mobile operating system and saved in a memory of the Windows Mobile terminal.

When the Windows Mobile terminal needs to prompt a user with a current camping network the Windows Mobile terminal may directly invoke an API of the RIL function so as to acquire the previously saved LAC and CELLID or the Windows Mobile terminal may use other software functions to invoke the API of the RIL function so as to acquire the previously saved LAC and CELLID. This is not specifically limited herein.

In addition to locally acquiring the current camping location information of the UE through the API the UE may also acquire the current camping location information of the UE from other network side devices through the API or is capable of acquiring the current camping location information of the UE through the API in another manner. This is not limited herein.

After acquiring the current LAC of the UE the UE may perform matching between the LAC and the acquired location information configuration table. A specific matching process may be as follows 

The UE determines whether the current LAC is in an LAC range of the Femto network in the location information configuration table if yes determines that the matching succeeds and if no determines that the matching fails.

In this embodiment if the current LAC of the UE is 0x01D5 in the matching process the UE detects that the LAC is in the 0x0110 0x01EF range and determines that the matching succeeds.

In this embodiment if the current LAC of the UE is 0x01FF in the matching process the UE detects that the LAC is not in any LAC range of the Femto network in table 1 and determines that the matching fails.

In this embodiment after the matching is completed the UE may send out the corresponding prompt information according to the matching result which may be specifically as follows 

If the current LAC of the UE successfully matches the preset location information configuration table it indicates that the UE currently camps on the Femto network and the UE may send out first prompt information where the first prompt information is used to indicate that the UE currently camps on the Femto network.

Specifically the UE may display the first prompt information at an operator logo on a screen of the UE the first prompt information may pop up in a manner of a system message or the UE may send out the first prompt information in a manner of a play announcement and the like. A specific manner is not limited.

If the current LAC of the UE fails to match the preset location information configuration table it indicates that the UE currently camps on the macro network and the UE may send out second prompt information where the second prompt information is used to indicate that the UE currently camps on the macro network.

Specifically the UE may display the second prompt information at an operator logo on the screen of the UE the second prompt information may pop up in a manner of a system message or the UE may send out the second prompt information in a manner of a play announcement and the like. A specific manner is not limited.

In this embodiment the UE may provide an interface for the user to modify prompt information and the user is capable of modifying specific content of the first prompt information or the second prompt information through this interface so as to meet an individual demand.

For example default content of the first prompt information is Femto network and default content of the second prompt information is macro network . According to a demand of the user the user may modify the content of the first prompt information to indoor network tariff XXXX and modify the content of the second prompt information to outdoor network tariff XXXX .

In this embodiment the UE sends the configuration table acquiring request to the ASG when the UE loads a Widget or an Application for the first time after starting up so as to request acquiring of the location information configuration table. It can be understood that in a practical application the UE is not limited to acquiring the location information configuration table from the ASG at this moment as long as the location information configuration table is acquired before step . A specific moment is not limited herein.

It should be noted that the UE may further acquire the location information configuration table again from the ASG according to an instruction of the user and use the newly acquired location information configuration table to update the originally saved location information configuration table so as to improve precision of the matching process.

In this embodiment a UE may acquire current camping location information of the UE through an API and then the UE may determine according to a matching relationship between the camping location information and a preset location information configuration table a network on which it is located and send out corresponding prompt information. Almost all UEs having an operating system include an API and currently usage specifications and related standard protocols of the API are relatively mature. Therefore a process of acquiring the camping location information through the API interface is relatively reliable and various UEs are capable of accurately and effectively notifying a user of location information.

Secondly the UE may dynamically acquire the current camping location information of the UE and may acquire the location information configuration table again from the ASG according to the user s instruction so as to update the originally saved location information configuration table. In this way the precision of the matching process can be improved and the location information can be more accurately and effectively notified to the user.

Referring to implementation of the preceding method embodiment the following describes a user equipment according to an embodiment of the present invention. Referring to a user equipment according to an embodiment of the present invention includes 

a location information acquiring unit configured to acquire current camping location information of the UE through an API 

a matching unit configured to perform matching between the current camping location information of the UE obtained by the location information acquiring unit and a preset location information configuration table and

a prompting unit configured to send out corresponding prompt information according to a matching result obtained by the matching unit .

a saving unit configured to whenever the UE accesses a network acquire a current location area code LAC of the UE according to a network protocol in use and save the LAC locally.

In this case the location information acquiring unit in this embodiment may locally acquire through the API current camping location information of the UE recently saved by the saving unit .

It should be noted that in addition to locally acquiring the current camping location information of the UE through the API the location information acquiring unit may also acquire the current camping location information of the UE from another network side device through the API or acquire the current camping location information of the UE through the API in another manner. This is not limited herein.

The prompting unit in this embodiment is specifically configured to when the matching succeeds send out first prompt information and when the matching fails send out second prompt information.

The first prompt information is used to indicate that the UE currently camps on a first network and the second prompt information is used to indicate that the UE currently camps on a second network.

a configuration table requesting unit configured to send a configuration table acquiring request to an ASG and

a configuration table receiving unit configured to receive a location information configuration table fed back by the ASG where the location information configuration table is used to indicate an LAC range of the first network.

For ease of description the following describes communication relationships between the units of the user equipment in this embodiment by using a specific application scenario.

In this embodiment when a preset condition is met the location information acquiring unit locally acquires the current LAC and a current CELLID of the UE through the API.

Meeting a preset condition in this embodiment may indicate that the UE needs to prompt a user with a current camping network or inform the user that a preset moment a preset period or the like is reached. This is not specifically limited herein.

After the location information acquiring unit acquires the current LAC and CELLID of the UE the matching unit may perform matching between the LAC and the preset location information configuration table.

In this embodiment the preset location information configuration table may be used to indicate the LAC range of the first network.

In this embodiment the matching unit may specifically determine whether the current LAC is in the LAC range of the Femto network in the location information configuration table shown in table 1 if yes determine that the matching succeeds and if no determine that the matching fails.

After the matching unit completes the matching the prompting unit may send out the corresponding prompt information according to the matching result which may specifically be as follows 

If the matching succeeds the prompting unit sends out the first prompt information and if the matching fails the prompting unit sends out the second prompt information.

The first prompt information is used to indicate that the UE currently camps on the first network and the second prompt information is used to indicate that the UE currently camps on the second network.

In this embodiment the location information acquiring unit may acquire current camping location information of a UE through an API then the matching unit may determine according to a matching relationship between the camping location information and a preset location information configuration table a network on which the UE is located and the prompting unit may send out corresponding prompt information according to a matching result. Almost all UEs having an operating system include an API and currently usage specifications and related standard protocols of the API are relatively mature. Therefore a process of acquiring the camping location information through the API interface is relatively reliable and various UEs are capable of accurately and effectively notifying a user of location information.

Referring to implementation of the preceding method embodiment the following describes a user equipment according to an embodiment of the present invention. Referring to an application service gateway according to an embodiment of the present invention includes 

It should be noted that the UE in this embodiment may establish a communication connection with the ASG through various access devices and a specific networking structure is not limited herein.

In this embodiment a location information configuration table saved by the application service gateway may be as shown in table 1 and is not specifically described herein.

A person of ordinary skill in the art may understand that all or a part of the steps of the methods in the foregoing embodiments may be implemented by a program instructing relevant hardware. The program may be stored in a computer readable storage medium such as a read only memory a magnetic disk or an optical disc.

The above introduces a location information notification method a user equipment and an application service gateway that are provided in the present invention in detail. A person skilled in the art may make modifications to the specific implementation manners and application scopes according to the idea of embodiments of the present invention. Therefore the content of this specification should not be construed as a limitation on the present invention.

