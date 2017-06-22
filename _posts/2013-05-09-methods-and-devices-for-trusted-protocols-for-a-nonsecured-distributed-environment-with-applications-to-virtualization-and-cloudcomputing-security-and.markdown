---

title: Methods and devices for trusted protocols for a non-secured, distributed environment with applications to virtualization and cloud-computing security and management
abstract: The present invention discloses methods for trusted protocols for a non-secure computing-environment. Methods include the steps of: upon request for determining that an untrusted computing resource is trustworthy, vouching for the untrusted resource as trustworthy by a trusted computing resource upon satisfying at least one criterion of: the trusted resource was directly involved in setting up and/or activating the untrusted resource; and/or has access to a database of identifying credentials and/or information which allow the trusted resource to verify that the untrusted resource is trustworthy; and concealing at least one secret that needs to be present on any computing resource, wherein at least one secret is concealed differently on each computing resource; and transmitting at least one secret from any computing resource to any other computing resource in a way that changes the step of concealing at least one secret without any computing resource knowing at least one secret.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09380037&OS=09380037&RS=09380037
owner: Porticor Ltd.
number: 09380037
owner_city: Hod Hasharon
owner_country: IL
publication_date: 20130509
---
This patent application claims priority under 35 U.S.C. 119 e to U.S. Provisional Patent Application No. 61 563 893 filed Nov. 28 2011 and U.S. Provisional Patent Application No. 61 603 383 filed Feb. 27 2012 and under 35 U.S.C. 120 to PCT Patent Application No. IL2012 050483 filed Nov. 28 2012 which are hereby incorporated by reference in their entirety.

The present invention relates to methods and devices for trusted protocols for a non secured distributed environment with applications to virtualization and cloud computing security and management.

A trend in modern computer networking web and cloud computing is to rely on public group shared or virtualized resources. The IT information technology marketplace offers public private and hybrid solutions for virtualization and cloud computing. This growing trend is occurring at many levels infrastructure platform and software.

A recurring problem hampering such solutions is the fact that networked virtualized and or cloud solutions are by their very nature non secured and distributed. The resources may be physically owned by different entities other than the users or may be shared among multiple users having existing security privacy and trust concerns . This may occur within one legal entity or among different entities.

For example a file may be saved in a network storage cloud. Since the storage cloud is a shared resource a user is entrusting his her data to a resource that is routinely accessed by many other users over which the user has no control at all.

Vendors of network cloud and virtualization solutions provide various mechanisms e.g. authentication authorization and virtual private networks to ameliorate this state of affairs. Such approaches are significant but incomplete. Such mechanisms do not solve various important problems e.g. encryption at rest protection of data in use during computation protection of data when transmitted on the network single point for security handling key management and requiring the user to trust the provider the provider s implementation or the provider s staff .

Of course one solution for the security conscious consumer is to avoid shared resources altogether. However such an option is an unpleasant choice for the user since modern shared resources provide many economic operational and technical benefits.

It would be desirable to have methods and devices for trusted protocols for a non secured distributed environment with applications to virtualization and cloud computing security and management. Such methods and devices would inter alfa overcome the limitations mentioned above.

It is the purpose of the present invention to provide methods and devices for trusted protocols for a non secured distributed environment with applications to virtualization and cloud computing security and management.

In the interest of clarity several terms which follow are specifically defined for use herein. The term virtualization is used herein to refer to any means of executing software in an environment separated from the underlying hardware resources including but not limited to hardware virtualization software virtualization memory virtualization database virtualization data virtualization storage virtualization application virtualization desktop virtualization and network virtualization.

The term computing resource is used herein to refer to any computing service which provides data storage volatile memory permanent memory computing and calculation capacity networking capacity algorithmic capabilities software capabilities and or software based objects using hardware or software provided by any service provider.

The term appliance is used herein to refer to any software or hardware which may be embodied on physically separate servers as agents on existing servers of a network system as virtual servers as agents on virtual servers containing additional software or using any appropriate computational resource available to the system serving as a cryptographic appliance for the encryption and or decryption of resources.

The term customer application is used herein to refer to a cloud application that is written by customers or other third parties and may use an appliance to perform secure storage I O operations for avoidance of doubt an appliance may be a software agent installed on the same computing resource as the customer application.

The term protected item is used herein to refer to any object which should be encrypted. The term homomorphic agent is used herein to refer to an optional server or agent for maintaining an encrypted version of a blinding value which can be applied and removed on demand by the homomorphic agent.

Furthermore it is noted that the term exemplary is used herein to refer to examples of embodiments and or implementations and is not meant to necessarily convey a more desirable use case. Similarly the terms preferred and preferably are used herein to refer to an example out of an assortment of contemplated embodiments and or implementations and is not meant to necessarily convey a more desirable use case. Therefore it is understood from the above that exemplary and preferred may be applied herein to multiple embodiments and or implementations.

Preferred embodiments of the present invention enable a security conscious consumer to use available public private hybrid or shared resources from providers or vendors while enjoying full security and control. Preferred embodiments of the present invention provide the ability to secure resources that are non secured without impairing the functionality of the resources. Preferred embodiments of the present invention enable non secured resources to be secured and controlled more completely while maintaining the benefits of the emerging shared resource model.

Preferred embodiments of the present invention enable a resource to be encrypted by one entity i.e. appliance in an environment yet may be decrypted by a different entity i.e. appliance and that each such encryption or decryption operation may in principal be done by a different entity.

Such appliances are operationally connected to a Protected Virtual Key Manager PVKM for providing services to the appliances and to users of the system. Such services can be related to managing the encryption keys of the system and or related to enhancing the security of the system. Such service features include but are not limited to 

Preferred embodiments of the present invention are applicable in public private and hybrid scenarios in which secure resources may belong to different legal entities.

Some preferred embodiments of the present invention provide trusted protocols for cooperation of computing resources in a collection of computing resources or in a cluster of computing resources. In such embodiments a collection of entities e.g. a cluster of appliances or a collection of customer applications can ensure that each member of the collection is worthy of trust in a non secured environment. In particular such embodiments ensure that a new member of the collection is secure and trustworthy.

Other preferred embodiments of the present invention provide secure virtualized key management system in the form of a key repository which may store keys used by a consumer without knowing such key s values and without risk of exposing such key s values.

Other preferred embodiments of the present invention provide algorithmic methods for advanced security applications.

Therefore according to the present invention there is provided for the first time a method for trusted protocols for a non secure computing environment the method including the steps of a upon request for determining that an untrusted computing resource in the computing environment is trustworthy vouching for the untrusted computing resource as trustworthy by a trusted computing resource in the computing environment upon satisfying at least one criterion selected from the group consisting of i the trusted computing resource was directly involved in setting up and or activating the untrusted computing resource and ii the trusted computing resource has access to a database of identifying credentials and or identifying information which allow the trusted computing resource to verify that the untrusted computing resource is trustworthy and b concealing at least one secret that needs to be present on any of the computing resources including the trusted computing resource wherein at least one secret is concealed differently on each computing resource and c transmitting at least one secret from any of the computing resources to any other computing resource in a way that changes the step of concealing at least one secret without any of the computing resources including the trusted computing resource knowing at least one secret.

According to the present invention there is provided for the first time a device for trusted protocols for a non secure computing environment the device including a a server including i a CPU for performing computational operations ii a memory module for storing data and iii a network connection for communicating across a network and b a vouching module residing on the server configured for i upon request for determining that an untrusted computing resource in the computing environment is trustworthy vouching for the untrusted computing resource as trustworthy by a trusted computing resource in the computing environment upon satisfying at least one criterion selected from the group consisting of A the trusted computing resource was directly involved in setting up and or activating the untrusted computing resource and B the trusted computing resource has access to a database of identifying credentials and or identifying information which allow the trusted computing resource to verify that the untrusted computing resource is trustworthy and ii concealing at least one secret that needs to be present on any of the computing resources including the trusted computing resource wherein at least one secret is concealed differently on each computing resource and iii transmitting at least one secret from any of the computing resources to any other computing resource in a way that changes the concealing at least one secret without any of the computing resources including the trusted computing resource knowing at least one secret.

According to the present invention there is provided for the first time a non transitory computer readable medium having computer readable code embodied on the non transitory computer readable medium the computer readable code including a program code for upon request for determining that an untrusted computing resource in a computing environment is trustworthy vouching for the untrusted computing resource as trustworthy by a trusted computing resource in the computing environment upon satisfying at least one criterion selected from the group consisting of i the trusted computing resource was directly involved in setting up and or activating the untrusted computing resource and ii the trusted computing resource has access to a database of identifying credentials and or identifying information which allow the trusted computing resource to verify that the untrusted computing resource is trustworthy and b program code for concealing at least one secret that needs to be present on any of the computing resources including the trusted computing resource wherein at least one secret is concealed differently on each computing resource and c program code for transmitting at least one secret from any of the computing resources to any other computing resource in a way that changes the concealing at least one secret without any of the computing resources including said trusted computing resource knowing at least one secret.

These and further embodiments will be apparent from the detailed description and examples that follow.

The present invention relates to methods and devices for trusted protocols for a non secured distributed environment with applications to virtualization and cloud computing security and management. The principles and operation for such methods and devices according to the present invention may be better understood with reference to the accompanying description and drawings.

In some preferred embodiments of the present invention methods and devices for securing keys used in a non secured environment are provided. As an example consider a system e.g. a software application running in a virtualized or cloud environment. The system includes multiple computing resources such as servers and storage resources. It is required to occasionally encrypt some of the resources in the system for security.

Encrypted resources may be files disks or any resource in the system containing data e.g. data in server memory is also a resource in this context . Resources may be protected through any encryption technique such as symmetric or asymmetric encryption. These techniques always involve the generation and or use of cryptographic keys for encryption and decryption. Such cryptographic keys are typically stored for later retrieval such that the system can encrypt and decrypt the resources whenever necessary.

In order to provide a designated service i.e. encryption and or decryption of resources appliances are operationally connected with the servers and resources of the system as well as with the PVKM which may provide services related to the aforementioned cryptographic keys and the security of the system. Such operational connectivity may include network communication in memory communication or any appropriate communication technique available to the system. Thus such operational connectivity may also be referred to herein as a communication channel and or communication.

 Collections non state interactive groupings and clusters state interactive groupings of appliances are useful in such systems for example to ensure fail over or scalability of the system and its encryption mechanisms. It is often useful that a resource be encrypted by one appliance yet may be decrypted by a different appliance and that each such encryption or decryption operation may in principle be done by a different appliance. At the same time from a security point of view it is desired that if an attacker compromises one appliance the entire system is not compromised.

It is noted that while the methods described herein are highly useful in a cluster they are also useful in a cluster of one i.e. a lone appliance . Clusters are discussed to generalize the applicability and to emphasize the features of the system however the techniques herein are also useful for protecting the keys residing on a single instance of an appliance.

As a general framework to describe the embodiments and implementations detailed below the following secret keys and key elements inter alfa are relevant to the discussion of the system configuration.

A specific key K is a key or a group of keys used to encrypt a specific protected resource employing any encryption technique known in the art. Note that the system is configured to protect multiple such resources each of which may have a different K. In preferred embodiments of the present invention the specific key K does not need to be persistently stored in unencrypted form anywhere.

The specific key Kmay be split into multiple parts i.e. two or more . For purposes of clarity the most general case is used in the embodiments described below to split Kinto two parts a master key Kand a second key share. It is understood that implementations using a third key share or even more key shares have been contemplated within the scope of the present invention.

The following description often refers to mathematical operators and such operators denote any appropriate operation e.g. XOR multiplication modulus p division modulus p addition modulus p and subtraction modulus p . Such mathematical operations are useful for example in key joining key splitting and blinding. Such operator notation is used to denote these kinds of operations generically. For simplicity is used to denote both an operation and its inverse in the same equation e.g. the inverse of XOR is XOR itself while the inverse of multiplication is division . The same is true for the usage of . Both and are used since occasionally it is useful to denote two operations in one equation sometimes these generalized operators are used in homomorphic operations such as E A E B E A B .

The master key K is one key share of the specific key. Preferred embodiments of the present invention enable the system to be configured such that the master key does not need to be stored in unencrypted form anywhere in any computing system nor does the master key need to be in unencrypted form in memory anywhere in any computing system.

Such embodiments in which a key does not need to be stored in unencrypted form anywhere in any computing system nor does the key need to be in unencrypted form in memory anywhere in any computing system can be extended to additional keys or key shares. In the general framework provided below such aspects have only been applied to the master key for simplicity.

Such aspects as implemented in the following embodiments allow the master key or a key share to be used in mathematical operations such as key splitting key joining or any other relevant mathematical operation without the key s unencrypted value being known. In some preferred embodiments of the present invention a blinding value r is used to prevent keys or key shares from being stored or in transient memory. Other preferred embodiments implement homomorphic encryption e.g. using the ElGamal Paillier RSA or Goldwasser Micali algorithms using a group of keys denoted E or a public private key pair denoted E D to encrypt and secure keys and key shares. Other embodiments of the present invention may use any encryption technique known in the art.

Preferred embodiments of the present invention enable some of the keys such as master keys or key shares to reside entirely outside the computing environment so that they are never known in a plain unencrypted form within the computing environment. Such aspects of embodiments of the present invention enhance security since sensitive keys can be used in the computing environment without ever being in the computing environment in their plain form.

In some embodiments of the present invention blinding values keys or key pairs may be different for each appliance in the system or even for each resource intended to be protected. Preferred embodiments of the present invention ensure that keys are encrypted differently in their various usages within the computing environment. Such aspects of embodiments of the present invention enhance security since a theft of one encrypted form does not aid a thief since the encrypted form even if stolen is unusable in any other part of the system.

Preferred embodiments of the present invention enable the establishment of trust within an imperfectly trusted environment. Preferred embodiments of the present invention enable keys used in a non secured environment to be secured.

In the discussion below the PVKM may be viewed as a location whether physical or virtual in such an environment while each appliance and other security element may be viewed as another location whether physical or virtual . However for the avoidance of doubt the PVKM itself may be implemented as a collection or a cluster we will still refer to it as a location for the sake of simplicity.

In some embodiments of the present invention a split key encryption approach is implemented with a blinded key which uses a blinding value r in order to prevent Kfrom being in unencrypted form on the appliance the PVKM or anywhere in the computing system.

Referring now to the drawings is a simplified high level block diagram of the scheme of major operational steps in an exemplary implementation of split key encryption using a blinded key according to preferred embodiments of the present invention. In as well as subsequent the overall process has been depicted according to separate sequential time lines going from top to bottom in the drawings for two primary generalized components an appliance A and a PVKM B in order to representationally isolate the parallel processes that are occurring on each component independently.

It is noted that appliance A is intended to be a simplified example of a plurality of appliances in order to provide clarity in the description. It is understood that the present invention has broader applicability to a collection or cluster of such appliances. Furthermore PVKM B is intended to be one conceptual entity e.g. a server however in practical implementations PVKM B may be a plurality of servers e.g. for fail over protection . In generalizations of this approach there may be more locations and therefore more timelines e.g. timelines for a homomorphic server C and other additional elements .

Moreover the overall process has been classified into three sub processes a Sub Process I for creating a new appliance a Sub Process II for creating a new protected item and a Sub Process III for accessing an existing protected item.

In such blinded key embodiments to create a new appliance Sub Process I PVKM B generates a key pair E D Block Step and transmits the public key Eto appliance A Arrow Step for storing Block Step . Standard cryptographic techniques e.g. wrapping the public key within a so called certificate may be used to guarantee the authenticity of the public key E. A blinding value r is used to encrypt and conceal blind the value of Kon Appliance A this blinding can be calculated as K r where denotes any appropriate operation. The blinded value K r is then stored on appliance A Block Step . Such storage can be purely in memory it does not require disk storage or other permanent storage though these may be allowed in some embodiments.

As an exemplary implementation appliance A could perform such an operation as the user enters the original input value of K. In such configurations a copy of r is sent to Arrow Step and stored on PVKM B Block Step . The blinding value r is not stored on appliance A r is erased from memory once the blinded value is calculated and PVKM B stores a copy of r Block Step .

By performing operations with r and the blinded value K r in the protocol described herein the system can manage keys without Kor any Kever being known on PVKM B and without Kbeing known any more on appliance A after the blinding was performed.

Whenever a new protected item is created Sub Process II Appliance A generates Kwhich is the specific key used to encrypt and protect the item using any cryptographic technique known in the art.

To store Ksecurely and without exposing neither Knor K a blinding of the key share of PVKM B K K r is created Block Step which is then encrypted using E Block Step and sent to PVKM B Arrow Step . PVKM B calculates the non blinded key share Block Step using its stored value of r and stores the non blinded key share locally on PVKM B Block Step .

Optionally Hash based Message Authentication Code HMAC may be used to transmit a modified form of the key share of PVKM B back to appliance A Arrow Step . With or without HMAC the non blinded key share of PVKM B can be optionally stored on appliance A Block Step in place of or in addition to storing on PVKM B Block Step . The use of HMAC in such implementations is described below.

The operator should be considered an example of possible operations which are useful in such a context.

When the protected item is accessed again Sub Process III the PVKM key share is retrieved. This may optionally be done on the appliance in Block Step is retrieved and transmitted to PVKM B optionally using HMAC Arrow Step or it may be retrieved locally on the PVKM. PVKM B then decrypts the encrypted key share Block Step . PVKM B finally sends a blinded decrypted key share to appliance A Arrow Step where the decrypted key share is combined with the appliance s blinded key share K r to recover the storage key K Block Step .

By adding the blinding value Kis never stored on the appliance or on the PVKM. Thus a breach of the appliance does not allow an attacker to recover K. Equally a breach of the PVKM does not allow an attacker to recover K.

In some embodiments of the present invention homomorphic blinding is implemented in two locations using a homomorphic public key encryption scheme in order to achieve blinding of the master key K.

In such 2 location homomorphic blinding embodiments to create a new appliance Sub Process I PVKM B generates the E D key pair Block Step and transmits Eto appliance A Arrow Step for storing Block Step . The key pair is for an appropriate partially homomorphic or fully homomorphic cryptographic system. Appliance A either encrypts the master key K as soon as the key is received Block Step or receives the master key already encrypted but does not send the unencrypted key to PVKM B.

Whenever a new protected item is created Sub Process II Appliance A generates Kwhich is the specific key used to encrypt and protect the item using any cryptographic technique known in the art.

To store Ksecurely and without exposing neither Knor K the encrypted key share of PVKM B of the key E K K is created Block Step . The encrypted key share is then sent to PVKM B Arrow Step for storing Block Step . The encrypted key share of PVKM B can be optionally stored on appliance A Block Step in place of or in addition to storing on PVKM B Block Step .

In such embodiments the homomorphic property which allows an appliance to multiply cipher text together without decryption is used. This enables E K K to be calculated from Kand E K without knowing K E K E K E K K as depicted in Block Step .

When the protected item is accessed again Sub Process III appliance A first retrieves the encrypted key share E K K . Appliance A then needs to request PVKM B to decrypt the key since appliance A does not have D. However PVKM B should not be allowed to determine the values of the specific key Kor the master key K. To prevent PVKM B from obtaining these keys directly the specific key is blinded Block Step with a new random value r known only the appliance every time the key is sent Arrow Step to PVKM B for decryption Block Step .

Again the homomorphic property is used to have appliance A add the blinding to E K without knowing Kor K E K K E K E r E K r .

PVKM B then sends the blinded decrypted key share to appliance A Arrow Step where the decrypted key share is combined with the key share of appliance A K and the blinding value to recover the storage key K Block Step .

Algorithmically the same 2 location homomorphic blinding process may be described as follows. As an example consider a cryptographic key S protecting a sensitive resource wherein 

Each b may be a byte or bit of data for example. If some or all bbecomes known to an unauthorized entity then the key is exposed in whole or in part and as a result the sensitive resource is exposed as well. S can be protected by encrypting the string of b elements up to b. S may be encrypted once or n times using several different encryption methods E . . . E and appropriate encryption keys P P . . . P. It can be defined that . . . . . . .

In the above expression P which is the ordered set of P . . . P is the secure key set and C is the encrypted form of S i.e. the cipher of S . Each Emay be any type of encryption known in the art e.g. a symmetric encryption a public private scheme or a key sharing scheme and each Pmay be any type of key known in the art e.g. a symmetric key a public private key pair or a key in a key sharing scheme .

In such an approach each Dis the inverse of E and is the inverse of c. S is considered secure in such a scheme if the secure key set P is safe and if the cipher C is deciphered in close proximity to the time and location that S is to be used. In other words the operation is applied only when S is actually needed and the value S is thrown away when it is not needed.

Consider one of the encryption methods E where k is between 1 and n . Emay be embodied on an appliance as defined above. Supporting a cluster of appliances would require an implementation in which Ecan be embodied on any of the appliances in the cluster. In order to achieve fail over or scalability for the encryption method Ewould have to be embodied on all appliances in the cluster.

Consider another encryption method E where j is different from k and between 1 and n . The method Eis embodied on the PVKM. For generality and avoidance of doubt we make no assumptions regarding the exact location or nature of the PVKM other than that it is available for communication with the appliance in a secure way and is able to provide an embodiment of E. For example the PVKM may be embodied itself on computing resources such as servers or clusters of servers.

If we disregard methods other than j and k a simplified notation for the relevant methods in the following discussion are defined as and .

Recall that S was introduced as a cryptographic key that serves to protect a sensitive resource. The present embodiment seeks to protect S itself. S is available in its unencrypted form only in the memory of the appliance and only when S is in use for encryption or decryption of a sensitive resource. S is never available outside the memory of the appliance e.g. S is never stored in persistent memory such as disk storage and never available on the PVKM.

The PKI Public Key Infrastructure technique involves an encryption algorithm Eand a decryption algorithm D. The PKI key pair includes the public key e m and private key d m as is commonly used in PKI. The private key d m is only found on the PVKM and is used in the decryption algorithm D y D y d m . The public key e m may be found on both the PVKM and the appliance and is used in the encryption algorithm E x E x e m .

The PKI technique may be any PKI technique common in the art which has a partially homomorphic or fully homomorphic behavior e.g. ElGamal Paillier RSA and Goldwasser Micali . The actual meaning of e d and m depends on the particular technique chosen. For example in RSA m is the modulus e is the encryption exponent d is the decryption exponent e m comprises the public key and d m comprises the private key.

For convenience the master key M is used herein interchangeably with K. The PKI encrypted master key is E M and is available only on the particular appliance which participates in the embodiment described below. Note that M is never available anywhere in the system only is available and only on the particular appliance.

A generalized multiplication operator denoted by a middle dot is defined. The actual choice of operation depends on the specific PKI technique used. The operator selected for this exemplary embodiment is a partially homomorphic operation appropriate for the PKI technique chosen. For example in RSA the operator could be multiplication while in Goldwasser Micali the operator could be a XOR logic operation. The partially homomorphic property implies and .

The inverse of is called generalized division denoted by a slanted line and is assumed to exist for the chosen PKI technique. Using such definitions the encryption techniques Eand E and the decryption techniques Dand Dcan be described as follows.

To encrypt a resource e.g. a file stored on a disk with an encryption technique that depends on S the following steps are performed.

Taken together the steps above that occur on the appliance describe E while the steps that occur on the PVKM describe E.

Taken together the steps above that occur on the appliance describe D while the steps that occur on the PVKM describe D.

Since Kis only stored in encrypted form a breach of the appliance does not allow an attacker to recover K.

In some embodiments of the present invention homomorphic blinding is implemented in three locations. Such 3 location homomorphic blinding embodiments are similar to the process described above regarding split key encryption using a blinded key except for the fact that r is never stored in unencrypted form anywhere in the 3 location method. Instead an encrypted version of r is sent to an external homomorphic server. 

In such 3 location homomorphic blinding encryption to create a new appliance Sub Process I PVKM B generates the E D key pair Block Step and transmits Eto appliance A Arrow Step for storing Block Step . Appliance A stores Kblinded Block Step .

As an exemplary implementation the blinding operation could be performed with a random value r as the user enters the original input value of K. In such configurations an encrypted form of r is calculated Block Step then sent to Arrow Step and stored on Block Step a homomorphic server C neither r nor its encrypted form are stored on appliance A or PVKM B .

Whenever a new protected item is created Sub Process II Appliance A generates Kwhich is the specific key used to encrypt and protect the item using any cryptographic technique known in the art.

To store Ksecurely and without exposing neither Knor K the encrypted key share of PVMK B of the blinded key K K is created Block Step which involves calculating E K K r and then sending to homomorphic server C Arrow Step . C calculates the non blinded key share using its stored encrypted form of r Block Step . The encrypted non blinded key is then transmitted Arrow Step and stored locally on PVKM B Block Step .

Optionally HMAC may be used to transmit a modified form of the key share calculated in Block Step back to appliance A Arrow Step . With or without HMAC the encrypted non blinded key share of PVKM B can be optionally stored on appliance A Block Step in place of or in addition to storing on PVKM B Block Step .

When the protected item is accessed again Sub Process III the stored encrypted key share in is retrieved Block Step and transmitted to homomorphic server C optionally using HMAC Arrow Step . depicts the key shared being transmitted from appliance A in the case of storage on appliance A Block Step however the key share can be transmitted from PVKM B in the case of storage on PVKM B Block Step . Homomorphic server C then calculates a blinded encrypted key share Block Step and sends the blinded encrypted key share to PVKM B Arrow Step . PVKM B finally decrypts the blinded encrypted key share Block Step and sends the blinded decrypted key share to appliance A Arrow Step where the decrypted key share is combined with the appliance s blinded key share K r to recover the specific key K Block Step .

The homomorphic property of the above encryption method means that the blinding value can be applied to and removed directly from the cipher text without knowing the plain r. Since the value of r is never stored in unencrypted form a passive attack on the PVKM or the appliance or even both cannot reveal r. The only way to reveal the master key would be to exploit all three servers retrieve K r from the appliance Dfrom the PVKM and E r from the homomorphic server and combine all three key elements.

In some embodiments of the present invention 2 location homomorphic blinding encryption is implemented with protocol optimizations. Such embodiments are similar to the 2 location homomorphic blinding encryption described above with regard to except that the protocol is more efficient in certain places and can achieve similar goals with fewer calculations and fewer round trips. 

In such 2 location homomorphic blinding embodiments to create a new appliance Sub Process I PVKM B generates the E D key pair Block Step and transmits Eto appliance A Arrow Step for storing Block Step as well as optionally sending Eto the user Arrow Step e.g. to the user s web browser . Appliance A stores the encrypted master key E K upon receipt Block Step and then blinds the encrypted K from a generated and stored blinding value r by calculating E K r Block Step . The blinded encrypted Kis then transmitted to PVKM B Arrow Step and stored on PVKM B Block Step .

The homomorphic property of the above encryption method means that the blinding can be applied without ever knowing K E K r E K E r .

Whenever a new protected item is created Sub Process II a new specific key K which is the specific key used to encrypt and protect the item is needed. Any cryptographic technique known in the art can be used. In such embodiments the specific key is generated as follows.

Appliance A can optionally gather entropy as known in the art in the form of random bits on Appliance A Block Step to be sent with a key generation request. Appliance A then requests a key to be generated Block Step by transmitting the request to PVKM B optionally passing on the gathered entropy Arrow Step . PVKM B then generates a random value which serves as the key share of PVKM B K K optionally with appliance entropy Block Step .

PVKM B can either use the appliance entropy supplied with the request or PVKM entropy or both for generating the new key. The key share is then used to generate the blinded key K r Block Step which is sent from PVKM B to Appliance A Arrow Step from which Appliance A can calculate the key Kusing the previously stored blinding value r Block Step .

When the protected item is accessed again Sub Process III appliance A obtains the specific key K by generating a request Block Step and transmitting the request to PVKM B Arrow Step . PVKM B retrieves its key share Block Step calculates the blinded key Block Step and transmits the blinded key to appliance A Arrow Step . Appliance A can then calculate the key K Block Step .

In some embodiments of the present invention an N location encryption process is implemented in which the embodiments described above can be extended to more locations within the environment. While the exemplary embodiments described above related to 2 location and 3 location encryption such approaches have been contemplated within the scope of the present invention to extend the applicability to N locations.

In some embodiments of the present invention trusted protocols for participating in a cluster are implemented in order to enable a cluster of entities i.e. appliances to ensure that each member of the cluster is worthy of trust in a virtualized or cloud environment. In particular such implementations inter alfa ensure that a new member of a cluster is secure and trustworthy.

In such embodiments a protocol for verifying trust in an entity within a cluster is defined. An appliance is provided with an identification ticket which may be an appropriate ticket as known in the art or the appliance is denoted as trusted in an appropriate database or any other technique that denotes a creation of trust in such an appliance. Such ticketing or denoting of the appliance is referred to herein as the appliance being flagged trusted. 

Before an appliance is flagged trusted the trust in that particular appliance must be established. An appliance is never flagged trusted unless it is vouched for by at least one trusted entity which may be another appliance a PVKM or any other trusted entity in the system. An appliance is flagged trusted only after being vouched for. A trusted entity which vouches for an appliance is presumed to be itself trusted only by the methods described herein as follows.

While one method for vouching trust may be preferable over another depending on the situation both approaches are provided to maintain generality. Once the trusted entity decides to vouch for an appliance the trusted entity vouches for the appliance to other members of the cluster and or the PVKM. The establishment of trust in the entity occurs when the newly vouched for appliance receives an appropriate secret or set of secrets which may be 

In exemplary embodiments of the present invention the vouching entity is an appliance which may remove its own encryption of the secrets in cooperation with the PVKM without either the PVKM or the vouching appliance knowing those secrets e.g. not knowing the master key . A new encryption of the secrets may then be applied in cooperation with the PVKM again without either the PVKM or any appliance knowing those secrets. The new encryption is appropriate for the receiving vouched for appliance.

Such embodiments not only enable trust in the new appliance but ensure that if one appliance is compromised then other appliances are not compromised since the secrets they contain are encrypted differently.

In some embodiments of the present invention HMAC is implemented in order to restrict use of the decryption key Dmaintained by the PVKM in the embodiments described above both for denial of service DoS prevention and for security. HMAC is a special checksum mechanism which is easy to calculate for the PVKM but very difficult to forge by any other entity. Using an HMAC implementation the PVKM calculates a ticket every time the PVKM encrypts data and sends the data to an appliance together with the cipher text. The PVKM refuses to decrypt data without a valid ticket. The PVKM can easily calculate the checksum from the cipher text enabling the approach to work even if the PVKM does not store the encrypted keys in its database.

In further embodiments of the present invention the PVKM and appliances are used as a secure virtualized key management system providing encryption keys to a user via an API Application Programming Interface . In such embodiments the user is responsible for performing the actual encryption while the implementation system only provides the keys. In such embodiments the PVKM appliances and the protocols between each of them may be any of the cases described above or any protocol which falls under the general principals described.

Furthermore the actual encryption keys supplied to a user in such embodiment may themselves be completely unknown to the implementation system i.e. completely unknown to the PVKM and the appliances . Such an implementation can be achieved by enhancing the protocol so that the user also participates in the process by requiring the user to issue a blinding value an encryption key an encryption key group or an encryption key pair of its own.

In such embodiments the PVKM and the appliances would switch their own encryption of the key and replace it by the encryption specified by the user without knowing the key. Such embodiments can be implemented such that neither the PVKM nor the appliances know the key value i.e. via an additional blinding using a blinding value supplied by the user . In such embodiments a secure virtualized key management system can serve as a key generation and key storage system on behalf of such users yet never know the values of the keys that the system serves to the users. Such implementations provide a further security enhancement by ensuring security since something completely unknown to the system cannot be stolen from the system. In particular key values cannot be stolen from the temporary memory caches of the system.

While the present invention has been described with respect to a limited number of embodiments it will be appreciated that many variations modifications and other applications of the present invention may be made.

