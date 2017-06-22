---

title: ECC polar coding and list decoding methods and codecs
abstract: A method of decoding data encoded with a polar code and devices that encode data with a polar code. A received word of polar encoded data is decoded following several distinct decoding paths to generate a list of codeword candidates. The decoding paths are successively duplicated and selectively pruned to generate a list of potential decoding paths. A single decoding path among the list of potential decoding paths is selected as the output and a single candidate codeword is thereby identified. In another preferred embodiment, the polar encoded data includes redundancy values in its unfrozen bits. The redundancy values aid the selection of the single decoding path. A preferred device of the invention is a cellular network device, (e.g., a handset) that conducts decoding in accordance with the methods of the invention.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09503126&OS=09503126&RS=09503126
owner: The Regents of the University of California
number: 09503126
owner_city: Oakland
owner_country: US
publication_date: 20130710
---
The application claims priority under 35 U.S.C. 119 from prior provisional application Ser. No. 61 670 381 which was filed Jul. 11 2012 which application is incorporated by reference herein.

This invention was made with government support under CCF 1116820 awarded by National Science Foundation. The government has certain rights in the invention.

A field of the invention is information coding and decoding. The invention is particularly useful for communication over noisy mediums. Example applications of the invention include communications such as wireless communications including e.g. cellular communications satellite communications and deep space communications and data storage such as used in data storage devices e.g. computer hard disk devices .

Error correcting codes are used whenever communication over ag noisy medium channel takes place. Cell phones computer hard disks deep space communication and many other devices communicate over a noisy medium. Error correcting codes have been widely used and improved since 1948 as the search for optimal error correcting codes continued for decades. The basic problem in decoding is attempting to recover an original transmitted codeword from a received word that is a distorted version of the original codeword. The distortion is introduced by the noisy medium.

Polar codes were introduced in 2009. See E. Arikan Channel Polarization A method for Constructing Capacity Achieving Codes for Symmetric Binary Input Memoryless Channels IEEE Trans. Inform. Theory vol. 55 pp. 3051 3073 2009 E. Arikan and E. Telatar On the Rate of Channel Polarization in Proc. IEEE Int l Symp. Inform. Theory Seoul South Korea pp. 1493 1495 2009 

Polar codes were the first and presently remain the only family of codes known to have an explicit construction no ensemble to pick from and efficient encoding and decoding algorithms while also being capacity achieving over binary input symmetric memoryless channels. . A drawback of existing polar codes to date is disappointing performance for short to moderate block lengths. Polar codes have not been widely implemented despite recognized inherent advantages over other coding schemes such as turbo codes because channel polarization remains slow in prior methods.

List decoding was introduced in the 1950s. See P. Elias List decoding for noisy channels Technical Report 335 Research Laboratory of Electronics MIT 1957 . List decoding addresses a worst case scenario by outputting a small number of codewords that are a small distance from the code word. List decoding has not been widely used however. Modern applications of list decoding have sought to reduce worst case decoding penalties. Successive cancellation list decoding has been applied in to Reed Muller codes. See I. Dumer and K. Shabunov Soft decision Decoding of Reed Muller codes Recursive Lists IEEE Trans. Inform. Theory vol. 52 pp. 1260 1266 2006 . Reed Muller codes are structured differently than polar codes and are widely considered in the art to have a different decoding approach. Indeed Arikan s original paper that presented polar codes emphasized differences between polar codes and Reed Muller codes. Phrasing of the decoding algorithms in Reed Muller and Polar codes makes comparison difficult. The present inventors recognized that Arikan s successive cancellation decoding is similar in nature to the successive cancellation decoding of Reed Muller codes as in Dumer Shabnov. However application of successive list decoding as set forth in Dumer Shavanov would increase complexity of polar decoding to an extent that would make its application impractical. The successive cancellation list decoding in Dumer Shabunov is also complex and can lead to L n complexity. As with prior list decoders it will also fail to produce a single output instead producing a small list of candidates without a single explicit codeword.

The observation that one can reduce the space complexity of successive cancellation decoders for polar codes with hardware architectures to O n was noted in the context of VLSI design by the present inventors and colleagues in C. Leroux I. Tal A. Vardy and W. J. Gross Hardware Architectures for Successive Cancellation Decoding of Polar Codes rXiv 1011.2919v1 2010 . This paper does not provide a different decoding approach for polar codes but provides architectures that can reduce the space complexity for the decoding scheme that was provided by Arikan with the introduction of polar codes.

An embodiment of the invention is a method of decoding data encoded with a polar code. A received word of polar encoded data is decoded following several distinct decoding paths to generate codeword candidates. The decoding paths are selectively successively duplicated and pruned to generate a list of potential decoding paths. A single decoding path among the list of potential decoding paths is selected as the output and a single candidate codeword is identified as the output. In another preferred embodiment the polar encoded data includes redundancy data in its unfrozen bits. The redundancy data aids the selection of the single decoding path. A preferred device of the invention is a cellular network device e.g. a handset that conducts decoding in according with the methods of the invention.

The present inventors have recognized that drawbacks in polar codes at short to medium block lengths arises from inherent weaknesses of the code itself at these lengths or from the fact that the successive cancellation SC decoder employed to decode them is significantly degraded with respect to maximum likelihood ML decoding performance. These two possibilities are complementary and so both may occur.

Disclosed are methods and their computer implementation that greatly improve the error correcting performance of polar codes. Polar codes are a family of error correcting codes that facilitate the transfer of information from a transmitter to a receiver over a noisy medium e.g. as happens in cell phones computer hard disks deep space communication etc . The invention employs a new decoding method for polar codes as well as a modification of the codes themselves. The method has been fully implemented and tested. The resulting performance is better than the current state of the art in error correction coding.

Preferred embodiments of the invention also provide a modified polar code and decoding method. In prior polar coding methods on the transmitting end encoding a sequence of K information bits are mapped to a codeword of length n. In the preferred embodiment k information bits and r CRC cyclic redundancy check bits together constitute the K k r bits mapped to a codeword of length n. These bits are denoted as u 1 u 2 . . . u K. On the receiving end decoding instead of first decoding u 1 to either 0 or 1 then decoding u 2 to either 0 or 1 and so forth what occurs is as follows. When decoding u 1 both the option of it being a 0 and the option of it being a 1 are considered. These two options are termed paths . For each such path both options of u 2 lead to 4 paths and so forth.

An aspect of the invention provides an improvement to the SC decoder namely a successive cancellation list SCL decoder. The list decoder has a corresponding list size L and setting L 1 results in the classic SC decoder. While lists are used in the decoder when the algorithm executes the decoder returns a single codeword. L is an integer parameter that can be freely chosen by a system designer. L 1 indicates the classic successive cancellation decoding or Arikan . Higher values of L lead to better performance and higher complexity. In HI examples used to test the invention the highest value of L is 32 but much higher values are possible extending into tens of thousands. In embodiments of the invention L is the number of different decoding paths after pruning. After duplication that value is 2 L. In preferred embodiments the pruning reduces the number of paths from 2 L to L.

Embodiments of the invention also include encoders and decoders for ECC error corrected coded polar code communications. A preferred embodiment decoder uses a theory that duplicates data structures used by a parent path each time a decoding path spits into two forks. Each fork receives a copy. The complexity of making actual copies can grow the cost of copying quickly. To avoid this and provide reduced copying expense namely at each given stage the same array may be flagged as belonging to more than one decoding path. However when a given decoding path needs access to an array it is sharing with another path a copy is made.

Embodiments of the invention also include polar concatenated codes executed by computer hardware and or software that aid the decoding. Instead of setting all unfrozen bits to information bits to transmit a following concatenation is applied. For some small constant r embodiments of the invention set the first k r unfrozen bits to information bits. The last r unfrozen bits will hold the r bit CRC cyclic redundancy code value of the first k r unfrozen bits. This provides a reasonable penalty rate of k r n. During decoding the concantenation provides a shortcut to refine selection. A path for which the CRC is invalid can not correspond to the transmitted codeword. Thus the selection can be refined as follows. If at least one path has a correct CRC then remove from the list all paths having incorrect CRC and then choose the most likely path. Otherwise select the most likely path in the hope of reducing the number of bits in error but with the knowledge that at least one bit is in error.

Artisans will appreciate that preferred embodiments of the invention efficiently decode polar codes by generating a list of candidate codewords with successive cancellation decoding. In preferred embodiments a codeword is selected from the list using an outer CRC coded polar code provided by the invention.

In a preferred list decoder of the invention up to L decoding paths are considered concurrently at each decoding stage. Simulation results show that the resulting performance is very close to that of a maximum likelihood decoder even for moderate values of L. The present list decoder effectively bridges the gap between successive cancellation and maximum likelihood decoding of polar codes. The specific list decoding algorithm that achieves this performance doubles the number of decoding paths at each decoding step and then uses the pruning procedure to discard all but the L best paths. The natural pruning criterion can be easily evaluated. Nevertheless a straightforward implementation still requires O L n 2 time which is in stark contrast with the O n log n complexity of the original successive cancellation decoder. The structure of polar codes is used to overcome this problem and provide an efficient numerically stable implementation taking only O L n log n time and O L n space. The polar coding strategies of the invention achieve better performance with lower complexity. In the preferred embodiment list decoder up to L decoding paths are considered concurrently at each decoding stage. Then a single codeword is selected from the list as output. If the most likely codeword is selected simulation results show that the resulting performance is very close to that of a maximum likelihood decoder even for moderate values of L. Alternatively if an intelligent selection procedure selects the codeword from the list the results are comparable to the current state of the LDPC codes.

The preferred list decoder doubles the number of decoding paths at each decoding step and then uses a pruning procedure to discard all but the L best paths. Nevertheless a straightforward implementation still requires O L n time which is in stark contrast with the O n log n complexity of the original successive cancellation decoder. The structure or polar codes is exploited by the invention with an efficient numerically stable implementation taking only O L n log n time and O L n space.

Those knowledgeable in the art will appreciate that embodiments of the present invention lend themselves well to practice in the form of computer program products. Accordingly it will be appreciated that embodiments of the present invention may comprise computer program products comprising computer executable instructions stored on a non transitory computer readable medium that when executed cause a computer to undertake methods according to the present invention or a computer configured to carry out such methods. The executable instructions may comprise computer program language instructions that have been compiled into a machine readable format. The non transitory computer readable medium may comprise by way of example a magnetic optical signal based and or circuitry medium useful for storing data. The instructions may be downloaded entirely or in part from a networked computer. Also it will be appreciated that the term computer as used herein is intended to broadly refer to any machine capable of reading and executing recorded instructions. It will also be understood that results of methods of the present invention may be displayed on one or more monitors or displays e.g. as text graphics charts code etc. printed on suitable media stored in appropriate memory or storage etc.

Preferred embodiments of the invention will now be discussed with respect to the experiments and results. Artisans will appreciate additional features of the invention from the discussion of the experimental results and example embodiments.

A preferred embodiment Successive Cancellation SC decoder is a modification to polar codec of Arikan. The basic decoder must first be defined to explain the modifications.

Let the polar code under consideration have length n 2and dimension k. Thus the number of frozen bits is n k. The reformulation denotes by u u uthe information bits vector including the frozen bits and by c cthe corresponding codeword which is sent over a binary input channel W where 0 1. At the other end of the channel the received word is y y. A decoding algorithm is then applied to y resulting in a decoded codeword having corresponding information bits .

A high level description of the SC decoding algorithm is provided in Algorithm I see Algorithm section . In Algorithm I at each phase of the algorithm the pair of probabilities W y 0 and W y 1 is calculated. Then the value of is determined according to the pair of probabilities.

bit channel W is a binary input channel with output alphabet the conditional probability of which is generically denoted W y u u . 3 

In the present context yis always a contiguous subvector of received vector y. Next for 1 m. recall the recursive definition of a bit channel Provided in Equations 22 and 23 of E. Arikan Channel Polarization A method for Constructing Capacity Achieving Codes for Symmetric Binary Input Memoryless Channels IEEE Trans. Inform. Theory vol. 55 pp. 3051 3073 2009 let 0 2 

For algorithm 1 to become concrete it is necessary to specify how the probability pair associated with W is calculated and how the values of namely are propagated into those calculations. For 0 and 0 

Since during the run of the SC algorithm the channel W is only evaluated with a single output y u u and corresponding branch number 0 is assigned to each output. Next proceed recursively as follows. For 0 consider a channel W with output y u a branch number 0 is assigned to each such output. Next proceed recursively as follows. For 0 consider a channel W with output y u and corresponding branch number . Denote 2 . The output y u u will have a branch number of 2 1. An output corresponding to branch of a channel is introduced.

The input corresponding to a branch can be defined via a similar terminology. Start at layer m and continue recursively. Consider the channel W and let be the corresponding input which Algorithm 1 assumes. This input is assigned a branch number 0. Proceed recursively as follows. For layer 0 consider the channels W and Whaving the same branch with corresponding inputs u and u 1 respectively. In view of 5 consider W and define the input corresponding to branch 2 as u u 1. Under this recursive definition for all 0 

The following lemma points at the natural meaning that a branch number has at layer 0. This can be proved using a straightforward induction.

Lemma 1 Let y and be as in Algorithm 1 the received vector and the decoded codeword. Consider layer 0 and thus set 0. Next fix a branch number 0 

which adopts the same shorthand as 8 . The total memory consumed by this algorithm is O n log n . A preferred first implementation of the SC decoder is given as Algorithms 2 4 see Algorithm Section . The main loop is given in Algorithm 2 and follows the high level description given in Algorithm 1. Note that the elements of the probabilities arrays P and bit array B start out uninitialized and become initialized as the algorithm runs its course. The code to initialize the array values is given in Algorithms 3 and 4.

Proof In addition to proving the claim explicitly stated in the lemma the implicit claim can also be proven. Namely the actions taken by the algorithm should be shown to be well defined. This could be shown by demonstrating that when an array element is read from it was already written to it is initialized .

Both the implicit and the explicit claims are easily derived from the following observation. For a given 0 

The running time of the known SC decoder is O n log n and the implementation provided above is no exception. The space complexity of the present algorithm is O n log n as well. However in the above observation the space complexity can be reduced to O n .

As a first step towards this end consider the probability pair array P. By examining the main loop in Algorithm 2 it is seen that when it is currently at phase then it will never again make of use P 0 for all . Thus instead of reading and writing to P 0 it is possible to essentially disregard the phase information and use only the first element P 0 of the array discarding all the rest. By the recursive nature of the polar codes this observation disregarding the phase information can be exploited for a general layer as well. Specifically for all 0 

Note that the total space needed to hold the P arrays has gone down from O n log n to O n . That is also desirable for the B arrays. However the above implementation does not permit the phase to be disregarded as can be seen for example in line of Algorithm 4. The solution is a simple renaming. As a first step define for each 0 m an array C consisting of bit pairs and have length n 2. Next let a generic reference of the form B be replaced by C 2 mod 2 where 2 . This renames the elements of B as elements of C. It is now possible to disregard the value of and take note only of the parity of . With one more substitution replace every instance of C 2 mod 2 by C mod 2 and resize each array with C to have 2 bit pairs. To sum up B is replaced by C mod 2 . 12 

A further reduction in space is possible for 0 0 and thus the parity of is always even. However this reduction does not affect the asymptotic space complexity which is now indeed down to O n . The revised algorithm is given as Algorithms 5 7.

The above statements are also of use in analyzing the time complexity of the preferred embodiment list decoder.

A preferred embodiment is referred to as a successive cancellation list SCL decoder and example decoding is shown in . The list decoder has a parameter L called the list size. Generally speaking larger values of L mean lower error rates but longer running times. In the main loop of an SC decoder each phase provides a decision on the value of . In the present SCL decoder instead of deciding to set the value of an unfrozen to either a 0 or a 1 the decoding path splits into two paths see to be examined. Paths must be pruned to limit the maximum number of paths allowed to the specified list size L. A pruning criterion is provided to keep the most likely paths at each stage. A simple implementation of the pruning can proceed as follows. Each time a decoding path is split into two forks the data structures used by the parent path are duplicated with one copy given to the first fork and other to the second. Since the number of splits is L n and since the size of the data structures used by each path is n the copying operation alone would consume time L n . This running time is only practical for short codes. However all known to the present inventors implementations of successive cancellation list have complexity at least L n . Preferred embodiments of SCL decoding reduces time complexity to O L n log n instead of L n .

Consider the P arrays of and recall that the size of P is proportional to 2. Thus the cost of copying P grows exponentially small with . On the other hand looking at the main loop of Algorithm 5 and unwinding the recursion P is accessed only every 2 increments of . The bigger P is the less frequently it is accessed. The same observation applies to the C arrays. This observation of the present inventors leads to the use of a lazy copy operation in preferred embodiments. Namely at each given stage the same array may be flagged as belonging to more than one decoding path. However when a given decoding path needs access to an array it is sharing with another path a copy is made.

Low level functions and data structures can provide the lazy copy methodology. The formulation is kept simple for purposes of explanation but artisan will recognize some clear optimizations. The following data structures are defined and initialized in Algorithm 8.

For every layer there will be a bank of L probability pair arrays for use by the active paths. At any given moment some these arrays might be used by several paths while others might not be used by any path. Each such array is pointed by an element of arrayPointer P. Likewise there will be a bank of bit pair arrays pointed to by elements of arrayPointer C.

The pathIndexToArrayIndex array is used as follows. For a given layer and path index l the probability pair array and bit pair array corresponding to layer of path l are pointed to by arrayPointer P pathIndexToArrayIndex l and arrayPointer C pathIndexToArrayIndex l respectively.

At any given moment some probability pair and bit pair arrays from the bank might be used to multiple paths while others may not be used by any. The value of arrayReferenceCount s denotes the number of paths currently using the array pointed to by arrayPointer P s . This is also the number of paths making use of arrayPointer C s . The index s is contained in the stack inactiveARrayIndieces if arrayReferenceCount s is zero.

With the data structures initialized the low level functions by which paths are made active and inactive can be stated. Start by reference to Algorithm 9 by which the initial path of the algorithm is assigned and allocated. This serves to choose a path index l that is not currently in use none of them are and mark it as used. Then for each layer mark through pathIndexToArrayIndex an index s such that both arrayPointer P s and arrayPointer C s are allocated to the current path.

Algorithm 10 is used to clone a path the final step before splitting that path in two. The logic is very similar to that of Algorithm 9 but now the two paths are made to share bit arrays and probability arrays.

Algorithm 11 is used to terminate a path which is achieved by marking it as inactive. After this is done the arrays marked as associated with the path are considered. Since the path is inactive it is treated as not having any associated arrays and thus all the arrays that were previously associated with the path can have their reference count decreased by one.

The goal of all previously discussed low level functions was essential to enable the abstraction implemented by the functions getArrayPointer P and getArrayPointer C. The function getArrayPointer P is called each time a higher level function needs to access either for reading or writing the probability pair array associated with a certain path l and layer . The implementation of getArrayPointer P is provided in Algorithm 12. There are two cases to consider either the array is associated with more than one path or it is not. If it is not then nothing needs to be done and a pointer can be returned to the array. On the other hand if he array is shared a private copy is created for path l and a pointer is returned to that copy. This ensures that two paths will never write to the same array. The function getArrayPointer C is used in the same manner for bit pair arrays and has exactly the same essential implementation.

The above implementation deliberately sacrifices speed for simplicity. Namely each such function is called either before reading or writing to an array. A variation to optimize speed conducts the copy operation only before writing.

This completes the definition of almost all low level functions. Constraints that should be followed and what is expected if these constraints are met are provided next.

Definition 1 Valid calling sequence Consider a sequence f of T 1 calls to the low level functions implemented in Algorithms 8 12. The sequence is considered valid if the following traits hold.

Initialized The one and only index t for which fis equal to intializedDataStructures is t 0. The one and only index t for which fis equal to assignIntialPath is t 1.

Balanced For 1 t T denote the number of times the function clonePath was called up to and including t as 1 is clonePath .

Active A path l is active at the end of stage 1 t T if the following conditions hold. First there exists an index 1 i t for which fis either clonePath with corresponding output l or assignIntialPath with output l. Second there is no intermediate index i

Lemma 3 Let f be a valid sequence of calls to the low level function implemented in Algorithms 8 12. Then the run is well defined i A pop operation is never carried out on an empty stack ii a push operation never results in a stack with more than L elements and iii a read operation from any array defined in lines of Algorithm 8 is always preceded by a write operation to the same location in the array.

Proof The proof reduces to proving the following four statements concurrently for the end of each step 1 t T by induction on t.

I A path index l is active by Definition 1 if activePath l is true if inactivePathIndices does not contail the index l.

III The value of arrayReferenceCount s is positive if the stack inactiveArrayIndices does not contain the index s and is zero otherwise.

IV The value of arrayReferenceCount s is equal to the number of active paths l for which pathIndexArrayIndex l s.

Before completing formalization of the utility of the low level functions the concept of a descendant path needs to be specified. Let f be a valid sequence of calls. Next let l be an active path index at the end of stage t T. Henceforth abbreviate the phrase path index l at the end of stage t by l t . l t 1 is a child of l t if i l is active at the end of stage t 1 and ii either l l or fwas the clonePath operation with input l and output l . Likewise l t is a descendant of l t if 1 t t and there is a possibly empty hereditary chain.

The definition of a valid function calling sequence can now be broadened by allowing reads and writes to arrays.

Fresh pointer consider the case where t 1 and fis either the getArrayPointer P or getArrayPointer C function with input l and output p. Then for valid indices I allow read and write operations to p i after stage t but only before ant stage t t for which f is either clonePath or killPath.

Lemma 4 Let f be a valid sequence of calls to the low level functions implemented in Algorithms 8 12. Assume the read write operations between stages satisfy the fresh pointer condition.

Let the function fbe getArrayPointer P with input l and output p. Similarly for stage t t let f be getArrayPointer P with input l and output p . Assume that l t is a descendant of l t .

Consider a fresh pointer write operation to p i . Similarly consider a fresh pointer read operation from p i carried out after the write operation. Then assuming no intermediate write operations of the above nature the value written is the value read.

Proof With the observations made in the proof Lemma 3 at hand a simple induction on t is all that is needed.

The function pathIndexInactive given in Algorithm 13 is simply a shorthand meant to help readability.

Algorithms 14 and 15 are modified implementations of Algorithms 6 and 7 respectively for the list decoding setting.

These implementations of the preferred embodiment loop over all the path indices l. Thus the implementations make use of the functions getArrayPointer P and getArrayPointer C in order to assure that the consistency of calculations is preserved despite multiple paths sharing information. In addition Algorithm 6 contains code to normalize probabilities. The normalization retained for a technical reason to avoid floating point underflow and will be expanded on shortly.

Note that the fresh pointer condition imposed indeed holds. To see this consider first Algorithm 14. The key point to note is that neither the killPath nor the clonePath function is called from inside the algorithm. The same observation holds for Algorithm 15. Thus the fresh pointer condition is met and Lemma 4 holds.

Consider next the normalization step carried out in lines of Algorithm 14. Recall that a floating point variable cannot be used to hold arbitrarily small positive reals and in a typical implementation the result of a calculation that is too small will be rounded to 0. This scenario is called an underflow .

Previous implementations of SC decoders were prone to underflow . To see this consider line in the outline implementation given in Algorithm 2. Denote by Y and U the random vectors corresponding to y and u respectively. For 0 1 2 2 2.

Recall that iterates from 0 to n 1. Thus for codes having length greater than some small constant the comparison in line of Algorithm 2 ultimately becomes meaningless since both probabilities are rounded to 0.

Preferred embodiments provide a fix to this problem. After the probabilities are calculated in lines of Algorithm 14 normalize the highest probability to be 1 in lines . The correction does not guarantee in all circumstances that underflows will not occur. However the probability of a meaningless comparison due to underflow will be extremely low.

Apart from minimizing risk of overflows normalization does not alter the algorithm. The following lemma formalizes this claim.

Lemma 5 Assume perfect floating point numbers. That is floating point variables are infinitely accurate and do not suffer from underflow overflow. Next consider a variant of Algorithm 14 termed Algorithm 14 in which just before line is first executed the variable is set to 1. That is effectively there is no normalization of probabilities in Algorithm 14 .

Consider two runs one of Algorithm 14 and one of Algorithm 14 . In both runs the input parameters to both algorithms are the same. Moreover assume that in both runs the state of the auxiliary data structures is the same apart from the following.

Recall that the present algorithm is recursive and let be the first value of the variable for which line is executed. That is is the layer in which both algorithms do not perform preliminary recursive calculations. Assume at this base stage the following holds the values read from Pin lines and in the run of Algorithm 14 are a multiple by of the corresponding values read in the run of Algorithm 14 . Then for every there exists a constant such that values written to P in line in the run of Algorithm 14 are a multiple by of the corresponding values written by Algorithm 14 .

Proof For the base case inspections shows that the constant is simply divided by the value of after the main loop has finished executing in Algorithm 14. The claim for a general follows by induction.

Consider the topmost function the main loop given in algorithm 16. Line 1 and 2 provide that the condition initialized in Definition 1 is satisfied. Also for the inductive basis the condition balanced holds that for t 1 at the the end of line . Next notice that lines are in accordance with the fresh pointer condition.

The main loop lines is the analog of the main loop in Algorithm 5. After the main loop has finished the algorithm selects in lines the most likely codeword from the list and returns it.

Algorithms 17 and 18 are now introduced. Algorithm 17 is the analog of line in Algorithm 5 applied to active paths.

Algorithm 18 is the analog of lines in Algorithm 5. However now instead of choosing the most likely fork out of 2 possible forks it is typical to need to choose the L most likely forks out of 2 L possible forks. The most interesting line is 14 in which the best forks are marked. Surprisingly this can be done in O L time See Section 9.3 of T. H. Cormen et al. Introduction to Algorithms 2nd ed. Cambridge Mass. The MIT Press 2001 . The O L time result rather theoretical. Since L is typically a small number the fastest way to achieve the selection goal would be through simple sorting. After the forks are marked first kill the path for which both forks are discontinued and then continue paths for which one or both are the forks are marked. In case of the latter the path is first split. The procedure first kills paths and only then splits paths in order for the balanced constraint 13 to hold. This provides a limit of L active paths at a time.

A primary function of Algorithm 18 is to prune the list and leave only the L best paths. This pruning is performed using the accumulated likelihood of each path. The accumulated likelihood is stored in the probForks array of Algorithm 18. The selection of the L best paths is conducted on line of Algorithm 18. Selection of the L best paths is indeed achieved in the following sense. At stage to rank each patch according to the probability W y .

By 9 and 11 this would indeed by the if the floating point variables were perfect and the normalization step in lines of Algorithm 14 were not carried out. By Lemma 5 this is still the case if normalization is carried out.

In Algorithm 19 the most probable path is selected from the final list. As before by 9 12 and Lemma 5 the value of P 0 C 0 1 is simply

Proof All the data structures of the list decoder are allocated by in Algorithm 8 and it can be checked that the total space used by them is O L n . Apart from these the space complexity needed in order to perform the selection operation in line of Algorithm 18 is O L . Lastly the various local variables needed by the algorithm take O 1 space and the stack needed in order to implement the recursion takes O log n space.

Proof Recall that m log n. The following bottom to top table summarizes the running time of each function. The notation O will be explained after.

The first 7 functions in the table the low level functions are easily checked to have the stated running time. Note that the running time of getArrayPointer P and getArrayPointer C is due to the copy operation in line of Algorithm 6 applied to an array of size O 2 . Thus as we previously mentioned reducing the size of the arrays has helped to reduce the running time of the list decoding algorithm.

Next consider the two mid level functions namely recusivelyCalcP and recursivelyUpdateC. The notation recursivelyCalcP m O L m n 

is O L m n . To see this denote by f the total running time of the above with m replaced by . By splitting the running time of Algorithm 14 into a non recursive part and a recursive part for 0 2 2 1 .

In essentially the same way it can be proven that the total running time of the recursivelyUpdateC m over all 2valid odd values of is O m n . Note that the two mid level functions are invoked in lines and of Algorithm 16 on all valid inputs.

The plots in were obtained by simulation. The performance of the decoder for various list sizes is given by the solid lines in the figure. As expected as the list size L increases the performance of the decoder improves.

A diminishing returns phenomenon is noticeable in terms of increasing list size. The reason for this turns out to be simple.

The dashed line termed the ML bound was obtained as follows. During simulations for L 32 each time a decoding failure occurred a check was conducted to see whether the decoded codeword was more likely than the transmitted codeword. That is true whether W y W y c . If so then the optimal ML decoder would surely misdecode y as well. The dashed line records the frequency of the above event and is thus a lower bound on the error probability of the ML decoder. Thus for an SNR value greater than about 1.5 dB suggests an essentially optimal decoder is provided when L 32.

Better performance seems unlikely at least for the region in which the decoder is essentially optimal. However a modified polar code of a preferred embodiment dramatically improved performance can be achieved.

During simulations when a decoding error occurred the path corresponding to the transmitted codeword was often a member of the final list. However since there was a more likely path in the list the codeword corresponding tot that path was returned which resulted in a decoding error. Thus intelligent selection at the final stage can specify which path to pick from the list then the performance of the decoder can be improved.

Such intelligent selection can be implemented with preferred embodiments that provide a modified polar code. Recall that there are k unfrozen bits that are free to be set. Instead of setting all of them to information bits to be transmitted a concatenation scheme is employed. For some small constant r set the first k r unfrozen bits to information bits. The last r bits will hold the r bit CRC See Section8.8 of W. W. Peterson and E. J. Weldon Error Correcting Codes 2nd ed. Cambridge Mass. The MIT Press 1972 value of the first k r unfrozen bits. A binary linear code having a corresponding k r parity check matrix constructed as follows will perform well. Le the first k r columns be chosen at random and the last r columns be equal to the identity matrix. This concantated encoding is a variation of the polar coding scheme that provides an important functionality for intelligent selection while being minor from the perspective of the polar code structure. The concentration incurs a penalty in rate since the rate of the code is now k r n instead of the previous k n.

What is gained is an approximation to a perfect selector at the final stage of decoding instead of calling the function findMostProbablePath in Algorithm 19 do the following. A path for which the CRC is invalid can not correspond to the transmitted codeword. Thus refine the selection as follows. If at least one path has a correct CRC then remove from the list all paths having incorrect CRC and then choose the most likely path. Otherwise select the most likely path in the hope of reducing the number of bits in error but with the knowledge that there is at least one bit in error.

Advantageously when the preferred algorithm finishes it outputs a single codeword. In addition its performance approaches an ML decoder even with modest L values.

The solid line in correspond to choosing the most likely codeword from the list as the decoder input. As can be seen this choice of the most likely codeword results in a large range in which the present algorithm has performance very close to that of the ML decoder even for moderate values of L. Thus the sub optimality of the SC decoder indeed does play a role in the disappointing performance of polar codes.

The invention also shows that polar codes themselves are weak. Instead of picking the most likely codeword from the list an intelligent selector can select the codeword in the list that was the transmitted codeword if the transmitted codeword was indeed present in the list . Implementing such an intelligent selector turns out to be a minor structural change of the polar code with a minor penalty in preferred embodiments and entails a modification of the polar code. With this modification the performance of polar codes is comparable to state of the art LDPC codes as can be seen in .

While specific embodiments of the present invention have been shown and described it should be understood that other modifications substitutions and alternatives are apparent to one of ordinary skill in the art. Such modifications substitutions and alternatives can be made without departing from the spirit and scope of the invention which should be determined from the appended claims.

