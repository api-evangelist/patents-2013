---

title: Method for data maintenance
abstract: A method for data storage implemented in a data storage system is disclosed. Data storage nodes may be interconnected by means of a communications network. The method may include sending a request for a first data item to a plurality of storage nodes. The first data item may include a reference to a second data item stored in the storage system. The method may include receiving the first data item from at least one storage node, and sending a request for the second data item to the plurality of storage nodes based on the reference included in the first data item.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09305012&OS=09305012&RS=09305012
owner: COMPUVERDE AB
number: 09305012
owner_city: 
owner_country: SE
publication_date: 20131205
---
This application is a continuation of U.S. patent application Ser. No. 13 224 415 filed Sep. 2 2011 which issued as U.S. Pat. No. 8 645 978 on Feb. 4 2014 the contents of which are hereby incorporated by reference herein.

This application includes subject matter that may be related to subject matter included in the following applications U.S. patent application Ser. No. 13 224 393 entitled A Method And Device For Maintaining Data In A Data Storage System Comprising A Plurality Of Data Storage Nodes filed Sep. 2 2011 which issued as U.S. Pat. No. 8 650 365 on Feb. 11 2014 U.S. patent application Ser. No. 13 224 404 entitled Method And Device For Writing Data In A Data Storage System Comprising A Plurality Of Data Storage Nodes filed Sep. 2 2011 which issued as U.S. Pat. No. 9 021 053 on Apr. 28 2015 U.S. patent application Ser. No. 13 224 424 entitled Method For Handling Requests In A Storage System And A Storage Node For A Storage System filed Sep. 2 2011 U.S. patent application Ser. No. 13 224 433 entitled Method For Data Retrieval From A Distributed Data Storage System filed Sep. 2 2011 which issued as U.S. Pat. No. 8 769 138 on Jul. 1 2014 and U.S. patent application Ser. No. 13 224 446 entitled Method For Updating Data In A Distributed Data Storage System filed Sep. 2 2011 which issued as U.S. Pat. No. 8 997 124 on Mar. 31 2015.

The present disclosure relates to an apparatus and method for accessing writing and deleting data in a data storage system comprising a plurality of data storage nodes the methods may be employed in a server and or in a storage node in the data storage system. The disclosure further relates to storage nodes or servers that may be capable of carrying out such methods.

Such a method is disclosed in US Patent Publication No. 2005 0246393 A1. This method is disclosed for a system that may use a plurality of storage centers at geographically disparate locations. Distributed object storage managers may be included to maintain information regarding stored data. One problem associated with such a system is how to accomplish simple and yet robust and reliable maintenance of data.

A method to maintain data in a data storage system comprising data storage nodes interconnected by means of a communications network is disclosed. The method may include sending a request for a first data item to a plurality of storage nodes. The first data item may include a reference to a second data item stored in the storage system. The method may also include receiving the first data item from at least one storage node and or sending a request for the second data item to the plurality of storage nodes for example based on the reference included in the first data item.

In an embodiment a virtual directory structure may be implemented in a storage system where the files are stored in an unstructured manner.

In an embodiment the files in the storage system may be accessed directly irrespective of their location in the system.

The first and second unique key may include a cluster address pointing out a subset of said storage nodes within the system and or a data item identifier identifying a data item within the subset of storage nodes. A reference to a data item may include the unique key.

In an embodiment the method may be implemented in large storage systems for example a storage system which include hundreds or thousands of storage nodes.

The method may comprise sending the first and second request from an application programming interface API.

For example by utilizing a common API to access the storage nodes the method may be easily implemented on many different platforms.

In an embodiment the method may be implemented on a dedicated device provided e.g. by a third party which may not be responsible for the maintenance of the storage nodes.

In an example embodiment implementing the API in a storage node may allow the number of access points into the storage system may be increased.

The method may comprise the API retrieving the unique key identifying the second data item from the received first data item.

For example the unique identifier for the second data item may be easily retrievable if an indication of the unique identifier is included in the first data item.

For example data files with payload data may be part of the directory structure e.g. stored in sub folders .

According to an embodiment a method for maintaining data in a data storage system including data storage nodes interconnected by means of a communications network may be implemented in a server and or a data storage node. The method may include storing a first data item in at least one storage node. The method may also include updating a second data item stored in at least one storage node. For example the second data item may be updated by adding a reference to the first data item in the second data item. Updating the second data item may include sending a request to at least one storage node that stores a copy of the second data item. The request may instruct and or request that the at least one storage node add a reference to the first data item to the second data item.

In an embodiment new items may easily be added to the directory structure for example by adding references to the new items to other items in the directory structure.

According to an embodiment a method for maintaining data may be implemented a server or data storage node included in a data storage system. The data storage nodes may be interconnected by means of a communications network. The method may include deleting a first data item stored in at least one storage node. The method may also include updating a second data item stored in at least one storage node by deleting a reference to the second data item in the second data item.

In an example embodiment items in the directory structure may easily be deleted for example by deleting references to the items.

According an embodiment a data storage system may include data storage nodes interconnected by means of a communications network. A server or node may include an application programming interface API and may be configured to send a request for a first data item to a plurality of storage nodes. The first data item may include a reference to a second data item stored in the storage system. At least one storage node may be configured to send the first data item to the API. The API and or storage node or sever may be further configured to send a request for a second data item to the plurality of storage nodes based on the reference included in the first data item.

For example a virtual directory structure may be implemented in a storage system where the files are stored in an unstructured manner.

Other objectives features and advantages of the disclosed embodiments may appear from the following detailed disclosure from the attached claims as well as from the drawings.

Generally all terms used in the claims are to be interpreted according to their ordinary meaning in the technical field unless explicitly defined otherwise herein. All references to a an the element device component means step etc. are to be interpreted openly as referring to at least one instance of said element device component means step etc. unless explicitly stated otherwise. The steps of any method disclosed herein do not have to be performed in the exact order disclosed unless explicitly stated.

Detailed embodiments of the disclosed methods and systems may be described with reference to the drawings. The present disclosure is related to a distributed data storage system comprising a plurality of storage nodes. An example structure of the system and the context in which it may be used is outlined in .

A user computer may access for example via the Internet an application running on a server . The user context as illustrated here may be therefore a client server configuration. However it should be noted that the data storage system to be disclosed may be useful also in other configurations for example utilizing other communication methods.

In the illustrated case two applications may run on the server . Of course however any number of applications may be running on server . Each application may have an API Application Programming Interface which may provide an interface in relation to the distributed data storage system and may support requests typically write and read requests from the applications running on the server. Data may be read and written to the storage system using the methods described in detail in U.S. patent application Ser. No. 13 125 524 filed Apr. 21 2011 which issued as U.S. Pat. No. 8 688 630 on Apr. 1 2014 the contents of which are hereby incorporated by reference herein. Methods of reading and writing of data therefore may not be further elaborated upon in detail herein. From an application s point of view reading or writing information from to the data storage system may appear to be the same as using any other type of storage solution for instance a file server or a hard drive.

Each API may communicate with storage nodes in the data storage system and the storage nodes may communicate with each other. Alternatively or additionally one or more of the storage nodes may include an API for supporting requests as disclosed above. These communications may be based on TCP Transmission Control Protocol and UDP User Datagram Protocol . Other communication protocols may also be utilized.

The components of the distributed data storage system may be the storage nodes and the APIs in the server which may access the storage nodes . The present disclosure may be described in relation to methods carried out in the server and in the storage nodes . Those methods may be primarily be embodied as combination software hardware implementations which are executed on the server and the storage nodes respectively. The operations of the server and or storage nodes may together determine the operation and the properties of the overall distributed data storage system.

Although in the server is illustrated as a member of the storage system which is separate from the storage nodes it should be noted that the server may be a storage node including server functionality.

The storage node may typically be embodied by a file server which is provided with a number of functional blocks. The storage node may thus include a storage medium which for example may include a number of internal e.g. connected via Integrated Drive Electronics IDE Serial Advanced Technology Attachment SATA and or the like or external hard drives e.g. connected via Universal Serial Bus USB Firewire Bluetooth and or the like optionally configured as a RAID Redundant Array of Independent Disk system. Other types of storage media are however conceivable as well.

Each storage node may contain a node list including the IP addresses of all storage nodes in its set or group of storage nodes. The number of storage nodes in a group may vary from a few to hundreds or thousands of storage nodes.

The storage medium may store one or more data items in the form of collection objects or payload data in the form of data files . A collection object may include a set of references. A reference may be a reference to one or more data files stored in the storage system e.g. data files . A reference may also be a reference to another collection object stored in the storage system. A reference may include a pointer e.g. a memory address to a storage location of a storage node . A reference may include an identifier of the collection object or data file referred to.

As will be disclosed in more detail below the collection object may be used for implementing a structured layer in the storage system. Data files referenced in the collection object may in such an implementation represent data files stored in the structure. Additional collection objects referenced in the collection object may in such an implementation represent subdirectories stored in the directory.

A collection object may be embodied as a data object having a predetermined format. The data object may be a special file in the file system of the storage medium in the sense that it may be a binary file to be interpreted by the API. In an example the data object may be a standard data file in the file system of the storage medium the data object may e.g. be a plain text file indicating the referenced collection objects and or data files . A data object may be readable using the same routines of the file system as the data files .

The collection object may include a field with an identifier of another collection object e.g. in the form of a string. The collection object may include a reference to the collection object . The collection object may be stored on the same storage node as the collection object or on another storage node than the collection object . The storage system may use the identifier in the field to locate and access the collection object . Thus the collection object may form a second data item which is identified by a second unique key.

In one embodiment in order to implement large storage systems spanning over multiple networks the data item identifiers may include two data elements. With reference to the first data element may be a cluster ID that may identify the cluster where the data item collection object or data file is located. The cluster address may be a multicast address . The multicast address may be utilized by the API to send a request for a data item to a specific cluster. The second data element may be a data item ID formed by a unique number that identifies the data item inside the cluster. The unique number may be a number of with a defined length e.g. 128 bits or the length may vary. The unique number may include a large number of bits enabling a large number of data items to be uniquely identified within the cluster. By this arrangement a collection element in one cluster may reference another collection element or data file in another cluster. In other words the first and second unique key may include a cluster address pointing out a subset of the storage nodes within the system and a data item identifier identifying a data item within the subset of storage nodes.

Referring back to the server may for example include a register indicating a storage node storing the collection object e.g. collection object associated with a specific identifier e.g. identifier . In another example the collection object may be located using the read method disclosed in U.S. patent application Ser. No. 13 125 524. Briefly according to this read method the server or a storage node may send a multicast message to the plurality of storage nodes . The multicast message may include the identifier of the desired collection object . Each storage node in response to receiving the multicast message may scan its storage medium for a collection object having said identifier. If found the storage node may respond and indicate that it stores the object sought after to the originator of the multicast message. The collection object may then be accessed by means of a unicast request sent to a responding storage node storing the collection object

According to the present embodiment multicast communication may be used to communicate simultaneously with a plurality of storage nodes. By a multicast or IP multicast is here meant a point to multipoint communication which may be accomplished by sending a message to an IP address which may be reserved for multicast applications. For example a message for example a request may be sent to such an IP address e.g. 244.0.0.1 and a number of recipient servers may be registered as subscribers to that IP address. Each of the recipient servers may have its own IP address. When a switch in the network receives the message directed to 244.0.0.1 the switch may forward the message to the IP addresses of each server registered as a subscriber.

In principle a single server may be registered as a subscriber to a multicast address in which case a point to point communication may be achieved. However in the context of this disclosure such a communication may nevertheless be considered a multicast communication since a multicast scheme is employed.

According to the present embodiment unicast communication may refer to a communication with a single recipient. A unicast communication may be initiated by a party of the network and may be directed to a single specific recipient.

In addition to the collection object the collection object may include a field with an identifier of a third collection object . The collection object may include a field with an identifier of a data file . In other words anyone of the collection objects or for example each of the collection objects may represent a second data item including a reference to third data item and the data file may represent a second data item including payload data for example an image.

By appointing the collection object as a root collection object the collection object may represent a root directory of the storage system. Analogously the collection object may represent a subdirectory of the root directory . The collection object may represent a subdirectory of the subdirectory . The data file may represent a data file stored in the subdirectory . The collection objects may thus define a hierarchical storage structure. The structure may be referred to as a directory tree.

With reference to a method for parsing a directory structure in order to access a file stored in a storage node may be disclosed.

The starting point of the directory structure may be a predefined root key. For example any of the storage nodes may include a root key. This key may be stored outside of the storage cluster and may be used to identify the first data item e.g. collection object in the directory structure. A storage cluster may have multiple root keys that enable the user to have multiple individual directory structures stored within the same storage cluster. The directory structures may span over several storage clusters. The root key may be stored together with external information describing the directory structure stored within the cluster.

In block the server may receive the root key which may identify the first data item and may pass the unique identifier to identify the file within the storage system to the API . In an example the API may be implemented in a storage node wherein the root key may be received in the storage node rather than in the server .

In block the API in the server may multicast a request for the data item e.g. the collection object identified by the root key to storage nodes in the storage system or to a subset of the nodes. For example the multicast message may be sent to a specific cluster for example using the data item identifier configuration disclosed in relation to . According to one embodiment the data item e.g. the collection object identified by the root key may be a special data item in the sense that it may include additional metadata which may be used by the system. Examples of such data may be information regarding access permissions to the items in the directory structure information where to store certain data items e.g. on a storage node with quick access such as an Solid State Drive SSD and the like.

In block storage node in response to receiving the multicast message may scan their respective storage mediums in an attempt to locate the data item identified by the data item ID in the root key.

For purposes of illustration it may be assumed in this example that nodes and locate the data item identified by the data item ID . In block the nodes that find the data item may reply with information about what other nodes may contain the data item and the current execution load e.g. how busy the nodes are how many request the nodes received how much free space is on the node etc. in the node . The requested data item may be stored in a plurality of storage nodes wherein the API may collect the information received from the nodes and may wait until it has received answers from more than 50 of the listed storage nodes that contains the data item before it may make a decision on which one to select for the retrieval of the data item. The decision may be based on which node that has the lowest execution load.

In block the API may send a unicast request for the specific file to the chosen storage node. In this example for purposes of illustration it may be assumed store node is chosen. API may retrieve the data item from the storage node . The API may maintain a list of all storage nodes that store copies of the file in the event of a read or communication failure with the selected node . If an error occurs the API may transparently select the next best node in the list and continues the read operation.

In block the API may interpret the content of the retrieved data item. If the directory structure comprises additional levels the retrieved data item may be a collection object . If so the API may read the field which may include an identifier referring to another collection object in the directory structure. For example the API may retrieve the unique key i.e. the identifier identifying the second data item e.g. the collection object from the received first data item e.g. the collection object . The process may then return to block and may continue parsing the directory structure. Thus both the first and second request may be sent from an application programming interface API. The process may continue until the last object in the directory structure has been identified and retrieved e.g. the data file whereupon the process may end at . In another example the API may send an update request to the identified object e.g. a command to alter or concatenate data in the data item corresponding to the object in the directory structure.

As an example it may be that the data file is located in the root of the directory structure. In such a case the process may be looped a single time since the first retrieved collection object may contain a reference to the data file . It is emphasized that the retrieved collection object in addition to including the reference to the data file may also include references to other data items such as collection object

Thus according to the above a method may implemented in a data storage system including data storage nodes interconnected by means of a communications network for accessing file. The method may include sending a request for a first data item e.g. collection object to a plurality of storage nodes . The first data item may include a reference to a second data item e.g. data file or collection object stored in the storage system. The method may include receiving the first data item from at least one storage node and sending a request for the second data item to the plurality of storage nodes based on the reference included in the first data item.

As an illustrative example with reference to the API may recursively read and interpret referenced envelopes to resolve a path in a directory structure. For example the API may identify an unstructured key that represents a file in the structured path. For example a user accessing the storage system may want to resolve the path Documents Sample Pictures Blue Hills.jpg .

In collection object may represent the root key I identified by the unique key and the identifier may include a reference to collection object representing the folder Documents identified by the unique key . The identifier in the collection object may include a reference to collection object representing the folder Sample Pictures . Finally the identifier in the collection object may include a reference to the data file comprising the payload data for the file Blue Hills.jpg . Thus by recursively reading the references in the collection objects a virtual file structure may be created in an unstructured storage system.

With reference to a method for parsing a directory structure in order to create a file in a storage node is disclosed.

similarly to the system discloses in the starting point of the directory structure is a predefined root key. The root key may be an arbitrary key and there may be many root keys throughout the system. This key may be stored outside of the storage cluster and may be used to identify the first data item e.g. collection object in the directory structure.

In block the server may receive the root key and may pass the unique identifier to identify the file within the storage system to the API.

In block the API in the server may multicast a request for storing the data item e.g. the collection object including the identifier to all storage nodes in the storage system or to a subset of the nodes e.g. within a specific cluster for example using the data item identifier configuration disclosed in relation to .

In block storage nodes in response to receiving the multicast message may verify that the data item ID is not already in use.

In block a storage node which that fails to find an existing file with that specific identifier may reply with an acknowledgment that may indicate free storage space on the storage node an indication of the age of the hardware that the storage node is running on current CPU load and or the geographical position of the storage node in the form of latitude longitude and altitude or the like.

In block the API may select three storage nodes e.g. storage nodes and based on the data returned from storage nodes that responded to the multicast request. When the three most suitable nodes have been selected the API may send a request to the three nodes simultaneously to store the data item. If an error occurs during the transfer of the data item to one of the selected nodes the operation continues for example as long as more than 50 of the selected nodes are operational.

In block the identifier field in the data item one level higher up in the directory structure e.g. the first data item the collection object may be updated with a reference to the stored data item e.g. the collection object either by retrieving the first data item according to the read method according to the above or by accessing the first data item directly for example if the server has cached the identifier of the first data item.

In order to increase the data integrity in the system the method above may be supplemented with the act of prior to storing the data item retrieving the first data item in case the communication with all storage nodes should be lost after the data item has been stored but before the first data item is updated. By this procedure the API may resume the update procedure once the communication with the storage nodes is resumed.

Thus according to the above a method may be implemented in various devices within a data storage system including data storage nodes interconnected by means of a communications network. The method may include storing a first data item in at least one storage node and updating a second data item stored in at least one storage node by adding a reference to the first data item in the second data item.

With reference to a method for parsing a directory structure in order to delete a file in a storage node is disclosed.

In similarity to the disclosure in relation to the starting point of the directory structure may be a predefined but arbitrary root key. This key may be stored outside of the storage cluster and may be used to identify the first data item e.g. collection object in the directory structure.

In block the server may receive the root key and may pass the unique identifier to identify the file within the storage system to the API.

In block the API in the server may multicast a query regarding the location of the data item e.g. the collection object including the identifier to storage nodes in the storage system or to a subset of the nodes e.g. within a specific cluster for example using the data item identifier configuration disclosed in relation to .

In block storage nodes in response to receiving the multicast message may scan their respective storage medium to locate data item identified by the data item ID .

In block the nodes that locate the data item may reply with information regarding other nodes that may store the data item and the current execution load in the node. The requested data item may be stored in a plurality of storage nodes. The API may collect the information received from the nodes and may wait until it has received answers from more than 50 of the listed storage nodes that contains the data item before making a decision on which nodes to select for the deletion of the data item.

In block the API may send a unicast request to delete the specific file e.g. the collection object to the chosen storage nodes.

In block the identifier field in a data item one level higher in the directory structure e.g. the collection object may be updated by deleting the reference to the deleted data item e.g. the collection object . The update may occur by retrieving the first data item according to the read method described above and or by accessing the first data item directly for example if the server cached the identifier of the first data item. In the case where the data item to be deleted is located a number of levels down in the directory structure the delete operation may be expressed as the method disclosed in relation to with the addition of i deleting the first data item and ii updating the second data item by deleting the reference to the first data item.

Thus a data deletion method may be implemented in a data storage system including data storage nodes interconnected by means of a communications network. The method may include deleting a first data item stored in at least one storage node. The method may also include updating a second data item stored in at least one storage node by deleting a reference to the first data item in the second data item.

The collection objects may be handle and maintained in manner similar to data files. This may allow the data to be stored in a flat storage structure e.g. without any subdirectories or within a single directory. A virtual hierarchical storage structure may be created by adding collection objects including references to other collection objects and or data files . It even allows the same data to be organized in several different virtual hierarchical storage structures by using different sets of collection objects .

For data security reasons some or all information stored in the storage system e.g. the collection objects and or the data files may be stored redundantly in the storage system. The collection objects and the data file may be stored at two or more storage nodes . Each instance of a collection object or data file may be associated with the same identifier. In such a case the above described read method may result in a response from each storage node storing the collection object. A redundantly stored collection object may thus be retrieved from either one of or all of the storage nodes storing the collection object.

Several embodiments which demonstrate the disclosed method and system have been described. However as is readily appreciated by a person skilled in the art other embodiments in addition to the ones disclosed above are equally possible that are in accordance with the methods and products described herein. The foregoing examples are not meant to be limiting and the scope of the protection is to be defined by the appended patent claims.

