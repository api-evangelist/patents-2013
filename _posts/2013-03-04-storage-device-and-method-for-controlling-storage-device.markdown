---

title: Storage device and method for controlling storage device
abstract: A storage device includes a memory and a control device. The control device allocates a first storage region out of a plurality of storage regions to a first logical address specified by an external device. The control device stores, in the memory, first information associating the first logical address with a first physical address indicating the first storage region. The control device deletes, upon accepting a request for release of a second storage region indicated by a second physical address associated with a second logical address specified by the external device, second information associating the second logical address with the second physical address from the memory. The control device releases, when copy process of copying first data stored in the second storage region is unexecuted, the second storage region after finishing the copy process.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09141304&OS=09141304&RS=09141304
owner: FUJITSU LIMITED
number: 09141304
owner_city: Kawasaki
owner_country: JP
publication_date: 20130304
---
This application is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2012 118956 filed on May 24 2012 the entire contents of which are incorporated herein by reference.

The embodiments discussed herein are related to a storage device and a method for controlling a storage device.

In the past in a case of receiving a request for allocation of for example 10 TB of storage area from a server a storage device allocates a physical disk capacity of 10 TB. In contrast there is a case that the server actually uses only 20 through 30 of the allocated amount out of the physical disk capacity allocated as requested. In such a manner there is a case that a physical disk capacity allocated to a server is not utilized efficiently.

Given such a situation as an arrangement for efficiently using a physical disk capacity of a storage device there is a technique called thin provisioning. In thin provisioning in a case of receiving a request for allocation of 10 TB from a server for example a storage device allocates a virtual volume of 10 TB to the server as requested while actually allocating a physical disk capacity of only 2 TB.

Then in a case that the server uses a physical disk capacity exceeding a predetermined threshold the storage device allocates a fresh additional physical disk capacity to the server. In such a manner thin provisioning allocates a physical disk capacity at the time of a host access request as the occasion arises. This enables the storage device to efficiently utilize the physical disk capacity. The virtual volume used at this time is called as a thin provisioning volume TPV and a smallest unit of the physical disk capacity allocated to the TPV is called as a thin provisioning pool slice TPPS .

In a case that data is deleted by the server the deleted data is handled as unused in the operating system OS of the server. In contrast since the TPPS is still allocated to the deleted data in the storage device the storage device turns out to consume the physical disk capacity uselessly.

As an arrangement to improve this there is an UNMAP command. An UNMAP command is a command to request the TPV in the storage device for release of the TPPS by specifying a logical address of the unused TPPS. The server issues this UNMAP command to the storage device in coordination with the deletion of data thereby efficiently operating the TPPS allocated by thin provisioning. The UNMAP command is one of vStorage APIs application programming interfaces for array integration VAAI out of storage APIs provided by VMware.

The storage device sometimes has a copy function of a snapshot type that logically copies TPPS data. The UNMAP command is allowed to be used together with the copy function executed by the storage device. For example in a case that an UNMAP command is issued to uncopied TPPS data the storage device copies the TPPS data and releases the TPPS after finishing the copy. Then after releasing the TPPS the storage device responds to the server for the UNMAP command.

The UNMAP command has a capacity subjected to be processed in a single request from a host from several GB to several tens of GB or even more and in comparison with regular write I O input output the capacity subjected to be processed is large. Therefore in a case that the storage device receives an UNMAP command and copies all the range requested by the UNMAP command the time until the UNMAP command is executed increases. As a result since the server is not able to receive a response to the UNMAP command until finishing TPPS release process by the storage device there is a higher possibility that the UNMAP command is timed out.

Given such a situation the storage device records that release process is in a state of being reserved for the TPPS requested for release and immediately returns a response to the UNMAP command to the server. Then the storage device executes the release process asynchronously at the time of completion of saving the TPPS data to a copy destination to release the TPPS. In such a manner the storage device keeps an UNMAP command issued to a region subjected to copy from being timed out.

Japanese Laid open Patent Publication No. 2009 251970 and Japanese Laid open Patent Publication No. 2011 13821 disclose related techniques.

However the techniques in the past described above have a problem of delaying data writing that specifies a logical address specified in the request for release.

In a case that a request for writing data is issued to the TPPS of release process in a reserved state the storage device puts the request for writing data on standby until the TPPS data is copied and the TPPS is released after finishing the copy. Therefore the server is not able to receive a response to the request for writing data until finishing the TPPS release process by the storage device and there is a higher possibility that the request for writing data is timed out.

In addition the storage device sometimes executes copy of a snapshot type to identical TPPS data at different time. Then in a case that after an UNMAP command is issued to the TPPS of a copy source a request for writing data is issued to the TPPS of release process in a reserved state the request for writing data is put on standby until finishing the TPPS release process by the storage device. As a result the possibility that the request for writing data is timed out becomes even higher.

Still in addition the storage device sometimes executes an UNMAP command and copy of a snapshot type alternately. In such a case a response performance of the data writing process to the TPPS of release process in a reserved state decreases chronically.

According to an aspect of the present invention provided is a storage device including a memory and a control device. The control device allocates a first storage region out of a plurality of storage regions to a first logical address specified by an external device. The control device stores in the memory first information associating the first logical address with a first physical address indicating the first storage region. The control device deletes upon accepting a request for release of a second storage region indicated by a second physical address associated with a second logical address specified by the external device second information associating the second logical address with the second physical address from the memory. The control device releases when copy process of copying first data stored in the second storage region is unexecuted the second storage region after finishing the copy process.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

Detailed descriptions are given below to embodiments of a storage device and a method for controlling a storage device disclosed herein with reference to the drawings. Embodiments are not limited to these embodiments. It is possible to appropriately combine each embodiment as long as the process contents do not contradict with each other.

In a first embodiment with reference to descriptions are given to a configuration of an information processing system a configuration of a storage device a configuration of a control module CM process behaviors by the storage device a process procedure by the storage device effects and the like.

The host computer is for example a server and executes reading and writing of data of a logical volume to the storage device .

The storage device allocates a physical disk capacity by thin provisioning as the occasion arises in a case that an access is requested by the host computer . For example in a case of receiving a request for allocation of 10 TB from the host computer the storage device allocates a virtual volume of 10 TB to the host computer as requested while actually allocating a physical disk capacity of only 2 TB. Then in a case that the host computer uses a physical disk capacity exceeding a predetermined threshold the storage device allocates a fresh additional physical disk capacity to the host computer . The virtual volume used at this time is called as a thin provisioning volume TPV and a smallest unit of the physical disk capacity allocated to the TPV is called as a thin provisioning pool slice TPPS . The disk capacity that the host computer requests the storage device to allocate and the capacity of the virtual volume and the physical disk capacity that is allocated to the host computer by the storage device are not limited as the above descriptions.

With reference to consecutively a configuration of the storage device according to the first embodiment is described. The storage device includes a channel adapter CA a CA a CA a CA a disk device a disk device a disk device a disk device a control module CM and a CM . The CAs and are interfaces to the host computer . The host computer and the CAs and are communicably connected with each other via an FC an iSCSI or the like.

The disk devices and constitute redundant arrays of inexpensive disks RAID and store writing data received from the host computer . The disk devices and constitute TPVs which are virtual volumes.

The CM controls input output of data between the host computer and the disk devices and . The CM controls input output of data between the host computer and the disk devices and . The number of CMs included in the storage device is not limited to the illustrated number.

With reference to consecutively a configuration of the CM according to the first embodiment is described. As illustrated in the CM includes a device adapter DA a DA a random access memory RAM a flash memory and a central processing unit CPU .

The RAM stores a mapping information table and a copy management table . The RAM also stores pool management information not illustrated for managing a pool of unused TPPSs. The RAM is substitutable with a dual inline memory module DIMM a dynamic random access memory DRAM or the like.

The mapping information table stores mapping information that associates a logical address of a TPV achieved by the disk device with a physical address indicating a TPPS allocated in the TPV. The data structure of data stored in the mapping information table is described later with reference to .

The copy management table stores information for managing whether or not data of a logical volume stored in the TPPS has been copied. The data structure of data stored in the copy management table is described later with reference to .

The flash memory stores firmware . The functional configuration of functions described in the firmware is described later with reference to . The CPU loads and executes the firmware stored in the flash memory thereby performing various types of arithmetic process.

As illustrated in the CM includes a DA a DA a RAM a flash memory and a CPU . The DA is an interface to the disk device and the DA is an interface to the disk device .

The RAM stores a mapping information table and a copy management table . The mapping information table stores information similar to the mapping information table . The copy management table stores information similar to the copy management table . The RAM also stores pool management information not illustrated for managing a pool of unused TPPSs. The RAM is substitutable with a DIMM a DRAM or the like.

The flash memory stores firmware . The functional configuration of functions described in the firmware is described later with reference to . The CPU loads and executes the firmware stored in the flash memory thereby performing various types of arithmetic process.

The storage device configured in such a manner executes the following process in a case that the CPU has loaded the firmware or in a case that the CPU has loaded the firmware . That is the storage device maintains in the RAM mapping information that associates a logical address of a TPV achieved by the disk device with a physical address indicating a TPPS allocated in the TPV. The storage device executes the following process to the TPPS storing data of a logical volume subjected to copy in a case of being requested for release with a specified logical address that is associated with a physical address indicating the TPPS. That is the storage device deletes the TPPS from the mapping information and saves the TPPS from an access related to the TPV by the host computer . Then the storage device updates the field of a physical address of the mapping information corresponding to the logical address to information indicating that a physical address is unallocated allowing allocation of a physical address indicating a fresh TPPS to the logical address. Subsequently the storage device executes copy of data of the logical volume stored in the saved TPPS. After finishing the copy the storage device releases the TPPS storing the data of the logical volume subjected to the copy. That is to say the physical address indicating this TPPS is registered in the pool management information for managing the pool of unused regions thereby managing the physical address as an unused region after that. The mapping information table the copy management table and the pool management information that are stored in the storage device are collectively referred to as management information .

Next with reference to one example of data structure of data stored in the mapping information tables and is described. Since the data structure of data stored in the mapping information tables and are similar the data structure of data stored in the mapping information table is described here. In the following description data stored in the mapping information tables and is appropriately mentioned as mapping information .

A logical LBA stored in the mapping information table represents a logical address in a TPV which is a virtual region achieved by the disk devices and . For example a logical LBA has a value such as 1000 and 2000 . The host computer accesses the data of the logical volume stored in the TPPS by specifying the logical LBA. The host computer also requests for release of the TPPS by specifying the logical LBA.

A physical LBA stored in the mapping information table represents a physical address in a TPV which is a virtual region achieved by the disk devices. For example a physical LBA has a value such as 35000 and 47000 .

The physical LBA is uniquely associated with an identifier of a TPPS. In other words a physical LBA indicates a TPPS allocated in the TPV. For example 35000 as a physical LBA is associated with a TPPS TPPS10 and 47000 as a physical LBA is associated with a TPPS TPPS22 . In a case of accepting input output process from the host computer with a specified logical LBA the storage device executes the input output process to the TPPS indicated by a physical LBA associated with the specified logical LBA.

In the example illustrated in the logical LBA 1000 in the TPV corresponds to the physical LBA 35000 and indicates the physical region identified by TPPS10 . Similarly the logical LBA 2000 in the TPV corresponds to the physical LBA 47000 and indicates the physical region identified by TPPS22 .

The physical LBA stored in the mapping information table is updated by a TPPS mapping management section and a TPPS allocation management section described later.

Next with reference to one example of data structure of data stored in the copy management tables and is described. Since the data structure of data stored in the copy management tables and are similar the data structure of data stored in the copy management table is described here.

Here the copy source TPPS stored in the copy management table represents an identifier of a TPPS of a copy source. For example a copy source TPPS has a value such as TPPS11 and TPPS20 .

The copy destination OLU stored in the copy management table represents an identifier of an OLU of a copy destination. For example a copy destination OLU has a value such as 1 and 2 . The OLU is not a TPV managed by thin provisioning but a logical unit generally used in open systems.

The copy destination logical LBA stored in the copy management table represents a logical address in the OLU of the copy destination. For example a copy destination logical LBA has a value such as 5000 and 6000 .

The state stored in the copy management table represents a state of a copy process. For example a state has a value such as unexecuted representing that the copy process is unexecuted in execution representing that the copy process is in execution or finished representing that the copy process is finished.

In the example illustrated in the copy management table represents that process of copying the data of the logical volume stored in TPPS11 to the logical LBA 5000 of the OLU 1 is finished . Similarly the copy management table represents that process of copying the data of the logical volume stored in TPPS11 to the logical LBA 6000 of the OLU 2 is finished .

The state stored in the copy management table is updated by a copy process control section described later.

Next with reference to functional configurations of the functions described in the firmware and executed by the storage device according to the first embodiment are described. Since the functional configurations of the functions described in the firmware and executed by the storage device according to the first embodiment are similar the firmware and are referred to as firmware here for the description.

As illustrated in the functions described in the firmware include an UNMAP command processing section a write I O processing section a conflict detection section the copy process control section the TPPS mapping management section and the TPPS allocation management section .

The UNMAP command processing section receives an UNMAP command from the host computer . Then the UNMAP command processing section causes the conflict detection section described later to determine whether or not to copy data of the logical volume stored in the TPPS requested for release by the UNMAP command.

The UNMAP command processing section suspends release of the TPPS requested for release in a case of being determined by the conflict detection section to execute copy process of the data of the logical volume stored in the TPPS requested for release. Then the UNMAP command processing section causes the TPPS mapping management section to update the mapping information table . The UNMAP command processing section releases the TPPS storing the data of the logical volume subjected to copy after finishing the copy of the data of the logical volume stored in the TPPS requested for release.

The UNMAP command processing section releases the TPPS requested for release in a case of being determined by the conflict detection section not to execute copy process of the data of the logical volume stored in the TPPS requested for release. Then the UNMAP command processing section causes the TPPS mapping management section to update the mapping information table

The UNMAP command processing section sends a response corresponding to the UNMAP command to the host computer in a case of being informed that the mapping information table is updated by the TPPS mapping management section .

In a case of receiving a write I O from the host computer with a specified logical address the write I O processing section writes the data of the logical volume in the TPPS indicated by the physical address allocated to the logical address.

For example in a case of receiving a write I O from the host computer with a specified logical address the write I O processing section requests the TPPS allocation management section for allocation of a TPPS to the specified logical address. Then the write I O processing section writes the write data received from the host computer in the TPPS allocated by the TPPS allocation management section . The write I O processing section responds to the host computer for completion of the write I O after writing the write data received from the host computer .

The conflict detection section determines whether or not to execute copy process of the TPPS requested for release. For example the conflict detection section reads out the state corresponding to the TPPS requested for release in the copy management table and determines whether or not the state is finished . In a case that the state in the copy management table is finished the conflict detection section determines not to execute copy process.

In a case that the state in the copy management table is not finished that is in a case that the state in the copy management table is in execution or unexecuted the conflict detection section determines to execute copy process.

The copy process control section launches copy process of the data of the logical volume stored in the TPPS in the background. For example in a case of executing copy process of the TPPS requested for release the copy process control section executes copy of the data of the logical volume stored in the saved TPPS.

The copy process control section sets in execution for the state in the copy management table in a case of executing the copy process and sets finished for the state in the copy management table in a case of finishing the copy process.

The TPPS mapping management section updates the mapping information table stored in the RAM such that the TPPS requested for release by the host computer becomes in a release state. For example in a case of not executing copy of the TPPS requested for release the TPPS mapping management section updates the mapping information after the TPPS requested for release is released by the UNMAP command processing section .

The TPPS mapping management section also executes the following process to the TPPS storing the data of the logical volume subjected to copy in a case of being requested for release with a specified logical address that is associated with a physical address indicating the TPPS. That is the TPPS mapping management section saves the TPPS requested for release and updates the mapping information to be in a state of allowing allocation of a physical address indicating a fresh TPPS to the logical address specified in the request for release.

For example the TPPS mapping management section deletes a value stored in the physical LBA that is associated with the logical LBA indicating the TPPS requested for release. To cite one example in a case of being requested for release with a specified logical LBA 2000 the TPPS mapping management section deletes 36000 stored in the physical LBA corresponding to the logical LBA 2000 .

In a case of accepting a request for writing data of a logical volume with the logical address specified in the request for release the TPPS allocation management section allocates a physical address indicating a fresh TPPS to the logical address. For example the TPPS allocation management section acquires a physical LBA indicating a new TPPS in association with the logical LBA requested for a write I O. To cite one example in a case of accepting a request for writing data of a logical volume with a specified logical LBA 2000 the TPPS allocation management section stores 47000 in the physical LBA corresponding to the logical LBA 2000 .

Next with reference to one example of process behaviors by the storage device according to the first embodiment is described. is a diagram illustrating one example of process behaviors by the storage device according to the first embodiment. illustrates a case that release of a TPPS indicated by the logical LBA 2000 is requested and copy of the data of the logical volume stored in the TPPS is unexecuted.

As illustrated in the storage device receives an UNMAP command from the host computer that requests for release of the TPPS indicated by the logical LBA 2000 S . Since copy of the data of the logical volume stored in the TPPS requested for release is unexecuted the storage device deletes the TPPS from the mapping information and to update the mapping information table S . Accordingly it is possible to save the TPPS from the access related to the TPV by the host computer .

Then the storage device sends a response to the UNMAP command to the host computer S . Subsequently the storage device receives a write request to the TPPS indicated by the logical LBA 2000 from the host computer S .

Since the logical LBA 2000 is in a state where no TPPS is allocated in the mapping information table the storage device having the write request received therein acquires a new TPPS for the logical LBA 2000 S . Then the storage device receives write data from the host computer S and sends a response to the write request to the host computer S .

The storage device executes copy of the data of the logical volume stored in the saved TPPS S . Then the storage device releases the TPPS after finishing the copy S .

Next with reference to a process procedure of process by the storage device according to the first embodiment is described. A process procedure of the mapping information update process upon receiving an UNMAP command in the storage device is described with reference to FIG. and a process procedure of the TPPS acquisition process upon receiving a write I O in the storage device is described with reference to .

As illustrated in the UNMAP command processing section receives an UNMAP command from the host computer S . Then the conflict detection section determines whether or not to execute copy process of the TPPS requested for release S .

Here in a case of being determined to execute the copy process of the TPPS requested for release by the conflict detection section Yes in S the UNMAP command processing section suspends release of the TPPS requested for release S . Then the copy process control section launches the copy process in the background S .

In contrast in a case of being determined not to execute the copy process of the TPPS requested for release by the conflict detection section No in S the UNMAP command processing section releases the TPPS requested for release S .

After finishing S or S the TPPS mapping management section updates the mapping information stored in the mapping information table such that the TPPS requested for release from the host computer becomes in a release state S . For example the TPPS mapping management section deletes a value stored in the physical LBA that is associated with the logical LBA indicating the TPPS requested for release.

After finishing the process of S the UNMAP command processing section sends a response to the UNMAP command to the host computer S and finishes the mapping information update process.

Then the write I O processing section requests the TPPS allocation management section to acquire a TPPS for the logical LBA requested for a write I O. This causes the TPPS allocation management section to acquire a new TPPS for the logical LBA requested by the write I O processing section S .

Subsequently the write I O processing section receives write data from the host computer after a new TPPS is acquired by the TPPS allocation management section S and responds to the host computer S .

In a case that an UNMAP command is issued the storage device according to the first embodiment does not put the TPPS requested for release in an UNMAP reservation state but updates the mapping information of the logical LBA and the physical LBA to a state of allowing allocation of another new TPPS. After that the storage device controls an access from the host computer to access a newly allocated TPPS and copy process within the storage device to access the originally allocated TPPS requested for release. Then the storage device releases the TPPS requested for release at the time when the copy is completed and the information in the TPPS requested for release becomes unused. The storage device pools the TPPS in the pool of a physical disk capacity as an unused region. This enables the UNMAP command process and the copy process to be independent from each other and the storage device to avoid a possibility that a write I O is timed out.

In the first embodiment a case that the storage device is requested for release of the TPPS storing the data of the logical volume subjected to copy is described. In the storage device there is a case that an UNMAP command and copy of a snapshot type are executed alternately and repeatedly to an identical logical LBA. In this case the storage device is requested for release of the TPPS storing the data of the logical volume subjected to copy and also executes new copy to data of a logical volume stored in a TPPS that is newly associated with the logical address specified in the request for release.

With that a second embodiment represents an example that a storage device stores copy information that associates a saving generation number of copy generation an identifier of a TPPS storing copy source data and a logical address indicating a copy destination with each other.

With reference to consecutively the configuration of the CM according to the second embodiment is described. As illustrated in the CM includes a DA a DA a RAM a flash memory and a CPU .

The RAM stores a mapping information table a copy management table and a copy generation management table . The RAM also stores pool management information not illustrated for managing a pool of unused TPPSs.

The copy generation management table stores copy information that associates a saving generation number of copy generation an identifier of a TPPS storing copy source data and a logical address indicating a copy destination with each other. The data structure of data stored in the copy generation management table is described later with reference to .

The flash memory stores firmware . The functional configuration of functions described in the firmware is described later with reference to . The CPU loads and executes the firmware stored in the flash memory thereby performing various types of arithmetic process. The configuration of the CM is similar to that of the CM .

Next with reference to the data structure of data stored in the copy generation management table and a copy generation management table are described. Since the data structure of data stored in the copy generation management table is similar to the data structure of data stored in the copy generation management table the data structure of data stored in the copy generation management table is described here.

Here a copy generation stored in the copy generation management table represents a saving generation number of copy generation. In other words the copy generation represents how many times an UNMAP command and copy of a snapshot type are executed alternately and repeatedly to an identical logical LBA. For example the copy generation has a value such as 1 and 2 .

The copy source TPPS stored in the copy generation management table represents an identifier of the TPPS of the copy source. For example the copy source TPPS has a value such as TPPS11 and TPPS20 .

The copy destination OLU stored in the copy generation management table represents an identifier of the OLU of the copy destination. For example the copy destination OLU has a value such as 1 and 2 . The OLU is a logical unit generally used in open systems.

The copy destination logical LBA stored in the copy generation management table represents a logical address in the OLU of the copy destination. For example the copy destination logical LBA has a value such as 5000 and 6000 .

In the example illustrated in the copy generation management table represents that the data of the logical volume stored in the TPPS11 is copied to the logical LBA 5000 of the OLU 1 as a first generation. Similarly the copy generation management table represents that the data of the logical volume stored in the TPPS11 is copied to the logical LBA 6000 of the OLU 2 as a second generation.

The copy generation management table represents that the data of the logical volume stored in the TPPS20 is copied to the logical LBA 7000 of the OLU 3 as a third generation.

Next with reference to functional configurations of the functions described in the firmware and executed by the storage device according to the second embodiment are described. Since the functional configurations of the functions described in the firmware and executed by the storage device according to the second embodiment are similar the firmware and are referred as firmware here for the description.

The TPPS generation management section executes the following process in a case of executing copy process to data stored in a physical address that is freshly associated with the logical address specified in the request for release upon accepting a request for release of the TPPS storing the data subjected to copy. That is the TPPS generation management section gives a saving generation number to carry out copy process and causes the given saving generation number to be stored in the copy generation management table thereby managing generations of the TPPS.

The copy generation process control section executes the following process in a case of executing copy process to the data stored in the physical address that is freshly associated with the logical address specified in the request for release upon accepting a request for release of the TPPS storing the data subjected to copy. That is the copy generation process control section causes the copy information that associates an identifier of a TPPS storing copy source data and a logical address indicating a copy destination in association with a saving generation number of copy generation to be stored in the copy generation management table . For example the copy generation process control section causes a pair of the TPPS of the copy source and the OLU of the copy destination to be stored in the copy generation management table for each copy generation.

The copy process control section executes copy process for each saving generation number of copy generation with reference to the copy generation management table

Next with reference to one example of process behaviors by the storage device according to the second embodiment is described. is a diagram illustrating one example of process behaviors by the storage device according to the second embodiment. illustrates a case that release of the TPPS indicated by the logical LBA 2000 and copy of the data of the logical volume stored in the TPPS indicated by the logical LBA 2000 are executed alternately.

As illustrated in the storage device executes copy mentioned as copy A of the data of the logical volume stored in a TPPS mentioned as TPPS A indicated by the logical LBA 2000 S . The storage device also executes copy mentioned as copy B of the data of the logical volume stored in the TPPS A indicated by the logical LBA 2000 S .

The storage device receives an UNMAP command from the host computer that requests for release of the TPPS A indicated by the logical LBA 2000 . Since the copy of the data of the logical volume stored in the TPPS A requested for release is in execution the storage device manages the TPPS A indicated by the logical LBA 2000 as a first generation. The storage device also deletes the TPPS A from the mapping information to update the mapping information table S . Accordingly it is possible to save the TPPS A from an access related to the TPV by the host computer . Then the storage device sends a response to the UNMAP command to the host computer .

Subsequently the storage device receives a write request from the host computer to the TPPS indicated by the logical LBA 2000 . The storage device acquires a new TPPS mentioned as TPPS B for the logical LBA 2000 upon receiving the write request.

Then the storage device receives write data from the host computer and sends a response to the write request to the host computer . The storage device also executes copy mentioned as copy C of the data of the logical volume stored in the TPPS B S .

Subsequently the storage device receives an UNMAP command from the host computer that requests for release of the TPPS B indicated by the logical LBA 2000 . Since the copy of the data of the logical volume stored in the TPPS B requested for release is in execution the storage device manages the TPPS B indicated by the logical LBA 2000 as a second generation. The storage device also deletes the TPPS B from the mapping information to update the mapping information table S . Accordingly it is possible to save the TPPS B from an access related to the TPV by the host computer . Then the storage device sends a response to the UNMAP command to the host computer .

Subsequently the storage device receives a write request from the host computer to the TPPS indicated by the logical LBA 2000 . The storage device acquires a new TPPS mentioned as TPPS C for the logical LBA 2000 upon receiving the write request.

Then the storage device receives write data from the host computer and sends a response to the write request to the host computer . The storage device also executes copy mentioned as copy D of the data of the logical volume stored in the TPPS C S .

Subsequently the storage device receives an UNMAP command from the host computer that requests for release of the TPPS C indicated by the logical LBA 2000 . Since the copy of the data of the logical volume stored in the TPPS C requested for release is in execution the storage device manages the TPPS C indicated by the logical LBA 2000 as a third generation. The storage device also deletes the TPPS C from the mapping information to update the mapping information table S . Accordingly it is possible to save the TPPS C from an access related to the TPV by the host computer . The storage device acquires a new TPPS mentioned as TPPS D for the logical LBA 2000 in a case of receiving a write request from the host computer to the TPPS indicated by the logical LBA 2000 .

The storage device releases the TPPS A in the first generation after finishing the copy A and the copy B of the TPPS A S . The storage device also releases the TPPS B in the second generation after finishing the copy C of the TPPS B S . Similarly the storage device releases the TPPS C in the third generation after finishing the copy D of the TPPS C S .

Next with reference to a process procedure of the mapping information update process by the storage device according to the second embodiment is described. is a flowchart illustrating a process procedure of mapping information update process by the storage device according to the second embodiment.

As illustrated in the UNMAP command processing section receives an UNMAP command S . Then the conflict detection section determines whether or not to execute the copy process of the TPPS requested for release S .

Here in a case of being determined to execute the copy process of the TPPS requested for release by the conflict detection section Yes in S the UNMAP command processing section does not immediately release the TPPS requested for release S .

Then the TPPS generation management section gives a saving generation number to carry out the copy process to be stored in the copy generation management table S . The copy generation process control section causes the copy information that associates an identifier of a TPPS storing copy source data with a logical address indicating a copy destination to be stored in the copy generation management table S .

Subsequently the copy process control section determines whether or not there are a plurality of items of copy process S . Here in a case of determining that there are a plurality of items of copy process Yes in S the copy process control section launches the plurality of items of copy process in the background S . In contrast in a case of determining that there is only one item of copy process No in S the copy process control section launches the copy process in the background S .

In contrast in a case of being determined not to execute copy process of the TPPS requested for release by the conflict detection section No in S the UNMAP command processing section releases the TPPS requested for release S .

After finishing S S or S the TPPS mapping management section updates the mapping information stored in the mapping information table such that the TPPS requested for release from the host computer becomes in a release state S .

Subsequently the UNMAP command processing section sends a response to the UNMAP command to the host computer S and finishes the mapping information update process.

As described above the storage device according to the second embodiment is capable of managing a pair of a copy source and a copy destination for each generation.

In the first and second embodiments the copy is executed by taking an OLU as a copy destination in a case that the storage device copies the data of the logical volume stored in the TPPS requested for release. The storage device may also take a TPV not an OLU as a copy destination.

In such a case the storage device may also updates the mapping information table or for the copy destination without executing copy process.

With that in a third embodiment a case that the copy process control section has the following functions is described. The copy process control section according to the third embodiment executes the following process in a case that the copy destination of the data of the logical volume stored in the saved TPPS is a TPV. That is the copy process control section associates the logical LBA of the TPV in the copy destination with the physical LBA indicating the TPPS to be stored in the mapping information table

With reference to the process procedure of the process by the storage device according to the third embodiment is described. is a flowchart illustrating a process procedure at the time of copy to a TPV by the storage device according to the third embodiment. illustrates a case of copying the TPPS22 indicated by the logical LBA 2000 to the logical LBA 9000 of the TPV.

As illustrated in the UNMAP command processing section receives an UNMAP command S . Then the conflict detection section determines whether or not to execute the copy process of the TPPS requested for release S .

Here in a case of being determined to execute the copy process of the TPPS requested for release by the conflict detection section Yes in S the UNMAP command processing section suspends release of the TPPS requested for release S . Then the copy process control section determines whether or not the copy destination is a TPV S .

In a case of determining that the copy destination is not a TPV No in S the copy process control section launches the copy process in the background S . In contrast in a case of determining that the copy destination is a TPV Yes in S the copy process control section determines to omit the copy process in the background S . Then the copy process control section updates the mapping information for the copy destination instead of executing the copy process S . For example the copy process control section causes information that associates the logical LBA 9000 with the TPPS22 to be stored in the mapping information table as the mapping information for the copy destination.

In contrast in a case of being determined not to execute the copy process of the TPPS requested for release by the conflict detection section No in S the UNMAP command processing section releases the TPPS requested for release S .

After finishing S S or S the TPPS mapping management section updates the mapping information such that the TPPS requested for release from the host computer becomes in a release state S . For example the TPPS mapping management section deletes a value stored in the physical LBA that is associated with the logical LBA 2000 .

Then the UNMAP command processing section sends a response to the UNMAP command to the host computer S and finishes the process.

In such a manner in a case that the copy destination of the TPPS requested for release is a TPV the storage device may omit the copy process. The process of omitting the copy process may be combined with the process of managing the copy generation.

Next with reference to one example of process behaviors to combine the process of omitting copy process with the process of managing the copy generation by the storage device according to the third embodiment is described. is a diagram illustrating one example of process behaviors by the storage device according to the third embodiment. illustrates a case that release of the TPPS indicated by the logical LBA 2000 and copy of the data of the logical volume stored in the TPPS indicated by the logical LBA 2000 are executed alternately and that the copy destination is a TPV.

As illustrated in the storage device receives an UNMAP command from the host computer that requests for release of the TPPS A indicated by the logical LBA 2000 . Here in a case of executing copy mentioned as copy A of the data of the logical volume stored in a TPPS mentioned as TPPS A requested for release the storage device manages the TPPS A indicated by the logical LBA 2000 as a first generation. The storage device also deletes the TPPS A from the mapping information to update the mapping information table . Accordingly it is possible to save the TPPS A from the access related to the TPV by the host computer . Since the copy destination is a TPV the storage device determines to omit copy process and updates the mapping information for the copy destination instead of executing the copy process S .

After finishing the copy A the storage device executes copy mentioned as copy B of the data of the logical volume stored in the TPPS A S . In this case since the copy source is the already saved TPPS A the storage device physically copies the data of the logical volume stored in the TPPS A .

Subsequently the storage device receives a write request from the host computer to the TPPS indicated by the logical LBA 2000 . The storage device acquires a new TPPS mentioned as TPPS B for the logical LBA 2000 .

Then the storage device receives an UNMAP command from the host computer that requests for release of the TPPS B indicated by the logical LBA 2000 . Here in a case of executing copy mentioned as copy C of the data of the logical volume stored in the TPPS B requested for release the storage device manages the TPPS B indicated by the logical LBA 2000 as a second generation. The storage device also deletes the TPPS B from the mapping information to update the mapping information table . Accordingly it is possible to save the TPPS B from the access related to the TPV by the host computer . Since the copy destination is a TPV the storage device determines to omit copy process and updates the mapping information for the copy destination instead of executing the copy process S .

Subsequently the storage device receives a write request from the host computer to the TPPS indicated by the logical LBA 2000 . The storage device acquires a new TPPS mentioned as TPPS C for the logical LBA 2000 .

Then the storage device receives an UNMAP command from the host computer that requests for release of the TPPS C indicated by the logical LBA 2000 . Here in a case of executing copy mentioned as copy D of the data of the logical volume stored in the TPPS C requested for release the storage device manages the TPPS C indicated by the logical LBA 2000 as a third generation. The storage device also deletes the TPPS C from the mapping information to update the mapping information table . Accordingly it is possible to save the TPPS C from the access related to the TPV by the host computer . Since the copy destination is a TPV the storage device determines to omit copy process and updates the mapping information for the copy destination instead of executing the copy process S .

Subsequently the storage device receives a write request from the host computer to the TPPS indicated by the logical LBA 2000 . The storage device acquires a new TPPS mentioned as TPPS D for the logical LBA 2000 .

After finishing the copy A and the copy B of the TPPS A in the first generation the storage device releases the TPPS A . After finishing the copy C of the TPPS B in the second generation the storage device releases the TPPS B . Similarly after finishing the copy D of the TPPS C in the third generation the storage device releases the TPPS C .

The embodiments may be implemented in a variety of different modes other than the embodiments described above. Among each items of process described in the embodiments all or part of the process described to be executed automatically may also be executed manually. Alternatively all or part of the process described to be executed manually may also be executed automatically in an existing method. Other than them the process procedure the control procedure and the specific names represented in the above description and the drawings may be optionally modified unless otherwise specified.

In accordance with various types of load status of use and the like the order of process may also be modified in the process described in each embodiment.

Each of the illustrated components is functionally conceptual and is not desired to be physically configured as illustrated. For example among the functions of the firmware executed by the storage device the TPPS generation management section and the copy generation process control section may be integrated. Further each process function executed in each device may be achieved by a CPU and a program analyzed and executed by the CPU or achieved as hardware by a wired logic in its all or an optional part.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

