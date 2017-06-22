---

title: Secure virtual machine memory allocation management via memory usage trust groups
abstract: Embodiments are disclosed for recycling memory among virtual machine instances in the same memory usage trust group. Memory scrubbing can be ordinarily performed to avoid data leakage between different customers. However, scrubbing can be inhibited when a given virtual machine reclaims memory previously released by another virtual machine in the same trust group. Further features, such as enabling and disabling trust groups can be supported. Control of the features can be accomplished via API calls as part of a web service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09507540&OS=09507540&RS=09507540
owner: Amazon Technologies, Inc.
number: 09507540
owner_city: Reno
owner_country: US
publication_date: 20130314
---
In shared virtualized hosting environments security concerns dictate that the contents of memory be wiped before allocation to prevent leaking information to another user. For example when memory is allocated to a virtual machine instance without first scrubbing the memory data from previous memory allocations may remain available for inspection by another user. It is thus possible for a user to collect information left behind by the virtual machines of other users. Such information leakage can be problematic because virtual machine users typically expect their information to remain private.

A simple solution is to simply scrub memory after every memory deallocation before every memory allocation or both. However as virtual machine instances increase in size considerable resources can be expended on memory scrubbing.

The technologies described herein can be used for secure hosting of virtual machine instances executed by multiple customers in a hosting environment. Adoption of the technologies can provide improved performance due to reduction in resources spent scrubbing memory.

The technologies can be helpful for those wishing to provide virtual machine hosting services to multiple customers while maintaining data confidentiality. Unwanted information leaking between users can be avoided. Beneficiaries include virtual machine hosting service providers who wish to securely provide access to virtual machine instances by multiple customers. Customers can also benefit from the technologies because they can experience performance improvements.

Whenever a virtual machine is rebooted the memory allocated to the virtual machine is typically deallocated as part of the reboot process. However immediately thereafter memory is needed for allocation to the virtual machine for use after reboot. Ordinarily memory is typically scrubbed before reallocation and scrubbing large memory allocations can consume considerable resources. As described herein when a virtual machine reboots the memory can be recycled e.g. provided back to the virtual machine while avoiding scrubbing to avoid unnecessarily expending resources on scrubbing while still maintaining customer expectations regarding security.

In a server hosts a virtual machine VM instance . A memory manager maintains VM memory associations that indicate the memory portions that have been allocated to a virtual machine instance.

As shown in a memory portion out of a memory pool has been allocated to the virtual machine instance . An association ties the virtual machine instance to the memory portion . For example the memory portion can be marked as to be preserved for the virtual machine instance after reboot.

Subsequently in the virtual machine instance is rebooted. As part of the reboot process the memory portion is deallocated. However the association is maintained during reboot. The memory portion is reserved for when the virtual machine instance comes back up because it is known that the virtual machine instance is rebooting.

As shown in based on the association the same memory portion is reallocated to the same virtual machine instance. In practice the association need not be maintained after reallocation but can be.

Scrubbing of the memory portion can be inhibited as described herein. The insight leveraged here is that there is no need to scrub memory that will later be returned to a virtual machine instance right after the virtual machine instance relinquishes it temporarily as it reboots. In short if a virtual machine will be coming back online soon do not bother erasing the memory it had.

In practice the systems shown herein such as system can vary in complexity with different functionality components of differing complexity and the like. For example in practice a server will typically host a plurality of virtual machine instances and have a memory pool with various memory portions allocated to the virtual machine instances. Additional features relating to security and redundancy can also be included.

The system and any of the other systems described herein can be implemented in conjunction with any of the hardware components described herein such as the computing systems described below e.g. processing units memory and the like . In any of the examples herein the inputs outputs associations and policies can be stored in one or more computer readable storage media or computer readable storage devices. The technologies described herein can be generic to the specifics of operating systems or hardware and can be applied in any variety of environments to take advantage of the described features.

At memory e.g. a memory portion of a memory pool that is currently allocated to a virtual machine instance is marked as associated with e.g. allocated to the virtual machine instance.

At during a reboot process for the virtual machine instance the marking is preserved. Ordinarily as part of the reboot process e.g. deprovisioning the memory portion would normally be unmarked e.g. deallocated and placed into the pool of free memory. Instead as described herein the marked memory is held back from being put back in the free pool. Thus instead of removing the marking as would ordinarily be done e.g. association between the memory and the virtual machine is removed the marking is preserved.

At the marked memory is reallocated to the virtual machine instance e.g. the rebooted virtual machine instance . In practice allocation can take place before during or after the reboot. After the reboot process is complete the memory remains allocated to the virtual machine instance. The reallocating can be based at least on determining that the marked memory is marked as previously allocated to the same virtual machine instance.

In practice after reboot the virtual machine instance may require only a subset of the memory portion that was allocated before reboot. For example the virtual machine instance may have taken advantage of a memory ballooning feature during execution to increase the amount of memory beyond that initially allocated e.g. the amount of memory indicated as to be allocated in the virtual machine template or image .

Although scrubbing of the memory may ordinarily take place because the memory was deallocated and reallocated scrubbing can be inhibited for the marked memory e.g. or the subset of the memory portion as described above after the marked memory is deallocated from the virtual machine instance during the reboot process. By deallocation the virtual machine instance temporarily relinquishes the marked memory.

Subsequently when the virtual machine instance is terminated e.g. not rebooted but terminated permanently scrubbing can be performed on the memory e.g. or the subset responsive to termination. The memory no longer needs to be marked and the association between the memory portion and the virtual machine instance no longer needs to be preserved.

The method and any of the other methods described herein can be performed by computer executable instructions e.g. causing a computing system to perform the method stored in one or more computer readable media e.g. storage or other tangible media or stored in one or more computer readable storage devices. Such methods can be executed at least in part by a computing system.

In the example a plurality of virtual machine instances A N are managed by a hypervisor which includes a memory manager that maintains associations between virtual machine instances e.g. A N and memory portions e.g. A N in the memory pool . An example association can relate a particular virtual machine instance e.g. A and one or more particular memory portions e.g. A .

In the example the system also supports application programming interface API calls . Such calls can be received by a control plane management interface and sent to the memory manager to configure how the memory manager applies the technologies described herein. For example a memory policy can be specified to determine how or whether the memory manager applies various memory recycling technologies to the virtual machine instances A N. As described herein the control plane management interface can reside on a different machine than the server hosting the virtual machine instances A N.

In the example an association between a rebooting virtual machine instance A and a memory portion A is preserved during the reboot process. The memory portion A can then be reallocated to the instance A without scrubbing as described herein. In any of the examples herein one or more memory portions A can be involved.

In the example a reboot process is initiated for a virtual machine instance. At after the reboot process is initiated an association between the virtual machine instance and memory that was allocated to the virtual machine instance before the reboot process is preserved.

At after the reboot process at least a subset of the memory that was allocated to the virtual machine instance before the reboot process was initiated is reused for the virtual machine instance. For example if the memory is deallocated the memory e.g. or a portion of it can be reallocated to the instance.

The reusing can be based at least on the association between the virtual machine instance and the memory that was allocated to the virtual machine instance. As described herein scrubbing of the reused memory can be inhibited.

As described herein an indication to enable memory reuse after reboot e.g. without scrubbing can be received via an API call. The reusing can then be performed responsive to such an indication. As described herein such API calls can operate at the virtual machine instance level or other levels of granularity.

In any of the examples herein a virtual machine instance may reboot for a variety of reasons. For example an operating system executing on a virtual machine instance may reboot for any of variety of reasons internal to the operating system. Alternatively an external reason e.g. API call or the like can reboot the virtual machine instance. As part of the reboot process the guest operating system can shut down the virtual machine instance is typically deprovisioned e.g. memory is deallocated and the like relationships to the host e.g. Dom0 or other initial domain can be severed and then the relationships can be recreated. Memory can be reallocated as described herein.

In any of the examples herein a virtual machine instance may be allocated less memory after reboot than was used before reboot. For example before the reboot a memory allocation of the virtual machine instance may have been ballooned. When rebooting the amount of memory specified in the template or image for the virtual machine instance may be a lesser amount.

If so memory reuse may use less memory than what was used before the reboot e.g. because the extra memory is not needed . In such case the left over memory can be scrubbed and returned to the shared memory pool. Or the memory can continue to be reserved in anticipation of an upcoming memory ballooning request and the memory can be used to fulfill the ballooning request e.g. without scrubbing .

In any of the examples herein a feature can allow a virtual machine instance to enable or disable memory reuse after reboot. For example an indication to disable memory reuse after reboot can be received. Responsive to the indication memory is not reused e.g. unless it is first scrubbed after a reboot of the virtual machine instance.

Further it can be explicitly specified that the virtual machine be forced to different memory after a reboot e.g. regardless of whether the memory is scrubbed or not . Such a feature can be helpful when attempting to determine whether a hardware failure is causing the virtual machine to repeatedly land on defective memory.

Such features can be invoked via API calls e.g. received by a control plane management interface configured to accept such API calls . For example an API call can specify the virtual machine instance and which features are enabled or disabled. For example a particular API call can enable memory reuse after reboot without scrubbing e.g. inhibiting memory scrubbing when allocating a memory portion to a same virtual machine instance after reboot of the virtual machine instance . In practice customers may prefer a particular default e.g. no reuse which can be supported e.g. customers opt in to avail themselves of reuse .

In any of the examples herein a hosting environment can support multiple customers. Such a customer may be identified by a customer identifier but can have a plurality of users who avail themselves of the hosting services. Although a customer may be treated as a logical unit for some purposes different users within a single customer may have different configuration preferences or requirements. Further a customer or user may be performing processing for more than one internal user. Therefore control over features can be supported at a finer level of granularity than the customer identifier level. For example memory use trust groups virtual machine instance identifiers or other mechanisms can be supported as described herein.

In any of the examples herein memory scrubbing can take the form of removing the contents of memory. In practice such scrubbing can take any of a variety of approaches such as erasing memory or overwriting memory with a pattern e.g. zeros ones or some other pattern or random data to avoid the possibility that data leftover in the memory from previous processing e.g. by another virtual machine instance can be read.

In practice allocation of memory to a virtual machine instance can be prevented until scrubbing is completed. Implementations can adopt a scrub after deallocation approach a scrub before allocation approach or some combination of the two. Instead of immediate scrubbing scrubbing can be scheduled for performance at a later time during which time allocation of the memory is avoided.

However as described herein allocation e.g. recycling of memory without scrubbing or with only partial scrubbing can be implemented as described herein while addressing security concerns.

In any of the examples herein a hosting environment can support execution of multiple virtual machine instances. Such virtual machine instances can support any of a variety of operating systems virtual hardware configurations and the like. In practice virtual machine instances can be divided into different respective logical domains. Thus the instances are sometimes themselves called domains. Such domains can be considered different entities for purposes of security isolation and the like.

The hosting environment can provide the virtual machine instance with requested resources. The hosting environment can be operated by a service provider providing services to one of a plurality of customers availing themselves of the services in a cloud computing scenario. Thus the virtual machine instances are also sometimes called guests. Such guests can start execute reboot and terminate on the hosting server.

In any of the examples herein a memory manager can provide services related to memory allocation and deallocation for virtual machine instances. In practice the memory manager manages the allocation of memory in a memory pool that is shared among the virtual machine instances. Such a memory manager can be incorporated into a hypervisor or other manager of virtual machine instances. Thus any of the actions described or shown as performed by the memory manager can be performed by a hypervisor.

Management of the memory pool shared among virtual machine instances can be done independently or separately from memory management within a virtual machine instance. How the virtual machine instance manages its own memory internally need not be connected to external memory management e.g. of the memory pool shared among the virtual machine instances as described herein.

The memory manager can be configured to ordinarily scrub memory before allocating it to a virtual machine instance. However as described herein the memory manager can be further configured to inhibit memory scrubbing when reallocating a memory portion to a same virtual machine instance after reboot of the virtual machine instance.

The memory manager can track allocations and leverage such tracking mechanisms to support the features described herein. For example an allocation can be specially marked as reserved for returning to a virtual machine instance after reboot as described herein. Alternatively a mechanism separate from the allocation mechanism can be employed as desired.

In any of the examples herein allocation of memory from the memory pool to a virtual machine instance and deallocation from a virtual machine instance to the memory pool can be supported. Allocations can be chosen from available memory and deallocations can be returned to the pool for subsequent use by the same instance or other instances e.g. subject to scrubbing as described herein . While allocated to a particular virtual machine instance memory is typically unavailable to other virtual machine instances to enforce isolation. Although some of the examples show an allocation as a single portion in practice one or more portions of memory can be allocated to a virtual machine instance. Because memory addresses from the virtual machine s perspective can be mapped to the memory allocated from the pool whether or not such portions are contiguous can be transparent to the internal execution of the virtual machine.

Such memory allocation can occur in a number of scenarios. For example a virtual machine instance that is being created for hosting is sometimes called an incoming guest. Such an incoming guest is typically associated with a specified amount of memory e.g. according to a template configuration or image . As part of the creation process the specified amount of memory is allocated for the virtual machine instance before it is launched. Subsequently when the instance terminates the memory is deallocated. Rebooting can also result in deallocation as described herein subsequently the resurrected instance is then allocated memory as described herein.

Memory ballooning as described herein can also result in memory allocation after a virtual machine instance is created.

Allocating memory that has been previously deallocated is sometimes called recycling or reusing memory. Such recycling or reusing can be done while avoiding scrubbing e.g. without scrubbing or only partial scrubbing as described herein.

In any of the examples herein a memory pool can be partially or fully shared between virtual machine instances e.g. from multiple different customers executing in a hosting environment. Such a memory pool may comprise memory pages portions or the like. The memory pool described herein can comprise volatile memory such as RAM or nonvolatile storage such as magnetic or optical storage. Other technologies e.g. solid state disks or the like can also be supported.

In practice the memory can be organized as a heap or other arrangement that is managed to track allocations deallocations and available remaining memory. Associations between virtual machine instances and memory portions within the memory pool can be stored in a variety of ways. Portions or pages of the pool can be marked as allocated to a particular virtual machine instance a separate data structure can track allocations or the like.

In any of the examples herein one or more portions of a memory pool can be marked as associated with a virtual machine instance for purposes of reserving the memory for reuse after reboot. Such marking can be achieved by marking the memory portion e.g. reserved memory pages using a special allocation status e.g. reserved for reboot storing a separate association or the like. Such marking whether by association or other mechanism can be preserved e.g. by the memory manager during reboot of the virtual machine instance.

As described herein an association between the rebooting virtual machine instance and the one or more memory portions allocated to the virtual machine instance can be stored e.g. by a memory manager in a memory pool or the like .

In any of the examples herein the memory manager hypervisor or other mechanism can be configured to detect when a virtual machine instance is about to reboot. For example differentiation between termination without reboot and reboot can be supported. The memory recycling feature described herein can be implemented for those occasions where a reboot is about to take place or is initiated or requested.

In practice reboot requests can be monitored to determine when a reboot process for a virtual machine instance is initiated.

In any of the examples herein the memory manager can support memory ballooning. For example when a virtual machine instance is instantiated a certain amount of memory may be requested e.g. as part of a template or image .

Subsequently during execution ballooning functionality may be used by or for the virtual machine instance to request additional memory beyond that initially allocated. The memory manager can process and grant such a request by allocating additional memory from the memory pool as described herein. Such a request can be external to the virtual machine instance however functionality can be implemented by which a virtual machine instance requests additional memory via ballooning.

In any of the examples herein a control plane management interface can be configured to accept API calls and communicate information to one or more hypervisors responsible for managing execution of virtual machine instances thereby providing the technologies described herein as part of a web service. For example in a scenario where cloud computing is provided as a service users of the service can configure the technologies by specifying parameters in API calls.

The control plane management interface can take the form of a specialized web server of other management software. Although the control plane management interface is shown in examples as residing on the same server machine as the memory manager and virtual machine instances it is possible to implement the control plane management interface on a separate server machine that then communicates to the relevant hypervisor memory manager or the like.

Scrubbing memory can consume considerable resources so avoiding scrubbing in reboot scenarios can greatly increase performance especially for large e.g. high storage platform virtual machine instances.

Memory scrubbing is typically performed on memory after deallocation to prevent information leakage. However dedicated memory pools can be assigned to virtual machine instances. If a memory allocation request is received for a virtual machine memory can be provided from the dedicated memory pool. Even if such memory was previously used and deallocated it can be recycled e.g. provided back to the virtual machine while avoiding scrubbing within the dedicated pool. Such an approach avoids unnecessarily expending resources on scrubbing while still maintaining customer expectations regarding security.

In the example a memory manager executing on a server manages a memory pool for allocation to virtual machine instances A B by managing per VM instance memory sub pools A B and memory cross pool .

The memory sub pools A B can be assigned to e.g. pre allocated for the virtual machine instances. For example if an expected or configured number of virtual machine instances is known the memory pool can be divided among the instances. Associations A B can be maintained between the virtual machine instances A B and their respective dedicated memory sub pools A B.

An amount of memory can be reserved for the cross virtual machine instance pool . Memory in the cross pool is allocable to any of the virtual machine instances. The memory manager can be configured to scrub memory returned to the cross pool . In practice the cross pool need not be explicitly allocated e.g. the memory can simply reside in the memory pool . It is possible that the cross pool becomes of size zero e.g. no cross pool memory remains .

When allocating memory to the virtual machine instances A B the memory manager can use the memory from the respective assigned dedicated sub pools A B. Ballooning or other functionality that deviates from expected allocations can be supported from the memory cross pool . Although scrubbing can ordinarily be performed before allocating memory to a virtual machine instance e.g. before pre allocation scrubbing can be inhibited when memory is allocated e.g. deallocated and reallocated from a dedicated memory sub pool to the same virtual machine instance.

Because a virtual machine instance has memory dedicated to it it is not necessary to scrub between reuse e.g. until the virtual machine instance terminates or is otherwise going away permanently .

The memory manager can store information about the sub pools e.g. size location and the like and the associations between the virtual machine instances A B and the memory sub pools A B e.g. associations A and B .

The memory manager can be implemented as part of a hypervisor that can receive configuration directives from a control plane management interface that receives API calls as part of a web service provided to customers availing themselves of the virtual machine hosting environment. As described herein the API calls can be used to configure the behavior of the memory manager e.g. to enable sub pool creation for a virtual machine instance as described herein .

At dedicated memory pools are assigned for respective of the virtual machine instances. For example as described herein sub pools from a memory pool can be assigned to the virtual machine instances.

At after memory is reclaimed from a given virtual machine instance to a dedicated memory pool for the virtual machine instance it is reallocated to the virtual machine instance e.g. from the dedicated pool without scrubbing.

At before allocating memory reclaimed to the memory pool for cross virtual machine instance use the memory reclaimed to the memory pool for cross virtual machine instance use is scrubbed.

Subsequently for a virtual machine instance having a dedicated memory pool upon termination of the virtual machine instance the dedicated memory pool can be scrubbed.

In any of the examples herein supporting dedicated memory pools a memory pool can be partitioned merged or both.

In a partition scenario a request to partition a memory pool dedicated to a virtual machine instance can be received. Responsive to the request the dedicated memory pool can be partitioned into at least two partitions. One of the partitions can remain dedicated to the virtual machine instance to which it was originally dedicated.

In a merge scenario a request to merge the dedicated memory pool with another dedicated memory pool can be received. Responsive to the request the memory pools can be merged.

Partition and merge functionality can be controlled via API calls to a control plane management interface as described herein.

In any of the examples herein the memory pools e.g. the dedicated sub pools the cross pool or the like can grow e.g. increase size of the pool or shrink e.g. decrease size of the pool as desired to accommodate requests or particular situations. Memory can thus be shifted from one pool to another. For example to grow a dedicated pool memory from the cross pool can be shrunk.

For example when a virtual machine instance reboots the dedicated memory pool can be grown to the present size e.g. immediately before reboot of the virtual machine instance. Such a scenario can be useful in a variety of scenarios such as after a virtual machine instance is subjected to ballooning. Thus memory pool resizing on reboot can be supported.

Memory scrubbing is typically performed on memory after deallocation to prevent information leakage. However memory usage trust groups can be supported for virtual machine instances. If a memory allocation request is received for a virtual machine memory can be recycled e.g. provided while avoiding scrubbing from a deallocation of another virtual machine in the same trust group. Such an approach avoids unnecessarily expending resources on scrubbing while still maintaining customer expectations regarding security. Memory scrubbing can be canceled if scheduled or already begun.

In a server hosts virtual machine instances A N. A memory manager tracks memory allocations e.g. allocations and for the virtual machine instances A N. The memory manager also has access to memory usage trust groups e.g. the trust group which contains VM A and VM B .

As shown in a memory portion out of a memory pool has been allocated to the virtual machine instance A.

Subsequently as shown in the memory portion is deallocated from the virtual machine instance A. Upon deallocation the memory portion can be scheduled for scrubbing.

However as shown in to fulfill a memory allocation request for virtual machine instance B scrubbing can be canceled and the memory portion can be reused and allocated to the virtual machine instance B. The reuse of the memory without scrubbing can be based on the fact that the virtual machine instances are in the same memory usage trust group .

The trust group indicates that the two instances trust each other so it is not necessary to scrub memory that the instances reuse after each other s use.

The feature of reusing memory among trust groups can be called memory usage group stickiness because memory can tend to remain within a particular memory usage group e.g. be reallocated to other instances in the same group .

The memory manager can be incorporated into a hypervisor that accepts configuration directives from a control plane management interface that receives API calls as part of a web service provided to customers availing themselves of the virtual machine hosting environment. As described herein the API calls can be used to configure the behavior of the memory manager e.g. to enable memory usage trust groups as described herein .

At memory is allocated to a first virtual machine instance that is associated with a memory usage trust group.

At a memory request for a second virtual machine instance in the same memory usage trust group as the first virtual machine instance is received.

At responsive to determining that the available e.g. deallocated memory was deallocated from a virtual machine instance in the same memory usage trust group as the requesting instance scrubbing of the deallocated memory is canceled. Canceling can occur after the deallocated memory is partially scrubbed.

At a request for memory for a virtual machine associated with a memory usage trust group is received.

At unallocated memory that is at least partially unscrubbed after deallocation from another virtual machine instance associated with the same memory usage trust group is identified.

Reusing memory within memory usage trust groups can be extended to a reboot scenario. For example when memory is deallocated during reboot of a virtual machine instance if a memory allocation request is received from an instance in the same trust group the memory can be allocated to the requesting instance.

In any of the examples herein a plurality of virtual machine instances can be designated as belonging to a same memory usage trust group. In practice the memory usage trust group can be subsumed by a larger designation such as a security partition a generic trust group or the like.

Although a customer identifier can be used as a trust group customers may wish to have finer grained control over trust groups e.g. for processing performed on behalf of different internal users who do not share a trust relationship .

To facilitate management and configuration of the features described herein a memory allocation policy can be implemented. is a block diagram of an example memory allocation policy .

Such a policy can be implemented as a data structure XML or other mechanism that can be stored configured and duplicated. The policy can be associated with individual instances customers users trust groups or the like. Such association can cause the policy to be applied to covered virtual machine instances e.g. the explicitly specified instance or instances associated with a customer user trust group or the like .

Although other implementations are possible many of the values e.g. enable memory policy value force new memory value recycle memory on reboot value allow recycle within dedicated pool value and recycle within trust group value can take the form of Boolean values e.g. yes no 0 1 or the like .

In the example an enable memory policy value indicates whether or not any memory re use e.g. without scrubbing is to be implemented. For whatever reason it may be desired not to use the memory re use features described herein. If so the policy can be disabled via the value e.g. by setting the value to false or the like .

Another value for forcing new memory can be implemented to support forcing memory allocations to different memory rather than re using e.g. whether or not the memory is scrubbed .

A value can indicate whether memory is to be recycled on reboot without scrubbing as described herein.

A value can indicate whether memory is to be recycled within a dedicated pool without scrubbing as described herein.

A value can indicate whether memory is to be recycled within a trust group as described herein. A memory usage trust group identifier can be specified to indicate in which trust group a virtual machine instance belongs. Such a trust group identifier can be ensured to be unique across customers e.g. instances from two different customers cannot be accidentally or intentionally placed in the same trust group . Other arrangements are possible. For example the trust group identifier can be set to a special value e.g. nil 0 or the like to specify that recycling within trust groups is not permitted.

API calls to a control plane management interface can direct a memory policy manager to alter the memory policy for a particular virtual machine instance customer user trust group or the like as described herein.

In any of the examples herein inhibition of or avoiding scrubbing can comprise canceling memory scrubbing if scheduled or already begun.

In any of the examples herein API calls can be used to control the implementation of the various memory recycling technologies described herein. For example an API call can specify a virtual machine instance trust group customer user or the like and indicate which features are to be implemented and how. A memory policy as described herein can be created manipulated and applied via such API calls.

Such API calls can be received by a server from a control component that is operated by the environment provider or a customer of the environment.

An API call can support per virtual machine instance configuration. For example the API call can comprise a parameter specifying the virtual machine instance. Features such as memory reuse without scrubbing after reboot and the like can thus be controlled via the API calls. Example options are shown in Table 1.

The API call options can be specified in a separate data structure e.g. policy that is referenced in the API call or the parameters can be specified in the API call itself.

In some cases a series of API calls can be used to set up configuration before the virtual machine is instantiated. Such API calls can set up configuration so that a virtual machine instance has the specified configuration at instantiation time. Alternatively some options can be specified after the instance has been instantiated.

In any of the examples herein rather than repeatedly specifying parameters a security template can be created named and reused for subsequent configurations. For example a particular customer may wish to specify a certain set of features in a security policy for a set of virtual machine instances. The template can be applied e.g. via API calls to such instances.

By way of background the service center i.e. the cloud provider is capable of delivery of computing and storage capacity as a service to a community of end recipients. Generally speaking the service center can provide the following models Infrastructure as a Service Platform as a Service and or Software as a Service SaaS . Other models can be provided.

For the IaaS model the service center can offer computers as physical or virtual machines and other resources. The virtual machines can be run as guests by a hypervisor as described herein. The PaaS model delivers a computing platform that can include an operating system programming language execution environment database and web server. Application developers can develop and run their software solutions on the service center platform without the cost of buying and managing the underlying hardware and software. The SaaS model allows installation and operation of application software in the service center.

In some embodiments end users access the service center using networked client devices such as desktop computers laptops tablets smartphones etc. running web browsers or other lightweight client applications. The service center can be described as a cloud environment.

The particular illustrated service center includes a plurality of server computers A D. While only four server computers are shown any number can be used and large centers can include thousands of server computers. The server computers can include memory one or more processors and other hardware typically associated with a computing system. The server computers A D can provide computing resources for executing software instances A D. In one embodiment the instances A D are virtual machines.

A virtual machine is an instance of a software implementation of a machine i.e. a computer that executes applications like a physical machine. In the example of virtual machines the servers A D can be configured to execute an instance manager capable of executing the instances. The instance manager can be a hypervisor or another type of program configured to enable the execution of multiple instances A D on a single server. Additionally any single one of the instances A D can be configured to execute one or more applications.

Although the embodiments disclosed herein are described primarily in the context of virtual machines other types of instances can be utilized with the concepts and technologies disclosed herein. For instance the technologies disclosed herein can be utilized with storage resources data communications resources and with other types of computing resources. The embodiments disclosed herein might also execute all or a portion of an application directly on a computer system without utilizing virtual machine instances.

A server computer can be reserved for executing software components for managing the operation of the server computers A D and the instances A D. For example the server computer can execute a management component . A customer can access the management component to configure various aspects of the operation of the instances A D purchased by the customer. For example the customer can purchase rent or lease instances and make changes to the configuration of the instances. The customer can also specify settings regarding how the purchased instances are to be scaled in response to demand. An auto scaling component can scale the instances based upon rules defined by the customer. In one embodiment the auto scaling component allows a customer to specify scale up rules for use in determining when new instances should be instantiated and scale down rules for use in determining when existing instances should be terminated. The auto scaling component can comprise a number of subcomponents executing on different server computers A D or other computing devices. The auto scaling component can monitor available computing resources over an internal management network and modify resources available based on need.

A deployment component can be used to assist customers in the deployment of new instances of computing resources. The deployment component can have access to account information associated with the instances such as who is the owner of the account credit card information country of the owner etc. The deployment component can receive a configuration from a customer that includes data describing how new instances should be configured. For example the configuration can specify one or more applications to be installed in new instances provide scripts and or other types of code to be executed for configuring new instances provide cache logic specifying how an application cache should be prepared and other types of information. The deployment component can utilize the customer provided configuration and cache logic to configure prime and launch new instances . The configuration cache logic and other information may be specified by a customer using the management component or by providing this information directly to the deployment component .

The deployment component can receive an API call for launching a new instance and use an identifier associated therewith to determine a VM registration record which can be stored in a database on a server computer etc. The VM registration record can include a VM image configuration and metadata configuration information . The deployment component can then use the VM registration record to launch a VM.

A network can be utilized to interconnect the server computers A D and the server computer . The network can be a local area network LAN and can be connected to a Wide Area Network WAN so that end users can access the service center . The network topology illustrated in has been simplified any other type of network arrangement or networking devices can be utilized to interconnect the various computing systems disclosed herein.

Although the operations of some of the disclosed methods are described in a particular sequential order for convenient presentation it should be understood that this manner of description encompasses rearrangement unless a particular ordering is required by specific language set forth below. For example operations described sequentially may in some cases be rearranged or performed concurrently. Moreover for the sake of simplicity the attached figures may not show the various ways in which the disclosed methods can be used in conjunction with other methods.

Any of the disclosed methods can be implemented as computer executable instructions stored on one or more computer readable storage media e.g. non transitory computer readable media such as one or more optical media discs volatile memory components such as DRAM or SRAM or nonvolatile memory components such as flash memory or hard drives and executed on a computer. As should be readily understood the term computer readable storage media does not include communication connections such as modulated data signals.

The computing systems described herein can take the form of any of a variety of general purpose or dedicated computer based hardware that includes memory multi processor systems multi computer systems and the like.

For clarity only certain selected aspects of the software based implementations are described. Other details that are well known in the art are omitted. For example it should be understood that the disclosed technology is not limited to any specific computer language or program. For instance the disclosed technology can be implemented by software written in C Java Perl JavaScript or any other suitable programming language. Likewise the disclosed technology is not limited to any particular computer or type of hardware. Certain details of suitable computers and hardware are well known and need not be set forth in detail in this disclosure.

It should also be well understood that any functionality described herein can be performed at least in part by one or more hardware logic components instead of software. For example and without limitation illustrative types of hardware logic components that can be used include Field programmable Gate Arrays FPGAs Program specific Integrated Circuits ASICs Program specific Standard Products ASSPs System on a chip systems SOCs Complex Programmable Logic Devices CPLDs etc.

Furthermore any of the software based embodiments comprising for example computer executable instructions for causing a computer to perform any of the disclosed methods can be uploaded downloaded or remotely accessed through a suitable communication means. Such suitable communication means include for example the Internet the World Wide Web an Intranet software applications cable including fiber optic cable magnetic communications electromagnetic communications including RF microwave and infrared communications electronic communications or other such communication means.

Any of the computer readable media herein can be non transitory e.g. volatile memory such as DRAM or SRAM nonvolatile memory such as magnetic storage optical storage or the like and or tangible. Any of the storing actions described herein can be implemented by storing in one or more computer readable media e.g. computer readable storage media or other tangible media . Any of the items e.g. data created and used during implementation described as stored can be stored in one or more computer readable media e.g. computer readable storage media or other tangible media . Computer readable media can be limited to implementations not consisting of a signal.

Any of the methods described herein can be implemented by computer executable instructions in e.g. stored on encoded on or the like one or more computer readable media e.g. computer readable storage media or other tangible media or one or more computer readable storage devices e.g. memory magnetic storage optical storage or the like . Such instructions can cause a computing device to perform the method. The technologies described herein can be implemented in a variety of programming languages.

The disclosed methods apparatus and systems should not be construed as limiting in any way. Instead the present disclosure is directed toward all novel and nonobvious features and aspects of the various disclosed embodiments alone and in various combinations and subcombinations with one another. The disclosed methods apparatus and systems are not limited to any specific aspect or feature or combination thereof nor do the disclosed embodiments require that any one or more specific advantages be present or problems be solved.

The technologies from any example can be combined with the technologies described in any one or more of the other examples. In view of the many possible embodiments to which the principles of the disclosed invention may be applied it should be recognized that the illustrated embodiments are only preferred examples of the invention and should not be taken as limiting the scope of the invention. Rather the scope of the invention is defined by the following claims. We therefore claim as our invention all that comes within the scope of these claims.

