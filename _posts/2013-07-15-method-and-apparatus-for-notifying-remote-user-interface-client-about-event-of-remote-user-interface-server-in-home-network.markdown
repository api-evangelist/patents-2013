---

title: Method and apparatus for notifying remote user interface client about event of remote user interface server in home network
abstract: An event notifying method includes determining whether a current home network, which is currently connected to a remote user interface server (RUIS) in a home network, is a user's home network selected by a user so as to be allowed to be notified of the event, selectively providing an event page to a remote user interface client (RUIC) selected by a user in the user's home network, and performing user authentication prior to providing the event page, thereby ensuring security of the user's private information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09088458&OS=09088458&RS=09088458
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09088458
owner_city: Suwon-si
owner_country: KR
publication_date: 20130715
---
This application is a Continuation Application of U.S. application Ser. No. 12 535 982 filed Aug. 5 2009 which claims the benefit of U.S. Provisional Patent Application No. 61 086 245 filed on Aug. 5 2008 in the U.S. Patent and Trademark Office and the benefit of Korean Patent Application No. 10 2008 0124746 filed on Dec. 9 2008 in the Korean Intellectual Property Office the disclosures of which are incorporated herein in their entirety by reference.

The present invention relates to a method of notifying a remote user interface client RUIC about an event occurring in a remote user interface server RUIS in a home network.

As various home electronic devices develop enhanced networking functions a home network needs various types of devices. Further users can use various services provided by devices in the home network or services provided by an external service provider of the home network. Thus there is a need to notify all home network devices hereinafter referred to as devices about an event that occurs with respect to a single service.

Since the home network is a user s area a user prefers to be informed of all events that occur with respect to a service used by the user within the home network irrespective of the type of device currently being used by the user. In more detail the user may be notified in real time about an event that occurs with regard to another device in which the user is not interested.

An example of a home network specification adopting such a framework is the Consumer Electronics Association CEA 2014. The CEA 2014 publishes technologies for using a service provided by another device of a home network or a server over the Internet through a remote user interface in a home electronic device such as a digital TV. A more detailed description is disclosed in the CEA 2014 specification and is not repeated here.

In operation 0 the RUIC forms a remote user interface RUI session with a remote user interface server RUIS . That is the RUIC displays a user interface UI page of the RUIS in the format of an extensible hypertext markup language XHTML . A user uses a service of the RUIS through the UI page.

In operation 1 an event occurs in a service of another RUIS and the RUIC is notified about the event. The RUIS in which the event occurs is a 3party that does not form the RUI session with the RUIC.

In operations 3 and 4 the XHTML browser browses an XHTML page including an event from the 3party through an HTTP GET instruction and provides the content of the event to a user. For reference a uniform resource locator URL of the XHTML page including the event is contained in an event notification page that the 3party transmits to the RUIC in operation 1.

As described above since all home network devices in the home network adopting a 3party event notification framework are notified about an event the user can be informed of the occurrence of all events through any home network device.

However the user may not want to display an event of the RUIS on all RUICs. For example when the user is watching TV with his or her family the user may not want to display a short message received by his or her cellular phone that is a RUIS on the TV. In addition when a user is at his or her friend s home the user may not want to display a short message received by the user s cellular phone on a friend s TV.

The present invention provides a method and apparatus of selectively notifying a remote user interface client RUIC about an event by selectively providing an event page to the RUIC in a home network which is performed by a remote user interface server RUIS .

According to an aspect of the present invention there is provided a method of notifying a remote user interface client RUIC about an event occurring in a remote user interface server RUIS in a home network which is performed in the RUIS the method including performing authentication with respect to a remote user interface client RUIC determining whether the RUIC is authorized to display the event based on a result of the authentication and selectively transmitting an event page indicating content of the event based on a result of the determination to the RUIC.

The performing of the authentication may include transmitting an event notification message in which a uniform resource locator URL of an event page is replaced with a URL of an authentication page receiving authentication information input by the user through an HTTP POST command from the authentication page and determining whether the authentication is successful based on the authentication information.

The performing of the authentication may include transmitting an HTTP 401 Login Required message in response to an HTTP GET command with respect to the event page receiving authentication information input by the user from the RUIC through the HTTP GET command of the authentication window and determining whether the authentication is successful using the authentication information.

According to another aspect of the present invention there is provided a computer readable recording medium having recorded thereon a program for causing a computer to execute the method.

According to another aspect of the present invention there is provided an apparatus for notifying a remote user interface client RUIC about an event in a remote user interface server RUIS in a home network the apparatus including an authentication performing unit that performs authentication with respect to a remote user interface client RUIC and determines whether the RUIC is authorized to display the event and an event page providing unit that selectively transmits an event page indicating content of the event based on a result of the determining to the RUIC.

The authentication performing unit may include an event notification unit that transmits an event notification message in which a uniform resource locator URL of an event page is replaced with a URL of an authentication page an authentication information receiving unit that receives authentication information input by a user through an HTTP POST command from the authentication page and a determining unit that determines whether the authentication is successful based on the authentication information.

The authentication performing unit may include an authentication information receiving unit that transmits an HTTP 401 Login Required message in response to an HTTP GET command with respect to the event page and receives authentication information input by a user from the RUIC through the HTTP GET command of an authentication window displayed in response to the transmitting and a determining unit that determines whether the authentication is successful based on the authentication information.

According to another aspect of the present invention there is provided a method of notifying a remote user interface client RUIC an event occurring in a remote user interface server RUIS which is performed by the RUIS the method including determining whether a current home network that is currently connected to the RUIS is a selected home network that is allowed to be notified about the event and selectively transmitting an event page indicating the event to at least one remote user interface client RUIC belonging to the current home network based on a result of the determining.

The determining may include determining whether at least one selected device discovered in the selected home network is discovered in the current home network and determining whether the current home network is the selected home network based on a result of the determining whether at least one selected device discovered in the selected home network is discovered in the current home network.

The transmitting may include transmitting the event page to at least one RUIC that is previously selected by a user s input in one of a unicast and a multicast method.

According to another aspect of the present invention there is provided an apparatus for notifying a remote user interface client RUIC about an event in a remote user interface server RUIS the apparatus including an estimation unit that determines whether a current home network that is currently connected to the RUIS is a selected home network that is allowed to be notified about the event and an event page providing unit that selectively transmits an event page indicating the event to at least one remote user interface client RUIC belonging to the current home network based on a result of the determining.

Hereinafter the present invention will be described in detail by explaining exemplary embodiments of the invention with reference to the attached drawings.

In the present exemplary embodiment a television TV functions as the RUIC and a cellular phone functions as a remote user interface server RUIS . Referring to while a viewer named Mike is watching the TV with his family even if he receives a call on the cellular phone the caller s identification ID is not immediately displayed on the TV.

Instead an authentication page for performing user authentication is displayed on the TV in order to determine whether the caller s ID is to be displayed.

If Mike inputs correct authentication information through the authentication page the caller s ID is displayed on the TV. The authentication information may be a password that may be previously set by Mike in the cellular phone or may be previously defined between the RUIS and the RUIC. However the password set in the cellular phone may be used in order to check the content of an event by using an RUIC.

According to the present exemplary embodiment an event occurring in the RUIS is displayed on the corresponding RUIC only when the user authentication is successful and thus the user s privacy may be ensured.

In operation the RUIS performs user authentication in order to check whether an RUIC is authorized to display the event.

Preferably Authentication information input by a user may be transmitted to the RUIS via a secure channel.

In order for the RUIC to display an authentication page for performing the user authentication instead of an event page on which content of the event is displayed a uniform resource locator URL of the event page included in the event notification message may be replaced with a URL of the authentication page. When the user inputs the authentication information via the authentication page the RUIS receives the authentication information through HTTP POST.

Alternatively HTTP authentication is used. That is while the URL of the event page is used in the event notification message an HTTP 401 Login Required message may be transmitted in response to an HTTP GET instruction of the RUIC. In this case an authentication window is displayed on a screen of the RUIC and the user may input the authentication information via the authentication window. When the user inputs the authentication information via the authentication window the RUIS receives the authentication information through HTTP GET.

In operation the RUIS determines whether the authentication information input by the user is correct.

Whenever an event occurs if a user needs to input authentication information each time the user may feel annoyed or may prefer to omit user authentication in a selected RUIC.

Referring to when the authentication page is displayed on the RUIC if the user puts a check in a check box of save your PW the authentication information is stored in an RUIS a local memory of the RUIC or an external memory. The authentication information may be stored through an application programming interface API of a selected plug in or a CEA 2014 standard Save Restore function may be used.

After the authentication information is stored since the RUIS and the RUIC perform the user authentication by using the stored authentication information if the user inputs the authentication information once the user is not required to input the authentication information when a next event occurs.

In the present exemplary embodiment a storage device for storing the authentication information is not limited to any selected device. Thus the authentication information may be stored in the RUIS the RUIC or another device. The case where the authentication information is stored in the RUIC will be described with reference to . The case where the authentication information is stored in the RUIS will be described with reference to .

In the present exemplary embodiment it is assumed that authentication information input by a user is stored in the RUIC and access to an event page is performed through HTTP authentication.

Referring to mappings between a URL of an RUIS and an authentication key are defined where the URL is extracted from an event notification message and the authentication key is generated using the authentication information input by the user during an initial authentication process with respect to a corresponding event.

Next when the RUIC receives the event notification message the RUIC extracts a URL from the RUIC and then determines whether corresponding authentication information whose mapping is defined with respect to the extracted URI exists in the authentication information table. When the corresponding authentication information exists in the authentication information table the RUIC inserts the corresponding authentication information into an HTTP GET command for accessing the event page. The RUIC receiving the HTTP GET command checks whether the authentication is correct and then provides the event page instead of an authentication window or an authentication page to the RUIC. Thus when an event occurs in the RUIS that displays a page for Internet Protocol IP address 192.10.10.11 5678 the RUIC displays the event page immediately rather than displaying the authentication window or the authentication page.

In a general HTTP authentication communication process when an XHTML browser in an active state repeatedly accesses a selected URL session information such as cookie information may be used. However when the XHTML browser is closed the session information may be deleted. Thus when the XHTML browser accesses the selected URL the user needs to input the authentication information again. However in the RUIC according to the present exemplary embodiment even if the XHTML browser is closed the authentication information used in the initial authentication process with respect to the RUIS may be stored.

In an initial authentication process when a user inputs authentication information an RUIC inserts the authentication information into an HTTP GET command requesting an event page of the RUIS. When the initial authentication is successful the RUIS generates the authentication information table in which mappings between the authentication information and identification ID of a corresponding RUIC are defined and stores the authentication information table in a local memory or an external memory. Various pieces of information such as a universally unique identifier UUID and or a provider s IP address may be used as the ID of the RUIC.

Next when the RUIS receives an HTTP command for accessing the event page the RUIS extracts an ID of the RUIC from the HTTP command and then determines whether corresponding authentication information whose mapping is defined with respect to the extracted ID exists in the authentication information table. When the corresponding authentication information exists in the authentication information table the RUIS omits an authentication process and the RUIS provides the event page to the RUIC. Thus according to the present exemplary embodiment when an event occurs in the RUIS the RUIC displaying UUID 123 45 3456 displays the event page immediately rather than displaying an authentication window or an authentication page.

In operation the RUIS performs environment settings so that only a selected RUIC is notified about an event in a selected home network hereinafter referred to as a user home network according to user s input. For example at least one RUIC is selected as a standard RUIC from among RUICs belonging to the user home network and an ID e.g. an IP address of the selected RUIC is stored as illustrated in .

Referring again to in operation when an event occurs it is checked whether a home network hereinafter referred to as the current home network that is currently connected to the RUIS is the user home network. Also in operation by checking whether a RUIC selected as a standard RUIC is discovered it may be checked whether the current home network is the user home network.

In operation it is determined whether an event notification message is allowed to be transmitted in the current home network. When the current home network is the user home network the event notification message is allowed to be transmitted. On the other hand when the current home network is not the user home network the event notification message is not allowed to be transmitted.

In operation when the current home network is the user home network the RUIS transmits the event notification message only to the selected RUIC that is to be notified about an event. When a plurality of RUICs are selected the event notification message is transmitted using a multicast method. When a single RUIC is selected the event notification message is transmitted using a unicast method.

According to the present exemplary embodiment a user may prevent an RUIS from notifying an RUIC about an event occurring in the RUIS in a home network that is not a user s own home network. In addition only a selected RUIC may notify n RUIC about an event in the user s own home network.

Alternatively only a selected RUIC may generate an event page by using a general universal plug and play UPnP technology without a user selecting n RUIC that is to be notified about an event. Such a method will be described with reference to .

In the present exemplary embodiment the RUIS notifies only the selected RUIC about an event by using a general UPnP Event transmitting method. In the general UPnP event transmitting method when an event occurs a UPnP event notification message for notifying the RUIC about the event is transmitted only to a device subscribing to the UPnP event. According to the present exemplary embodiment the UPnP event notification message including a URL for reproducing a related user interface UI is transmitted to the device which has subscribed to UPnP event and when the device receives an event the device may provide event information by reproducing the UI or the transmitted URL.

In operation the RUIS receives a request message to subscribe to the UPnP event with respect to a selected service from the remote UI control point. For example a user subscribes to a short message service of a cellular phone in which the RUIS is embedded through a TV in which the RUIC is embedded.

In operation when a corresponding event occurs in the RUIC a UPnP event notification message is transmitted to the RUIC that is a UPnP control point subscribing to the UPnP event. In this case the UPnP message includes a URL of an event page. The RUIC receiving the UPnP event notification message may reproduce the event page. Thus only the RUIC subscribing to the UPnP event may generate the event page.

Referring to the RUIS device includes a setting unit a memory an estimation unit an authentication performing unit and an event page providing unit .

The setting unit performs environmental settings so that only a selected RUIC is notified of an event in a selected home network according to user s input. Thus an ID of a standard RUIC and IDs of RUICs that are to be notified about an event are stored in the memory .

The authentication performing unit performs an authentication process with respect to an RUIC that accesses an event page through an HTTP GET command. The authentication performing unit includes an event notification unit an authentication information receiving unit and a determining unit .

When the estimation unit determines that the current home network is the user home network the event notification unit transmits the event page to an RUIC selected by a user in a multicast or unicast method. When a plurality of RUICs are selected the event page is transmitted using a multicast method. When a single RUIC is selected the event page is transmitted using a unicast method.

The event notification unit may transmit an event notification message including an authentication page whose URL is replaced with a URL of the event page to the RUIC in order to request authentication information of the RUIC.

When the URL of the event page of the event notification message is replaced with the URL of the authentication page the authentication information receiving unit receives the authentication information input by a user from the RUIC through an HTTP POST command using the authentication page. Alternatively when the URL of the event page is included in the event notification message the authentication information receiving unit transmits an HTTP Login Required message in response to a HTTP GET command with respect to the event page and receives the authentication information input by the user from the RUIC through the HTTP GET command by using an authentication window in response to the HTTP 401 Login Required message.

The determining unit determines whether the authentication information input to the RUIC by the user is correct with respect to authentication information that is previously stored in the memory and then determines whether user authentication is successful.

When the determining unit determines that the user authentication is successful the event page providing unit transmits the event page to the RUIC.

While the present invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by one of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the following claims.

