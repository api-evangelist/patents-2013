---

title: Secure storage and retrieval of data in a database with multiple data classes and multiple data identifiers
abstract: Secure storage and retrieval of data is provided with multiple data classes and data identifiers. Data values of a client are stored by receiving one or more authentication sets, at least one data value, an associated data class of the data value and a pseudo-random client value; calculating a data seed value based on the pseudo-random client value, a pseudo-random server value and the associated data class of the data value; generating a random data index value; generating a database index value based on the data seed value and the random data index value; storing the database index value; and providing the random data index value to the client. The client can be authenticated at the time of storage based on the one or more authentication sets. The authentication of the client and the storage of the data can be atomic such that only authenticated clients store the one or more data values. Techniques are also provided for the retrieval of stored data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09455973&OS=09455973&RS=09455973
owner: EMC Corporation
number: 09455973
owner_city: Hopkinton
owner_country: US
publication_date: 20131224
---
The present application is related to U.S. patent application Ser. No. 13 931 188 filed Jun. 28 2013 entitled Cryptographically Linking Data and Authentication Identifiers Without Explicit Storage of Linkage now U.S. Pat. No. 9 288 049 incorporated by reference herein.

The present invention relates generally to techniques for secure storage and retrieval of data in a database.

A user must often authenticate with a given authentication secret to gain access to a certain data secret. No other authentication secret should be able to be used to gain access to the associated data secret. In order to link data secrets with a corresponding authentication secret e.g. defining which data secret is owned by or associated with which authentication secret a look up table is typically employed in which each data identifier DataId for a given data secret is matched up with the authentication identifier AuthId of the corresponding authentication secret that owns the data secret. The look up table association however is explicitly stored in the server s database.

From a security perspective explicitly storing the association between data secrets and corresponding authentication secrets means that an attacker who steals the database will obtain the association between data secrets and corresponding authentication secrets. If for instance the attacker knows that a certain authentication secret belongs to a user of interest then the attacker may wish to concentrate their efforts on obtaining and recovering the data secrets associated with the authentication secret for the user of interest the data secrets may be individually protected at the server .

U.S. patent application Ser. No. 13 931 188 filed Jun. 28 2013 entitled Cryptographically Linking Data and Authentication Identifiers Without Explicit Storage of Linkage discloses methods and apparatus for cryptographically linking data identifiers and authentication identifiers without storing the association between the authentication and data secrets in the database of the server. While the disclosed techniques effectively cryptographically link authentication values and data values without having an explicit in database look up table a need still remains for improved techniques for secure storage and retrieval of data in a database with multiple data classes and multiple data identifiers. A further need exists for additional techniques for mathematically determining the identifiers.

Generally methods and apparatus are provided for secure storage and retrieval of data in a database with multiple data classes and multiple data identifiers. According to one aspect of the invention one or more data values of a client are stored by a server by receiving from the client one or more authentication sets at least one data value an associated data class of the at least one data value and a pseudo random client value calculating a data seed value based on the pseudo random client value a pseudo random server value and the associated data class of the at least one data value generating a random data index value generating a database index value based on the data seed value and the random data index value storing the database index value and providing the random data index value to the client.

According to another aspect of the invention the client is authenticated at the time of storage based on the one or more authentication sets. The authentication sets comprise for example an authentication value that the client has previously provided to the server and an authentication index that the server has provided to the client in response to the client previously providing the authentication value. In one exemplary embodiment the authentication of the client and the storage of the data are atomic steps such that only authenticated clients store the one or more data values.

According to another aspect of the invention the client can retrieve data by providing one or more authentication sets a random data index value of at least one data value that the client would like to obtain from storage an associated data class of the at least one data value and a pseudo random client value.

The disclosed techniques for secure storage and retrieval of data in a database of the illustrative embodiments overcome one or more of the problems associated with the conventional techniques described previously and provide improved security and functionality by providing multiple data classes and multiple data identifiers. These and other features and advantages of the present invention will become more readily apparent from the accompanying drawings and the following detailed description.

The present invention will be described herein with reference to an example network based communication system in which one or more clients communicate over a network with one or more servers. It is to be appreciated however that the invention is not restricted to use in this or any other particular system configuration.

Aspects of the present invention provide improved techniques for secure storage and retrieval of data in a database with multiple data classes and multiple data identifiers. According to one aspect of the invention multiple authentication identifiers are provided that can be linked together and used to authenticate a user. For example multiple authentication identifiers can be used to link a current and one or more previous passwords to enable password history checking and thereby ensure that the current password does not match any of the previous N passwords. In a further variation multiple authentication identifiers can be used to allow password roll over. In yet another variation multiple authentication identifiers can be used to require that M of N M

In addition multiple authentication identifiers can be used for N users each having one password. The system can optionally require that all N users need to provide their passwords together to a system and then M of N M

As indicated above U.S. patent application Ser. No. 13 931 188 filed Jun. 28 2013 entitled Cryptographically Linking Data and Authentication Identifiers Without Explicit Storage of Linkage discloses methods and apparatus for cryptographically linking data identifiers and authentication identifiers. In one exemplary embodiment an authentication identifier AuthId is cryptographically associated with its associated data identifiers DataIds using a random client value Client Random and a random server value Server Random . The random client and server values are combined to produce a seed for a Key Derivation Function which in turn is used to generate and validate the AuthId and DataIds.

According to one aspect of the present invention multiple authentication identifiers are provided by associating the AuthIds with offsets of the Key Derivation Function other than offset 0. The DataIds are optionally stored in a separate database table thus preventing a conflict of identifiers between the AuthIds and DataIds.

According to another aspect of the invention multiple data classes i.e. multiple classes of identifiers are provided for the securely stored and retrieved data. Thus the seed is a function of the random client and server values as well as the data class identifier. For example a storage system may optionally provide the following data classes 

Although only a single client is shown in it is expected that a practical implementation of the system will support a substantially larger number of clients. Similarly although only a single server is shown in a system in accordance with the invention may include many such servers. The invention is therefore not restricted to the particular number of client or server devices.

The client may represent a lightweight device such as a mobile telephone PDA game console etc. The client may alternatively represent a desktop or laptop personal computer PC a microcomputer a workstation a mainframe computer a wired telephone a facsimile machine a television set top box or any other information processing device which can benefit from the secure authentication techniques of the invention. The client may therefore also be implemented as a server. In other words the invention although particularly well suited for use in applications in which roaming lightweight client devices authenticate themselves to servers can be used for the secure authentication of any type of information processing device including a device that is itself a server.

The client may also be referred to herein as a user. The term user should be understood to encompass either a client device a person utilizing or otherwise associated with the device or both. An operation described herein as being performed by a user may therefore be performed by a device a person utilizing or otherwise associated with the device or by both the user and the device. Similarly a password associated with a device may be a password of a user of the device. In this case the password may be temporarily associated with the device upon entry of the password into the device by the user as in the case of a device that serves multiple users each having different passwords.

The server may be implemented as an otherwise conventional server programmed to perform the secure storage and retrieval functions described herein or as other types of suitably programmed information processing devices.

The network may represent a global computer network such as the Internet a wide area network WAN a local area network LAN a satellite network a telephone or cable network or various portions or combinations of these and other types of networks.

It is noted that the client can optionally communicate with an Application Server not shown and the Application Server can optionally communicate with a Database Server not shown that could own the database . In such a variation the information described herein as pertaining to the Client would be spread between the Client and the Application Server. Likewise the information described herein as pertaining to the Server in this case would pertain to the Database Server. Typically the Application Server would contain the Client Random and would be Data Class aware. The Client would use Application Programming Interfaces APIs in the Application Server and the Application Server would determine which Data Class to use. The Client would store the indices n and p and would know the authentication values and data values.

As is apparent from the foregoing the system as illustrated in may be viewed more generally as a system having at least two processing devices that are configured to communicate with one another and in which a given one of the devices securely stores data of the other devices. The particular client and server labels provided for devices in should thus be considered as examples only and not limitations of the invention.

As indicated above aspects of the present invention provide improved techniques for secure storage and retrieval of data in a database with multiple data classes and multiple data identifiers. As discussed hereinafter describes an exemplary initialization process that generates and stores the random client and server values. describes an exemplary registration process that generates one or more authentication value indices AuthIds . describe an exemplary authentication process. describe an exemplary authentication and value storage process. describe an exemplary authentication and value retrieval process. The storage and retrieval of a value associated with a data identifier requires one or more authentication value indices AuthIds to be presented along with the authentication indices and the data identifier value.

Prior to first usage of this system an initial first authentication value must be stored. is a flow diagram showing an exemplary registration process that incorporates aspects of the present invention. Generally the registration process registers the first authentication value.

As shown in the client initially has an authentication value Auth Value1 that the client wants to use as the first authentication secret during step . The client sends Auth Value1 Client Random and Data Class as authentication to the server during step .

The exemplary server randomly generates a large number index1 during step . The server calculates an index value during step as follows 

and then sends the client the generated large number index1 comprising the authentication value index during step .

As shown in a client preparation portion of the exemplary authentication process is initiated during step when the client has one or more authentication sets that the client wants to authenticate with where each authentication set has the following form 

As shown in an authentication portion of the exemplary authentication process is initiated during step where the server authenticates the user client as follows. During step the server calculates an authentication seed as follows 

For each authentication set at step the server performs the following steps. The server calculates a database index during step 

The server then checks the database during step to determine if there is an entry for dbIndex2. The authentication fails if dbIndex2 is not in the database .

If dbIndex2 is in the database the server fetches the value associated with dbIndex2 during step and compares the obtained value with Auth Value. The authentication fails if the obtained value and Auth Value are not equal. The authentication passes during step if all authentication sets pass. The server sends the client the authentication result during step .

As shown in a client preparation portion of the exemplary authentication and value storage process is initiated during step when the client has one of more authentication sets Auth Value authIndex that the client wants to use to authenticate with and a data value belonging to a certain Data Class that the client wishes to store such as the following 

The client sends the server the Client Random value the authentication sets and the value to be stored during step . As indicated above the exemplary authentication sets are of the following form 

For example if there was one authentication set then the client might send the following values to the server 

As shown in an authentication portion of the exemplary authentication and value storage process is initiated during step where the server authenticates the user client as follows. During step the server calculates an authentication seed as follows 

For each authentication set at step the server performs the following steps. The server calculates a database index during step as follows 

The server then checks the database during step to determine if there is an entry for dbIndex3. The authentication fails if dbIndex3 is not in the database .

If dbIndex3 is in the database the server fetches the value associated with dbIndex3 during step and compares the obtained value with Auth Value. The authentication fails if the obtained value and Auth Value are not equal. The authentication passes during step if all authentication sets pass.

As shown in a value storage portion of the exemplary authentication and value storage process is initiated during step where the server calculates a data seed as follows 

The server then generates a large random number index4 during step and calculates a database index value during step as follows 

As shown in a client preparation portion of the exemplary authentication and value retrieval process is initiated during step when the client has one of more authentication sets Auth Value authIndex that the client wants to use to authenticate with the index of a data value that the client wants to fetch and the Data Class that the data value is in. For example the index may be dataIndex and the Data Class may be DataValues .

During step the client sends the server the Client Random value the authentication set s and information about the data value to be retrieved. The authentication sets may have the following exemplary form 

As shown in an authentication portion of the exemplary authentication and value retrieval process is initiated during step where the server authenticates the user client as follows. During step the server calculates an authentication seed as follows 

For each authentication set at step the server performs the following steps. The server calculates a database index during step as follows 

The server then checks the database during step to determine if there is an entry for dbIndex6. The authentication fails if dbIndex6 is not in the database .

If dbIndex6 is in the database the server fetches the value associated with dbIndex6 during step and compares the obtained value with Auth Value. The authentication fails if the obtained value and Auth Value are not equal. The authentication passes during step if all authentication sets pass.

As shown in a value retrieval portion of the exemplary authentication and value retrieval process is initiated during step where the server rejects the request if DataClass authentication. In this manner the server cannot return authentication values.

The server fetches the requested value from the database during step . If no value exists for the index dataIndex8 then the request fails. Otherwise Data Value is returned from the database .

During step the server sends one or more of the following indicators to the client Data Value Authentication Failure or data value does not exist for data index dataIndex8 .

NIST SP 800 108 http csrc.nist.gov publications nistpubs 800 108 sp800 108.pdf specifies a variety of Key Derivation Functions KDFs .

The KDF should be cryptographically strong so that it cannot be reversed determining the association from one identifier to another .

Identifier Symmetric Cipher Initialization Vector Value . Initialization Vector is the Seed. Value is the index.

Identifier RSA Encrypt Public Key Value where the value could be the message digested value of any of the Identifier values above.

Additional details regarding certain conventional cryptographic techniques referred to herein may be found in e.g. A. J. Menezes et al. Handbook of Applied Cryptography CRC Press 1997 which is incorporated by reference herein.

The term authentication information as used herein is intended to include passwords passcodes answers to life questions or other authentication credentials or values derived from such authentication credentials or more generally any other information that a user may be required to submit in order to obtain access to an access controlled application. Although the illustrative embodiments are described herein in the context of passwords it is to be appreciated that the invention is more broadly applicable to any other type of authentication information.

The illustrative embodiments of the invention as described herein provide improved techniques for cryptographically linking data secrets with a corresponding authentication secret. The described techniques may be used with security tokens that generate one time passwords or other types of authentication information regardless of whether such tokens are connectable to the user device.

It should again be emphasized that the particular authentication techniques described above are provided by way of illustration and should not be construed as limiting the present invention to any specific embodiment or group of embodiments. For example as previously noted the described embodiments may be adapted in a straightforward manner to operate with time varying credentials such as token codes or authentication information and other types of access controlled resources. Also the particular configuration of system elements shown in and their interactions as shown in may be varied in other embodiments. Moreover the various simplifying assumptions made above in the course of describing the illustrative embodiments should also be viewed as exemplary rather than as requirements or limitations of the invention. Numerous alternative embodiments within the scope of the appended claims will be readily apparent to those skilled in the art.

