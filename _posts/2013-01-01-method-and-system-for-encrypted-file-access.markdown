---

title: Method and system for encrypted file access
abstract: A method and system for encrypted file access are provided. The method includes the steps of: receiving () an access request for an encrypted file (-) by an application (); determining () the application () making the access request; checking () if the application () is authorized for access; and if authorized, allowing the access request. The access request may be a read or write access by a destination or source application (). If the application () is authorized for access, the method checks () if the application () is authorized for unencrypted access; and if so, allowing unencrypted file access.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08799651&OS=08799651&RS=08799651
owner: International Business Machines Corporation
number: 08799651
owner_city: Armonk
owner_country: US
publication_date: 20130101
---
This application is a Divisional of U.S. application Ser. No. 12 361 268 filed on Jan. 28 2009 entitled METHOD AND SYSTEM FOR ENCRYPTED FILE ACCESS the entirety of which is incorporated herein by reference.

This invention relates to the field of encrypted file access. In particular the invention relates to file access through an encrypting system based on the accessing application.

Backup of data has become very important as the amount of data produced by enterprises and personal users has increased. The security of backup data must be maintained to prevent unauthorised access to the backed up data.

Many home users now backup their computers to the Internet and several anti virus packages offer Internet storage facilities. The problem with such facilities is that since the servers are publicly visible on the Internet the security of the user s information is heavily dependent on the application. This is very fragile given that bulk file encryption is typically done with a less secure symmetric key. If the application s security is cracked the user s personal information such as financial documents is compromised with a corresponding risk of fraud and identity theft.

Another form of backup is an encrypting file system which allows applications to access the contents of a file in clear while the actual data is stored on disk encrypted. If the storage media is stolen then an adversary has considerable work to decrypt the data. So that existing applications continue to work as before encrypting file systems decrypt data into clear through the standard file system application programming interfaces APIs .

However a problem arises if a virus such as a Trojan horse or a worm infiltrates the computer and accesses the stored data by the route of applications access. Malicious software can scan the hard disk and copy documents to the Internet.

An aim of the present invention is to provide an enhanced encrypting file system in which the encrypting file system conditionally decrypts data depending on the destination application. The encrypting file system may also conditionally encrypt data depending on the source application of the data.

According to a first aspect of the present invention there is provided a method for file access in a file encryption system comprising receiving an access request for an encrypted file by an application determining the application making the access request checking if the application is authorised for access and if authorised allowing the access request.

If the application is authorised for access the method may include checking if the application is authorised for unencrypted access and if so allowing unencrypted file access.

The step of determining the application making the access request may include calculating a hash value of the contents of the application. Calculating a hash value of the contents of the application may apply a hash function to the executable file of the application.

The step of checking if the application is authorised for access may include checking a record of file types to which an application is authorised for access. Checking a record of file types to which an application is authorised for access may include checking the record for the hash value of the application.

The record of file types to which an application is authorised for access may be administered by a security policy. The security policy may have a secure user interface for updating by an administrator. The security policy may be a group policy for a plurality of file encryption systems.

The access request may be a read request by a destination application. An application authorised for read access but not for unencrypted read access may only be allowed access to the encrypted file.

The access request may be a write request by a source application. An application authorised for write access but not for unencrypted write access may only be allowed access to the encrypted file by writing an encrypted file.

According to a second aspect of the present invention there is provided a computer program product stored on a computer readable storage medium for encrypted file access comprising computer readable program code means for performing the steps of receiving an access request for an encrypted file by an application determining the application making the access request checking if the application is authorised for access and if authorised allowing the access request.

According to a third aspect of the present invention there is provided a method of providing a service to a customer over a network the service comprising receiving an access request for an encrypted file by an application determining the application making the access request checking if the application is authorised for access and if authorised allowing the access request.

According to a fourth aspect of the present invention there is provided a file encryption system comprising an application identifier for identifying an application making an access request for an encrypted file a data store of application permissions for accessing file types means for checking if an application is authorised for access of a file and means for providing access to the file.

The system may include means for checking if the application is authorised for unencrypted access and may further include encryption or decryption means for providing access to the unencrypted file.

The application identifier may include a hash function for calculating a hash value of the contents of the application. The hash function for calculating a hash value of the contents of the application may apply the hash function to the executable file of the application. The data store of application permissions for accessing file types may identify applications by the hash value.

The system may also include a security means to administer the data store of application permissions for accessing file types. The security means may have a secure user interface for updating security policy by an administrator. The security means may administer a group policy for a plurality of file encryption systems.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numbers may be repeated among the figures to indicate corresponding or analogous features.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the invention. However it will be understood by those skilled in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present invention.

Referring to a computer system is shown within which the present invention may be implemented. The computer system may be a server workstation or a combination thereof and may be connected to other computer based resources. The computer system is suitable for storing and or executing program code and includes at least one processor coupled directly or indirectly to memory elements through a bus system . The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

The memory elements may include system memory in the form of read only memory ROM and random access memory RAM . A basic input output system BIOS may be stored in ROM . System software may be stored in RAM including an operating system . A file system associated with or included in the operating system may also be stored in RAM . Software applications may also be stored in RAM which interface with the operating system and file system through application programming interfaces APIs .

The computer system also includes non volatile storage means such as primary storage including a magnetic hard disk drive and secondary storage including magnetic and optical disc drives and USB storage devices. The drives and their associated computer readable media provide non volatile storage of computer executable instructions data structures program modules and other data for the system . Software applications may be stored on the non volatile storage means as well as the system memory .

The computer system may operate in a networked environment using logical connections to one or more remote computers via a network adapter .

Input output devices can be coupled to the system either directly or through intervening I O controllers. A user may enter commands and information into the system through input devices such as a keyboard pointing device or other input devices for example microphone joy stick game pad satellite dish scanner or the like . Output devices may include speakers printers etc. A display device is also connected to system bus via an interface such as video adapter .

The file system connects through a device driver to communicate with a non volatile storage device and to mange the files thereon. A file system generally includes methods for storing referencing sharing and securing files accessing file data and maintaining file integrity. There may not be a clear distinction between the file system and the associated operating system and any of the processes carried out by the file system may be performed by the operating system .

The file system operations may use an encryption file system driver which may be provided as part of the file system the operating system or separately. The encrypting file system driver is layered on top of the file system and provides support to communicate with an encrypting file system client service and to store files as encrypted data streams in non volatile storage .

File system level encryption often called file or folder encryption is a form of disk encryption where individual files or directories are encrypted by the file system itself. This is in contrast to full disk encryption where the entire partition or disk in which the file system resides is encrypted.

Unlike cryptographic file systems or full disk encryption general purpose file systems that include file system level encryption do not typically encrypt file system metadata such as the directory structure file names sizes or modification timestamps.

An encrypting file system is a file system driver with file system level encryption available in some operating systems. The technology transparently allows files to be encrypted on file systems to protect confidential data from attackers with physical access to the computer.

User authentication and access control lists can protect files from unauthorized access while the operating system is running but can be circumvented if an attacker gains physical access to the computer. One solution is to store the files encrypted on the disks of the computer. An encrypting file system usually does this using public key cryptography and aims to ensure that decrypting the files requires the correct key.

Referring to an example method of the operation of an encrypting file system when encrypting a file is illustrated. A file is encrypted with a bulk symmetric key also known as the file encryption key FEK to produce an encrypted file . Simultaneously the FEK is encrypted using the user s public key to produce an encrypted FEK . The encrypted file and the encrypted FEK are stored in alternative data streams or with the encrypted FEK in the header of the encrypted file .

Encrypting file systems use a symmetric encryption algorithm because it takes a relatively smaller amount of time to encrypt and decrypt large amounts of data than if an asymmetric key cipher is used. The symmetric encryption algorithm used will vary depending on the version and configuration of the operating system. The FEK is encrypted with a public key that is associated with the user who encrypted the file.

Referring to an example method of the operation of an encrypting file system when decrypting a file is illustrated. The encrypted file and encrypted FEK are separated . The encrypted FEK is decrypted using the user s private key to obtain the FEK . The FEK is used to decrypt the encrypted file to produce the original file .

To decrypt the file the encrypting file system driver uses the private key that matches the encrypting file system digital certificate used to encrypt the file to decrypt the symmetric key that is stored in the encrypting file system stream. The encrypting file system driver uses the symmetric key to decrypt the file. As the encryption and decryption operations are performed at a layer below the file system it is transparent to the user and all his applications.

Folders whose contents are to be encrypted by the file system are marked with an encryption attribute. The encrypting file system component driver treats this encryption attribute in a way that is analogous to the inheritance of file permissions in the file system. If a folder is marked for encryption then by default all files and subfolders that are created under the folder are also encrypted. When encrypted files are moved within a file system volume the files remain encrypted.

An enhanced encrypting file system is now described in which the encrypting file system conditionally decrypts data depending on the destination application. The encrypting file system driver is configurable so for example an encrypting file system driver might allow the application Microsoft Excel Microsoft and Excel are trade marks of Microsoft Corporation to read spreadsheets in the clear. In this case the encrypting file system driver would decrypt any spreadsheet files where the destination process is C Program Files Microsoft Office Office excel.exe. However a backup application would not be granted the same access to decrypted spreadsheet data and so any data it read would be returned encrypted. This extension to encrypting file systems also catches malicious software such as viruses that are scanning the hard disk and copying documents to the Internet.

Referring to a schematic diagram is provided of an enhanced encrypting file system driver in which the encrypting file system driver conditionally decrypts data depending on the destination application. The enhanced encrypting file system driver may also conditionally encrypt data depending on the source application. An encrypting file system driver is provided in conjunction with a file system as previously described. The file system accesses data files and folders stored in non volatile storage .

A recognized application for example Microsoft Excel is granted access to the clear text contents of the spreadsheet file. When the application reads the file the encrypting file system driver allows the file contents to be decrypted and accessed by the application in its decrypted form .

Any application or process that does not match a list of allowed applications is passed the encrypted file contents . This includes applications such as well known backup applications. However this also includes Trojan horses and other viruses which may be trying to access a file. The encrypting file system driver is responsible for checking the destination process and encrypting the file contents if required.

The encrypting file system driver can provide additional security checks on applications and does not rely on the application s executable file name for authentication of the application. For example a hash of the destination application can be checked to ensure that an adversary has not copied their own Trojan horse application named excel.exe into the file address C Program Files Microsoft Office Office .

Referring to a block diagram of a system including an enhanced encrypting file system driver is shown. The encrypting file system driver includes an encryption decryption means for encrypting and decrypting files. The encrypting file system driver is coupled to a file system for managing files stored on non volatile storage . Applications attempt read and write accesses of the files .

The encrypting file system driver includes an application identifier which includes a hash function or other form of signature generator to create a hash or signature from the contents of the accessing application . With a hash function the executable file for the application is used as the input data and is fed through the hash function. This produces a small fingerprint which identifies the application and which is very unlikely to collide with anything else fed through the hash function. The reason for the use of the hash function is to stop a potential adversary putting together an impostor executable file which has the same fingerprint as the real executable file.

Hash functions are designed to be fast and to yield few hash collisions in expected input domains. A hash function must be deterministic i.e. if two hashes generated by the same hash function are different then the two inputs were different in some way.

A desirable property of a hash function is the mixing property a small change in the input e.g. one bit should cause a large change in the output e.g. about half of the bits . This is called the avalanche effect.

Cryptographic hash functions assume the existence of an adversary who can deliberately try to find inputs with the same hash value. A well designed cryptographic hash function is a one way operation there is no practical way to calculate a particular data input that will result in a desired hash value so it is also very difficult to forge. Functions intended for cryptographic hashing such as MD5 are commonly used as stock hash functions.

The encrypting file system driver also includes a data store with a record of application names which may be the application hashes or derived therefrom and types of files to which the applications are allowed access. The data store may be administered by a security policy. The data store may include two levels of access. A first level of access is for applications which are authorized for unencrypted file access. A second level of access is for applications which are only authorized for encrypted file access. This second level may include applications in a write access in which the data is already encrypted. This second level may also include applications in a read access which are only allowed the raw encrypted data for example backup applications.

A user interface may be used for administration of the data store contents. The information of application names and types of files to which the applications are allowed access may be distributed as part of an enterprise security policy.

Using a domain or group policy a system administrator can define a policy just once and it will be applied to a whole group of users computers. In the described system for a customer running a network of users computers the configuration of the encrypting file system driver can be configured through a domain or group policy. This allows the system administrator to configure the data store of applications. For example it could be configured so that only Excel should be allowed to read and write spreadsheets.

The configuration information can be stored in many different places such as a file on a local machine s hard disk. The only requirement is that access to the information is tightly controlled so that a potential adversary cannot gain access to it. If the information is stored in a local file then this security can be achieved by only granting the encrypting file system driver and perhaps the system administrator access to the file. A user interface is simply provides a way for an authorised user such as a system administrator to view the current configuration and make changes if need be.

Referring to a flow diagram shows the process of a write access by an application . The process starts and an application opens a file for write access . The encrypting file system driver determines the application that is opening the file. This may be done by determining the application executable file name.

The encrypting file system driver calculates a hash from the contents of the executable file. A hash is calculated so that the driver can check the application making the request. Only using the executable file name to determine if an application should be granted access to a file is not sufficient since an adversary virus Trojan horse or worm may have replaced the application with its own version that operates differently.

It is then determined if the application is authorized for write access. This checks whether the application is allowed unencrypted access to the file. This check is in addition to any other operating system checks such as whether the current user has permissions to access the file. The determination of whether of not the application is authorized for write access references the data store which stores a list of the applications and types of files that they have been granted permission to access.

If access is not permitted to the file type by this application an error code is returned and the process ends .

If access is permitted to the file type by this application it is determined if the application is authorized for unencrypted write access.

If the application is authorized for encrypted write access data is written to the underlying file system without encrypting it. This is because the data is already be encrypted for example if the application is a backup application. The process then ends .

If the application is authorized for unencrypted write access data is then encrypted using the relevant encryption key. There are several different embodiments possible in key selection. A simplistic implementation uses a single key on a computer to encrypt and decrypt all data to its local file system. A more sophisticated embodiment could use multiple keys perhaps a different key for each and every file.

Referring to a flow diagram shows the corresponding process of a read access by an application . The process starts and an application opens a file for read access . The encrypting file system driver determines the application that is opening the file. This may be done by determining the application executable file name.

The encrypting file system driver calculates a hash from the contents of the executable file. A hash is calculated so that the driver can check the application making the request.

It is then determined if the application is authorized for read access. This checks whether the application is allowed unencrypted access to the file. The determination of whether of not the application is authorized for read access references the data store which stores a list of the applications and types of files that they have been granted permission to access.

If access is not permitted to the file type by this application an error code is returned and the process ends .

If access is permitted to the file type by this application it is determined if the application is authorized for unencrypted read access.

If the application is not authorized for unencrypted read access data is read from the underlying file system and returned in its raw state without decrypting it. The process then ends .

If the application is authorized for unencrypted write access the encrypted data is read from the underlying file system. The data is then decrypted using the relevant encryption key. As with write encryption there are several different embodiments possible in key selection. A simplistic implementation uses a single key on a computer to encrypt and decrypt all data to its local file system. A more sophisticated embodiment could use multiple keys perhaps a different key for each and every file.

Some known encrypting file systems provide access to the underlying raw encrypted data however this is done through a separate set of APIs. This does not provide the ability to configure access based on destination application or process.

An encrypting file system driver alone or as part of a file system may be provided as a service to a customer over a network.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In an embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

The invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

Improvements and modifications can be made to the foregoing without departing from the scope of the present invention.

