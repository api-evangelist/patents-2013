---

title: Backup method and information processing apparatus
abstract: A backup method may include discontinuing a process of a working system virtual machine (VM) operating within a physical machine (PM) of a processing apparatus, first duplicating data of a state of the working system VM in a memory of the PM, as a duplicating system VM, second duplicating data of contents of a working system virtual recording medium used to realize the working system VM, in a duplicating system virtual recording medium forming the duplicating system VM, within a storage apparatus of the processing apparatus, and resuming the process of the working system VM. The discontinuing and the first resuming may maintain consistency between the data in the memory and the storage apparatus.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09594522&OS=09594522&RS=09594522
owner: FUJITSU LIMITED
number: 09594522
owner_city: Kawasaki
owner_country: JP
publication_date: 20130208
---
This application is a continuation application of International Application No. PCT JP2010 063619 filed on Aug. 11 2010 and designated the U.S. the entire contents of which are incorporated herein by reference.

The embodiments discussed herein are related to a backup method an information processing apparatus and a computer readable storage medians.

In a physical machine hereinafter also referred to as a computer an operating state of the computer may be acquired to provide a backup in order to enable execution of a process to continue even when a fault is generated within the computer during the execution of the process. The backup of the operation state of the computer may be acquired as a so called snapshot . For example even when the fault is generated within a working system computer the snapshot of the operating state of the working system computer acquired as the backup before the fault is generated may be used to restore the operating state of the working system computer before the fault is generated within a duplicating or backup or copying system computer.

On the other hand in a VM Virtual Machine there are various proposed methods to acquire an operating state of the VM as the snapshot in order to cope with a situation in which the fault is generated within the VM. The operating state of the VM includes an operating state of a virtual processor for example a virtual CPU Central Processing Unit and memory contents where the virtual processor may run on or operate in a processor for example a CPU of the computer in which the VM operates. In addition the fault may include a fault that is caused by software and is generated within the VM and a fault that is caused by hardware and is generated within the computer in which the VM operates.

According to the proposed method that provides the backup by acquiring the operating state of the VM as the snapshot the operating state of the VM operating state of the virtual CPU and memory contents may be stored directly in a storage unit such as a disk drive and the like as backup data that is snapshot in order to provide the backup. For this reason it may take a relatively long time to perform a backup process depending on a memory size allocated to the VM. Hence a stop time of a working process may become relatively long when the working system VM is temporarily stopped during the backup process. On the other hand when the working system VM is not temporarily stopped during the backup process a data consistency cannot be maintained between the data of the VM restored using the backup data and the data of the working system VM. Furthermore according to the proposed method the VM may be restored using the backup data only when the fault is generated within the working system VM and a reference to the backup data maintaining the data consistency cannot be made while the working system VM is operating. When the data consistency is not maintained a state in which there is no dropout or discrepancy in a structure or meaning of the data when viewed front an application or application program that is executed in the working system VM hereinafter referred to as an application consistency cannot be maintained.

In the case of a method that stops the working system VM during the backup process in order to maintain the application consistency the working process or service may be discontinued. In this case when the working system VM is used in a data center and the like a notification may be required to notify users that the working process or service is discontinued. On the other hand in the case of a method that embeds an associating mechanism with respect to the storage unit for each application and writes contents of a buffer and cache into the storage unit when creating the snapshot the method cannot be applied to an application that does not have the associating mechanism. In addition in the case of a method that calls a snapshot creating application in the storage unit side from the working system side applied with the working system VM functions need to be added with respect to the working system and users need to be educated. In this case when the working VM is used in the data center and the like the storage unit side may require multiplicity management scheduling and security measures.

The applicant is aware of Japanese Laid Open Patent Publications No. 2009 533777 No. 2009 80692 and No. 2007 183701 for example.

According to the prior art backup method it may be difficult to appropriately provide a backup of the data of the VM while the working system VM is operating.

Accordingly it is an object in one aspect of the embodiment to provide a backup method an information processing apparatus and a computer readable storage medium which may appropriately provide a backup of the data of the VM while the working system VM is operating.

According to one aspect of the present invention a backup method to backup data of an information processing apparatus including a storage apparatus and a physical machine that includes a memory may include discontinuing a process of a working system virtual machine operating within the physical machine first duplicating data of a state of the working system virtual machine in the memory as a duplicating system virtual machine second duplicating data of contents of a working system virtual recording medium used to realize the working system virtual machine in a duplicating system virtual recording medium forming the duplicating system virtual machine within the storage apparatus and resuming the process of the working system virtual machine wherein the discontinuing and the resuming maintain consistency between the data in the memory and the data in the storage apparatus.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

Preferred embodiments of the present invention will be described with reference to the accompanying drawings.

In one embodiment a backup method an information processing apparatus and a computer readable storage medium may backup data of the information processing apparatus including a storage apparatus and a physical machine that includes a memory. The backup process may include discontinuing a process of a working system virtual machine operating within the physical machine duplicating data of a state of the working system virtual machine in the memory as a duplicating system virtual machine duplicating data of contents of a working system virtual recording medium used to realize the working system virtual machine in a duplicating system virtual recording medium forming the duplicating system virtual machine within the storage apparatus and resuming the process of the working system virtual machine. The discontinuing and the resuming may maintain consistency between the data in the memory and the data in the storage apparatus.

Because the backup process may duplicate the state of the working system virtual machine in the memory as the duplicating system virtual machine substantially without stopping the working system virtual machine the backup of the state of the working system virtual machine to the duplicate system virtual machine may be performed appropriately while the working virtual machine operates.

A description will now be given of the backup method the information processing apparatus and the computer readable storage medium in each embodiment according to the present invention.

The computer may have a known hardware structure including at least one processor such as a CPU and the like at least one memory an input device such as a keyboard and the like a display unit and the like. The memory may store one or more programs to be executed by the processor and various data including intermediate data of computation processes executed by the processor. Working system VMs Virtual Machines through N N is a natural number greater than or equal to one a duplicating or backup or copying system VM a backup mechanism a visualization mechanism a duplicate mechanism a discontinue mechanism a resume mechanism and a store mechanism of the computer may respectively correspond to functions or means that are realized when the processor executes procedures of the program. The visualization mechanism may provide a known function or means that realizes the VMs through N and within the computer . In parts of the duplicating system are surrounded by a dotted line.

On the other hand the storage apparatus may have a known structure including at least one processor and at least one storage unit. In this embodiment it is assumed for the sake of convenience that the storage unit forming the storage apparatus is at least one disk drive having at least one disk recording medium that is physical recording medium . The storage apparatus may include working system virtual disks through M M is a natural number greater than or equal to two a SS Snap Shot mechanism a duplicating system virtual disk and a backup storage .

The SS mechanism may be provided within the computer instead of within the storage apparatus . In addition the backup storage may be formed by a storage unit that is separate from the storage apparatus and is externally connected to the computer as long as the backup storage is accessible from the store mechanism .

When a user inputs a backup instruction from the input device to the backup mechanism or a known timer mechanism not illustrated within the computer inputs the backup instruction to the backup mechanism in step ST the backup mechanism issues a discontinue instruction with respect to the discontinue mechanism in step ST. The timer mechanism may input the backup instruction to the backup mechanism for every predetermined time or at a timing in accordance with an arbitrary schedule that may be preset. In addition a sequence in which the timer mechanism inputs the backup instruction of the plurality of working system VMs through N to the backup mechanism may be fixedly set to an arbitrary sequence or may be set to a random sequence. For example when the backup instruction of the working system VM is input the discontinue mechanism may execute a discontinue operation with respect to the working system VM in order to discontinue the process of the working system VM in step ST. On the other hand the backup mechanism may issue a duplicate instruction with respect to the duplicate mechanism in step ST. Hence the duplicate mechanism may create within the memory a duplicate of the operating state of the virtual CPU forming the working system VM and the contents of the memory or memory contents used to realize the working system VM that is a snapshot of the operating state in step ST. Because the operating state of the virtual CPU forming the working system VM is stored within the memory that stores the memory contents used to realize the working system VM the snapshot of the operating state created within the memory used to realize the duplicating system VM by the duplicate mechanism corresponds to the duplicate of the memory contents used to realize the working system VM . In this embodiment the snapshot of the operating state of the working system VM may be created within the memory as the duplicating system VM by a COW Copy On Write as indicated by COW in .

Accordingly when storing the operating state of the working system VM that is memory contents used to realize the working system VM the working system VM may be duplicated temporarily or permanently in the memory within the computer instead of writing the operating state directly to the disk of the storage apparatus . For this reason the backup process may be performed at a high speed.

The backup mechanism may issue a duplicate instruction with respect to the SS mechanism. in step ST. Hence the SS mechanism may create a snapshot of the working system virtual disk of the storage apparatus for example in the duplicating system virtual disk in step ST. On the other hand the backup mechanism may issue a resume instruction with respect to the resume mechanism in step ST. The resume mechanism may execute a resume operation to resume the process with respect to the working system VM whose process is discontinued by the discontinue mechanism and whose snapshot of the operating state is formed in the duplicating system VM by the duplicate mechanism that is with respect to the working system VM in this example in step ST.

In addition the backup mechanism may issue a store instruction with respect to the store mechanism in step ST. Hence the store mechanism may store the memory contents of the duplicating system VM and the contents of the duplicating system virtual disk into the backup storage in a single store operation in step ST. A timing at which the backup mechanism issues the store instruction with respect to the store mechanism may be any arbitrary timing after the process of the working system VM is resumed by the resume mechanism and may be a timing instructed by the timer mechanism for example. In other words the process that stores the memory contents of the duplicating system VM and the contents of the duplicating system virtual disk into the backup storage in the single store operation may be completed without affecting the process of the working system VM . However because the process of creating the duplicate of the operating state of the virtual CPU and the memory contents of the working system VM within the memory of the duplicating system VM and the process of creating the duplicate of the contents of the working system virtual disk within the duplicating system virtual disk may foe executed asynchronously to each other the discontinue mechanism and the resume mechanism operate to maintain the consistency of the data in the memory and the data in the disk. In addition by executing the process of creating the duplicate of the operating state of the virtual CPU and the memory contents of the working system VM within the memory of the duplicating system VM that is creating the snapshot of the operating state by the COW the time for which the process of the working system VM stops may be further reduced and a memory capacity of the duplicating system VM used to store the snapshot of the operating state may be reduced. For this reason even when the memory size of the working system VM is relatively large the duplicate of the contents of the working system virtual disk may be created in a satisfactory manner.

Information held by the known virtualization mechanism may include at least a part of the information managed by the VM management table . Hence the VM management table may be created by making a reference to the information held by the virtualization mechanism .

On the other hand the process advances to step SS when the judgment result in step S is YES. In step S the controller judges whether the VM having the VM ID specified by the backup instruction and managed by the VM management table has a VM state that indicates executing and the process advances to step S when the judgment result in step SS is YES. In step S the controller outputs a discontinue instruction with respect to the discontinue mechanism instructing the process of the VM that is executing that is the working system VM to be discontinued. Hence the discontinue mechanism may update the VM state of the VM having the corresponding VM ID in the management table to stopped in response to the discontinue instruction and sets the resume flag to 1 in order to indicate that the process of this VM needs to be resumed. When the judgment result in step S is NO or after step S the process advances to step S. In step S the controller outputs a duplicate instruction with respect to the duplicate mechanism instructing the duplicate of the working system VM to be created. Hence the duplicate mechanism may create a duplicate of the operating state of the virtual CPU forming the VM of the working system VM and the memory contents used to realize the working system VM that is the snapshot of the operating state within the memory that stores the memory contents used to realize the duplicating system VM in response to the duplicate instruction. Step S outputs the duplicate instruction with respect to the SS mechanism instructing the duplicate of the working system virtual disk to be created. Accordingly the SS mechanism may create the duplicate of the contents of the working system virtual disk that is the snapshot of the storage apparatus within the duplicating system virtual disk in response to the duplicate instruction. In step S the controller makes a reference to the information of the VM that is managed by the VM management table and has the VM ID specified by the backup instruction.

In step S the controller judges whether the resume flag of the VM ID managed by the VM management table and specified by the backup instruction is set to 1 and the process advances to step S when the judgment result in step S is YES. In step S the controller outputs a resume instruction with respect to the resume mechanism . Hence the resume mechanism may clear the resume flag of the VM having the corresponding VM ID in the VM management table to 0 in response to the resume instruction. When the judgment result in step S is or after step S the process advances to step S. In step S the controller outputs a store instruction with respect to the store mechanism . Accordingly the store mechanism may store the memory contents of the duplicating system VM and the contents of the duplicating system virtual disk in the backup storage in the single store operation. In step S the controller notifies the backup completion or the successful backup via the UI or the external API that received the backup instruction and the process ends.

According to the backup process of this embodiment the backup of the data of the working system VM may be provided while the working VM is operating and in a state in which the application consistency is maintained.

In addition because the operating state of the working system VM may be duplicated in the memory at a high speed the backup process may be completed within a predictable time substantially without stopping the working system VM. Hence when the VM is used in the data center for example an operator or manager of the data center may flexibly schedule the system backup operation.

Moreover by duplicating the operating state of the working system VM within the memory in the VM format the process may be resumed by the duplicating system VM when a fault is generated in the working system VM in order to quickly restore the system using the VM. Of course the operating state of the working system VM stored in the memory that is the duplicating system VM may be discarded at an arbitrary timing such as when the storage to the backup storage in the single store operation is completed for example.

Furthermore because there is no need to embed the backup mechanism for maintaining the application consistency in the VM the cost of negotiations or exchanges between the operator or manager and the user embedding operation and inspection operation may foe prevented from increasing. In addition because there is no need to embed the backup mechanism for maintaining the application consistency in the VM the application consistency may be maintained regardless of the operating state or the type of an OS Operating System and applications running on the VM.

In this embodiment a virtual disk at a connecting destination of the duplicating system VM is switched to the duplicating system virtual disk different from the working system virtual disk . In order not to affect the process or operation of the working system VM an external network connection of the duplicating system VM is cutoff so that the duplicating system VM cannot make a network communication with a VM other than itself. After the external network connection of the duplicating system VM is cutoff the process or operation of the duplicating system VM is resumed. These series of processes may be executed automatically by the backup mechanism in succession to the storage of the contents to the backup storage in a single store operation in accordance with the first embodiment described above.

When the user inputs a restore instruction from the input device to the backup mechanism or a restore instruction generated within the computer is input to the backup mechanism in step ST the backup mechanism issues a load instruction with respect to the load mechanism. in step ST issues a switch instruction with respect to the switching mechanism in step ST and issues a cutoff instruction with respect to the cutoff mechanism in step ST. The cutoff mechanism issues the cutoff instruction with respect to the virtual bridge in step ST. The backup mechanism issues a resume instruction with respect to the resume mechanism in step ST and the resume mechanism executes a resume operation to resume the process with respect to the duplicating system VM in step ST. In addition the backup mechanism issues an end instruction with respect to the end mechanism in step ST and the end mechanism executes an end operation that ends the process of the duplicating system VM hereinafter also referred to as the duplicate VM by a shutdown procedure in step ST.

Physical disk regions for each of the VMs through N and within the storage apparatus correspond to each of the virtual disks through M and in the computer . The visualization mechanism performs the process of making each of the virtual disks through M and correspond to each of the VMs through N and . The process of making the virtual disk correspond to the VM may also be executed in the first embodiment described above. The switching mechanism switches the correspondence of the virtual disks and the VMs in order to avoid the duplicate system VM from writing to and reading from the virtual disk identical to the virtual disk to which and from which the working system VM performs the writing and reading.

In step S illustrated in the switching mechanism receives the switch instruction with respect to the duplicating system VM from the backup mechanism . In step S the switching mechanism makes a reference to the VM management table and acquires the physical disk address of the physical disk that is a switching target. In step S the switching mechanism newly creates a duplicating system virtual disk that is different from the working system virtual disk in the computer . In this example the physical disk address acquired in step S is iqn.2009 12.com.bk001 and the virtual disk identifier of the duplicating system virtual disk newly created in step S is dev sdbk001 which is different from the virtual disk identifier dev sd001 of the working system virtual disk. In step S the switching mechanism connects tat is relates the newly created duplicating system virtual disk to the physical disk within the storage apparatus . In step S the switching mechanism updates the virtual disk identifier column in the VM management table . In this example the virtual disk identifier with respect to the VM ID bk001 managed by the VM management table is dev sd001 and is the same as the virtual disk identifier with respect to the VM ID vm001 but is updated to dev sdbk001 in step S. In step S the switching mechanism performs a complete notification with respect to the backup mechanism to indicate that the switching of the virtual disks is completed.

On the other hand when the judgment result in step S is YES the process advances to step S. In step S the controller outputs a load instruction with respect to the load mechanism . Hence the load mechanism loads the duplicating system VM that is specified by the restore instruction and is managed by the VM management table and whose executing state is stopped from the backup storage to the computer in response to the load instruction. In step S the controller outputs a switch instruction with respect to the switching mechanism . Accordingly the switching mechanism executes the switching of the virtual disks as described above in conjunction with in response to the switch instruction and updates the virtual disk identifier of the VM management table depending on the switching of the virtual disks. In step S the controller outputs a cutoff instruction with respect to the cutoff mechanism . Thus the cutoff mechanism cuts off the duplicating system VM that is the cutoff target specified by the restore instruction with respect to the external network in the manner described above in conjunction with in response to the cutoff instruction.

In step S the controller outputs a resume instruction with respect to the resume mechanism . Hence the resume mechanism executes a resume operation to resume the process of the duplicating system VM that is specified by the restore instruction in response to the resume instruction. In addition the resume mechanism updates the VM state with respect to the VM ID of the duplicating system VM that is managed in the VM management table to executing . In step S the controller makes a reference to the VM management table . In step S the controller judges whether the VM state with respect to the VM ID of the duplicating system VM specified by the restore instruction is executing in the VM management table to which the reference is made by the controller . The process advances to step S when the judgment result in step S is NO.

On the other hand the process advances to step S when the judgment result in step S is YES. In step S the controller outputs an end instruction with respect to the end mechanism . Hence the end mechanism executes an end operation to end the process of the duplicating system VM specified by the restore instruction by a shutdown procedure in response to the end instruction. In addition the end mechanism updates the VM state with respect to the VM ID of the duplicating system VM managed by the VM management table to executing . In step S the controller makes a reference to the VM management table . In step S the controller judges whether the VM state with respect to the VM ID of the duplicating system VM specified by the restore instruction is stopped in the VM management table to which the reference is made by the controller . The process advances to step S when the judgment result in step S is NO and the process advances to step S when the judgment result in step S is YES. In step S the controller notifies the restore completion or the successful restore via the UI or the external API that received the restore instruction and the process ends.

According to this embodiment by executing the loading of the duplicate system VM the resume of the process and the end of the process the backup is created from the duplicate system VM and the application consistency may be maintained solely by the virtual disk forming the duplicate system VM. In addition by switching the virtual disk at the connecting destination of the duplicate system VM to the duplicate system virtual disk different from the working system virtual disk and cutting off the connection of the duplicate system VM with respect to the external network the application consistency may be maintained solely by the virtual disk of the forming the duplicate system VM without affecting the process of the working system VM. As a result the duplicate system virtual disk maintaining the application consistency may be referred to or be updated from the working system VM or an external system.

In this embodiment after the switching of the virtual disk and the cutoff of the connection to the external network the process of the duplicate system VM may be resumed and the process of the duplicate system VM may be ended in order to store only the virtual disk maintaining the application consistency without having to once store the duplicate system VM and the virtual disk in the backup storage.

In steps ST through ST correspond to steps ST through ST illustrated in respectively. In addition steps ST through ST correspond to steps ST through ST illustrated in respectively. In this embodiment the backup mechanism does not output the load instruction in response to the restore instruction. Hence the output of the switching instruction from the backup mechanism in step ST is not triggered by the restore instruction but is triggered by the resume instruction output in step ST that is by the start of the resume operation of the resume mechanism with respect to the working system VM .

Steps ST and ST correspond to steps ST and ST illustrated in respectively. When the backup mechanism outputs the store instruction with respect to the store mechanism in step ST the store mechanism stores the contents of the virtual disk maintaining the application consistency into the backup storage in step ST. In step ST the store mechanism illustrated in stores the memory contents of the duplicate system VM and the contents of the duplicate system disk into the backup storage in the single store operation. On the other hand in the step ST the store mechanism illustrated in does not store the memory contents of the duplicate system VM into the backup storage and thus the storage in step ST is different from the single store operation of step ST.

According to this embodiment the first embodiment and the second embodiment are appropriately combined in order not to perform the single store operation to store the duplicate system VM into the backup storage and not to perform the reloading of the duplicate system VM. Hence the backup process may become relatively simple and the backup process may foe completed in a relatively short time.

According to the embodiments described above it may foe possible to appropriately provide a backup of the data of the VM while the working system VM is operating.

Although the embodiments are numbered with for example first second or third the ordinal numbers do not imply priorities of the embodiments. Many other variations and modifications will be apparent to those skilled in the art.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

