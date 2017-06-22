---

title: Secure access to applications behind firewall
abstract: A user having remote device wants to access an application executing on an application server computer that is behind a firewall. During set-up, another firewall and a gateway computer are configured in front of the original firewall. During registration, users' remote devices are configured with security data. The security data includes user authentication cryptographic credentials, for establishing secure channels, and may include user application cryptographic credentials as needed by individual applications executing on the application server. During operation, the user provides a password to an application program executing on his/her remote device to use the security information on the remote device to establish a secure channel to the application, and then conducts a data session with the application. If the application needs to verify the identity of the user, the user's remote device performs a cryptographic operation using the user application cryptographic credentials, and sends the result to the application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09059962&OS=09059962&RS=09059962
owner: Route1 Inc.
number: 09059962
owner_city: Toronto, Ontario
owner_country: CA
publication_date: 20130313
---
The present invention relates to enabling a user having a remote device to access applications executing on an application server.

It is desirable that a remote user of an organization s computer applications be able to connect to these applications using a public communication network such as the Internet. It is also desirable that an organization s computers not be exposed to unauthorized access from the public communication network such as by hackers. It is further desirable that security measures such as authorizing access to potential users occur in a separate device from the host computer to strongly isolate the host computer and the authorization module from malicious users.

One way to allow remote connectivity is for the organization to establish a virtual private network VPN using the public communication network. However a VPN is complex to manage and so is burdensome for an enterprise. Also a VPN may make the internal enterprise network vulnerable to computer viruses and other malware.

Another way to allow remote connectivity is for the organization to set up a web page allowing the remote user to log in. If non encrypted the information exchanged between the web server and the remote user is unsecured. Whether or not encrypted the web server is vulnerable to attacks such as distributed denial of service attacks. If encrypted and a strong authentication of the client is desired both the web server and the remote user need to have cryptographic certificates introducing a certificate management burden.

A further way to allow remote connectivity is described in U.S. Pat. No. 7 814 216 which is commonly owned with the instant application the disclosure of which is hereby incorporated by reference in its entirety. The 216 patent discloses that a remote device a controller and a host computer are all connected to a public communication network. The remote device uses a special software program adapted to use public key infrastructure PKI security certificates to access the controller and tells the controller which host it wishes to connect to. The controller verifies the remote and then tells the host computer to send a connection request to the remote device. After the remote device accepts the connection request the controller is no longer involved unless the connection is undesirably broken.

U.S. Pat. No. 7 739 726 which is commonly owned with the instant application the disclosure of which is hereby incorporated by reference in its entirety discloses a memory stick device that contains the special software program and is inserted into a USB port or similar connector of a computer to enable the computer to function as the remote device in the configuration of the 216 patent.

Yet another way to allow remote connectivity is described in U.S. Patent Application Publication No. 2005 0120204 Kiwimagi . FIG. 2 of Kiwimagi is reproduced as of the instant application and shows a public communication network having connected thereto security host remote client and system host .

During registration shown in FIGS. 3 a and 4 of Kiwimagi corresponding to of the instant application remote client contacts security host and requests the network address of system host . After verification of remote client security host provides the network address of system host to remote client .

During operation shown in FIGS. 3 b and 4 of Kiwimagi corresponding to of the instant application remote client sends a connection request to system host . In turn system host asks security host to verify remote client . After security host verifies remote client system host grants access to remote client and remote client then uses system host .

Application programs that require user to computationally verify their identity generally assume that a user has cryptographic data that has been provided only to that user and then expect the user to perform a computation using that cryptographic data to provide a result which will verify the identity of the user as only the user with the particular cryptographic data will be able to properly compute the result. However managing the distribution and revocation of such cryptographic information is burdensome for an enterprise particularly if the enterprise uses different applications that each require different cryptographic data for each user.

In accordance with an aspect of this invention there is provided a method of enabling use of an application program comprising receiving at a controller computer a request from a user of a remote device for application entitlement. The controller computer sends to the remote device a list of application programs that the user of the remote device is entitled to use and network addresses of gateway computers respectively associated with the application programs. One of the gateway computers receives a request from the user of the remote device for use of a selected application program. The gateway computer sends to the controller computer a request for verification that the user of the remote device is entitled to use the selected application program and receives a response from the controller computer indicating that the user of the remote device is entitled to use the selected application program. The gateway computer establishes a secure channel to the selected application program executing on a computer other than the gateway computer or the controller computer. The gateway computer receives data from the selected application program and automatically sends the data from the selected application program to the remote device. The gateway computer receives data from the remote device and automatically sends the data from the remote device to the application program using the secure channel.

It is not intended that the invention be summarized here in its entirety. Rather further features aspects and advantages of the invention are set forth in or are apparent from the following description and drawings.

A user having remote device wants to access an application executing on an application server computer that is behind a firewall. During a set up phase another firewall and a gateway computer are configured in front of the original firewall creating a demilitarized zone DMZ having the gateway computer. During a registration phase users remote devices are configured with security data.

After set up and registration i.e. during operation the user provides a password to an application program executing on his her remote device. The password enables use of the security information on the remote device.

In one embodiment the user now accesses an application through a conventional method such as a non secure channel and when the application requires use of the security information on the remote device the user is able to respond properly.

In another embodiment the user uses the security information to establish a secure channel to the application and then conducts a data session with the application.

Generally controller is operated by a service provider different than the enterprises that want their remote users to securely use the enterprise application programs. The enterprise administrator sometimes referred to as a domain administrator typically prefers to store as little as possible on the controller due to the enterprise security policy. Because the gateway is located at the premises of the enterprise it is under the physical control of the enterprise and so the enterprise administrator is usually more comfortable with managing from the gateway and storing information at the gateway. However if the enterprise has multiple gateways storing certain information at the controller is efficient as it provides a single point from which to manage security information with a uniform interface even if the originators of the security information use different techniques.

As used herein and in the claims cryptographic credentials CryCre comprises a private key and corresponding cryptographic certificate as defined in EMC CORPORATION Public Key Cryptographic Standards PKCS specifically RSA LABORATORIES PKCS 12v.1.1 Personal Information Exchange Syntax Oct. 27 2012 available at www.rsa.com and the container information for the private key and certificate. CryCre may also include the public key instead of the corresponding certificate in cases where such a certificate has not yet been issued and all certificates in the trust chain to the root certificate authority. CryCre can be created as needed or pre created stored and retrieved when needed. CryCre can reside on a removable smart card. Table 1 summarizes the CryCre 

Controller is a general purpose computer programmed in accordance with the present invention. Controller executes at least four software programs 

Remote device is a tablet computer such as an APPLE iPAD executing the APPLE IOS operating system. In other embodiments remote device may be another tablet such as a MICROSOFT SURFACE tablet executing the MICROSOFT WINDOWS operating system another tablet executing the GOOGLE ANDROID operating system a smart phone a laptop computer or other suitable device. In some embodiments remote device is operative to receive removable smart card . In some embodiments smart card is embedded in remote device and is not readily removable. Smart cards are generally based on ISO 7816 card with contacts or ISO 14443 contact less cards . Smart card usually generates a mathematically related private key and public key pair to be used in cryptographic credentials and the private key never leaves smart card .

As used herein and in the claims a firewall refers to a program that controls network traffic by analyzing data packets to a host and determining whether or not to transmit them to the host based on a predetermined rule set. The firewall program can run in a separate dedicated device or in another device. The rule set can specify attributes of the packet such as source IP address source port destination IP address destination port or destination service world wide web or file transfer protocol protocol used time to live and so on. An example of a firewall is the Cisco ASA Firewall described at www.cisco.com.

Firewall is coupled to network and gateway via suitable wireline or wireless communication links. Firewall is a general purpose computer dedicated to executing a firewall program in accordance with a predetermined rule set for determining which data packets from network to pass through so that all other data packets from network are blocked.

Gateway is coupled to firewall firewall and optionally third party via suitable wireline or wireless communication links. Gateway is a general purpose computer programmed to cooperate with controller in accordance with the present invention. At least one instance of gateway is located at each domain. An enterprise is associated with at least one domain. In some embodiments gateway is operative to receive removable smart card .

Third party is shown with dashed lines in to indicate that it is absent in some embodiments. Third party is shown in as directly connected to gateway in some embodiments third party is actually coupled to network and accessed via network by gateway . In some embodiments a firewall is present between gateway and third party . In some embodiments third party is the source of the security certificate for users.

Third party executes certificate authority software program for issuing certificates according to the X.509 standard or other suitable standard when an enterprise administrator designates controller as the source thereof and stores certificate revocation data indicating which certificates have been revoked with list of revocation data per root certificate authority and optional user cryptographic credentials when the domain administrator has specified that the user CryCre are stored in third party for subsequent transfer to the user. In some embodiments controller stores a local copy certificate revocation list .

Firewall is coupled to gateway and application server via suitable wireline or wireless communication links. Firewall is a general purpose computer dedicated to executing a firewall program in accordance with a predetermined rule set for determining which data packets from gateway to pass through so that all other data packets from gateway and optionally to gateway are blocked.

Gateway is said to reside in a demilitarized zone DMZ between firewalls and . As used herein and in the claims a DMZ means a computing area that is accessible via network .

Application server is a general purpose computer executing applications . Generally a user of remote device wants to remotely use one of applications and the present invention enables such remote usage from authorized remote devices while protecting against remote usage from unauthorized remote devices. Each of applications may optionally be associated with respective cryptographic credentials .

Web server is a general purpose computer operative to send and receive information via network . Web server executes application program which at some points requires that a user provide the results of a cryptographic operation to be entitled to particular functions of application program .

Various uses of the configuration of will now be described at a high level with references to followed by a detailed description. Table 2 summarizes some of the configurations that need to be accommodated to provide flexibility so that domain administrators can optimize for their needs. The rightmost column of Table 2 indicates which of the figures correspond to the configuration of that row.

In the embodiments shown and discussed herein pre stored cryptographic credentials are in one place. In other embodiments for added protection the cryptographic credentials are divided into multiple parts with each part stored in a different place. During retrieval the parts are retrieved from their various locations and combined.

The certificate or CryCre can be used for authentication encryption or an application that is the distribution process is the same regardless of the eventual use of the security data. The pre stored CryCre are generated as specified by a domain administrator by either controller third party or possibly another source and then the domain administrator specifies where they should be stored.

At various points in the set up registration and operation flowcharts below the procedure of establish secure channel is used. Any appropriate technique may be used. In this embodiment a secure channel is established using the Transport Layer Security protocol defined in Internet Engineering Task Force Request For Comments 5246 available at tools.ietf.org html rfc5246 specifying a procedure involving about twenty steps. It will be understood that when each endpoint of the channel has a security certificate then the channel is mutually authenticated in that both endpoints cryptographically validate each other s cryptographic credentials. However if only one endpoint of the channel has a security certificate and corresponding cryptographic credentials as occurs during remote device registration when the remote device is one of the channel endpoints and lacks its own security certificate then the remote device uses cryptographic methods to authenticate the controller and establish the secure communication channel but the controller cannot use cryptographic methods to authenticate the remote device.

In at step firewall is configured to allow properly formatted requests to gateway . A properly formatted request comprises a TCP IP packet from any sender that has a destination of a specified gateway port.

In at step firewall is configured to allow properly formatted requests to application server . A properly formatted request comprises a TCP IP packet from gateway and addressed to one of the applications executing on application server i.e. application or and forwarded by the operating system of application server to the application.

In step a master administrator uses master administrator interface to generate cryptographic credentials for controller and stores the controller CryCre in controller crypto credentials shown in . For instance the OpenSSL Toolkit available at www.openssl.org may be used to generate cryptographic credentials. OpenSSL 1.0.1e was released on Feb. 11 2013. The openssl program is a command line tool for using the cryptography functions of the OpenSSL crypto library including 

At step the master administrator uses master administrator interface to create enterprise domains and authorize respective enterprise administrators. Practically when an enterprise becomes a customer for the controller gateway services described herein the enterprise designates someone as its enterprise administrator also referred to as a domain administrator.

At step a domain administrator for the enterprise associated with application server provides common data for the domain to populate domain data . Generally the domain administrator uses a browser and a secure channel via network to access enterprise administrator interface and either provides data via a screen based graphical user interface or uploads a data file in a predetermined format see step .

At step the domain administrator populates user data for the domain using enterprise administrator interface via a screen based graphical user interface or uploads a data file in a predetermined format see step .

At optional step enterprise administrator interface provides a license key for each user. More specifically if domain data indicates that the domain will use license keys for its users then license keys are generated for the users at step .

At optional step the domain administrator provides user authentication cryptographic credentials to controller for storage therein. The domain administrator may interact directly with enterprise administrator interface executing on controller or the domain administrator may interact with enterprise administrator interface executing on gateway and gateway forwards the information to enterprise administrator interface on controller . The double vertical lines around the box in indicate that it is a process further described in another flowchart specifically the left hand side of the flowchart of discussed below.

At optional step the domain administrator provides user application cryptographic credentials to controller for storage therein. The double vertical lines around the box in indicate that it is a process further described in another flowchart specifically the left hand side of the flowchart of discussed below.

At step controller provides an encryption certificate for gateway authentication cryptographic credentials see the left hand side of .

At step controller provides an encryption certificate for gateway encryption cryptographic credentials or provides the encrypted gateway encryption cryptographic credentials see the left hand side of .

At optional step controller imports gateway encryption cryptographic credentials see the left hand side of .

In at step the domain administrator configures gateway populating gateway data using domain administrator interface . The process of configuring includes 

At step the domain administrator installs the gateway authentication cryptographic credentials. The double vertical lines around the box in indicate that it is a process further described in another flowchart specifically the right hand side of the flowchart of discussed below.

At step the domain administrator installs the gateway encryption cryptographic credentials. The double vertical lines around the box in indicate that it is a process further described in another flowchart specifically the right hand side of the flowchart of discussed below.

At optional step the domain administrator uploads common data for the domain to controller see step .

At optional step typically used when a domain is associated with multiple gateways the domain administrator exports the gateway encryption cryptographic credentials created at step to controller for convenient distribution to the other gateways associated with the domain. The domain administrator usually also exports the gateway encryption cryptographic credentials for back up such as to removable storage media that is kept in a physically secured location. The double vertical lines around the box in indicate that it is a process further described in another flowchart specifically the right hand side of the flowchart of discussed below.

The remaining steps in are assumed to be executed during set up and also after each power up or rebooting activity.

At step enterprise administrator interface checks whether the Spassword see step is stored. If not which is the preferred and more secure method of operating gateway then at step the domain administrator inputs the Spassword. Otherwise at step enterprise administrator interface retrieves the stored Spassword from gateway data . Steps are repeated for the Gpassword not shown .

At step enterprise administrator interface checks whether gateway smart card is present in gateway . If so interface uses the Spassword to unlock smart card . ISO standard 7816 15 describes use of smart cards locking unlocking and cryptographic operations. If there is no smart card at step interface retrieves the encryption cryptographic credentials for the gateway installed at step and at step interface decrypts the encrypted gateway encryption cryptographic credentials using the Spassword. Steps are repeated for the Gpassword not shown .

At optional step enterprise administrator interface creates a set of pools of mutually authenticated sessions with applications respectively to save time later by avoiding the time delay of creating a channel. A channel from this pool is used in step . In some embodiments there are respective channel pools for the applications. In other embodiments there is one trusted secure and mutually authenticated channel between gateway and application server for instance according to the IPsec protocol and the application sessions may rely on the trusted channel.

At optional step the domain administrator imports authentication cryptographic credentials for its users populating user cryptographic credentials using domain administrator interface see the right hand side of .

At optional step the domain administrator imports application cryptographic credentials for its users populating user cryptographic credentials using domain administrator interface see the right hand side of .

Turning to the controller see steps and at step enterprise administrator interface determines whether the source of the user cryptographic credentials is manual entry or gateway using either domain data or asking the domain administrator.

If the source of the user cryptographic credentials is manual entry at step the domain administrator provides a file with the user cryptographic credentials or imports the cryptographic credentials one at a time at step controller stores the CryCre in user crypto credentials at step enterprise administrator interface updates domain data and processing is complete.

If the source of the user cryptographic credentials is gateway then at step controller establishes a secure channel with gateway in response to a request from gateway at step discussed below. At step controller receives encrypted user cryptographic credentials from gateway . At step controller stores the encrypted user CryCre in user crypto credentials .

At step controller receives updated domain information namely the metadata that the user cryptographic credentials are stored in user crypto credentials and updates domain data and user data as appropriate.

Turning to the gateway see steps and at step similar to step the domain administrator provides a file with the user cryptographic credentials. At step the domain administrator specifies whether the encryption type is asymmetric or symmetric. Symmetric encryption is performed according to the AES standard in other embodiments other standards are followed.

If asymmetric encryption is used at step enterprise administrator interface encrypts the user cryptographic credentials with the public key of the gateway encryption cryptographic credentials tags the encrypted user CryCre with the gateway certificate used for encryption sets a flag indicating that the encryption type is asymmetric and either attaches a tag that identifies the certificate or provides appends the certificate. Processing continues at step .

If symmetric encryption is used at step enterprise administrator interface generates random numbers X Y and Z. At step interface encrypts the user cryptographic credentials plus the random number Y using the random number X to generate a number XX. At step interface encrypts the sum of random numbers X and Z with the public key of the gateway encryption cryptographic credentials to generate a number PP. At step interface packages the sum XX PP sets a flag indicating that the encryption type is symmetric and either attaches a tag that identifies the certificate or provides appends the certificate.

At step interface determines whether the storage destination of the user cryptographic credentials is controller or gateway using gateway data or asking the domain administrator. If the storage destination is gateway then interface stores the encrypted user cryptographic credentials in user crypto credentials and processing continues at step .

If the storage destination is controller at step gateway establishes a secure channel with controller . At step gateway sends the encrypted user cryptographic credentials to controller .

At step enterprise administrator interface on gateway sends a message to enterprise administrator interface on controller providing metadata about the user cryptographic credentials including where they are stored whether they are encrypted their encryption method and so on.

At step enterprise administrator interface on gateway checks the source of the Gpassword. If not which is the preferred and more secure method of operating gateway then at step the domain administrator inputs the Gpassword. Otherwise at step enterprise administrator interface retrieves the stored Gpassword from gateway data .

For the first case cryptographic credentials obtained from a pre issued smart card at step the domain administrator inserts the smart card and at step interface unlocks the smart card using the Gpassword and retrieves the cryptographic credentials from the smart card and the procedure of is complete.

For the second case cryptographic credentials based on a public private key pair generated by gateway and a corresponding certificate issued by controller at step interface generates a public and private key pair. At step interface establishes a secure channel with controller . At step interface sends the public key to controller requests a corresponding authentication certificate and receives the certificate. At step interface creates a cryptographic credentials package including the private key and the certificate according to the PKCS 12 standard.

At controller at step controller does its part to establish a secure channel. At step certificate authority issues a certificate corresponding to the public key and provides the certificate to gateway .

For the third case cryptographic credentials manually provided by the domain administrator at step the domain administrator imports the cryptographic credentials. At step the domain administrator provides the Epassword to interface . At step interface uses the Epassword to decrypt the imported cryptographic credentials.

At step enterprise administrator interface checks whether gateway smart card is present. If so at step interface stores the cryptographic credentials on smart card . It will be appreciated that the private key is already on smart card . If not at step interface encrypts the cryptographic credentials according to the PKCS 5 standard with the Gpassword and stores them in user crypto credentials .

At step interface determines whether it should store the Gpassword. If so interface obfuscates the Gpassword such as by XOR ing it with another number and stores it in gateway data preferably in a visible to system only area. Storing the Gpassword means that gateway can be started or rebooted without intervention from the enterprise administrator. Not storing the Gpassword is more secure but requires the domain administrator to enter the Gpassword.

In at step there is a fourth source of the cryptographic credentials controller such as when a domain has multiple gateways using the same encryption cryptographic credentials. At step interface establishes a secure channel with controller . At step interface sends a request for the gateway encryption cryptographic credentials to controller and receives them. At step controller does its part in establishing a secure channel. At step controller sends the gateway encryption cryptographic credentials to gateway . Processing continues at step corresponding to step .

At step interface checks the destination for exporting. If the destination is an external backup such as removable media or enterprise network storage at step interface sends the encrypted cryptographic credentials to the external destination.

If the destination is controller at step gateway establishes a secure channel with the controller and at step interface sends the encrypted cryptographic credentials to controller .

Turning to the controller at step enterprise administrator interface establishes a secure channel with gateway . At step interface receives the encrypted cryptographic credentials. At step interface stores the encrypted cryptographic credentials in user crypto credentials .

The user gets access application by downloading it from an network site such as third party or controller by downloading it from an application store such as the Apple App Store by installing it from a file on a removable media by receiving it as an email attachment or other suitable technique.

At optional step the user gets a license key from the domain administrator via a suitable technique such as email physical mail or voicemail. See step for license key creation. A license key is a long alphanumeric character string created by a non sequential algorithm that does not produce recognizable patters making it impractical to try to predict or guess a valid license key.

At step the user launches access application such as by clicking on an icon associated with access application or other suitable technique.

At step access application checks whether this is a new registration attempt registration a continuation of a pending new registration attempt or whether remote device has previously registered.

If previously registered at step access application receives the Upassword from the user. At step access application checks whether remote smart card is present. If not at step access application retrieves the user authentication cryptographic credentials from user crypto credentials and decrypts them. If smart card is present access application unlocks smart card as specified in ISO 7816 15. At step access application reads the hardware ID from remote device using the native application programming interface for remote device and processing continues at step .

If this is a first registration at step access application checks whether a pre issued remote smart card is present. If so processing continues at step above . Generally a blank smart card is prepared for use by setting a user password or personal identification number PIN generating cryptographic keys and adding certificate s signed by the appropriate certificate authority. Examples of pre issued smart cards include U.S. government issued Personal Identity Validation PIV cards.

If a pre issued smart card is not present at step the user selects whether authentication will proceed with a license key or via a hardware identifier such as the media address control MAC address of remote device in accordance with the selection instructions received from the domain administrator.

At step access application reads the hardware identifier from remote device using the native application programming interface for remote device . Examples of hardware IDs are 

At step the user creates a Upassword for use with access application for protecting cryptographic credentials. A version of the Upassword processed through a one way cryptographic hashing function such as SHA 2 may also be stored on controller to allow the user access to his her account settings. The hashing of the original Upassword ensures that only the user knows the original password and that controller has no ability to uncover the password. The Upassword is kept in the memory of remote device but is never permanently stored therein.

Also at step the user provides his her user identification code received from the domain administrator. For example the user identification code may be the user s enterprise email address or the user s Windows domain user ID. Access application stores the user identification code in configuration data .

At step access application reads configuration data to determine whether the method of obtaining the user s security material is known. If known at step access application retrieves the method from configuration data and processing continues at step

If the method of obtaining the user s security material is not known at step access application establishes a secure channel with controller controller side only authentication . At step controller does its part in establishing a secure channel. At step access application requests and receives the method of obtaining the user s security material. At step authorization module of controller provides the method.

At step access application checks which method it should use to obtain the user s security information. If the method is on demand issuance of a security certificate processing continues at step . If the method is to use pre issued cryptographic credentials processing continues at step .

Turning to at step access application generates a public and private key pair according to a public key cryptography technique such as RSA PKCS 1 elliptic curve cryptography ECC PKCS 13 Diffie Hellman key exchange PKCS 3 or other suitable technique.

At step access application establishes a secure channel with authorization module executing on controller and at step controller does its part towards establishing the secure channel.

At step access application requests a security certificate for the public key that it generated at step . At step authorization module at controller receives the request.

At step authorization module checks domain data to determine the source of the security certificate manual itself or a third party.

If the source of the security certificate is itself then at step certificate authority generates a security certificate for the user s public key that is signed by certificate authority . See . Processing continues at step .

If the source of the security certificate is a third party then at step authorization module establishes a secure channel with authorization module executing on gateway which in turn at steps and establishes a secure channel with third party .

At step authorization module sends a request for a security certificate corresponding to the user s public key to authorization module which forwards the request to third party at step .

At step third party receives the request for a security certificate and at step third party functions as a certificate authority to issue and sign the security certificate. See . At step third party provides the security certificate to gateway .

At step gateway receives the security certificate from third party and forwards it to controller . At step authorization module receives the security certificate.

At step authorization module provides the security certificate to access application . At step access application receives the security certificate.

At step access application checks whether remote device smart card is present. If so at step access application stores the certificate on smart card and processing continues at step .

If there is no smart card at step access application creates a user authentication cryptographic credentials package with the just obtained certificate. At step access application encrypts the user authentication cryptographic credentials package using the Upassword and a characteristic of remote device such as its MAC address and stores the encrypted cryptographic credentials package in user cryptographic credentials . Processing continues at step .

Turning to at step access application establishes a secure channel with authorization module executing on controller and at step controller does its part towards establishing the secure channel.

At step access application requests a cryptographic credentials package. At step authorization module executing on controller receives the request.

At step authorization module checks domain data to determine the source of the user authentication cryptographic credentials package. There are three possibilities for accessing the user authentication cryptographic credentials controller a third party via gateway or instructing remote device to contact gateway directly. The third case is attractive to domain administrators that want to minimize the involvement of controller in their enterprise security.

If the source of the cryptographic credentials package is controller at step authorization module retrieves the cryptographic credentials package from user cryptographic credentials . See . The double vertical lines at step indicate this is a procedure see . Processing continues at step .

If the source of the cryptographic credentials package is gateway or a third party via gateway at step authorization module obtains the cryptographic credentials from gateway . See . The double vertical lines at step indicate this is a procedure see . Processing continues at step .

If remote device is to obtain its user authentication cryptographic credentials directly from gateway then at step it does so. See . The double vertical lines at step indicate this is a procedure see . Processing continues at step .

At step authorization module provides the user authentication cryptographic credentials to access application executing on remote device . At step access application receives the user authentication cryptographic credentials.

At step access application checks whether the user authentication cryptographic credentials are encrypted. If so at step access application decrypts the user authentication cryptographic credentials using either i its encryption private key if the remote has user encryption cryptographic credentials or ii the private key associated with the user authentication cryptographic credentials. Since the user authentication cryptographic credentials are tagged with an identification of the certificate used for encryption or the certificate itself access application is easily able to determine the appropriate private key to use.

At step access application encrypts its user authentication cryptographic credentials with the Upassword and a characteristic of remote device such as its MAC address and stores in user authentication CryCre . Processing continues at step .

In step authorization module of controller retrieves the user authentication cryptographic credentials from user CryCre .

At step authorization module checks whether the user authentication cryptographic credentials were encrypted with the gateway certificate. If not processing is complete.

If encrypted at step authorization module establishes a secure channel with authorization module executing on gateway and at step gateway does its part towards establishing the secure channel.

At step authorization module sends the encrypted CryCre to gateway . At step authorization module receives the encrypted CryCre. At step authorization module decrypts the encrypted CryCre using the private key from its gateway encryption cryptographic credentials. It will be recalled that usually all gateways in a domain have the same gateway encryption cryptographic credentials. At step authorization module sends the decrypted CryCre to authorization module . At step authorization module receives the decrypted CryCre and processing is complete.

In at step authorization module establishes a secure channel with authorization module executing on gateway and at step gateway does its part towards establishing the secure channel.

At step authorization module requests an authorization cryptographic credentials package for the user. At step authorization module receives the request.

At step authorization module checks gateway data to determine the source of the cryptographic credentials package.

If the source of the cryptographic credentials package is itself at step authorization module retrieves the cryptographic credentials package from user cryptographic credentials . At step authorization module checks whether the CryCre are encrypted and if so at step decrypts them using the private key from its gateway encryption cryptographic credentials. Processing continues at step .

If the source of the cryptographic credentials package is other than itself at step authorization module establishes a secure channel with third party and at step third party does its part towards establishing the secure channel.

At step authorization module requests a cryptographic credentials package for the user. At step third party receives the request.

At step third party retrieves the cryptographic credentials package from user CryCre . At step third party provides the cryptographic credentials package to gateway . At step authorization module receives the user cryptographic credentials package.

At step authorization module checks whether the cryptographic credentials for this user from steps are user application cryptographic credentials. If not processing continues at step .

If there are user application cryptographic credentials then at step authorization module requests the user s authentication certificate from controller . At step authorization module of controller receives the request.

At step authorization module provides the user authentication certificate. At step authorization module receives the user authentication certificate and extracts the public key from the user authentication certificate.

At step authorization module encrypts the user application cryptographic credentials with the public key extracted from the user authentication certificate sets a flag indicating that this encryption has occurred and tags the user application cryptographic credentials with a reference to the user authentication certificate from which the public key was extracted or appends the user authentication certificate to the user application cryptographic credentials.

At step authorization module provides the user authentication cryptographic credentials and if any the user application cryptographic credentials to authorization module . In other embodiments the user encryption cryptographic credentials are also or alternatively provided at step . At step authorization module receives the user CryCre and processing is complete.

At step authorization module instructs remote device to ask gateway for its cryptographic credentials.

At step access application executing on remote device receives the instruction. At step access application establishes a secure channel with gateway . At step gateway does its part to establish a secure channel.

At step access application requests its user cryptographic credentials. At step authorization module on gateway receives the request.

At step authorization module uses gateway data to determine the source of the user cryptographic credentials. There are three possible sources 

If the source of the cryptographic credentials package is controller at step authorization module establishes a secure channel with controller and at step controller does its part towards establishing the secure channel. At step authorization module requests a cryptographic credentials package for the user and receives it. At step controller receives the request retrieves the user cryptographic credentials from user CryCre and provides them to gateway .

At step authorization module checks whether the user CryCre have been encrypted with the private key from the gateway encryption certificate. If so at step authorization module decrypts them. Processing continues at step .

If the source of the cryptographic credentials package is gateway at step authorization module retrieves the user cryptographic credentials from user CryCre and processing continues at step see above .

If the source of the cryptographic credentials package is third party at step authorization module establishes a secure channel with third party and at step third party does its part towards establishing the secure channel. At step authorization module requests a cryptographic credentials package for the user. At step third party receives the request. At step third party retrieves the cryptographic credentials package from user CryCre . At step third party provides the cryptographic credentials package to gateway . At step authorization module receives the user cryptographic credentials package.

At step authorization module provides the user authentication cryptographic credentials and if any the user application cryptographic credentials to access application . In some embodiments the user encryption cryptographic credentials are also or alternatively provided at step . At step access application receives the user CryCre and processing is complete.

In at step access application establishes a secure channel with controller and at step controller does its part towards establishing the secure channel. At optional step access application sends an update message for its hardware ID. At step authorization module on controller receives the update message and applies it to user data if the policy established by the domain administrator allows. If the policy does not allow storage of a new hardware ID then the user must completely re register or must ask the domain administrator to manually update the hardware ID for remote device .

At step access application inquires whether controller has notice of any new user application cryptographic credentials for the user. During the initial registration assuming no pre issued smart card the user application cryptographic credentials were provided in step or step . Here when a pre issued smart card is used or during a subsequent partial registration there is another opportunity to get new user application CryCre. At step authorization module replies with the number of new user application CryCre.

At step access application checks whether there are any new application CryCre. If not processing continues at step .

If there are new application cryptographic credentials then step is repeated once for each new application CryCre.

At step similar to step access application checks which method it should use to obtain the CryCre. If the method is on demand issuance of a security certificate as indicated by A1 in a circle the processing of is performed. If the method is to use pre issued cryptographic credentials as indicated by B1 in a circle the processing of is performed. The difference between A1 and AA is that A1 returns to whereas AA continues to CC. The difference between B1 and BB is that B1 returns to whereas BB continues to CC.

At step access application checks configuration data to determine whether the identification data for the applications that the user is entitled to use and the associated gateway network addresses will be stored in remote device or will be dynamically obtained from controller as needed. Dynamic provision is preferred so that the user does not have to re register when s he is entitled to another application. If dynamic processing is complete and remote device is registered.

If the applications gateway address data are to be stored at step access application requests data and at step authorization module provides the applications gateway address data. A secure channel between access application and authorization module has already been established and is used for this transaction. At step access application stores the applications gateway addresses list in configuration data .

At step access application establishes a secure channel with authorization module executing on controller and at step controller does its part towards establishing the secure channel.

At step access application requests its certificate. The certificate was originally requested at step but since the fulfillment was manual the registration process was suspended for the certificate to be manually provided. At step the user is checking whether the certificate has been provided so that s he can continue registering. At step authorization module receives the request.

At step authorization module checks user data to determine if the certificate has been issued and provided. If the certificate has not been issued at step authorization module sends a NOT READY notice to remote device . Processing continues at step .

If the certificate has been issued at step authorization module retrieves the certificate from user CryCre . At step authorization module sends the certificate to remote device .

If the response is a NOT READY notice at step access application displays instructions to the user to try again later. After an appropriate time period which may be a few days the user tries again at step .

Turning to at step authorization module executing on controller stores the certificate request as pending in user data . In practice the domain administrator may have a predetermined schedule for manually obtaining new user certificates such as once per week so it is helpful to store the certificate request as pending. In some embodiments controller sends a message to domain administrator that a new request is pending via email or text message not shown .

At step the domain administrator exports the new pending certificate requests to external media such as removable storage. In practice the domain administrator is now getting a batch of requests.

At step the domain administrator manually requests certificates from third party to fulfill its new requests for certificates generally by sending the external media to third party .

At step third party receives the certificate requests. In practice a third party administrator has its own procedure for obtaining new certificate requests such as in the morning and in the afternoon.

At step the third party administrator issues a certificate for the request using certificate authority . In some cases third party administrator may require the requesting user to appear in person and present a particular form of identification prior to issuing the certificate. It will be understood that this process could easily take days to complete.

At step the third party administrator exports the certificate to external media such as removable storage and sends the external media to the domain administrator.

At step the domain administrator receives the certificate. At step the domain administrator imports the certificate to user CryCre of controller and processing is complete.

The operation procedure for the configuration of will now be discussed. In one case a secure channel is used. In another case a non secure channel is used.

At step the user launches access application and provides the Upassword created during registration see step .

At step access application checks whether remote smart card is present. If not at step access application retrieves the user authentication cryptographic credentials from user authentication CryCre . If so at step access application unlocks remote smart card .

At step access application checks configuration file to determine whether its entitled applications and associated gateway addresses are stored or must be obtained dynamically.

If the application gateway data must be obtained at step access application establishes a secure channel with authorization module executing on controller and at step controller does its part towards establishing the secure channel.

At step access application requests its application entitlements and associated gateway addresses the request includes the hardware ID of remote device . At step authorization module receives the request.

At step authorization module validates the hardware ID of remote device by comparing the hardware ID in the request to the hardware ID stored for the user. If invalid authorization module sends an ACCESS DENIED message to remote device . At step access application receives the ACCESS DENIED message and must contact the domain administrator. If valid at step authorization module retrieves the application gateway data from user data along with notice of i whether any new user application security information is available ii whether the new user application cryptographic credentials should be stored or cached i.e. used only for one session and iii whether the new application security information is requested on demand remote device generates a public private key pair and requests a certificate or pre issued cryptographic credentials are requested.

At step authorization module provides the application gateway data to remote device . At step access application receives the list of application addresses. Processing continues at step .

At step access application retrieves its application entitlements and associated gateway addresses from configuration file . Processing continues at step .

At step access application checks the notice of whether any new application cryptographic credentials are required received at step . If no new application cryptographic credentials are required processing continues at step .

If the notice indicates new application cryptographic credentials are required at step access application checks whether the new user application security data should be stored or cached. If cached processing continues at step .

If the notice indicates that the new application security information should be stored then step is repeated once for each new application cryptographic credential.

At step similar to step access application checks which method it should use to obtain the CryCre. If the method is on demand issuance of a security certificate as indicated by A1 in a circle the processing of is performed. If the method is to use pre issued cryptographic credentials as indicated by B1 in a circle the processing of is performed.

At step the user selects the application that s he wishes to use such as application executing on application server typically via a graphical user interface provided by access application on remote device .

At step access application establishes a secure channel with authorization module executing on gateway and at step gateway does its part towards establishing the secure channel.

At step access application determines from step whether it needs new cached session only application cryptographic credentials for its desired use of the selected application. If so as indicated in by B2 in a circle the processing of is performed except that step is not performed and processing returns to instead of going to CC. In an alternate embodiment not shown access application generates a public private key pair and requests a certificate on demand i.e. the processing of creating ephemeral credentials for use only during the session.

At step access application sends a request for access to the selected application to gateway . At step authorization module receives the request. Processing continues at step or step .

Turning to at step authorization module executing on gateway establishes a secure channel with authorization module executing on controller and at step controller does its part towards establishing the secure channel.

At step authorization module sends a request to authorization module to determine whether the user of remote device is authorized to use any applications. At step authorization module receives the request.

At step authorization module checks user data to determine whether the user is authorized to use any applications. The check includes examining the general access policy for the user and any specific restrictions for use of this application. The check also includes examining certificate revocation data for certificates issued by controller and checking certificate revocation data via a process not shown for brevity for certificates issued by third party .

If the user is not authorized i.e. the user s cryptographic credentials are incorrect such as because they have been revoked or an unauthorized user is trying to gain access then authorization module sends a NOT AUTHORIZED message to authorization module . At step authorization module receives the NOT AUTHORIZED message. At step authorization module sends an ACCESS DENIED message to remote device . At step access application receives the ACCESS DENIED message and processing is complete. The user must contact the domain administrator to determine how to re register.

If the user is authorized then at step authorization module retrieves the applications and corresponding gateway addresses that the user is entitled to access from user data and provides this list to gateway . At step authorization module receives the applications addresses data.

At step authorization module checks whether the selected application received from the user at step matches one of the entitled applications received from controller at step .

If the selected application does not match one of the entitled applications then at step authorization module sends an APPLICATION DENIED message to remote device . At step access application receives the APPLICATION DENIED message and processing is complete. The user must contact the domain administrator to determine how to properly become entitled to use the application.

If the selected application matches one of the entitled applications then at step authorization module establishes a secure channel with application executing on application server and at step application server does its part towards establishing the secure channel.

At step application is used by the user. Data to from application is transmitted on the application s secure channel to gateway . The vertical lines on the box at step indicate this is a procedure. See step .

At step the user uses application . Data to from the user is transmitted on the user s secure channel to gateway . The vertical lines on the box at step indicate this is a procedure. See step .

At step authorization module serves as a proxy for the data session between the user and application receiving data on one of the user application secure channels and transmitting it on the other of the user application secure channels. The vertical lines on the box at step indicate this is a procedure. See step .

A first difference is that in at step controller sends a list of entitled applications and their addresses to gateway . When there are a large number of applications this can become unwieldy. Instead in after controller determines that a user is authorized gateway asks the controller if the user is authorized to use the selected application. The fact that the gateway has a two part authorization request protocol with the controller in results in better security than the one part authorization request protocol of .

At step if the user is authorized authorization module provides user authorization to gateway . At step authorization module receives the user authorization.

At step authorization module asks controller whether the user is entitled to use the selected application i.e. application . At step authorization module receives the request.

At step authorization module checks user data and determines whether the user is authorized to use application .

If the user is not authorized to use application authorization module sends an APPLICATION DENIED message to gateway . At step authorization module receives the APPLICATION DENIED message. Processing continues at step as in .

If the user is authorized to use application at step authorization module notifies gateway that the user is entitled. At step authorization module receives the notice that the user is entitled to use application .

A second difference is that in at step gateway establishes a secure channel to application . This can be time consuming possibly leading to time out delays at remote device . Instead in gateway uses a pre established channel to application .

At step authorization module allocates one of the channels from the pool established in step . Processing continues at steps as in .

At step remote sends data to and receives data from application . At step application receives data from and sends data to remote . At step gateway functions as a proxy for the sending and receiving between remote and application .

At step application requests that remote device perform a cryptographic operation using its user application cryptographic credentials. At step gateway forwards this request to remote device . At step remote device receives the request.

At step access application executing on remote device checks whether a remote smart card is present. If not at step access application retrieves the user application cryptographic credentials from user application CryCre . If remote smart card is present access application unlocks smart card with the Upassword and obtains the user application cryptographic credentials.

At step access application checks whether the user application cryptographic credentials are encrypted. If so at step access application decrypts the user application cryptographic credentials per the attached tags typically using the user authentication cryptographic credentials or if present the user encryption cryptographic credentials.

At step access application uses the user application cryptographic credentials to perform the cryptographic operation requested by application .

At step access application sends the results of the cryptographic operation to gateway . At step gateway forwards the results to application . At step application receives the results.

At step application determines whether the results are valid that is the results demonstrate that remote device possesses the appropriate user application cryptographic credentials. If not application sends a USAGE DENIED message to gateway . At step gateway forwards the message to remote device . At step remote device receives the USAGE DENIED message and may need to contact the domain administrator if use of the protected application function is needed or if application also halts due to the invalid results. In other embodiments the user may continue using application except for the protected application function

If the results demonstrate that remote device possesses the user application cryptographic credentials then application proceeds to step and continues allowing remote device to use application .

At step access application checks configuration data to determine whether it should check for new cryptographic credentials that is whether it stores its application entitlements or receives them dynamically. This is a bit like step of except that there is no gateway address associated with the application entitlements since either a non secure channel is used or remote device establishes a secure channel without using gateway .

Depending on the domain administrator s preference the configuration data for remote device can be set to cause remote device to combine its requests for new user application cryptographic credentials for secure data sessions and non secure data sessions or to cause remote device to make separate requests as shown in .

If access application determines that it should not check for new user application cryptographic credentials then processing continues at step .

If access application determines that it should check for new application cryptographic credentials then processing continues at step .

At step access application establishes a secure channel with authorization module executing on controller and at step controller does its part towards establishing the secure channel.

At step access application requests its new application cryptographic credentials the request includes the hardware ID of remote device . At step authorization module receives the request.

At step authorization module validates the hardware ID of remote device by comparing the hardware ID in the request to the hardware ID stored for the user. If invalid authorization module sends an ACCESS DENIED message to remote device . At step access application receives the ACCESS DENIED message and must contact the domain administrator. If valid at step authorization module sends a notice of i whether any new user application security information is available ii whether the new user application security data should be stored or cached i.e. used only for one session and iii whether the new application security information is dynamically provided as certificates or pre stored cryptographic credentials.

At step access application receives the notice. At step access application checks the notice of whether any new application security information is available. If no new security information is available processing continues at step .

If the notice indicates new application security information is available processing continues at step .

At step access application checks whether the new user application security data should be stored or cached. If cached processing continues at step .

If the notice indicates that the new application security information should be stored then step is repeated once for each new application security information. Step is similar to step .

At step remote device sends a request to application executing on web server using network for a non secure channel. In other embodiments remote device establishes a secure channel with web server via a technique outside the scope of the instant application. At step application receives the request.

An instance of an application that generally permits non secure use but sometimes requires that a user verify their identity to permit use is a medical chat board where anyone can read the chat board posting and anyone can post a question but only a verified doctor can post an answer.

At step application checks whether it needs to verify the identity of the user that made the request. If not processing continues at step .

If the user s identity needs to be verified at step application sends a request for a cryptographic operation to remote device . At step remote device receives the request.

At step access application sends the results of the cryptographic operation to application . At step application receives the results.

At step application determines whether the results are valid that is the results demonstrate that remote device possesses the user application cryptographic credentials. If not application sends a USAGE DENIED message to remote device . At step remote device receives the USAGE DENIED message and must contact the domain administrator.

If the results demonstrate that remote device possesses the user application cryptographic credentials then application proceeds to step .

At step application responds to the request from remote device to use application . If the user wants to continue processing returns to step .

Although illustrative embodiments of the present invention and various modifications thereof have been described in detail herein with reference to the accompanying drawings it is to be understood that the invention is not limited to these precise embodiments and the described modifications and that various changes and further modifications may be effected therein by one skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.

