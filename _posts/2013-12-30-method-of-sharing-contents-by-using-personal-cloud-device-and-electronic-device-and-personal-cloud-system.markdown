---

title: Method of sharing contents by using personal cloud device, and electronic device and personal cloud system
abstract: A method of sharing content by using a personal cloud device and an electronic device and a personal cloud system using the method are provided. The method includes connecting to a personal cloud device configured to share the content with another electronic device, if a new first content is added to a set first folder, determining an upload condition of the electronic device, and if the upload condition satisfies a set condition, transmitting the first content to the personal cloud device. Accordingly, a user is able to share contents between a plurality of electronic devices by using a personal cloud device in real time.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09516090&OS=09516090&RS=09516090
owner: Samsung Electronics Co., Ltd.
number: 09516090
owner_city: Suwon-si
owner_country: KR
publication_date: 20131230
---
This application claims the benefit under 35 U.S.C. 119 a of a Korean patent application filed on Jan. 4 2013 in the Korean Intellectual Property Office and assigned Serial No. 10 2013 0001250 the entire disclosure of which is hereby incorporated by reference.

The present disclosure relates to a method of sharing contents and an electronic device and a personal cloud system using the same. More particularly the present disclosure relates to a method of accessing a personal cloud device through a network in a home or through an external network to share contents and an electronic device and a personal cloud system using the same.

A cloud service has been provided to store various types of contents in a server and allows for downloading the contents from the server at any time and from anywhere by using an electronic device such as a smart phone or the like.

Among these cloud services a public cloud service of the related art includes a server having a fixed infrastructure. A client for example an electronic device accesses the server through a fixed Internet identifier for example an Internet Protocol IP address or a domain . A Network Attached Storage NAS system of the related art is a sharing storage system on a network wherein the sharing storage system uploads or downloads contents by using an electronic device to share the contents.

Since a cloud service of the related art shares a cloud server as described above a privacy issue occurs. For example a plurality of electronic devices for example a smart phone a smart TV a tablet Personal Computer PC and the like may be used in a home and a need may exist for sharing contents between family members.

Therefore a need exists for a method of sharing contents between a plurality of electronic devices by using a personal cloud device installed in a home and an electronic device and a personal cloud system using the same.

The above information is presented as background information only to assist with an understanding of the present disclosure. No determination has been made and no assertion is made as to whether any of the above might be applicable as prior art with regard to the present disclosure.

Aspects of the present disclosure are to address at least the above mentioned problems and or disadvantages and to provide at least the advantages described below. Accordingly an aspect of the present disclosure is to provide a method of sharing contents between a plurality of electronic devices by using a personal cloud device installed in a home and an electronic device and a personal cloud system using the same.

Another aspect of the present disclosure is to provide a user authentication method of providing a secure area in a personal cloud device to allow only a certified user to use contents of the secure area.

In accordance with an aspect of the present disclosure a method of sharing content of an electronic device is provided. The method includes connecting to a personal cloud device configured to share the content with another electronic device if a new first content is added to a set first folder determining an upload condition of the electronic device and if the upload condition satisfies a set condition transmitting the first content to the personal cloud device.

The upload condition may include at least one of a status of a network connected between the electronic device and the personal cloud and battery information of the electronic device.

If the electronic device and the personal cloud device are connected to each other through a set network interface and a residual amount of a battery of the electronic device is higher than or equal to a set value the first content may be transmitted to the personal cloud device.

If the first content is transmitted the personal cloud device may store the first content in a set folder and update a DataBase DB configured to manage contents.

The method may further include determining a download condition of the electronic device if the download condition of the electronic device satisfies a set condition periodically requesting update information of the DB from the personal cloud device if the update information exists in the DB downloading an updated second content from the personal cloud device and storing the second content in a second folder and wherein the DB is configured to manage contents of the personal cloud device.

The download condition may include at least one of a status of a network connected between the electronic device and the personal cloud device battery information of the electronic device and memory information of the electronic device.

Content information and a time stamp that are recorded in the DB of the personal cloud device and lastly downloaded by the electronic device may be determined to request updated content information from the personal cloud device.

The method may further include if the second content is completely downloaded transmitting a download result to the personal cloud device wherein the personal cloud device updates content information and a time stamp lastly updated by the electronic device based on the download result.

The method may further include if the first content stored in the first folder is revised to generate a third content determining an upload condition of the electronic device and if the upload condition satisfies a set condition transmitting the third content to the personal cloud device wherein the personal cloud device stores the first and second contents together.

The method may further include if a fourth content generated by revising the second content exists in the DB of the personal cloud device downloading the fourth content from the personal cloud device and storing the downloaded fourth content and the second content together in the second folder.

If an external device is connected to the personal cloud device through a wire and content stored in the external device is uploaded into the personal cloud device the personal cloud device may update the DB of the personal cloud device and the electronic device may download the content stored in the external device from the personal cloud device.

If an external device is connected to the personal cloud device through a wire and a new sixth content is overwritten on a fifth content stored in the personal cloud device through the external device the personal cloud device stores the sixth content and a time stamp when the sixth content is overwritten in the DB and the electronic device determines the time stamp to download the sixth content in order to store the sixth content and the fifth content together.

In accordance with another aspect of the present disclosure an electronic device is provided. The electronic device includes a communicator configured to communicate with a personal cloud device configured to share contents with another device a storage unit configured to store the contents and a controller configured to control the communicator to determine an upload condition of the electronic device if a new first content is added to a set first folder of the storage unit and to transmit the first content to the personal cloud device if the upload condition satisfies a set condition.

The upload condition may include at least one of a status of a network connected between the electronic device and the personal cloud and battery information of the electronic device.

If the electronic device and the personal cloud device are connected to each other through a set network interface and a residual amount of a battery of the electronic device is higher than or equal to a set value the controller may control the communicator to transmit the first content to the personal cloud device.

If the first content is transmitted the personal cloud device may store the first content in a set folder and update a DB configured to manage contents.

The controller may determine a download condition of the electronic device periodically request update information of the DB from the personal cloud device if the download condition of the electronic device satisfies a set condition control the communicator to download an updated second content from the personal cloud device if the update information exists in the DB and store the second content in a second folder and wherein the DB is configured to manage contents of the personal cloud device.

The download condition may include at least one of a status of a network connected between the electronic device and the personal cloud device battery information of the electronic device and memory information of the electronic device.

The controller may control the communicator to determine content information and a time stamp that are recorded in the DB of the personal cloud device and lastly downloaded by the electronic device to request updated content information from the personal cloud device.

If the second content is completely downloaded the controller may control the communicator to transmit a download result to the personal cloud device wherein the personal cloud device updates content information and a time stamp lastly downloaded by the electronic device based on the download result.

If the first content stored in the first folder is revised to generate a third content the controller may determine an upload condition of the electronic device and if the upload condition satisfies a set condition control the communicator to transmit the third content to the personal cloud device wherein the personal cloud device stores the first and second contents together.

If a fourth content generated by revising the second content exists in the DB of the personal cloud device the controller may control the communicator to download the fourth content from the personal cloud device and control the storage unit to store the downloaded fourth content and the second content together in the second folder.

If an external device is connected to the personal cloud device through a wire and content stored in the external device is uploaded into the personal cloud device the personal cloud device may update the DB of the personal cloud device and the controller may control the communicator to download the content stored in the external device from the personal cloud device.

If an external device is connected to the personal cloud device through a wire and a new sixth content is overwritten on a fifth content stored in the personal cloud device through the external device the personal cloud device may store the sixth content and a time stamp when the sixth content is overwritten in the DB and the controller may control the communicator to determine the time stamp in order to download the sixth content and control the storage unit to store the sixth content and the fifth content together.

In accordance with another aspect of the present disclosure a method of sharing content in a personal cloud system comprising a first electronic device a second electronic device and a personal cloud device is provided. The method includes connecting between the first electronic device the second electronic device and the personal cloud device if a new first content is added to a set first folder of the first electronic device determining an upload condition of the first electronic device through the first electronic device if the upload condition satisfies a set condition transmitting the first content from the first electronic device to the personal cloud device storing the first content in the personal cloud device and updating information of a DB determining update information of the DB of the personal cloud device through the second electronic device to download the first content from the personal cloud device and storing the first content in a set second folder of the second electronic device.

In accordance with another aspect of the present disclosure a method of authenticating a user between an electronic device and a personal cloud device is provided. The method includes inputting a password into the electronic device encoding the password by using a public key in the electronic device transmitting the encoded password from the electronic device to the personal cloud device verifying the encoded password by using a private key in the personal cloud device if the encoded password is verified generating and storing a session key for a user authentication in the personal cloud device encoding the session key by using the private key in the personal cloud device transmitting the encoded session key from the personal cloud device to the electronic device and decoding the encoded session key by using the private key in the electronic device.

Other aspects advantages and salient features of the disclosure will become apparent to those skilled in the art from the following detailed description which taken in conjunction with the annexed drawings discloses various embodiments of the present disclosure.

The following description with reference to the accompanying drawings is provided to assist in a comprehensive understanding of various embodiments of the present disclosure as defined by the claims and their equivalents. It includes various specific details to assist in that understanding but these are to be regarded as merely exemplary. Accordingly those of ordinary skill in the art will recognize that various changes and modifications of the various embodiments described herein can be made without departing from the scope and spirit of the present disclosure. In addition descriptions of well known functions or constructions may be omitted for clarity and conciseness.

The terms and words used in the following description and claims are not limited to the bibliographical meanings but are merely used by the inventor to enable a clear and consistent understanding of the present disclosure. Accordingly it should be apparent to those skilled in the art that the following description of various embodiments of the present disclosure is provided for illustration purpose only and not for the purpose of limiting the present disclosure as defined by the appended claims and their equivalents.

It is to be understood that the singular forms a an and the include plural referents unless the context clearly dictates otherwise. Thus for example reference to a component surface includes reference to one or more of such surfaces.

By the term substantially it is meant that the recited characteristic parameter or value need not be achieved exactly but that deviations or variations including for example tolerances measurement error measurement accuracy limitations and other factors known to those of skill in the art may occur in amounts that do not preclude the effect the characteristic was intended to provide.

Referring to a personal cloud system includes a plurality of electronic devices and a personal cloud device a home Access Point AP a public network an authentication server a public cloud server a registration server and a network server .

The plurality of electronic devices and upload or download various types of contents by using the personal cloud device . More particularly the plurality of electronic devices and may directly communicate with the personal cloud device in a home or may communicate with the personal cloud device by using the public network and the home AP from the outside. Therefore the plurality of electronic devices and may upload or download contents for example photos music videos and the like by using the personal cloud device in the home or from the outside.

Here the plurality of electronic devices and may be realized as various types of electronic devices such as smart phones tablet Personal Computers PCs smart TVs or the like.

The personal cloud device is installed in the home or an office to store contents so that the plurality of electronic devices and area able to share the contents. Here the personal cloud device may directly communicate with any of the electronic devices and hereinafter commonly referred to as an electronic device to upload or download contents but this is only an embodiment of the present disclosure. Therefore the personal cloud device may communicate with the electronic device through the home AP and the public network .

More particularly the personal cloud device is registered in the registration server based on a user account. Therefore an arbitrary user may log in to the personal cloud device through a registered user account to share contents stored in the personal cloud device from the outside by using the electronic device .

In addition the personal cloud device may set a normal area from which a plurality of users freely upload or download contents and a secure area that only a particular user accesses. More particularly the personal cloud device may allow only a user who has undergone a user authentication process to access contents stored in the secure area. The user authentication process of the personal cloud device will be described later with reference to .

The home AP relays a connection of the electronic device to the public network so that the electronic device and the personal cloud device share contents outside the home.

The authentication server certifies the user account through a login operation of the user that is performed through the electronic device and transmits information about the user account to the electronic device to register the personal cloud device in the registration server .

The registration server registers the plurality of electronic devices and and the personal cloud device based on the user account. For example the registration server may register the first electronic device and the personal cloud device based on user account A samsung.com and register the second electronic device and the personal cloud device based on user account B samsung.com . Here the registration server may be registered based on the user account and thus may be referred to as a user portal server. More particularly the registration server may generate a user account list based on the user account and the user account list may include at least one of types of electronic devices peer IDentifications IDs Internet Protocol IP addresses and the like.

The network server relays a communication between the personal cloud device and an external network based on the peer IDs generated by the registration server and domain information.

A user logs in to the authentication server through the personal cloud system described above by using the electronic device connects the electronic device to the personal cloud device and uploads contents to the personal cloud device or downloads contents from the personal cloud device .

The plurality of servers and may be realized as different servers but this is only an embodiment of the present disclosure. Therefore the plurality of servers and may be realized as one server.

Methods of sharing contents in the personal cloud system according to various embodiments of the present disclosure will now be described with reference to .

Referring to in operation S the electronic device performs a connection to the personal cloud device . Here if a set application is executed the electronic device may perform the connection to the personal cloud device but this is only an embodiment of the present disclosure. Therefore if the electronic device is turned on the electronic device may automatically perform the connection to the personal cloud device .

In operation S the electronic device determines whether a first content has been added to a first folder. Here if the first content is generated and a storage route of the generated first content is designated to the first folder or a first content stored in another folder is copied into the first folder the electronic device may determine that the first content has been added to the first folder.

If it is determined in operation S that the first content has been added to the first folder the electronic device determines an upload condition in operation S. Here the upload condition may include at least one of a status of a network connected between the electronic device and the personal cloud device and information about a battery of the electronic device .

In operation S the electronic device determines whether the upload condition satisfies a set condition. Here if the electronic device is connected to the personal cloud device through a set network interface for example a WiFi interface a Bluetooth interface or the like and a residual amount of the battery of the electronic device is higher than or equal to a set value for example 50 the electronic device may determine that the upload condition satisfies the set condition. Here the set condition may be changed by a user.

If it is determined in operation S that the upload condition satisfies the set condition the electronic device transmits the first content to the personal cloud device in operation S. If the first content is transmitted the personal cloud device may store the first content in a set folder and update a DataBase DB that manages contents.

Referring to in operation S the electronic device generates a first content. Here the electronic device may generate a new picture or video content through an imaging unit not shown and generate new document data. Here the electronic device may generate the first content for example A.jpg in a first folder for example a Data Center Infrastructure Management DCIM folder .

In operation S the electronic device detects that the first content has been generated in the first folder. Here the first folder refers to a folder that stores content that the electronic device is to automatically upload to the personal cloud device wherein the first folder may be designated or added by a user.

If it is detected in operation S that the first content has been generated in the first folder the electronic device determines an upload condition in operation S. More specifically the electronic device may determine whether a network interface connected to the personal cloud device is a set type for example a WiFi interface a Bluetooth interface or the like and whether a residual amount of a battery of the electronic device is higher than or equal to a set value for example 50 .

In the present embodiment the upload condition includes a type of the network interface and the residual amount of the battery but this is only an embodiment of the present disclosure. Therefore the upload condition may include other conditions for example an upload time whether a prohibition of uploading contents has been set by the user and the like .

If the first content is transmitted the personal cloud device stores the first content in operation S. Here the personal cloud device may store the first content in a set folder for example a sync folder and the like . Here the personal cloud device may store contents in different folders according to the type of electronic device. For example if a first content is transmitted from a first electronic device the personal cloud device may store the first content in a second folder for example sync A . If a second content is transmitted from a second electronic device the personal cloud device may store the second content in a third folder for example sync B .

In operation S the personal cloud device updates DB information. More specifically the personal cloud device may update information about a first content that is newly added to the DB information and a time stamp indicating a time so that another electronic device downloads the first content.

According to the methods described with reference to the electronic device may automatically upload content generated in a set folder to the personal cloud device .

Referring to in operation S the electronic device determines a download condition of the electronic device . Here the download condition may include at least one of a status of a network connected between the electronic device and the personal cloud device battery information of the electronic device and memory information of the electronic device . More particularly if a network interface connected between the electronic device and the personal cloud device is a set type for example a WiFi interface a Bluetooth interface or the like the battery information for example remaining capacity of the electronic device is higher than or equal to a set value for example 50 and the memory information for example available space of the electronic device is higher than or equal to a set value for example 100 MB the electronic device may determine that the download condition has been satisfied.

If the download condition has been satisfied the electronic device requests update information from the personal cloud device in operation S. More specifically the electronic device may determine content information and a time stamp that is recorded in a DB of the personal cloud device and lastly downloaded by the electronic device to request information about a newly generated content from the personal cloud device . Here the electronic device may periodically request the update information.

If the update information is received the personal cloud device determines the update information in operation S. More specifically the personal cloud device may determine whether the newly generated content exists based on the content information and the time stamp that is recorded in the DB and is lastly downloaded by the electronic device to determine the update information. For example the personal cloud device may determine the content information and the time stamp lastly downloaded by the electronic device to determine that a newly generated second content exists in a set folder.

If the second content is received the electronic device stores the second content in a second folder in operation S. Here the second folder is different from the first folder for example may be a download folder.

If the downloaded result is transmitted the personal cloud device updates the DB in operation S. Here the personal cloud device may update the content information and the time stamp lastly downloaded by the electronic device in the DB.

According to the above described method the electronic device may receive a newly generated content from the personal cloud device in real time.

Referring to in operation S the first electronic device revises the stored first content into a third content. More specifically the first electronic device may revise contents of the first content through a user input to generate the third content. For example if the first content for example A.doc is a document content the first electronic device may newly add contents through a user input to generate the third content for example A .doc . Here titles of the first and third contents may be the same.

In operation S the first electronic device detects the third content as a new content. In other words if the first and third contents have the same titles and at least one of contents and sizes of the first and third contents is changed the first electronic device may detect the third content as the new content.

In operation S the first electronic device determines an upload condition. More specifically the first electronic device may determine whether a network interface connected to the personal cloud device is a set type for example a WiFi interface a Bluetooth interface or the like and determine whether a residual amount of a battery of the first electronic device is higher than or equal to a set value for example 50 .

If the upload condition is satisfied the first electronic device transmits the third content to the personal cloud device in operation S.

In operation S the personal cloud device stores the third content transmitted from the first electronic device . Here the personal cloud device may change the title of the third content into a different title from the title of the first content and store the changed title of the third content in a set folder to distinguish the third content from the first content. For example the personal cloud device may change the title of the third content from A.doc to A 1 .doc and store the title of the third contents as A 1 .doc .

In operation S the personal cloud device updates DB information. More specifically the personal cloud device may update information about the third content and a time stamp indicating an upload time so that the second electronic device downloads the third content wherein the information about the third content and the time stamp are newly added to the DB information.

In operation S the second electronic device requests update information from the personal cloud device . Here the second electronic device may periodically request the update information.

If the request for the update information is received the personal cloud device determines the update information in operation S. More specifically the personal cloud device may determine whether a newly generated content exists based on content information and a time stamp lastly downloaded by the second electronic device to determine the update information. For example the personal cloud device may determine the content information and the time stamp lastly downloaded by the second electronic device to determine whether a newly generated third content exists in a set folder of the personal cloud device .

In operation S the personal cloud device transmits the third content to the second electronic device .

If the third content is received the second electronic device stores the third content in operation S. Here the second electronic device may store the third content in a download folder in which the first content has been stored.

The second electronic device transmits a download result to the personal cloud device in operation S.

If the download result is transmitted the personal cloud device updates a DB in operation S. Here the personal cloud device may update information about content for example information about the third content and information about a time stamp in the DB wherein the content and the time stamp are lastly downloaded by the second electronic device .

Through the personal cloud device as described above a user may share content with another electronic device wherein the content is generated by revising content that has been stored in the first electronic device .

Referring to in operation S the second electronic device changes a title of the stored second content. More specifically the second electronic device may change the title of the second content through a user input. For example if a title of a first content is B.jpg the second electronic device may change the title of the first content into BB.jpg through a user input.

In operation S the second electronic device detects the second content having the changed title as a new content. In other words although the first and third contents have the same contents and sizes but have changed titles the second electronic device may detect the second content having the changed title as the new content.

In operation S the second electronic device determines an upload condition. More specifically the second electronic device may determine whether a network interface connected to the personal cloud device is a set type for example a WiFi interface a Bluetooth interface or the like and determine whether a residual amount of the battery of the second electronic device is higher than or equal to a set value for example 50 .

If the upload condition is satisfied the second electronic device transmits the second content having the changed title to the personal cloud device in operation S.

In operation S the personal cloud device stores the second content that has the changed title and is transmitted from the second electronic device . Here the personal cloud device may store the second content BB.jpg having the changed title and the second content B.jpg in a set folder for example a sync B folder .

In operation S the personal cloud device updates DB information. More specifically the personal cloud device may update information about the second content having the changed title and a time stamp indicating an upload time so that the first electronic device downloads the second content having the changed title wherein the second content having the changed title is newly added to the DB information.

In operation S the first electronic device requests update information from the personal cloud device . Here the first electronic device may periodically request the update information.

If the request for the update information is received the personal cloud device determines the update information in operation S. More specifically the personal cloud device may determine whether a newly generated content exists based on content information and a time stamp that is recorded in a DB and is lastly downloaded by the first electronic device to determine the update information. For example the personal cloud device may determine the content information and the time stamp lastly downloaded by the first electronic device to determine whether the second content having the changed title exists in a set folder of the personal cloud device .

In operation S the personal cloud device transmits the second content having the changed title to the first electronic device .

If the second content having the changed tile is received the first electronic device stores the second content having the changed title in operation S. Here the first electronic device may store the second content having the changed title in a download folder in which the second content has been stored.

In operation S the first electronic device transmits a download result to the personal cloud device .

If the download result is transmitted the personal cloud device updates the DB in operation S. Here the personal cloud device may update information about content for example information about the second content having the changed title and information about a time stamp in the DB wherein the content and the time stamp are lastly downloaded by the first electronic device .

Through the personal cloud system as described above if the second electronic device changes a title of a stored content the user may share the content having the changed title with another electronic device.

Referring to in operation S the personal cloud device performs a wire connection to an external device . For example the personal cloud device may perform the wire connection to the external device through a Universal Serial Bus USB interface by a user. Here the external device may be a device such as a notebook PC a tablet PC or the like.

If the wire connection is performed between the personal cloud device and the external device the external device selects content that is to be uploaded in operation S. Here the external device may select the content that is to be uploaded through a user input. For example the external device may select C.mp3 as content to be uploaded through a user input. However this is only an embodiment of the present disclosure and thus the external device may select content that is stored in a set folder of the external device as content to be uploaded.

In operation S the personal cloud device stores the selected content transmitted from the external device . Here the personal cloud device may store a selected content C.mp3 having a changed title in a set folder for example a sync C folder .

In operation S the personal cloud device updates DB information. More specifically the personal cloud device may update information about the selected content and a time stamp indicating an upload time so that the electronic device downloads the selected content wherein the information about the selected content and the time stamp are newly added to the DB information.

In operation S the electronic device requests update information from the personal cloud device . Here the electronic device may periodically request the update information.

If the request for the update information is received the personal cloud device determines the update information in operation S. More specifically the personal cloud device may determine whether a newly generated content exists based on content information and a time stamp that are recorded in a DB and are lastly downloaded by the electronic device to determine the update information. For example the personal cloud device may determine the content information and the time stamp lastly downloaded by the electronic device to determine that a selected content C.mp3 exists in a set folder of the personal cloud device .

If the selected content is received the electronic device stores the selected content in operation S. Here the electronic device may store the selected content in a download folder.

If the download result is transmitted the personal cloud device updates a DB in operation S. Here the personal cloud device may update information about content and information about a time stamp in the DB wherein the content and the time stamp are lastly downloaded by the electronic device .

Through the personal cloud system as described above a user may share content stored in the external device connected to the personal cloud device through a wire with the electronic device connected to the personal cloud device .

Referring to in operation S the personal cloud device performs a wire connection to the external device . For example the personal cloud device may perform the wire connection to the external device through a USB interface by a user.

If the wire connection is performed between the personal cloud device and the external device the external device overwrites a sixth content on the fifth content in operation S. More specifically the external device may overwrite the sixth content having the same title as the fifth content stored in the personal cloud device in the personal cloud device .

In operation S the personal cloud device stores the sixth content that is overwritten on the fifth content. Here since the personal cloud device overwrites the sixth content having the same title as the fifth content on the fifth content the personal cloud device may delete only the fifth content and store only the sixth content.

In operation S the personal cloud device updates DB information. More specifically the personal cloud device may update information about the sixth content that is overwritten on the DB information and a time stamp indicating an upload time of the sixth content so that the electronic device downloads the sixth content.

In operation S the electronic device requests update information from the personal cloud device . Here the electronic device may periodically request the update information.

If the request for the update information is received the personal cloud device determines the update information in operation S. More specifically the personal cloud device may determine whether a newly generated content exists based on content information and a time stamp that are recorded in a DB and are lastly downloaded by the electronic device to determine the update information. For example the personal cloud device may determine the content information and the time stamp lastly downloaded by the electronic device to determine that the sixth content exists in a set folder of the personal cloud device .

If the sixth content is received the electronic device stores the sixth content in operation S. Here the electronic device may store the sixth content along with the fifth content in a download folder. Here the electronic device may change a title of the sixth content to distinguish the sixth content from the fifth content. For example if titles of the fifth and sixth contents are D.avi the electronic device may change the title of the sixth content into D 1 .avi .

If the download result is transmitted the personal cloud device updates the DB in operation S. Here the personal cloud device may update information about content and information about a time stamp in the DB wherein the content and the time stamp are lastly downloaded by the electronic device .

Through the personal cloud system as described above although content stored in the personal cloud device is overwritten on another content through the external device connected to the personal cloud device through a wire the user may share the overwritten content in the electronic device connected to the personal cloud device .

In the above described embodiment the electronic device automatically downloads content stored in the personal cloud device or automatically uploads content into the personal cloud device . However this is only an embodiment of the present disclosure and thus the electronic device may manually download content stored in the personal cloud device or may manually upload content into the personal cloud device . In other words the user may access the personal cloud device to select content that is to be downloaded or uploaded in order to perform downloading or uploading.

Structures of the electronic device and the personal cloud device will now be described with reference to .

Referring to the electronic device includes a communicator a storage unit a display unit a user input unit and a controller . Here the electronic device may play various types of contents and may be realized as various types of devices such as a smart phone a table PC a smart TV and the like.

In the electronic device has a personal cloud service function and synthetically includes various types of elements. Therefore according to various embodiments some of the elements of may be omitted or changed and other elements may be added.

The communicator communicates with the personal cloud device the home AP and the external servers and . More particularly the communicator may be realized as at least one of a Near Field Communication NFC interface a Wi Fi interface a Bluetooth interface a Zigbee interface and the like to communicate with the personal cloud device . In addition the communicator may wirelessly communicate with an external server. Various types of communication standards such as the Institute of Electrical and Electronics Engineers IEEE Zigbee 3rd Generation 3G 3rd Generation Partnership Project 3GPP Long Term Evolution LTE and the like may be used for the wireless communication.

The storage unit stores various types of data and software modules for controlling the electronic device . More particularly the storage unit registers the personal cloud device in the registration server and includes a plurality of software modules not shown to share various types of contents by using the personal cloud device .

The display unit outputs an image content under control of the controller . For example the display unit may display a picture content and a moving picture content.

The user input unit receives a user command for controlling the electronic device . The user input unit may be realized as a touch screen but this is only an embodiment of the present disclosure. Therefore the user input unit may be realized as various types of input devices such as a mouse a pointing device a motion input unit a button and the like.

The controller controls an overall function of the electronic device according to the user command input through the user input unit . More particularly if a new first content is added to a set first folder of the storage unit the controller determines an upload condition of the electronic device . Here the upload condition may include at least one of a status of a network connected between the electronic device and the personal cloud device and battery information of the electronic device .

If the upload condition satisfies a set condition the controller controls the communicator to transmit the first content to the personal cloud device . More specifically if the electronic device and the personal cloud device are connected to each other through a set network interface for example a WiFi interface a Bluetooth interface or the like and a residual amount of the battery of the electronic device is higher than or equal to a set value the controller may control the communicator to transmit the first content to the personal cloud device .

If the first content is transmitted the personal cloud device may store the first content in a set folder and update a DB that manages contents.

The controller determines a download condition of the electronic device to download content stored in the personal cloud device . Here the download condition may include at least one of a status of a network connected between the electronic device and the personal cloud device battery information of the electronic device and memory information of the electronic device .

If the download condition of the electronic device satisfies a set condition the controller may control the communicator to periodically request update information of the DB which manages contents of the personal cloud device from the personal cloud device. Here the controller may control the communicator to determine content information and a time stamp that are recorded in the DB of the personal cloud device and are lastly downloaded by the electronic device in order to request updated content information from the personal cloud device .

If the update information exists in the DB the controller may control the communicator to download an updated second content from the personal cloud device and store the second content in a set second folder for example a download folder of the storage unit .

If the second content is completely downloaded the controller may control the communicator to transmit a download result to the personal cloud device . Here the personal cloud device may update the content information and the time stamp lastly downloaded by the electronic device based on the download result.

If the first content stored in the first folder is revised to generate a third content the controller may determine an upload condition of the electronic device and if the upload condition satisfies a set condition the controller may control the communicator to transmit the third content to the personal cloud device .

If the second content stored in the DB of the personal cloud device is revised to generate a fourth content the controller may control the communicator to download the fourth content from the personal cloud device and control the storage unit to store the fourth content and the second content together in the second folder. Here the fourth content may be content that is generated by revising at least one of the content the size and the title of the second content.

If the personal cloud device is connected to the external device through a wire and content stored in the external device is uploaded into the personal cloud device the DB of the personal cloud device may be updated and the controller may control the communicator to download the content stored in the external device from the personal cloud device .

If the personal cloud device is connected to the external device through a wire a new sixth content is overwritten on a fifth content stored in the personal cloud device through the external device the personal cloud device may store the sixth content and a time stamp when the sixth content is overwritten in the DB and the controller may control the communicator to determine the time stamp in order to download the sixth content and may control the storage unit to store the fifth content and the sixth content together.

Referring to the personal cloud device includes a communicator a button a storage unit and a controller .

The communicator communicates with the electronic device and the home AP . Here the communicator may use at least one of an NFC communication interface a WiFi interface a Bluetooth interface a Zigbee interface and the like to communicate with the electronic device and the home AP .

The button receives a user command. More particularly the button receives a user command to perform pairing with the electronic device .

The storage unit stores various types of data and various software modules for controlling the personal cloud device . More particularly the storage unit registers the personal cloud device in the registration server and includes a plurality of software modules to share various types of contents by using the personal cloud device .

The storage unit stores a DB that manages uploading and downloading of contents to share contents between a plurality of electronic devices . More specifically the DB may store information about contents and time stamps respectively lastly downloaded by the plurality of electronic devices and store information about contents and time stamps respectively lastly uploaded by the plurality of electronic devices .

The controller controls an overall operation of the personal cloud device . More particularly if content is uploaded from the electronic device the controller stores the uploaded content in the storage unit and updates the DB of the storage unit . More specifically if content is uploaded from the electronic device the controller may update information about content and a time stamp that are recorded in the DB and are lastly uploaded by the electronic device .

If an update determination request is received from the electronic device the controller determines update information based on information stored in the DB and transmits a newly generated content to the electronic device .

If a download result is received from the electronic device the controller updates the DB. More specifically if the download result is received from the electronic device the controller updates information about content and a time stamp that are recorded in the DB and lastly downloaded by the electronic device .

Through the electronic device and the personal cloud device as described above a user may share contents with another electronic device by using the personal cloud device .

Referring to the personal cloud device stores a media play module a media gateway module a cloud service module an easy setup module a Network Tracking System NTS client module a content management module a REpresentational State Transfer REST server module and a storage Application Programming Interface API parser module a sync engine module a push agent module a multi account manager module a security module a Digital Living Network Alliance DLNA module a controlee server module a Firmware Over The Air FOTA agent module and a middleware module and a Basic Security Profile BSP Kernal Boot loader modules .

Here the middleware module and the BSP Kernal Boot loader module manage booting a system and a file system and set firmware of the system such as a network setting a graphic setting or the like. The security module sets coding decoding of content and an access authority to the content. The DLNA module processes a multimedia standard protocol for sharing contents. The controlee server module receives a remote control command of a client. The FOTA agent module manages updating of firmware of the personal cloud device .

The easy setup module manages a communication protocol with the electronic device to register the personal cloud device in the registration server . The NTS client module manages a connection to the network server based on a peer ID. The content management module controls an interface with a media player that plays a stored content. The REST server module and storage API parser module operates as a classifier that receives and processes a command transmission format such as playing of content from the client analyzes an API of a message requested through a server to handle the content shares the content and divides and handles a personal area. The sync engine module maintains content synchronization between the public cloud server and the client. The push agent module notifies updated contents such as changed contents of contents changed contents of a user account list and the like. The multi account manager module manages a plurality of user accounts.

The media play module plays content through an output device for example a smart TV . The media gateway module operates as content hub of music and images. The cloud service module manages automatic uploading and downloading setting of content.

A server includes an authentication server an NTS server a user portal server a cloud server and the like.

The electronic device includes an auto upload module a content viewer module a proxy server module a content manager module an Allshare play client module an easy setup solution module and an Android middleware module .

The Android middleware module manages booting of the system and the file system and sets firmware of the system such as a network setting a graphic setting or the like.

The easy setup solution module includes a connectivity manager module an account manager module and a provisioning manager module. The connectivity manager module sets a network such as WiFi Bluetooth or the like and identifies a type of network when being connected to the personal cloud device . The account manager module manages a user account that registers the personal cloud device . The provisioning manager module registers the personal cloud device in the registration server the authentication server and the network server .

The Allshare play client module operates as an interface with a compatible application that may access the personal cloud device .

The content manager module includes a viewing manager module a REST handler module and a setting manager module. The viewing manager module manages playing and controlling of content on the electronic device . The REST handler module remotely transmits a play request for content of the personal cloud device . The setting manage module manages setting of automatic uploading and automatic downloading.

The proxy server module manages information transmission with a player installed in the electronic device when playing the content.

The auto upload module includes a service handler module that manages cycles of setting and executing automatic or manual uploading and a Delta handler module that manages new information of an updated content.

Therefore the electronic device and the personal cloud device may share contents stored in the personal cloud device inside or outside a home by using a software module as described above.

In the above described embodiment a plurality of electronic devices automatically upload or download contents to share contents stored in the personal cloud device . However this is only an embodiment of the present disclosure and thus the personal cloud device may set a particular area of the storage unit as a secure area to provide a security function that may not be accessed by other users except an authenticated user.

More specifically the personal cloud device may provide a normal area from which a plurality of users freely upload or download contents and a secure area that may be accessed only by an authenticated user. Accordingly an arbitrary user may be prevented from accessing content stored in the secure area of the personal cloud device . In addition the personal cloud device may perform a user authentication process and an encoding process with respect to a stored content so that only an authenticated user accesses the secure area.

More particularly the personal cloud device may perform the user authentication process by using a public key and a private key. For example the personal cloud device may perform the user authentication process by using a Rivest Shamir Adleman RSA encoding technique. A method of performing a user authentication process to provide a security function of the personal cloud device to a user will now be described with reference to .

Referring to in operation S the electronic device receives a password of a secure area of the personal cloud device from a user.

In operation S the electronic device encodes the password by using a public key. Here the public key may be stored in the electronic device when installing an application.

In operation S the personal cloud device verifies the encoded password transmitted to the electronic device by using a private key. More specifically the personal cloud device may decode the encoded password by using the private key of the personal cloud device and verify whether the decoded password has been justly encoded.

If the encoded password is completely verified the personal cloud device generates and stores a session key in operation S. Here the personal cloud device may map and store corresponding user information for example an ID a password and the like with the session key.

In operation S the personal cloud device encodes the session key by using the private key. In operation S the personal cloud device transmits the encoded session key to the electronic device .

In operation S the electronic device decodes the encoded session key by using the public key to perform a user authentication process.

The user may perform the above described user authentication process to control for example play store restore and the like content stored in the secure area of the personal cloud device .

The personal cloud device may access content stored in a normal area by using only a server solution module in response to an automatic uploading downloading request for content stored in a normal area. However the personal cloud device may access content stored in the secure area through only the server solution module and an additional security module in response to an access request for the secure area. The personal cloud device may encode content to exchange data between the secure area of the storage unit the security module and the server solution module in order to input and or output content of the secure area.

According to various embodiments of the present disclosure as described above the personal cloud device may provide a secure area in which a plurality of users freely share contents and which may be accessed only by a particular user.

A program code for performing a method of registering the personal cloud device according to various embodiments of the present disclosure as described above may be stored on various types of recording media. More specifically the program code may be stored on various types of computer readable recording media such as a Random Access Memory RAM a flash memory a Read Only Memory ROM an Erasable Programmable ROM EPROM an Electronically Erasable and Programmable ROM EEPROM a Compact Disc CD ROM and the like.

While the present disclosure has been shown and described with reference to various embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present disclosure as defined by the appended claims and their equivalents.

