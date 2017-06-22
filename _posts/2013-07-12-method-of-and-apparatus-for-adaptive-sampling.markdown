---

title: Method of, and apparatus for, adaptive sampling
abstract: A method of sampling sensor data from a computing system is presented. The computing system includes a plurality of components and a sensor network for monitoring the computing system. The sensor network includes primary sensor nodes operable to obtain primary parameter data from a measurement of a primary parameter of the components, and secondary sensor nodes operable to obtain secondary parameter data from a measurement of secondary parameters of the components. The method includes: a) obtaining secondary parameter data from secondary sensor nodes relating to components; b) processing, in a computing device, the secondary parameter data; c) determining, based upon determined or pre-determined relationships between the secondary parameters and the primary parameter, a sample rate for the primary parameter data for the components; and d) obtaining primary parameter data from the primary sensor nodes relating to components at the determined sample rate.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09306828&OS=09306828&RS=09306828
owner: XYRATEX TECHNOLOGY LIMITED-A SEAGATE COMPANY
number: 09306828
owner_city: Havant
owner_country: GB
publication_date: 20130712
---
The present invention relates to a method of and apparatus for adaptive sampling on a storage system. More particularly the present invention relates to a method of and apparatus for predicting primary operational parameters of a storage system using secondary operational parameters.

A typical storage system generally comprises a server and a plurality of hard disk drives connected together over a network to one or more servers each of which provides a network addressable storage resource. Alternatively the storage system may comprise a local configuration where the storage resource is connected directly to a terminal or server or may form a local storage arrangement such as a hard disk drive in a laptop or personal computer.

RAID arrays are the primary storage architecture for large networked computer storage systems. There are a number of different RAID architectures Commonly used architectures comprise RAID 1 through to RAID 6. Each architecture offers disk fault tolerance and offers different trade offs in terms of features and performance. A RAID network is generally controlled by one or more RAID controllers which manage the physical storage of data on the drives forming part of the RAID array. RAID controllers provide data integrity through redundant data mechanisms high speed through streamlined algorithms and accessibility to stored data for clients and administrators. Should one of the disks in a RAID group fail or become corrupted the missing data usually in the form of blocks can be recreated from the data on the other disks.

Certain storage systems are particularly optimised for access performance. Such systems are known as high performance computing HPC systems. These systems are often complex and are used for complex tasks such as and analysing complex physical or algorithmic data.

In general HPC systems comprise a plurality of HPC clusters of one or more servers. These servers comprise one or more controllers and one or more arrays of storage devices such as hard drives . The performance of HPC systems is generally a function of the number of servers and or storage devices which are operable in parallel.

It is necessary to monitor properties of such systems in order to detect failures and errors in the system. In the context of HPC systems such failures may be hardware errors such as hard drive corruptions and failures or CPU errors due to for example overheating. Therefore it is common to request such data from the hardware this data then being stored in a monitored log. Hardware failure can then be logged and detected.

However HPC systems are complex and may comprise a large number of components e.g. CPUs controllers and hard drives. Each component that is required to be monitored requires an appropriate sensor or some sensing capability. This may take the form of inter alia a hardware sensor such as a temperature or fan speed sensor a sensing capability of the hardware e.g. SMART Self Monitoring Analysis and Reporting Technology enabled hard drive diagnostic properties or a software sensor such as a CPU usage monitor. Each sensor or sensor capable element is operable to provide at regular intervals e.g. at a particular sampling rate or on demand a measurement at a particular time on the hardware software quantity in question. This data may be stored in a log either locally or remotely across for example a network.

Each sensor or sensor capable element may be considered to be a sensor node. In a typical HPC system there may be a large number of sensor nodes. Therefore to report sensor data from all the sensor nodes requires the streaming and storage of a huge amount of data. This data is required to be stored over a long period of time. Storing archiving and maintaining this data can be costly and subsequent analysis of archived data can be computationally time consuming and expensive.

Furthermore obtaining sensory data can reduce the performance of HPC systems. For example performing SMART diagnostics on a hard drive can reduce the instantaneous read write speed of the drive in question. Since read write access speed and data streaming performance is paramount for HPC systems this additional load on the system is inconvenient and unwanted.

One approach to reduce the volume of data required is to reduce the sampling rate for the sensor nodes. However in order to perform useful data analysis a minimum sampling rate is required. This is often the case for monitoring algorithms which may use historical data to attempt to predict drive failure. Furthermore if the sampling rate is too low it may be possible to miss errors and problems altogether.

It is also known to provide a variable sampling rate for sensor nodes in different applications. This is known as adaptive sampling and examples of this technique can be found in U.S. Pat. No. 5 977 957 U.S. Pat. No. 8 017 411 U.S. Pat. No. 4 755 795 WO A 00 69042 and Adaptive Sampling for Sensor Networks ETH Swiss Federal Institute of Technology 2005 . These examples typically use frequency based algorithms.

However whilst adaptive sampling may reduce the overall sensor data load on a system it is still necessary to routinely sample data from the sensor nodes. This is because the selected frequency of sampling is entirely dependent upon the monitored parameter. This will still have a significant impact on the performance of an HPC system since sensor node monitoring and reports will still be necessary albeit at reduced and variable intervals. Much of the data gathered will still be of little interest and will unnecessarily consume computing and storage resources.

Therefore known approaches to sensor node sampling suffer from the technical problem that monitoring of sensor nodes is still required even in situations where such data is of little use. Therefore there exists a need to provide a method and system which is able to obtain sensor data more pertinently and reduce data collection in situations where the data collection is unnecessary.

According to a first aspect of the present invention there is provided a method of sampling sensor data from a computing system comprising a plurality of components and a sensor network for monitoring said computing system said sensor network comprising one or more primary sensor nodes operable to obtain primary parameter data from a measurement of a primary parameter of one or more of said components and one or more secondary sensor nodes operable to obtain secondary parameter data from a measurement of one or more secondary parameters of said one or more components the method comprising a obtaining secondary parameter data from one or more secondary sensor nodes relating to one or more components b processing in a computing device said secondary parameter data c determining based upon one or more determined or pre determined relationships between said one or more secondary parameters and said primary parameter a sample rate for said primary parameter data for said one or more components and d obtaining primary parameter data from said one or more primary sensor nodes relating to one or more components at said determined sample rate.

In one embodiment one or more of said components comprise hard drives and said primary parameter comprises hard drive status.

In one embodiment the computing system comprises a midplane including a CPU and memory one or more hard drives located within an enclosure and at least one network connection.

In one embodiment one or more of said secondary parameters is selected from the group of hard drive enclosure temperature hard drive enclosure fan speed CPU temperature CPU loading memory usage network usage localised vibration and midplane temperature.

In one embodiment the method further comprises prior to step a e obtaining data relating to said primary and secondary parameters and f analysing said primary and secondary parameters to determine correlations therebetween and g constructing a database containing pre determined relational parameters between said primary and secondary parameters.

According to a second aspect of the present invention there is provided a sensor network operable to obtain sensor data from a computing system comprising a plurality of components said sensor network comprising one or more primary sensor nodes operable to obtain primary parameter data from a measurement of a primary parameter of one or more of said components and one or more secondary sensor nodes operable to obtain secondary parameter data from a measurement of one or more secondary parameters of said one or more components the sensor network being operable to obtain secondary parameter data from one or more secondary sensor nodes relating to one or more components to processing said secondary parameter data to determine based upon one or more determined or pre determined relationships between said one or more secondary parameters and said primary parameter a sample rate for said primary parameter data for said one or more components and to obtain primary parameter data from said one or more primary sensor nodes relating to one or more components at said determined sample rate.

In one embodiment one or more of said components comprise hard drives and said primary parameter comprises hard drive status.

In one embodiment the computing system comprises a midplane including a CPU and memory one or more hard drives located within an enclosure and at least one network connection.

hard drive enclosure temperature hard drive enclosure fan speed CPU temperature CPU loading memory usage network usage localised vibration and midplane temperature.

In one embodiment the sensor network is further operable to obtain data relating to said primary and secondary parameters analyse said primary and secondary parameters to determine correlations therebetween and construct a database containing pre determined relational parameters between said primary and secondary parameters.

According to a third aspect of the invention there is provided at least one data storage resource and the sensor network of the second aspect.

According to a fourth aspect of the present invention there is provided a computer program product executable by a programmable processing apparatus comprising one or more software portions for performing the steps of the first and or second aspects.

According to a fifth aspect of the present invention there is provided a computer usable storage medium having a computer program product according to the fourth aspect stored thereon.

According to a sixth aspect of the present invention there is provided a method of sampling sensor data from a computing system comprising a plurality of components and a sensor network for monitoring said computing system said sensor network comprising one or more primary sensor nodes operable to obtain primary parameter data from a measurement of a primary parameter of one or more of said components and one or more secondary sensor nodes operable to obtain secondary parameter data from a measurement of one or more secondary parameters of said one or more components the method comprising a obtaining secondary parameter data from one or more secondary sensor nodes relating to one or more components b processing in a computing device said secondary parameter data c determining based upon one or more determined or pre determined relationships between said one or more secondary parameters and or said primary parameter a sample rate for the or each secondary parameter data for said one or more components d obtaining secondary parameter data at the or each sample rate and e utilising said secondary parameter data to infer indirectly properties of said primary parameter.

In one embodiment the method further comprises f determining based upon one or more determined or pre determined relationships between said one or more secondary parameters and or said primary parameter a primary sample rate for the primary parameter data for said one or more components and g obtaining primary parameter data from said one or more primary sensor nodes relating to one or more components at said determined primary sample rate.

In one embodiment one or more of said components comprise hard drives and said primary parameter comprises hard drive status.

In one embodiment the computing system comprises a midplane including a CPU and memory one or more hard drives located within an enclosure and at least one network connection.

In one embodiment one or more of said secondary parameters is selected from the group of hard drive enclosure temperature hard drive enclosure fan speed CPU temperature CPU loading memory usage network usage localised vibration and midplane temperature.

In one embodiment the method further comprises prior to step a h obtaining data relating to said primary and secondary parameters and i analysing said primary and secondary parameters to determine correlations therebetween and j constructing a database containing pre determined relational parameters between said primary and secondary parameters.

Embodiments of the present invention provide a method of indirectly obtaining information relevant to a primary parameter of a storage system or other computing apparatus using pre determined relationships between measurable secondary parameters of the system.

In general measurement of a primary parameter has a performance impact on the system. However the primary parameter is required to be measured in order to determine the status of the component of the system directly. In contrast the measurement of a secondary parameter has less or no impact on system performance. By establishing a database of hierarchical rules and relationships between secondary parameters and the or each primary parameter the secondary parameters can be measured without substantial performance cost until such a point where it is determined that the primary parameter should be measured. In other words if the status of the one or more secondary properties indicates that a potential error or other condition may exist the primary parameter can then be measured

The networked storage resource comprises a cluster file system. A cluster file system consists of client to N and server to N nodes connected by a network . Client applications running on client nodes make storage requests which may comprise file storage requests against the cluster file system. Some of these calls result in updates to the file system state recorded in volatile and persistent stores of node.

A commonly used distributed cluster file system is Lustre . Lustre is a parallel distributed file system generally used for large scale cluster computing. Lustre file systems are scalable and are able to support many thousands of clients and multiple servers.

The networked storage resource comprises a plurality of hosts . The hosts are representative of any computer systems or terminals that are operable to communicate over a network. Any number of hosts or servers may be provided N hosts and N servers are shown in where N is an integer value.

The hosts are connected to a first communication network which couples the hosts to a plurality of servers . The communication network may take any suitable form and may comprise any form of electronic network that uses a communication protocol for example a local network such as a LAN or Ethernet or any other suitable network such as a mobile network or the internet.

The servers are connected through device ports not shown to a second communication network which is also connected to a plurality of storage devices to N. The second communication network may comprise any suitable type of storage controller network which is able to connect the servers to the storage devices . The second communication network may take the form of for example a SCSI network an iSCSI network or fibre channel.

The servers may comprise any storage controller devices that process commands from the hosts and based on those commands control the storage devices . The storage devices may take any suitable form for example tape drives disk drives non volatile memory or solid state devices.

Although most RAID architectures use hard disk drives as the main storage devices it will be clear to the person skilled in the art that the embodiments described herein apply to any type of suitable storage device. More than one drive may form a storage device for example a RAID array of drives may form a single storage device . The skilled person will be readily aware that the above features of the present embodiment could be implemented in a variety of suitable configurations and arrangements. Additionally each storage device comprising a RAID array of devices appears to the hosts as a single logical storage unit LSU or drive. Any number of storage devices may be provided in N storage devices are shown where N is any integer value.

The operation of the servers may be set at the Application Programming Interface API level. Typically Original Equipment Manufactures OEMs provide RAID networks to end clients for network storage. OEMs generally customise a RAID network and tune the network performance through an API.

The servers and storage devices also provide data redundancy. The storage devices comprise RAID controllers which provide data integrity through a built in redundancy which includes data mirroring. The storage devices are arranged such that should one of the drives in a group forming a RAID array fail or become corrupted the missing data can be recreated from the data on the other drives.

The network storage resource comprises a sensor network . The sensor network comprises a sensor server . The sensor server comprises a storage device . However whilst the sensor server is illustrated for clarity as a separate device structure in this embodiment this need not be so. The sensor server may form part of one or more of the servers to N or a metadata server MDS or any additional or alternative structure operable to receive and process sensor data.

The sensor network further comprises a plurality of primary sensor nodes where i 1 to N and a plurality of secondary sensor nodes where i 1 to N .

In this embodiment the primary sensor nodes are operable to measure a primary parameter of one or more components of the network storage resource . A primary parameter is a parameter which provides direct information regarding a property of the component s in question.

For example in an embodiment the primary sensor nodes comprise hard drive SMART diagnostic elements as will be described with reference to When parsed by the sensor server the primary sensor nodes are operable to obtain SMART data from one or more of the hard drives forming part of the storage resource as will be described later.

The secondary sensor nodes are operable to measure one or more secondary parameters of one or more components of the network storage resource . A secondary parameter is one which provides information regarding a parameter related in some way to the primary parameter in question. The secondary parameter provides direct information regarding a property of the component s in question which is related to the primary parameter through a known or determined relationship.

For example a secondary sensor node may measure the speed of a cooling fan in a storage resource . If it is known that there is a relationship between the speed of the cooling fan and the likelihood of errors in the hard drives within the storage resource enclosure a measured change in speed of the cooling fan could be used as a secondary parameter condition to trigger a measurement of the primary parameter which may be the acquisition of SMART data from the hard drives within the storage resource .

The host comprises a general purpose computer PC which is operated by a client and which has access to the storage resource . A graphical user interface GUI is run on the host . The GUI is a software application which acts as a user interface for a client of the host .

The server comprises hardware components including a CPU having a local memory and RAID controller hardware . The RAID controller hardware comprises a memory .

The software components of the server comprise a software application layer and an operating system . The software application layer comprises software applications including the algorithms and logic necessary for the initialisation and run time operation of the server . The software application layer includes software functional blocks such as a system manager for fault management task scheduling and power management. The software application layer also receives commands from the host e.g. assigning new volumes read write commands and executes those commands. Commands that cannot be processed because of lack of space available for example are returned as error messages to the client of the host .

The operating system utilises an industry standard software platform such as for example Linux upon which the software applications forming part of the software application layer can run. The operating system comprises a file system which enables the RAID controller to store and transfer files and interprets the data stored on the primary and secondary drives into for example files and directories for use by the operating system .

The RAID controller hardware is the physical processor platform of the RAID controller that executes the software applications in the software application layer . The RAID controller hardware comprises a microprocessor memory and all other electronic devices necessary for RAID control of the storage devices . However the controller hardware need not be in the form of RAID hardware and other storage architectures may be utilised and controlled by the controller and fall within the scope of the present invention.

Whilst in the RAID controller hardware is shown as part of the server this need not be so. The skilled person would be readily aware of alternatives which fall within the scope of the present invention for example the RAID controller hardware may be remote from the server . In addition the RAID controller hardware may be located together with the storage devices or remotely therefrom.

The server as described above is specified as a general component of a networked storage resource and may comprise any suitable networked computer system capable of receiving and issuing storage requests such as I O requests and data transfers. However the server may also be utilised with a computing device having local storage such as a personal computer or laptop with an internal hard drive or flash memory.

The server is operable to receive storage requests which may comprise I O requests to a file system from hosts or clients and process said storage requests to the file system . The file system may comprise any suitable system and may be run on the server to provide access to the storage devices . Non exhaustive examples of suitable file systems may be NTFS HFS ext3 ext4 or idiskfs.

The hard drives N may be connected in any suitable RAID array for example RAID 5 or RAID 6. Furthermore whilst for clarity only 5 drives are shown in it is to be understood that other numbers of drives may be used as required i.e. N may be any suitable number.

The hard drives N forming part of the storage device are located within a storage enclosure . The storage enclosure may comprise a suitable rack or container to secure the hard drives N within. The storage enclosure comprises a cooling device which in this embodiment comprises a fan. However this need not be the case and other arrangements may be utilised as appropriate for example liquid cooling systems or a plurality of fans or airflow generators.

Furthermore the storage enclosure comprises a number of sensors. In this embodiment a temperature sensor and a vibration sensor are provided.

The sensor network is operable to cover the server and storage resource . The sensor network comprises a plurality of primary sensor nodes . In this embodiment as described above each hard drive N has a corresponding primary sensor node N. Each primary sensor node N comprises a SMART diagnostic element. This may comprise a hardware or software element or a combination of both.

The SMART diagnostic element provides a SMART status comprising two values threshold not exceeded and threshold exceeded . Often these are represented as drive OK or drive fail . A threshold exceeded value is intended to indicate that there is a relatively high probability that the drive is likely to fail. The predicted failure may be catastrophic or may relate to a more minor error such as a bad sector or a write fail.

In addition SMART diagnostics comprise further detail in the form of SMART attributes. This may vary from hard drive to hard drive but may comprise a log containing further information as to the drive status for example read write status spin up time start stop count seek time performance seek error rate command timeout drive life protection status or spin retry count.

The above list is intended to be exemplary and is non exhaustive. Further formats other than SMART may be used. The primary nodes are merely intended to be operable to report the status of the hard drive in question and the skilled person would readily be aware of variations and alternatives which could be used with the present invention.

The primary nodes are adapted to report the status of one or more hard drives when commanded to do so by the sensor server . However such an instruction and report consumes hardware resources for example CPU time memory capacity network resources and results in a reduction in read write access speed on the hard drives concerned. This may be particularly acute if a large number of drives are being commanded to report at the same time and sampled over a particular time period.

For example SMART data from an enclosure of 84 drives with an average of 40 signals will result to a total of 3360 signals. 5 second internal sampling rate will result to 40320 data points per minute to be transferred collected and analysed.

In order to reduce the loads on the server and networked storage resource the secondary nodes can be utilised to obtain measurement data of secondary parameters which in effect provide indirect measurement of the primary parameter. In other words certain detected conditions or combinations of conditions of the secondary nodes can indicate that a measurement of the primary nodes is required.

The secondary parameters which can be measured are numerous and are situation and hardware dependent. However in this embodiment the functioning of a number of non exhaustive different secondary nodes will be described.

With reference to secondary node is arranged to monitor the secondary parameter of network traffic to the server through the network . Secondary node is arranged to monitor the secondary parameter of operating system access behaviour. Secondary node is arranged to monitor the secondary parameter of midplane temperature within the server .

Secondary nodes and are arranged to monitor the secondary parameters of CPU usage and CPU temperature. Secondary node is arranged to monitor the secondary parameter of memory usage. Finally secondary node is arranged to monitor the network connection and network traffic between the storage resource and the server .

Turning now to the storage resource secondary nodes and are arranged to monitor the fan speed and enclosure temperature respectively. Secondary node is arranged to monitor vibration in the enclosure .

The above secondary parameters can be used to provide an indication that the primary parameter should be sampled. However before this can be implemented it is necessary to obtain experimental and empirical data relating to the relationships between one or more secondary parameter s and the primary parameter in question.

The following non exhaustive examples show how the secondary parameters can be utilised to infer properties of the primary parameter without measuring the primary parameter. The following examples are based on a range of interrelationships and techniques. For example a direct mathematical relationship between two parameters could be established such as the effect of hard drive temperature on the lifetime of a hard drive. Other relationships could be based upon statistical inference using techniques such as Bayesian probability.

Bayesian probability involves the use of hierarchical models and marginalisation over the values of secondary parameters to infer values of the primary parameter s . In many cases the determination of such computational relationships is intractable. However good approximations can be obtained using for example Markov chain Monte Carlo methods or by experimental or empirical verification.

If by measuring the above secondary parameters deviation from the expected model occurs then the primary parameter should be obtained or obtained more frequently since there is a greater likelihood of there being a hard drive problem based on the detected secondary parameters and the relationship between the primary parameter i.e. hard drive status and the secondary parameters.

The cooling fan causes vibration in the enclosure . Vibration of the enclosure and correspondingly the enclosed hard drives N has a correlation with the emergence of hard drive errors.

Operational modes of the fan e.g. fan speed ranges can result in critical operating modes in the system e.g. resonance conditions which cause excessive vibration. Concomitantly lower fan speeds can result in excessive heating which can also lead to hard drive failure. These critical modes of operation may affect the enclosure and the performance of the hard drives CPU and memory .

In addition to the example outlined above possible hard drive failure e.g. head failures can be identified by deviation from expected characteristics of these interrelated secondary parameters. In this case the primary parameter should be obtained or obtained more frequently since there is a greater likelihood of there being a hard drive problem based on the detected secondary parameters and the relationship between the primary parameter i.e. hard drive status and the secondary parameters.

Further the arrangements above enable optimisation of the components of the network storage resource where knowledge of the interconnections between parameters is obtained and utilised.

In a situation where the I O patterns CPU usage and fan operational modes are known the power trends of the server and enclosure may follow a specific pattern. This can be determined by forming a power model based on a thermal model application loads and network loads on the server . Deviations from the power model potentially demonstrate a hard drive issue.

Therefore by measuring the above secondary parameters deviation from the expected model can be detected. In response the primary parameter can be obtained or obtained more frequently since there is a greater likelihood of there being a hard drive problem based on the detected secondary parameters and the relationship between the primary parameter i.e. hard drive status and the secondary parameters.

The following further examples illustrate additional parameters and relationships that could be used.

The utilisation factor of the hard drives CPU and network via appropriate secondary sensor nodes could be used to determine the sampling rate for the primary parameter drive status .

For example it is known that the utilisation factor has a correlation with drive failure. Therefore in response the primary parameter can be obtained or obtained more frequently since there is a greater likelihood of there being a hard drive problem based on the detected secondary parameters and the relationship between the primary parameter i.e. hard drive status and the secondary parameters.

There is a network bandwidth limit which enforces how much data can be used. This enforces a top limit on amount of data that can be requested. If this data limit is reached or varies from a predetermined model it may have an adverse effect on the performance of the drives. This may be detected through secondary parameters.

Specific drive types have an expected life time. By having this information and cross correlating with rate of error on the hard drives critical modes can be detected. Therefore in response the primary parameter can be obtained or obtained more frequently on those particular hard drives since there is a greater likelihood of there being a hard drive problem based on the detected secondary parameters and the relationship between the primary parameter i.e. hard drive status and the secondary parameters.

If the server and enclosure are to be used in an application such as on board ship other sensory information from the platform can be used to detect critical operational modes. The sensory information can include but are not limited to temperature humidity altitude shock vibration airborne particles which can affect the performance and life time of the components. Once a model is established for these parameters they can be used as secondary parameters to detect drive status.

In an application with high audible noise e.g. factory performance of the hard drives can be affected. The vibration sensor can be used as a secondary sensor node or a microphone could be used as an alternative or additional secondary node .

Information about the model of the server hard drives and enclosure could be used in conjunction with network bandwidth to define a particular sampling rate for the primary parameter.

Customer usage of a network storage resource could be used to determine the sampling rate of the primary parameter. Thus the monitoring of the primary parameter could be increased when the usage of the networked storage resource is low reducing the impact on system performance. Alternatively it may be determined that the higher the customer usage the greater the likelihood of errors occurring and so checking of the primary parameter could be scheduled more frequently.

This variability can be contrasted with known utilities which conventionally pull data at the same rate irrespective of usage. This may result in system halt if many components are monitored at the same time.

Component versions model and lifetime expectancy information could be used as secondary parameters to determine the sampling rate or range of sampling rates available for sampling the primary parameter.

In general the I O rate of the hard drives will be approximately constant for a given load on the storage resource . Therefore an abrupt step change in the average I O rate of the hard drives e.g. read write speed and pattern potentially identifies a change in performance. For example this may indicate a slower hard drive in the system or an intermittent failure. The primary parameter could then be sampled more frequently in response to this indication.

The above examples illustrate how the relationships between different secondary parameters could be used to infer information regarding the primary parameter and thus be used to control the sampling rate of the primary parameter. However the above examples are non exhaustive and other relationships between the disclosed secondary parameters and other secondary parameters may be used with the present invention to control the sampling rate of the primary parameter.

In addition whilst the primary parameter has been described and illustrated with respect to drive status in the disclosed embodiments utilising the SMART protocol alternative or additional primary parameters could be used. In general it is desirable for the primary parameter to be one that measurement thereof is required to be minimised to improve performance of the system. However this need not be so.

At step the database of relationships between primary and secondary parameters is initialised. This is done by identifying the primary and secondary nodes from which data is to be obtained. The method proceeds to step .

At step a computer program is arranged to monitor the operation of a given network storage resource or server and to obtain data relating to multiple parameters as discussed above in the context of the embodiments of . The data collection program interacts with the relevant sensor nodes and system components to capture the sensory and status data to enable determination of dynamic relationships between the primary and secondary parameters.

At step the computer program uses appropriate algorithms computation or inputted empirical relationships to determine relationships between parameters for a given system. The analytics package is arranged to interpret the complex correlations in the system. After the models are built through the analytics package primary parameters can be adjusted in use if deviations on other correlated secondary signals are observed.

The information derived in step can then be stored in a look up table or similar arrangement and used to control the sampling rate of the primary parameter in use.

The method of discussed above may operate in conjunction with the method of or may be separate. For example the training method of may establish a standalone database of relationships which are implemented in hardware or software and utilised unamended on a given network storage resource. In this case the prepared database will be general to similar storage systems and not individual to a specific storage system.

Alternatively the method of may be run for the first time when implemented on a given piece of hardware such as a specific network storage resource. Thus the algorithms and optimization will prepare a database of relationships specific to that individual system.

In a further alternative a hybrid of the above cases could be implemented whereby a basic core of relationships could be modified to relate to specific individual requirements of a particular system.

Once the database of relationships has been established this can be used to control the sampling rate of the primary parameter as discussed below in relation to .

At step the database of relationships between primary and secondary parameters is initialized and the primary and secondary nodes from which data is to be obtained are initiated with initial sampling rates. The sampling rates used may vary and may be zero if the node is not required at runtime .

The arrangement as set up above is run and data is collected on the primary and secondary nodes as set up above. In general the sample rate for the primary nodes is set as low as possible possibly at zero and controlled in subsequent steps in response to data collected from the secondary nodes .

The secondary parameter data is collected from the secondary sensor nodes as initialized in the steps above. These nodes may include any or additional secondary sensor nodes as set out in the examples of . The sampling rate set for these secondary nodes is set during initialisation but may be varied. In general secondary node data will be less resource intensive than primary node data and so the sampling rate can be correspondingly higher. Data collection on a hardware level is carried out through a script. The required sampling rate is sent through a command line and as an argument.

As more secondary parameter data is obtained the system is also operable to determine the optimal sample rate for the secondary parameters based on the criticality of each parameter for monitoring the operational state of the system or the primary parameter. In other words the sample rates for the secondary parameter data are obtained based upon the importance of the relationships between those specific secondary parameters and the primary parameter.

The data collected in step is then analysed based on the pre determined algorithms and relationships as set out above. The method then proceeds to step .

At step it is determined whether the analysis performed in step on the data obtained in step is in accordance with nominal hard drive operation or whether the obtained relationships indicate that there may be a hard drive issue.

If it is determined that there is no or little likelihood of a hard drive problem the sampling rate of the primary parameter may be reduced or the sampling stopped altogether. Alternatively if it is determined that a problem or a potential anomaly may have arisen the primary node sampling rate may need to be increased. In either of these cases the secondary parameters have provided indication that the primary sampling rate is required to be adjusted. The method then proceeds to step .

Alternatively if it is determined that the sampling rate of the primary parameter is at the level required based on the indications from the obtained secondary parameters the method proceeds back to step and the steps are repeated.

At step it is determined that based upon the correlated secondary parameter data obtained in the steps above that the primary sampling rate of the primary parameter which is in one described embodiment the hard drive status should be adjusted. The sampling rate can be increased or decreased in dependence upon the nature of the secondary data and the relationships as set out above. The required sampling rate is sent through a command line and as an argument.

Once the sampling rate has been adjusted the method proceeds to step if the primary sampling rate is greater than zero. If the primary sampling rate is zero i.e. primary node sampling is disabled the method proceeds directly back to step .

Primary parameter data is collected if enabled. This data can be used to perform analytics on the hard drives to determine if there is a drive error or an imminent failure. This data can be stored in a log on for example the storage resource of the sensor server . Data collection on a hardware level is carried out through a script.

Variations of the above embodiments will be apparent to the skilled person. The precise configuration of hardware and software components may differ and still fall within the scope of the present invention.

Whilst the above embodiments have been described with reference to networked systems resources and servers other implementations could be used. The present invention is applicable to any arrangement where large amount of data is to be stored or analysed. Some examples of other applications may be manufacturing technology factory automation aerospace or indexing in data storage.

Further whilst the above embodiment has been illustrated with regard to a single primary parameter of drive status this need not be so. Any suitable primary parameter could be implemented as required. In addition multiple primary parameters may be controlled by one or more secondary parameters.

Additionally the secondary sampling rate could be varied in dependence upon the criticality of various secondary parameters to the current operational state of the system or to the primary parameter.

Further the present invention has been described with reference to controllers in hardware. However the controllers and or the invention may be implemented in software.

Additionally whilst the present embodiment relates to arrangements operating predominantly in off host firmware or software an on host arrangement could be used.

The controller or method of the present embodiments may be used to manage a plurality of separate networked storage resources if required.

In addition whilst a RAID array has been described in embodiments as a storage architecture for use with the present invention this need not necessarily be the case. Any suitable storage or hard disk protocol may be used with the present invention.

Embodiments of the present invention have been described with particular reference to the examples illustrated. While specific examples are shown in the drawings and are herein described in detail it should be understood however that the drawings and detailed description are not intended to limit the invention to the particular form disclosed. It will be appreciated that variations and modifications may be made to the examples described within the scope of the present invention.

