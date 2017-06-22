---

title: Method of, and apparatus for, layout rectification of erasure encoded storage systems
abstract: There is provided a method of recovering configuration metadata from an erasure encoded RAID array. The RAID array includes raw data including a plurality of codewords encoded using Reed-Solomon encoding. The codewords include message data and checksum data, and the configuration metadata includes parameters relating to the layout of the RAID array. The method includes reading, from the RAID array, raw data including message data and checksum data. Then a set of linear equations are defined using the message data and checksum data. The linear equations are then solved and then, from the solved linear equations, one or more parameters relating to the layout of the RAID array are determined.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09405623&OS=09405623&RS=09405623
owner: Xyratex Technology Limited
number: 09405623
owner_city: Havant
owner_country: GB
publication_date: 20130925
---
The present invention relates to a method of and apparatus for layout rectification of erasure encoded storage systems. More particularly the present invention to a method of and apparatus for layout rectification of Reed Solomon erasure encoded storage systems

Performance and data integrity are core requirements for modern storage systems. The ability to prevent and if necessary identify and correct data errors and corruptions is essential for operation of storage systems ranging from a simple hard disk drive up to large mainframe storage arrays.

One approach to improve the reliability and performance of a hard disk drive storage system is to employ redundant arrays of inexpensive disks RAID also referred to as redundant arrats of independent disks . RAID arrays are the primary storage architecture for large networked computer storage systems.

The RAID architecture was first disclosed in A Case for Redundant Arrays of Inexpensive Disks RAID Patterson Gibson and Katz University of California Berkeley . RAID architecture combines multiple small inexpensive disk drives into an array of disk drives that yields performance exceeding that of a single large drive.

There are a number of different RAID architectures designated as RAID 1 through RAID . Each architecture offers disk fault tolerance and offers different trade offs in terms of features and performance. In addition to the different architectures a non redundant array of disk drives is referred to as a RAID 0 array. RAID controllers provide data integrity through redundant data mechanisms high speed through streamlined algorithms and accessibility to stored data for users and administrators.

RAID architecture provides data redundancy in two basic forms mirroring RAID 1 and parity RAID 3 4 5 and 6 . RAID 3 4 5 or 6 architectures generally utilise three or more disks of identical capacity. RAID 5 and 6 architectures are particularly popular and comprise distributed parity architectures in which the data and parity data are interleaved across the disks.

Data interleaving across the disks is usually in the form of data striping in which the data to be stored is broken down into stripe groups comprising a plurality of blocks called stripe units . The stripe units are then distributed across the disks.

Therefore should one of the disks in a RAID group fail or become corrupted the missing data can be recreated from the data on the other disks. The data may be reconstructed through the use of the redundant stripe units stored on the remaining disks.

As shown in data is stored on the RAID 6 array in the form of stripe groups comprising stripe units. Each stripe group A B comprises five separate stripe units stripe A comprises stripes A A A Aand A. Stripe B comprises stripe units B B B Band B. Therefore the stripe units comprising each stripe A A or B B respectively are distributed across a plurality of disk drives together with parity information Aand Aand Band Brespectively. This provides data redundancy.

As shown in each stripe unit in a stripe group is mapped to a different storage component in the array as a contiguous chunk of data. To map each stripe unit to a disk storage component creates two desirable properties. Firstly most common I O workloads can be parallelized across the storage components forming the RAID array . Secondly should a storage component fail only one stripe unit in a stripe group will affected aiding recovery.

Some stripe units in a stripe group will store data whereas others will store redundancy checksum parity information. Further some implementations may reserve stripe units as distributed spare space inside of the RAID array for the purpose of accelerated recovery from storage component failure.

The arrangement format parameters and configuration of the particular stripe units across the drives of a RAID array is known as the layout. The layout may include non exhaustively RAID array configuration parameters such as information on the distribution of particular stripe groups the number and size of the stripe units within those stripe groups the size of the checksum symbols etc.

A number of rules exist which place certain bounds on the layout of a RAID array. One example of this is known as the layout goodness criteria as set out in PhD thesis M. C. Holland Carnegie Mellon University 1994 .

How the data and parity information stripe units are distributed across the drives in an array is a function of the particular RAID software and is known as the unit mapping strategy. There are numerous strategies for how to layout data. In many cases the layout is selected to eliminate areas of particularly high activity on the array hotspots and maximise performance of the array.

The layout of a RAID array is stored as configuration metadata. The configuration metadata is as can be appreciated critical to operation of the RAID array. If the configuration metadata is lost or corrupted the geometry of an array and its various attributes are then unknown rendering the RAID array unusable. Configuration metadata may be lost for a number of reasons. An administrator error may cause the configuration metadata to be overwritten. Alternatively a software error may be responsible.

However irrespective of the cause few robust methods of recovery are known. Recovery of a layout when configuration metadata is lost is problematic and to date no coherent solution exists. It is possible for a skilled RAID expert to handcraft a solution to configuration recovery from clues left in logs fragments on disk and intuition. However this is highly situation and operator skill dependent.

More formal approaches to recovery from such catastrophic failures use for example probabilistic methods to attempt to recover key aspect of the configuration metadata. However these tools are not widely discussed in the literature and have no guarantee of success.

Therefore known storage systems suffer from a technical problem that known methods of recovering a layout of a RAID array when configuration metadata is lost are insufficiently accurate robust or successful. The present invention is in embodiments directed to methods of recovery and further approaches to RAID array configuration that make such recovery more straightforward to help protect against data loss and corruption.

According to a first aspect of the present invention there is provided a method for recovering configuration metadata from an erasure encoded RAID array the RAID array comprising raw data comprising a plurality of codewords encoded using Reed Solomon encoding said codewords including message data and checksum data comprising a plurality of checksums and said configuration metadata comprising parameters relating to the layout of said RAID array the method comprising a reading from said RAID array raw data comprising message data and checksum data b defining on a computing device a set of linear equations using said message data and checksum data c solving on a computing device said set of linear equations d determining from said solved linear equations one or more parameters relating to the layout of said RAID array.

By providing such a method array configuration parameters can be recovered after configuration metadata is lost. Storage component membership order stripe group size stripe unit size and unit mapping functions are example array parameters which can be recovered or otherwise obtained to assist in rectification. Minimum assumptions are made about a lost configuration although available knowledge can help to guide the recovery process.

In one embodiment wherein step b comprises forming a matrix equation based on said set of linear equations said matrix equation comprising a matrix based on said raw data step c comprises inverting said matrix to obtain a set of coefficients and step d comprises utilizing said coefficients to obtain one or more parameters relating to the layout of said RAID array.

In one embodiment said one or more parameters relating to the layout of said RAID array comprises a checksum basis vector used to generate one of said checksums comprising said checksum data.

In one embodiment the method further comprises subsequent to step c e verifying the or each checksum basis vector using a geometric series.

In one embodiment the method further comprises repeating steps b to d to generate further checksum basis vectors for further checksums each checksum basis vector being used to generate one of said checksums. A codeword comprises the message data and all checksums together. The checksum basis vector is the set of coefficients used to generate a single checksum. Each checksum basis vector is recovered turn one for each checksum. This enables important parameters of the configuration metadata to be recovered.

In one embodiment the RAID array comprises a plurality of stripe groups each stripe group comprising a plurality of stripe units and said one or more parameters relating to the layout of said RAID array comprises the stripe unit size and the method further comprises f iterating through said codewords to identify a change in codeword permutation and g identifying the stripe unit size based on said change in codeword permutation.

In one embodiment said one or more parameters relating to the layout of said RAID array comprises the unit mapping strategy and the method further comprising h obtaining said unit mapping strategy based on said plurality of checksum basis vectors and said stripe unit size by i recovering the position of said stripe units within an array from said checksum basis vectors and j repeating step i for multiple sequential stripe groups to obtain the unit mapping strategy.

In one embodiment said one or more parameters relating to the layout of said RAID array comprise the stripe group width the number of message data units per stripe the number of checksum data units per stripe and the symbol size and wherein said parameters are determined empirically prior to step a .

In one embodiment the method further comprises subsequent to step d k rebuilding said configuration metadata from the one or more determined parameters relating to the layout of said RAID array.

In one embodiment the method further comprises subsequent to step k l verifying data consistency across the entire RAID array.

In one embodiment the step of verifying data consistency across the entire RAID array comprises performing a parity check on the raw data on the RAID array.

In one embodiment the method further comprises subsequent to step l m bringing the RAID array online with said rebuilt configuration metadata.

According to a second aspect of the present invention there is provided a RAID hardware controller operable to recover configuration metadata from an erasure encoded RAID array the controller being operable to carry out the steps of the first aspect.

According to a third aspect of the present invention there is provided a storage apparatus comprising at least one storage device and the controller of the second aspect.

According to a fourth aspect of the present invention there is provided a non transitory computer usable storage medium having stored thereon a computer program product executable by a programmable processing apparatus comprising one or more software portions for performing a method according to the first aspect.

According to a fifth aspect of the present invention there is provided a method of encoding data in an erasure encoded RAID array to facilitate recovery in the event of the loss of configuration metadata the method comprising a utilizing Reed Solomon encoding to encode message data and an array unique identifier to form a codeword comprising message data and checksum information comprising a plurality of checksums b writing said codeword to said RAID array wherein in step a said basis root is greater than one for all checksums.

In one embodiment step a further comprises c translating said message data using a involutary function to generate translated message data and translated checksum information and step b further comprises d writing untranslated message data to said RAID array and e writing translated checksum data to said RAID array.

According to a sixth aspect of the present invention there is provided a method of encoding data in an erasure encoded RAID array to facilitate recovery in the event of the loss of configuration metadata the method comprising a utilizing Reed Solomon encoding to encode message data to form a codeword comprising message data and checksum information comprising a plurality of checksums b translating said message data using an involuntary function to generate translated message data and translated checksum information c writing untranslated message data to said RAID array and d writing translated checksum data to said RAID array.

According to a seventh aspect of the present invention there is provided a method of encoding data in an erasure encoded RAID array to facilitate recovery in the event of the loss of configuration metadata the method comprising a utilizing Reed Solomon encoding to encode message data to form a codeword comprising message data and checksum information comprising a plurality of checksums said message data being encoded using a w bit basis root for the basis vector for the or each checksum said w bit basis root storing configuration parameters for said RAID array and b writing said codeword to said RAID array.

By providing such a method a w bit Galois field element can be encoded into the encoded data such that the w bit Galois field element serves as the basis root for the basis vector. Further the w bit Galois field element is selected so that each of the w bits represents configuration parameters. Therefore when the basis root is recovered so are those configuration parameters. This aids in recovery of the layout.

In one embodiment said w bit basis root for the basis vector comprises one or more configuration parameters selected from the list of CRC field number of checksums per stripe group stripe number array number and a first row of the unit mapping identifier.

The host is connected to the RAID controller through a communication network such as an Ethernet and the RAID controller is in turn connected to the storage devices via a storage network such as an iSCSI network.

The host comprises a general purpose computer PC which is operated by a user and which has access to the storage resource . A graphical user interface GUI is run on the host . The GUI is a software application which acts as a user interface for a user of the host .

The RAID controller comprises a software application layer an operating system and RAID controller hardware . The software application layer comprises software applications including the algorithms and logic necessary for the initialisation and run time operation of the RAID controller . The software application layer includes software functional blocks such as a system manager for fault management task scheduling and power management. The software application layer also receives commands from the host e.g. assigning new volumes read write commands and executes those commands. Commands that cannot be processed because of lack of space available for example are returned as error messages to the user of the host .

The operation of the RAID controller may be set at the Application Programming Interface API level. Typically Original Equipment Manufactures OEMs provide RAID networks to end users for network storage. OEMs generally customise a RAID network and tune the network performance through an API.

The operating system utilises an industry standard software platform such as for example Linux upon which the software applications forming part of the software application layer can run. The operating system comprises a file system which enables the RAID controller to store and transfer files and interprets the data stored on the primary and secondary drives into for example files and directories for use by the operating system .

The RAID controller hardware is the physical processor platform of the RAID controller that executes the software applications in the software application layer . The RAID controller hardware comprises a microprocessor memory and all other electronic devices necessary for RAID control of the storage devices 

The storage devices may take any suitable form for example tape drives disk drives non volatile memory or solid state devices. Although most RAID architectures use hard disk drives as the main storage devices it will be clear to the person skilled in the art that the embodiments described herein apply to any type of suitable storage device. More than one drive may form a storage device for example a RAID array of drives may form a single storage device . The skilled person will be readily aware that the above features of the present embodiment could be implemented in a variety of suitable configurations and arrangements.

As set out above the term storage device in the context of the following description may refer to a logical drive which is formed on the RAID array . In this case a sector refers to a portion of the logical drive created on the RAID array . The following embodiment of the present invention is applicable to any of the above described arrangements.

In this embodiment the storage devices are formatted such that each sector comprises 512 bytes 4096 bits . The term sector used herein is generally applicable to any sector sizes. Therefore the term sector is merely intended to indicate a portion of the storage availability on a storage device and is not intended to be limited to any of the disclosed examples. Additionally sector may be used to refer to a portion of a logical drive i.e. a virtual drive created from a plurality of physical hard drives linked together in a RAID configuration.

Further whilst only a single server and RAID array is shown in any number of RAID controllers may be provided to serve any number of storage devices forming an array.

The RAID controller stores configuration metadata for the RAID array . This denotes the configuration of data storage on the RAID array as described above. The present invention is concerned with a situation where such metadata is lost corrupted or maliciously destroyed and there is insufficient knowledge to manually restore the configuration. These parameters need to be recovered to enable to the RAID array to function.

These parameters need to be recovered from the raw data in the RAID array when the configuration metadata is lost. Recovery becomes even more important when an administrator has no backup of the data on the array. In general if the configuration metadata is lost the data remaining on the RAID array is still likely to be valid and can be recovered. However care must be taken in this regard. An administrator error during recovery for example to redefine the RAID array in the wrong disk order or with the wrong unit size can permanently destroy the data on the RAID array .

As set out above without the RAID array configuration parameters as specified in the configuration metadata the RAID array comprises entirely raw data the format and or configuration of which is unknown. The recovery of the array configuration parameters from the raw data on the RAID array is known as layout rectification. Layout rectification attempts to recover the parameters which are required to restore an array to a functional state. These may include for example storage component membership position information stripe group width stripe unit size etc.

As is well known the RAID level of an array in part describes the level of protection afforded against storage component failures. For example RAID 5 arrays can only survive a single failure or corruption within a stripe whereas RAID 6 arrays can survive two failures or corruptions within the same stripe.

In some cases the RAID level also defines how checksum data is calculated. RAID 5 implements XOR based parity. However RAID 6 can be implemented with a greater variety of codes. For example an EVENODD code or an RDP code may be used. Combinations are possible with the P parity of RAID 6 being calculated from XOR and the Q parity being calculated from a Reed Solomon RS code.

The present invention is operable in one aspect to enable more accurate and reliable layout rectification for Reed Solomon RS erasure encoded RAID arrays. In another aspect the present invention provides an improved method of encoding an RS code to create a configuration aware code to facilitate layout rectification. This substantially increases the probability of a successful recovery.

 Erasures within RAID array systems are defined as detected data losses such as complete device failures or latent sector errors. They do not include for example silent data corruption. An erasure code is an error correcting code that extends message data with checksum data in a way that known lost or erased data can be recovered from the available remaining data. One especially popular code is the RS erasure code.

The operation of an RS code is to transform inputted user data known as message data into a codeword. Each codeword is a vector comprising a plurality of symbols where each symbol is of w bit width where w is any positive integer having a value greater than 2 .

An RS code specifically comprises a linear code of the format n k d . Where the code comprises n symbols of w bit width. Of those n symbols k symbols comprise message data and m where m n k symbols comprise checksum data. D is the minimum Hamming distance between any two valid codewords. In other words at least D symbols in a codeword must be modified to generate another valid codeword. In general when the number of erasures is less than d then the original codeword can be determined from the remaining symbols. In a RAID 6 array D 3. Therefore any combination of two erasures can be tolerated by the system.

Reed Solomon codes are non binary cyclic codes with symbols made up of w bit symbols. Reed Solomon codes on w bit symbols exist for all n and k for which 0and 2 1 

The codeword is the combination of message and checksum symbols together. All of the w bit words at the same offset within each stripe unit in a stripe group is equivalent to the codeword.

When applied to RAID n is the stripe group width i.e. the number of stripe units per stripe group k is the number of data or message stripe units per stripe group and m is number of parity or checksum stripe units per stripe group.

The size of the stripe group in storage terms is then a function of the stripe unit size and the number of stripe units per group n. However the stripe unit size is usually selected to be a multiple of w so that a plurality of codewords can be stored within a single stripe. For instance given a stripe unit size of 4 KiB and symbol size w of 16 bits each stripe unit comprises 2048 codewords. Further each symbol in the codeword is stored on a different stripe unit so that when any unit is lost only one symbol from the codeword is lost.

RS arithmetic is carried out inside of a Galois field denoted as GF 2 . In order to transform a message into a codeword a generator matrix G is required as set out in expression 2 2 where Iis the k k identity matrix and P is a k m matrix. Row vector c is an n component codeword and row vector D is the k component message data. A specific codeword c is generated from message data such that equation 3 3 

The final m components of c are the checksum symbols and these are generated with P. Elements of P must be selected carefully so that its column rank is m. In doing so P is often defined to be a submatrix of the Vandermonde matrix as set out in expression 4 

Given that the RS approach to RAID only requires checksum data the set of linear equations can be expressed more concisely as 5 

In other words the RS checksum data is the result of a linear equation. For instance taking expression 6 in longhand format Q parity on a RAID 6 array is encoded as 2 2 2 . . . 2 7 Q and dthrough d are all stored on the disks comprising the array . However without analysis it cannot be determined which information is parity information and which is message data. The present invention addresses amongst other things this matter.

Nevertheless the encoding coefficients are a geometric series and the power of each coefficient x relates to the position of data in the code. Therefore to recover the position of data and parity in the code is equivalent to recovering the coefficients which can be performed in one embodiment using linear algebra.

By way of brief overview of the present method it is possible to define a set of k linear equations treating the checksum coefficients as unknown quantities. This produces a matrix of the raw data D on the array multiplied against a set of unknown coefficients u resulting in a vector of raw data d. So D u d. To obtain the coefficients the raw data matrix can be inverted and left multiplied such that u Dd.

The first embodiment of the present invention provides a method for recovering the configuration metadata based on an analysis of the above RS approach. shows a flow chart of a method according to the first embodiment.

At step the recovery system is initialised. The recovery system may comprise a software application run on the storage system e.g. as a software application run on the operating system . Alternatively and non exhaustively the recovery system may be run from a remote server or from hardware or firmware.

The recovery system is operable to read and analyse raw data on a RAID array and to determine key parameters of the configuration metadata. Assuming the entire configuration metadata of a RAID array has been lost the following parameters need to recovered 

To simplify the process a number of assumptions can be made to place constraints on the rectification process. This reduces the amount of computation required.

Firstly it can be assumed that the RAID array starts at the same offset on each storage component in the RAID array .

It can also be assumed that the symbols of a specific codeword are mapped to the same offset within each storage component .

Finally it can be assumed that the symbol size w is fixed across the whole RAID array implementation.

These assumptions are not essential and are to be taken as non limiting. However they provide a mechanism to reduce the search space and reduce the complexity of the operation and the time required to complete the operation.

The present method relates to the determination of configuration parameters in the case of n storage components when it is known that they comprise part of a single RAID array as shown in .

In general n k and m are also known without needing to analyse the array data in detail. This is because these parameters are general and known at initialisation or the array . Therefore the following steps of the analysis can focus on the remaining parameters as set out in step .

Equation 5 above defines checksum data to be the inner product of message data D and a geometric progression of coefficients i.e. the basis vector i i.e. P Expressed differently codeword c is the combined message data and generated checksum data defined as c dG equation 3 .

Both the message data and checksums are stored in the RAID array raw data. However which data is message data and which data is checksum parity data is unknown at this stage. Nevertheless even when the layout parameters remain unknown the structure of the code and how D and c are related is known from the raw data and from the RS coding process as set out above.

In step each basis vector i is recovered in turn by treating its vector components as unknown quantities building a set of linear equations that can solve for these unknown quantities.

The data set comprises k unknowns and so k raw data equations must be stacked. As can be appreciated these equations must come from the same permutation in the unit mapping strategy. However because a specific permutation is repeated stripe unit length times to the end of a stripe group a single sector worth of symbols across each unit will likely yield more equations than is actually needed. Consider for example that when w 16 bits and the storage component sector size is 512 B a single sector contains one symbol from 32 different codewords.

As set out above it is not known which stripe units store message data and which stripe units store checksum data. Therefore each combination of k linear equations taken from the raw data is required to be tested. The basis vector recovery equation is expressed as follows 

Or more concisely 9 where D is the raw data matrix. Each element dis the xsymbol on storage component y and column vector u is a set of unknown coefficients that transforms D into column vector d.

At step it is determined whether the raw matrix data D is invertible. If the raw data matrix D is invertible then the unknown coefficients are recovered using equation 10 . 10 

In the situation where raw data on the left hand side of Equation 10 is message data and the right hand side is checksum data then u is the basis vector.

In step the basis vector determined in step is verified. Whether u is a basis vector can be verified by using a property of geometric series as set out in equation 11 

In a RAID 6 system which has fixed basis roots the right hand side of Equation 12 for each basis root can be computed such that the component summation of u can be directly compared.

A match indicates that a candidate basis root has been identified. Otherwise if a RAID system uses non standard basis roots the component in u that solves Equation 12 is a candidate basis root.

Further in addition to satisfying the constraints of Equation 10 the components of u must form a geometric progression of the candidate basis root.

However there may be rare situations in which random data may generate u that appears to be correct. Therefore it is important that the layout should be empirically validated before the array is brought back online.

Once the basis vectors are recovered one permutation of the unit mapping strategy is also recovered. That is the position of message data in the codeword is related to the exponent of each component in u by log.u

Nevertheless the stripe unit number and unit mapping strategy are still unknown and so the position of storage components in the array cannot be determined until later steps have been carried out.

In many cases the permutation changes at each stripe boundary. For layouts where this is the case the unit size can be recovered by observing the change in permutation at the boundaries.

Therefore in such cases at least one permutation of the unit mapping strategy is learned when the generator matrix G is recovered. However as set out above in relation to step the relationship of the one permutation in the unit mapping strategy to the remaining permutations is still unknown.

Nevertheless this information can be utilised to determine the unit size. This is done by in step iterating forward and backwards through the codewords until a change in the permutation is detected. The difference between these points is then the stripe unit size.

However in some cases the unit size cannot be recovered. If for example the unit mapping strategy only has one permutation e.g. as with dedicated parity then alternative methods must be used.

This is done on a logarithmic basis by searching through the storage components using a binary search. For each iteration of the search the search is continued in that direction if the raw data decodes correctly. Otherwise the direction of the search is switched until the boundaries are determined.

This approach assumes that the entire array is properly encoded and initialised. One problem that may arise is when multiple arrays share the same set of storage components and have a similar layout. In this case the search may cross over one array boundary and not recognize that it is working in a different array space. This may be addressed by the encoding of the second embodiment.

The unit mapping strategy permutes units of a stripe across the member storage components on a per stripe basis. In step this strategy is recovered.

Data encoded into a codeword and permuted can be written as set out in equation 13 13 where is the permutation matrix for stripe s and c is the permuted codeword. Or in other words vector component x in c is mapped to storage component x.

With this formulation the unit mapping strategy can be described as an ordered set of n permutations that are cycled over the stripes. Given permutation set . . . then selects the permutation at stripe i. Alternatively the set of permutations as a matrix is set out in equation 14 

Matrix M then represents the mapping of codeword symbols onto storage components . This is interpreted as the codeword symbol Mis mapped to storage component j when stripe number s mod n i.

This is used in step to construct a permutation from the raw data on the RAID array in part from the candidate basis vectors with log.u. However the checksum symbols also need to be included into the permutation so that the order of message and checksum data with respect to the storage components are preserved in because the position of checksum cis k i.

Consequently if the unit size has been determined in step then the process can proceed to subsequent stripe boundaries recover the basis vectors at each said boundary and the full set of permutations from the raw data can be obtained as set out in equation 15 

After the first stripe in the array is identified its symbol map can be used to identify which row y in Mis the first row of the permutation set. When y is recovered Mis row rotated by y to recover the unit mapping strategy.

In other words the position of stripe units in the array are recovered from the basis vector and then the full mapping strategy is recovered by recovering the basis vectors and thus unit positions from multiple sequential stripes.

Further the storage component order is also recovered with respect to the code. However even though row rotated Mis the unit mapping strategy it may still be necessary to correlate the mapping with a labelled strategy e.g. left symmetric etc . In general data is mapped onto a set of storage components starting at an arbitrary offset in the array using a specific strategy M as follows 16 where R is a row permutation matrix and C is a column permutation matrix. C in essence relates to the order of storage components. R is restricted to being a row rotation matrix since the strategy is applied cyclically over the entire array.

For example define R I because Mis known to sit on a cycle boundary. The column permutation is then recovered with C MMfor the labelled unit mapping strategy whose M results in a true column permutation matrix. However when R is not identity in some cases we can still recover the exact unit mapping strategy by introducing the concept of a unit mapping strategy signature.

Equations 17 and 18 below is an example strategy signature. Row vector s is comprised of n elements where each element in s is based on a column in M. The column is indexed by j not shown in equations 17 and 18 .

Further the row index wraps around at the matrix boundary. This particular example signature accumulates the absolute difference at each transition in a column where the column changes from a message symbol to a checksum symbol between rows and vice versa.

The above approach in step creates a unique signature for each of the four common strategies listed in when m

The above expressions define each element in the signature as belonging to a base n numeral system with transitions acting as digits.

For example consider the left asymmetric strategy signature that is shown in With n 6 the first element is 0 4 n 5 0 n 34.

However this approximation only holds when each signature in the set of all supported strategies is unique. In this case the formulation is also row rotation and column permutation invariant. That is the unit mapping strategy can be named without knowing R or C.

Further when each element in a given signature is unique the column permutation C can be recovered. In Cauchy s two line notation 

Using Equation 20 permutation matrix C can be recovered for element wise unique signatures such as with the left and right asymmetric strategies shown in and . Once C is known the row rotation matrix is then R MCM.

However in the situation where a strategy s signature is not element wise unique we cannot recover C until R is known first. Once R is identified e.g. by finding the first or last stripe then C MRM.

Once the above steps have been carried out the following parameters have been determined from the raw data 

Based on these parameters replacement configuration metadata can be generated and stored. The method then proceeds to step .

As set out above reconfiguring and bringing an array online with an incorrect layout could result in corruption or destruction of the raw data remaining on the array .

Therefore optionally an empirical validation should be carried out on the proposed parameter data to ensure that the data matches the array. This may be by way of a parity check of the remaining data.

At step the validated configuration metadata can be used to bring the array back online. At this point the recovery process is completed. A log may be stored for reference should the configuration metadata become damaged or corrupted at a later stage.

A method according to a second embodiment of the present invention will now be described with reference to .

The method of the first embodiment described above relates to a procedure for recovery of conventional RS encoded RAID array configuration information. However it is possible to modify the coding procedure to enable more accurate and more easily rectifiable code. The second embodiment of the invention implements this.

The second embodiment of the present invention defines modifications to the standard RS code to yield a code which enables more straightforward rectification. The following rectification assisting code is proposed in equations 21 and 22 

The basis for the above strategy will be to provide a data structure that defines important layout configuration parameters and casts these into an element in the field to use in the code as a basis root. Consequently when the coefficients are recovered additional information about the layout is provided. The following description addresses how the various code modifications address issues with rectification.

When the basis root is 1 u resolves to be a vector of ones. Therefore in a conventional RS code it is not possible to determine the position of message symbols from log.u alone.

In the present invention this is done by providing a basis root greater than one for all checksums. However this results in a modification in which the first checksum calculation is no longer a simple XOR summation of the message data. All checksums will require finite field multiplication.

However if there is more than one checksum in the code position information can still be recovered from another non one based checksum. In this case once the positions of the message data are known the one based checksum position can be implied.

The search space however can be reduced by rewriting the checksum equation as set out in equation 23 23 where g is a non zero constant. Now the checksum can be included in the raw data matrix so that the unknown coefficients u are solved with u Dg where g in this context is a constant vector. Building on the same example the search space is significantly reduced from 91 to

Any penalty incurred with this modification is minimal. When encoding the checksum initialisation value is simply changed from zero to g.

A similar issue occurs when trying to recover multiple arrays from a pool of storage components. Suppose for instance there are three k 8 m 2 RAID 6 arrays buried in 30 storage components . To recover a first basis vector yields

However by using a similar approach as for a single array several basis vectors can be recovered simultaneously by building a raw data matrix representing k 1 a equations where a is the number of arrays to recover.

However when the equations are put together they will be rank deficient if all arrays use the same value of g. A geometric progression of values is thus implemented so that each array is assigned a unique identifier and 2 24 where a is the array ID. Continuing on with the previous example the search space is now reduced to

As discussed previously raw data matrix D must be an invertible matrix in order for the proposed method to work. However in reality raw data can be highly repetitious. Consider for example an array that is initialised with a write zeros policy for array consistency initialisation or a software entity that adds padding to its files.

In these situations raw data is not likely to be invertible. Nevertheless this can be avoided by first translating all data in the code. We describe data translation as follows 25 where j is a storage component index and i is an address within the storage component.

In shorthand equation 25 can be written as d with the remaining parameters implied. The translated raw data matrix is denoted as D. Translation function takes data dand transforms said data into using characteristics of storage component j at address i.

We also require that is an involutary function is its own inverse so that d d. For example XOR can be used to create an involutary function e.g. A A B B .

The translation function is required to be predictable repeatable and independent of all configuration parameter characteristics. This independence is required because when data is read from a storage device there is no knowledge of what data is being read i.e. whether the read data is message or checksum data. Consequently it is preferred that the translation function is based only on persistent characteristics of the storage component such as its SCSI logical unit address if applicable.

Message data is translated for the purpose of encoding only and the original unmodified data dis written to storage component j. However for checksum data the translated redundancy information c must be written out to storage. This is necessary because all data must be translated by when building the transformed raw data matrix D. However when data is read from the storage during recovery it is unknown whether the data is message data or checksum information. This means it is necessary to translate all data with the same function.

So by writing c to storage all data read back can be safely translated when the translated data matrix D is built due to c c.

One possible translation function which can be utilised with the present invention is a function which utilises a non cryptographic hash function. A hash value is generated from the storage component s logical unit address and codeword address. Therefore the hash function must exhibit good avalanching properties because the logical unit address may only differ by one between the storage components and because codeword symbol addresses are also sequential. Therefore small changes in the input must produce large changes in the output.

Whilst a hash function is generally associated with a large overhead in this embodiment of the present invention this can be handled very efficiently. The translation function is arranged to minimise the probability of encountering a singular matrix.

Additionally the raw data matrix needs only to stack a minimum set of equations to solve for the unknowns. Therefore the logical address modulo can be taken as an appropriate integer and used as a parameter to the hash function. Therefore the set of hash values for a storage component can be pre computed for a sufficiently small set size.

This can be expanded on and refined. As is known the transition function is merely XOR. Therefore all of the hashes are reduced to a constant value as set out in equations 26 to 29 below 

The equations above illustrate that the hash values can be combined with constant g to form a new constant K at the associated codeword address. Therefore the penalty is only one additional lookup for each codeword into a pre computed table rather than a hash computation for each symbol in the codeword.

Traditionally basis roots are selected in sequential order starting with 1 2 etc. However other coefficients may be used to encode checksum data provided that the generator matrix is invertible.

Therefore basis roots may be used which when recovered yield additional information about the array configuration parameters. One strategy to accomplish this is to create a w bit binary representation of the most critical configuration parameters to enhance recovery. This basis root is denoted A and this appears in the equations 26 to 29 set out above.

The basis root comprises a set of parameters. Firstly the CRC field is included in to provide an additional level of verification in the rare case that random data decodes into a proper geometric series. Further by using a CRC the basis root in u is quickly identified. The basis root also encodes the value of m and so the recovery process can readily determine how many checksums are in a code after the first basis vector is recovered. A checksum index i is also encoded in the basis root to identify which checksum is the basis vector.

Additional parameters can be encoded into the basis root . For example the array number if multiple arrays are present on a storage system the stripe number and the first permutation the first flag .

For example if the unit mapping strategy contains only a single row then the least significant bit of each stripe group number can be used the stripe no field . Since this will cause the basis root to change at stripe monitoring changes while traversing through the raw data will alternatively allow for recovery of the unit size.

When recovering a unit mapping strategy that is ambiguous i.e. one that requires the first row of the permutation matrix to be known to solve Equation 16 then the first flag can be utilised.

Each codeword generated on the first row of the unit map matrix will have the first flag set to one. Otherwise the flag is set to zero. Therefore when the basis root is recovered the RAID software will know whether the data comes from the first row or not. Once the first row is known R is also known and the storage component order C can be recovered.

In case generates a geometric series with a period less than k the selector field allows for various alternative basis roots that encode the same layout parameters.

A problem can also be addressed with regard to array boundaries. A binary search over a storage component to find the first and last stripes of an array can be problematic if multiple arrays exist on the same set of storage components and have a similar layout. However through the use of defining a set of parameters and assigning a unique number to each array the identifier can be encoded into each codeword using the array no field in . Therefore it is clear when the search process has crossed over a boundary into another array.

The array no field also solves the issue of identifying which storage components belong to which arrays when recovering multiple arrays simultaneously. Since the array identifier is built into the basis root of each array is unique. By following the geometric series membership of the storage components can be determined.

Intuitively a larger symbol size will allow more layout information to be encoded into the basis root . For example a w 32 bit code for instance could be implemented using Intel s Streaming SIMD Extension SSE instruction set.

At step the host generates a write request for a specific volume e.g. storage device to which it has been assigned access rights. The request is sent via a communication network to the host ports not shown of the RAID controller . The write command is then stored in a local cache not shown forming part of the RAID controller hardware of the RAID controller .

The RAID controller is programmed to respond to any commands that request write access to the storage device . The RAID controller processes the write request from the host . The method then proceeds to step .

The RAID controller utilises the message data sent in step to generate a codeword in accordance with equations 26 to 29 . In other words the RAID controller utilises the modified Reed Solomon code of the present invention to generate the parity information forming part of the codeword. The codeword comprises the message data plus parity information generated from the message.

During codeword generation message data and checksum data are translated in accordance with the translation function A to generate a translated raw data matrix D.

Once the codeword has been generated the message data part of the codeword i.e. unmodified data d can be written to the storage component j. It is not necessary to write the translated data d to storage.

For checksum data the translated redundancy information c must be written out to storage. This is necessary because all data must be translated by when building the transformed raw data matrix D during decoding of the data.

At step the writing of the data together with parity information is complete. The method may then proceed back to step for further message data or may terminate.

The arrangement of the modified RS code according to the second embodiment of the present invention is used in the same manner as the method of the first embodiment set out above. However the encoding enables a more robust procedure to be carried out when rectifying the RAID array .

In general the method of rectification is similar to that of the first embodiment. However the use of the translated format means that additional modifications are necessary.

When data is read from the storage during recovery it is unknown whether the data is message data or checksum information. This means it is necessary to translate all data with the same function.

As set out above c is written to storage. Therefore when checksum data is read back in step it can be safely translated when the translated data matrix D is built due to c c.

Message data is however not stored in translated format so can be translated back into this format using .

In addition the array constant g can be obtained to provide information on the number and format of the arrays.

The data can then be analysed in accordance with the method of the first embodiment as set out in steps to .

Variations of the above embodiments will be apparent to the skilled person. The precise configuration of hardware and software components may differ and still fall within the scope of the present invention.

For example the present invention has been described with reference to controllers in hardware. However the controllers and or the invention may be implemented in software. This can be done with a dedicated core in a multi core system. Given a proper software algorithm it should be feasible to calculate protection information in parallel with array parity so that each piece of user data is read only once.

Additionally whilst the present embodiment relates to arrangements operating predominantly in off host firmware or software e.g. on the RAID controller an on host arrangement could be used.

Alternatively symbols other than 16 bit symbols could be used. The skilled person would be readily aware of the different symbol sizes that could be used with the present invention.

Embodiments of the present invention have been described with particular reference to the examples illustrated. While specific examples are shown in the drawings and are herein described in detail it should be understood however that the drawings and detailed description are not intended to limit the invention to the particular form disclosed. It will be appreciated that variations and modifications may be made to the examples described within the scope of the present invention.

