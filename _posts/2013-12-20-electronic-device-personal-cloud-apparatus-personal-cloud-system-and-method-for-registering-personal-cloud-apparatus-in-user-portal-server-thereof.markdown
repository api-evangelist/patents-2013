---

title: Electronic device, personal cloud apparatus, personal cloud system and method for registering personal cloud apparatus in user portal server thereof
abstract: An electronic device, a personal cloud apparatus, a personal cloud system, and a method thereof for registering personal cloud apparatus are provided. The method of the electronic device for registering the personal cloud apparatus includes pairing with the personal cloud apparatus when an application is executed, acquiring information about an access point and transmitting the same to the personal cloud apparatus to connect the personal cloud apparatus to a network, and registering the personal cloud apparatus to a registration server, when the personal cloud apparatus is connected to the network via the access point. As a result, users are able to upload or download various contents using the personal cloud apparatus, inside or outside the house.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09386445&OS=09386445&RS=09386445
owner: Samsung Electronics Co., Ltd.
number: 09386445
owner_city: Suwon-si
owner_country: KR
publication_date: 20131220
---
This application claims the benefit under 35 U.S.C. 119 a of a Korean patent application filed on Dec. 21 2012 in the Korean Intellectual Property Office and assigned Serial 10 2012 0150189 the entire disclosure of which is hereby incorporated by reference.

The present disclosure relates to an electronic device a personal cloud apparatus a personal cloud system and a method thereof for registering a personal cloud apparatus. More particularly the present disclosure relates to an electronic device a personal cloud apparatus and a personal cloud system in which the electronic device is able to access the personal cloud apparatus via a home network or an external network and store and share contents and a method for registering the personal cloud apparatus.

Combined with the increased amount of contents and fast advancing communication technologies the cloud service has recently begun providing download services enabling an electronic device such as a smart phone to download the contents anywhere and anytime.

Considering the Public Cloud Service PCS of the related art as one example of a cloud service a fixed infrastructure is provided and a client e.g. electronic device can access the server via a fixed internet identifier e.g. IP address or domain . Further the Network Attached Storage NAS system of the related art is a network system for sharing storage which uses internal or external electronic devices to upload or download the contents for sharing.

For either PCS or NAS it is necessary for a user to go through an initial process to set up account information to use cloud servers of the related art. This causes an inconvenience to the user who has to perform the initial setup before using the cloud services. When particularly considering the fact that the cloud services of the related art typically use common cloud servers privacy issue also arises.

Recently many electronic devices such as smartphones smart TVs tablet PCs etc. are used in homes. It is therefore increasingly desired that the family members be able to share contents. Given the above there exists a need for a personal cloud apparatus that a family member can use personally or all the family can use commonly.

The above information is presented as background information only to assist with an understanding of the present disclosure. No determination has been made and no assertion is made as to whether any of the above might be applicable as prior art with regard to the present disclosure.

Aspects of the present disclosure are to address at least the above mentioned problems and or disadvantages and to provide at least the advantages described below. Also the present inventive concept is not required to overcome the disadvantages described above and an embodiment of the present inventive concept may not overcome any of the problems described above.

An aspect of the present invention is to provide an electronic device a personal cloud apparatus and a personal cloud system to register the personal cloud apparatus to an external registration server so that the electronic device can store and share contents via a network inside a house or an external network using a personal cloud apparatus at home and a method thereof for registering a personal cloud apparatus.

In accordance with an aspect of the present disclosure a method of an electronic device for registering a personal cloud apparatus is provided. The method may include pairing with the personal cloud apparatus when an application is executed acquiring information about an access point transmitting the information about the access point to the personal cloud apparatus to connect the personal cloud apparatus to a network and registering the personal cloud apparatus with a registration server when the personal cloud apparatus is connected to the network via the access point.

The method may additionally include the electronic device entering a Near Field Communication NFC mode in response to a user command when the electronic device is within a threshold distance of the personal cloud apparatus receiving download information of the application using NFC and downloading the application based on the download information of the application.

The pairing may include determining whether the electronic device is in a login state with an authentication server using a specific user account searching available communication interfaces for the pairing with the personal cloud apparatus when determining that the electronic device is in the login state with the authentication server and pairing with the personal cloud apparatus via one of the searched communication interfaces.

The available communication interfaces may include at least one of a Bluetooth interface a WiFi interface and a Zigbee interface.

For the pairing with the personal cloud apparatus via a WiFi interface the pairing may include receiving Service Set IDentifier SSID information when the SSID of the personal cloud apparatus is broadcast via the personal cloud apparatus generating encryption information with a Hash algorithm using the SSID information and MAC address information of the personal cloud apparatus and pairing with the personal cloud apparatus based on the SSID information and the encryption information.

For the pairing with the personal cloud apparatus via a Bluetooth interface the pairing may include performing a discovery operation to search for personal cloud apparatuses existing within a threshold distance of the electronic device receiving MAC address information from the personal cloud apparatus in response to a request for pairing with the searched personal cloud apparatus inputted from a user setting a channel to perform communication with the searched personal cloud apparatus transmitting a request signal for connection to the personal cloud apparatus via the channel and receiving a response signal in response to the request signal.

The transmitting may include transmitting SSID information and encryption information of an access point currently used by the electronic device.

The registering may include receiving MAC address information from the personal cloud apparatus receiving user account information from an authentication server when the user account is logged in to the authentication server transmitting the user account information and the MAC address information to the registration server to register the personal cloud apparatus when the personal cloud apparatus is registered to the registration server using the user account information and the MAC address information receiving from the registration server domain information and peer Identification ID information of a network server to which the personal cloud apparatus can connect and transmitting the received domain information and peer ID information to the personal cloud apparatus.

The personal cloud apparatus may be connected to an external network via the network server using the received domain information and peer ID information and the peer ID information corresponds to MAC address information of the personal cloud apparatus.

The registering may include registering the personal cloud apparatus to the registration server based on a user account. When a plurality of user accounts register the same personal cloud apparatus to the registration server a plurality of electronic devices using the plurality of user accounts share the personal cloud apparatus.

In accordance with another aspect of the present disclosure an electronic device is provided. The electronic device includes a communicator configured to perform communication with a personal cloud apparatus and an external server a storage and a controller configured to perform pairing with a personal cloud apparatus to acquire information of an access point to connect the personal cloud apparatus to a network and to control the communicator to transmit the acquired information to the personal cloud apparatus when an application is executed and to register the personal cloud apparatus to a registration server when the personal cloud apparatus is connected to the network via the access point.

The controller causes the electronic device to enter an NFC mode in response to a user command and when the electronic device is within a threshold distance to the personal cloud apparatus receives download information of the application using the NFC and downloads the application based on the download information of the application and stores the same at the storage.

The controller determines as to whether it is in a login state with an authentication server using a specific user account and when it is in the login state with the authentication server to perform pairing with the personal cloud apparatus searches available communication interfaces and pairs with the personal cloud apparatus via one of the searched communication interfaces.

The available communication interfaces may include at least one of a Bluetooth interface a WiFi interface and a Zigbee interface.

For the pairing with the personal cloud apparatus via a WiFi interface the controller receives SSID information via the communicator when the SSID of the personal cloud apparatus is broadcast via the personal cloud apparatus generates encryption information with a Hash algorithm using the SSID information and MAC address information of the personal cloud apparatus and pairs with the personal cloud apparatus based on the SSID information and the encryption information.

For the pairing with the personal cloud apparatus via a Bluetooth interface the controller performs a discovery operation to search for personal cloud apparatuses existing within a threshold distance of the electronic device receives MAC address information from the searched personal cloud apparatus and in response to a request for pairing with the searched personal cloud apparatus inputted from a user sets a channel to perform communication with the searched personal cloud apparatus transmits a request signal for connection to the personal cloud apparatus via the channel and controls the communicator to receive a response signal in response to the request signal.

The controller controls the communicator to transmit SSID information and encryption information of an access point currently used by the electronic device to the personal cloud apparatus.

The controller receives MAC address information from the personal cloud apparatus and when the user account is logged in to an authentication server receives user account information from the authentication server and transmits the user account information and the MAC address information to the registration server to register the personal cloud apparatus and when the personal cloud apparatus is registered to the registration server using the user account information and MAC address information receives domain information and peer ID information of a network server to which the personal cloud apparatus can connect and controls the communicator to transmit the received domain information and peer ID information to the personal cloud apparatus.

The personal cloud apparatus is connected to an external network via the network server using the received domain information and peer ID information and the peer ID information corresponds to MAC address information of the personal cloud apparatus.

The personal cloud apparatus is registered to the registration server based on a user account and when a plurality of user accounts register the same personal cloud apparatus to the registration server a plurality of electronic devices using the plurality of user accounts share the personal cloud apparatus.

In accordance with an aspect of the present disclosure a method of a personal cloud system for registering a personal cloud apparatus to a registration server is provided. The method includes pairing an electronic device with the personal cloud apparatus when an application of the electronic device is executed and a button of the personal cloud apparatus is selected acquiring at the electronic device information of an access point from the access point to connect the personal cloud apparatus to a network transmitting at the electronic device the information of the access point to the personal cloud apparatus connecting at the personal cloud apparatus to the access point using the information of the access point transmitting at the electronic device user account information and information of the personal cloud apparatus to the registration server to register the personal cloud apparatus to the registration server registering at the registration server the personal cloud apparatus and transmitting domain information and peer ID information of a network server to which the personal cloud apparatus can connect to the electronic device.

In accordance with an aspect of the present disclosure a method for registering a personal cloud apparatus to a registration server is provided. The method includes pairing with an electronic device when a button provided on the personal cloud apparatus is selected receiving from the electronic device information of an access point connecting to the access point using the information of the access point and transmitting MAC address information to the electronic device to register the personal cloud apparatus to the registration server.

Other aspects advantages and salient features of the disclosure will become apparent to those skilled in the art from the following detailed description which taken in conjunction with the annexed drawings discloses various embodiments of the present disclosure.

The following description with reference to the accompanying drawings is provided to assist in a comprehensive understanding of various embodiments of the present disclosure as defined by the claims and their equivalents. It includes various specific details to assist in that understanding but these are to be regarded as merely exemplary. Accordingly those of ordinary skill in the art will recognize that various changes and modifications of the various embodiments described herein can be made without departing from the scope and spirit of the present disclosure. In addition descriptions of well known functions and constructions may be omitted for clarity and conciseness.

The terms and words used in the following description and claims are not limited to the bibliographical meanings but are merely used by the inventor to enable a clear and consistent understanding of the present disclosure. Accordingly it should be apparent to those skilled in the art that the following description of various embodiments of the present disclosure is provided for illustration purpose only and not for the purpose of limiting the present disclosure as defined by the appended claims and their equivalents.

It is to be understood that the singular forms a an and the include plural referents unless the context clearly dictates otherwise. Thus for example reference to a component surface includes reference to one or more of such surfaces.

In the following description various explanations are provided to assist in a comprehensive understanding of the present inventive concept. Accordingly it is apparent that the embodiments of the present disclosure can be carried out without those specifically defined matters. Also well known functions or constructions are not described in detail since they would unnecessarily obscure the disclosure.

Referring to a personal cloud system may include a plurality of electronic devices a personal cloud apparatus a home Access Point AP a public network an authentication validation server an open cloud server a registration server and a network server .

The plurality of electronic devices may download or upload various contents using the personal cloud apparatus . The plurality of electronic devices may particularly perform direct communication with the personal cloud apparatus in the house or perform communication outside the house with the personal cloud apparatus using the public network and the home AP . Accordingly the plurality of electronic devices may download or upload the contents e.g. photos music video etc. using the personal cloud apparatus inside and outside the house.

The personal cloud apparatus refers to hardware where various data of a user may be stored and it may be configured in the form of various types of hardware for storing personal information.

The plurality of electronic devices may be implemented as any of various electronic devices such as smartphones tablet PCs smart TVs and the like.

The personal cloud apparatus is installed in a home or an office and stores contents for sharing by the plurality of electronic devices . The personal cloud apparatus may upload and download the content via direct communication with the electronic device but is not limited thereof. According to another embodiment the personal cloud apparatus may also communicate with the electronic device via the home AP and the public network .

The personal cloud apparatus is particularly registered to the registration server based on user account. Accordingly a certain user outside the house may be able to log in with the registered user account using the electronic device and share the contents stored in the personal cloud apparatus .

The home AP relays connection of the electronic device and the personal cloud apparatus to external public network to enable content sharing even outside the house.

The authentication server verifies a user account in response to the user s login via the electronic device and transmits the user account information to the electronic device to register the personal cloud apparatus to the registration server .

The open cloud server backs up the contents stored at the personal cloud apparatus and stores the same.

The registration server registers the plurality of electronic devices and the personal cloud apparatus based on the user account. By way of example the registration server may register the first electronic device and the personal cloud apparatus based on a user account A samsung.com and register the second electronic device and the personal cloud apparatus based on a user account B samsung.com. The registration server may be referred to as a user portal server as this can be registered based on the user account.

The registration server may generate a user account list based on the user accounts which may include at least one of type peer ID IP address and the like of the electronic device .

The network server relays the communication between the personal cloud apparatus and the external network based on the peer ID and domain information generated at the registration server .

Accordingly the user is able to register the personal cloud apparatus to the registration server using the electronic device via the personal cloud system and download or upload the contents using the personal cloud apparatus inside and outside the house.

Meanwhile the plurality of electronic devices may be implemented as different servers but the invention is not so limited. In another embodiment the plurality of electronic devices may be implemented as at least one server rather than four servers.

A method for registering the personal cloud apparatus to the registration server according to an embodiment will be explained below with reference to .

Referring to at operation S the electronic device determines whether an application is executed. The application may be an application for content sharing by the electronic device using the personal cloud apparatus .

At operation S Y when determining that the application is executed the electronic device performs pairing with the personal cloud apparatus at operation S. The electronic device may perform pairing with the personal cloud apparatus via various communication interfaces such as for example a Bluetooth interface a WiFi interface a Zigbee interface and the like. A method for performing pairing with a personal cloud apparatus using various communication interfaces will be explained below with reference to .

At operation S the electronic device acquires access point information and transmits the same to the personal cloud apparatus . For example the electronic device may receive information of the home AP currently connected to the electronic device and transmit the information of the home AP to the home AP so that the personal cloud apparatus connects to the home AP .

At operation S the electronic device registers the personal cloud apparatus to the registration server . For example the electronic device may register the personal cloud apparatus to the registration server based on the user account for content sharing inside or outside the house using the personal cloud apparatus . A method of an electronic device registering a personal cloud apparatus to a registration server will be explained below with reference to .

As explained above the user can share the contents using the personal cloud apparatus inside or outside the house by registering the personal cloud apparatus to the registration server with use of the electronic device .

Referring to at operation S the electronic device enters NFC mode. For example the electronic device enters NFC mode in response to a user s manipulation e.g. selecting of an icon to enter NFC mode .

At operation S the electronic device tags the NFC module to the personal cloud apparatus . The electronic device determines whether the NFC module is tagged or not by determining the presence or absence of the personal cloud apparatus within a threshold distance. When the personal cloud apparatus is within the threshold distance to the electronic device the electronic device may determine that the NFC module is tagged to the personal cloud apparatus .

When the electronic device is NFC tagged to the personal cloud apparatus the personal cloud apparatus may transmit the application download information to the electronic device at operation S. The application download information may include at least one of an application name a version a download Uniform Resource Locator URL and the like.

At operation S the electronic device determines whether the received application download information refers to a previously installed application.

At operation S Y when determining that the previously installed application is referred the electronic device loads the previously installed application and executes the same at operation S. The electronic device may display an application loading screen such as the one illustrated in on a display screen.

At operation S N when determining that the previously installed application is not referred the electronic device downloads an application based on the application download information at operation S. For example the electronic device may access an application store based on the URL of the application store from which the application can be downloaded and download the latest version of the file of the corresponding application.

At operation S the electronic device installs the downloaded application and at operation S loads the installed application and executes the same. The electronic device may display an application loading screen such as the one illustrated in on a display screen.

At operation S the electronic device determines whether the login was done with the user account. At operation S N when the login was not done with a specific user account the electronic device performs a login operation according to user input at operation S. That is when the login was not done with a specific user account the electronic device may display a login page and log in with a specific user account through the login page. The electronic device may perform a login operation to thus transmit information about the user account e.g. user account ID and password to the authentication server .

At operation S the electronic device searches available communication interfaces. The available communication interface may include at least one of the Bluetooth interface the WiFi interface the Zigbee interface and the like.

At operation S the electronic device searches for personal cloud apparatus using the available communication interface. The electronic device may search for the personal cloud apparatus in different manners depending on the types of the available communication interfaces. For example when the available communication interface is Bluetooth interface the electronic device may search for the personal cloud apparatus through a discovery operation. On the other hand while when the available communication interface is the WiFi interface the electronic device may receive Service Set IDentifier SSID information broadcast from the personal cloud apparatus and search the personal cloud apparatus .

At operation S the electronic device selects the searched personal cloud apparatus . When the electronic device selects a plurality of personal cloud apparatuses the electronic device may select one from among these personal cloud apparatuses in accordance with a user input. For example the electronic device may display a User Interface UI on a display screen through which the searched personal cloud apparatuses can be selected. For example referring to the electronic device may display a UI including the plurality of searched personal cloud apparatuses . In response to a user command to select one from among the plurality of personal cloud apparatuses included in the UI the electronic device may select a personal cloud apparatus to which the user command refers.

At operation S the electronic device transmits a pairing request signal to the selected personal cloud apparatus . The electronic device may display an instruction to select a button provided on the personal cloud apparatus as the one illustrated in to increase security on the connection between the electronic device and the personal cloud apparatus .

At operation S the personal cloud apparatus transmits a pairing response signal in response to the pairing request signal. The personal cloud apparatus may transmit a pairing response signal upon selecting of a button.

At operation S the electronic device acquires information about the home AP which is currently connected. For example the electronic device may receive access point information e.g. SSID and password of the home AP from the home AP .

At operation S the electronic device transmits the information about the home AP to the personal cloud apparatus . The electronic device may automatically transmit the home AP information to the personal cloud apparatus but the invention is not so limited. According to another embodiment the electronic device may transmit the information about the home AP to the personal cloud apparatus in response to a user command. For example referring to the UI illustrated in when a password is inputted and then a Send button is selected the electronic device may transmit the information about the home AP to the personal cloud apparatus .

At operation S the personal cloud apparatus establishes communication to the home AP using the access point information of the home AP as received.

At operation S the personal cloud apparatus transmits the information on the personal cloud apparatus to the electronic device . The information on the personal cloud apparatus may be MAC address information of the personal cloud apparatus .

After that the electronic device may provide the UI such as the one illustrated in while registering the personal cloud apparatus to the registration server .

Accordingly the electronic device may perform pairing with the personal cloud apparatus in the manner explained above. Further the personal cloud apparatus may access the home AP to connect to an external network.

A method of an electronic device for pairing with a personal cloud apparatus and of a personal cloud apparatus for accessing the home AP depending on the types of communication interfaces will be explained below with reference to .

Referring to at operation S the personal cloud apparatus enters an AP mode in response to a user input. For example the personal cloud apparatus may enter the AP mode in response to a selection made on a button provided on the personal cloud apparatus .

At operation S the personal cloud apparatus broadcasts an SSID so that electronic device performs a search through the WiFi interface. The broadcast SSID may be unique number of the personal cloud apparatus . For example the broadcast SSID may be SPC 80C78LS4P by combining SPC which stands for the personal cloud apparatus and 80C78LS4P which stands for the serial number of the personal cloud apparatus .

At operation S the electronic device executes an application in response to a user input. Referring to the electronic device may download an application in an NFC tagging operation and execute the downloaded application.

At operation S the electronic device searches for the personal cloud apparatus . For example the electronic device may search for the personal cloud apparatus by checking the SSID broadcast from the personal cloud apparatus .

At operation S the electronic device generates a password using the received SSID and the MAC address of the personal cloud apparatus . For example the electronic device may obtain a hash value by applying a hash algorithm such as SHA 1 with the received SSID and MAC address of the personal cloud apparatus and uses the obtained hash value as a password. Accordingly the data transmitted between the personal cloud apparatus and the electronic device can be safeguarded and the electronic device can automatically generate the password to access the personal cloud apparatus without requiring a prestored password.

Since the personal cloud apparatus operates in AP mode at operation S the electronic device disconnects the home AP to connect to the personal cloud apparatus .

At operation S the electronic device transmits the information about the home AP connected so far to the personal cloud apparatus .

At operation S the personal cloud apparatus performs connection with the home AP based on the received information about the home AP . At operation S the electronic device again performs connection to the home AP .

To register the personal cloud apparatus to the registration server at operation S the personal cloud apparatus sends the information about the personal cloud apparatus e.g. MAC address device ID etc. to the electronic device .

When the information about the home AP is transmitted to the personal cloud apparatus via the WiFi interface in the case of an application it is possible to store unique data information such as a secret code of the application that is stored at the time of developing. The electronic device may be so designed as to acquire the information about the home AP using the application secret code information as a key value via a specific software interface e.g. a Get WiFi Info function on the Supplicant Config. Accordingly a security problem such as exposure of a password in the acquisition process of the information about home AP is prevented.

Referring to at operation S the electronic device executes an application. As explained above with reference to the electronic device may download an application with an NFC tagging operation and execute the downloaded application.

At operation S the electronic device performs a Bluetooth discovery operation. That is the electronic device may search for the personal cloud apparatuses in the neighborhood by transmitting a Bluetooth discovery request signal.

When the discovery request signal is transmitted at operation S the personal cloud apparatus transmits a Bluetooth MAC address to the electronic device in response to the discovery request signal.

At operation S the electronic device requests the personal cloud apparatus for pairing and the personal cloud apparatus confirms the request for pairing.

At operation S the personal cloud apparatus sets RFCOMM channel on the Bluetooth interface standard to perform communication with the electronic device . The personal cloud apparatus stands by for a request for connection from the electronic device .

At operation S the electronic device sets the same RFCOMM channel as the RFCOMM channel set by the personal cloud apparatus and at operation S requests the personal cloud apparatus for connection.

At operation S the personal cloud apparatus transmits a response signal in response to the request for connection. Accordingly the pairing between the electronic device and the personal cloud apparatus is completed.

At operation S the electronic device transmits the information about the currently connected home AP to the personal cloud apparatus . The electronic device may encrypt the information about the home AP before sending the same. That is to ensure security of the home AP information e.g. SSID and password of the home AP the electronic device may encrypt the information of the home AP by applying an encryption algorithm e.g. AES 128 before transmitting the same. The symmetric key used in the encryption and decryption between the electronic device and the personal cloud apparatus may use unique information e.g. application ID hash of the application.

At operation S when the home AP information is transmitted the personal cloud apparatus performs a connecting operation to the home AP . The personal cloud apparatus may particularly decrypt the encrypted information of the home AP and perform a connecting operation to the home AP based on the decrypted home AP information.

At operation S the personal cloud apparatus may transmit the information of the personal cloud apparatus to the electronic device to register the personal cloud apparatus to the registration server .

Referring to at operation S the electronic device executes an application. As explained above with reference to the electronic device may download an application with an NFC tagging operation and execute the downloaded application.

At operation S the electronic device may transmit a discovery request signal. The electronic device may periodically transmit a discovery request signal.

At operation S the personal cloud apparatus receives a pairing request command. The pairing request command may be a selecting of a button provided on the personal cloud apparatus .

At operation S when the electronic device transmits a discovery request signal the personal cloud apparatus transmits a discovery response signal at operation S in response to the discovery request signal.

When the response signal is received the electronic device transmits a pairing request signal at operation S. When the pairing request signal is transmitted at operation S the personal cloud apparatus determines whether to allow pairing and at operation S transmits a pairing response signal in response to the pairing request signal.

At operation S when the pairing response signal is received the electronic device pairs with the personal cloud apparatus .

At operation S when the electronic device and the personal cloud apparatus are paired with each other the electronic device transmits the information of the home AP .

At operation S the personal cloud apparatus performs a connecting operation to the home AP based on the received information about the home AP .

At operation S the personal cloud apparatus transmits information about personal cloud apparatus to register the personal cloud apparatus to the registration server .

As explained above with reference to the electronic device may perform pairing with the personal cloud apparatus via various communication interfaces and the personal cloud apparatus may connect to the home AP using the information of the home AP as transmitted from the electronic device .

Referring to the electronic device logs in to an authentication server with a specific user account at operation S. The user account may be email information e.g. A samsung.com used by a user.

At operation S the personal cloud apparatus transmits MAC address information of the personal cloud apparatus to the electronic device .

Operation at S corresponds to operation S and operation S of and operation S may correspond to operation S of .

At operation S the personal cloud apparatus requests the authentication server for user account information. The personal cloud apparatus may transmit a user account ID and a password to request the user account information.

At operation S the authentication server transmits the user account information in response to the request for the user account information. The user account information may include not only the user account ID and the password but also token information and token secret information.

The electronic device transmits the received user account information and the MAC address information of the personal cloud apparatus to the registration server at operation S. The electronic device may additionally transmit information about the personal cloud apparatus e.g. device type device model name etc. and information about a service type along with the user account information and the MAC address information of the personal cloud apparatus .

The registration server registers the personal cloud apparatus at operation S. The registration server determines whether the personal cloud apparatus is registered on the registration server based on the MAC address information the unique information of the personal cloud apparatus . When the personal cloud apparatus is not registered the registration server registers the personal cloud apparatus under the log in user account.

At operation S the registration server generates peer ID so that the personal cloud apparatus can connect to the network server and transmits the same to the network server . The peer ID may be generated using the MAC address information which is the unique information of the personal cloud apparatus . That is the peer ID may correspond to the MAC address information of the personal cloud apparatus .

At operation S the network server transmits a response signal in response to the peer ID information as transmitted.

At operation S the registration server transmits the domain information and peer ID information of the network server to the electronic device . The domain information of the network server is the domain information to which the personal cloud apparatus can connect.

At the electronic device transmits the domain information of the network server and the peer ID information as received to the personal cloud apparatus and at operation S the personal cloud apparatus performs a connecting operation to the network server based on the domain information of the network server and the peer ID information as received.

As a result of the operation explained above with reference to the user is able to register the personal cloud apparatus to the registration server using the electronic device . Further since the personal cloud apparatus is connected to the network server the user is also able to share the content not only inside the house but also outside the house.

The user can particularly register the personal cloud apparatus to the registration server in response to a simple selecting of the personal cloud apparatus and a pressing motion on a button of the personal cloud apparatus when a plurality of personal cloud apparatuses are searched in response to an input to execute an application. That is user convenience is greatly increased since the user is able to register the personal cloud apparatus to the registration server by simply selecting an icon or a button without having to go through an initial network setup operation.

In one embodiment the registration server may register the personal cloud apparatus and the electronic device based on the user account. That is by registering the personal cloud apparatus using a plurality of user accounts a plurality of users can share the same personal cloud apparatus .

As explained above with reference to when one user registers the personal cloud apparatus with a specific user account an additional user may register the personal cloud apparatus with another user account in the manners explained above with reference to .

However the registration server may generate a user account list and register the personal cloud apparatus and the electronic device based on the user accounts when registering the personal cloud apparatus . That is the registration server may divide and manage the personal cloud apparatuses and electronic devices based on the user accounts. The method of the registration server for registering personal cloud apparatus according to user accounts will be explained below with reference to .

Referring to the registration server receives user account information from the electronic device at operation S. Operation S of may correspond to operation S of .

At operation S the registration server determines whether the user account is previously registered. That is the registration server may determine whether the user account logging in the authentication server is previously registered.

At operation S Y when the user account is previously registered the registration server registers the personal cloud apparatus on an existing user account information list at operation S.

However at operation S N when the user account is not previously registered at operation S the registration server generates a user account list and at operation S registers the personal cloud apparatus on the generated user account list.

Referring to the user account A may have user ID acklqczh5b while the user account B may have user ID gulnoevz0p . As illustrated in since the same personal cloud apparatus is registered the personal cloud apparatus has the same MAC address information e.g. MAC 00000000001 although the user accounts are different.

Referring to the personal cloud apparatus may keep two network server connection modules to keep both a user account using a first electronic device and a user account using a second electronic device at the same time.

The peer ID for the personal cloud apparatus to connect to the network server may be generated based on the MAC address information of the personal cloud apparatus irrespective of the user account.

For example referring to the first electronic device of the user account B as registered on the registration server may have user ID gulnoevz0p and peer ID IMEI 333322222111111 and the personal cloud apparatus of the user account B may have user ID gulnoevz0p and peer ID MAC 000000010203000. Further the second electronic device of the user account A as registered on the registration server may have user ID acklqczh5b and peer ID IMEI 111111222223333 and the personal cloud apparatus of the user account A may have user ID acklqczh5b and peer ID MAC 000000010203000.

That is as illustrated in with the same personal cloud apparatus even with different registered user accounts or user IDs are given the same peer ID. As a result a plurality of users can use the same personal cloud apparatus using different accounts.

Referring to the personal cloud apparatus registered under different user accounts stores the same peer ID information MAC 000000010203000 and local IP information 203.241.176.200 in the user account lists of the user account A and user account B.

Accordingly the plurality of electronic devices may connect to the personal cloud apparatus using the peer information of the personal cloud apparatus as stored in the registration server .

As explained above with reference to as the electronic device and the personal cloud apparatus are grouped based on the user accounts and the peer ID is generated based on the MAC address information of the personal cloud apparatus a plurality of users can share the same personal cloud apparatus .

The constitutions of an electronic device and a personal cloud apparatus will now be explained below with reference to .

Referring to the electronic device may include a communicator a storage a display a user input and a controller . The electronic device according to an embodiment may be able to play back various contents and may be implemented as a smart phone a tablet PC a smart TV and the like.

The electronic device of is equipped with elements to perform personal cloud service functions according to one example. Accordingly the elements illustrated in may be partially removed or altered or other elements may be added depending on embodiments.

The communicator performs communication with the personal cloud apparatus the home AP and the external servers . The communicator may be implemented as at least one of the WiFi interface the Bluetooth interface the Zigbee interface and the like to perform communication with the personal cloud apparatus . Further the communicator may use wireless communication to perform communication with an external server outside the house and the wireless communication may use a communication specification such as IEEE Zigbee 3rd Generation 3G 3rd Generation Partnership Project 3GPP Long Term Evolution LTE and the like.

The storage stores various data and software modules to control the electronic device . The storage may particularly include a plurality of software modules and as the ones illustrated in to register the personal cloud apparatus to the registration server and share various contents using the personal cloud apparatus .

The display outputs image content under control of the controller . For example the display may display photo content video content and the like.

The display may particularly display a UI to select one from among a plurality of searched personal cloud apparatuses when the plurality of personal cloud apparatuses are searched.

The user input may receive a user command to control the electronic device . The user input may particularly receive a user command to execute an application to register the personal cloud apparatus to the registration server and when a plurality of personal cloud apparatuses are searched receive a user command to select one from among the searched plurality of personal cloud apparatuses .

Meanwhile the user input may be implemented in the form of a touch screen but is not limited thereto. Accordingly the user input may be implemented as a mouse a pointing device a motion input a button or many other input devices.

The controller controls operations of the electronic device according to the user command as inputted through the user input . The controller may particularly perform a pairing operation with the personal cloud apparatus and acquire information about an access point of the home AP to connect the personal cloud apparatus to the network and control the communicator to transmit the acquired information to the personal cloud apparatus when an application is executed. When the personal cloud apparatus is connected to the network via the home AP the controller registers the personal cloud apparatus to the registration server .

That is the controller causes the electronic device to enter NFC mode in response to a user command. When the electronic device is within a threshold distance to the personal cloud apparatus i.e. when NFC tagging is performed the controller receives download information of an application downloads the application based on the download information thereof and stores the downloaded application to the storage . The controller may then perform loading and execution of the downloaded application in response to a user command.

When the application is executed the controller determines whether it is in a login state with the authentication server using a specific user account and if not may control the display to display a login page.

When determining that it is in the login state with the authentication server the controller searches for an available communication interface and performs a pairing operation with the personal cloud apparatus through one of the searched communication interfaces. The available communication interface may be one of the Bluetooth interface the WiFi interface the Zigbee interface and the like and a method for performing a pairing operation with the personal cloud apparatus via various interfaces is referred to the explanation provided above with reference to .

When the controller is paired with the personal cloud apparatus the controller controls the communicator to transmit information of the home AP e.g. SSID or password of the home AP to the personal cloud apparatus so that the personal cloud apparatus connects to the home AP .

When the personal cloud apparatus connects to the home AP the controller registers the personal cloud apparatus to the registration server .

For example the controller receives a MAC address which is the unique information of the personal cloud apparatus from the personal cloud apparatus via the communicator . When the user account is logged in to the authentication server the controller is able to receive user account information from the authentication server via the communicator . The user account information may include not only a user ID or a password but also token information and token secret information.

To register the personal cloud apparatus to the registration server the controller may transmit the user account information and the MAC address to the registration server . When the personal cloud apparatus is registered to the registration server using the user account information and the MAC address the controller receives from the registration server the domain information and the peer ID information of the network server to which the personal cloud apparatus can connect and controls the communicator to transmit the received domain information and peer ID information to the personal cloud apparatus .

The personal cloud apparatus is registered to the registration server based on the user account and when a plurality of user accounts register the same personal cloud apparatus to the registration server a plurality of electronic devices using the plurality of user accounts can share the contents via the personal cloud apparatus .

Referring to the personal cloud apparatus may include a communicator a button a storage and a controller .

The communicator may perform communication with the electronic device and the home AP . To perform communication with the electronic device and the home AP the communicator may use at least one of the NFC interface the WiFi interface the Bluetooth interface the Zigbee interface and the like.

The button may receive a user command. The button may particularly receive a user command for the pairing with the electronic device .

The storage stores various data and software modules to control the personal cloud apparatus . The storage may particularly include a plurality of software modules and as the ones illustrated in to register the personal cloud apparatus to the registration server and share various contents using the personal cloud apparatus .

The controller controls the overall operation of the personal cloud apparatus . For example when the button is selected the controller may perform pairing with the electronic device via one of the various communication interfaces. The method for performing the pairing operation using various communication interfaces is referred to in the explanation provided above with reference to and a redundant explanation will be omitted for the sake of brevity.

When paired with the electronic device the controller receives information of the home AP e.g. SSID or password of the home AP from the electronic device via the communicator and performs a connecting operation to the home AP using the received information about the home AP . To register the personal cloud apparatus to the registration server the controller may transmit MAC address information to the electronic device via the communicator .

When the personal cloud apparatus is registered to the registration server the controller connects to the network server based on the domain information and peer ID received from the electronic device so that at least one electronic device shares contents.

Referring to the personal cloud apparatus stores a media play module a media gateway module a cloud service module an easy setup module an NTS client module a contents MGT module a rest server module and storage API parser module a sync engine module a push agent module a multi account manager module a security module a DLNA module a controlee server module a FOTA agent module and a middleware module and BSP kernal boot loader module .

The middleware module and BSP kernal boot loader module boots up the system manages a file system and sets up a system firmware such as network setup or graphic setup. The security module involves content encryption decryption and setup of access to the content. The DLNA module processes a multimedia standard protocol for content sharing. The controlee server module receives a remote control command of a client. The FOTA agent module manages firmware update of the personal cloud apparatus .

The easy setup module manages a communication protocol with the electronic device to register the personal cloud apparatus to the registration server . The NTS client module manages connection to the network server based on a peer ID. The contents MGT module controls an interface with a media player for playing stored contents. The REST server module and storage API parser module receive a command transmission format such as content playback and process the same analyze the API of the message requested through the server and handle the contents and play a role of a classifier which handles the contents by classifying these into sharing and private regions. The sync engine module maintains content synchronization between the open cloud server and the client. The push agent module plays a role of notifying updates such as changes in contents changes in a user account list etc. The multi account manager module manages a plurality of user accounts.

The media play module performs a function of playing contents through an output device e.g. smart TV . The media gateway module performs a function of content hub such as music and video. The cloud service module manages setup of automatic content upload and download.

On the server s end there are an authentication server Auth. Server an NTS a registration server user portal server and an open cloud server.

The electronic device may include an auto upload module a contents viewer module a proxy server module a contents manager module an allshare play client module an easy setup solution module and an android middleware module .

The android middleware module involves system booting and file system management and sets up a system firmware such as network setup or graphic setup.

The easy setup solution module handles setup of a network such as WiFi or Bluetooth and includes a connectivity manager module which identifies a network type when connected to the personal cloud apparatus an account manager module which manages a user account to register the personal cloud apparatus and a provisioning manager module which registers the personal cloud apparatus to the registration server the authentication server and the network server .

The allshare play client module plays a role of an interface with a compatible application which can access the personal cloud apparatus .

The contents manager module includes a viewing manager module which manages playing and control of the content on the electronic device a rest handler module which remotely transmits a request for playing content of the personal cloud apparatus and a setting manager module which manages setup of automatic upload and download.

The proxy server module manages transmission of the information with the player installed on the electronic device when the content is played.

The auto upload module includes a service handler module which sets up automatic or manual upload and manages intervals of executing the same and a delta handler module which manages new information of the updated content.

Accordingly the electronic device and the personal cloud apparatus are able to share the contents stored in the personal cloud apparatus inside or outside the house using the software module as the one explained above.

A program code to execute the method for registering the personal cloud apparatus according to various embodiments may be stored in various types of recording media. For example the program code may be stored in various types of terminal readable recording media such as for example Random Access Memory RAM flash memory Read Only Memory ROM Erasable Programmable ROM EPROM Electronically Erasable and Programmable ROM EEPROM register hard disk removable disk memory card USB memory or CD ROM.

While the present disclosure has been shown and described with reference to various embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and the scope of the present disclosure as defined by the appended claims and their equivalents.

