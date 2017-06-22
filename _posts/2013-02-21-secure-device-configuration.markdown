---

title: Secure device configuration
abstract: Described herein are systems and methods for secure configuration provisioning of network credentials to configure a device to join one or more networks. One implementation provides for distribution of network credentials to associated devices without user intervention while maintaining security and avoiding distribution of the network credentials to external devices, such as a third-party server. Devices may be associated by purchase from a common merchant, registration to a common account, and so forth.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09154483&OS=09154483&RS=09154483
owner: Amazon Technologies, Inc.
number: 09154483
owner_city: Reno
owner_country: US
publication_date: 20130221
---
An increasing number of devices are configured to connect to networks in order to exchange information. A device may join a network after being configured with network credentials. However the configuration with network credentials has traditionally involved user intervention or the storage of those network credentials outside of the network. Users may have a negative user experience in providing the network credentials to devices on the network or may be reluctant to have the network credentials stored elsewhere.

Certain implementations and embodiments will now be described more fully below with reference to the accompanying figures in which various aspects are shown. However various aspects may be implemented in many different forms and should not be construed as limited to the implementations set forth herein. Like numbers refer to like elements throughout.

A network allows two or more devices to communicate with one another and exchange information. A wide variety of devices are able to be configured to connect to one or more networks. The devices may include televisions tablet computers personal computers electronic book readers gaming consoles set top boxes media players vehicles portable media players smartphones home automation devices security systems appliances access points routers and so forth. The networks may include local area networks LANs personal area networks PANs and so forth. A LAN may use protocols compliant with at least a portion of the 802.11 standards promulgated by the Institute of Electrical and Electronic Engineers IEEE . A PAN may communicate using the Bluetooth standard as promulgated by the Bluetooth Special Interest Group.

Some networks may require the device to be configured with network credentials in order to join the network. These network credentials may include one or more of a network name a password an encryption type an encryption key and so forth. Devices which have the proper credentials may then join to the network and communicate with other devices which have joined the network. Different networks may share common physical layer implementations. For example several different 802.11 networks each with a different service set identification SSID and password may coexist in a given physical location.

At least some of the devices may be configurable to communicate with more than one network. Some networks may not use network credentials or may use network credentials which have previously been received by a particular device. For example a first device joined to a first network may also form a peer to peer network with a second device which has not yet joined the first network.

Traditionally joining a device to a network which requires network credentials has involved manual user intervention storage of the network credentials on an external device such as an authentication server and so forth. Manual intervention may result in an adverse user experience as a user may be called upon to input the network credentials a process which may be prone to human error or confusion. Storage of the network credentials on the external device may be undesirable to some network administrators. Furthermore such storage may call for enhanced security to safeguard the network credentials from compromise.

Described in this disclosure are methods and systems for secure configuration provisioning of network credentials for one or more networks to devices. Once securely provisioned the device may join one or more networks. A first device may already be joined to the one or more networks. For example the first device may have been manually configured previously or may be the initial device which establishes the network. The first device is configured to communicate with a second device which is not yet joined to the one or more networks. This communication may use an unsecured default network using previously specified credentials an alternative protocol and so forth. For example a peer to peer network may be established between the first device and the second device.

The second device requests credentials from the first device. The first device in turn communicates with an association server which determines whether the first device and the second device are associated. This association may be by purchase from a common merchant registration to a common account manual user entry and so forth. For example when the first device and the second device are purchased from a same merchant account and delivered to a same address they may be associated with one another.

The association server is configured to provide challenge data which is based on a device specific secret which is known to the second device and the association server. The association server may also be configured to cryptographically sign information received from the first device the second device the challenge data and so forth.

The challenge data is provided to the first device which in turn uses a portion of this challenge information to determine that the second device is associated with the first device and entitled to receive the network credentials. The first device may then provide the network credentials to the second device. The second device uses these network credentials to join the one or more networks.

This process allows for secure configuration provisioning without user intervention improving the user experience. For example a user purchases the second device activates the second device in the user s home and in a few moments the second device is configured and has joined the network. The process implements various cryptographic signatures a cryptographic nonce the association data and a previously known device specific secret to mitigate potential security exploits.

Furthermore using this process the network credentials remain on the first device and are not sent to an external device which is outside the network such as a server. Security of the network credentials may thus be improved by not sending the network credentials to the external device.

In situations where the automatic exchange of network credentials described above is unavailable techniques are also discussed which involve minimal user intervention and avoid presenting the user with complicated network credential information. In one implementation a first device receives a presented code which is manually input. The presented code was originally presented by the second device which seeks the network credentials. The first device generates a zero knowledge proof based on the entered code. The second device receives this zero knowledge proof to determine if the entered code corresponds to the presented code. The manual input minimizes or eliminates the likelihood of electronic eavesdropping while the zero knowledge proof allows verification without the need to send the actual entered code over what may be an insecure connection. Furthermore use of this technique reduces or eliminates the possibility of another device spoofing or maliciously causing the second device to join an unintended network. Once the second device has determined the correspondence between the presented code and the entered code network credentials which have been sent to the second device may then be used to configure and join the one or more networks. Other implementations using manual input are also discussed.

A first device and a second device are depicted. These devices may include televisions tablet computers personal computers electronic book readers gaming consoles set top boxes media players vehicles portable media players smartphones home automation devices security systems appliances access points routers and so forth. Each of the devices may be connected to one or more networks. The networks may include a wireless local area network WLAN . The examples used herein are made with respect to a WLAN however it is understood that the techniques described may be used with other networks such as cabled local area networks LANs personal area networks PANs and so forth. The WLAN may use protocols which are compliant with at least a portion of the 802.11 standards promulgated by the Institute of Electrical and Electronic Engineers IEEE . In one implementation the PAN may communicate using the Bluetooth standard as promulgated by the Bluetooth Special Interest Group.

The first device has been previously joined to the WLAN . For example the user may have manually entered one or more network credentials into the first device allowing the first device to join the WLAN . Because the first device has been joined to the WLAN the first device is able to use the WLAN to communicate with other devices which have joined that network such as an access point gateway router and so forth.

The WLAN is configured to connect to external devices using a wide area network WAN . For example the access point of the WLAN may be coupled to a gateway router which in turn connects to a communication interface device which connects to the WAN . The WAN may comprise the Internet a private network cellular data network and so forth. Connected to the WAN and thus accessible to the first device which is on the WLAN which connects to the WAN is an association server . The association server is configured to assist the first device and the second device in determining that an association exists between the two. The association server is discussed in more detail below.

The second device may be newly brought to an area in which the WLAN is accessible may have been previously on the WLAN but has been reset to default settings or otherwise lacks the network credentials to successfully join the WLAN . For example the user may have recently purchased the second device and brought it home where the WLAN is available.

Because the second device lacks the network credentials to join the WLAN communication with the first device using the WLAN is not available. However the first device and the second device may be able to communicate with one another using a previously defined set of network credentials using no network credentials at all or by using communications protocols and channels which differ from that used by the WLAN . For example the first device and the second device may be able to communicate directly with one another without an intermediary access point using the Wi Fi Direct as promulgated by the Wi Fi Alliance. In another implementation the first device and the second device may both be able to communicate with the other using optical transceivers Bluetooth and so forth.

The first device and the second device are configured to become aware of one another. In one implementation the first device may discover the presence of the second device . For example the first device may receive a transmission by the second device . In another implementation the second device may discover the presence of the first device . For example the second device may receive a transmission by the first device . In yet another implementation a third device may make the determination that the second device is within communication range of the first device . For example a geolocation server may provide data indicating that both the first device and the second device are likely to be within range of the same WLAN . The discovery may involve the use of data broadcasts previously stored information manual input and so forth. For example the second device may have been configured such that the WLAN may be available based at least in part on a delivery address associated with physical shipment of the second device to the user .

The second device provides a credential request to the first device using a connection other than the WLAN . For example the second device may use Wi Fi Direct to send the credential request . In some implementations the second device may receive information from the first device which when processed by the second device initiates the credential request . For example the first device may send a packet indicating the presence of the first device and the WLAN . This packet is received by the second device which responds by sending the credential request .

The credential request may include a second device identifier and a cryptographic nonce . The second device identifier is used to distinguish the second device from other devices. The second device identifier may be based at least in part on a model number of the second device serial number of the second device and so forth.

The cryptographic nonce comprises an arbitrary value such as a number or a string. The arbitrary value is not used to encode other information. The cryptographic nonce is not reused. The cryptographic nonce may be configured to be valid for a limited period of time or for a limited scope of use. The cryptographic nonce may be generated by the second device using a random or pseudo random number generator. As described below the cryptographic nonce is used at least in part so the second device can confirm that information later received actually corresponds to the credential request .

The first device receives the credential request . Based at least in part on the credential request the first device generates and sends a verification request to the association server . The verification request may include a first device identifier the second device identifier the cryptographic nonce and a network credential hash . The first device identifier as above with the second device identifier distinguishes the first device from other devices. The first device has the network credentials for joining the WLAN . The first device generates the network credential hash based at least in part on the network credentials. By sending the network credential hash in the verification request rather than the network credentials the external device such as the association server never learns the network credentials. Thus use of the network credential hash may improve security of the WLAN .

The association server accepts the verification request and accesses account data to determine if the first device and the second device are associated. This association may be that the first device and the second device have been purchased from a common merchant are registered to a common account were shipped to the same delivery address have been paid for with a common method of payment previous data which was manually entered and so forth. For example when the first device and the second device are purchased from a same merchant account and delivered to a same address they may be associated with one another.

The association server is also configured to maintain or have access to device specific secrets . These device specific secrets comprise data which is known to the second device and the association server . In some implementations the device specific secrets may include data which is stored on the second device during manufacture. In some implementations the secret used may be associated with a group of devices. For example a group specific secret may be associated with devices which are delivered to a school.

The association server generates verification data which is then sent to the first device . The association server may be configured to cryptographically sign the verification data or pieces of the verification data . For example the cryptographic nonce which was received originally from the second device and relayed by the first device to the association server may be signed to form a signed cryptographic nonce . The network credential hash may also be cryptographically signed to form a signed network credential hash .

The association server is configured to generate a challenge. The challenge is based at least in part on the device specific secret and thus is specific to the second device . This challenge is cryptographically signed to form a signed challenge . The association server is also configured to generate an expected challenge response to the signed challenge . In some implementations the expected challenge response may be cryptographically signed as well.

The verification data is provided to the first device . For example the association server may send the verification data using the WAN and the WLAN . The first device may be configured to verify the cryptographic signatures of at least some of the verification data . For example the first device may use the signature to confirm that the association server was the source of the signed challenge .

A portion of the verification data may be designated as challenge data . The challenge data may include the signed cryptographic nonce the signed network credential hash and the signed challenge . The first device sends the challenge data to the second device . The second device receives and verifies the challenge data . The verification may include confirming that the signed cryptographic nonce corresponds to the cryptographic nonce originally generated by the second device and that the nonce is still valid. The verification may also include verification of the signature of the signed cryptographic nonce allowing the second device to verify that the same cryptographic nonce was processed by the association server .

Once verified the second device uses the signed challenge to generate a challenge response to the signed challenge . In some implementations the generation of the challenge response may be based at least in part on the device specific secret which has been previously stored on the second device such as during manufacture. The second device may also determine the authenticity of the signed network credential hash by checking the cryptographic signature. The second device may then send the challenge response to the first device .

The first device receives the challenge response and verifies against the expected challenge response . This verification allows the first device to be assured that the first device and the second device are associated and that the network credentials may be appropriately provided to the second device . The first device sends network credentials to the second device . The network credentials may include data indicative of one or more of a service set identification SSID for the WLAN a password associated with the WLAN a wireless channel for the WLAN encryption used for the WLAN and so forth. The network credentials may include one or more pieces of information indicative of a network configuration stored by the first device .

The second device receives the network credentials and verifies the network credentials against the signed network credential hash . This allows the second device to confirm that the first device has provided the network credentials and that the network credential hash was cryptographically signed by the association server . With the network credentials corresponding to the signed network credential hash the second device may now be configured to join the WLAN .

Implementation of this process thus allows the second device to join the WLAN without undue or complicated configuration on the part of the user . Furthermore the network credentials remain secure within the WLAN rather than being sent to an external server.

Communications between the first device the second device the association server and so forth may be encrypted. This encryption may secure socket layers SSL transport layer security TLS and so forth. This encryption is used to mitigate eavesdropping on the communications. Without the network credentials these communications may be encrypted but do not necessarily provide authentication as to the identity of the devices involved in the communication. For example public keys may be exchanged between the devices to allow for encrypted communications.

At the user configures the first device on a first network such as the WLAN . This configuration may include manually inputting the network credentials receiving from another device such as an access point the network credentials and so forth. The WLAN illustrated here may be within a home network such as that previously configured at the user s residence with the SSID of MYHOME .

At the user brings the second device to join the first network such as the WLAN . For example the user may have physically received the second device and activated it while at the residence.

At the second device establishes a connection with the first device . This connection may result in the first device and the second device establishing a second network between the two devices. This second network may use previously defined network credentials . Or the second network may be configured such that network credentials are not used for communication. The second network may use the same communication interface as the first network or may use a different communication interface. For example the second network may also use Wi Fi but may use a different SSID no encryption and may be configured to operate on a particular group of radio frequency channels. In another example the second network may use Bluetooth to establish communication between the devices.

This connection may be configured to be encrypted even though the devices participating may be unauthenticated to one another. The newly discovered devices may exchange public keys with one another to allow for the establishment of an encrypted exchange. For example the devices may implement the transport layer security protocol.

At the first device requests from a trusted server such as the association server information to authenticate the second device . Responsive to the request at the first device proceeds to authenticate the second device . At the first device sends the network credentials to the second device . Based at least in part on the network credentials the second device configures a communication interface and joins the first network such as the WLAN .

With the first device and the second device on a common network such as the first network comprising the WLAN the connection using the second network may be discontinued. The second device may be configured to re initiate the process upon a change in geographic location changes in use time loss of connectivity with the WLAN receiving data to restart the process and so forth.

The I O interface s may couple to one or more I O devices . The I O devices may include input devices such as one or more of a camera a microphone a touch sensor a button and so forth. The I O devices may also include output devices such as one or more of a display audio speakers haptic output devices and so forth. In some embodiments the I O devices may be physically incorporated with the first device or may be externally placed.

The first device may also include one or more communication interfaces . The communication interfaces are configured to provide communications between the first device and other devices such as other media devices routers access points servers and so forth. The communication interfaces may include devices configured to couple to one or more networks including PANs LANs WLANs WANs and so forth. For example Ethernet Wi Fi Bluetooth ZigBee and so forth.

The first device may also include one or more busses or other internal communications hardware or software that allow for the transfer of data between the various modules and components of the first device .

As shown in the first device includes one or more memories . The memory comprises one or more computer readable storage media CRSM . The CRSM may be any one or more of an electronic storage medium a magnetic storage medium an optical storage medium a quantum storage medium a mechanical computer storage medium and so forth. The memory provides storage of computer readable instructions data structures program modules and other data for the operation of the first device .

The memory may include at least one operating system OS module . The OS module is configured to manage hardware resource devices such as the I O interfaces the I O devices the communication interfaces and provide various services to applications or modules executing on the processors . The OS module may also be configured to support encrypted communications such as SSL TLS or other protocols with other devices such as the second device the association server an access point and so forth.

Also stored in the memory may be one or more of the following modules. These modules may be executed as foreground applications background tasks daemons and so forth.

A user interface module is configured to provide a user interface to the user using the I O devices and to accept inputs received from the I O devices . The user interface may include one or more visual audible or haptic elements. For example the user interface may be configured to provide a graphic user interface an audible user interface and so forth.

A secure configuration provisioning module or provisioning module is also stored in the memory . The provisioning module is configured to support the processes described in this disclosure. This may include receiving the credential requests generating verification requests receiving verification data communicating with the second device coordinating the actions of other modules and so forth.

A hash module is configured to generate one or more hashes from inputs verify hashes and so forth. The hash module may be configured to generate the network credential hash based on one or more portions of the network credentials . In one implementation the network credential hash may be based on the SSID and the password of the WLAN .

A cryptographic signature module is configured to provide cryptographic signatures for files or other data. The cryptographic signature module may be configured to verify or validate cryptographic signatures.

A challenge verification module is configured to compare a challenge response with an expected challenge response to determine if a challenge has been satisfied. As described below in more detail this challenge allows the first device to be assured that the second device with which it is in communication is properly associated and entitled to receive the network credentials .

A credential management module is configured to manage network credentials which have been received provide network credentials to other devices and so forth. For example the secure configuration provisioning module may be configured to direct the credential management module to send the network credentials to the second device after receipt of a correct challenge response .

Other modules may also be present. For example a digital rights management module may provide support for presenting or processing content protected using one or more digital rights management schemes.

One or more of the modules described above may be configured to execute in one or more secure modules. The secure module may comprise dedicated memory dedicated processor or other resources configured to improve security of the modules executing therein.

The memory may also include a datastore to store information. The datastore may use a flat file database linked list tree or other data structure to store the information. In some implementations the datastore or a portion of the datastore may be distributed across one or more other devices including servers network attached storage devices and so forth.

As depicted here the datastore may store one or more of the verification requests the verification data or the network credentials . The datastore may also include encryption key s . For example where the secure communications involve the use of public key and private key cryptography the public key and the private key of the first device the public keys of the second device and the association server and so forth may be stored. Other data may also be stored. For example the other data may include user preferences configuration files and so forth.

In some implementations the first device may also store the modules and data depicted below with respect to the second device and vice versa. In this implementation the second device may later act to assist the secure configuration provisioning of another device which is seeking the network credentials . Likewise the first device which needs to acquire network credentials may send a credential request to another device.

The second device may include one or more processors configured to execute one or more stored instructions. The processors may comprise one or more cores. The second device may include one or more I O interface s to allow the processor or other portions of the second device to communicate with other devices. The I O interfaces may comprise I2C SPI USB RS 232 one or more media device interfaces and so forth.

The I O interface s may couple to one or more I O devices . The I O devices may include input devices such as one or more of a camera a microphone a touch sensor a button and so forth. The I O devices may also include output devices such as one or more of a display audio speakers haptic output devices and so forth. In some embodiments the I O devices may be physically incorporated with the second device or may be externally placed.

The second device may also include one or more communication interfaces . The communication interfaces are configured to provide communications between the second device and other devices such as other devices routers access points servers and so forth. The communication interfaces may include devices configured to couple to one or more networks including PANs LANs WLANs WANs and so forth. For example the networks may use Ethernet Wi Fi Bluetooth ZigBee and so forth.

The second device may also include one or more busses or other internal communications hardware or software that allow for the transfer of data between the various modules and components of the second device .

As shown in the second device includes one or more memories . The memory comprises one or more CRSM. The memory provides storage of computer readable instructions data structures program modules and other data for the operation of the second device .

The memory may include at least one OS module . The OS module is configured to manage hardware resource devices such as the I O interfaces the I O devices the communication interfaces and provide various services to applications or modules executing on the processors . The OS module may also be configured to support encrypted communications such as SSL TLS or other protocols with other devices such as the first device the association server an access point and so forth.

Also stored in the memory may be one or more of the following modules. These modules may be executed as foreground applications background tasks daemons and so forth.

A user interface module is configured to provide a user interface to the user using the I O devices and to accept inputs received from the I O devices . The user interface may include one or more visual audible or haptic elements. For example the user interface may be configured to provide a graphic user interface an audible user interface and so forth.

A secure configuration provisioning module or provisioning module is also stored in the memory . The provisioning module is configured to support the processes described in this disclosure. This may include generating the credential requests communicating with the first device coordinating the actions of other modules and so forth.

A cryptographic nonce module is configured to generate the cryptographic nonce . The cryptographic nonce is an arbitrary value and may be generated using a random or pseudo random number generator. The cryptographic nonce module may also be configured to compare nonce values such as the cryptographic nonce as originally generated and the signed cryptographic nonce to determine if the two are equivalent.

A challenge response module is configured to process the signed challenge and generate the challenge response . In some implementations the processing of the signed challenge may be based at least in part on the device specific secret . The challenge response module may be directed by the secure configuration provisioning module to send the challenge response after the cryptographic nonce module has verified the signed cryptographic nonce and that the signature of the signed cryptographic nonce is valid.

A credential management module is configured to manage network credentials which have been received provide network credentials to other devices and so forth. For example the secure configuration provisioning module may be configured to direct the credential management module to use the network credentials to configure the second device to join the WLAN or other networks.

Other modules may also be present. For example a speech recognition module may be configured to accept spoken input. As described above one or more of the modules described above may be configured to execute in one or more secure modules. The secure module may comprise dedicated memory dedicated processor or other resources configured to improve security of the modules executing therein.

The memory may also include a datastore to store information. The datastore may use a flat file database linked list tree or other data structure to store the information. In some implementations the datastore or a portion of the datastore may be distributed across one or more other devices including servers network attached storage devices and so forth.

As depicted here the datastore may store one or more of the credential request the device specific secret the challenge data the challenge response and so forth. The datastore may also include encryption key s . As described above this may include public keys and private keys to support secure communications. Other data may also be stored. For example the other data may include user preferences configuration files and so forth.

The I O interface s may couple to one or more I O devices . The I O devices may include input devices such as one or more of a camera a microphone a touch sensor a button and so forth. The I O devices may also include output devices such as one or more of a display audio speakers haptic output devices and so forth. In some embodiments the I O devices may be physically incorporated with the association server or may be externally placed.

The association server may also include one or more communication interfaces similar to those described above with respect to . The association server may also include one or more busses or other internal communications hardware or software that allow for the transfer of data between the various modules and components of the association server .

As shown in the association server includes one or more memories . The memory comprises one or more CRSM. The memory provides storage of computer readable instructions data structures program modules and other data for the operation of the association server .

The memory may include at least one OS module . The OS module is configured to manage hardware resource devices such as the I O interfaces the I O devices the communication interfaces and provide various services to applications or modules executing on the processors . The OS module may also be configured to support encrypted communications such as SSL TLS or other protocols with other devices such as the first device the second device an access point and so forth.

Also stored in the memory may be one or more of the following modules. These modules may be executed as foreground applications background tasks daemons and so forth.

A communication module is configured to support communication between the association server and other devices including the first device . The communication module may be configured to implement one or more application programming interfaces API .

An account maintenance module is configured to manage information such as the account data the device specific secrets and so forth. In one implementation the account maintenance module may be configured to receive information from merchants manufacturers and so forth. This information may be used to maintain or update the account data the device specific secrets and so forth.

A challenge response generation module is configured to generate the challenge and the expected challenge response . The challenge may be based at least in part on the device specific secret associated with the second device . In one implementation the expected challenge response may be based on processing the challenge with a function such as HMAC SHA 256.

A cryptographic signature module is configured to cryptographically sign files or other data verify cryptographic signatures and so forth. For example the cryptographic signature module may be configured to cryptographically sign the challenge to form the signed challenge .

Other modules may also be present. For example a billing module may be configured to manage billing functions associated with the devices.

The memory may also include a datastore to store information. As described above the datastore may use a flat file database linked list tree or other data structure to store the information. In some implementations the datastore or a portion of the datastore may be distributed across one or more other devices including servers network attached storage devices and so forth.

As depicted here the datastore may store one or more of the verification request the account data the device specific secret the verification data and so forth.

The account data provides information which associates devices. In one implementation this information may include a table such as that depicted here. In this table several accounts are listed along with device identifiers for the associated devices. For example device identifier 5466KQ3 and K498BE1 are associated with the same account 45649 . As described above this association may be based on one or more factors such as a common delivery address method of payment user account and so forth.

The device specific secret associates a particular secret with a particular device. For example device 5466KQ3 has the associated device specific secret of 81868q4 . As described above the device specific secret may be used to generate at least a portion of the challenge data .

The datastore may also include encryption key s . As described above these may include public keys and private keys to support secure communications.

Other data may also be stored. For example the other data may include billing information data about expired nonces or keys a blacklist of devices to not respond to and so forth. Continuing the example a device identifier of a device which is suspected or known to be associated with attempts to compromise the security of the system may be blacklisted such that secure configuration provisioning is unavailable.

Blocks and establish a connection between the first device and the second device . As described above in some implementations this connection may be secured such as by implementing SSL TLS and so forth. The connection is secure in that it is encrypted. However even when encrypted the identity of the devices in the connection may not be authenticated. This connection between the first device and the second device does not utilize the WLAN or another network to which the second device has not yet received the network credentials .

Block at the second device sends a credential request comprising the second device identifier and the cryptographic nonce . As described above the cryptographic nonce may be configured to expire or become invalid after a predetermined period of time. As also described above the second device identifier is indicative of the identity of the second device .

The first device receives from the second device the credential request . Block at the first device generates the network credential hash . The network credential hash is generated by applying a hash function to at least a portion of the network credentials . The network credentials may comprise data associated with connecting to a network. For example the data may include SSID password encryption type used and so forth. In some implementations the network credential hash may also be generated based on the cryptographic nonce .

Block at the first device cryptographically signs and sends the verification request to the association server . As described above the verification request includes the first device identifier the second device identifier the cryptographic nonce and the network credential hash .

The association server receives the verification request . In some implementations the verification request may be cryptographically signed by the first device . In implementations where the verification request is cryptographically signed block verifies the cryptographic signature of the signed verification request .

Block at the association server verifies the first device and the second device are associated. This association may be indicated by data stored at or accessible to the association server . For example both devices may be registered to the same user account. In some implementations the verification may include lookup of the device identifiers in the account data .

Block based at least in part on the second device identifier generates the challenge and the expected challenge response for the second device . As described above the challenge and the expected challenge response may be based at least in part on the device specific secret which is known to the association server .

Block cryptographically signs the verification data . As described above the verification data comprises the second device identifier to create the signed cryptographic nonce the network credential hash to create the signed network credential hash and the challenge to create the signed challenge . In some implementations the expected challenge response may not be cryptographically signed.

Continuing to block sends the verification data to the first device . As described above the verification data comprises the signed second device identifier the signed cryptographic nonce the signed network credential hash the signed challenge and the signed expected challenge response . In some implementations the expected challenge response may be left unsigned.

The first device receives from the association server the verification data . In some implementations the first device may verify the cryptographic signatures of the verification data to confirm the verification data originates from the association server .

Block at the first device sends the challenge data to the second device . As described above the challenge data may comprise the signed cryptographic nonce the signed network credential hash and the signed challenge .

The second device receives the challenge data . As described above the challenge data may be cryptographically signed by an association server . Block verifies the signatures in the challenge data . For example the second device may verify the signature of the signed cryptographic nonce the signed network credential hash and the signed challenge . This verification helps confirm the legitimacy of the challenge data .

Block generates the challenge response to the signed challenge using the previously stored device specific secret . As described above where legitimate the challenge response corresponds to an expected challenge response generated by the association server .

Block sends the challenge response to the other device such as the first device . For example the second device may use the communication interface to transmit the challenge response to the first device .

The first device receives the challenge response from the second device . As described the challenge response is based at least in part on a response to the signed challenge . Block at the first device verifies the challenge response against the signed expected challenge response .

Based at least in part on the verification block sends the network credentials from the first device to the second device .

At the second device block verifies the network credentials correspond to the signed network credential hash . For example the hash function may be applied to the network credentials and the result compared to the signed network credential hash .

Block configures one or more network connections based at least in part on the verified network credentials . The network credentials may now be used to join the second device to the WLAN .

In some implementations the data included in one or more of the credential request the verification request or the verification data may vary. For example in some implementations the cryptographic nonce may be omitted from the credential request and the subsequent process. In another implementation the network credential hash may be omitted from the verification request and the subsequent process.

In this illustration time increases down the page as indicated by the arrow . Horizontally across the page are the first device and the second device . The process may be implemented by these devices.

Block at the first device determines the second device is available to receive the network credentials . For example the second device may have broadcast a credential request which is received by the first device .

Block at the first device determines an automatic exchange of the network credentials is unavailable. For example the first device may be unable to communicate with the association server the account data may indicate no association between the devices and so forth.

Block at the first device receives user input to send the network credentials to the second device . For example the user interface module on the first device may receive a user selection of a control configured to initiate transmission of the network credentials .

Block at the first device sends the network credentials to the second device . Block at the second device receives user input approving use of the received network credentials . For example the user may provide input to the user interface module that accepts the received network credentials .

Block at the second device configures the communication interface using the network credentials . For example the communication interface may be set to the SSID MYHOME and the password of hello allowing the second device to join the WLAN .

In this illustration time increases down the page as indicated by the arrow . Horizontally across the page are the first device and the second device . The process may be implemented by these devices.

Block at the second device determines an automatic exchange of the network credentials is unavailable. For example the first device may be unable to communicate with the association server the account data may indicate no association between the devices and so forth.

Block presents a presented code to the user . The presented code may be presented with a user interface provided by the user interface module . For example the presented code may be displayed visually on a display device or light audibly using a speaker and so forth. The code may be a string sequence of shapes sounds colors lights blink pattern or other distinctive arrangement of information.

Block at the first device accepts an entered code comprising user input of the presented code. The user input may be received by a user interface provided by the user interface module . For example the user may enter the entered code using buttons presented on a touch sensitive display.

Block at the first device performs a zero knowledge proof based on the entered code. As described above the zero knowledge proof is based at least in part on the entered code accepted at the first device . Likewise block at the second device performs a zero knowledge proof based on the presented code. The zero knowledge proof is configured to allow a recipient to determine that the sender knows a piece of information without revealing the information to the recipient. In some implementations based on a successful proof a secure connection may be established. For example SSL or TLS may be used for communications between the two devices which are now known to have the same code.

The zero knowledge proof is analyzed to confirm a successful proof of the presented code. Based on a successful proof block at the first device sends network credentials to the second device . For example the first device may send this data using a Wi Fi Direct connection.

Block at the second device receives from the first device the network credentials . Block at the second device configures the communication interface based at least in part on the network credentials . In some implementations the configuration of the communication interface may be based at least in part on the successful proof as determined by the second device . The correspondence of the entered code with the presented code indicates that the same user has access to both devices and may serve as sufficient demonstration that the network credentials should be permitted to be exchanged.

In this illustration time increases down the page as indicated by the arrow . Horizontally across the page are the first device and the second device . The process may be implemented by these devices.

Block at the second device stores a stored code at a second device. The stored code may be a string sequence of shapes sounds colors lights blink pattern or other distinctive arrangement of information. In some implementations stored code may be stored in the memory of the second device . In other implementations the stored code may be stored by writing on an object affixed to the second device such as a sticker or nameplate embossing etching or other marking.

Block at the second device determines an automatic exchange of the network credentials is unavailable. Block presents the stored code to a user. This presentation may include displaying the stored code visually on a display device or light audibly using a speaker and so forth. The stored code may be a string sequence of shapes sounds colors lights blink pattern or other distinctive arrangement of information.

Block at the first device receives user input comprising a received code. For example the user input may be of a string of letters and numbers. The received code may be associated with the stored code. For example the user may see the stored code on a sticker and enters that information using a user interface provided by the user interface module .

Block at the first device sends the received code and the network credentials to the second device . Block at the second device receives the received code and the network credentials . Block at the second device determines the received code matches the stored code. Block at the second device based at least in part on the determined match configures the communication interface based at least in part on the network credentials .

Those having ordinary skill in the art will readily recognize that certain steps or operations illustrated in the figures above can be eliminated or taken in an alternate order. Moreover the methods described above may be implemented as one or more software programs for a computer system and are encoded in a computer readable storage medium as instructions executable on one or more processors.

The computer readable storage medium can be any one of an electronic storage medium a magnetic storage medium an optical storage medium a quantum storage medium and so forth. Separate instances of these programs can be executed on or distributed across separate computer systems. Thus although certain steps have been described as being performed by certain devices software programs processes or entities this need not be the case and a variety of alternative implementations will be understood by those having ordinary skill in the art.

Additionally those having ordinary skill in the art readily recognize that the techniques described above can be utilized in a variety of devices environments and situations.

Although the present disclosure is written with respect to specific embodiments and implementations various changes and modifications may be suggested to one skilled in the art and it is intended that the present disclosure encompass such changes and modifications that fall within the scope of the appended claims.

