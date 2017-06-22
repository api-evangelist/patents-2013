---

title: Virtual file system integrating multiple cloud storage services and operating method of the same
abstract: Disclosed is a virtual file system integrating and managing multiple cloud storages. A virtual file system may comprise an API database storing information on open API of the cloud storages, a storage state database storing state information of the cloud storages, a metadata database storing metadata of the cloud storages, a cloud storage allocation part receiving an user request and selecting a cloud storage appropriate for the user request among the cloud storages by referring to the storage state database and the metadata database, and an API mapping part reading out open API information of the cloud storage selected by the cloud storage allocation part from the API database, converting the user request to an open API of the selected cloud storage, and transferring the converted open API to the selected cloud storage.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09384209&OS=09384209&RS=09384209
owner: POSTECH ACADEMY—INDUSTRY FOUNDATION
number: 09384209
owner_city: Gyeongbuk
owner_country: KR
publication_date: 20131210
---
This application claims priorities to Korean Patent Application No. 10 2012 0142754 filed on Dec. 10 2012 in the Korean Intellectual Property Office KIPO the entire contents of which are hereby incorporated by references.

Example embodiments of the present invention relate to a file system and more specifically to a method for providing a file system environment integrating multiple cloud storages by mapping multiple cloud storage services supporting open API to POSIX interfaces and a file system using the method.

Commercial could storage service vendors provide users with browsing tools for the users to use their cloud storage services and the browsing tools may be classified into three types as follows.

A first type of the browsing tools is a web interface operating on web browser without installing a separate program in system of the users. A second type of the browsing tools is an application app which operates in mobile terminal of the users for accessing cloud storage. A third type of the browsing tools is a program for mount and synchronization which can provide the same interface as that of local storages such as a file explorer and the like.

Also most of commercial cloud storage services may provide open application programming interfaces Open API for users or companies wanting to provide a third party service to develop applications using the commercial cloud storage services.

The open APIs usually perform communications with the cloud storages by using Representational State Transfer REST or Simple Object Access Protocol SOAP interfaces with Extensible Markup Language XML or Javascript Object Notation JSON format of data. Such the open API may basically provide a function of uploading files in the cloud storage a function of downloading files stored in the cloud storages a function of creating new folders and a function of deleting files or folders in the cloud storages. Also a function of retrieving meta data such as creation dates of the stored folders and files and sizes of them may be provided and any other extended functions may be provided according to their services.

The mount and synchronization program which can be installed in a personal computer of the user may operate by mapping POSIX interfaces to open API of the cloud storage service. That is when the user wants to copy specific files of local storage to cloud storage system calls open read write and release of the POSIX interface may be converted to corresponding APIs of the cloud storage service and the converted requests may be provided to a server of the cloud storage service.

However when a plurality of cloud storage services are used browsing programs dedicated for each cloud storage service should be developed and managed respectively. For example when two cloud storage services service A and service B are supposed to be used and the user wants to copy or move a file stored in the service A to the service B there has been an inconvenience that the user should download the specific file to local storage by executing a browsing program for the service A and upload the downloaded specific file to the service B by executing a browsing program for the service B.

That is direct move or replication of data between difference cloud storages is impossible and so the inconvenience that the user should manually perform downloading and uploading exists. In addition the user should check spaces remaining in respective cloud storage and upload download performance of the respective cloud storage before performing downloading and uploading. Also when a synchronization function of the dedicated browsing program is executed there may be a problem that the same size of space accommodating stored data in cloud storage is needed in a local storage.

Accordingly example embodiments of the present invention are provided to substantially obviate one or more problems due to limitations and disadvantages of the related art.

Example embodiments of the present invention provide an integrated virtual file system which can provide an integrated virtual file system environment by integrating multiple cloud storages.

Example embodiments of the present invention also provide an operation method of an integrated virtual file system which can provide an integrated virtual file system environment by integrating multiple cloud storages.

In some example embodiments a virtual file system integrating and managing multiple cloud storages may comprise an API database storing information on open API of the cloud storages a storage state database storing state information of the cloud storages a metadata database storing metadata of the cloud storages a cloud storage allocation part receiving an user request and selecting a cloud storage appropriate for the user request among the cloud storages by referring to the storage state database and the metadata database and an API mapping part reading out open API information of the cloud storage selected by the cloud storage allocation part from the API database converting the user request to an open API of the selected cloud storage and transferring the converted open API to the selected cloud storage.

Here the virtual file system may further comprise an information collecting part collecting the information on open API the metadata and the state information of the cloud storages and storing the information on open API the metadata and the state information of the cloud storages in the API database the storage state database and the metadata database.

Also the information collecting part may collect the information on open API of the cloud storages by referring to API description files of the cloud storages.

Also the information collecting part may collect the metadata and the state information by calling API of respective cloud storage of the cloud storages through the API mapping part.

Here the state information may include at least one of information on total capacity of corresponding cloud storage information of used capacity of corresponding cloud storage and information on upload or download performance of corresponding cloud storage.

Here the metadata may include at least one of information on names of files or folders existing in corresponding cloud storage information on creation dates and or modification dates of files or folders existing in corresponding cloud storage information on size and directory path of files or folders existing in corresponding cloud storage.

Here the virtual file system may further comprise a usage pattern monitoring part monitoring usage pattern of the file system by users and a performance monitoring part monitoring performances of the cloud storages wherein the cloud storage allocating part may select the cloud storage appropriate for the user request based on information provided from the usage pattern monitoring part and the performance monitoring part.

Here the cloud storage allocation part may select a cloud storage having a best upload performance monitored by the performance monitoring part as the cloud storage appropriate to the user request when an access type of an objective file of the user request monitored in the usage pattern monitoring part is a type in which the objective file is more frequently uploaded than downloaded.

Here the cloud storage allocation part may select a cloud storage having a best download performance monitored by the performance monitoring part as the cloud storage appropriate for the user request when an access type of an objective file of the user request monitored in the usage pattern monitoring part is a type in which the objective file is more frequently downloaded than uploaded.

In other example embodiments a method of operating a virtual file system integrating and managing multiple cloud storages may comprise initializing at least one database storing information on open API state information and metadata of the cloud storages monitoring usage pattern of the file system by users and performances of the cloud storages receiving a user request and selecting a cloud storage appropriate to the user request among the cloud storages by referring to the state information and the metadata stored in the at least one database and to the usage pattern of the file system and the performances of the cloud storages and converting the user request to an open API of the selected cloud storage by referring the information on open API stored in the at least one database and transferring the converted open API to the selected cloud storage.

Here the initializing at least one database may comprise collecting the information on open API the metadata and the state information of the cloud storages and storing the information on open API the metadata and the state information of the cloud storages are stored in the at least one database.

Also the information on open API of the cloud storages may be collected by referring to API description file of the cloud storage.

Also the metadata and the state information may be collected by calling API of respective cloud storage of the cloud storages.

Here the state information may include at least one of information on total capacity of corresponding cloud storage information of used capacity of corresponding cloud storage and information on upload or download performance of corresponding cloud storage.

Here the metadata may include at least one of information on names of files or folders existing in corresponding cloud storage information on creation dates and or modification dates of files or folders existing in corresponding cloud storage information on size and directory path of files or folders existing in corresponding cloud storage.

Here a cloud storage having a best upload performance monitored may be selected as the cloud storage appropriate for the user request when an access type of an objective file of the user request monitored is a type in which the objective file is more frequently uploaded than downloaded.

Here a cloud storage having a best download performance monitored may be selected as the cloud storage appropriate for the user request when an access type of an objective file of the user request monitored is a type in which the objective file is more frequently downloaded than uploaded.

Example embodiments of the present invention are disclosed herein. However specific structural and functional details disclosed herein are merely representative for purposes of describing example embodiments of the present invention however example embodiments of the present invention may be embodied in many alternate forms and should not be construed as limited to example embodiments of the present invention set forth herein.

Accordingly while the invention is susceptible to various modifications and alternative forms specific embodiments thereof are shown by way of example in the drawings and will herein be described in detail. It should be understood however that there is no intent to limit the invention to the particular forms disclosed but on the contrary the invention is to cover all modifications equivalents and alternatives falling within the spirit and scope of the invention. Like numbers refer to like elements throughout the description of the figures.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this invention belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

Referring to multiple cloud storages and exist. The multiple cloud storages may include cloud storages according to commercial cloud storage services and non commercial cloud storages. It is not required that the cloud storages are newly developed or modified for cooperating with a unified virtual file system according to the present invention. The cloud storages may be configured to provide users with services through at least one of the three types of browsing tools such as the web interfaces the dedicated app and the mount and synchronization program.

On the other hand the cloud storages should provide open APIs for the unified virtual file system to access them. However the open API provided from the cloud storages are not required to be standardized and so each of the cloud storages may have its unique open API.

The cloud storages and may be connected to the unified virtual file system according to the present invention through an internet . An user may access the virtual file system via their local computer and the virtual file system may be configured to convert requests of the user transferred via the local computer into API of the multiple cloud storages and and transfer the requests to the cloud storages by calling the converted API. That is we can understand that the virtual file system provides the local computer with abstraction on multiple cloud storages existing in the lower side.

In the conventional environment which the virtual file system does not exist the local computer of the user should access the cloud storages directly through the internet . For example the user should use at least one of the three type of browsing tools such as the web interfaces the dedicated app and the mount and synchronization program.

However in the case of the virtual file system according to the present invention the local computer may operate under a unified file system environment integrating storages of the multiple cloud storages provided by the virtual file system.

The local computer may include a personal computer a notebook laptop computer a tablet a smartphone and the like that is any computing device which can access the cloud storages via the internet and can use file upload download services and synchronization service provided by the cloud storage services.

Referring to an example embodiment of a unified cloud storage virtual file system according to the present invention may include an API database a storage state database a metadata database a cloud storage allocating part and an API mapping part .

Meanwhile the unified cloud storage virtual file system may further comprise an information collecting part as an additional component collecting information to be stored in the databases and . The detail role of the information collecting part will be explained later.

First databases referred by the unified cloud storage virtual file system during operation of the unified cloud storage virtual file system may include the API database the storage state information and the metadata database .

The API database is a component storing service name and information on APIs performing file uploading file downloading folder creation file deleting metadata reading for each cloud storage of the multiple cloud storages and .

The metadata database is a component storing metadata for the multiple cloud storages and which are being managed by the virtual file system . The metadata may mean names sizes creation and modification dates and whole director paths of files and folders stored in each of the cloud storages.

At last the storage state database is a component storing state information of each cloud storage. The state information may include information on total capacities used capacities performance information for example upload speed or download speed of each cloud storage. Since the information related to the total capacity and used capacity of each cloud storage is information which can be obtained by analyzing the above described metadata information the metadata database may be configured to take a role of the storage state database in addition to a role of the metadata base.

Here the above databases do not necessarily be implemented as separate physical entities. That is the name of each database is entitled only according to purposes types and formats of information stored in each database. That is the three databases may be integrated into a single database or one of the three databases may take a role of another database of the three databases. Also the term database in the specification does not necessarily indicate a rigid form of database such as a relational database and an object oriented database and may mean a functional component which can store information. Thus the databases may be implemented as simple storages such as file bases.

Meanwhile when the unified cloud storage virtual file system according to the present invention is initialized it is possible that the databases are not constructed yet. Therefore the additional component the information collecting part may collect information for the databases construct the above databases through a database management system DBMS and store the collected information in the constructed databases.

The information collecting part may register APIs for each cloud storage in the API database by referring to API description files describing APIs provided from each cloud storage service vendor or written by user. The registered APIs may include APIs for reading service name of each cloud storage service uploading files to each cloud storage downloading files from each cloud storage creating new folder in each cloud storage deleting files in each cloud storage and reading metadata. The information collecting part may collect information on APIs provided by each cloud storage service in a way other than the way of referring to the API description files.

The information collecting part may collect metadata information names of files or folders sizes of files or folders creation or modification dates of files or folders whole directory paths of files or folders after performing authentication procedures for all cloud storages registered in the API database . At this time the information collecting part may search an API of each cloud storage for requesting metadata of each cloud storage in the API database and use the searched APIs to request metadata of each cloud storage.

Here metadata provided by each cloud storage may have similar data formats. However they have different formats for each cloud storage. In this case the metadata having different formats may be integrated to have a unified metadata format and stored in the metadata database . Also in order to identify relations between folders and between files and folders unified whole directory paths of each file and each folder may be stored in the metadata database so that a unified virtual file system environment can be provided to the user.

After the information collecting part collects metadata information state information of each cloud storage such as total capacity and used capacity of each cloud storage may be identified and the state information for each cloud storage may be registered to the storage state database .

Second the cloud storage allocating part is a component configured to receive a user request from a local computer and select a cloud storage appropriate to the user request by referring to the storage state database and the metadata database . At this time the user request may be made based on standard interface according to Portable Operating System Interface POSIX and may be provided to the virtual file system according to the present invention specifically to the cloud storage allocating part .

The cloud storage allocating part may select the cloud storage appropriate to the user request in various manners. For example in the case that the user request is for reading or writing a specific file the cloud storage allocating part may identify directory path of the specific file in a unified directory space provided by the virtual file system by referring to the metadata database and select a cloud storage to which the identified directory path is mapped as the cloud storage appropriate to the user request. In addition the cloud storage allocating part may also select the cloud storage appropriate to the user request based on analysis results on usage pattern of the user and performances of each cloud storage. The above mentioned manner will be explained as another embodiment referring to .

Finally the API mapping part may receive the user request and information indicating the cloud storage appropriate to the user request from the cloud storage allocating part convert the user request into API corresponding to the designated cloud storage call the converted API receive a response including a result of the API call and transfer the response to the cloud storage allocating part .

At this time the API mapping part may perform mapping of the user request for example described in POSIX interface manner to corresponding API of the designated cloud storage convert the response of the designated cloud storage into a format which is understandable by the local computer for example described in POSIX and transfer the converted response to the local computer through the cloud storage allocating part .

For example interfaces specified in POSIX and APIs of cloud storage may have one to one relationship or various m to n relationships. That is a single POSIX interface may correspond to multiple APIs of cloud storage. That is multiple POSIX interfaces may correspond to a single API of cloud storage. The API mapping part may have the information on the mapping relationship in itself in the forms of mapping tables or mapping scripts. Alternatively the information on the mapping relationship may be stored in the API database .

Referring to another example embodiment of a unified cloud storage virtual file system may include an usage pattern monitoring part and a performance monitoring part as additional components to the example embodiment shown in .

Other components except the usage pattern monitoring part and the performance monitoring part in another example embodiment shown in are the same as those of the example embodiment depicted in and so redundant explanation will be omitted.

As described above the cloud storage allocating part may select a cloud storage appropriate to a user request in various manners. Thus the usage pattern monitoring part and the performance monitoring part are additional components to provide information which can be used for the cloud storage allocating part to select the cloud storage appropriate to a user request.

First the usage pattern monitoring part is a component for monitoring file system usage pattern of a user. For example the usage pattern monitoring part may record the number of reading or writing for each file type for example documents multimedia contents and general data and so on when the use write or read a file.

The usage pattern monitoring part may be configured to monitor the user request inputted from the local computer and the response to the user request outputted to the local computer directly or may be configured to analyze the user request and the response indirectly transferred from the cloud storage allocating part .

Second the performance monitoring part may operate independently and measure periodically or aperiodically for example according to user s demand uploading speed and downloading speed by unloading and downloading a specific size of file to and from each cloud storage. The performance of each cloud storage may have a characteristic of changing according to area of the user and time of access. Therefore the performance monitoring part may be configured to measure performance of each cloud storage periodically or aperiodically performance of each cloud storage and store the measured performance in the above storage state database.

Here the performance monitoring part may access the cloud storages and through the above described API mapping part .

An example of a procedure that the cloud storage allocating part selects a cloud storage appropriate to the user request by using information provided from the additional components such as the usage pattern monitoring part and the performance monitoring part may be configured as follows.

Since file access patterns may be different according to preferences of the users the cloud storage allocating part may use usage pattern information of the users analyzed in the usage pattern monitoring part so that a type of file which is more frequently uploaded than downloaded may be uploaded to a cloud storage having fast uploading speed and a type of file which is more frequently downloaded than uploaded may be uploaded to a cloud storage having fast downloading speed.

For example when a user copies or moves a specific file from the local system to the virtual file system the cloud storage allocating part may obtain information on access pattern of the specific file from the usage pattern monitoring part . The access pattern may be classified into three types such as a type having more uploading a type having more downloading and a type of having similar downloading and uploading.

For the type having more uploading the cloud storage allocating part may obtain information on a cloud storage having the fastest uploading speed from the performance monitoring part and identify a remained space of the cloud storage having the fastest uploading speed. If the remained space is larger than a size of the specific file the cloud storage allocating part may select the cloud storage having the fastest uploading speed as a cloud storage appropriate to the user request and process the user request on the cloud storage having through the API mapping part .

For the type having more downloading the cloud storage allocating part may obtain information on a cloud storage having the fastest downloading speed from the performance monitoring part and identify a remained space of the cloud storage having the fastest downloading speed. If the remained space is larger than a size of the specific file the cloud storage allocating part may select the cloud storage having the fastest downloading speed as a cloud storage appropriate to the user request and process the user request on the cloud storage having through the API mapping part .

For the type having similar downloading and uploading the cloud storage allocating part may select a cloud storage having the largest remained space as a cloud storage appropriate to the user request.

Meanwhile for all the three types if the remained space is smaller than a size of the specific file the cloud storage allocating part may obtain information on a cloud storage having the next performance that is the second fastest uploading downloading speed or the second largest remained space from the performance monitoring part and select a cloud storage appropriate to the user request.

Referring to an operation method of a unified cloud storage virtual file system according to the present invention may include a step S of initializing database a step S of monitoring usage pattern and performance a step S of selecting a cloud storage appropriate to a user request and a step S of mapping and calling API.

In a below explanation of the specification each step constituting an operation method of virtual file system of the present invention may be understood as an operation of corresponding component but each step constituting an operation method should be limited only by each function defining each step. That is an entity performing each step should not be limited by a name of the entity which is used in this specification.

First the step S of initializing database is a step of initializing at least one database storing information used in the virtual file system according to the present invention.

That is when the virtual file system is started the virtual file system may check whether each database already exists or not and start initializing each database if the corresponding database does not exist. The explanation of purpose and meaning of each database is omitted since they have been explained above.

In the step of collecting information API description file of each cloud storage service is read out. For each cloud storage service a service name and APIs for file uploading file downloading folder creation file or folder deleting and metadata reading may be registered to the API database based on the API description file of each cloud storage service. Also in the step of collecting information authentication procedures on all the cloud storages registered to the API database may be performed and then metadata information such as names sizes creation modification dates whole directory paths of files and folders may be collected. In collecting the metadata information an API for requesting metadata searched in the API database may be used to request the metadata for each cloud storage.

At this time although metadata of each cloud storage may have similar data formats they may have also different data formats for each cloud storage. In this case the virtual file system may unify formats of metadata of the cloud storages into a unified format and store metadata of the cloud storages in the metadata database. Also in order to identify relations between folders and between files and folders unified whole directory paths of each file and each folder may be stored in the metadata database so that a unified virtual file system environment can be provided to the user. After the metadata information is collected total capacity and used capacity of each cloud storage may be identified and the state information for each cloud storage may be registered to the storage state database .

Second in the step S of monitoring usage pattern and performance a file system access pattern of the users and performances of the cloud storages may be monitored and analyzed. The step S may be performed in periodical or aperiodical manner independently to other steps.

That is in the step S of monitoring usage pattern and performance uploading speed and downloading speed for each cloud storage may be monitored by unloading and downloading a specific size of file to and from each cloud storage. Also the number of reading or writing for each file type for example documents multimedia contents and general data and so on may be monitored when the use write or read a file.

The step S may be performed by the performance monitoring part and the usage pattern monitoring part of the virtual file system as explained above.

Second the step S of selecting a cloud storage appropriate to a user request is a step of receiving the user request to the virtual file system and selecting a cloud storage appropriate to the user request.

For example after the step S of initializing if the user inputs a request of searching folders and files in the unified virtual file system the virtual file system may search and show files and folders located in corresponding directory paths found out in the metadata database.

The user may transfer a user request such as copying or moving a specific file from the local system to the virtual file system to the virtual file system. In the step S the user request may be received and a cloud storage appropriate to the user request may be selected according to an access type of the specific file.

At this time the step S may be performed based on file access pattern information of the user identified in the step S of monitoring.

For example the access pattern on the specific file may be classified into three types such as a type having more uploading a type having more downloading and a type of having similar downloading and uploading.

For the type having more uploading in the step S a cloud storage having the fastest uploading speed may be identified and a remained space of the cloud storage having the fastest uploading speed may be identified in the storage state database. If the remained space is larger than a size of the specific file the cloud storage having the fastest uploading speed may be selected as a cloud storage appropriate to the user request.

For the type having more downloading in the step S a cloud storage having the fastest downloading speed may be identified and a remained space of the cloud storage having the fastest downloading speed may be identified in the storage state database. If the remained space is larger than a size of the specific file the cloud storage having the fastest downloading speed may be selected as a cloud storage appropriate to the user request.

For the type having similar downloading and uploading a cloud storage having the largest remained space may be selected as a cloud storage appropriate to the user request.

For all the three types if the remained space is smaller than a size of the specific file a cloud storage having the next performance that is the second fastest uploading downloading speed or the second largest remained space may be identified and selected as a cloud storage appropriate to the user request.

Finally in the step S of mapping and calling API the user request may be converted into an API corresponding to the designated selected cloud storage based on the user request received and information on the cloud storage selected in the step S and the user may be transferred to the selected cloud storage by calling the API. Then a response to the user request may be received from the selected cloud storage.

The procedures performed in the step of mapping and calling API are similar to the above explained procedures performed by the API mapping part and so redundant explanation may be omitted.

Then the databases may be updated by reflecting metadata and states of the selected cloud storage changed according to the user request at S and the steps may be repeatedly performed from the step S of monitoring usage pattern and performance.

The virtual file system mapping multiple cloud storage services supporting open APIs to POSIX interfaces which is proposed according to the present invention may provide a unified virtual file system environment integrating multiple cloud storage services to users as opposed to that the conventional mount and synchronization program operates only on a single cloud storage.

The proposed virtual file system may analyze access patterns of users for each file type monitor performances of cloud storages integrated and select an optimal cloud storage automatically based on a user request and the analyzed and monitored result.

While the example embodiments of the present invention and their advantages have been described in detail it should be understood that various changes substitutions and alterations may be made herein without departing from the scope of the invention.

