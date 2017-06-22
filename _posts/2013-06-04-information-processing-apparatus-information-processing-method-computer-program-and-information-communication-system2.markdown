---

title: Information processing apparatus, information processing method, computer program, and information communication system
abstract: There is provided an information processing apparatus including a Web service using unit configured to have a Web browser function supporting a cookie and use a Web service provided by a Web server, a URL acquiring unit configured to acquire a URL to use a Web service in a different device, and a URL transferring unit configured to transfer the URL acquired by the URL acquiring unit to the different device. The URL acquiring unit acquires a one-time URL to make an access request to a Web service requesting authentication, from the Web server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09628320&OS=09628320&RS=09628320
owner: Saturn Licensing LLC
number: 09628320
owner_city: New York
owner_country: US
publication_date: 20130604
---
The present disclosure in the specification relates to an information processing apparatus information processing method computer program and information communication system in which web services requesting authentication are used in homes. Specifically the present disclosure relates to an information processing apparatus information processing method computer program and information communication system that switch devices using Web services requesting authentication.

Web services that can be used on the Internet include Web services requesting authentication. For example at the time of using such services from a multifunctional terminal such as a smartphone the user may perform an input operation of URL Uniform Resource Locator or ID and password through a user interface held in the multifunctional terminal and after that it is possible to play content provided by Web services on a screen of the terminal.

Also there is a case where the user wants to view content which is viewed on the multifunctional terminal using a larger screen of a TV set. Most of recent TV sets incorporate a browser function and can display Web services of the multifunctional terminal on the TV set.

However in the case of using a Web service requesting authentication the user is requested to input authentication information such as the same ID and password on the TV set side again which is bothersome. It is troublesome to repeat an input operation of the same character string every time a device to display Web services is switched regardless of performing the authentication processing once on the multifunctional terminal. Also an input of the string character in the TV set is normally performed through a numeric key or arrow key of a remote control device which is a very troublesome operation for the user.

For example there is suggested a content distribution system in which at the time of changing a content viewing terminal to view content distributed from a content server requesting login authentication an original viewing terminal acquires a view right certificate from an authentication management apparatus and transfers it to a destination content viewing terminal and the destination content viewing terminal uses the received view right certificate assertion and requests the content to a content providing apparatus e.g. see Japanese Patent Laid open No. 2009 217370 . According to this content distribution system the destination content viewing terminal can save the effort of performing login by the destination content viewing terminal. However in the case of this content distribution system the view right certificate i.e. authentication information is moved at the time of switching a viewing terminal. Therefore since not only the authentication management apparatus but also the original content viewing terminal and the destination content viewing terminal request a dedicated system to perform authentication information processing the system becomes large.

According to a technique disclosed in the specification for example there are provided a superior information processing apparatus information processing method computer program and information communication system that can switch a device using Web services requesting authentication by a simple operation on a home network.

According to an embodiment of the present technology there is provided an information processing apparatus including a Web service using unit configured to have a Web browser function supporting a cookie and use a Web service provided by a Web server a URL acquiring unit configured to acquire a URL to use a Web service in a different device and a URL transferring unit configured to transfer the URL acquired by the URL acquiring unit to the different device. The URL acquiring unit acquires a one time URL to make an access request to a Web service requesting authentication from the Web server.

The information processing apparatus may further include an inputting unit on which a user performs an input operation of a character. At a time of using a Web service requesting authentication the Web service using unit may transmit authentication information input by the user though the inputting unit to the Web server by using the Web browser function.

By using the Web browser function the URL acquiring unit may send a query as to whether the Web service used by the different device requests authentication to the Web server.

The URL acquiring unit may transmit an HTTP HEAD request with respect to a URL of the Web service and in a case where a one time URL issue requestor is included in a header of a response to the HTTP HEAD request recognize that the Web service requests authentication.

The URL acquiring unit may transmit an HTTP GET request with respect to a one time URL issue API extracted from the header of the response and receive a one time URL as a response to the HTTP GET request.

The URL transferring unit may serve as a digital media controller and a digital media server of DLNA and transmit a URL as mimetype text html to the different device serving as a digital media renderer.

Further according to an embodiment of the present technology there is provided an information processing apparatus including a URL acquiring unit configured to acquire a URL to use a Web service from a different device and a Web service using unit configured to have a Web browser function supporting a cookie make an access request to the URL acquired by the URL acquiring unit and use a Web service provided by a Web server. The URL acquiring unit acquires a one time URL to make an access request to a Web service requesting authentication from the different device. And the Web service using unit uses the Web service requesting authentication by using the one time URL.

In response to reception of a URL as mimetype text html from the different device serving as a digital media controller and a digital media server the URL acquiring unit serving as a digital media renderer of DLNA may activate the Web browser function of the Web service using unit and display the received URL.

Further according to an embodiment of the present technology there is provided an information processing apparatus including a Web service providing unit configured to provide a Web service a one time URL providing unit configured to generate a one time URL to access a Web service requesting authentication and transmit the one time URL to a first device and a one time URL storing unit configured to store the one time URL and session information of the first device as a pair. At a time of receiving a one time URL from a second device the Web service providing unit checks the session information stored as one of the pair in the one time URL storing unit and provides a Web service requesting authentication.

In a case where the first device accesses a Web service requesting authentication the Web service providing unit may request a user to input authentication information on a Web browser incorporated in the first device and in a case where the authentication information is correctly authorized manage the session information by a cookie.

In a case where an HTTP HEAD request received from the first device is an access request with respect to a URL of a Web service requesting authentication in response to this the one time URL providing unit may transmit a one time URL issue requestor including a one time URL issue API and show the first device that the URL is a Web service requesting authentication.

At a time of receiving an HTTP GET request with respect to the one time URL issue API from the first device the one time URL providing unit may check that the first device is already authorized generate a one time URL with respect to the Web service requesting authentication and transmit the one time URL as a response to the HTTP GET request.

In a case where the second device accesses the one time URL based on the session information stored as one of the pair in the one time URL storing unit the Web service providing unit may take that the second device logs in with same authentication information as the first device and transmit a cookie to manage the session information to the second device and start a new session.

The Web service providing unit may discard the one time URL accessed by the second device and the session information as one of the pair from the one time URL storing unit.

Further according to an embodiment of the present technology there is provided an information processing method including using a Web service provided by a Web server acquiring a URL to use a Web service in a different device and transferring the URL acquired in the URL acquiring step to the different device. In the URL acquiring step a one time URL to make an access request to a Web service requesting authentication is acquired from the Web server.

Further according to an embodiment of the present technology there is provided an information processing method including acquiring a URL to use a Web service from a different device and making an access request to the URL acquired in the URL acquiring step and using a Web service provided by a Web server. In the URL acquiring step a one time URL to make an access request to a Web service requesting authentication is acquired from the different device. And in the Web service using step the Web service requesting authentication is used by using the one time URL.

Further according to an embodiment of the present technology there is provided an information processing method including providing a Web service generating a one time URL to access a Web service requesting authentication and transmitting the one time URL to a first device and storing the one time URL and session information of the first device as a pair. In the Web service providing step at a time of receiving a one time URL from a second device the session information stored as one of the pair in the one time URL storing step is checked and a Web service requesting authentication is provided.

Further according to an embodiment of the present technology there is provided a computer program written in a computer readable format to cause a computer to function as a Web service using unit configured to have a Web browser function supporting a cookie and use a Web service provided by a Web server a URL acquiring unit configured to acquire a URL to use a Web service in a different device and a URL transferring unit configured to transfer the URL acquired by the URL acquiring unit to the different device. The URL acquiring unit acquires a one time URL to make an access request to a Web service requesting authentication from the Web server.

Further according to an embodiment of the present technology there is provided a computer program written in a computer readable format to cause a computer to function as a URL acquiring unit configured to acquire a URL to use a Web service from a different device and a Web service using unit configured to have a Web browser function supporting a cookie make an access request to the URL acquired by the URL acquiring unit and use a Web service provided by a Web server. The URL acquiring unit acquires a one time URL to make an access request to a Web service requesting authentication from the different device. And the Web service using unit uses the Web service requesting authentication by using the one time URL.

A computer program according to an embodiment of the present disclosure defines a computer program described in a computer readable format such that predetermined processing is realized on a computer. In other words by installing the computer program according to the embodiment of the present disclosure in the computer a coactive operation is exerted on the computer and it is possible to acquire the same operational effect as an information processing apparatus according to an embodiment of the present disclosure.

Further according to an embodiment of the present technology there is provided an information communication system including a first device having a web browser function a second device having a web browser function and a Web server providing a Web service in a case where a URL is accessed. The Web server issues a one time URL to access a Web service requesting authentication to an authorized device and stores the one time URL and session information of the device as a pair. The first device transmits authentication information to the Web server through the Web browser function acquires the one time URL and transfers the one time URL to the second device. And the second device accesses the Web service requesting authentication by the received one time URL.

However the system herein denotes a logical aggregation of multiple apparatuses or functional modules to realize a specific function and it does not matter whether the apparatuses or functional modules are included in a single chassis.

According to a technique disclosed in the specification for example it is possible to provide a superior information processing apparatus information processing method computer program and information communication system that can save the effort of repeat login and switch a device using Web services requesting authentication on a home network.

Also according to a technique disclosed in the specification it is possible to provide a superior information processing apparatus information processing method computer program and information communication system that can switch a device using Web services requesting authentication without exchanging authentication information on a home network.

Other objects features and advantages of the technique disclosed in the specification are clarified by detailed explanation based on embodiments and appended drawings described below.

Hereinafter preferred embodiments of the present disclosure will be described in detail with reference to the appended drawings. Note that in this specification and the appended drawings structural elements that have substantially the same function and structure are denoted with the same reference numerals and repeated explanation of these structural elements is omitted.

In the following embodiments of a technique disclosed in the specification are explained in detail with reference to the drawings.

On Internet an endless number of hosts not illustrated including the Web server are set. In the present embodiment the Web server provides Web services requesting authentication on the Internet . An example of the Web services is streaming of moving image content.

Also an endless number of networks not illustrated including a LAN Local Area Network are mutually connected to the Internet .

The LAN is installed in for example a home. Also in the home there are provided devices incorporating Web browsers connectable to the LAN and the Internet such as the TV set and the portable device including a smartphone and it is possible to use Web services such as moving image streaming provided by the Web server from the devices. The Web browsers incorporated in the portable device and the TV set correspond to cookies.

In the LAN as a system to operate AV content via an IP Internet Protocol network in the home for example the DLNA Digital Living Network Alliance guideline is installed. Here the DLNA guideline 1.0 and 1.5 defines connection conditions of 2 box pull system usage including a DMS Digital Media Server corresponding to a server to provide content and a DMP Digital Media Player corresponding to a client to play it. Also the DLNA guideline 1.5 defines 3 box system usage including a DMR Digital Media Renderer and a DMC Digital Media Controller and the client can operate the DMC transmit content from the DMS to the DMR and play it.

When the system of the DLNA guideline is applied to the information communication system illustrated in there is assumed an operation in which the portable device serves as the DMC and the DMS the TV set serves as the DMR and AV content is played on the TV set .

For example when a Web service used in the portable device is requested to be displayed on a large screen of the TV set the portable device as the DMC and the DMS may perform DLNA push of URL to access the Web service to the TV set as the DMR. Here at the time of using a Web service requesting authentication the portable device transmits authentication information such as an ID and password input by the user on the Web browser to the Web server and the Web server performs authentication processing. Also the Web server issues a one time URL to access a Web service to the authorized portable device and stores it and session information of the portable device as a pair. Therefore when the portable device gives the one time URL to the TV set by accessing this one time URL the TV set can take over the authentication state and use the same Web service without inputting the authentication information again.

First an explanation is given to a case where a Web service which requests authentication and is provided in the Web server is used on the LAN .

First the user inputs an URL of the Web service provided by the Web server in a Web browser on the portable device . At this time the Web server requests authentication for use of the Web service and displays a screen to request the user to input an ID and password on the Web browser. In response to this when the user uses an UI User Interface such as a button and touch panel held in the portable device and correctly inputs authentication information including the ID and the password it is transmitted from the Web browser to the Web server . Subsequently the Web server performs authentication processing of the user or the portable device using the received ID and password and if the authentication succeeds displays a screen to provide the Web service on the Web browser.

The portable device requests an URL input in the Web browser to the Web server SEQ . This request is performed using for example an HTTP Hyper Text Transfer Protocol GET message. Here it is assumed that the requested URL is a Web service requesting authentication.

When receiving the request from the portable device the Web server checks whether the portable device is authorized SEQ . Subsequently when the portable device is not authorized yet the Web server displays a screen to request the user to input an ID and password on the Web browser SEQ .

On the side of the portable device when the user inputs a correct ID and password for example it is transmitted from the Web browser to the Web server using an HTTP POST message SEQ . In response to this the Web server checks the received ID and password and performs authentication processing of the user or the portable device SEQ .

Here if the authentication succeeds the Web server generates a cookie to manage a login session with the portable device links this with user information and manages these. Further the Web server inserts the cookie in the header of a response to the HTTP POST message and transmits content to the portable device SEQ .

The portable device stores the cookie received from the Web server SEQ . After that by inserting the cookie in the head part of a request to the Web server and transmitting it the portable device can deal with the Web server while maintaining a connection state of the login session. Subsequently on the side of the portable device the content received by the Web browser from the Web server is displayed SEQ .

After that it is assumed that the user wants to view the content which is viewed on the portable device using a larger screen of the TV set . In such a case the user performs an operation of transmitting the URL of the content displayed on the portable device to the TV set .

When the URL transmission operation for other devices such as the TV set is performed by the user the portable device transmits an HTTP HEAD request with respect to the URL to be displayed on the TV set to the Web server .

Here although a response to the HTTP HEAD request does not include a message body other responses are equivalent to those to the HTTP GET request and it is often used to acquire additional information with respect to the request. For example although requested content itself is cached in the portable device the HTTP HEAD request is transmitted at the time of checking whether the content is updated.

When receiving the HTTP HEAD request the Web server checks whether authentication is requested to display the requested URL. Subsequently in a case where the authentication is requested it returns a response in which a one time URL issue requestor shown in following table is attached into the header to the portable device .

The one time URL issue requestor shown in the above table is formed with a combination of the value X OneTimeURLIssuer showing that the response header is a one time URL issue requestor and a character string http a.b.c onetimeurl url http a.b.c xyz.html of an API Application Programming Interface to request an issue of the one time URL. For example the URL of a Web service requesting authentication is http a.b.c xyz.html and an issue request of a one time URL with respect to that URL is represented by http a.b.c onetimeurl url http a.b.c xyz.html.

Here the one time URL is an URL with an expiration date with respect to a resource for which the Web server accepts an HTTP GET request only once or in a limited time or number . The above one time URL issue API is an API to request to the Web server a one time URL to access an URL requesting authentication. The Web server discards the issued one time URL in a case where a certain period of time elapses or the number of accesses is one or predetermined number .

When receiving a response to the HTTP HEAD request from the Web server the portable device checks whether the header includes a one time URL issue requestor X OneTimeURLIssuer .

In a case where this response header does not include the one time URL issue requestor it is interpreted that the Web service requested by the HTTP HEAD request does not request authentication. Therefore the portable device may transmit the URL to be displayed on the TV set without requesting a generation of the one time URL as is to the TV set .

Meanwhile in a case where the response header includes the one time URL issue requestor i.e. in a case where the header includes a character string X OneTimeURLIssuer it is interpreted that the Web service requested by the HTTP HEAD request requests authentication and the Web server has issued the one time URL issue API. In this case the portable device regards the value http a.b.c onetimeurl url http a.b.c xyz.html set in the header as the one time URL issue API and transmits an HTTP GET request for the URL to the Web server .

When receiving this HTTP GET request the Web server checks an authentication state of the portable device of the transmission source. The portable device inserts a cookie acquired in an authentication sequence in the header part and transmits the HTTP GET request. Also the Web server links the cookie generated in the authentication sequence with user information and manages these as described above . Therefore the Web server can check the authentication state of the portable device based on the cookie extracted from the header of the HTTP GET request.

When finding that the portable device is authorized after generating the one time URL requested be issued the Web server transmits to the portable device a response to the HTTP GET request including the one time URL as a message body. Meanwhile in a case where the portable device is not authorized the Web server returns an error message 401 Unauthorized. Subsequently in response to this error message the portable device cancels processing of displaying content of the URL on other devices such as the TV set .

In the parameters of the one time URL issue API see Table 1 an URL in this example http a.b.c xyz.html indicating content to be displayed on the TV set by the portable device is designated. Authentication is not requested to access the one time URL generated from the parameter designated in the one time URL issue API. At this time to turn over session information i.e. authentication state of the portable device to the TV set through the one time URL the Web server temporarily stores this one time URL and the session information as a pair. At the timing the one time URL becomes invalid the Web server discards the pair of the one time URL and the session information.

The portable device extracts the message boy from the response received from the Web server specifies an URL to be transmitted to the TV set and transmits it to the TV set .

First the portable device transmits to the Web server an HTTP HEAD request to a URL to be displayed on the TV set step S . For example in response to a URL transmission operation performed for other devices such as the TV set by the user transmission processing of an HTTP HEAD request is activated.

The Web server checks whether authentication is requested to display the URL requested by the HTTP HEAD request step S .

Here in a case where a URL not requesting authentication is requested No in step S the Web server attaches a status 200 OK to the header part and returns a response to the HTTP HEAD request to the portable device step S .

Also in a case where a URL requesting authentication is requested Yes in step S the Web server sets a combination of a value X OneTimeURLIssuer indicating a one time URL issue requestor and a character string http a.b.c onetimeurl url http a.b.c xyz.html of an API Application Programming Interface to request an issue of a one time URL to the header part step S and returns a response to the HTTP HEAD request to the portable device step S .

The portable device checks whether the header of the response received from the Web server includes the one time URL issue requestor X OneTimeURLIssuer step S .

Here in a case where the response header does not include the one time URL issue requestor No in step S the portable device transmits the URL to be displayed on the TV set as is to the TV set step S .

Meanwhile in a case where the response header includes the one time URL issue requestor Yes in step S the portable device can recognize it as a URL requesting authentication. In this case the portable device regards the value http a.b.c onetimeurl url http a.b.c xyz.html set in the header as the one time URL issue API and transmits an HTTP GET request to the URL to the Web server step S .

When receiving this HTTP GET request the Web server checks an authentication state of the portable device of the transmission source step S . A cookie is attached to the header of the HTTP GET request and the Web server can check the authentication state of the portable device based on user information linked with the cookie.

Here in a case where the portable device is not authorized No in step S the Web server returns an error message 401 Unauthorized step S . Subsequently in response to this error message the portable device cancels processing of displaying content of the URL on the TV set step S and the processing routine is over.

Meanwhile when it is found that the portable device is authorized Yes in step S the Web server generates the one time URL requested to be issued and temporarily stores this and session information as a pair step S . Also the Web server transmits to the portable device a response to the HTTP GET request using the generated one time URL as a message body step S .

When the portable device extracts the message body from the response received from the Web server and specifies a URL to be transmitted to the TV set step S the portable device transmits the URL to the TV set step S . In step S although the portable device transmits the one time URL to the TV set by DLNA push and activates a Web browser on the TV set this point is described below in detail.

The portable device requests a one time URL issue API by HTTP GET SEQ . At this time by including a cookie in the header of the HTTP GET request session information is transmitted.

When receiving this HTTP GET request the Web server checks an authentication state of the portable device of the transmission source based on user information linked with the cookie. Subsequently when finding that the portable device is authorized the Web server generates a one time URL corresponding to a URL http a.b.c xyz.html to be transmitted to the TV set SEQ .

Also to turn over session information to the TV set through the one time URL the Web server temporarily stores this one time URL and the session information as a pair SEQ .

Subsequently the Web server transmits to the portable device a response to the HTTP GET request using the generated one time URL as a message body SEQ .

The portable device extracts the one time URL from the message body of the response received from the Web server and holds it SEQ . After that the portable device transmits the one time URL to the TV set by DLNA push and activates a Web browser on the TV set .

A system of the DLNA guideline is installed in the information communication system according to the present embodiment the portable device serves as a DMS to distribute a URL and as a DMC to transmit content and the TV set serves as a DMR as described above . Here in the URL transmission from the portable device to the TV set a DLNA renderer is expanded and used so as to identify mimetypr text html. 

The portable device serving as the DMS and the DMC multicasts an M SEARCH message using urn schemas upnp org device MediaRenderer 1 as an ST Search Target and waits for a response from the DMR on the LAN SEQ .

The TV set serves as the DMR and therefore responses to the M SEARCH message from the portable device .

The portable device transmits a GetProtocolInfo message to check whether there is text html in formats that can be played by the TV set responding to the M SEARCH message SEQ . That is the portable device checks whether a URL to be subjected to DLNA push can be displayed by the TV set .

In response to GetProtocolInfo the TV set replies a list of protocols formats that can be played by the apparatus SEQ . At that time text html is included in the list to show that the TV set supports activation of the Web browser.

When finding from the received list that the TV set supports text html SEQ the portable device subsequently transmits a PrepareForConnection message SEQ and starts connection with the TV set . When the TV set returns a response in response to the PrepareForConnection message SEQ connection between the portable device and the TV set is established.

Next the portable device transmits a SetAVTransportURI message to the TV set using the one time URL acquired from the Web server as mimetype text html SEQ . In response to this the TV set returns a response SEQ .

Subsequently the portable device transmits a Play message to the TV set and requests a playback of the transmitted one time URL SEQ . The TV set returns a response in response to the Play message SEQ . Also in a case where mimetype of the URL set by the received SetAVTransportURI message is text html the TV set activates the Web browser incorporated in the device and displays the URL SEQ .

As described above the Web server temporarily stores the one time URL and session information as a pair. Therefore when the TV set accesses the one time URL the Web server can check whether the TV set takes over the session information of the portable device through this one time URL.

That is when the TV set accesses the one time URL the Web server transmits a cookie to the TV set using the session information stored as one of the pair takes that the TV set requests a login by the same ID as that input on the portable device and starts a login session. After that the TV set and the Web server perform communication while exchanging the session information using this cookie.

The TV set requests a one time URL which is requested to be played from the portable device to the Web server SEQ . This request is performed using for example an HTTP GET message.

The Web server searches for session information stored as a pair with the one time URL accessed by the TV set SEQ . Subsequently when the session information pairing up with the one time URL is found it is possible to recognize that the TV set takes over the session information from the authorized portable device .

The Web server newly generates a cookie to manage a login session with the TV set and starts a new session with the TV set SEQ . Also the Web server links the generated cookie with user information and manages it.

Subsequently the Web server inserts the cookie in the header of a response to the HTTP GET message and transmits content to the TV set SEQ .

Here the Web server discards information of the one type URL which the TV set accessed once. Also the Web server discards the session information pairing up with the one time URL too SEQ . After that since an error occurs if the discarded or invalidated one time URL is accessed it is not possible to view it if the same URL is displayed later.

The TV set stores the cookie received from the Web server SEQ . After that by inserting the cookie in the header part of a request to the Web server and transmitting the result the TV set can deal with the Web server while maintaining a connection state of the login session. Subsequently on the side of the TV set the content received by the Web browser from the Web server is displayed SEQ .

Thus while using a Web service requesting authentication on the portable device it is possible to display the same Web service on the Web browser incorporated in the TV set without authorizing the TV set . The TV set gets in a login state without performing an input operation of login information such as an ID and password on the Web browser.

Here although it is not illustrated the TV set can perform the processing procedures illustrated in and in the same way and issue a one time URL. Subsequently by transferring i.e. DLNA push this one time URL to other devices e.g. DMR on the LAN the TV set can further turn over the session information taken over from the portable device .

When there is a request to a one time URL issue API the Web server is designed to check authentication information of the access source and deny the access in the case of an unauthorized terminal e.g. see step S in . Therefore even a device on the LAN may not use a Web service requesting authentication unless it is in an authorized state e.g. it is not possible to display a page requesting authentication . Also since a one time URL is basically transmitted in the LAN using a system of DLNA it is difficult for a third party to intercept it.

Also a one time URL is generated on the side of the Web server and consequently on the Web service side handling the Web server it is possible to control conditions as to whether to generate a one time URL and conditions such as a period of time to discard the generated one time URL. As for Web services it is possible to set a security level every Web service i.e. every provided content .

Although it is possible to take over session information or authentication information through a one time URL it is only the Web server that manages the authentication information. In other words the portable device and the TV set request a one time URL issue API to issue a one time URL and receive URL push to activate a Web browser and take over the use of a Web service but it is not requested to exchange authentication information with the Web server and it can be realized by a simple system.

The communication processing unit connects to the LAN and the Internet and performs a communication operation as a DMC and DMS of DLNA and a communication operation as a Web client.

The Web service using unit has a Web browser function and accesses a URL input by the user through for example the inputting unit and displays a Web service provided by the Web server on the displaying unit . The Web service using unit has a Web browser function supporting a cookie and stores a cookie received from the Web server and includes the cookie in the header of a message directed to the Web server .

The URL acquiring unit acquires a URL to use a Web service in other devices on the LAN such as the TV set . The URL transferring unit transfers the URL acquired by the URL acquiring unit to other devices on the LAN such as the TV set .

In the case of using a Web service requesting authentication the Web service using unit transmits to the Web server authentication information such as an ID and password input in the Web browser through the inputting unit by the user. Also the URL acquiring unit acquires a one time URL to make an access request to a Web service requesting authentication from the Web server and the URL transferring unit transfers the acquired one time URL to other devices.

Using the Web browser function the URL acquiring unit can send a query as to whether a Web service to be used by the TV set requests authentication to the Web server . To be more specific the URL acquiring unit transmits an HTTP HEAD request to the URL of the Web service to the Web server . Subsequently whether the Web service requests authentication is checked depending on whether a one time URL issue requestor is included in the header of a response from the Web server . Also the URL acquiring unit can transmit an HTTP GET request with respect to the one time URL issue API extracted from the header of the response from the Web server and receive a one time URL as the response.

Also the URL transferring unit serves as a DMC and DMS of DLNA and transmits a URL or one time URL as mimetype text html to the TV set serving as a DMR.

Also schematically illustrates a functional configuration of an information processing apparatus operating as the TV set in the information communication system according to the present embodiment. The information processing apparatus illustrated in the figure includes a communication processing unit an inputting unit a displaying unit a URL acquiring unit and a Web service using unit . However as for function modules that are not directly related to the gist of the technique disclosed in the specification their illustration is omitted.

The communication processing unit connects to the LAN and the Internet and performs a communication operation as a DMR of DLNA and a communication operation as a Web client.

The URL acquiring unit acquires a URL to use the same Web service from other devices such as the portable device . The Web service using unit has a Web browser function and makes an access request to the URL acquired by the URL acquiring unit and uses a Web service provided by the Web server . The Web service using unit has a Web browser function supporting a cookie and stores a cookie received from the Web server and includes the cookie in the header of a message to the Web server .

Here in a case where a Web service to be used requests authentication the URL acquiring unit acquires a one time URL to make an access request to the Web service from the portable device and the Web service using unit uses this one time URL to use the Web service requesting authentication.

In response to reception of a URL as mimetype text html from the portable device serving as a DMR of DLNA and a DMC and DMS the URL acquiring unit activates the Web browser function of the Web service using unit and displays the received URL on the displaying unit .

Also schematically illustrates a functional configuration of an information processing apparatus operating as a Web server in the information communication system according to the present embodiment. The information processing apparatus illustrated in the figure includes a communication processing unit an inputting unit a displaying unit a Web service providing unit a one time URL providing unit and a one time URL storing unit . However as for function modules that are not directly related to the gist of the technique disclosed in the specification their illustration is omitted.

The communication processing unit connects to the Internet and performs a communication operation as a Web server.

The Web service providing unit basically provides a Web service such as transmission of a corresponding Web page in response to an access request of a URL. The information communication system according to the present embodiment has a feature in that the Web service providing unit causes even the TV set to take over an authentication state and use a Web service which is used through authentication processing in the portable device . Therefore the one time URL providing unit generates a one time URL to access the Web service requesting authentication and transmits it to the portable device . Also the one time URL storing unit stores the generated one time URL and session information of the portable device as a pair to realize a transition of the session information. Subsequently when receiving a one time URL from the TV set the Web service providing unit checks the session information stored as one of the pair in the one time URL storing unit and provides the Web service requesting authentication.

In a case where an HTTP HEAD request received from the portable device or the like is an access request to a URL of a Web service requesting authentication in response to this the one time URL providing unit transmits a one time URL issue requestor see Table 1 including a one time URL issue API and shows the request source that it is a Web service requesting information. Subsequently when an HTTP GET request to the one time URL issue API is received after it is checked that it is already authorized a one time URL for the Web service requesting authentication is generated and transmitted as an HTTP GET response.

The Web service providing unit requests an input of authentication information by the user on the Web browser incorporated in the portable device when the portable device accesses a Web service requesting authentication. Subsequently if it is correctly authorized session information is managed by a cookie.

Also when the TV set accesses the one time URL taken over from the portable device the Web service providing unit takes that it logs in with the same authentication information as the portable device based on session information stored as one of the pair in the one time URL storing unit . At this time the Web service providing unit transmits a cookie to manage the session information and starts a new session with the TV set . Subsequently the one time URL accessed by the TV set and the session information as one of the pair are discarded by the one time URL storing unit .

a Web service using unit configured to have a Web browser function supporting a cookie and use a Web service provided by a Web server 

a URL transferring unit configured to transfer the URL acquired by the URL acquiring unit to the different device 

wherein the URL acquiring unit acquires a one time URL to make an access request to a Web service requesting authentication from the Web server.

wherein at a time of using a Web service requesting authentication the Web service using unit transmits authentication information input by the user though the inputting unit to the Web server by using the Web browser function.

wherein by using the Web browser function the URL acquiring unit sends a query as to whether the Web service used by the different device requests authentication to the Web server.

wherein the URL acquiring unit transmits an HTTP HEAD request with respect to a URL of the Web service and in a case where a one time URL issue requestor is included in a header of a response to the HTTP HEAD request recognizes that the Web service requests authentication.

wherein the URL acquiring unit transmits an HTTP GET request with respect to a one time URL issue API extracted from the header of the response and receives a one time URL as a response to the HTTP GET request.

wherein the URL transferring unit serves as a digital media controller and a digital media server of DLNA and transmits a URL as mimetype text html to the different device serving as a digital media renderer.

a Web service using unit configured to have a Web browser function supporting a cookie make an access request to the URL acquired by the URL acquiring unit and use a Web service provided by a Web server 

wherein the URL acquiring unit acquires a one time URL to make an access request to a Web service requesting authentication from the different device and

wherein the Web service using unit uses the Web service requesting authentication by using the one time URL.

wherein in response to reception of a URL as mimetype text html from the different device serving as a digital media controller and a digital media server the URL acquiring unit serving as a digital media renderer of DLNA activates the Web browser function of the Web service using unit and displays the received URL.

a one time URL providing unit configured to generate a one time URL to access a Web service requesting authentication and transmit the one time URL to a first device and

a one time URL storing unit configured to store the one time URL and session information of the first device as a pair 

wherein at a time of receiving a one time URL from a second device the Web service providing unit checks the session information stored as one of the pair in the one time URL storing unit and provides a Web service requesting authentication.

wherein in a case where the first device accesses a Web service requesting authentication the Web service providing unit requests a user to input authentication information on a Web browser incorporated in the first device and in a case where the authentication information is correctly authorized manages the session information by a cookie.

wherein in a case where an HTTP HEAD request received from the first device is an access request with respect to a URL of a Web service requesting authentication in response to this the one time URL providing unit transmits a one time URL issue requestor including a one time URL issue API and shows the first device that the URL is a Web service requesting authentication.

wherein at a time of receiving an HTTP GET request with respect to the one time URL issue API from the first device the one time URL providing unit checks that the first device is already authorized generates a one time URL with respect to the Web service requesting authentication and transmits the one time URL as a response to the HTTP GET request.

wherein in a case where the second device accesses the one time URL based on the session information stored as one of the pair in the one time URL storing unit the Web service providing unit takes that the second device logs in with same authentication information as the first device and transmits a cookie to manage the session information to the second device and starts a new session.

wherein the Web service providing unit discards the one time URL accessed by the second device and the session information as one of the pair from the one time URL storing unit.

wherein in the URL acquiring step a one time URL to make an access request to a Web service requesting authentication is acquired from the Web server.

making an access request to the URL acquired in the URL acquiring step and using a Web service provided by a Web server 

wherein in the URL acquiring step a one time URL to make an access request to a Web service requesting authentication is acquired from the different device and

wherein in the Web service using step the Web service requesting authentication is used by using the one time URL.

generating a one time URL to access a Web service requesting authentication and transmitting the one time URL to a first device and

wherein in the Web service providing step at a time of receiving a one time URL from a second device the session information stored as one of the pair in the one time URL storing step is checked and a Web service requesting authentication is provided.

a Web service using unit configured to have a Web browser function supporting a cookie and use a Web service provided by a Web server 

a URL transferring unit configured to transfer the URL acquired by the URL acquiring unit to the different device 

wherein the URL acquiring unit acquires a one time URL to make an access request to a Web service requesting authentication from the Web server.

a Web service using unit configured to have a Web browser function supporting a cookie make an access request to the URL acquired by the URL acquiring unit and use a Web service provided by a Web server 

wherein the URL acquiring unit acquires a one time URL to make an access request to a Web service requesting authentication from the different device and

wherein the Web service using unit uses the Web service requesting authentication by using the one time URL.

wherein the Web server issues a one time URL to access a Web service requesting authentication to an authorized device and stores the one time URL and session information of the device as a pair 

wherein the first device transmits authentication information to the Web server through the Web browser function acquires the one time URL and transfers the one time URL to the second device and

wherein the second device accesses the Web service requesting authentication by the received one time URL.

The technique disclosed in the specification has been explained in detail with reference to the specific embodiment. However it is clear that the embodiment can be amended or substituted by those skilled in the art without departing from the gist of the technique disclosed in the specification.

In the specification although an explanation has been mainly given to the embodiment in which the identical Web service is used between devices on a LAN using the system of the DLNA guideline the gist of the technique disclosed in the specification is not limited to a specific guideline. The technique disclosed in the specification is also applicable to a case where the identical Web service is used between multiple devices on a LAN not using the DLNA guideline or the identical Web service is used between multiple devices on a wide area network such as the Internet instead of the LAN.

In short the technique disclosed in the specification has been explained in a format of exemplification and the description content of the specification should not be limitedly interpreted. To decide the gist of the technique disclosed in the specification the claims should be referred to.

The present disclosure contains subject matter related to that disclosed in Japanese Priority Patent Application JP 2012 146120 filed in the Japan Patent Office on Jun. 28 2012 the entire content of which is hereby incorporated by reference.

