---

title: Rank deficient decoding of linear network coding
abstract: Rank deficient decoding for linear network coding. The decoding problem is first decomposed into multiple parallel sub-problems. A determination is made whether the decoding problem is or is not rank deficient. If rank deficient, and for each sub-problem, a rank deficient decoder is applied to obtain a solution.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09059832&OS=09059832&RS=09059832
owner: The United States of America as represented by the Secretary of the Air Force
number: 09059832
owner_city: Washington
owner_country: US
publication_date: 20130724
---
This patent application claims the priority benefit of the filing date of provisional application Ser. No. 61 742 058 having been filed in the United States Patent and Trademark Office on Aug. 1 2012 and now incorporated by reference herein.

The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalty thereon.

This invention relates generally to the field of communication networks. More specifically the present invention relates to rank deficient decoding of linear network coding.

Communications networks CNs are ubiquitous in our everyday life as well as our national infrastructure. Network coding 1 has the potential to fundamentally transform current and future CNs due to the promise of significant throughput gains. Furthermore network coding has other advantages such as robustness and can be implemented in a distributed manner with random linear network coding 2 . Hence network coding is already used or considered for a wide variety of wired and wireless networks.

One significant drawback of network coding is its all or nothing property in more than one sense. First a full rank of received packets at the receiver nodes is needed before decoding can start leading to long delays and low throughputs especially when the number of packets of a session is large. This is particularly undesirable for military and civil applications with stringent delay requirements. Second all the bits in any packet are created equal in the sense that they are recovered simultaneously.

Network coding is a network paradigm where packets can be operated on or mixed. It has been shown that network coding improves the network throughput and robustness to network failures. Although network coding is first applied to packets this idea has later been applied to waveforms on the physical layer.

It has been shown that in most practical scenarios linear network coding is close to optimal. Furthermore in all existing linear network coding schemes a full rank decoder is used. A full rank decoder fails unless the rank of the received packets is the same as that of the transmitted packets.

U.S. Pat. No. 8 473 998 to Lucani et al. discloses a method apparatus and computer program product for utilizing network coding for multi resolution multicast. A network source partitions source content into a base layer and one or more refinement layers. The network source receives a respective one or more push back messages from one or more network destination receivers the push back messages identifying the one or more refinement layers suited for each one of the one or more network destination receivers. The network source computes a network code involving the base layer and the one or more refinement layers for at least one of the one or more network destination receivers and transmits the network code to the one or more network destination receivers in accordance with the push back messages.

U.S. Pat. No. 8 046 426 to Medard et al. discloses a method and computer program product for providing a random linear coding approach to distributed data storage is presented. A file is broken into a plurality of pieces. For every peer peer means storage location with limited storage space the number of coded pieces the peer can store is determined. Each of the coded piece is determined by taking random linear combination of all the pieces of the entire file. The associate code vector is stored for every coded piece. The file is retrieved by collecting code vectors and the coded pieces from the peers and viewing the collected code vectors as a matrix. When a dimension of the matrix is equal to the number of pieces of the file the file is recovered using the collection of code vectors in the matrix.

U.S. Pat. No. 8 375 102 to Medard et al. discloses a method and computer program product for providing a random linear coding approach to distributed data storage is presented. A file is broken into a plurality of pieces. For every peer peer means storage location with limited storage space the number of coded pieces the peer can store is determined. Each of the coded piece is determined by taking random linear combination of all the pieces of the entire file. The associate code vector is stored for every coded piece. The file is retrieved by collecting code vectors and the coded pieces from the peers and viewing the collected code vectors as a matrix. When a dimension of the matrix is equal to the number of pieces of the file the file is recovered using the collection of code vectors in the matrix.

U.S. Pat. No. 8 102 837 to Deb et al. discloses a method apparatus and computer program product for providing rapid information dissemination using network coding is presented. A coded message including a payload and a code vector is transmitted from a first node of the network to a second node of the network. The information thus stored can also be retrieved by collecting code vectors from at least one node and viewing the collected code vectors as a matrix. A determination is made regarding whether a dimension of the matrix is equal to a predefined number. When the dimension of the matrix equals the predefined number the information is retrieved using the collection of code vectors in the matrix.

All network coding schemes in the prior art assume a full rank decoder. Hence more received packets are needed before decoding starts.

The present invention provides an apparatus and method for rank deficient decoding of linear network coding in a communications network.

It is therefore an object of the present invention to provide a decoding apparatus and method for linear network coding that works even when the received packets are rank deficient.

Briefly stated the present invention achieves these and other objects by providing a decoding method when the received packets are rank deficient.

In a fundamental embodiment of the present invention packets in a communications network are transmitted in batches. In linear network coding any communications network node performs linear operations on any packets received for a particular batch. Hence at the destination a set of packets is received corresponding to the batch of transmitted packets. The full rank decoder starts only when the rank of the received packets is the same as the rank of the transmitted packets.

The above and other objects features and advantages of the present invention will become apparent from the following description read in conjunction with the accompanying drawings in which like reference numerals designate the same elements.

In a fundamental embodiment of the present invention packets are transmitted in batches. In linear network coding any network node performs linear operations on any packets received for a particular batch. Hence at the destination a set of packets is received corresponding to the batch of transmitted packets. The full rank decoder starts only when the rank of the received packets is the same as the rank of the transmitted packets.

This invention reconstructs the transmitted packets from a set of received packets even if the received packets are rank deficient. Referring to the received packets are first processed in order to remove linearly dependent packets. Then the decoding problem is decomposed into multiple parallel sub problems. After solving the sub problems in parallel the solutions to the sub problems are used to reconstruct the transmitted data packets.

Each received packet has two parts relevant to linear network coding the first called the header contains the linear coefficients used to obtain the received packet and the second is the data. Note that the data is the linear combination of the transmitted data packets using the coefficients in the header.

Suppose packet i is treated as two row vectors hand d where his the header and dthe data. The received packets are hence represented by H D where row i of H and D are hand d respectively. Gaussian elimination is applied to H D and the result is a two by two block matrix

After all N sub problems are solved the solutions to all sub problems are collected . Next the invention determines whether every sub problem has a single solution. If yes then W s have been obtained from the sub problems and they are collected to form the transmitted data packets as shown in . That is the transmitted data packets are the rows of WW. . . W . If no it means that multiple candidates exist for WW. . . W . The invention first forms the set of possible data packets and then selects the transmitted data packets using additional data packets. For instance if the number of bits being one in each data packet is limited then this limit can be used to select the transmitted data packet.

The present invention is most readily implemented in computer software instructions being executed on a computer that has inputs and outputs to and from a communications network. Inputs to the invention are received data packets. Outputs from the invention are reconstructed data packets.

Having described preferred embodiments of the invention with reference to the accompanying drawings it is to be understood that the invention is not limited to those precise embodiments and that various changes and modifications may be effected therein by one skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.

