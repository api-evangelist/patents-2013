---

title: Apparatus for performing matrix vector multiplication approximation using crossbar arrays of resistive memory devices
abstract: An apparatus that performs the mathematical matrix-vector multiplication approximation operations using crossbar arrays of resistive memory devices (e.g. memristor, resistive random-access memory, spintronics, etc.). A crossbar array formed by resistive memory devices serves as a memory array that stores the coefficients of a matrix. Combined with input and output analog circuits, the crossbar array system realizes the method of performing matrix-vector multiplication approximation operations with significant performance, area and energy advantages over existing methods and designs. This invention also includes an extended method that realizes the auto-associative neural network recall function using the resistive memory crossbar architecture.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09152827&OS=09152827&RS=09152827
owner: The United States of America as represented by the Secretary of the Air Force
number: 09152827
owner_city: Washington
owner_country: US
publication_date: 20130813
---
This patent application claims the priority benefit of the filing date of provisional application Ser. No. 61 848 775 having been filed in the United States Patent and Trademark Office on Dec. 19 2012 and now incorporated by reference herein.

The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

Matrix vector multiplication is one of the most commonly used mathematical operations in science and engineering computations. Mathematically a matrix is usually represented by a two dimensional array of real numbers and a vector is represented by a one dimensional array of real numbers. Since a matrix can be viewed as an array of vectors the matrix vector multiplication operation can be generalized to vector vector multiplication inner product or matrix matrix multiplication operations. In today s computer systems matrix vector multiplication operations are performed by digital integrated circuits in which the numbers are represented in binary format and the computation is performed by Boolean logic circuits.

The existence of resistive memory devices such as the memristor resistive random access memory RRAM and spintronic switches were predicted in circuit theory nearly forty years ago. However it wasn t until 2008 that the first physical realization was demonstrated by HP Labs through a TiOthin film structure. Afterward many resistive memory materials and devices have been reported or rediscovered. The resistive memory device has many promising features such as non volatility low power consumption high integration density and excellent scalability. More importantly the unique property to record the historical profile of the excitations on the device makes it an ideal candidate to perform storage and computation functions in one device.

For the purpose of succinct description the present invention uses the terminology memristor to represent the category of resistive memory device . For the remainder of the patent description references to memristor shall be regarded as referring to any resistive memory device .

Based on circuit theory an ideal memristor with memristance M builds the relationship between the magnetic flux and electric charge q that passes through the device that is d M dq. Since the magnetic flux and the electric charge are time dependent parameters the instantaneous memristance varies with time and reflects the historical profile of the excitations through the device.

When developing actual memristive devices many materials have demonstrated memristive behavior in theory and or experimentation via different mechanisms. In general a certain energy or threshold voltage is required to enable a state change in a memristor. When the electrical excitation through a memristor is greater than the threshold voltage e.g. v v the memristance changes. Otherwise the memristor behaves like a resistor.

It is therefore an object of the present invention to provide an apparatus that performs mathematical matrix vector multiplication approximation.

It is a further object of the present invention to provide an apparatus that utilizes resistive memory devices to store matrix coefficients so as to facilitate matrix vector multiplication approximation.

It is yet a further object of the present invention to apply matrix vector multiplication approximation to facilitate auto associative neural network recall functionality.

Briefly stated the present invention is an apparatus that performs mathematical matrix vector multiplication approximation operations using crossbar arrays of resistive memory devices e.g. memristor resistive random access memory spintronics etc. . A crossbar array formed by resistive memory devices serves as a memory array that stores the coefficients of a matrix. Combined with input and output analog circuits the crossbar array system realizes the method of performing matrix vector multiplication approximation with significant performance area and energy advantages over existing methods and designs. This invention also includes an extended method that realizes the auto associative neural network recall function using the resistive memory crossbar architecture.

In this invention we describe a matrix vector multiplication approximation hardware method and design based on crossbar arrays of resistive memory devices.

By nature the memristor crossbar array is attractive for the implementation of matrix vector multiplication operations. The crossbar array inherently provides capabilities for this type of operation. In this invention we focus on a hardware architecture and realization of the matrix vector multiplication approximation assuming all of the memristors have been pre programmed to store the elements of the matrix. During the multiplication operations the voltages across the memristors are constrained below the threshold voltage so that all the memristance values remain unchanged. The crossbar architecture can naturally transfer the weighted combination matrix of input voltages input vector to output voltages output vector . We also describe a fast approximation mapping method so that the matrix can be mapped to pure circuit element relations.

As shown in the proposed hardware method and design includes two crossbar arrays of resistive memory devices M for positive elements of the matrix and M for negative elements of the matrix. The input vector is represented by the input voltages VI that are driving the row horizontal wires of the crossbar arrays. The matrix vector multiplication approximation resulting vector is represented by the outputs VO of the analog subtraction amplifier circuits connected to the column vertical wires of the crossbar arrays.

This invention also includes an extended method and design that realizes the auto associative neural network recall function using the resistive memory crossbar architecture see and . The Brain State in a Box BSB model recall operation will be used as an example to illustrate the method.

Referring to the present invention uses an N by M memristor crossbar array as a basic building block to achieve matrix vector multiplication approximation computation functionality.

A set of input voltages VI vi vi . . . vi are applied on each of the N word lines WLs of the array and the current is collected through each of the M bit lines BLs by measuring the voltage across a sensing resistor . The same sensing resistors are used on all the BLs with resistance r or conductance g 1 r. The output voltage vector is VO vo vo . . . vo. Assume the memristive device i.e. memristor sitting on the connection between WLand BLhas a memristance of m. The corresponding conductance is g 1 m. Then the relation between the input and output voltages can be approximated by 1 Here C is an MA by N matrix that can be represented by the memristors and the sensing load resistors as 

Eq. 1 indicates that a trained memristor crossbar array can be used to construct the connection matrix C and transfer the input vector VI to the output vector VO. However Eq. 2 shows that C is not a direct one to one mapping of conductance matrix G of the memristor crossbar array since the diagonal matrix D is also a function of G. We have two methods to obtain the solution of G an complex numerical iteration method to obtain the exact mathematical solution of G and a simple approximation useful for frequent or resource constrained updates. In this invention we adopt the second method which is described next.

In this section we first show how to map C to G when cis in the range of 0 1.0 . In the next section we will show the method of mapping a general matrix A with both positive and negative elements.

We assume any g G satisfies g g g where gand grespectively represent the minimum and the maximum conductance of all memristors in the crossbar array. Instead we propose a simple and fast approximation to the mapping problem by allowing 4 

In the following we will prove that by using this mapping method a scaled version of the connection matrix C can be approximately mapped to the conductance matrix G of the memristor array.

Note that many memristor materials such as the TiOmemristor demonstrate a large g gratio. Thus a memristor at the high resistance state under a low voltage excitation can be regarded as an insulator that is g 0. And ccan be further reduced by increasing the ratio of g g. As a result the impact of ccan be ignored. These two facts indicate that Eq. 5 can be further simplified to 

In summary with the proposed mapping method the memristor crossbar array performs as a scaled connection matrix between the input and output voltage signals.

In this section we describe the method of mapping from a matrix A to the memristor conductances G under the condition that ais in the range from 1.0 to 1.0. In the general case we can scale any given matrix to the 1.0 1.0 range then perform the operation and finally scale the resulting outputs back to the original range.

Given a matrix A with all its elements scaled to the range of 1.0 1.0 we first split the positive and negative elements of A into two matrixes A and A as 

As such a general matrix vector multiplication approximation becomes 8 Here the two matrices A and A can be mapped to two memristor crossbar arrays Mand Min a scaled version and respectively by combining the mapping method in Eq. 4 with Eq. 7a and 7b as follows.

To realize the matrix vector multiplication approximation function y A x at the circuit level the elements of the input vector x are converted to the range of input voltage levels VI. The corresponding functions for the multiplication approximation can be expressed as 

As shown in the memristor crossbar arrays are used to realize the matrix vector multiplication approximation operation. To obtain both positive and negative elements in the matrix two memristor crossbar arrays M and M are required in the design to represent the positive and negative matrices and respectively. The memristor crossbar arrays have the same dimensions as the transposed matrix A.

In the present invention the input signal VI along with VO and VO the corresponding voltage outputs of two memristor crossbar arrays are fed into a number of analog subtraction amplifier circuits . The design of the subtraction amplifier is shown in .

Resulting from the scaled mapping method the required VO should be g gtimes the generated VO or VO. In the present invention we set R R 1 gand R R 1 g. The resulting output of the subtraction amplifier is 

The Brain State in a Box BSB model is a typical auto associative neural network. The mathematical model of the BSB recall function can be represented as 1 16 where x is an N dimensional real vector and A is an N by N connection matrix. A x t is a matrix vector multiplication operation which is the main function of the recall function. is a scalar constant feedback factor. is an inhibition decay constant. S y is the squash 

For a given input pattern x 0 the recall function computes Eq. 16 iteratively until convergence that is when all entries of x t 1 are either 1 or 1 .

Using the same method for general matrix vector multiplication approximation described previously. Eq. 16 converts to 1 18 Here for the default case we set 1. The two connection matrices A and A can be mapped to two N by N memristor crossbar arrays M and M in a scaled version and respectively by following the mapping method in Eq. 9 and Eq. 10 .

To realize the BSB recall function at the circuit level the normalized input vector x t is converted to a set of input voltage signals V t . The corresponding function for the voltage feedback system can be expressed as 

As the key component of the overall design the memristor crossbar arrays are used to approximate the matrix vector multiplication functions in the BSB recall operation. To obtain both positive and negative weights in the original BSB algorithm in Eq. 16 two N by N memristor crossbar arrays M and M are required in the design to represent the connection matrices and respectively. The memristor crossbar arrays have the same dimensions as the BSB weight matrix A transposed.

In the present invention the input signal v t along with v t and v t the corresponding voltage outputs of two memristor crossbar arrays are fed into a summation subtraction amplifier . The design of the summation subtraction amplifier circuit can be found in .

Resulting from the decayed mapping method the required v t and v t should be g gtimes of the generated v t and v t respectively. In the present invention R R R 1 gand R R R R 1 g. The resulting output of the summation subtraction amplifier is 

Once a new set of voltage signals V t 1 is generated from the summation subtraction amplifiers the present invention sends them back as the input of the next iteration. Meanwhile each v t 1 V t 1 is compared to vand vso that when vequals to either vor v we deem the output i as having converged . The recall operation stops when all N outputs reach convergence. In total N comparators are needed to cover all the outputs.

There are three major physical constraints in the circuit implementation 1 For any v 0 V 0 the voltage amplitude of initial input signal v 0 is limited by the input circuit 2 boundary voltage vmust be smaller than vof memristors and 3 the summation subtraction amplifier has finite resolution.

In the BSB recall function the ratio between boundaries of S y and the initial amplitude of x 0 x 0 x 0 determines the learning space of the recall function. If the ratio is greater than the normalized value the recall operation will take more iterations to converge with a higher accuracy. Otherwise the procedure converges faster by lowering stability. Thus minimizing the ratio of v 0 and vcan help obtain the best performance. However the real amplifier has a finite resolution and vis limited within vof the memristor . Continuously reducing v 0 eventually will lose a significant amount of information in the recall circuit.

Having described preferred embodiments of the invention with reference to the accompanying drawings it is to be understood that the invention is not limited to these precise embodiments and that various changes and modifications may be affected therein by one skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.

