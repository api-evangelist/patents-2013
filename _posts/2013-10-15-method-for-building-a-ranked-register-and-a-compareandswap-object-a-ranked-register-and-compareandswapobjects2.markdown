---

title: Method for building a ranked register and a compare-and-swap object, a ranked register and compare-and-swap-objects
abstract: A method is used to build a concurrent data structure in the form of a ranked register based on a Compare-And-Swap (CAS) functionality and an according ranked register, to allow reliable access of shared data within a storage by multiple clients. Read and write operations are defined within the ranked register. The read operation takes a rank as argument and returns a rank-value pair. The write operation takes a rank-value pair as argument and returns either commit or abort. The read operation returns a rank-value pair that was written in a previous write operation.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09652302&OS=09652302&RS=09652302
owner: NEC CORPORATION
number: 09652302
owner_city: Tokyo
owner_country: JP
publication_date: 20131015
---
This application is a U.S. National Phase application under 35 U.S.C. 371 of International Application No. PCT EP2013 071489 filed on Oct. 15 2013 and claims priority to European Patent Application No. EP 12188516.4 filed Oct. 15 2012. The International Application was published in English on Apr. 24 2014 as WO 2014 060393 under PCT Article 21 2 .

The present invention relates to a method for building a concurrent data structure in the form of a ranked register and a compare and swap object for data transactions in distributed data storage.

The present invention further relates to a ranked register and a compare and swap object built for a concurrent data structure for data transactions in distributed data storage.

Thanks to the advent of cloud services distributed databases have benefited from deployments spanning a cluster of machines within a single cloud. In such a setting replication is the advocated solution to achieve data scalability and fault tolerant durability. However entire clouds may fail rendering critical data unavailable which ultimately leads to revenue losses.

With embodiments of this invention the following problem is addressed How can multiple storage clouds or servers be leveraged to enable transactional access to shared data among a large possibly unbounded number of clients despite crashes asynchrony and concurrency 

An increasing number of data serving platform providers such as Amazon and Yahoo have recognized the need for transactional access to shared data in addition to atomic read write. It is possible to construct strong coordination primitives enabling transactional access just from atomic read write operations. However it is known that such constructions do not scale since the space and communication overhead is proportional in the number of clients. Furthermore leaving it to the developer to directly deal with the intricacies of implementing strong data sharing primitives such as read modify write from weaker ones may result in inefficient and or error prone implementations.

As a consequence a number of data serving platforms such as DynamoDB PNUTS and cloud data bases such as Couchbase MongoDB Redis etc. have started including in their APIs coordination abstractions stronger than read write. The most powerful among such primitives is Compare And Swap CAS for it enables implementing any shared functionality in a non blocking manner i.e. without using locks.

Intuitively CAS updates a storage location only if the current value of that location is as expected where the expected value is supplied to CAS along with the new value. Typically CAS is used for optimistic concurrency control as follows 1 a storage location x is read into a local variable v then 2 based on the value of v some local computation is done that changes v and then 3 x is updated with v via CAS. If x didn t change then x takes the new value v. Else x remains unchanged. In that case steps 1 3 are repeated. Used this way CAS enables transactional access to shared data.

For example Gregory Chockler and Dahlia Malkhi. 2002 Active disk paxos with infinitely many processes In Proceedings of the twenty first annual symposium on Principles of distributed computing PODC 02 herein PODC02 illustrate the above data transaction.

A method is used to build a concurrent data structure in the form of a ranked register based on a Compare And Swap CAS functionality and an according ranked register to allow reliable access of shared data within a storage by multiple clients. A read and write operations are defined within the ranked register. The read operation takes a rank as argument and returns a rank value pair. The write operation takes a rank value pair as argument and returns either commit or abort. The read operation returns a rank value pair that was written in a previous write operation.

In an embodiment the present invention relates to a method for building a concurrent data structure in the form of a ranked register RR wherein within the RR two operations rr read and rr write are defined wherein the rr read operation is provided for taking a rank as argument and for returning a rank value pair wherein the rr write operation is provided for taking a rank value pair as argument and for returning either commit or abort and wherein the RR satisfies the following specification 

Safety Every rr read operation returns a rank value pair that was written in some rr write invocation additionally let W rr write r 1 v be a rr write operation that commits and let R rr read r 2 such that r 2 r 1 then R returns r v where r r 1 R sees W wherein v and v are values and wherein r r 2 and r 1 are ranks Non triviality If a rr write operation W invoked with rank r 1 aborts then there exists a rr read or rr write operation with rank r 2 r 1 which is invoked before W returns and Liveness If an operation rr read or rr write is invoked by a non faulty process then it eventually returns.

In an embodiment the present invention also relates to a concurrent data structure in the form of a ranked register RR preferably built by the method according to any one of claims to wherein within the RR two operations rr read and rr write are defined wherein the rr read operation is provided for taking a rank as argument and for returning a rank value pair wherein the rr write operation is provided for taking a rank value pair as argument and for returning either commit or abort and wherein the RR satisfies the following specification 

Safety Every rr read operation returns a rank value pair that was written in some rr write invocation additionally let W rr write r 1 v be a rr write operation that commits and let R rr read r 2 such that r 2 r 1 then R returns r v where r r 1 R sees W wherein v and v are values and wherein r r 2 and r 1 are ranks Non triviality If a rr write operation W invoked with rank r 1 aborts then there exists a rr read or rr write operation with rank r 2 r 1 which is invoked before W returns and Liveness If an operation rr read or rr write is invoked by a non faulty process then it eventually returns.

In an embodiment the present invention further relates to a method for building a Compare And Swap CAS object wherein a concurrent data structure in the form of a ranked register RR is used wherein within the RR two operations rr read and rr write are defined wherein the rr read operation is provided for taking a rank as argument and for returning a rank value pair wherein the rr write operation is provided for taking a rank value pair as argument and for returning either commit or abort and wherein the RR satisfies the following specification 

Safety Every rr read operation returns a rank value pair that was written in some rr write invocation additionally let W rr write r 1 v be a rr write operation that commits and let R rr read r 2 such that r 2 r 1 then R returns r v where r r 1 R sees W wherein v and v are values and wherein r r 2 and r 1 are ranks Non triviality If a rr write operation W invoked with rank r 1 aborts then there exists a rr read or rr write operation with rank r 2 r 1 which is invoked before W returns and Liveness If an operation rr read or rr write is invoked by a non faulty process then it eventually returns wherein increasing versions of values within data objects are stored for ensuring that newer values are never overwritten with older ones.

In an embodiment the present invention even further relates to a Compare And Swap CAS object preferably built by the method according to any one of claims to based on a concurrent data structure in the form of a ranked register RR wherein within the RR two operations rr read and rr write are defined wherein the rr read operation is provided for taking a rank as argument and for returning a rank value pair wherein the rr write operation is provided for taking a rank value pair as argument and for returning either commit or abort and wherein the RR satisfies the following specification 

Safety Every rr read operation returns a rank value pair that was written in some rr write invocation additionally let W rr write r 1 v be a rr write operation that commits and let R rr read r 2 such that r 2 r 1 then R returns r v where r r 1 R sees W wherein v and v are values and wherein r r 2 and r 1 are ranks Non triviality If a rr write operation W invoked with rank r 1 aborts then there exists a rr read or rr write operation with rank r 2 r 1 which is invoked before W returns and Liveness If an operation rr read or rr write is invoked by a non faulty process then it eventually returns wherein increasing versions of values within data objects are stored for ensuring that newer values are never overwritten with older ones.

In an embodiment the present invention even further relates to a method for providing a Compare And Swap CAS object for transactional access to shared data within a storage by multiple clients wherein the storage comprises multiple storage units each of which being accessible via a separate Application Programming Interface API each of which comprising a Compare And Swap CAS primitive wherein an entirety of multiple such storage units is assigned one further API comprising a further Compare And Swap CAS primitive for access by the clients and wherein as the CAS object a CAS object according to claim based on a ranked register according to claim is used so that the CAS object comprises multiple CAS objects in the form of said multiple storage units with their APIs.

In an embodiment the present invention even further relates to a Compare And Swap CAS object for transactional access to shared data within a storage by multiple clients wherein the storage comprises multiple storage units each of which being accessible via a separate Application Programming Interface API each of which comprising a Compare And Swap CAS primitive wherein an entirety of multiple such storage units is assigned one further API comprising a further Compare And Swap CAS primitive for access by the clients and wherein the CAS object is a CAS object according to claim based on a ranked register according to claim so that the CAS object comprises multiple CAS objects in the form of said multiple storage units with their APIs.

In an embodiment the present invention even further relates to a method for providing transactional access to shared data within a storage by multiple clients wherein the storage comprises multiple storage units each of which being accessible via a separate Application Programming Interface API each of which comprising a Compare And Swap CAS primitive wherein an entirety of multiple such storage units is assigned one further API comprising a further Compare And Swap CAS primitive for access by the clients and wherein as a functional connection between the entirety of multiple such storage units and the further API a ranked register is used.

In an embodiment the present invention provides a method for building a concurrent data structure in the form of a ranked register an according ranked register a method for building a CAS object an according CAS object a method for providing a CAS object for transactional access to shared data within a storage by multiple clients an according CAS object for transactional access to shared data within a storage by multiple clients and a method for providing transactional access to shared data within a storage by multiple clients for allowing a very reliable access of shared data within a storage by multiple clients.

According to an embodiment of the invention the method comprises building of the RR based on a Compare And Swap CAS functionality for storing increasing versions of values within data objects for ensuring that newer values are never overwritten with older ones.

According to an embodiment of the invention the concurrent data structure includes the RR based on a Compare And Swap CAS functionality for storing increasing versions of values within data objects for ensuring that newer values are never overwritten with older ones.

According to an embodiment of the invention it has been recognized that it is possible to provide a very reliable access of shared data within a storage by multiple clients when using CAS functionality within the construction of a ranked register. Contrary to the situation within PODC02 the present invention does not require server side code. In contrast CAS supports only update if nothing changed functionality that tests for equality only. Within the inventive method and ranked register a fault tolerant ranked register is constructed from fault prone CAS objects.

Within a preferred embodiment of the invention each base object or data object holds a read rank rR changed only by rr read as well as a value val and a write rank wR changed only by rr write wherein the designation CAS r and CAS w is used to distinguish CAS invocations by rr read and rr write respectively.

Within a further preferred embodiment of the invention an rr read operation R with rank r attempts to change the read rank of a majority of base objects or data objects to r wherein at the same time R accumulates the values returned.

Within a further preferred embodiment of the invention R tries to update a data object only if the current rank rR is lower than r ensuring that ranks are monotonically increasing.

Within a further preferred embodiment of the invention once a majority of base objects or data objects hold a rank either rW or rR greater or equal to r R returns the rank value pair with the highest write rank wR among the values or accumulated values.

Within a further preferred embodiment of the invention an rr write operation W with rank value pair r v attempts to update a majority of data objects with r v wherein W tries to update a data object x only if the current ranks both rR and wR of x are not higher than r wherein if W commits then it has successfully updated a majority of data objects with r v else if W is not able to update x and some of the ranks either rR or wR is higher than r then W aborts.

With the method for building a CAS object according to an embodiment of the invention it is possible to construct an obstruction free CAS object from a ranked register.

Within a further preferred embodiment of the invention a client picks a rank r and first fetches the current value V using rr read r next it checks if V.val equals an expected value exp and if yes it attempts to update V with r new using rr write else if V.val differs from exp the client attempts to update V with r v i.e. only the rank is changed.

Within a further preferred embodiment of the invention if the operation aborts the steps are repeated with a higher rank.

Within a further preferred embodiment of the invention for increasing the chances of solo runs of clients a concurrency management is used.

Within a further preferred embodiment of the invention the concurrency management comprises exponential back off or leader election where all clients throw their CAS operations into a global set and a particular client i.e. the leader linearizes all operations in the set.

Within a further preferred embodiment of the invention an extended CAS object is implemented that aborts whenever the underlying rr write operation aborts wherein contention resolution would then be handled by an invoking application.

Within a further preferred embodiment of the invention a method provides a CAS object for transactional access to shared data within a storage by multiple clients. The CAS object is based on a ranked register according to claim . As a result the crash tolerant CAS object is provided from a set of crash prone CAS objects in the form of the storage units while supporting an unbounded number of crash prone clients with constant space.

Within a further preferred embodiment of the invention a method provides transactional access to shared data within a storage by multiple clients. Under consideration of a storage with multiple storage units a Compare And Swap API is build on top of an entirety of at least some of said storage units.

Within a further preferred embodiment of the invention the ranked register is a ranked register according to an embodiment of the invention.

Within a further preferred embodiment of the invention the storage units can be storage clouds or storage servers which can be provided within a data center.

On the basis of the present invention ranked registers can be leveraged in the construction of fault tolerant CAS objects from fault prone CAS objects. Further a fault tolerant ranked register can be constructed from fault prone CAS objects. Moreover a CAS object can be constructed from a ranked register.

The present invention builds entirely on the specification of CAS and does not require running customized server side code as in PODC02 . Our method leverages existing APIs without requiring any change in the server.

According to embodiments of the present invention a method and a system for transactional data sharing in a multi cloud or multi storage setting can be provided. Embodiments of the present invention leverage the Compare And Swap API provided by existing data serving platforms such as Yahoo PNUTS Amazon DynamoDB Couchbase etc. to build a Compare And Swap API on top of multiple such storage clouds. The present construction tolerates the crash of up to a minority of storage clouds i.e. optimal resilience and supports arbitrary many clients with constant space. Unlike PODC02 the present solution does not require server side code.

Embodiments of the present invention describe a method and system of implementing a crash tolerant CAS object from a set of crash prone CAS objects while supporting an unbounded number of crash prone clients with constant space. Specifically for each high level CAS object client view a single low level CAS object is required per server see . Concretely each CAS object like for example DynamoDB Couchbase or MongoDB comprises the objects x x . . . which are accessible for the clients from their CAS API from above within . The software for using the access functionality could only be provided at the client. Such a software can contact all single clouds or storages.

The present invention is related to Active Disk Paxos PODC02 which introduces the abstraction of the Ranked Register RR to capture the safety property of Consensus safety here means decision on a single value. The authors of PODC02 present a crash tolerant construction of a RR from a set of crash prone Read Modify Write RMW objects. Unlike CAS that is a generic reusable functionality readily available in cloud data stores e.g. DynamoDB Couchbase MongoDB etc. a RMW object requires customized server side code which is quite different from our setting see in which individual storages have a well defined API.

A correct construction of a RR requires that servers store monotonically increasing versions which ensures that newer values are never overwritten with older ones. This property is enforced in PODC02 by specialized RMW functionality executed in the server that compares versions to determine the highest one. In contrast CAS supports only update if nothing changed functionality that tests for equality only turning the construction of a RR into a challenging task.

Together a b yield the first obstruction free construction of CAS from a set of crash prone or fault prone CASs.

It is important to note that the results a and b are interesting in their own right. For instance in combination with PODC02 the result b yields fault tolerant constructions of arbitrary atomic objects.

From PODC02 is obtainable a detailed description of a construction of a ranked register. This explanation and further details and facts which are important for the present invention are explicitly included in this application by reference. In the following a summary of a ranked register and CAS functionality is provided.

A ranked register is a concurrent data structure with two methods rr read and rr write. The rr read method takes a rank i.e. monotonically increasing timestamp as argument and returns a rank value pair. The rr write method takes a rank value pair as argument and returns either commit or abort. A ranked register needs to satisfy the following specification as defined in PODC02 

Safety Every rr read operation returns a rank value pair that was written in some rr write invocation. Additionally let W rr write r 1 v be a rr write operation that commits and let R rr read r 2 such that r 2 r 1. Then R returns r v where r r 1 R sees W .

Intuitively safety demands that a rr read operation doesn t miss any rr write with a lower rank than itself.

Non triviality If a rr write operation W invoked with rank r 1 aborts then there exists a rr read or rr write operation with rank r 2 r 1 which is invoked before W returns.

Intuitively non triviality stipulates that rr write operations are allowed to abort only because of concurrency. Note that the spec does not rule out that crashed clients cause aborts but any sensible implementation needs to prevent such a scenario.

Liveness If an operation rr read or rr write is invoked by a non faulty process then it eventually returns.

A compare and swap object C supports a single operation called CAS and stores a scalar value over some domain V. The operation CAS exp new for exp new V induces the following state transition of the compare and swap object. If C s value is exp C s value is changed to new otherwise C s value remains unchanged. In any case the operation returns C s old value.

The idea is illustrated in left. V is a tuple V rank val . A client picks a rank r and first fetches the current value V using rr read r . Next it checks if V.val equals the expected value exp and if yes it attempts to update V with r new using rr write. Else if V.val differs from exp the client attempts to update V with r v i.e. only the rank is changed. If the operation aborts the steps are repeated with a higher rank. The operation returns when rr write commits. The construction is obstruction free i.e. termination is guaranteed when the client invoking CAS eventually runs solo. To increase the chances of solo runs exponential back off is used.

A viable alternative to exponential back off is leader election where all clients throw their CAS operations into a global set and a particular client i.e. the leader linearizes all operations in the set. Another alternative is to implement an extended CAS object that aborts whenever the underlying rr write operation aborts. Contention resolution would then be handled by the invoking application.

The construction in is correct to the extent that it is atomic and that it satisfies the sequential specification of CAS Definition. Furthermore it is obstruction free.

If the code is run sequentially it is easy to see that our construction is obstruction free and that it abides the sequential specification of CAS Definition. Now assume that two clients c i and c j run concurrently and that both return committing with rank r i and r j respectively. Let CAS i and CAS j be the instances invoked by c i and c j respectively. It can be shown that if r i

Furthermore if a client eventually runs solo then it picks a rank which is higher than any other rank used so far in which case the rr write operation commits and the client returns from the CAS invocation.

Finally the READ operation on the right side of is added for completeness since CAS is typically used as part of a first read then write pattern. Since CAS is executed with equal parameters here the initial value nothing is changed.

The idea is illustrated in . Each base object holds a read rank rR changed only by rr read as well as a value val and write rank wR changed only by rr write. CAS r CAS w are used to distinguish CAS invocations by rr read rr write respectively.

An rr read operation R with rank r attempts to change the read rank of a majority of base objects to r. At the same time R accumulates the values returned. R tries to update an object only if the current rank rR is lower than r ensuring that ranks are monotonically increasing. Once a majority of base objects hold a rank either rW or rR greater or equal to r R returns the rank value pair with the highest write rank wR among the accumulated values.

An rr write operation W with rank value pair r v attempts to update a majority of objects with r v . W tries to update an object x only if the current ranks both rR and wR of x are not higher than r. If W commits then it has successfully updated a majority of objects with r v . Else if W is not able to update x and some of the ranks either rR or wR is higher than r then W aborts.

R rr read r 2 such that r 2 r 1. It can be argued that R returns r v where r r 1 thus satisfying Safety. Let O w and O r be the sets of based objects accessed by W and R respectively. Let k O w O r. Let CAS r and CAS w be the last operation on x k by R and W respectively. If CAS r is sequenced before CAS w then CAS w returns a rank higher than r 1 at least r 2 . Since CAS w is invoked with rank at most r 1 the value returned by CAS w does not match the expected value and W would abort contradicting our assumption. Otherwise if CAS w is sequenced before CAS r CAS r would assign to x k a value with rank r 1 or higher and consequently R would return a rank value pair with rank r r 1 as needed.

In addition to the multi cloud setting our method is useful in a single datacenter setting with multiple storage units as well. For instance it enables building data centric coordination on top of fault prone storage servers within a data center. Since all our solution needs is a generic CAS interface full customization of the controller logic as in PODC02 is not required and the interface can be reused by several applications.

Many modifications and other embodiments of the invention set forth herein will come to mind the one skilled in the art to which the invention pertains having the benefit of the teachings presented in the foregoing description and the associated drawings. Therefore it is to be understood that the invention is not to be limited to the specific embodiments disclosed and that modifications and other embodiments are intended to be included within the scope of the appended claims. Although specific terms are employed herein they are used in a generic and descriptive sense only and not for purposes of limitation.

While the invention has been illustrated and described in detail in the drawings and foregoing description such illustration and description are to be considered illustrative or exemplary and not restrictive. It will be understood that changes and modifications may be made by those of ordinary skill within the scope of the following claims. In particular the present invention covers further embodiments with any combination of features from different embodiments described above and below. Additionally statements made herein characterizing the invention refer to an embodiment of the invention and not necessarily all embodiments.

The terms used in the claims should be construed to have the broadest reasonable interpretation consistent with the foregoing description. For example the use of the article a or the in introducing an element should not be interpreted as being exclusive of a plurality of elements. Likewise the recitation of or should be interpreted as being inclusive such that the recitation of A or B is not exclusive of A and B unless it is clear from the context or the foregoing description that only one of A and B is intended. Further the recitation of at least one of A B and C should be interpreted as one or more of a group of elements consisting of A B and C and should not be interpreted as requiring at least one of each of the listed elements A B and C regardless of whether A B and C are related as categories or otherwise. Moreover the recitation of A B and or C or at least one of A B or C should be interpreted as including any singular entity from the listed elements e.g. A any subset from the listed elements e.g. A and B or the entire list of elements A B and C.

