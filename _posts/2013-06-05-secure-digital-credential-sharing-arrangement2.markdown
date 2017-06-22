---

title: Secure digital credential sharing arrangement
abstract: A secure and transparent digital credential sharing arrangement which utilizes one or more cryptographic levels of indirection to obfuscate a sharing entity's credentials from those entities authorized to share the credentials. A security policy table is provided which allows the sharing entity to selectively authorize or revoke digital credential sharing among a plurality of entities. Various embodiments of the invention provide for secure storage and retrieval of digital credentials from security tokens such as smart cards. The secure sharing arrangement may be implemented in hierarchical or non-hierarchical embodiments as desired.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09563757&OS=09563757&RS=09563757
owner: Assa Abloy AB
number: 09563757
owner_city: Stockholm
owner_country: SE
publication_date: 20130605
---
This application is a continuation of U.S. application Ser. No. 12 806 451 filed Aug. 12 2010 which is a continuation of U.S. application Ser. No. 11 397 710 filed Apr. 5 2006 now U.S. Pat. No. 7 802 293 which are hereby incorporated by reference.

The present invention relates generally to a data processing method and more specifically to a method system and computer program product which allows a plurality of entities to securely share digital credentials.

In today s increasingly security conscious world data is generally encoded using a variety of techniques to prevent unauthorized access to the underlying information. While encoding of data does improve security the ability to securely share the information with another entity becomes more difficult as both the mechanism and encoding secret s must also be shared with each entity requiring access to the encoded data.

One approach is provided by Microsoft Inc. in Windows XP which allows an entity to specify at the file level which registered entities may access the encoded information as part of operating system s encrypting file system. While effective for sharing large amounts of data with one or more entities in a one to many relationship the mechanism does not support multiple entities sharing a common workspace who wish to selectively encode discrete files in a many to many relationship. That is to allow multiple levels of encryption within the common workspace.

In addition the Microsoft solution is limited to file sharing alone and does not address other circumstances which may require sharing of digital credentials. For example network administrators frequently need to assist users or other entities in accessing selected services or networks where multiple credentials associated with the user or entity are implemented to access the various services or networks. In many cases full disclosure of a user s credentials is unnecessary as only the problematic credentials need be made available to the network administrator.

Furthermore the disclosure of even a partial portion of a user or entity s credentials is undesirable from a security perspective. As such there is a need for a secure and selective credential sharing arrangement which is transparent and revocable by the sharing entity or user.

This invention addresses the limitations described above and provides a mechanism for selectively and securely sharing user or entity credentials among a plurality of entities without automatically providing the sharing entities full access to all credentials or otherwise directly disclosing the shared credentials.

According to the invention a method is provided which allows the secure and selective sharing of digital credentials among a plurality of separate entities to said method comprising 

providing a first credential store having retrievably stored therein a plurality of first entity credentials 

protecting at least a portion of said first entity credentials with first protection means configured to revocably allow said at least a portion of said first entity credentials to be revocably shared with at least a second entity said first protection means comprising a first secret determinable by at least said second entity 

responsive to at least said first secret granting said at least a second entity permission to share said at least a portion of said first entity credentials.

According to an aspect of the invention said method comprises preferably one or several of the following features 

According to other aspects of said particular embodiment of the invention said method further comprises one or several of the following features 

In still other aspects of the method according to the invention said method further comprises one or several of the following features 

The invention also provides a system to securely and selectively share digital credentials among a plurality of separate entities comprising 

In one aspect of the invention said system comprises preferably one or several of the following features 

According to other aspects of said particular embodiment of the invention said system further comprises one or several of the following features 

In yet other aspects of the system according to the invention said system further comprises one or several of the following features 

The invention provides also a computer program product embodied in a tangible form comprising instructions for a processor to securely and selectively share credentials among a plurality of separate entities said instructions executable by said processor to 

access a first credential store having retrievably stored therein a plurality of first entity credentials 

protect at least a portion of said first entity credentials with first protection means for revocably allowing said at least a portion of said first entity credentials to be shared with at least a second entity said first protection means comprising a first secret determinable by at least said second entity 

responsive to at least said first secret to grant said at least a second entity permission to share said at least a portion of said first entity credentials.

In one aspect of the computer program said tangible form includes at least one of magnetic media optical media or logical media.

In another aspect of the computer program said executable instructions are stored in a code format comprising byte code compiled interpreted compliable and interpretable.

The invention also provides a computer readable medium having stored thereon a data structure comprising 

a second field containing encoded data representing a credential associated with the entity specific data string and

a third field containing data representing a entity specific secret used in encoding at least the second field.

In one aspect of the computer readable medium according to the invention a forth field is provided which contains data representing a common secret from which the entity specific secret is derived in conjunction with the first field.

The present invention provides a mechanism to securely share entity credentials among a plurality of separate entities. The secure sharing mechanism is based on cryptographic indirection techniques and is intended to supplement the standardized security features normally provided by the various operating systems currently available. Where necessary applications used to implement the various embodiments of the invention are envisioned to be programmed in a high level language such as Java C and C C or Visual Basic .

Referring to a functional block diagram of a computer system and associated peripherals is depicted. In a networking environment the depicted computer system is intended to apply to both client and server arrangements.

The term credential as referred to herein includes authentication data related attributes digital certificates passwords personal identification numbers PIN biometric samples asymmetric and symmetric cryptographic keys and other information used to establish an entity s access rights and or access permissions.

The computer system includes a processor a main memory a visual display electrically coupled to a display interface a secondary memory subsystem electrically coupled to a hard disk drive a removable storage drive electrically coupled to a removable storage unit and an auxiliary removable storage interface electrically coupled to an logical media storage unit . The display device may include a touch sensitive screen. The removable storage units are intended to include flash memory devices such as USB based solid state hard drives and related logical media drives.

A communications interface subsystem is coupled to a network via a network interface . The network includes traditional wired optical or wireless networks which may incorporate a secure communications protocol such as secure socket layer SSL transport layer security TLS private communications technology PCT or internet protocol security IPsec. 

A security token is operably coupled to the communications interface . The term security token as described herein includes hardware based security devices such as cryptographic modules smart cards integrated circuit chip cards portable data carriers PDC personal security devices PSD subscriber identification modules SEM wireless identification modules WIM USB token dongles identification tokens secure application modules SAM hardware security modules HSM secure multi media token SMMC trusted platform computing alliance chips TPCA and like devices.

The security token may be directly coupled to the computer system or remotely coupled to the computer system via another networked computer system. The security token. includes a wireless optical and or electrical connection means compatible with the communications interface a microprocessor a cryptography co processor volatile and non volatile memory electrically coupled to the processor and co processor a runtime operating environment.

The security token further comprises cryptography extensions available to the runtime environment and capable of performing symmetric and asymmetric cryptographic functions compatible with the computer system s and or an authentication server s cryptography software.

The security token further comprises in an embodiment of the invention one or more credentials. One or more security applications are provided to allow implementation of the embodiment of the invention which utilizes the security token. In another embodiment of the invention the security token further includes one or more security policies which allow an entity to securely share one or more of the credentials stored therein.

User input devices such as a mouse and a keyboard are operatively coupled to the communications interface . Lastly a biometric scanner may optionally be coupled to the communications interface . The biometric scanner is used capture biometric samples from one or more entities which become stored in a credential store.

The processor main memory display interface secondary memory subsystem and communications interface system are electrically coupled to a communications infrastructure commonly referred to as I O bus or system bus. The computer system includes an operating system one or more security applications a security token application programming interface where necessary one or more security token aware applications cryptography software capable of performing symmetric and asymmetric cryptographic functions compatible with that of the security token and or an authentication server at least one graphical display application suitable for displaying the security information received from the security token and all necessary device interface and driver software.

Referring to a flow chart is provided which illustrates the major process interactions used to implement the various embodiments of the invention. The processes are initiated by providing a first credential store associated with a first entity . At least a portion of the first entity s credentials maintained in the credential store are then revocably protected using a secret belonging to the first entity. The first entity secret is depicted as a key for example only. One skilled in the art will appreciate that other types of static secrets will work as well. The original first entity s secret is generally stored in the first entity s credential data store along with a copy of a common secret .

Once the first entity s credentials have been protected revocable credential rights for each separate entity authorized to share the first entity s credentials are defined by establishing the revocable credential rights in a security policy .

The security policy comprises a security table which allows an entity to authorize or revoke credential sharing privileges among a plurality of entities. The security policy may further include other sharing criteria including sharing expiration dates logical usage rules location usage rules priority usage rules time usage rules or security state based rules.

A second entity is used as an example of a separate entity intending to share the first entity s credentials. Additional sharing entities may be established in the security policy as well. The security policy may be incorporated into an access rights table for multiple session usage or maintained in volatile memory to limit the sharing of the first entity s credentials to a single session.

In order for the second entity to share the first entity s credentials a verification process is provided . The verification process examines the security policy to determine if the second entity has been granted revocable credential rights.

If the second entity has not been granted revocable credential rights access is denied followed by process termination . If the second entity has been granted revocable credential rights a security application retrieves a publicly available data string unique to the first entity along with the common secret . Each entity which is authorized to share the first entity s credentials is provided a copy of the common secret or the means to regenerate the common secret .

The common secret is normally stored in each sharing entity s credential data store or securely provided from a central datastore . An alternate embodiment of the invention which affords greater protection of the common secret is described in .

The first entity string and the common secret are then algorithmically combined to regenerate the first entity s secret . The security application then facilitates access to the first entity s credentials by the authorized second entity . The specific security mechanism employed by the security application may be cryptography based or performed as a gatekeeper function. In both instances the first entity s regenerated secret is incorporated into the security mechanism. Once the second entity has completed sharing of the first entity s credentials processing ends .

In one embodiment of invention the regenerated first entity s secret is stored in a credential data store belonging to the second entity. In another embodiment of invention the regenerated first entity s secret is maintained in volatile memory only for the duration of its use and is destroyed upon processing termination .

In various embodiments of the invention the credential protection security policy and second entity verification designated with an asterisks are performed by either the same security application or in conjunction with other security applications .

Referring to an alternate embodiment of invention is shown which affords greater protection of the common secret . In this embodiment of invention the second entity s copy of the common secret is encoded with the second entity s own secret . In order to use the common secret for generating the first entity s entities secret the encoded common secret is decoded by combining algorithmically the second entity s secret with the encoded common secret using the security application . The first entity string and the common secret are then algorithmically combined to regenerate the first entity s secret 

The resulting first entity s secret is then used to decode one or more of the encoded first entity credentials using the security application freeing the decoded first entity credential s for use by the second entity. Processing ends after the second entity has completed using the first entity s decoded credentials.

In an embodiment of the invention the entity secrets are generated on demand rather than being stored with each entity s credentials. This arrangement is somewhat more secure by limiting the number of stored secrets available for interception. However reconstruction of one or more of the entity secrets may reduce overall system performance.

Referring to a detailed block diagram is provided which describes the interactions of the common secret security policy and the entity secret . The common secret denoted as Cmay be generated from a random string a random number a hash of an existing secret or simply utilizing an existing symmetric key . The common secret C provides a level of indirection which allows the second entity to derive a specific secret of the first entity secret used to encode a portion of the first entity s credentials.

When a suitable source for the entity string data and common secret C has been generated or derived each entity s secret may be generated by algorithmically combining each entity s unique string data Ewith the common secret using the security application .

Once each entities unique secret has been generated it is then stored along with a copy of the common secret in a credential data store unique to each entity.

Another security application compatible with the security application which generated the entity secret is used to update a security policy with the proposed credential sharing arrangement between entities.

For example entity E is only allowed to access its own credentials as designed by the 1 and 0 s elsewhere in the array holding the revocable credential rights. In furtherance of this example entity Eis permitted to use its own credentials and also may share the credentials of entity E. Lastly it is also envisioned by the inventors to include an additional security provision which prevents an entity from using its own credentials in the event of a security compromise.

In another embodiment of the invention each entity s credential data store or portions thereof are encoded using the security application and each entity s secret . The results of the encoding process are stored in each entity s credential data store along with an encoded copy of the common secret and an unencoded copy of the entity s specific secret . Security protection of each entity s secret is provided by the normal operating system security policies.

Ms may be generated from a random string a random number a hash of a random string or number a symmetric encryption key or any combination thereof.

The function f is generally a symmetric cryptographic algorithm such as DES 3DES AES. However other common operations such as an exclusive OR operation or a concatenation operation and may be substituted for or used in conjunction with the symmetric cryptographic algorithm.

In one embodiment of the invention the entity specific secret denoted as Sis derived from a function f generally having the form of where Sis derived from the common secret Cand an entity specific string Eunique to a credential holding entity Entity .

The entity specific string E is derived from existing non secret information such as a username email address security token identifier network address MAC address or other entity specific information available to other entities in which the entity credentials are to be shared.

The function f is likewise a symmetric cryptographic algorithm such as DES 3DES AES. However a different symmetric cryptographic algorithm may be used from the one which generated the common secret C. As described above other common operations such as an exclusive OR operation or a concatenation operation may be substituted for or used in conjunction with the symmetric cryptographic algorithm.

While only one level of indirection is shown one skilled in the art will appreciate that multiple levels of indirection may be provided for improving security or providing a secret hierarchy. A shared secret hierarchy may be established using an entity s specific secret S substituted for the common secret C for all subsequent entities in which a hierarchal arrangement is desired. In the hierarchal arrangement the dependent entity specific secret is derived from a function having the general form of 

Sis an intermediate non dependent entity secret of the intended hierarchal entity corresponding to the specific string E and 

Sis the final hierarchal entity secret derived from the combination of the non hierarchal entity secret Sand the intermediate non dependent entity secret Susing the general function f described above. In this embodiment of the invention it will be necessary to consistently utilize the same function f throughout the derivation and entity secret regeneration process including the common secret C.

In all cases the common secret C and entity secret S should have sufficient bit strength to inhibit attempts at decoding the protected credentials. Minimum bit strength of 64 bits should be used and preferably a bit strength of 128 bits or greater where possible.

Referring to an example of a credential sharing session is depicted. In this continuing example from entity E is attempting to share the credentials of entity E. The security application first verifies that entity E is authorized to share entity E credentials. The security application locates entity E entry in the security policy and verifies that entity E is authorized to access entity E credentials along with entity E own credentials .

Continuing the security application retrieves the encoded common secret and entity Esecret . The encoded common secret is then decoded by the security application using entity Esecret . Entity Eunique string data is retrieved from a public location such as the LDAP file directory an e mail address book URL or MAC address and combined algorithmically using the security application which regenerates Entity Esecret . Entity secret is then used to decode the Entity Ecredential store using security application and allowing use of one or more of the decoded Entity Ecredentials by entity E.

According to a first aspect the sharing arrangement between the first entity and the second entity is bi directional. Not only does the second entity have access to some portion of the credentials of the first entity but the first entity also has access to some portion of the credentials of the second entity. In this bi directional sharing arrangement the common secret between the first entity and the second entity can be used not only in the retrieval of the first secret by the second entity but also in the retrieval of the second secret by the first entity. The functional relationship between the first secret and the second secret is therefore via the common secret.

In a second aspect of the invention the said first secret and said second secret incorporate a hierarchical structure such that said first secret may be used to derive said second secret but not visa versa. The said second secret is protected with said first secret.

In a third aspect of the invention the first secret and said second secret incorporate a hierarchical structure such that said second secret may be used to derive said first secret but not visa versa. The first secret is protected with said second secret.

In the first aspect the first secret and the second secret have functional parity. In the second aspect the entity that can retrieve the second secret can access only part of the second credentials but the entity who can retrieve the first secret can access both part of the first credentials and part of the second credentials. In the third aspect the entity that can retrieve the first secret can access only part of the first credentials but the entity who can retrieve the second secret can access both part of the first credentials and part of the second credentials.

Referring to a block diagram illustrating a systematic embodiment of the invention is provided. In this embodiment of the invention a network enabled computer system is shown having operatively installed therein at least one security application . The security application is programmed to process sources of security information necessary for credential sharing including an operatively coupled credential datastore a common secret one or more retrievable entity strings and a security policy .

In another embodiment of the invention the security application is further programmed to process information utilizing an operatively coupled security token . In this embodiment of the invention the security token includes a local security application T and optionally one or more credentials T the common secret one or more entity strings and a separate security policy . This embodiment of the invention allows the secure storage features available from the security token to be utilized by the security application by selectively maintaining one or more of the sources of security information necessary for credential sharing.

In yet another embodiment of the invention the security application is programmed to process the sources of security information necessary for credential sharing from the security token alone. In this embodiment of the invention the security token the local security application T the credential store T the common secret entity strings and separate security policy replace the credential store common secret entity strings and a security policy coupled to the security application .

Referring to a block diagram illustrating a systematic embodiment of the invention in an enterprise operating environment is provided. In this embodiment of the invention a plurality of networked enabled computer systems A B are shown in processing communications with a security server S S.

Each of the computer systems A B has operatively installed security applications A B which are programmed to process sources of security information necessary for credential sharing. The sources of security information are distributed among a security application S installed on the security server S S and entity specific security tokens A B operatively coupled to each security application A B.

The security tokens A B have operatively installed therein one or more credentials A B which are controlled by local security applications AT BT installed within the security tokens A B.

The security application S is operatively installed in the security server S and is programmed to process sources of security information necessary for credential sharing from the security tokens A B and server maintained set of security policies set of credentials set of entity strings and a common secret . This arrangement allows for credential sharing A B S among a plurality of networked client computer systems A B S while maintaining centralized control of credential sharing activities using the security server S S. Furthermore in this embodiment of invention the server version of the security application S performs the majority of the processing. The client and security token security applications A AT B BT provide the basic verification of an incoming request for credential sharing while the server S S performs the majority of the transport and security of credentials. Various sharing arrangements may be combined which incorporate elements obtained from the embodiments shown in

The common secret and or the credential store S may be stored inside a hardware security module HSM S or derived from a securely stored master secret contained inside the hardware security module HSM S. The hardware security module HSM S is an optional component to consider highly desirable for large enterprise deployment of the invention.

Referring to a detailed block diagram is presented of a basic data structure embodiment of the invention. In this embodiment of the invention a computer system incorporates a data structure having a first data field comprising entity string information a second data field comprising encoded credentials a third data field comprising an entity secret utilized in encoding the credentials of the second data field and a forth data field comprising a common secret utilized in deriving the entity secret of the third data field .

The foregoing described embodiments of the invention are provided as illustrations and descriptions. They are not intended to limit the invention to precise form described. In particular it is contemplated that functional implementation of the invention described herein may be implemented equivalently in hardware software firmware and or other available functional components or building blocks. No specific limitation is intended to a particular security system or financial services system. Other variations and embodiments are possible in light of above teachings and it is not intended that this Detailed Description limit the scope of invention but rather by the Claims following herein.

