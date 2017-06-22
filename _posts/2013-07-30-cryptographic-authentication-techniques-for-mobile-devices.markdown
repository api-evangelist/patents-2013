---

title: Cryptographic authentication techniques for mobile devices
abstract: A method of authenticating a computing device to a back-end subsystem. In one embodiment a prover black-box in the computing device regenerates a credential containing a key pair from a PIN and a protocredential, and authenticates cryptographically to a verifier black-box in the back-end subsystem; then the verifier black-box sends an authentication token to the prover black-box as verifiable confirmation of the cryptographic authentication, the prover black-box sends the authentication token to an application front-end in the computing device, the application front-end sends the authentication token to an application back-end in the back-end subsystem, and the application back-end verifies the authentication token.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09185111&OS=09185111&RS=09185111
owner: Pomian & Corella, LLC
number: 09185111
owner_city: Carmichael
owner_country: US
publication_date: 20130730
---
This application is a continuation in part of U.S. application Ser. No. 13 925 824 filed Jun. 24 2013 which claims priority to U.S. Provisional Application Ser. No. 61 663 569 filed on Jun. 23 2012 U.S. Provisional Application Ser. No. 61 677 011 filed on Jul. 30 2012 U.S. Provisional Application Ser. No. 61 804 638 filed on Mar. 23 2013 and U.S. Provisional Application Ser. No. 61 809 790 filed on Apr. 8 2013 all of which applications are incorporated by reference herein.

Passwords are commonly used for returning user authentication to a software application back end across a network such as the Internet but they have well known security weaknesses including vulnerability to phishing attacks breaches of back end database security and reuse at malicious sites. Furthermore passwords are ill suited for use on mobile devices such as smart phones and tablets entering a strong password with letters digits and punctuation on a small touch screen keyboard is cumbersome and password characters are exposed to shoulder surfing because they are echoed by the keyboard as they are being typed in an effort to prevent typographical errors.

Cryptography provides alternatives for returning user authentication that are more secure and better suited for mobile devices. For example a mobile device could authenticate to an application back end by proving knowledge of a private key that is part of a key pair pertaining to a public key cryptosystem a hash of the public key that is part of the same key pair having been previously registered with the application back end the user would be indirectly authenticated as the owner of the device. This is more secure than authentication with a password because the private key is not sent to the application back end or stored in a back end database and it is better suited for mobile devices because it does not require typing a password.

Cryptography also allows a user to authenticate to an application back end as having an identity or attributes asserted by a third party without the third party being involved in the authentication transaction. For example a computing device owned by the user may generate a key pair pertaining to a public key cryptosystem. The user may ask the third party to sign a public key certificate binding the public key that is part of the key pair to one or more identifiers and or attributes that the third party is authoritative for and may then store the public key certificate in the computing device together with the private key that is part of the key pair. The computing device may then authenticate to the application back end by sending the certificate and proving knowledge of the private key. The user controlling the device is then indirectly authenticated as being entitled to the identifier and or attributes.

Cryptography is currently used successfully for user authentication in some specific use cases such as authentication of a US federal employee to the information system of a US federal agency using a public key certificate and its associated private key stored in a Personal Identity Verification PIV card connected to a personal computer. But cryptographic authentication is not broadly used outside such specific use cases.

One drawback is that it is difficult to implement for application developers. While user authentication with a password simply requires transmission of the password from a user s device to the application back end cryptographic authentication requires execution of a cryptographic protocol involving multiple cryptographic operations such as digital signatures verification of digital signatures computation of cryptographic hashes etc. by multiple parties and transmission of multiple messages between those parties. The details of the individual cryptographic operations performed by the parties to a cryptographic protocol are typically hidden from application developers in cryptographic libraries but application developers must still cope with many difficulties. They must understand the cryptographic protocol install cryptographic libraries ensure that all parties agree on the parameters of the protocol implement the sequence of messages and cryptographic operations required by the protocol and handle errors and exceptions.

Another drawback is that it relies on one or more secrets stored in the user s device such as a private key. Mobile devices are easily lost or stolen hence the user s device may easily be captured by an adversary. If no precautions are taken the adversary may obtain the secrets used for cryptographic authentication and use them to impersonate the user. One precaution that can be taken is to encrypt such secrets using an encryption key derived from a password supplied by the user. However prior art techniques for encrypting the secrets allow the adversary to launch an offline dictionary attack against the password after capturing the device and obtaining the encrypted secrets. To resist the attack the user must use a high entropy password which is not practical when the password must be entered on a small touch screen keyboard.

Hence there is a need for cryptographic authentication techniques well suited for mobile devices that are easier to implement for application developers and provide more effective protection against an adversary who captures a device.

Improved techniques are provided for cryptographic authentication of a computing device to a back end subsystem which are well suited for mobile devices are easy for application developers to implement and provide effective protection against an adversary who captures the computing device.

In one embodiment a prover black box in the computing device regenerates a credential containing a key pair from a PIN and a protocredential and authenticates cryptographically to a verifier black box in the back end subsystem by proving knowledge of the private key portion of the credential then the verifier black box sends an authentication token to the prover black box as verifiable confirmation of the cryptographic authentication the prover black box sends the authentication token to an application front end in the computing device the application front end sends the authentication token to an application back end in the back end subsystem and the application back end verifies the authentication token.

This Detailed Description refers to the accompanying drawings which are a part hereof and illustrate examples of embodiments of the invention. It is to be understood that other embodiments are possible and that the features of different exemplary embodiments can be combined together unless otherwise stated.

 The terms prover and verifier refer to roles performed in cryptographic authentication. A prover is a computer or computing module that proves possession of one or more cryptographic credentials while a verifier is a computer or computing module that verifies a proof of possession submitted by a prover. The term black box refers to a computing module that is dedicated to a specific purpose and can be used without an understanding of its internal workings. The term prover black box refers to a computing module that qualifies as a black box and plays the role of prover. The term verifier black box refers to a computing module that qualifies as a black box and plays the role of verifier. 

The computing device is controlled by a user via a user interface subsystem . In one embodiment the device is a mobile device such as a smart phone or a tablet and the user interface subsystem comprises a touch screen built into the device. In another embodiment the device is a laptop computer and the user interface subsystem comprises a keyboard and a trackpad built into the computer. In another embodiment the device is a desktop computer and the interface subsystem comprises a keyboard and a mouse connected to the computer. In another embodiment the device is a smart card connected to a computer system and user interface subsystem is part of the computer system.

 The user interface subsystem is omitted from some of the subsequent figures for lack of space but is to be understood as being present and connected or built into the computing device . 

The computing device authenticates to a back end subsystem over a network such as the Internet. Authentication of the device indirectly authenticates the user as the owner of the device.

The user interacts with an application front end running on the device which communicates over the network with an application back end that is part of the back end subsystem. The prover black box runs on the computing device and communicates with the verifier black box over the network. In some embodiments the application back end and the verifier black box communicate over the same network that connects the device to the application back end and the verifier black box while in other embodiments they communicate over a separate network such as a private network and in yet other embodiments they are implemented by software running on the same machine.

Within the device the application front end and the prover black box communicate with each other by exchanging messages.

In one embodiment the computing device is a mobile device equipped with the iOS operating system the prover black box and the application front end are separate iOS apps and messages exchanged between the prover black box and the application front end are implemented as URLs with custom schemes as explained in the sections entitled Communicating with Other Apps and Implementing Custom URL Schemes of the iOS App Programming Guide .

 The terms iOS app and Android app are used herein with their usual meanings to refer to computer programs running on computing devices equipped with the iOS and Android operating systems respectively. The unabbreviated term application on the other hand is used more broadly to refer to a computer program that may be distributed over multiple computers. For example an application may have a front end component running on a mobile device and aback end component running on a server connected to the device over a network. Different components of an application may be developed and deployed by different organizations. 

In one embodiment the computing device is a mobile device equipped with the Android operating system the prover block box and the application front end are separate Android apps and messages exchanged between the prover black box and the application front end are implemented as Intent objects as explained in the Android API Guide entitled Intents and Intent Filters . In an alternative embodiment the computing device is also equipped with the Android operating system and the messages exchanged between the prover black box and the application front end are also implemented as Intent objects but the prover black box and the application front end are parts of the same Android app each comprising one or more components of the app.

In one embodiment the prover black box is a software library linked to the application front end messages from the application front end to the prover black box being implemented as Application Programming Interface API function calls and messages from the prover black box to the application front end as callbacks.

At the application front end asks the prover black box to authenticate cryptographically to the verifier black box .

At the prover black box authenticates cryptographically to the verifier black box by proving possession of one or more cryptographic credentials. Then the process continues at .

At the process fails if cryptographic authentication failed at . Otherwise the process continues at .

At the verifier black box sends to the prover black box an authentication token providing verifiable confirmation of the cryptographic authentication. Then the process continues at .

At the prover black box sends the authentication token to the application front end. Then the process continues at .

At the application front end authenticates to the application back end by sending the authentication token. Then the process continues at .

At the application back end attempts to verify the authentication token as being confirmation of a cryptographic authentication. Then the process continues at .

Thus application specific functionality is embodied in the application front end and the application back end which are developed by developers skilled in the art of application development whereas cryptographic authentication functionality is encapsulated in the prover black box and the verifier black box which are developed by developers skilled in the art of cryptographic protocol development and which are made available for use by any number of different applications. This allows application developers to implement cryptographic authentication easily by making use of pre existing prover and verifier black boxes.

In one embodiment the verifier black box and the application back end are virtual servers known as Elastic Computing Cloud EC2 machine instances made available for rent by the hour by Amazon Web Services AWS and located within a Virtual Private Cloud VPC internal to the back end subsystem so that they communicate securely over a virtual private network. The verifier black box virtual server is pre configured by developers skilled in the art of implementing cryptographic protocols and made available as a virtual appliance on the AWS Marketplace. The application back end virtual server has access to a relational database provided by the AWS Relational Database Service RDS .

 The term appliance is to be understood as referring to a physical or virtual machine that has been pre configured as a black box dedicated to a specific purpose and made generally available for use by applications to that purpose. 

The database comprises a table of user records and a table of device records . Each user record corresponds to an application user and comprises a USER RECORD HANDLE field that uniquely identifies the record within the table as well as a collection of fields containing user data. Each user record is indexed by the value of the USER RECORD HANDLE field for efficient retrieval of the record given that value. Each device record corresponds to a device that an application user has registered for use with the application and comprises a DEVICE RECORD HANDLE field that uniquely identifies the record a HASH OF PUBLIC KEY field and a USER RECORD HANDLE field . The value of the USER RECORD HANDLE field refers to the user record for the user who registered the device. Each device record is indexed by the value of the DEVICE RECORD HANDLE field for efficient retrieval of the record given that value.

 The term handle is used herein as a synonym for the term primary key of database terminology to avoid confusion between database keys and cryptographic keys. Names of record fields are herein written in uppercase. Fields are are different fields of different records which have the same name USER RECORD HANDLE . 

The prover black box has a credential comprising a device record handle and a key pair pertaining to a digital signature public key cryptosystem such as one of the public key cryptosystems DSA ECDSA or RSA specified in the Digital Signature Standard DSS publication FIPS PUB 186 4 of the National Institute of Standards and Technology NIST . The device record handle identifies a device record in the database that contains the handle as the value of the DEVICE RECORD HANDLE field . That record is the one corresponding to computing device and it contains a hash of the public key portion of the key pair as the value of the HASH OF PUBLIC KEY field .

 The key pair consists of a collection of cryptographic parameters. In preferred embodiments the private key and public key comprise all the key pair parameters needed to sign and verify a signature respectively. For example in such embodiments with the notations of Section 4.1 of the DSS a DSA key pair consists of the parameters p q g x and y. The private key is p q g x and the public key is p q g y . By contrast the DSS does not consider domain parameters as being part of the private and public keys. For example in the case of the DSA cryptosystem the DSS refers to x as the private key and y as the public key omitting the domain parameters p q and g.

At the application front end sends a message to the prover black box asking it to authenticate cryptographically to the verifier black box . Then the process continues at .

At the prover black box authenticates cryptographically to the verifier black box. To that purpose it establishes a TLS connection to a cryptographic authentication endpoint of the verifier black box. The acronym TLS refers to the Transport Layer Security protocol of the Internet Engineering Task Force which is a successor to the Secure Sockets Layer protocol. During the TLS handshake the verifier black box authenticates to the prover black box by sending a TLS server certificate and proving knowledge of the corresponding private key. After the TLS connection has been established the verifier black box sends a random high entropy nonce to the prover black box over the TLS connection. The verifier black box and the prover black box separately construct a challenge by computing a cryptographic hash of the nonce and the TLS server certificate. The prover black box signs the challenge using the private key that is part of the key pair and sends the signature the public key that is part of the key pair and the device record handle to the verifier black box over the TLS connection by signing the challenge the prover black box proves knowledge of the private key by sending the device record handle and proving knowledge of the private key the prover black box proves possession of the credential . Then the process continues at .

 A nonce is a random string that is only used once. The term random string is meant to encompass both a truly random string and a string generated by a pseudo random string generator or an entropy accumulator such as the dev urandom facility of Linux and other Unix systems. High entropy refers to an entropy that is high enough for the security objectives of a particular embodiment. In one embodiment all high entropy random strings have at least 256 bits of entropy. 

At the verifier black box verifies the signature using the public key that is part of the key pair. If the verification of the signature succeeds cryptographic authentication is successful and the process continues at . Otherwise the process fails.

At the verifier black box creates an authentication object shown in containing an authentication token a timestamp and authentication data . The authentication token is generated by the verifier black box as a high entropy random string. The authentication data comprises the device record handle received from the prover black box at step and a cryptographic hash computed by applying a cryptographic hash function to the public key also received at step . In one embodiment the cryptographic hash function is the hash function SHA 1 specified in the Secure Hash Standard SHS published by NIST as FIPS PUB 180 4 in alternative embodiments it is one of the other hash functions specified in the SHS. The authentication object is an element of an array of such authentication objects. Since the authentication token is a high entropy random string the authentication object is uniquely identified with high probability by the authentication token and hence is retrievable by the authentication token. In one embodiment the array of objects is stored in shared memory allocated in the verifier black box virtual server in an alternative embodiment the array of authentication objects is implemented as a table of authentication records within a relational database internal to the verifier black box virtual server each authentication object being referred to as an authentication record and being indexed by the authentication token. Then the process continues at .

At the verifier black box sends the authentication token to the prover black box over the TLS connection established at step as confirmation that cryptographic authentication was successful at . This confirmation is verifiable by using the authentication token to retrieve the authentication object created at as is done at step . Then the process continues at .

At the prover black box sends a message to the application front end containing the authentication token. Then the process continues at .

At the application front end authenticates to the application back end by sending the authentication token over a TLS connection. Then the process continues at .

At the application back end sends the authentication token to an authentication data retrieval endpoint of the verifier black box for verification over the virtual private network provided by the VPC . Then the process continues at .

At the verifier black box attempts to retrieve an authentication object containing the authentication token received at step and being recent enough i.e. having an age determined by the timestamp that is less than an age limit set by a security policy. If there is no such object the process fails. Otherwise the authentication token is deemed to have been verified as a confirmation of the cryptographic authentication that resulted in the creation of the object and the process continues at .

At the verifier black box sends the authentication data contained in the authentication object to the application back end over the virtual private network. The authentication data comprises the device record handle and the public key hash . Then the process continues at .

At the application back end looks in the database for a device record containing the device record handle in the DEVICE RECORD HANDLE field and the public key hash in the HASH OF PUBLIC KEY field . If no such record is found the process fails. Otherwise the process continues at .

At the application back end looks in the database for a user record whose USER RECORD HANDLE field has the same value as the USER RECORD HANDLE field of the device record found at step . If no such record is found the process fails. Otherwise the process continues at .

At the application back end sends user data contained in the user data fields of the user record found at step to the application front end over the same TLS connection used at step . Then the process terminates successfully the device has been successfully authenticated to the application back end as being the device corresponding to the device record found at step owned by the user corresponding to the user record found at step .

In one embodiment steps and are combined and implemented together using a join of the table of device records and the table of user records in a manner well known to developers skilled in the art of relational database query processing.

At the application front end stores a copy of the authentication token received at step in the memory location before forwarding it to the application back end at step .

At the application back end creates a login session record in the table of login session records comprising the authentication token received at step as the value of the SESSION ID field the device record handle contained in the authentication data received at step as the value of the DEVICE RECORD HANDLE field and an expiration time as the value of the EXPIRATION TIME field .

At the application front end sends the authentication token stored in the memory location to the application back end over a TLS connection. Then the process continues at .

At the application back end looks in the database for a login session record where the value of the SESSION ID field is the authentication token. If no such record is found the process fails. Otherwise the process continues at .

At the application back end checks if the current time is past the expiration time specified by the EXPIRATION TIME field of the login session record found at step . If so the process fails. Otherwise the process continues at .

At the application back end looks in the database for a device record whose DEVICE RECORD HANDLE field that has the same value as the DEVICE RECORD HANDLE field of the login session record found at step . If no such record is found the process fails. Otherwise the process continues at .

At the application back end looks in the database for a user record whose USER RECORD HANDLE field that has the same value as the USER RECORD HANDLE field of the device record found at step . If no such record is found the process fails. Otherwise the process terminates successfully the device has been successfully authenticated to the application back end as being the device corresponding to the device record found at step owned by the user corresponding to the user record found at step .

In one embodiment steps and are combined and implemented together using a join of the table of login session records the table of device records and the table of user records in a manner well known to developers skilled in the art of relational database query processing.

At the verifier black box constructs authentication data as at step of process . But instead of storing the data in an authentication object it creates the authentication token comprising the authentication data a creation timestamp and a signature on the authentication data and the timestamp. In one embodiment the signature is computed using a private key pertaining to a digital signature public key cryptosystem such as those specified in the DSS DSA ECDSA or RSA .

At instead of sending the authentication token to the verifier black box for verification as at step of process the application back end checks that the timestamp is not older than an age limit set by a security policy and verifies the signature using the public key associated with private key that the verifier black box used to compute the signature at step .

At the process fails if the verification of the signature failed at . Otherwise the process continues at .

At the application front end receives a request from the user via the user interface subsystem to register the computing device with the back end subsystem . If the user has previously registered another device the user supplies a registration code obtained from the other device otherwise the user supplies user data. The application front end retains the registration code or user data and sends a message to the prover black box asking it to generate a credential and a protocredential. Then the process continues at .

At the prover black box obtains the non stored secrets from the user via the user interface subsystem. Then the process continues at .

At the prover black box generates a credential and a protocredential from the non stored secrets. The protocredential will later be used in conjunction with the non stored secrets to regenerate the credential. Then the process continues at .

At the device uses the credential and the registration code or user data to register with the back end subsystem then discards the credential. Details of this step are illustrated hereinafter in . Then the process continues with step which takes place at authentication time while steps through take place at registration time.

At the application front end receives a request from the user via the user interface subsystem to authenticate the device to the back end subsystem and sends a message to the prover black box asking it to authenticate cryptographically to the verifier black box . Then the process continues at .

At the prover black box obtains the non stored secrets from the user via the user interface subsystem. In embodiments where the non stored secrets include a biometric sample the sample obtained at is not identical to the sample obtained at but will yield the same credential. Then the process continues at .

At the prover black box regenerates the credential from the protocredential and the non stored secrets. Then the process continues at .

At the computing device uses the credential to authenticate to the back end subsystem. Details of this step are illustrated hereinafter in . The credential is discarded after being used. Then the process terminates.

At the prover black box discards the credential and sends a message to the application front end containing the authentication token. Then the process continues at .

At the application front end sends the authentication token obtained from at step to the application back end over a TLS connection together with the registration code or user data received at step of process . Then process continues at .

At the application back end determines whether the user is a new user or an existing user for whom a corresponding user record exists in the table of user records based on whether user data or a registration code was received from the application front end at step . If user data was received the user is a new user and process continues at . If a registration code was received the user is an existing user and process continues at .

At the application back end creates a user record containing the user data in the user data fields and containing a new user record handle distinct from those of other user records in the USER RECORD HANDLE field . In one embodiment the new user record handle is obtained by incrementing a counter of user record handles in an alternative embodiment it is generated as high entropy random string which is distinct from existing user record handles with high probability. Then process continues at .

At the application front end finds a user record identified by the registration code. In one embodiment the registration code identifies the user record indirectly the registration code being a handle of a short lived registration record that in turn contains a user record handle that identifies the user record. Then process continues at .

the device record handle that is part of the authentication data received from the verifier black box at step in the DEVICE RECORD HANDLE field 

the public key hash that is part of the authentication data received from the verifier black box at step in the HASH OF PUBLIC KEY field and

the value of the USER RECORD HANDLE field of the user record created at step or found at step in the USER RECORD HANDLE field of the device record.

At the application back end sends a confirmation that the device has been registered successfully to the application front end over the same TLS connection used at step and the application front end communicates the confirmation to the user over the user interface subsystem. Then process terminates.

At the prover black box discards the credential used at step and sends a message to the application front end containing the authentication token. Then the process continues at .

At the application back end looks in the database for a device record whose DEVICE RECORD HANDLE field contains the device record handle that is part of the authentication data received from the verifier black box at step . If no such record is found the process fails. Otherwise process continues at .

At the application back end checks if the HASH OF PUBLIC KEY field of the device record found at step contains the public key hash that is part of the authentication data received from the verifier black box at step . If so process continues at . Otherwise it continues at .

At the application back end resets to 0 the CONSECUTIVE FAILURE COUNTER field of the device record. Then process continues at .

At the application back end increments by 1 the CONSECUTIVE FAILURE COUNTER field of the device record. Then process continues at .

At the application back end looks in the database for a user record whose USER RECORD HANDLE field has the same value as the USER RECORD HANDLE field of the device record found at step . If no such record is found process fails otherwise it continues at .

At the application back end checks if the value of the CONSECUTIVE FAILURE COUNTER field of the device record has reached a configured limit of consecutive failures in one embodiment the configured limit is 5. If the configured limit has been reached process continues at otherwise it fails.

At the application back end sends user data contained in the user data fields of the user record found at step to the application front end over the same TLS connection used at step . Then the process terminates successfully the device has been successfully authenticated to the application back end as being the device corresponding to the device record found at step owned by the user corresponding to the user record found at step .

At the application back end disables the device record found at step . In one embodiment the application back end disables the record by setting a value in a field of the record indicating that the record is disabled. In an alternative embodiment the application back end deletes the record from the database. Once the record is disabled the device must be registered again with the back end subsystem before it can be used by the application. After the application back end disables the record process fails.

Some embodiments differ from embodiments discussed so far in that the credential used at authentication time does not comprise a complete key pair. A complete key pair is generated at registration time and used to register the device but the credential regenerated at authentication time comprises the private but not the public key portion of the key pair. In such embodiments the prover black box authenticates to the verifier black box by proving knowledge of the private key and sending the device record handle but not the public key. The verifier black box has access to the database and uses the device record handle to locate the device record which contains the public key rather than a hash of the public key. The verifier black box uses the public key found in the record to verify the proof of knowledge of the private key. The verifier black box retrieves user data from the user record referenced by the device record and stores it as authentication data in the authentication object instead of the hash of the public key. The user data is delivered to the application back end upon presentation of the authentication token.

At the prover black box generates the device record handle as a random high entropy string so that it is different from any other device record handles with high probability. In alternative embodiments a unique device record handle is allocated by the database management system that manages the database when the device record is created and added to the protocredential at that time. Then the process continues at .

At the prover black box generates the supplemental parameters and computes a Key Pair Regeneration Key KPRK from the supplemental parameters and the non stored secrets. The KPRK is of bitlength N 64 N being the bitlength of q. Then the process continues at .

At the prover black box generates the parameters p q and g as described in Section 4.3.1 and appendices A.1 and A.2 of the DSS. Then the process continues at .

At the prover black box computes an integer c as specified at step of the process described in Appendix B.1.1 of the DSS using the KPRK instead of the string called returned bits in the DSS. Then the process continues at .

At the prover black box computes the parameter x as specified in step of the process described in Appendix B.1.1 of the DSS using the integer c computed at step . Then the process continues at .

At the prover black box computes the parameter y as specified in step of the process described in Appendix B.1.1 of the DSS. Then the process continues at .

At the prover black box assembles the credential consisting of the device record handle and the parameters p q g x and y encoded as strings of bitlength L N L N and L respectively. Then the process continues at .

At the prover black box assembles the protocredential consisting of the device record handle the cryptosystem related parameters p q and g encoded as strings of bitlength L N and L respectively and the supplemental parameters. Then the process terminates.

At the prover black box computes a KPRK of bitlength N 64 N being the bitlength of the parameter q in the protocredential from the supplemental parameters in the protocredential and the non stored secrets. Then the process continues at .

At the prover black box computes an integer c as specified at step of the process described in Appendix B.1.1 of the DSS using the KPRK instead of the string called returned bits in the DSS. Then the process continues at .

At the prover black box computes the parameter x from the integer c as specified in step of the process described in Appendix B.1.1 of the DSS. Then the process continues at .

At the prover black box computes the parameter y as specified in step of the process described in Appendix B.1.1 of the DSS. Then the process continues at .

At the prover black box assembles the credential consisting of the device record handle found in the protocredential the parameters p q g found in the protocredential encoded as strings of bitlength L N and L respectively and the newly computed parameters x and y encoded as strings of bitlength N and L respectively. Then the process terminates.

At the prover black box generates the salt as a random high entropy string using an entropy accumulator such as the dev urandom facility of Linux and other Unix systems. Then the process continues at .

At the prover black box computes the KPRK by applying the HMAC based Extract and Expand Key Derivation Function HKDF described in Request For Comments RFC 5869 of the Internet Engineering Task Force IETF to the passcode used as Input Keying Material IKM and the salt the length of output being N 64 bits where N is the bitlength of the parameter q.

 Other key derivation functions such as PBKDF2 described in Section 5.2 of RFC 2892 of the IETF are used in alternative embodiments. Then the process terminates.

At the prover black box computes a KPRK by applying the HKDF key derivation function to the PIN used as Input Keying Material IKM and the salt the length of output being N 64 bits where N is the bitlength of the parameter q. Other key derivation functions such as PBKDF2 are used in alternative embodiments. Then the process continues at .

At the prover black box generates the device record handle as in step of process . Then the process continues at .

At the prover black box generates the supplemental parameters and computes an M bit Key Pair Regeneration Key KPRK from the supplemental parameters and the non stored secrets. In some embodiments the set of non stored secrets consists of a passcode the supplemental parameters consist of a random high entropy salt generated by an entropy accumulator such as dev urandom and the KPRK is computed by generating M bits of output from HKDF applied to the passcode playing the role of Input Keying Material IKM and the salt. Other key derivation functions such as PBKDF2 are used in alternative embodiments. Then the process continues at .

At the prover black box computes the parameters p q and g as described in Section 4.3.1 and appendices A.1 and A.2 of the DSS. Then the process continues at .

At the prover black box generates the parameter x computing it from an integer c that is itself computed from randomly generated bits as described in steps of the process specified in Appendix B.1.1 of the DSS. Then the process continues at .

At the prover black box computes the parameter y as specified in step of the process described in Appendix B.1.1 of the DSS. Then the process continues at .

At the prover black box generates a random 128 bit string to be used as the initialization vector . Then the process continues at .

At the prover black box encrypts the bare parameter x encoded as an N bit string without padding using AES in CFB mode with the KPRK as encryption key and the string generated at step as initialization vector. Then the process continues at .

At the prover black box computes an M bit KPRK from the supplemental parameters in the protocredential and the non stored secrets. Then the process continues at .

At the prover black box decrypts the encrypted parameter using AES in CFB mode with the KPRK as decryption key using the initialization vector in the protocredential obtaining x. Then the process continues at .

At the prover black box computes the parameter y as specified in step of the process described in Appendix B.1.1 of the DSS. Then the process continues at .

At the prover black box assembles the credential consisting of the device record handle the parameters p q g found in the protocredential encoded as strings of bitlength L N and L respectively and the newly computed parameters x and y encoded as strings of bitlength N and L respectively. Then the process terminates.

At the prover black box computes a KPRK by applying the HKDF key derivation function to the PIN used as Input Keying Material IKM and the salt the length of output being M bits. Other key derivation functions such as PBKDF2 are used in alternative embodiments. Then the process continues at .

One of the advantages of the present invention is that it provides better protection against an adversary who captures the computing device and is able to read all data stored in the device.

In cryptographic authentication with a key pair according to prior art the key pair is stored in the device either in the clear or wrapped in an ASN.1 data structure the wrapper that is encrypted using a key derived from a passcode. If the key pair is in the clear the adversary can use it to authenticate. If the key pair is wrapped and encrypted the adversary can mount an offline dictionary attack against the passcode. To test a passcode the adversary derives the corresponding key and uses it to decrypt the encrypted wrapper. If the passcode is incorrect the result of the decryption has a negligible probability of being well formed for three different reasons it is unlikely to be a well formed wrapper even if it is a well formed wrapper at least some of the purported parameters in the wrapper are unlikely to have their expected properties such as being prime and even if all the purported parameters have their expected properties the purported private key and public key portions of the key pair are unlikely to match each other.

By contrast embodiments of the present invention provide effective countermeasures against offline attacks.

In one embodiment the credential illustrated in is regenerated from the protocredential illustrated in and a 4 digit PIN using the credential regeneration process of then the credential is used for authentication using the process of . When an adversary applies the credential regeneration process to a guess of the PIN rather than to the correct PIN the probability of the process producing well formed output well formed output being a credential as illustrated in is 100 even though the probability of the process producing correct output correct output being the credential that was used at registration time is close to 1 in 10 000 when PIN guesses are uniformly distributed. There are 10 000 4 digit PINs and the probability that two PINs produce the same credential is negligible. If the public key y is treated as a shared secret between the computing device and the back end subsystem the adversary cannot mount an offline attack. The adversary can only test a guessed PIN by authenticating online to the back end subsystem rather than offline and the back end subsystem limits the number of guesses at step of process .

In another embodiment the credential illustrated in is regenerated from the protocredential illustrated in and a 4 digit PIN using the process of then the credential is used for authentication using the process of . The protocredential includes a ciphertext . But the ciphertext is the encryption of the single bare parameter. No ASN.1 wrapping is applied to the parameter before encrypting and no public key is included in the protocredential. When an adversary applies process to a guess of the PIN rather than to the correct PIN the output of the process is not necessarily well formed because the result of decrypting the ciphertext with an incorrect key at step may not be in the interval 1 q 1 that the parameter x belongs to. However the result of the decryption is close to uniformly distributed over the binary strings of same bitlength N as q and q is greater than 2 N so the probability of the output being well formed is at least 50 even though the probability of the process producing correct output correct output being the credential that was used at registration time is 1 in 10 000 when PIN guesses are uniformly distributed. There are 10 000 4 digit PINs and the probability that two PINs produce the same credential is negligible. If the public key y is treated as a shared secret between the computing device and the back end subsystem the adversary cannot mount an effective offline attack. At least every other PIN guess will result in well formed output and will have to be tested online rather than offline by authenticating to the back end subsystem which sets a limit on the number of guesses at step of process . In one embodiment where the limit is 5 the adversary will be able to make only about 10 or fewer guesses before the limit is reached and the application back end disables the device record at step of process .

Several biometric key generation methods have been described in the literature for computing a biometric key from a biometric sample and auxiliary data also called helper data . At enrollment time the user provides an enrollment biometric sample which is used to generate the biometric key and the auxiliary data. In some methods the biometric key is independent of the sample. At authentication time the user provides an authentication sample and the biometric key is computed from the biometric sample and the auxiliary data. The biometric key computed at authentication time is the same as the biometric key generated at enrollment time with moderately high probability even though the authentication sample is not identical to the enrollment sample as long as the authentication sample is genuine.

One biometric key generation method is described in the Technical Report Number 640 of the Computer Laboratory of the University of Cambridge entitled Combining cryptography with biometrics effectively by Feng Hao Ross Anderson and John Daugman dated July 2005. References to other biometric key generation methods can be found in Sections 3.3 and 3.4 of the review article entitled Biometric Template Security by Anil K. Jain Karthik Nandakumar and Abhishek Nagar in the EURASIP Journal on Advances in Signal Processing Volume 2008 Article ID 579416.

Any biometric key generation method can be combined with the present invention to enable the use of a biometric sample as a non stored secret for regeneration of a credential from a protocredential and a set of non stored secrets. Biometric enrollment takes place when the computing device is registered with the back end subsystem so enrollment time is registration time.

At the prover black box generates the auxiliary data and a biometric key from the enrollment biometric sample according to the biometric key generation method. Then the process continues at .

At the prover black box generates the salt as a random high entropy string using an entropy accumulator such as the dev urandom facility of Linux and other Unix systems. Then the process continues at .

At the prover black box computes the KPRK by applying a key derivation function such as HKDF to the biometric key used as Input Keying Material IKM and the salt the length of output being N 64 bits where N is the bitlength of the parameter q. Then the process terminates having computed the KPRK and the set of supplemental parameters consisting of the auxiliary data and the salt.

At a biometric key is computed from the auxiliary data and the biometric sample according to the biometric key generation method. Then the process continues at .

At the prover black box computes the KPRK by applying HKDF to the biometric key used as Input Keying Material IKM and the salt the length of output being N 64 bits where N is the bitlength of the parameter q. Then the process terminates.

Although specific embodiments have been illustrated and described herein it will be appreciated by those of ordinary skill in the art that a variety of alternate and or equivalent implementations may be substituted for the specific embodiments shown and described without departing from the scope of the present invention. This application is intended to cover any adaptations or variations of the specific embodiments discussed herein.

