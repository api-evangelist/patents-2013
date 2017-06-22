---

title: Method for asynchronous population of data caches used with mass storage devices
abstract: A method and system for transferring data from mass storage devices to the high speed data cache in a manner that imposes minimal overhead to the normal input/output mechanism and minimizes the load placed on the device being cached is disclosed herein. Minimizing the load placed on the slower device and minimizing the overhead of processing input/output requests results in optimal performance.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09442859&OS=09442859&RS=09442859
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09442859
owner_city: 
owner_country: KR
publication_date: 20130223
---
The present application claims priority to U.S. Provisional Patent Application No. 61 660 801 filed on Jun. 17 2012 which is herby incorporated by reference in its entirety.

Caches must be populated with data before they can begin to offload data accesses from slower devices. This involves copying data from the slower device being cached into the higher speed cache device. Typically this involves a read operation from the slower device followed by a write to the cache device. Since the main intent of high speed caching devices is to offload the slower mass storage devices most caching algorithms attempt to minimize I O requests to the slower mass storage devices.

Traditional caches copy the data to the cache device during the processing of an input output request to the slower device. This approach may be termed opportunistic synchronous population since it takes advantage of the opportunity afforded by the existing input output request to copy the data without having to perform an additional read request to the device being cached. Unfortunately this opportunistic approach introduces extra processing on the input output request since the data cannot be released to the origin of the input output request until the copy has been completed in effect synchronizing the act of copying the data for the purposes of populating the cache and the processing of an input output request. Furthermore this type of opportunistic cache population can be complicated by performance optimizations that coalesce non adjacent input output requests by creating scatter gather lists that discard portions of the data represented by the input output request. In environments that perform this type of optimization the opportunistic synchronous cache population algorithms must inspect the memory buffers associated with all outstanding input output requests to ensure there are no overlapping regions that could corrupt the data being copied to populate the cache.

Application Programming Interface API is a collection of computer software code usually a set of class definitions that can perform a set of related complex tasks but has a limited set of controls that may be manipulated by other software code entities. The set of controls is deliberately limited for the sake of clarity and ease of use so that programmers do not have to work with the detail contained within the given API itself.

 Cache refers to the memory in which data is stored in order to make the data more readily and speedily accessible transparently. When a cache is exhausted it is flushed of data to be replaced with the next cache according to a replacement algorithm.

 Cached data is data in cache memory duplicating original values stored elsewhere such as the hard disk on a computer.

 Cache hit refers to when the processor looks for data in cache memory and finds the data. A cache hit places less strain on input output I O resources and limited network resources.

 Cache miss refers to when the processor looks for data in cache memory and finds that it is not there resulting in having to read from the main memory or hard disk. Data retrieved during a cache miss is often written into the cache in anticipation of further need for it.

 Caching resources refers to the physical or virtual components of limited availability required for caches or the process of caching such as memory or a processing unit.

 Cloud computing is generally defined as using computing resources primarily servers owned by a third party provider such as the AMAZON ELASTIC COMPUTE CLOUD JOYENT and GOOGLE APPS such that the user does not need to make a substantial investment in computer hardware and scale resources depending on the user s needs. Cloud computing primarily involves Web applications but can include storage raw computing and other specialized services.

Compatibility library is a software program that provides an interface between computer programs and in particular an interface that provides an interface between a proprietary environment and an open source or GNU GPL device driver that provides the supporting functionality for the device driver.

 Data center is a centralized location where computing resources such as host computers servers applications databases or network access critical to an organization are maintained in a highly controlled physical environment.

Device driver is a software program that allows a hardware device to interact with software installed on the hardware device.

 Execution environments refers to operating systems or virtual machines in which executable programs are executed. When a computer program is executed or running a process is created.

GNU General Public License is a license for an open source operating system based on UNIX which requires that derived works be distributed under the same license terms.

Hypervisor is a hardware virtualization technique that allows a computer to host multiple operating systems by providing a guest operating system with a virtual operating platform.

Kernel is a component of an operating system that connects a computer s software applications to the computer s hardware.

 Load balancing refers to distributing workload across multiple computers central processing units or other resources to achieve optimal resource utilization maximize throughput minimize response time and avoid overload.

 Logical unit number or LUN is an identification number given to logical units devices connected to a SCSI Small Computer System Interface adapter typically the logical disks in a storage area network SAN .

 Mass storage devices refers to removable or non removable media that can store large amounts of data such as tape drives redundant array of independent disks RAID magnetic disks or flash drives.

 Non volatile caching device refers to a storage device that can retain data within memory even when the device is not powered on such as a flash drive.

 Open source software or OSS refers to computer software that is available with open access to the source code design and implementation which is typically free.

 Process identifier process ID or PID is a number used by operating systems OS to uniquely identify a process an OS object that consists of an executable program a set of virtual memory addresses and one or more threads. When a program runs a process is created.

Semaphore is an abstract data type that provides an abstraction for controlling access to a common resource in a parallel programming environment by multiple processes.

 Virtualization refers to a computer software hardware platform that allows running several operating systems simultaneously on the same computer. VMware vSphere Hypervisor ESXi is an example of a hardware virtualization product.

 Web Browser is a complex software program resident in a client computer that is capable of loading and displaying text and images and exhibiting behaviors as encoded in HTML HyperText Markup Language from the Internet and also from the client computer s memory. Major browsers include MICROSOFT INTERNET EXPLORER NETSCAPE APPLE SAFARI MOZILLA FIREFOX and OPERA.

 Web Server is a computer able to simultaneously manage many Internet information exchange processes at the same time. Normally server computers are more powerful than client computers and are administratively and or geographically centralized. An interactive form information collection process generally is controlled from a server computer.

Data within computing environments may be cached to high speed devices to improve performance. The majority of data is stored on mass storage devices i.e. disk drives and disk arrays and transferred to caches devices on an as needed basis. The placement of data within the high speed device is referred to as population of the cache and requires the transfer of data from the slower device being cached to the high speed device. The transfer of data to the high speed devices may create extra load on the slower device being cached and or add overhead extra work or delays not directly related to satisfying the input output request to the fetching of data.

The present invention discloses a method for transferring data from mass storage devices to the high speed data cache in a manner that imposes minimal overhead to the normal input output mechanism and minimizes the load placed on the device being cached. Minimizing the load placed on the slower device and minimizing the overhead of processing input output requests results in optimal performance.

The purpose of this invention is to populate a high speed cache device as efficiently as possible with respect to impact on the slower device being cached and normal input ouput processing.

Having briefly described the present invention the above and further objects features and advantages thereof will be recognized by those skilled in the pertinent art from the following detailed description of the invention when taken in conjunction with the accompanying drawings.

The present invention populates a cache device in an asynchronous manner and counter intuitively issues more input output requests to a slower device in a manner that actually improves efficiency. Since the cache device population mechanism is asynchronous the cache device population mechanism imposes minimal additional processing overhead on normal input output requests e.g. the cache device population mechanism does not have to delay processing while the cache device population mechanism copies the data nor does the cache device population mechanism have to inspect the destination memory buffers . Although the method for populating a high speed cache device in an efficient manner is asynchronous the key to efficiency is a direct correlation of the asynchronous cache population with the normal input output processing.

Modern mass storage devices are electro mechanical in nature and orders of magnitude slower in access time than solid state devices such as memory or flash based caches. illustrates a system for populating a high speed cache device in an efficient manner. The system preferably comprises a mass storage device and a high speed device .

The mass storage device preferably comprises a memory a central processing unit a system bus an input output interface and caches and . The high speed cache device preferably comprises an input output interface a memory a processor a buffer manager a flash controller and multiple flash memory modules .

In order to maximize performance the mass storage device contains internal caches . The major performance limitations of the mass storage device are related to the hard drives of the mass storage device as shown in . The movement of the actuator arms of the hard drive and the physical positioning of the read write heads seeking as well as rotational delays of the spinning disks . Due to the large delays incurred positioning the heads and waiting for the correct disk location to spin under the read write heads most mass storage systems read entire tracks of data off a disk into their internal caches in the hopes of being able to satisfy subsequent read accesses without having to position the heads or wait for rotational delays.

If data is contained within the internal cache of a mass storage device the impact of satisfying a read request is minimal and limited mainly to the bandwidth consumed by transferring the data from the mass storage device . Read access to data within the internal cache does not involve the most constrained resource of the mass storage device the read write heads and the associated positioning mechanisms .

As shown in the mechanism for populating the high speed cache involves issuing asynchronous read requests to the mass storage device when there is a high probability that the requested data is present within the internal cache of the mass storage device . When the requested data is already in the internal cache of the mass storage device the impact of the additional asynchronous read request is minimized since the asynchronous read request does not require the resources of the read write heads. Furthermore since the internal caches of the mass storage device typically cache entire disk tracks and perform read ahead caching of logically adjacent disk locations the asynchronous read request used to populate the high speed cache device is of a size that is optimized for the high speed cache device regardless of the size of the input output request that triggered the population of the data in the high speed cache device .

The preferred implementation involves the signaling of an event from the main processing of the input output read request for data that is desired to be populated in the high speed caching device to an asynchronous process responsible for populating the high speed cache device . The signaling of this event contains the logical address of the data desired to be populated and imposes minimal impact to the main processing of the read request. Preferably this event is queued to the asynchronous process in a last in first out LIFO manner.

The asynchronous process upon receipt of an event reads the requested data as soon as possible. Reading the data as soon as possible after the read that triggered the cache population event maximizes the probability that the requested data is within the internal cache of the mass storage device . The size of the read request to populate the high speed cache device is optimized for the high speed cache device taking advantage of whole track reads and read ahead in the internal cache of the slower mass storage device .

The use of a LIFO queue to process the asynchronous cache population process allows the asynchronous process to maximize the probability that the data requested is in the internal cache of the mass storage device . If the asynchronous process times the read requests the asynchronous process can determine when it is not able to keep up with the eviction of stale data within the internal caches of the slower mass storage device . If the asynchronous processing detects that read requests are not being processed from the internal caches by the amount of time necessary to satisfy the read requests the asynchronous process purges older events from the queue. Doing so causes these cache population events to be lost. 

Lost cache population events result in a slower population of the high speed cache device however lost cache population events avoid cache population reads from presenting extra load on the constrained resources of the read write heads in the mass storage device .

The mechanism for populating a high speed cache device in an efficient manner is alternatively implemented without the use of a LIFO queuing mechanism. Doing so decreases the likelihood of satisfying the asynchronous cache population read requests. Although events are listed as the signaling method between the main processing of input output requests and the asynchronous cache population process other mechanisms such as a combination of queues messages or other data structures and semaphores interrupts or other notifications may be used. The use of the term process is generic and may refer to any scheduling mechanism such as an actual process or threading implementation.

The present invention minimizes processing delays of normal input output requests. The mechanism for populating a high speed cache device in an efficient manner preferably does not require delays to copy data buffers during normal input output processing and does not need to verify the integrity of data read during normal input output processing prior to populating the high speed cache device. The mechanism for populating a high speed cache device in an efficient manner requires only a notification of the asynchronous population process when desired data is highly likely to be present in the internal cache of the mass storage device.

The present invention preferably reduces demands on the most highly limited resources of the mass storage device . By maximizing the probability the read request used to populate the high speed cache device will be present in the internal cache of the mass storage device the mechanism reduces load on the read write heads associated positioning mechanism as well as minimizing rotational latencies.

The present invention allows the cache to be populated in increments other than the size of an opportunistic input output request. The mechanism for populating a high speed cache device in an efficient manner can take advantage of whole track caching and read ahead caching in the mass storage device to efficiently populate the high speed cache device regardless of the size of normal input output requests.

From the foregoing it is believed that those skilled in the pertinent art will recognize the meritorious advancement of this invention and will readily understand that while the present invention has been described in association with a preferred embodiment thereof and other embodiments illustrated in the accompanying drawings numerous changes modification and substitutions of equivalents may be made therein without departing from the spirit and scope of this invention which is intended to be unlimited by the foregoing except as may appear in the following appended claim. Therefore the embodiments of the invention in which an exclusive property or privilege is claimed are defined in the following appended claims.

