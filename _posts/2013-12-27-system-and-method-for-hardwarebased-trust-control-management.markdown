---

title: System and method for hardware-based trust control management
abstract: A trust control management method for security, operable on a computer system generates a unique Trust ID value by combining user-defined values with hardware-specific values associated with the user's computer system and storing the Trust ID value in a memory register physically associated with the hardware of the computer system. A Trust Control Suite (TCS) operable with a server OS/hypervisor maintains a database of user-defined values and hardware-specific values for computer systems clustered in a trusted computing pool. An attestation procedure is performed by the trust control server combining the user-defined values with the hardware-specific values from its database and comparing it to the user-stored Trust ID value stored in the memory register associated with a user's computer system. Depending on whether it is a match or mismatch, the TCS can determine if it is a trusted computer or not, and can take appropriate alerts and policy actions.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09258331&OS=09258331&RS=09258331
owner: Trapezoid, Inc.
number: 09258331
owner_city: Miami
owner_country: US
publication_date: 20131227
---
Shared cloud computing technologies are designed to be very agile and flexible transparently using available resources to process workloads for their customers. However there are security and privacy concerns with not knowing the integrity identity and location of the physical devices that make up a cloud platform and allowing unrestricted workload migration among the servers that comprise an unverified cloud platform and across such unverified cloud platforms. Whenever multiple workloads are present on a multi server cloud platform there is a need to segregate those workloads from each other so that they do not interfere with each other gain access to each other s sensitive data or otherwise compromise the security or privacy of the workloads. Imagine two rival companies with workloads on the same cloud platform each company would want to ensure that the servers housing their workloads are trusted to protect their information from the other company as well as any other unauthorized access.

Another concern with shared cloud computing is that workloads could move from servers in a cloud platform located in one country to servers in a cloud platform located in another country. Each country has its own laws for data security privacy and other aspects of information technology IT . Because the requirements of these laws may conflict with an organization s policies or mandates e.g. laws regulations an organization may decide that it needs to restrict which cloud platform it uses based on its specific location. A common desire is to only use cloud platform with servers physically located within the same country as the organization.

Forming trusted computing pools is a leading approach to aggregate trusted systems and segregate them from untrusted resources. This allows for the separation of higher value more sensitive workloads from commodity applications and data. The principles of operation are to 1 Create a cloud platform to meet the specific and varying security requirements of users 2 Control access to that cloud platform so that only the right applications get deployed there and 3 Enable audits of the cloud platform so that users can verify compliance.

Such trusted computing pools allow IT to gain the benefits of the dynamic cloud environment while still enforcing higher levels of protections for their more critical workloads. The ultimate goal is to be able to use trusted verification and identification methodologies for deploying and migrating cloud workloads between and among trusted servers within a cloud platform. Current thinking has identified certain prerequisite steps which can be thought of as staged requirements that a trusted cloud platform solution must meet 

Platform Attestation and Safe Hypervisor Launch This stage attempts to ensure that the cloud workloads are run on trusted servers within the cloud platform. The cloud platform includes servers each with a hardware configuration e.g. BIOS settings and a hypervisor configuration. The hypervisor operates directly on the hardware not on top of another operating system thus it is imperative to show that the hypervisor has not been compromised and that it is the designated version and configuration. Before the server is used for workloads its trustworthiness must be verified measured . The items configured in the BIOS and hypervisor need to have their configurations verified before launching the hypervisor to ensure that the assumed level of trust is in place.

Trust Based Homogeneous Secure Migration Once the integrity of the cloud platform is established the next stage requires that cloud workloads are able to be migrated among homogeneous trusted server platforms within a cloud environment.

Trust Based and Geolocation Based Homogeneous Secure Migration This stage allows cloud workloads to be migrated among homogeneous trusted server platforms within a cloud environment taking into consideration geolocation restrictions.

Achieving all three levels of control will not prevent attacks from succeeding but unauthorized changes to the hypervisor or BIOS can be detected and launch of enforcement actions can be taken. These controls also facilitate compliance with security and governance policies thus limiting damage to the information being processed or accessed within the cloud computing server.

However the current approach to forming trusted computing pools by ensuring safe hypervisor launches and monitoring attestation of cloud server platforms has the deficiency that the conventional hypervisor management tools are software based and run from a platform server virtually connected to remote client computers.

An example of a trust management technology for forming trusted computing pools is provided by Intel Trusted Execution Technology TXT . TXT implements a foundation for establishing a Transitive Chain of Trust TCoT that is rooted in hardware. Each module within the chain has an opportunity to examine and measure the next module prior to that module s execution. The resulting Integrity Measurements IM are stored in shielded locations within a Trusted Platform Module TPM . By using a secure communication method via the process of Remote Attestation a third party can later request the Ns as evidence and proof that the BIOS and Operating System meet standards and thus are trusted.

In addition TXT provides a method for introducing a user defined value into the chain of evidence by storing that value in a specific secured NVRAM index with the TPM. The current art is to write the identical user defined value into the TPM NVRAM index of a group of servers to designate a logical grouping or pool. Common terms for this method are Geotag Geolocation and Geofence because historically the first user defined values used in demonstrating this capability were geographic in nature. In a current implementation of this process a country code or Geotag is encrypted using a SHA1 function and the resulting Geotag value is stored in the TPM NVRAM index e.g. SHA1 USA . During the boot process the Trusted Boot TBOOT module that initializes the BIOS uses a TPM EXTEND function to Extend the TPM NVRAM index Geotag value into Platform Configuration Register PCR . To validate the Geotag the value in PCR is compared with an externally maintained lookup table.

However the value placed into the TPM NVRAM index could be any arbitrary value because the lookup table only validates against the resulting PCR value. The validation confirms that PCR LookupHash GeoTag but does not validate that Extend PCR SHA1 Geotag LookupHash Geotag . The PCR Extend operation is not part of the validation.

There are drawbacks with deploying a homogeneous Geotag value across a number of server platforms within a Geofence. First the fact that the value can be read by a virtual request to scan the value written in PCR raises the concern that it could be spoofed. In addition a bad actor could introduce a rogue machine into the Geofence that displays the expected PCR Geotag value. A less nefarious but nonetheless important issue is the inability of the common Geotag to tie specific virtual machines to unique physical platform hosts from an evidentiary and forensics perspective. What is needed is a more robust and foolproof way of ensuring that Geotag of a trusted virtual machine cannot be spoofed.

Finally TXT includes an additional mechanism termed Launch Control Policy LCP which allows the Platform Supplier the manufacturer and the Platform Owner customer each to specify requirements for a Secure Operating System Launch. The LCP policies contain specifications of valid Platform Configurations PCONF policy Operating System Versions Measured Launch Environment or MLE policy and Authenticated Code Module ACM versions SINIT policy . The LCP values are protected using features of the TPM and are compared against measured PCR and ACM values to determine Platform and Operating System trust. LCP provides a go no go mechanism for Secure Operating System Launch as well as providing enhanced protection against reset attacks and the ability to restrict access to specific TPM keys data and resources.

Creating a Launch Control Policy can be a complex process and challenging to maintain. Given that the LCP process is a binary go no go function it can also be difficult to determine the root cause of LCP failures because the resulting inability to achieve Secure OS Launch is always the same. Moreover depending on implementation not all parts of LCP are included as part of the TCoT measurements therefore it is possible for LCP to change and not impact the TCoT measurements.

In accordance with the present invention a trust control management method for security in cloud computing operable on a computer system comprises 

generating a unique encoded alphanumeric value Trust ID value by combining a set of alphanumeric values defined by a user of the computer system with a set of other alphanumeric values associated with specific physical hardware embodied with the user s computer system using an encoding algorithm 

maintaining in a database the user defined values associated with the user s computer system together with a list of the types of physical hardware specific values associated with the user s computer system that are to be retrieved the user s computer system and combined with the user defined values and the encoding algorithm and

performing an attestation procedure via a trust control application by combining the user defined values retrieved from the database with the selected physical hardware specific values retrieved from the user s computer system using the same trust encoding algorithm retrieved from the database that was used to encode the original Trust ID value stored in the hardware of the user s computer system 

comparing the Trust ID value obtained in the attestation procedure with the original Trust ID value stored in the hardware of the user s computer system and upon a match determining that the user s computer system is a trusted computer system or failure to match determining that the user s computer system is not a trusted computer system then taking an appropriate security action by the trust control application.

The method of generating and comparing the newly encoded Trust ID value with the original user stored Trust ID value provides more robust and foolproof verification of the trust status of the user s computer system by encoding both user defined values and hardware specific values and storing the originally encoded Trust ID value in the hardware of the user s computer system.

The user defined data may include a value associated with the geographical location where the user s computer system is to be deployed in order to define its grouping with the trusted computing pool associated with that geolocation.

The hardware specific values may include values associated with a given version of firmware BIOS ROM or other embedded code collectively firmware present on the hardware.

The creation of the Trust ID value may be carried out without the knowledge of the person storing the Trust ID value on the user s computer hardware as a precaution against security penetration and spoofing.

Other objects features and advantages of the present invention will be explained in the following detailed description with reference to the appended drawings.

In the following detailed description certain preferred embodiments are described as illustrations of the invention in specific resource applications communication networks and or computer implemented services or application environments in order to provide a thorough understanding of the present invention. Common methods procedures components or functions for such applications networks and or services or environments which are commonly known to persons of ordinary skill in the field of the invention are not described in detail so as not to unnecessarily obscure a concise description of the present invention. Certain specific embodiments or examples are given for purposes of illustration only and it will be recognized by one skilled in the art that the present invention may be practiced in other analogous applications or environments and or with other analogous or equivalent variations of the illustrative embodiments.

The computer implemented services or application environments in the detailed description which follows may be presented in terms of certain procedures steps logic blocks processing and other symbolic representations of functional operations implemented on a computer device by a computer program operable on data bits stored within a computer memory. These descriptions and representations are intended to be understood by those skilled in the data processing arts. A program procedure computer executed step logic block process etc. is described as a self consistent sequence of steps or instructions leading to a desired end result such as providing a tangible computer output such as an alarm status indicator or data display or implemented by computer to result in physical manipulations of physical quantities or materials. Usually though not necessarily such tangible computer implemented output may take the form of electrical outputs or signals capable of being displayed stored transferred combined compared and otherwise manipulated in a computer system.

It should be borne in mind however that all of these and similar terms are to be associated with the appropriate physical quantities and are merely convenient labels applied to these quantities. Unless specifically stated otherwise as apparent from the following descriptions terms such as processing or computing or translating or calculating or determining or displaying or recognizing or the like refer to the action and processes of a computer system or analogous electronic computing device that manipulates and transforms data represented as physical electronic quantities within the computer system s registers and memories into other data similarly represented as physical quantities within the computer system memories or registers or other such information storage transmission or display devices.

A computer or computing resource commonly includes one or more input devices electronically coupled to a processor for executing one or more computer programs for producing an intended computing output. The computer is typically connected as a computing resource and or communications device on a network with other computer systems. The networked computer systems may be of different types such as remote PCs master servers network servers and mobile client devices connected via a wired wireless or mobile communications network.

The term Internet refers to a structure of global networks connecting a universe of users via common or industry standard protocols. Users having a connection to the Internet commonly use browsers on their computers or client devices to connect to websites maintained on web servers that provide informational content or business processes to users. The Internet can also be connected to other networks using different data handling protocols through a gateway or system interface such as wireless gateways to connect Internet websites to wireless data networks. Wireless data networks are deployed worldwide and allow users anywhere to connect to the Internet via wireless data devices.

 Attestation The process of vouching for the accuracy of information. External entities can attest to shielded locations protected capabilities and Roots of Trust. A platform can attest to its description of platform characteristics that affect the integrity trustworthiness of a platform. Both forms of attestation require reliable evidence of the attesting entity.

 Authenticated Code Module ACM a digitally signed module validated by the processor before execution.

 Attestation Service AS a service procedure for attestation of a trusted launch of a computer platform grouped in a trusted computing pool.

 Basic Input Output System BIOS a set of computer instructions in firmware that control input and output operations.

 Core Root of Trust for Measurement CRTM The instructions executed by the platform when it acts as the RTM.

 Dynamic Chain of Trust DCoT A set of Transitive Trust Integrity Measurements that starts on request by the operating system via a special processor instruction.

 GRC Governance risk management and compliance or GRC is the umbrella term covering an organization s approach across the areas of Governance risk management and compliance.

 Integrity Measurement IM Values that are the results of measurements on the integrity of the platform. Also referred to as Trust Measurement 

 ISV An independent software vendor company specializing in making or selling software designed for mass or niche markets.

 OS An operating system OS is a collection of software that manages a computer s hardware resources and provides common services for computer programs.

 Hypervisor A hypervisor or virtual machine monitor VMM is a piece of computer software firmware or hardware that creates and runs virtual machines. A computer on which a hypervisor is running one or more virtual machines is defined as a host machine. Each virtual machine is called a guest machine. The hypervisor presents the guest OS with a virtual operating platform and manages the execution of the guest operating systems. Multiple instances of a variety of OSs may share the virtualized hardware resources.

 Platform Configuration Register PCR A shielded location within a TPM containing a digest of integrity digests.

 Policy Management The process of enforcing the rules and regulations policies of an organization that pertain to information and computing.

 Remote Attestation means for one system to make reliable statements about the software it is running to another system.

 Root of Trust RoT In a TXT environment the component microprocessor which serves as the trusted component that begins the measurements necessary to establish a chain of trust.

 Root of Trust for Measurement RTM A computing engine capable of making inherently reliable integrity measurements. Typically the normal platform computing engine controlled by the CRTM. This is the root of the chain of transitive trust.

 SIEM Security Information and Event Management SIEM is a term for software and products services combining security information management SIM and security event manager SEM . SIEM technology provides real time analysis of security alerts generated by network hardware and applications.

 Static Chain of Trust SCoT A set of Transitive Trust Integrity Measurements that start when the platform powers on.

 Transitive Chain of Trust TCoT The full set of Integrity Measurements including the Static Chain of Trust and Dynamic Chain of Trust.

 Transitive Trust Also known as Inductive Trust in this process the Root of Trust gives a trustworthy description of a second group of functions. Based on this description an interested entity can determine the trust it is to place in this second group of functions. If the interested entity determines that the trust level of the second group of functions is acceptable the trust boundary is extended from the Root of Trust to include the second group of functions. In this case the process can be iterated. The second group of functions can give a trustworthy description of the third group of functions etc. Transitive trust is used to provide a trustworthy description of platform characteristics and also to prove that non migratable keys are non migratable.

 Trust Aware Proxy A proxy server is a server a computer system or an application that acts as an intermediary for requests from clients devices seeking resources from other servers. A Trust Aware Proxy is a proxy server that is aware of the integrity and identity of the computer systems to which the Trust Aware Server is connecting.

 Trust Aware App A software application that is aware of the integrity and identity of the computer system that is running the specific application.

 Trust Control Suite TCS a suite of trust control management tools to establish a measured trusted environment within a trusted computing pool and to carry out policies to protect the security of the trusted computing pool.

 Trusted Execution Technology TXT is the name of a computer hardware technology whose primary goals are a Attestation attest to the authenticity of a platform and its operating system OS b assure that an authentic OS starts in a trusted environment and thus can be considered a trusted OS c provide the trusted OS with additional security capabilities not available to an unproven OS.

 Trusted Platform Module TPM A hardware device implementing the functions defined in the TCG Trusted Platform Module Specification

 User an individual user business entity public sector agency and or service provider to such entity or agency using a specific computer system.

In a preferred embodiment in accordance with the present invention the trust control management system and method provides a processor based tamper resistant environment that compares user defined values and hardware specific values such as firmware BIOS and or operating system values to compute a Trust ID value and compare it to a previously computed and stored known good Trust ID value to establish a that a computer system is operating in a measured trusted state within a trusted computing pool. If integrity and trust are not verified the trust control management suite identifies that the system is not behaving as expected and follows the proper embedded policy or policies to protect the computer system and or the trusted computing pool to remediate the problem.

Because the TXT launch can evaluate and report on platform integrity using attestation mechanisms it can provide valuable insights and controls when used in the context of cloud computing platforms. This allows other key software hypervisor cloud orchestration and management and security policy applications to understand and use platform integrity attributes to control workloads and data and better address security risks by keeping sensitive or regulated workloads separate from platforms with unknown integrity status.

In order to have attestation of a trusted launch of a computer platform grouped in a trusted computing pool two key questions that an inquiring entity should have answered are 

1. How would the entity needing this attestation information know if a specific computer platform has performed a secure launch 

2. Why should the entity requesting the attestation information believe the response from the attested computer platform 

Attestation is the process of providing a digital signature of a set of platform configuration registers PCRs a set of registers in a TPM that are extended with specific measurements for various launch modules of the software and having the requestor validate the signature and the PCR contents. The entity wishing to validate the values in the TPM requests these using the TPM Quote command. This command specifies an Attestation Identity Key to perform a digital signature of the quote and a NONCE to ensure freshness of the digital signature. The entity that challenged this information from the TPM can now make a determination about the trust of the platform by comparing the measurements contained in the TPM quote with known good or golden measurements.

The disadvantages of the software only Whitelist are that the whitelist values are ONLY recorded in software and are potentially subject to invalid updates corruption or alteration it employs multiple Attestation Service components the OS Hypervisor or Hypervisor Manager are intermediaries between the TPM and the AS and successful attestation may not match actual intended values for a specific device. Managing the known good values for different hypervisors operating systems and BIOS software versions and ensuring they are protected from tampering and spoofing is a critical IT operations challenge. This capability can be internal to a company managed by a service provider or delivered remotely as a service by a trusted third party.

If the resulting Trust ID matches the reported Trust ID then implicitly all of the original device specific Seed Values from the device and the User specific Seed Values from the Database must match and furthermore the Trust ID was created using the Sequence stored in the Database. If the resulting Trust ID does not match the reported Trust ID then at least one Seed Value has changed or an incorrect Trust ID has been provisioned on the subject device either of which implicitly breach the trust of the subject device.

It is understood that many modifications and variations may be devised given the above description of the principles of the invention. It is intended that all such modifications and variations be considered as within the spirit and scope of this invention as defined in the following claims. For example a Trust ID can include other Trust IDs as Seed Values and can serve as multiple Attestation points. Furthermore the Trust ID can be used in systems to provide additional evidence as to the source nature and timeline of the cause.

