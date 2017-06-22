---

title: Server and method for secure and economical sharing of data
abstract: The present invention relates to a web server having a web application using published API of one or more cloud storage providers, said web application being dedicated to secure and economical sharing of encrypted files residing at the cloud storage providers, said files being managed under a virtual folder which is shared by a group of different entities.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09626527&OS=09626527&RS=09626527
owner: GEMALTO SA
number: 09626527
owner_city: Meudon
owner_country: FR
publication_date: 20131104
---
This invention relates to secure sharing of encrypted data stored on a third party server on the Internet. The need for such encryption arises in the context of cloud storage where enterprises and individual users store their data on a cloud storage service on the Internet instead of a local repository. The cloud concept enables data to be publicly accessible from a variety of end points such as office PC home PC and user s mobile devices. Specifically the invention concerns a web application server that leverages the published API of one or more cloud storage providers. The web application is dedicated to secure sharing of encrypted files residing at the cloud storage providers. According to the invention the secure sharing economizes the utilization of storage resources on the cloud storage providers from a user s point of view.

While the cloud model offers convenience and reduces cost there are always lingering concerns about the security and confidentiality of data stored at the cloud storage service. Such concerns are especially critical when dealing with enterprise data that needs to be shared with other authorized users both internal colleagues and external partners.

Cloud storage providers such as Box and Dropbox publish APIs for 3party companies to use for developing custom products that offer additional file related services built upon the storage capability of the cloud provider. When it comes to file sharing the available APIs vary between storage providers and do not always include all the necessary APIs for an end to end solution. Products exist to enable the encryption of data but no client managed encryption solution is known to offer flexible use of data storage and dynamic access control without re encrypting the stored data. Existing products also do not support file sharing between several devices and or between several users.

The present invention aims at providing a secure and economical sharing of files among several entities.

The present invention is defined in its broadest sense as a server wherein files are managed under a virtual folder which is shared by a group of different entities each entity having an identifier said server having an interface with the entities to receive and send them files and having an interface with the cloud storage providers to receive and send files from and to the corresponding folder stored at the cloud storage provider said server further having for the implementation of the web application 

The invention uses the published API of the storage provider and offers a web interface to the users which is very similar to the storage provider s user interface. The users get the same experience as though they were using the cloud storage service directly.

This invention allows secure sharing of encrypted data stored at a storage provider using an authorization control list ACL and the creation of virtual share folders to store encrypted files. With the invention the authorization to access virtual share folder is managed in the ACL. With the use of the authorization control list managed by the web server according to the invention publically accessible file s URI are protected. The web server manages the aggregation to present unified content for a shared folder to all the users in the shared folder s ACL. The web server of the invention controls the individual file URI s and verifies user authorization requests against each shared folder s ACL.

The use of ACL enables the users to be added to and removed from a shared folder s ACL dynamically without modifying the encryption on files already stored in the shared folder. When a user is removed from a shared folder s ACL two additional steps are performed. First any files contributed by this removed user are copied to the storage service account of the owner of the shared folder. This ensures that other users of the shared folder can continue to have access to these shared files. Second these shared files are deleted from the storage service account of the removed user so that they do not occupy storage space and unnecessarily use up storage quota.

With the invention the data sharing is accomplished using shared folders created for this purpose and where files are uploaded. The web server maintains a dedicated unique encryption master key for each shared folder. This encryption master key is used to protect all files added to the specific shared folder or to the sub folders created inside this shared folder. Access to shared folders is controlled by the web server itself and the authorization control list and not by the storage provider. The web server of the invention manages a separate ACL for each shared folder allowing the owner to specify which users are authorized to access the shared folder.

Also each shared file is hosted on a single account on the storage provider. The account used is of the user who uploads the file. Thus it only counts against storage quota of a single user. All other users can access the file for free using the public URI as soon as they are registered with access authorization in the authorization control list. The file sharing according to the invention is economical because data are stored in a single account. It is also economical for users as except for the account where data are stored other participants of the shared folder do not see the quota usage on their account.

In addition the solution of the invention removes the need for synchronization of files between different users in a sharing scenario. Also no data is lost when one or more users in the share group leave the group. The files stored on their account are preserved for use by other members of the group. Data in files can thus be shared with other selected users of the web server.

According to a first preferred embodiment the server of the invention further includes an encryption decryption module to encrypt the file to be shared inside the server the access to the encrypted file being provided by this encryption decryption module said encryption decryption module also decrypting the retrieved shared encrypted file before forwarding it to requesting entity.

In this embodiment by acting as an intermediary between user s browser and cloud storage the web server of the invention can seamlessly encrypt data before forwarding it to the storage provider and decrypt it before passing it back to the user.

It has to be noted here that the term clear text does not refer to text files but rather to files that are in the clear and not yet encrypted. Once encrypted such files are commonly called cipher text . Both binary and text ASCII files are thus implied.

All users that have access to a shared folder are allowed to download files belonging to this shared folder. To download a file the web server uses the public link created in step above to retrieve the encrypted file from the storage provider. The encrypted file is decrypted using the shared folder master key and then downloaded to the user s client browser in the clear.

Advantageously said key generator also generates an entity specific key and have a secure provisioning module to provision said entity with the specific key requests from this entity being further signed using the entity specific key before being sent to the server said server further includes a cryptography module to verify such signatures.

This advantageous embodiment enables to check the origin of the request to store files or the origin of the request to access stored files. It specially concerns the mobile devices for which security breach can be observed.

In advantageous applications of the invention entities are chosen among the group formed by web browser clients PC client applications mobile devices.

Such entities are the most commonly used to access cloud service provider. They are also particularly concerned by security issues and the invention would be particularly adapted to deal with such issues. In the case of PC client applications the server cannot send push notifications and the invention is thus particularly adapted to this situation.

According to a second embodiment of the invention said server provisions entities of the group with the generated master key in order to enable them to encrypt themselves a file to be shared and to send the encrypted file to said server the access to the encrypted file being thus provided by such an entity.

In this embodiment the invention is a fully client managed solution to encrypt data stored in the cloud. The file is encrypted on the user equipment side before being sent to the web server. The web server here manages the authorization control list and the forwarding to the storage provider. It still enables a single account to be charged for storage. It can be noted here that a same web server could implement the two presented embodiments depending on the addressed storage provider or on the kind of concerned user equipment for example.

According to a particular feature the single account where the encrypted file is stored at the cloud storage provider is the account of the entity from which the file originates.

This optional feature enables to structure the file storage and the share folders management. Files in a shared folder are thus stored in their respective user s storage provider account depending on who uploaded the file.

According to another particular feature the single account where the encrypted file is stored at the cloud storage provider is the account of the entity from which the file was last updated.

This feature enables to keep the economical advantages of the invention while providing equality of download access between different users.

On an applicative point of view entities can be different users or different devices from a same user.

The present invention also relates to a method to manage the secure and economical sharing of at least one virtual folder in which are stored encrypted files using a server web application using a published API of a cloud storage provider said folder being shared by a group of different entities each entity having an identifier said method comprising the steps of 

said method further comprising the steps of on request from one entity of the group for a file in the folder 

This method implemented in a machine or a group of machines enables to produce a server of the invention and to propose a secure and economical sharing of files according to the invention. It has to be noted that the method includes preferably a step of encrypting the clear file said method being fully implemented in a server.

According to a specific embodiment the method further includes a step of generating an entity specific device key a step of provisioning said entity with the specific key and said entity signing requests relative to the shared folder using said entity specific key a step of verifying signature of requests originating from the entity.

According to an advantageous feature the method further includes a step of adding a sharing user to share the shared folder in the authorization control list.

This feature enables to add a new user to the share while not having to modify the already encrypted files.

Advantageously the method further includes a step of removing an existing user from the authorization list of a shared folder so that this user later does not have access to the files in the given shared folder.

Again the access control list feature enables to easily manage authorization to access file without having to delete the file from the storage folder in the service provider or uploading a newly encrypted file to the storage provider. The encryption of the file does not change even if the list of users having access to the file is modified

Furthermore the method advantageously further includes the step of copying all files contributed by the removed user to another user s account and the step of cleaning up the files from the storage account of the user who was removed from share.

This feature enables any user that wants to be removed from a sharing list not to keep the shared files stored on his her own account thereby limiting the storage resources used on the user s account.

To the accomplishment of the foregoing and related ends one or more embodiments comprise the features hereinafter fully described and particularly pointed out in the claims.

The same elements have been designated with the same reference numerals in the different drawings. For clarity only those elements and steps which are useful to the understanding of the present invention have been shown in the drawings and will be described.

In a first step U the web server WS generates a master key Ks to be used for the encryption of files in a virtual folder VF. Such key can be generated in software HSM hardware security module or in SE secure element such as smart card . The keys can be stored in software HSM or in SE.

In the presented embodiment the virtual folder VF is associated with the account of the entity UEA. Then in this embodiment the entity UEA sends a request to store a clear file CF in the virtual folder VF at the storage provider SP. In a step U the web server WS then consults an authorization control list ACL VF UEA listing for each shared folder VF identifiers of entities authorized to access files in said shared folder VF. If the entity UEA from which the file is originated is authorized to access the folder in a step U the web server then uses the master key Ks to encrypt the clear file CF in an encrypted file EF. This encrypted file EF is then sent in a step U to be stored in a storage folder SF on the UEA s account on service provider SP. The storage folder SF contains all files contributed by the given user to the virtual folder VF. Indeed virtual folders VF exist only in the server WS of the invention. Service provider SP has only storage folder SF associated to a user and where the encrypted file EF is stored as part of the content. At last in a step U the virtual folder VF is updated to include the newly uploaded file CF.

If the user equipment UEB is authorized to access the shared folder VF in a step D the web server retrieves the encrypted file EF from the storage provider SP. Then it decrypts the encrypted file in a step D. At last the clear file CF is sent to the user equipment UEB in a step D.

With the invention the file added to share folder is encrypted and uploaded to user s account on SP. Each user with authorization to access the shared folder can have an account at a different SP. When a file is added all users in the shared folder group have immediate access to it. The added file resides in only one location so no synchronization is needed. Since file resides in only one location only one user s storage space is used on the SP. To download an encrypted file from the shared folder file is decrypted in the web server and passed to the user.

Also when the removal of a user from a shared folder is required the said user is simply removed from the ACL for the shared folder. Files already uploaded to this shared folder do not have to be changed. Files contributed by the removed user are advantageously copied to another user s account on the SP or the removed user s account on SP in cleaned up by deleting files. When the deletion of a shared folder is required the corresponding ACL is removed so that no user has authorization to access to the shared files. Besides each user s account are cleaned up on their corresponding SP so files are deleted. When the system is able to deal with several service providers the ACL has extra references to indicate which service provider is used.

On is presented another embodiment of the invention where the master key Ks is generated in a step U. Here the master key Ks is sent to the user equipment UEA in a step U . The encoding of a clear file CF is performed by the user equipment UEA in a step U . The encrypted file EF is then sent to the web server WS in a step U . The web server WS checks the access authorization of UEA in shared folder VF within the authorization control list ACL VF UEA in step U . If UEA is authorized the encrypted file EF is sent for storage to the storage provider SP in a step U . At last the virtual folder VF is updated in a step U to include the newly uploaded file CF.

Then under request R EF for the encrypted file EF from UEAB the web server checks the authorization of the user equipment UEB in the authorization control list ACL VF UEB in a step D . If the user equipment UEB is authorized to access the shared folder VF the encrypted file EF is retrieved by the web server Ws from the storage folder SF in a step D . This encrypted file EF is then forwarded to the user equipment UEB in a step D before being decrypted using Ks in the user equipment UEB itself in a step U .

Embodiment described on are particularly adapted to the mobile devices. The encryption in the user equipment itself can indeed be strongly wished as it reduces the risk to have data malevolently spied.

In this embodiment any upload download request is signed in a step H by the user equipment using its device key Kd. Clear file transmission is not signed but done under SSL TLS layer. The signed request Ris then sent to web server WS for verification of the signature in a step H and for processing of the request. Typically the authorization of the user equipment is then checked in a step H. If UEA is authorized to access the shared folder VF depending on the nature of the request R encoding or decoding are performed in the web server and the encoding file EF is sent to or retrieved from the shared folder VF as disclosed in more details in .

It is noted here that it can be advantageous in case the user equipment is a mobile device to also send the share folder master key to the user equipment with the device specific key. In this case the mobile device is able to encrypt decrypt itself the file to be stored or to retrieve. It solves security issues specific to mobile devices in particular when file is uploaded from such a mobile device.

Typically the user equipment UEA is connected to the web server to a browser client. In a first step S the client logs in to the web server WS. Then the user requires access to storage space provided by the storage provider SP. This consists in a request to get a share folder list sent in a step S. The web server then consults and builds a lookup table forming an authorization control list ACL in a step S. A list of share folders for user UEA is then sent to user equipment UEA in a step S.

The user chooses a share folder and asks for the access to this share folder in a step S. The web server then checks the user permission to view in a step S and gets a list of files in this share folder in a step S. The list of files in share folder is returned to UEA in a step S. In a step S the user equipment uploads a file to the selected share folder. The web server WS checks the permission to add the file in a step S. In a step the web server WS gets a master key for the share folder. Typically the master key is retrieved from storage or generated using a key generator.

Then the web server WS encrypts the file using the master key in a step S. The encrypted file is then uploaded to the storage provider SP in step S. The web server WS thus gets public reference for uploaded file in step S. It also gets copy reference for uploaded file in a step S. Those meta data are stored by the web server about the new file in a step S. The database thus includes at least a public reference and a copy reference for each file stored at the storage provider SP. Public reference is typically a URL that points to the file on storage provider SP. Anyone who has this URL can download the file. It can be used either directly through a browser or through the API. CopyRef is a unique string identifier that can be used to copy a file from one user s account to another user s account on the same storage provider SP. This is done through API and no download happens.

Advantageously a confirmation for the uploading of the file is at last sent to the user equipment UEA in a step S.

On a downloading sequence is presented. A user equipment UEB logs in to the web server WS in a step T. It asks for a share folder list in a step T. In a step T the lookup table of the authorization control list is consulted. The list of share folders for this user is then sent to the user equipment UEB in a step T. The user then selects a share folder in a step T. The web server WS checks the permission to view for the user equipment UEB in a step T and gets a list of files in the selected share folder in a step T. The list of files in share folder is returned to user equipment UEB in a step T. A file is then selected for download in a step T.

The web server WS then checks the permission to download the file in step T. In a step T the web server WS then gets the public reference for the file from the database in web server WS. It uses this public reference to download the file from UEA s storage account in a step T. Then the web server gets the master key for the concerned share folder in a step T. In a step T the web server WS decrypts the encrypted file. At last the decrypted file in clear is forwarded to user equipment UEA in step T.

The invention provides a complete user client owner control over encryption of data before sending to cloud storage provider. With the invention the same user can access his data securely from multiple devices office PC home PC mobile phone. Also the data can be securely shared among multiple users both internal to an enterprise and external partners. At last less storage quota is required to participate in file sharing than the sharing features offered directly by the storage providers.

In the above detailed description reference is made to the accompanying drawings that show by way of illustration specific embodiments in which the invention may be practiced. These embodiments are described in sufficient detail to enable those skilled in the art to practice the invention. It is to be understood that the various embodiments of the invention although different are not necessarily mutually exclusive. In addition it is to be understood that the location or arrangement of individual elements within each disclosed embodiment may be modified without departing from the spirit and scope of the invention. The following detailed description is therefore not to be taken in a limiting sense and the scope of the present invention is defined only by the appended claims appropriately interpreted along with the full range of equivalents to which the claims are entitled.

