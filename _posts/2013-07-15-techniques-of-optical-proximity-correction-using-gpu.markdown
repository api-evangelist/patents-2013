---

title: Techniques of optical proximity correction using GPU
abstract: Computationally intensive electronic design automation operations are accelerated with algorithms utilizing one or more graphics processing units. The optical proximity correction (OPC) process calculates, improves, and optimizes one or more features on an exposure mask (used in semiconductor or other processing) so that a resulting structure realized on an integrated circuit or chip meets desired design and performance requirements. When a chip has billions of transistors or more, each with many fine structures, the computational requirements for OPC can be very large. This processing can be accelerated using one or more graphics processing units.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08938696&OS=08938696&RS=08938696
owner: D2S, Inc.
number: 08938696
owner_city: San Jose
owner_country: US
publication_date: 20130715
---
This application is a continuation of U.S. patent application Ser. No. 13 178 883 filed Jul. 8 2011 issued as U.S. Pat. No. 8 490 034 on Jul. 16 2013 which claims priority to U.S. provisional patent application 61 362 565 filed Jul. 8 2010 which are incorporated by reference along with all other references cited in this patent application.

The present invention relates to the field of electronic design automation and in particular to improved techniques for computationally efficient and accurate optical proximity correction.

Optical proximity correction or OPC is a photolithography enhancement technique commonly used to compensate for image errors due to diffraction or process effects. The need for OPC is seen mainly in the making of semiconductor devices and is due to the limitations of light to maintain the edge placement integrity of the original design after processing into the etched image on the silicon wafer. These projected images appear with irregularities such as line widths that are narrower or wider than designed these are amenable to compensation by changing the pattern on the photomask used for imaging. Other distortions such as rounded corners are driven by the resolution of the optical imaging tool and are harder to compensate for. Such distortions if not corrected for may significantly alter the electrical properties of what was being fabricated. Optical Proximity Correction corrects these errors by moving edges or adding extra polygons to the pattern written on the photomask. The objective is to reproduce as well as possible the original layout drawn by the designer in the silicon wafer.

Using traditional approaches optical proximity correction is computationally complex and takes significant amount of computing resources and time. An improved approach with techniques that utilize graphical processing units GPUs is needed to accelerate optical proximity correction.

A technique of the invention uses adaptive fragmentation and sampling for optical proximity correction.

A technique of the invention uses an approximate calculation of two dimensional 2D matrix entries via graphics processing units to perform computations.

A technique of the invention uses optical proximity correction on hardware or software platforms with graphics processing units. Optical proximity correction techniques performed on one or more graphics processors improve the masks used for the printing of microelectronic circuit designs.

A technique of the invention uses a graphics processing unit based full chip inverse lithography solution for random patterns. In an implementation this technique involves selecting a computational platform a forward path process simulation modeling optics process modeling or mask modeling a feedback path using an optimization based mask synthesis method. In another implementation this technique uses full chips. In this implementation random logic experiments with flattened designs random logic experiments with hierarchical data processing and repetitive structure experiments may be performed.

A technique of the invention uses a modeling approach for mask and wafer process simulation. In an implementation physical models for mask modeling physical models for wafer processing modeling optics processing modeling neural networks for nonlinear mapping may be used.

A technique of the invention uses adaptive sampling and fragmentation algorithms for optical proximity correction.

A technique of the invention uses an instruction set architecture based hardware and software platform for electronic design automation. An implementation may use parallel processing systems virtual machines instruction sets instruction sets for electronic design automation and TCAD processes.

A technique of the invention uses an optimal implementation of computational algorithms on hardware software platforms with graphical processing units.

A technique of the invention uses a graphics processing unit based full chip source mask optimization solution. An implementation of the invention may use a hierarchical selection of critical features. Another implementation of the invention may use a source mask optimization algorithm. This algorithm may include in initialization method an initialization of a light source offspring generation and selection strategy initialization of a mask an optimization algorithm source shape optimization or mask shape optimization.

Other objects features and advantages of the present invention will become apparent upon consideration of the following detailed description and the accompanying drawings in which like reference designations represent like features throughout the figures.

This application incorporates by reference U.S. patent application Ser. No. 11 566 140 filed Dec. 1 2006 issued as U.S. Pat. No. 7 546 574 on Jun. 9 2009 Ser. No. 11 566 146 filed Dec. 1 2006 Ser. No. 11 864 296 filed Sep. 28 2007 60 827 333 filed Sep. 28 2006 Ser. No. 11 864 343 filed Sep. 28 2007 60 827 295 filed Sep. 28 2006 Ser. No. 11 875 650 filed Oct. 19 2007 60 862 362 filed Oct. 20 2006 Ser. No. 11 864 381 filed Sep. 28 2007 issued as U.S. Pat. No. 7 716 627 on May 11 2010 and Ser. No. 11 864 419 filed Sep. 28 2007.

Mass storage devices may include mass disk drives floppy disks magnetic disks optical disks magneto optical disks fixed disks hard disks CD ROMs recordable CDs DVDs recordable DVDs e.g. DVD R DVD R DVD RW DVD RW HD DVD or Blu ray Disc flash and other nonvolatile solid state storage e.g. USB flash drive battery backed up volatile memory tape storage reader and other similar media and combinations of these.

A computer implemented or computer executable version of the invention may be embodied using stored on or associated with computer readable medium. A computer readable medium may include any medium that participates in providing instructions to one or more processors for execution. Such a medium may take many forms including but not limited to nonvolatile volatile and transmission media. Nonvolatile media includes for example flash memory or optical or magnetic disks. Volatile media includes static or dynamic memory such as cache memory or RAM. Transmission media includes coaxial cables copper wire fiber optic lines and wires arranged in a bus. Transmission media can also take the form of electromagnetic radio frequency acoustic or light waves such as those generated during radio wave and infrared data communications.

For example a binary machine executable version of the software of the present invention may be stored or reside in RAM or cache memory or on mass storage device . The source code of the software of the present invention may also be stored or reside on mass storage device e.g. hard disk magnetic disk tape or CD ROM . As a further example code of the invention may be transmitted via wires radio waves or through a network such as the Internet.

The computer system may include any number of graphics processors. The graphics processor may reside on the motherboard such as being integrated with the motherboard chipset. One or more graphics processors may reside on external boards connected to the system through a bus such as an ISA bus PCI bus AGP port PCI Express or other system buses. Graphics processors may on separate boards each connected to a bus such as the PCI Express bus to each other and to the rest of the system. Further there may be a separate bus or connection e.g. Nvidia SLI or ATI CrossFire connection by which the graphics processors may communicate with each other. This separate bus or connection may be used in addition to or in substitution for system bus.

Each processor CPU or GPU or both may be a dual core or multicore processor where there are multiple processor cores on a single integrated circuit. The system may also be part of a distributed computing environment. In a distributed computing environment individual computing systems are connected to a network and are available to lend computing resources to another system in the network as needed. The network may be an internal Ethernet network Internet or other network.

Arrows such as represent the system bus architecture of computer system . However these arrows are illustrative of any interconnection scheme serving to link the subsystems. For example speaker could be connected to the other subsystems through a port or have an internal connection to central processor . Computer system shown in is but an example of a computer system suitable for use with the present invention. Other configurations of subsystems suitable for use with the present invention will be readily apparent to one of ordinary skill in the art.

Computer software products may be written in any of various suitable programming languages such as C C C Pascal Fortran Perl Matlab from MathWorks Inc. SAS SPSS Java JavaScript and AJAX. The computer software product may be an independent application with data input and data display modules. Alternatively the computer software products may be classes that may be instantiated as distributed objects. The computer software products may also be component software such as Java Beans from Sun Microsystems or Enterprise Java Beans EJB from Sun Microsystems .

An operating system for the system may be one of the Microsoft Windows family of operating systems e.g. Windows 95 98 Me Windows NT Windows 2000 Windows XP Windows XP x64 Edition Windows Vista Windows CE Windows Mobile Linux HP UX UNIX Sun OS Solaris Mac OS X Alpha OS AIX IRIX32 or IRIX64 or combinations of these. Other operating systems may be used. A computer in a distributed computing environment may use a different operating system from other computers.

Furthermore the computer may be connected to a network and may interface to other computers using this network. For example each computer in the network may perform part of the task of the many series of steps of the invention in parallel. Furthermore the network may be an intranet internet or the Internet among others. The network may be a wired network e.g. using copper telephone network packet network an optical network e.g. using optical fiber or a wireless network or any combination of these. For example data and other information may be passed between the computer and components or steps of a system of the invention using a wireless network using a protocol such as Wi Fi IEEE standards 802.11 802.11a 802.11b 802.11e 802.11g 802.11i and 802.11n just to name a few examples . For example signals from a computer may be transferred at least in part wirelessly to components or other computers.

The optimization of masks used for photolithographic printing of circuit designs is known in the field as optical proximity correction OPC . A fundamental idea behind OPC is to modify the mask to correct for nonidealities that occur during pattern transfer.

The a priori before the decoration selection of both fragmentation size and location based on a set of predefined rules may result in suboptimal results. In addition fragmentation results may affect both the mask error enhancement factor MEEF and mask manufacturability of the final decorated layout. Therefore what is needed is a constrained adaptive fragmentation.

One can model the mask decoration problem as a system control problem where only controls changing system outputs e.g. wafer contours are the fragments. It can be predicted that if there are not enough controls e.g. fragments the desired results may not be generated. In system theory perspective a similar problem called controllability of a system exists. For example if the system we would like to control has a linear behavior y ax b parameters are generated for any output. In the same token it is desired to find for any given layout the amount of control parameters needed.

In an algorithm an adaptive fragmentation analyzes each polygon its wafer contour light slope MEEF using the target layout and the manufacturing constraints then performs fracturing accordingly. As a result the fracturing adds more fractures where it is needed to perform enough correction controllability .

In addition the locations of sites used to compute edge placement error EPE also affects the quality of results. In system theoretic perspective this problem is known as the observability problem. As in the previous example if the underlying system is linear then we will need at least observations in two different locations. To resolve this issue oversampling of wafer contours has been used for the EPE calculation but this solution increases the computation time prohibitively. To this end an adaptive site selection method has been deployed. In essence the adaptive method decides on how many measurement sites for each fragment based on its wafer contour size location e.g. edge or corner . shows results of an adaptive method.

In scientific computations two dimensional matrix representations can be implemented as lookup tables. For example physics and image processing may use lookup tables. A finite set of values can be calculated beforehand and stored in memory to avoid real time computations. With this approach the computational burden is replaced with increased communication with the memory. In cases where these tables cannot fit into fast speed memories such as an L1 cache frequent access to these tables significantly slows down the computational speed. A technique or method provides a replacement of one or more computations with communication memory access . This is advantageous because graphics processing units have better handling of arithmetic complexity than those based on random access.

For example the nVidia 7900 series graphics processing unit at its peak can handle 24 2 4 vector 48 4 vector computations in 1 clock cycle. This is equivalent to 24 billion or 24G 4 component operations i.e. 96 Gflops. At the same time the same graphics processing unit can access memory with a peak performance of 35 Gigabytes sec access speed. Unfortunately in the case of random texture accesses this number reduces to 4 Gigabytes sec. In other words in the random access case one can perform 256 million 4 component accesses 4 Gigabytes 4 Components 4 bytes per component 256 million 4 component accesses . In other words one can replace one random 4 component texel access with 196 4 vector computations. The present application will describe this case in more detail.

This section explains the three steps for converting a two dimensional Matrix memory lookup into computations in graphics processing units. A specific implementation of steps is presented in this patent but it should be understood that the invention is not limited to the specific flow and steps presented. A flow of the invention may have additional steps not necessarily described in this application different steps which replace some of the steps presented fewer steps or a subset of the steps presented or steps in a different or alternative order than presented or any combination of these. Certain steps may be repeated as needed. Further the steps in other implementations of the invention may not be exactly the same as the steps presented and may be modified or altered as appropriate for a particular application or based on the circumstances.

By way of example a two dimensional lookup table h contains one complex number per entry. For a graphics processing unit there are two complex numbers. In this case there are four entries. An arbitrary two dimensional matrix can be decomposed into a sum of outer products of two one dimensional orthogonal functions. This can be mathematically represented as 12 Sum 1 1 2 2 .

A two dimensional lookup table can be partitioned by using a Singular Value Decomposition SVD technique.

The two dimensional lookup table that represents the sum h can be represented with 10 4 accuracy by using eight one dimensional tables. In other words by performing 16 table accesses 8 accesses per dimension the same table h can be generated. However this approach also uses 16 times more accesses to the memory.

Further simplifications can be performed if the one dimensional functions have certain properties. For example if the one dimensional functions are symmetric or skew symmetric these properties allow us to reduce the amount of data to be stored by half. Nevertheless this operation does not reduce the lookup count.

A lookup operation can be replaced with direct computation by representing each one dimensional function using a polynomial representation. In an implementation each lookup operation is replaced. In an embodiment the one dimensional bases can be represented by 20 25order polynomials. In this embodiment each lookup table can be replaced with a 20degree polynomial computation. The 20degree polynomial with constant coefficients can be programmed into the fragment program a priori.

However in this case each two dimensional lookup has been replaced with 16 eight per one dimensional function 20 320 computations multiply add operation . Although there is no lookup in this case it requires considerable amount of computation.

By way of example hk1 and hk2 can be the one dimensional functions. If the hk1 and hk2 functions are either identical to or conjugate reverse of each other the computations can be further reduced by half. In this case the total required number of computations is 8 20 160.

The computational cost can be reduced by dividing a domain of the hk1 or hk2 functions into subdomains such that in each domain as shown below a portion of the one dimensional function can be represented with a lower degree polynomial. For example by dividing the domain into 10 subregions each one dimensional function can be represented with a 3order quadratic polynomial.

By dividing the index space n1 or n2 into equal intervals the hnk1 with a lower degree polynomial can be approximated. The interval in which the given n1 or n2 values lie can be determined by dividing the index by the interval length and by using a switching operation described below . If a 3degree polynomial approximation is used the calculation cost can be reduced to 4 multiplications and a switching operation.

In other words the total cost can be reduced. In the above example the total cost can be reduced to 8 4 1 40 computations which is about 5 faster than the ones employing memory lookup operations.

Section 3 Optical Proximity Correction on Hardware or Software Platforms with Graphical Processing Units

The present invention relates to the field of electronic design automation and in particular to improved techniques for performing optical proximity correction OPC .

The manufacture of integrated circuits strives to place ever smaller features onto a given area of an integrated circuit chip. A challenge encountered in this effort to fabricate smaller features is the diffraction of the light used in photolithography. That is the quality and fidelity of the microlithography stage of very large scale integrated VLSI circuit chip production depends on the wavelength of the light source and the size of the features to be printed.

Recent subwavelength lithography approaches aim to use wavelengths that are larger than the minimum feature size to generate the images e.g. light with a wavelength of 193 nanometers is being used to generate features with dimensions of 90 65 or 45 nanometers . This approach however requires methods or techniques for correcting degradations and distortions in the final pattern caused by light diffraction. That is the photolithography mask used to generate the desired circuit pattern includes structures that anticipate and at least partially correct for the imperfections arising from striving to fabricate small features.

A computational simulation of the exposure and lithographic is run and the degradations or distortions are computed with various additions inclusions and adjustments to the mask design. A mask design is selected that improves the final structure. These methods commonly known as OPC are mainly dependent on the optical system and mask features and may be computationally intensive. While regions having densely packed features tend to be more prone to distortions the proximity effect OPC calculations are not limited to such regions and can be advantageously applied to less dense regions of the circuit.

OPC typically has numerous features in a pattern layout to be computationally processed one or more times. Recent advances in semiconductor manufacturing allow billions of transistors e.g. multibillion features to be placed on a single chip. Moore s law postulates that the number of transistors that can be placed on a single chip doubles about every 12 24 months. Unfortunately despite the advances in the central processing unit CPU clock speed and computing power the gap between the computational power required for OPC calculations and the available CPU processing power continues to increase. That is the computing power required to efficiently execute the OPC calculations in a timely manner is growing at a faster rate than the available CPU power in a reasonably priced engineering workstation.

To further complicate the issue the number of masks or layers to which OPC should be applied increases at each new semiconductor device manufacturing node. Since the features are getting smaller with every manufacturing node while the illumination wavelengths remain the same or decrease at a slower rate the number of neighboring features affecting the fidelity of each feature increases. Therefore the computational processing power required to perform OPC operations on new chip designs has been increasing at a rate of approximately factors of three or four or more for each successive manufacturing node.

Presently the generation of optically corrected masks takes from many hours to several days per mask and the complexity of this process continues to grow. Because the features printed after the OPC process may still be different from the desired features the impact of each feature on the functionality and performance of the chip is readdressed in an iterative manner. A typical VLSI design process consists of several iterations of mask generation OPC process and interpretation of the results. These iterations may contribute several months of delay to the chip qualification and manufacturing process.

The persistent time to market pressures on new chip designs mandate improved methods to estimate and shorten the impact of the OPC process in the early stages of the design. Since it is computationally prohibitive to perform many iterations of OPC on a full chip scale partial or simple model based OPC approaches are being applied in limited fashion still necessitating full chip OPC once the design is completed.

Therefore a need exists in the art for improved systems and methods that shorten the time required to perform OPC improve the accuracy of OPC methods and are scalable to address larger chip designs.

The present invention relates generally to the field of manufacturing integrated circuits and more particularly to using optical proximity correction OPC to improve the masks used for the printing of microelectronic circuit designs. Specifically the present invention relates to the execution of OPC techniques on hardware platforms software platforms or a combination of these utilizing specialized processing units.

Accordingly and advantageously the present invention relates to systems techniques and methods for the execution of OPC algorithms on hardware platforms software platforms or a combination of these with specialized processing units.

In an embodiment of the present invention spatial domain OPC computations are executed on a hardware system software system or a combination of these comprising one or more specialized processing units. Some examples of specialized processing units include central processing units CPUs graphics processing units GPUs physics processors cell processors digital signal processors DSPs field programmable gate arrays FPGAs and application specific integrated circuits ASICs . Other specialized processing units may be used. Portions of an OPC computational task may be transformed into a form of mathematical manipulations on matrices vectors or both. Graphics processing units may be particularly well suited to performing such operations on matrix and vector data.

The graphics processing unit or graphics processing units may operate on the data until the result converges on the target model within a predetermined error limit. Some examples of operations performed may include changing the shapes of mask features and may also include a detailed model of the illumination and optics systems used for exposing the pattern in the photoresist layer. The final data may be transformed back to the original data format and exported for generation of the mask used to print the pattern on the semiconductor device. Graphics processing units will be used as an example of a specialized processor but this is not intended to limit the scope of the teaching of the present invention to graphics processing units. The present invention may utilize any of the specialized processors mentioned previously and other substantially similar processors as understood by those having ordinary skill in the art and as similar or related processors may be developed later.

In an embodiment the invention is includes a computing system having at least one central processing unit and at least one graphics processing unit a user interface for interacting with the computer system a computer readable medium including data describing the size and placement of features to be formed on a photolithography exposure mask used to manufacture semiconductor devices a computer readable medium including optical proximity correction calculation procedures for acting upon the data where at least a portion of the optical proximity correction calculation procedures are executed using the graphics processing unit and output devices for displaying the results of applying the optical proximity correction calculation procedures executed using the graphics processing unit upon the data.

In an embodiment the invention is a method including providing a system having at least one central processing unit and at least one graphics processing unit separating an optical proximity correction process into tasks depending on a type of computation required allocating the tasks of the optical proximity correction process to the central processing unit or the graphics processing unit and delivering output of the central processing unit and the graphics processing unit as a result of the optical proximity corrections process.

In an embodiment a system of the invention includes a computing system including a number of nodes where each node includes at least one of at least one central processing unit or at least one graphics processing unit an interface to couple the nodes together a user interface for interacting with the computer system a computer readable medium including data describing the size and placement of features to be formed on a photolithography exposure mask used to manufacture semiconductor devices and a computer readable medium including optical proximity correction calculation procedures for acting upon the data where at least a portion of the optical proximity correction calculation procedures are executed using the graphics processing unit in one of the nodes.

The interface may be at least one of a peripheral component interconnect PCI Express bus accelerated graphics port AGP bus front side bus Ethernet the Internet or other interface that facilitates the transfer of data in any form including serial or parallel transfer of data. In an embodiment a computer readable medium having data describing a size and placement of features to be formed on a photolithography exposure mask used to manufacture semiconductor devices may be directly connected to one of the nodes and a portion of the data are passed through the interface to at least one other node. The direct connection may be by way of a different interface than how the nodes are connected. For example the direct connection may be by an integrated device electronics IDE serial advanced technology attachment SATA or universal serial bus USB interface.

In an embodiment a computer readable medium having optical proximity correction calculation procedures for acting upon the data is directly connected to one of the plurality of nodes and at least a portion of the optical proximity correction calculation procedures are executed using the graphics processing unit on a different node from which the optical proximity correction calculation procedures are directly connected. In an embodiment a computer readable medium having optical proximity correction calculation procedures for acting upon the data is directly connected to one of the nodes and at least a portion of the optical proximity correction calculation procedures are executed using the graphics processing unit of the node to which the optical proximity correction calculation procedures are directly connected.

A system of the present invention may include a computer readable medium having optical proximity correction calculation procedures to split given layout information into two dimensional subregions where these subregion overlap with each other. There may be a computer readable medium having optical proximity correction calculation procedures to transfer the given layout information split up into two dimensional subregions to two or more nodes of the system. A computer readable medium having optical proximity correction calculation procedures executing on the two or more nodes may operate on the given layout information split up into two dimensional subregions.

A computer readable medium having optical proximity correction calculation procedures to combine results from a first node and a second node on the given layout information split up into two dimensional subregions. The optical proximity correction calculation procedures may combine results by stitching together the results by removing the overlapping regions.

The present invention can be utilized in the improvement of OPC methods used in the manufacture of semiconductor devices.

Structures arising in the manufacture of microelectronic devices are typically formed by creating a pattern of a desired structure in a layer of photoresist deposited over a material in which the desired structure is to be formed. The pattern in the photoresist is created by exposing the photoresist to light through a patterned exposure mask. The exposed photoresist serves as a physical mask during a subsequent etch step or subsequent etch steps where the pattern in the photoresist is transferred to the underlying material.

Distortions and degradations in the final structure arise from a combination of factors including light source variations optical proximity effects development process nonuniformities and etch process nonuniformities among others. The total amount of energy deposited in a given volume of photoresist during the exposure or printing step will determine if that volume remains or is removed during the subsequent development process. The image features being printed on current microelectronic devices may be much smaller than the wavelengths of light being used to print the features e.g. light with a wavelength of 193 nanometers may be used to generate features with dimensions of 90 65 or 45 nanometers and below . The distortions may cause errors such as line thinning end shortening line thickening and clipping. Distortions may cause other errors.

A feature on the exposure mask is formed with the same size and shape as the desired structure on the chip. Due to the distortions described above the resulting pattern may not faithfully reproduce the pattern in the exposure mask. The distortions in this particular example may cause the final pattern to be shorter thinner and poorly controlled.

Various methods of OPC may be used to improve the fidelity of the final pattern transferred to the target material. The pattern that is formed on the exposure mask may be altered to compensate for various systematic distortions. One such method involves the use of serifs to augment the pattern in areas where the distortions cause feature shortening thinning and the like. A serif is understood to be a small feature that may be placed at a corner or vertex of a main feature. The serif may be positive in that it adds area to the main feature or it may be negative in that it subtracts area from the main feature.

A goal of the OPC process is to calculate improve and optimize at least one feature on the exposure mask so that the resulting structure realized on the chip meets the design and performance requirements of the circuit. In an implementation at least one or more features of the exposure mask are optimized. In another implementation all features of the exposure mask are optimized. When a chip has billions of transistors each with many fine structures the computational requirements for OPC can be very large.

Popular OPC methods in current use include two main classes frequency domain OPC computations and spatial domain OPC calculations.

The frequency domain FD OPC computations use Fourier transform techniques to calculate the deformation of the features on the exposure mask to realize the desired structure on the chip. There are typically several steps to this method 

FD 1. The layout is pixilated e.g. digitized as a pattern of pixels and transformed into a two dimensional frequency domain.

FD 2. The low pass filtering effects of the process such as the lens system etching characteristics and so forth are introduced.

FD 3. An inverse filtering process is applied to compensate for the low pass filtering effects introduced in the previous step.

FD 4. A two dimensional inverse filtering is applied to transform the results of these calculations back from the frequency domain into the spatial domain.

The accuracy of the frequency domain OPC calculations increases as the number of points used increases. Many points are used to include one or more of the local structures that may impact the distortion of the feature being optimized. However each of these neighboring local structures must also be optimized. The entire chip may be considered within a single calculation. However this also dramatically increases the computational requirement. Therefore this FD method has limited use.

The spatial domain SD OPC calculations are based on spatial properties of the features. The edges and vertices of the features on the exposure mask such as polygons or rectangles are modified in an effort to minimize the difference between the actual structure realized using the corrected exposure mask and the desired structure. There are several steps to this method.

The candidate control points or evaluation points on the edges and vertices are determined based on current design rules. An example of a flow is 

SD 1. For every edge or fragment of an edge an edge placement error EPE is determined by a model of the optical system. Calculations are performed using system kernels and their convolution with the exposure mask region around each edge.

SD 2. Upon determining an edge placement error an edge fragment may be pushed or pulled in an attempt to reduce the error.

SD 3. The simulations and adjustments are repeated several times for each edge fragment until the edge placement error is within the acceptable range for one or more features on the chip. In an implementation the simulations and adjustments are repeated several times for each edge fragment until the edge placement error is within the acceptable range for all features on the chip.

The spatial domain OPC methods enjoy several benefits over the frequency domain OPC methods. For example the light effects are generally localized to the features in the immediate vicinity of the feature under consideration. Therefore a size of a specific calculation may be smaller. However the same calculation is made for one or more of the feature groups on the chip.

Currently typical solutions to the OPC computational problem include the use of large systems of multi CPU computers. This increases the cost of the system and contributes to the cost of the chip. CPUs are typically designed for minimal latency and to address general purpose programs. This hardware configuration will be defined here as a homogeneous configuration meaning that the various computational tasks are executed by equivalent processors.

An alternative hardware configuration includes a cooperative collection of specialized processing units where each processing unit may be well suited for a specific type of computation. This hardware configuration will be defined here as a heterogeneous configuration meaning that the various computational tasks are executed by different typically specialized processors. As an example graphics processing units are designed specifically for high throughput on specialized types of problems found in graphics processing that perform a large number of arithmetic calculations with a relatively small number of memory access steps. Other specialized processors may be designed to handle other types of data or computational problems. Allocating the various portions of the OPC computations to specialized processors may improve the throughput increase the efficiency lower the cost and improve the results of the computation.

Graphics processing units may be designed for fast graphics processing. The data may be organized into a stream where a stream is an ordered set of data of the same data type. Operations procedures methods algorithms and the like that may be applied to entire streams of data are typically called kernels. Kernels are very efficient because they depend only on their input. Internal computations within the kernel are independent of other elements of the stream. Therefore graphics processing units may be designed for parallel processing memory efficiency and high throughput for specific problems.

Graphics processing units typically have hardware blocks that may be specifically designed for certain types of problems e.g. specific kernels may be implemented in hardware . As an example hardware blocks may be designed to implement various types of vector computations matrix computations or both. As an example graphics data is typically four dimensional referring to the channel value of the red green and blue pixels referred to as RGB and the opacity value typically referred to as alpha or A . Therefore graphics processing units have been designed to process four dimensional RGBA data very quickly and very efficiently.

Currently graphics processing units have moved to a unified architecture where there are a number of general purpose processors that can be programmed to perform a wide variety of tasks. Specialized hardware capable of performing operations very common in graphics processing exist. For example bilinear filtering dot products and antialiasing. Recognizing the usefulness of these processors for general purpose computation and the difficulty of reexpres sing non graphics applications to take advantage of the RGBA architecture of previous generation chips most graphics processing unit manufacturers are moving to a scalar architecture where only one component is processed at a time allowing for a higher utilization of the chip s resources.

CPU based approaches to improve the OPC procedures typically employ multi CPU systems as mentioned previously. Such approaches typically have attempted to increase the computational efficiency by dividing the computation into parallel parts at the task level. However they are not able to exploit additional parallelism at the instruction level due to their general purpose design.

OPC calculations are inherently graphics problems. In one embodiment of the present invention graphics data may be sent by one or more CPUs to one or more graphics processing units. The graphics processing units may be designed to efficiently implement one or more kernels for the efficient execution of the steps of the OPC method described previously. In an implementation graphics data are in the form of polygons. In an implementation graphics data are in the form of rectangles.

In an implementation the graphics processing units are programmed using traditional graphics APIs such as OpenGL or DirectX. In another implementation the graphics processing units are programmed using APIs that are designed for more general purpose calculations such as Brook from Stanford CUDA NVIDIA or CTM ATI . In modern graphics hardware there are unified shaders that can act as either vertex processors or pixel fragment processors depending on the requirements of the application. These processors are referred to as stream processors under the General Purpose graphics processing unit GPGPU APIs and their usage is similar to what it would be under the graphics APIs but without any distinction between the different kinds of processors.

 ii Allocation of unified shaders or stream processors for modification of evaluation points and their locations step SD 3 .

 iii Allocation of rasterization for determining the evaluation points based on one dimensional and two dimensional cost functions step SD 1 .

 iv Allocation of unified shaders or stream processors for intensity calculations using fast kernel lookups or fast kernel calculations step SD 2 .

 v Allocation of fragment tests such as depth tests for area query and tagging of edges and edge fragments step SD 2 . Other examples of common fragment tests that may be used include scissor tests alpha tests stencil tests blending tests dithering tests and logical operations. Other common fragment tests may also be used.

In a graphics processing unit vertex shaders or vertex processors are a programmable unit that operates on incoming vertex values and their associated data. Rasterization is the conversion of both geometric and pixel data into fragments. Pixel shaders or fragment processors are programmable units that operate on fragment values and their associated data. For depth tests for each pixel the depth buffer keeps track of the distance from the viewpoint and the object occupying that pixel. Then if the specified depth test passes the incoming depth value replaces the value already in the depth buffer.

In current architectures unified shaders have replaced pixel and vertex shaders and are capable of performing the tasks of either one. The driver generally handles allocating how many of the unified shaders are to be used as vertex shaders and how many as pixel fragment shaders at any one time. The term stream processor is used to refer to these same unified shaders but generally in the context of a general purpose graphics processing unit.

Typically the following functions may be implemented with evaluation point parallelism also known as data level parallelism 

 i Unified shaders or stream processors compute one or more evaluation points in parallel step SD 2 .

 ii Efficient use of four dimensional pixel values or other layouts as appropriate for the architecture and pixel operations for fast kernel computation step SD 2 .

Texture maps or image maps are rectangular arrays of data e.g. color data luminance data color and alpha data and the like . Texture interpolation is mathematical interpolation between texture map or image map data.

The technique applies to rectangular two dimensional and one dimensional layouts. One dimensional layouts are possible when using nVidia s CUDA architecture. Typically the following special hardware functions may be implemented for searching and region query 

A depth processor is a programmable unit that operates on incoming fragment or pixel values and their associated data. A video processor is a processor that performs video decoding or encoding operations on video data. In an implementation the processor is of a single instruction multiple data SIMD . In another implementation the processor is of a multiple instruction multiple data MIMD type.

Thus a subset of OPC calculations maps very efficiently onto typical graphics processing unit hardware and typical graphics processing unit programming features. Therefore graphics processing units may share computations with CPUs to more efficiently manage OPC problems leading to higher throughput lower cost improved efficiency and the like.

In an implementation the specific case illustrated uses an Nvidia GeForce graphics processing unit processor. The present invention may generally apply to any commercial graphics processing unit or similar device.

Trademarks are the property of their respective owners. Nvidia and GeForce are trademarks of Nvidia Corporation.

Various operations of an OPC flow are executed using a graphics processor. Some steps of an OPC flow include a geometric operation polygon fragmentation intensity calculation area search and placement error or EPE calculation. Geometric operations can be performed by a graphics processing unit. Polygon fragmentation operations can be performed by a graphics processing unit. Intensity calculations can be performed by a graphics processing unit. Area search can be performed by a graphics processing unit. Placement error or EPE can be performed by a graphics processing unit.

The graphics processor may be a single integrated circuit or multiple integrated circuits. For example one or more of the graphics processing unit components may reside on a single integrated circuit. In another implementation all of the graphics processing unit components reside on a single integrated circuit or any combination of components may reside on one integrated circuit and other components reside on one or more other integrated circuits. Also a single integrated circuit may include one or more graphics processor cores.

In a graphics processor there are one or more vertex processors which are connected to a triangle setup block. A unified shader allocated as a vertex processor is responsible for running the vertex shaders. The input for a vertex shader may be vertex data namely its position color normals and so forth. In a vertex shader code can be written for tasks such as vertex position transformation using the model view and projection matrices normal transformation and if required its normalization texture coordinate generation and transformation lighting per vertex or computing values for lighting per pixel and color computation.

The triangle set up block performs operations. The triangle set up block is connected to a shader instruction dispatch. The shader instruction dispatch performs operations. The shader instruction dispatch is connected to one or more fragment processors.

Unified shaders acting as fragment processors are where the fragment shaders run. In an implementation this unit is responsible for operations like computing colors and texture coordinates per pixel texture application fog computation and computing normals if one wants lighting per pixel. The inputs for a fragment processor this unit are typically the interpolated values computed in the previous stage of the pipeline such as vertex positions colors normals and so forth.

The fragment processor is connected to a fragment crossbar. The fragment crossbar performs operations. The fragment crossbar is connected to a stencil buffer. The stencil performs operations. The stencil is connected to one or more memory partitions.

The graphics processor may have one or more video processors. The video processor performs operations. The video processor is connected to other components. Any combination of the components shown in a graphics processor may be included in an integrated circuit. For example a graphics processing unit integrated circuit may include a vertex processor unit and a fragment processor unit. The graphics processing unit integrated circuit may include a vertex shader unit and a stencil buffer unit.

The geometric operations and polygon fragmentation step SD 1 may map to the vertex processor hardware blocks of the graphics processing unit. The intensity calculation area search and EPE calculation steps steps SD 2 through SD 4 may map to the fragment processor and depth filter hardware blocks of the graphics processing unit. EPE calculation may simply be referred to as placement error calculations especially in embodiments of the invention where edges are not used. In an implementation at least one or more of these operations map to the stream processors of the general purpose graphics processing unit languages or APIs. In another implementation all of these operations map to the stream processors of the general purpose graphics processing unit languages or APIs.

Geometric operations may be performed in the CPU e.g. outside the graphics processing unit vertex processors fragment processors or stream processors. Fragmentation operations may be performed in the CPU vertex processors fragment processors or stream processors. Intensity calculations may be performed in the fragment processors or stream processors. Area search may be performed in the fragment processors stream processors or stencil. EPE calculations may be performed in the fragment processors video processor or stream processors. In an OPC procedure any combination of these operations may be performed with each other.

For example the fragment processor may perform the geometric operations fragmentation operations intensity calculations area search and EPE calculations. In another embodiment the geometric operations and fragmentation operations may be performed by the CPU and the intensity calculations area search and EPE calculations may be performed in the graphics processing unit. In another embodiment the geometric operations and fragmentation operations may be performed by the vertex processor of the graphics processing unit and the intensity calculations area search and EPE calculations may be performed by the fragment processor of the graphics processing unit. In an embodiment one or more functions are executed on the stream processors of the graphics processing unit using a general purpose graphics processing unit language. In another implementation all functions are executed on the stream processors of the graphics processing unit using a general purpose graphics processing unit language. In an implementation the general purpose graphics processing unit language is CUDA. In an embodiment the area search may be performed in the stencil buffer of the graphics processing unit. In another embodiment the EPE calculation may be performed using the video processor. Positions of geometries of the layout may be represented in the four dimensional space RGBA format provided in the graphics processing unit. In other words a two dimensional trapezoidal shape of the data is represented as four channel data in the graphics processing unit. In specific implementations the trapezoid may be a rectangle or square. In an embodiment two opposite corners of a two dimensional trapezoidal shape of the data is represented in a RGBA color space format in the graphics processing unit. For example X1 will be R Y1 will be G X2 will be B and Y2 will be A. The graphics processing unit will operate on the data stored in such a four dimensional format.

In another embodiment X and Y coordinates for a corner a width and a height of a two dimensional trapezoidal shape of the data is represented in a RGBA color space format in the graphics processing unit. For example X1 will be R Y1 will be G W will be B and H will be A. The graphics processing unit will operate on the data stored in such a four dimensional format.

In another embodiment X and Y coordinates for a corner a change in X and a change in Y of a two dimensional trapezoidal shape of the data is represented in a RGBA color space format in the graphics processing unit. For example X1 will be R Y1 will be G delta X will be B and delta Y will be A. The graphics processing unit will operate on the data stored in such a four dimensional format.

In another embodiment X and Y coordinates for a corner an angle and a scalar of a two dimensional trapezoidal shape of the data is represented in a RGBA color space format in the graphics processing unit. For example X1 will be R Y1 will be G theta will be B and r will be A. The graphics processing unit will operate on the data stored in such a four dimensional format.

In another embodiment the data are stored as four separate one component textures or in the linear memory format exposed by CUDA.

In another embodiment the polygons are not converted to trapezoids and the data are stored as a list of vertices of each polygon. Neighborlists can be used to determine the interaction between sample points and polygons.

There representations of OPC data in a graphics processing unit are merely examples of some representations that may be used. In other embodiments of the invention other representation schemes may be used.

In an embodiment a system of the invention includes a computing system having at least one central processing unit and at least one graphics processing unit a user interface for interacting with the computer system a computer readable medium including data describing the size and placement of features to be formed on a photolithography exposure mask used to manufacture semiconductor devices a computer readable medium including optical proximity correction calculation procedures for acting upon the data where at least a portion of the optical proximity correction calculation procedures are executed using the graphics processing unit and output devices for displaying the results of applying the optical proximity correction calculation procedures executed using the graphics processing unit upon the data. The graphics processing unit may include a vertex processor unit and a fragment processor unit. The graphics processing unit may include a vertex shader unit and a stencil buffer unit.

In an embodiment there may be multiple CPUs and graphics processing units that perform the OPC calculations. A system of the invention may include multiple nodes which are connected with a high speed interface or connections between them. This interface may include for example a PCI Express bus AGP bus front side bus Ethernet or the Internet or a combination of these. Each node has one or multiple CPUs or one or more graphics processing units or any combination of CPU and graphics processing units. Each node may or may not be equipped with a secondary storage area such as a hard disk floppy CD writer or other secondary storage. OPC software of the invention may be run on any of the machines.

For example there may be a master program that runs on any subset of the nodes of the system. The master program may be executed on only one of the nodes. Data which OPC procedures of the invention will act upon may be associated with any node of the system. The master program may direct other nodes of the system to perform OPC calculations. The master program may coordinate operations of the computing system. The OPC procedures or data or both may be transferred from one node to any other node of the system. Results may then be passed back to the master program where individual results are combined.

The graphics processing units and the optical proximity correction calculation procedures may include at least one of 

Procedures for allocation of unified shaders or stream processors of evaluation points and their locations.

Procedures for allocation of rasterization for determining the evaluation points based on one dimensional and two dimensional cost functions.

Procedures for allocation of unified shaders or stream processors for intensity calculations including spatial or frequency domain approaches to calculate intensity or electromagnetic fields or a combination in air or in the other media including resist materials and on a chip surface.

Procedures for allocation of unified shaders or stream processors for intensity and electromagnetic field calculations in air and in the resist material as well as other related locations on the chip surface including memory lookups or fast kernel calculations.

Procedures for allocation of unified shaders or stream processors for intensity calculations using other methods of calculating intensity or electromagnetic fields or a combination such as convolution in frequency domain using fast Fourier transforms and inverse Fourier transforms or any other transforms to the same effect in air or in the resist material as well as other related locations on the chip surface.

Procedures for allocation of unified shaders or stream processors for intensity calculations using fast kernel lookups or fast kernel calculations.

Procedure for allocation of unified shaders or stream processors for intensity calculations using light lookups or light calculations.

Procedures for the use of a single input multiple data SIMD video processor for computing error terms.

In a specific embodiment of the present invention a procedure splits the given layout information into two dimensional subregions where these regions overlap with each other. There may be multiple such procedures running on separate nodes of a system. This information as well as whole or partial layout information is sent to each node where the nodes perform at least one OPC related calculation. The results of the calculation or calculations are collected such as at a single node where the information is stitched together by removing the overlapping regions. Stitching may be performed using a single node or multiple nodes in parallel.

In a specific embodiment a procedure includes splitting a layout into a number of nonrectangular two dimensional overlapping regions. The method splits the layout into overlapping two dimensional rectilinear or polygonal spaces sending whole or portions of the region or regions to each node. The method may perform OPC corrections or reticle corrections without sending or sharing any information between nodes. Portions or complete regional information may be provided to each node for parallel computation.

In a method or technique of the invention instead of performing calculations on an entire layout the layout is divided or partitioned into a number of subregions. In this case each subregion is two dimensional. In particular a technique partitions a layout into a number of regions or subregions. Although each region is shown as been rectangular each partition may have any shape such as square trapezoid any polygon or other shape.

According to a specific approach the data in each two dimensional subregion is operated on by one or more computing nodes of the system. As discussed above each node may include CPUs graphics processing units or both. In a specific implementation each node has a graphics processing unit which performs OPC calculations on a specific subregion of the layout. Calculations may be performed on a number of subregions in parallel which will speed up the calculations. Generally the greater the number of nodes the faster the calculations may be performed since more calculations will be performed in parallel. After a node has completed its calculations the output results can be transferred back to a calling node such as the node where a master program is running or to another specific location. Then one or more computing nodes will assemble the output results for the individual partitions together to provide the OPC calculation output for the complete layout data.

In a specific implementation of the invention each subregion is sent to a node including some overlapping region data from adjacent partitions. For example for a corner partition a subregion sent to a node will include overlap information from two adjacent sides. For an edge partition not corner a subregion sent to a node will include overlap information from three adjacent regions. For a middle partition the subregion will include overlap information from four adjacent regions. When performing the OPC calculations the nodes will use these subregions including overlap data.

In a specific implementation after the OPC calculations the output from each node will be simply the output data for the subregion itself without any overlap regions. In this case each node may have the overlap region as the input data but not in the output data. This approach may lead to more accurate results in the OPC calculations.

In a specific embodiment the computation of the lithography process simulation for OPC and RET purposes which includes the mask preparation related calculations EAPSM and AAPSM related calculations such as an electromagnetic field computation to take into account the thick mask effects the chemical processes happening during lithography processes including the exposure process the postbake process the chemical amplification process the development process all or partially computed in pixel shaders or in combination of pixel and vertex shaders.

In a specific embodiment a lookup table for light computations is broken into subsections which allow the storage in fast user controlled memory such as a local store of the SPEs on IBM s CELL chip or other user controlled memory on graphics processing units.

In an embodiment a computer system includes a server display one or more input interfaces and one or more output interfaces all conventionally coupled by one or more buses. In another embodiment a computer system includes a server display one or more input interfaces and one or more output interfaces where at least one or more components are conventionally coupled by one or more buses. Some examples of suitable buses include PCI Express AGP PCI and ISA. Other suitable buses may also be used.

The computer system may include any number of graphics processors. The graphics processor may reside on the motherboard such as being integrated with the motherboard chipset. One or more graphics processors may reside on external boards connected to the system through a bus such as an ISA bus PCI bus AGP port PCI Express or other system buses. Graphics processors may be located on separate boards each connected to a bus such as the PCI Express bus to each other and to the rest of the system. Further there may be a separate bus or connection e.g. Nvidia SLI or ATI CrossFire connection by which the graphics processors may communicate with each other. This separate bus or connection may be used in addition to or in substitution for system bus.

In an implementation the server includes one or more CPUs one or more graphics processing units and one or more memory modules. Each CPU and graphics processing unit may be a single core or multiple core unit. Some examples of suitable CPUs include Intel Pentium Intel Core 2 Duo AMD Athlon 64 and AMD Opteron . Other suitable CPUs may also be used. Some examples of suitable graphics processing units include Nvidia GeForce and ATI Radeon . Other suitable graphics processing units may also be used. The input interfaces may include a keyboard and a mouse. The output interface may include a printer.

The communications interface is a network interface that allows the computer system to communicate via a wireless or hardwired network. The communications interface may be coupled to a transmission medium not shown . In an implementation the transmission medium is a network transmission line for example twisted pair coaxial cable fiber optic cable and other transmission line. In another embodiment the communications interface provides a wireless interface that is the communication interface uses a wireless transmission medium. Some examples of other devices that may be used to access the computer system via a communications interface include cellular telephones PDAs personal computers. Other devices may also be used to access the computer system via the communications interface.

The memory modules generally include different modalities illustratively semiconductor memory such as random access memory RAM and disk drives as well as others. In various embodiments the memory modules store an operating system data structures instructions applications and procedures.

Storage devices may include mass disk drives floppy disks magnetic disks optical disks magneto optical disks fixed disks hard disks CD ROMs recordable CDs DVDs recordable DVDs e.g. DVD R DVD R DVD RW DVD RW HD DVD or Blu ray Disc flash and other nonvolatile solid state storage e.g. USB flash drive battery backed up volatile memory tape storage reader and other similar media and combinations of these.

In an embodiment specific software instructions data structures and data that implement various embodiments of the present invention are incorporated in a computer or server. An embodiment of the present invention can be tangibly embodied using a computer readable medium for example the memory and includes instructions applications and procedures which when executed by the processor causes the computer system to utilize the present invention for example the collection and analysis of data pixelating structures determining edge placement errors moving edge fragments optimizing edge fragment placements and the like. The memory may store the software instructions data structures and data for any of the operating system the data collection application the data aggregation application the data analysis procedures and the like in semiconductor memory in disk memory or a combination of these.

A computer implemented or computer executable version of the invention may be embodied using stored on or associated with computer readable medium. A computer readable medium may include any medium that participates in providing instructions to one or more processors for execution. Such a medium may take many forms including but not limited to nonvolatile volatile and transmission media. Nonvolatile media includes for example flash memory or optical or magnetic disks. Volatile media includes static or dynamic memory such as cache memory or RAM. Transmission media includes coaxial cables copper wire fiber optic lines and wires arranged in a bus. Transmission media can also take the form of electromagnetic radio frequency acoustic or light waves such as those generated during radio wave and infrared data communications.

For example a binary machine executable version of the software of the present invention may be stored or reside in RAM cache memory a mass storage device or a combination of these. The source code of the software of the present invention may also be stored or reside on a mass storage device e.g. hard disk magnetic disk tape or CD ROM . As a further example code of the invention may be transmitted via wires radio waves or through a network such as the Internet.

The operating system may be implemented by any conventional operating system such as Windows registered trademark of Microsoft Corporation Unix registered trademark of the Open Group in the United States and other countries Mac OS registered trademark of Apple Computer Inc. Linux registered trademark of Linus Torvalds . Other operating systems not listed here may also be used.

The present invention may be implemented as a method technique system or article of manufacture using standard programming or engineering techniques or both to produce software firmware hardware or any combination of these. The term article of manufacture or alternatively computer program product as used in this application is intended to encompass a computer program accessible from any computer readable device carrier or media. In addition the software in which various embodiments are implemented may be accessible through the transmission medium. For example software may be accessible from a server over the network. The article of manufacture in which the code is implemented may also encompass transmission media such as the network transmission line and wireless transmission media. The article of manufacture may also include the medium in which the code is embedded. Those skilled in the art will recognize that many modifications may be made to this configuration without departing from the scope and spirit of the present invention.

The computer system described in this application is not intended to limit the present invention. Other alternative hardware environments may be used without departing from the scope and spirit of the present invention.

This description of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form described and many modifications and variations are possible in light of the teachings above. The embodiments were chosen and described in order to best explain the principles of the invention and its practical applications. This description will enable others skilled in the art to best utilize and practice the invention in various embodiments and with various modifications as are suited to a particular use. The scope of the invention is defined by the following claims.

1. A system comprising a computing system comprising at least one central processing unit and at least one graphics processing unit 

a computer readable medium comprising data describing the size and placement of features to be formed on a photolithography exposure mask used to manufacture semiconductor devices 

a computer readable medium comprising optical proximity correction calculation procedures for acting upon the data wherein at least a portion of the optical proximity correction calculation procedures are executed using the graphics processing unit and

output devices for displaying the results of applying the optical proximity correction calculation procedures executed using the graphics processing unit upon the data.

2. The system of claim 1 wherein the graphics processing unit comprises a vertex processor unit and a fragment processor unit.

3. The system of claim 1 wherein the graphics processing unit comprises a vertex processor unit and a stencil buffer.

5. The system of claim 2 wherein the graphics processing unit further comprises a video processor unit.

The system of claim 1 wherein the graphics processing unit comprises a vertex processor unit fragment processor unit stencil buffer and video processor unit.

7. The system of claim 1 wherein the graphics processing unit comprises unified shaders a stencil buffer and a video processing unit.

8. The system of claim 1 wherein the optical proximity correction calculation procedures are shared between the central processing unit and the graphics processing unit.

9. The system of claim 7 wherein the at least one graphics processing unit is replaced by at least one of a physics processor cell processor digital signal processor or application specific integrated circuit.

10. The system of claim 1 wherein graphics processing units and the optical proximity correction calculation procedures comprise at least one of 

procedures for allocation of unified shaders or stream processors for modification of evaluation points and their location 

procedures for allocation of rasterization for determining the evaluation points based on one dimensional and two dimensional cost functions 

procedures for allocation of unified shaders or stream processors for intensity calculations including spatial or frequency domain approaches to calculate intensity or electromagnetic fields or a combination in air or in the other media including resist materials and on a chip surface procedures for allocation of unified shaders or stream processors for intensity and electromagnetic field calculations in air and in the resist material as well as other related locations on the chip surface including memory lookups or fast kernel calculations procedures for allocation of unified shaders or stream processors for intensity calculations using other methods of calculating intensity or electromagnetic fields or a combination of these such as convolution in frequency domain using fast Fourier transforms and inverse Fourier transforms or any other transforms to the same effect in air or in the resist material as well as other related locations on the chip surface procedures for allocation of unified shaders or stream processors for intensity calculations using fast kernel lookups or fast kernel calculations procedures for allocation of unified shaders or stream processors for intensity calculations using light lookups or light calculations procedures for allocation of depth filters for area query and tagging of edges and edge fragments procedures for unified shader or stream processor computation of evaluation points procedures for mapping of convolution tables as texture maps procedures for the use of texture interpolation for optimizing texture cache use procedures for the use of a depth processor for the selection of evaluation points or procedures for the use of a single input multiple data video processor for computing error terms. procedures for splitting lookup table into pieces to increase data locality. It is understood that the unified shaders could be used as either vertex or pixel shaders for these purposes although not always with equal efficiency.

11. The system of claim 1 wherein in intensity calculation procedures area search procedures and placement error calculation procedures of an optical proximity correction calculation procedure are executed using the unified shaders or stream processors of the graphics processing unit.

12. The system of claim 1 wherein in intensity calculation procedures area search procedures and optimization cost function calculations including edge placement error calculation procedures of an optical proximity correction procedure are executed using the unified shaders or stream processors of the graphics processing unit.

13. The system of claim 11 wherein geometric operation procedures of the optical proximity correction calculation procedure are executed using the central processing unit.

14. The system of claim 11 wherein geometric operation procedures of the optical proximity correction calculation procedure are executed using the unified shaders or stream processors unit of the graphics processing unit.

15. The system of claim 11 wherein geometric operation procedures of the optical proximity correction calculation procedure are executed using the unified shaders or stream processors of the graphics processing unit

16. The system of claim 11 wherein polygon fragmentation procedures of the optical proximity correction calculation procedure are executed using the central processing unit.

17. The system of claim 11 wherein polygon fragmentation procedures of the optical proximity correction calculation procedure are executed using the unified shaders or stream processors of the graphics processing unit.

18. The system of claim 11 wherein polygon fragmentation procedures of the optical proximity correction calculation procedure are executed using the unified shaders or stream processors of the graphics processing unit.

19. The system of claim 11 wherein geometric operation and polygon fragmentation procedures of the optical proximity correction calculation procedure are executed using the central processing unit.

20. The system of claim 1 wherein area search procedures of an optical proximity correction calculation procedure are executed using a stencil buffer of the graphics processing unit.

21. The system of claim 1 wherein placement error procedures of an optical proximity correction calculation procedure are executed using a video processor of the graphics processing unit.

22. The system of claim 1 wherein a two dimensional trapezoidal shape of the data is represented as four channel data in the graphics processing unit.

23. The system of claim 1 wherein X and Y coordinates for two opposite corners of a two dimensional trapezoidal shape of the data are represented in a RGBA color space format in the graphics processing unit.

24. The system of claim 1 wherein X and Y coordinates for a corner a width and a height of a two dimensional trapezoidal shape of the data are represented in a RGBA color space format in the graphics processing unit.

25. The system of claim 1 wherein X and Y coordinates for a corner a change in X and a change in Y of a two dimensional trapezoidal shape of the data are represented in a RGBA color space format in the graphics processing unit.

26. The system of claim 1 wherein X and Y coordinates for a corner an angle and a scalar of a two dimensional trapezoidal shape of the data are represented in a RGBA color space format in the graphics processing unit.

providing at least one central processing unit and at least one graphics processing unit separating an optical proximity correction process into tasks depending on a type of computation required 

allocating the tasks of the optical proximity correction process to the central processing unit or the graphics processing unit and

delivering output of the central processing unit and the graphics processing unit as a result of the optical proximity corrections process.

29. The system of claim 28 wherein the graphics processing unit comprises a vertex processor unit and a fragment processor unit.

30. The system of claim 28 wherein the graphics processing unit comprises a vertex processor unit and a stencil buffer.

32. The system of claim 29 wherein the graphics processing unit further comprises a video processor unit.

33. The system of claim 28 wherein the graphics processing unit comprises a vertex processor unit fragment processor unit stencil buffer and video processor unit.

34. The system of claim 28 wherein the graphics processing unit comprises a unified shader architecture stencil buffer and video processing unit.

35. The method of claim 28 wherein the at least one graphics processing unit is replaced by at least one of a physics processor cell processors digital signal processor or application specific integrated circuit.

allocating unified shaders or stream processors for modification of evaluation points and their locations 

allocating rasterization for determining the evaluation points based on one dimensional and two dimensional cost functions 

allocating unified shaders or stream processors for intensity calculations using fast kernel lookups or fast kernel calculations 

allocating unified shaders or stream processors for intensity calculations using light lookups or light calculations 

using unified shaders or stream processors for computation of evaluation points mapping of convolution tables as texture maps 

a computer readable medium comprising data describing the size and placement of features to be formed on a photolithography exposure mask used to manufacture semiconductor devices and

a computer readable medium comprising optical proximity correction calculation procedures for acting upon the data wherein at least a portion of the optical proximity correction calculation procedures are executed using the graphics processing unit in one of the nodes.

38. The system of claim 37 wherein the interface comprises at least one of a PCI Express bus AGP bus front side bus Ethernet or the Internet.

39. The system of claim 37 wherein the computer readable medium comprising data describing the size and placement of features to be formed on a photolithography exposure mask used to manufacture semiconductor devices is directly coupled to one of the plurality of nodes and a portion of the data are passed through the interface to at least one other node.

40. The system of claim 37 wherein the computer readable medium comprising optical proximity correction calculation procedures for acting upon the data is directly coupled to one of the plurality of nodes and at least a portion of the optical proximity correction calculation procedures are executed using the graphics processing unit on a different node from which the optical proximity correction calculation procedures are directly coupled.

41. The system of claim 37 wherein the computer readable medium comprising optical proximity correction calculation procedures for acting upon the data is directly coupled to one of the plurality of nodes and at least a portion of the optical proximity correction calculation procedures are executed using the graphics processing unit of the node to which the optical proximity correction calculation procedures are directly coupled.

a computer readable medium comprising optical proximity correction calculation procedures to split given layout information into two dimensional subregions where at least two subregions overlap with each other.

a computer readable medium comprising optical proximity correction calculation procedures to transfer the given layout information split up into two dimensional subregions to two or more nodes and

a computer readable medium comprising optical proximity correction calculation procedures executing on the two or more nodes to operate on the given layout information split up into two dimensional subregions.

a computer readable medium comprising optical proximity correction calculation procedures to combine results from a first node and a second node on the given layout information split up into two dimensional subregions.

45. The system of claim 44 wherein the optical proximity correction calculation procedures to combine results comprises stitching together the results by removing the overlapping regions.

Optical proximity correction techniques performed on one or more graphics processors improve the masks used for the printing of microelectronic circuit designs. Execution of OPC techniques on hardware or software platforms utilizing graphics processing units. Graphics processing units may share the computation load with the system CPUs to efficiently and effectively execute the OPC method steps.

Section 4 A Graphics Processing Unit based Full chip Inverse Lithography Solution for Random Patterns

An inverse lithography solution based on optimization is presented. An optimization approach operates as an inverse lithography tool based on modeling and simulation of the manufacturing process. Given the associated computational requirements the proposed solution intentionally uses graphic processors or graphics processing units as well as CPUs as computation hardware. The results are optimized towards manufacturability and process window maximization.

Optimization Graphics processors Inverse Lithography Computational Lithography Full Chip Feedback Control

In semiconductor manufacturing software simulations and correction tools have been used for the past several years to minimize lithography related yield loses and to improve printability. As the feature sizes of on chip structures shrink the physics of the lithographic process become highly complex and traditional OPC methods do not produce satisfactory results.

Studies on inverse lithography technology ILT have usually resulted in superb lithography. To date though ILT implementations in a production environment have in general proved impractical due to issues such as intractably long computer run times and nonmanufacturable mask designs. Due to the unrealistic computational requirements utilization of current ILT methods has been limited to processing small portions of layouts. In addition the ill conditioned behavior of high fidelity process models commonly utilized in traditional OPC makes it hard to use with ILT. This has been a factor to use an approximation for the inverse lithography limiting accuracy. Approaches that handle mask manufacturability constraints after a mask has already been synthesized are inherently prone to nonmanufacturable or suboptimal results. Pixel based approaches are ILT methods. Their computational and memory requirements are proportional to the grid density. Since the sufficient computational resources have not existed these solutions generally sacrifice fidelity for run time.

A microlithography process used in a manufacture of chips can be a projection process using a fixed monochromatic light source. An aim of this operation is to print an exact copy of the desired two dimensional pattern called a layout L onto a wafer usually scaled by 4 . The light source shines light through a mask M and exposes an image on a wafer bottom of the image covered with light sensitive material called photoresist. The mask M carries the two dimensional information about the desired pattern. In the non diffraction limited case the mask is very similar to the original layout L in an ideal case it is a 4 bigger version of the layout L .

After a prescribed exposure called the dosage an image of the features in the mask is formed in the photoresist material by photo chemically altering the properties of the material. To generate the pattern the wafer goes through a development step where the exposed resist is removed from wafer and the unexposed areas remain. The contours boundaries are expected to match the desired shapes in layout L.

As feature sizes of on chip structures shrink the fundamental physical limits of traditional lithography impact design performance. Below 180 nanometers the size of on chip elements falls below the 193 nanometer wavelength of light used to print those elements on silicon. At these subwavelength dimensions the light passing through the diffraction limited projection system as well as the properties of the resist and the development process result in a severe distortion of the patterns printed on the silicon compared to those created by the designer. Distortion effects impact pattern fidelity and in a worst case can even eliminate patterns entirely. Even relatively slight pattern distortions can result in non functioning silicon. Consequently manufacturers have resorted to applying corrections otherwise designs will experience large yield losses due to inaccurate image replication.

Toward this end silicon foundries are beginning to augment traditional computational lithography techniques with additional capabilities. Recently a promising new approach Inverse Lithography Technology ILT has caught the attention of semiconductor manufacturers. It has long been thought that the best theoretically possible mask design can be achieved by considering the design of masks as an inverse problem. That is to find an optimal mask for a given process solve the inverse problem using a rigorous mathematical approach.

Previous methods developed to date are impractical in a production environment due to intractable run times nonmanufacturable masks or both. Recently some commercialization effort has been done but to date a great number of ILT implementations in a production environment have proved impractical for random logic circuits due to intractably long computer run times and as a consequence the use of computational shortcuts that jeopardize converging to an optimal solution.

Nevertheless ILT demonstrations have usually resulted in superb lithography. Despite the practical limitations the masks generated generally result in superior accuracy and better pattern fidelity.

Today some fabrication houses employ CPU clusters comprising several hundred to several thousand processors as a part of their current computational lithography requirements. A practicable ILT solution should not require more than this many processors. A comparison of commonly employed computational hardware platforms in suggests that graphics processing units would be the best choice for computational lithography related modeling and simulation tasks.

Unfortunately graphics processing unit programming is in its infancy requiring specific algorithms developed for a given problem e.g. there is no universal tool that compiles a given sequential technical computing software for graphics processing unit hardware . For each given problem graphics processing unit specific algorithms utilizing the parallelism in the hardware are developed to achieve an attractive performance advantage. A fundamental reason for this is that legacy algorithms are sequential e.g. serial in nature and originally written for a latency centric CPU implementation. On the other hand graphics processing units are highly parallel processing engines and require different algorithms. By utilizing specialized hardware such as the texture interpolators as well as critical data organization techniques selected to maximize locality to leverage the multi cache graphics processing unit memory architecture we have been able to utilize the 4 TFLOP compute power of graphics processing units of the type found in a commodity desktop computer for lithography related computations.

In an implementation to estimate printed contours the software simulates one or more steps of the printing process including exposure and resist development. The parallelized graphics processing unit implementation can be used for this forward path lithography system modeling and a CPU graphics processing unit implementation of the optimization algorithm can be used in the feedback loop. The following section briefly explains the models used to perform this task. In another implementation to estimate printed contours the software simulates all steps of the printing process including exposure and resist development.

First the simulator runs with a given mask and projection lithography settings. A two dimensional intensity map of the absorbed energy in the photoresist is generated. Next using the two dimensional intensity map an etching process is simulated to determine how at least one pattern will print and where the contours e.g. the boundary between the fully dissolved photoresist and the un dissolved resist material will form. The difference between the as produced contours and the desired contours is used to compute the fidelity or error norm of the mask.

In an implementation a lithography process simulator models more physical phenomena than before to accurately capture the salient features that are utilized for the advanced nodes.

Mask related issues and an image on or inside the photo sensitive layer over the wafer resist can be modeled using a closed form integration given using Hopkins formulation. A main idea is to convert the equations into a four dimensional convolution between the transfer function of an optical system with a mask function M where TCC f g f g f g is a band limited function dependent on lithography settings including the Numerical Aperture NA collection angle light source coherence and light source shape.

A process model simulates processing steps done to generate contours on a wafer surface. In resist latent image calculation is used which accounts for defocus and high NA effects. The post exposure bake model models acid and base reactions separately. A density based development model is employed which accounts for development rate change with density. Similarly a light slope based development model is used to account for line end shortening. To account for wafer etch effects a model a density and solid angle based model is used that contains a constant term sum of Gaussian functions and an ion projection term.

A model uses three dimensional mask thick mask effects approximating more accurate Electro Magnetic Field EMF solvers using domain decomposition based approaches. The Gaussian rounding based model includes mask manufacturing effects such as corner rounding and offset.

A typical requirement for the nodes beyond 45 nanometers may be that the lithography simulator should generate outputs at sampling points of 1 20 of a wavelength to capture requisite variations. For advanced nodes such as 22 nanometers this corresponds to a 6 7 nanometer sampling size. Considering a chip of size 25 mm 25 mm a total number of sampling points where output data should be calculated can be 17 10. For a conservative 16 kernel Hopkins light intensity calculation and very efficient convolution of the order 5N log N a computational complexity is approximately 16 5 17 10 log 17 10 10floating point operations. If implemented on a high performing CPU available today with a very efficient convolution implementation a performance is about 5 10flops second. Therefore a total time for a single core CPU is 10 5 10 2 10seconds. Even with a 1000 CPU core cluster this number is 6 hours. In an implementation when employing an iterative mask synthesis or correction algorithm these computations are repeated in every step. If an ILT optimization loop requires 100 iterations for convergence just the forward path simulation would take 600 hours. Any additional phenomena such as latent image generation and process model further increase the computational complexity.

The mask synthesis process described here can be treated as an optimization problem. That is based on the modeling given above a mask synthesis problem can be converted into a constraint minimization problem. As indicated earlier the feedback loop designed around the forward litho simulation path is to modify the mask such that the printed image is as close as possible to the desired image.

In an implementation a mask synthesis is done in four stages using an error norm as part of a feedback loop. A specific implementation of stages is presented in this patent but it should be understood that the invention is not limited to the specific stages flow or steps presented. A flow of the invention may have additional stages not necessarily described in this application different stages which replace some of the stages presented fewer stages or a subset of the stages presented or stages in a different or alternative order than presented or any combination of these. Certain stages may be repeated as needed. Further the stages in other implementations of the invention may not be exactly the same as the stages presented and may be modified or altered as appropriate for a particular application or based on the circumstances.

In a first stage a pixelized mask Mis synthesized. In an implementation each pixel s transparency varies continuously between an mand m where mis a lower boundary for a final pixel value and mis an upper boundary for the final pixel value.

In a second stage Mis converted to M. In an implementation Mis converted to Mby pushing the pixel values towards either mor m but not exactly set to either mor myet. During this process a new cost function including initial terms and secondary binarization terms may be used.

In a fourth stage the almost binary Mis clipped to generate a binary function which minimizes F more details below .

In an implementation in each stage of the mask synthesis at least one proper learning algorithm is employed. In an implementation proper learning algorithms such as conjugate gradient or steepest descent based optimization algorithms are employed. A search space is selected as complex Fourier coefficients of a mask M. These values are modified through finding the impact of each of these coefficients.

During a line search frequencies of the mask are changed by computing a first derivative of a cost function. In an implementation an initial condition selected for the optimization section changes from stage to stage. In a first stage a low pass filtered version of a desired layout L is selected as the initial condition. For a second and third stage a result from the previous stage has been used as the initial condition.

An overall fitness function F In an implementation at each stage of the optimization a following cost function is used to determine a fitness of any given mask M. 1 1 

where Fis a continuous mask transmission fitness function and can be used to compute how well contours generated from mask M fit to target layout L. In an implementation this function has several components. To account for effects of process conditions during the optimization error fitness of mask M is computed in four focus exposure conditions and at nominal ideal conditions and their effect is combined with different weights 

Fis a binary fitness function and can be used to binarize the mask. After the initial phase of the optimization which produces the continuous transmission mask Mc the optimization loop starts binarizing continuous mask Mc. This can be achieved by drifting a transmission value of each pixel based on a warp function. For each pixel value this center peak has been adjusted at the beginning of the binarization stage. This function has two important properties 

Fis a mask fitness function and can be used to complete the binarization process. During the optimization since the transmission of each pixel is modified these values can go below minimum value mand beyond maximum value m. Although this produces a solution this infeasible solution is expected to be far from the feasible binary solution which then produces a suboptimal result. In an implementation to prevent this from happening an Ffunction finds pixels which have transmission values bigger than mor smaller than mand computes the sum of the squared differences. In an implementation the Ffunction finds all pixels which have transmission values bigger than mor smaller than mand computes the sum of the squared differences. In other words it computes a distance measure where each individual pixel can be viewed as a dimension by using the following equation 2 

As discussed earlier for advanced node devices the forward path lithography simulations alone require enormous computational horsepower. An optimization loop as described above adds to this requirement. Therefore from a practicability perspective utilizing the available 1000 GFLOP computational horsepower per graphics processing unit is a very attractive option compared to that of a single core CPU of 20 GFLOP.

To demonstrate the efficacy of this approach random logic standard cell layouts as well as repetitive structure memory designs were utilized. With a repetitive SRAM example we emphasize preserving certain properties of an original design while generating an inverse mask finding similar patterns and applying similar ILT for consistency reasons. As an option the approach has the capability to obey the built in hierarchy definitions.

Similarly an objective for selecting random logic designs is to demonstrate a full chip processing power of the approach which generates the ILT results for every individual feature.

The particular random logic layout we report here is a 45 nanometer design. The 10 mm 10 mm chip was partitioned into smaller tiles of size 15360 nanometers 15360 nanometers . The stepper and process conditions are the wavelength 193 nanometers NA 1.35 light source C quad with 0.53 0.98 200 defocus 100 nanometers and 5 intensity variation.

In a specific implementation we ran this layout on our 17 graphics processing unit farm containing 17 Intel CPU cores 17 Nvidia GTX 295 graphics processing units 16 GB main memory and 1 TB hard disk drive on each desktop running under Linux Open Suse 11.1 operating system. Stage 2 bottom up hierarchical data processing was used. The ILT processing of this full chip took 122.4 hours. Given the linear scaling feature of our solution it would use a 200 graphics processing unit 200 CPU core computer cluster to complete the task overnight e.g. less than 12 hours.

To study the additional speed improvements due to the hierarchical data processing we enabled this feature and recorded the processing speeds. Random logic pattern of size 10 millimeters 10 millimeters with hierarchical data processing capability with both top down and bottom up stages enabled took 22.3 hours on the abovementioned 17 graphics processing unit cluster e.g. a 5.4 times faster processing.

The studies we conducted under Section 4.7.1.2 represent one of the slowest possible runtimes. The speed improvements due to the data hierarchy are highly layout repetition dependent. For the case we report in for example when both top down and bottom up stages enabled the ILT processing was 8.3 times faster compared to the flattened case.

FIGS. .A .F show several random logic and repetitive structure full chip cases. shows a carve out from an original random logic implementation of a standard cell. shows the layout of the standard cell in after the ILT processing. shows a smaller portion of the layout of the standard cell in for a better view. shows the layout of after the ILT processing. shows a carve out from the original SRAM layout. shows the layout of after the ILT processing.

FIGS. .A .F show a specific progression of an optimized process illustrated for a simple layout. In the figures the representative layout has been used to illustrate the progression of the mask synthesis optimization scheme.

In an implementation a particular layout is of size 3591 nanometers 2598 nanometers using 32 kernels at the wavelength 193 nanometeres and NA 1.35 used 173 seconds processing time with the 1 graphics processing unit 1 CPU core desktop computer.

A new modeling technique or method to accurately represent mask and wafer process behavior is presented.

In an implementation a lithography simulation can be done in three steps 1 mask simulation 2 latent image calculations and 3 resist process simulation. Leading edge designs such as 32 nanometers and beyond smaller dimensions than 32 nanometer technology require higher fidelity models to adequately represent each of these actual processes. The effects that are previously considered secondary have become more pronounced at the advanced technology nodes.

Mask distortion issues due to the limitations in manufacturing can be modeled ahead of time and can be included in a design of layouts to achieve a better optimization. In an implementation a mask model has two main components material and manufacturing effects. For the material effects EMF grade solvers perform well but computational requirements are heavy. Similarly the manufacturing effects are approximated to a certain degree. In the present invention an adaptive nonlinear mapping algorithm models remaining effects that are not modeled by existing approximations.

Wafer distortions may be due to limitations in an optical system as well as to properties of the resist and development process. Among the various effects the post exposure bake and development process model mismatches once considered negligible need to be addressed even for the OPC tasks for the advanced nodes.

In an implementation a modeling approach combines two components physical models and nonlinear mappers. To model physical phenomena separate models may be used. For the behavior that is not completely captured by these physical models an adaptive nonlinear mapping algorithm can be developed and used.

In an implementation physical model parameters are calibrated by a genetic algorithm. Nonlinear mapper model parameters are identified by a gradient descent method. The present invention will demonstrate an improvement using real process data.

Given the computational requirements for a practical solution graphics processors as well as CPUs are used as computation hardware.

Lithography simulation can be done in three steps 1 mask simulation 2 latent image calculations and 3 resist process simulation. The leading edge designs such as 32 nanometers and beyond require higher fidelity models to adequately represent each of these actual processes. Effects that were previously considered secondary have become more pronounced at the advanced technology nodes.

Mask distortion issues due to the limitations in manufacturing can be modeled ahead of time and can be included in a design of layouts to achieve a better optimization. In an implementation a mask model has two main components material and manufacturing effects. For the material effects EMF grade solvers perform well but computational requirements are heavy. Similarly the manufacturing effects may be approximated to a certain degree. In the present invention an adaptive nonlinear mapping algorithm is presented that models the remaining effects that are not modeled by the existing approximations.

A physical model can use three dimensional mask thick mask effects approximating more accurate Electro Magnetic Field EMF solvers using domain decomposition based approaches. Also included is the Gaussian rounding based model for various mask manufacturing effects such as corner rounding and offset. A thick mask effects simulator can be designed to handle any type of binary chromeless or attenuated phase shift with programmable attenuation masks.

Wafer distortions may be due to limitations in an optical system as well as to properties of the resist and development process. Among various effects the post exposure bake and development process model mismatches once considered negligible need to be addressed even for the OPC tasks for the advanced nodes.

To estimate printed contours the software simulates one or more steps of the printing process. In an implementation this includes exposure and resist development. A parallelized graphics processing unit implementation for this forward path lithography system modeling and a central processing unit CPU graphics processing unit GPU implementation of the optimization algorithm used in the feedback loop can be used. The following section briefly explains the models used by the Gauda Lithography Simulator GLS to perform this task. All Gauda manuals including users manuals and other product information is incorporated by reference.

First a simulator runs with a given mask and projection lithography settings. Two dimensional intensity maps of an absorbed energy in a photoresist are generated at various slices. Using the two dimensional intensity maps an etching process is simulated to determine how patterns will print and where contours e.g. a boundary between a fully dissolved photoresist and an undissolved resist material will form. A difference between the produced contours and the desired contours is used to compute the fidelity or error norm of the mask.

An image due to a given mask on or inside a photo sensitive layer over a wafer resist can be modeled using a closed form integration using the Hopkins formulation. A main idea is to convert the equations into a four dimensional convolution between a transfer function of an optical system with a mask function M. In order to eliminate irregularities in a light source Kohler based illumination can be used in an optical path. Imaging characteristics of the light passing through the mask M are described with a double integration. That is Hopkins showed that the light intensity I f g a normed square of the electric field E can be calculated as 1 

where TCC f g f g f g is a band limited function dependent on lithography settings including the Numerical Aperture NA collection angle light source coherence and light source shape. A finite size of the collection lens means it can only collect the frequency components of the light up to a finite limit. This allows the system to be modeled by a low pass filter whose cutoff frequency is NA where is the wavelength of the light source.

A process model can simulate processing steps to generate contours on a wafer surface. In an implementation a threshold model is used. In the simplest form a threshold model a point is considered dissolved if the light intensity at that point exceeds the threshold value. In an implementation a more sophisticated model applies a sum of Gaussian blurring to simulate an impact of several processing steps and applies a variable threshold function based on the intensity its derivatives and also mask density. An in resist latent image calculation is used which accounts for defocus and high NA effects. A post exposure bake model represents acid and base reactions separately. In an implementation a density based development model is employed which accounts for development rate change with density. In an implementation a light slope based development model is also used to account for line end shortening. To simulate the postexposure bake process a model that separately accounts for acid and base diffusion is used. 0 0 2 

where S x y is a solvent distribution G 0 is a two dimensional Gaussian distribution I x y is a latent image intensity at a given depth z is a base percentile with respect to a maximum solvent concentration and represents a convolution operation. A development model can use the solvent distribution to determine areas where the resist material is left. The remaining resist material thickness at a given point x y can be determined as 3 

where tis a development time and . . . is a development rate. Even though the actual development rate changes nonlinearly with solvent the remaining resist material thickness can be represented as 

where Cis a development rate change with respect to density Cis a development rate change with respect to gradient of latent image L x y is a circuit layout density and . . . is a linear development rate function.

To account for wafer etch effects a density and solid angle based model can be used that contains a constant term sum of Gaussian functions and an ion projection term. The ion projection term can be the most significant term in the model representing the nonlinear etch bias.

Neural networks can be used in engineering to mimic the parallelism and massive interconnectivity in the human brain. Towards building a computation mechanism based on neural networks it is helpful to understand the structure of the brain. It is estimated that the human brain has over 10neurons. These neurons receive incoming signals from other neurons through a matrix of connection weights called the synapses. The neural dynamics are mainly determined by this connection matrix and in many instances it is necessary to change the connection strengths to facilitate new functions of the network. This changing phase is called learning.

The artificial neural networks are a simplified representation of this behavior to model engineering systems. shows a basic neural network structure. . shows inputs nodes an input layer hidden nodes an output layer and an output node. In the figure xare input signals tare weights of the link connecting node i to node j and ware weights of the output layer.

The incoming signals are propagated to the output node by using the following calculations. The inputs to the hidden nodes are weighted by the input layer as . . .

For a static nonlinear mapping function an output of a hidden node can be obtained by using a sigmoid function. shows a graph of a sigmoid function.

Given input output training data the weights can be adjusted to represent a nonlinear mapping between these two sets of data provided that the neural network is designed to approximate to a required accuracy.

Adaptive optical proximity correction algorithms improve computational efficiency and complexity mask design for a target accuracy. Further these adaptive algorithms can involve strictly local operations making it ideally suited for SIMD single instruction multiple data parallel hardware such as graphics processing units GPU .

The present invention relates to the field of electronic design automation and in particular to improved techniques for computationally efficient and accurate optical proximity correction. Further adaptive sampling and adaptive fragmentation algorithms in the present invention can be suited or used for computations with SIMD processors such as graphics processing units.

The manufacture of integrated circuits strives to place ever smaller features onto a given area of the integrated circuit chip. One challenge encountered in this effort to fabricate smaller features is the diffraction of light used in photolithography. That is the quality and fidelity of the microlithography stage of very large scale integrated VLSI circuit chip production depends on a wavelength of a light source and a size of the features to be printed.

Recent subwavelength lithography approaches aim to use wavelengths that are larger than the minimum feature size to generate images e.g. light with a wavelength of 193 nanometers can be used to generate features with dimensions of 90 65 or 45 nanometers . This approach however typically uses methods for the correction of degradations and distortions in the final pattern caused by light diffraction. That is the photolithography mask used to generate a desired circuit pattern includes structures that anticipate and precorrect for imperfections arising from fabricating small features.

A computational simulation of the exposure and lithographic is run and the degradations or distortions are computed with various additions inclusions and adjustments to the mask design. A mask design is selected that improves the final structure. These methods commonly known as optical proximity correction OPC are mainly dependent on the optical system and mask features and may be computationally intensive. While regions having densely packed features tend to be more prone to distortions the proximity effect OPC calculations are not limited to such regions and can be advantageously applied to less dense regions of the circuit.

OPC typically involved modeling numerous features in a pattern layout to be computationally processed one or more times. Recent advances in semiconductor manufacturing allow billions of transistors e.g. multibillion features to be placed on a single chip. Moore s law postulates that the number of transistors that can be placed on a single chip doubles about every 12 24 months. Unfortunately despite the advances in the central processing unit CPU clock speed and computing power the gap between the computational power required for OPC calculations and the available CPU processing power keeps increasing. That is the computing power required to efficiently execute OPC calculations in a timely manner is growing at a faster rate than the available CPU power in a reasonably priced engineering workstation.

To further complicate the issue a number of masks or layers to which OPC should be applied increases at new semiconductor device manufacturing nodes. Since the features are getting smaller with every manufacturing node while the illumination wavelengths remain the same or decrease at a slower rate the number of neighboring features affecting the fidelity of each feature increases. Therefore the computational processing power and accuracy required to perform OPC operations on new chip designs has been increasing at an enormous rate.

Presently the generation of optically corrected masks takes from many hours to several days per mask and the complexity of this process continues to grow. Further as feature density increases the proximity effects become more pronounced and hence the accuracy of simulation becomes very critical. Since features printed after an OPC process may still be different from the desired features the impact of each feature on the functionality and performance of the chip is readdressed in an iterative manner. A typical VLSI design process consists of several iterations of mask generation OPC process and interpretation of the results. These iterations may contribute several months of delay in the chip qualification and manufacturing process.

The persistent time to market pressures on new chip designs mandate improved methods to estimate and shorten the impact of the OPC process in the early stages of the design. Since it is computationally prohibitive to perform many iterations of OPC on a full chip scale partial or simple model based OPC approaches are being applied in limited fashion still necessitating full chip OPC once the design is completed.

Therefore a need exists in the art for improved systems methods and techniques that shorten a time required to perform OPC improve the accuracy of OPC methods and that are scalable to address larger chip designs.

The present invention relates generally to the field of manufacturing integrated circuits and more particularly to using optical proximity correction OPC to improve a mask used for the printing of microelectronic circuit designs. Further the present invention relates to increasing accuracy of OPC techniques while minimizing computational effort.

Accordingly and advantageously the present invention relates to adaptive OPC algorithms for hardware or software platforms.

An algorithm may include computation of optimal sampling points for light calculations for accurate representation of a light profile inflection points for deciding a number of fragments and length and position of the fragments for minimizing the number of fragments for a target accuracy. The final data may be transformed back to the original data format and exported for generation of the mask used to print a pattern on a semiconductor device.

An embodiment of the present invention can be readily utilized in the improvement of OPC methods used in the manufacture of semiconductor devices.

Structures arising in the manufacture of microelectronic devices are typically formed by creating a pattern of a desired structure in a layer of photoresist deposited over a material in which the desired structure is to be formed. The pattern in the photoresist is created by exposing the photoresist to light through a patterned exposure mask. The exposed photoresist serves as a physical mask during a subsequent etch step or steps where the pattern in the photoresist is transferred to the underlying material.

Distortions and degradations in the final structure can arise from a combination of factors such as light source variations optical proximity effects development process non uniformities and etch process non uniformities among others. A total amount of energy deposited in a given volume of photoresist during the exposure or printing step will determine if that volume remains or is removed during the subsequent development process. The image features being printed on current microelectronic devices may be much smaller than the wavelengths of light being used to print the features e.g. light with a wavelength of 193 nanometers is being used to generate features with dimensions of 90 65 or 45 nanometers and below . The distortions may cause errors such as line thinning end shortening line thickening or clipping and the like.

Various methods of OPC may be used to improve the fidelity of the final pattern transferred to the target material. The pattern that is formed on the exposure mask may be altered to compensate for various systematic distortions. One such method involves the use of serifs to augment the pattern in areas where the distortions cause feature shortening thinning and the like. A serif is understood to be a small feature that may be placed at a corner or vertex of a main feature. The serif may be positive in that it adds area to the main feature or it may be negative in that it subtracts area from the main feature.

A goal of the OPC process is to calculate improve and optimize one or more features on an exposure mask so that a resulting structure realized on the chip meets design and performance requirements of the circuit. In an implementation the OPC process calculates improves and optimizes all features on an exposure mask. Clearly when a chip has billions of transistors each with many fine structures the computational requirements for OPC can be very large.

Current solutions to a typical optical proximity correction problem can be classified in two main classes frequency domain and spatial domain.

Frequency domain OPC computations use transform techniques to calculate new shapes of the features on an exposure mask to realize a desired structure on a chip. The convolution computations are replaced by multiplication operations in a frequency domain on a uniform grid structure. An accuracy of the frequency domain OPC calculations increases as the number of the grid points increases. Many points can be used to include one or more of a local structure or structures that may impact the distortion of a feature being optimized. Each of these neighboring local structures can also be optimized. The entire chip can be considered within a single calculation. However this also dramatically increases the computational requirement. In an implementation many points must be used to include all structures that may impact the distortion of the feature being optimized. In an implementation each of these neighboring local structures must be optimized.

Spatial domain OPC calculations are based on the spatial properties of features. Edges and vertices of features on an exposure mask such as polygons or rectangles are modified in an effort to minimize the difference between the actual structure realized using the corrected exposure mask and the desired structure.

Spatial domain OPC methods may enjoy several benefits over the frequency domain methods. For example the light effects are generally localized to features in the immediate vicinity of the feature under consideration. Therefore a size of a specific calculation may be smaller. However the same calculation is made for one or more of the feature groups on the chip. In an implementation the same calculation is made for all feature groups on the chip.

A typical solution to improve OPC accuracy would be to either increase a number of the sampling points or to perform a rule based local refinement. Both approaches may have issues. In the former case the computational effort increases tremendously since the computational complexity is of the order O n e.g. proportional to n n where n is the number of points. In the later case the accuracy improvement is neither provable nor guaranteed.

An alternative approach may be to use adaptive sampling and fragmentation which provides an accurate OPC algorithm which has an improved accuracy and yet minimizes computational effort for a target accuracy.

Accuracy of an OPC computation may depend on a sampling location in a fragment where an objective function such as EPE edge placement error is sampled. In an implementation an accuracy of an OPC computation depends on the sampling location in each fragment where an objective function such as EPE is sampled. In an implementation for the best mask layout these sampling points are located where the objective function assumes an extremum value e.g. a location where a slope of the objective function along the fragment is zero.

Further to make sure at an extrema in a layout there is at least one sampling point initial fragmentation is done by inserting a fragment between at least one pair of consecutive inflection points inflection points are the points where curvature of the objective function along the line changes its sign . By such a fragmentation scheme the extrema will have a sampling point since whenever there is a change of curvature sign of a continuous function then it may assume an extremum value between the inflection points.

In an implementation to make sure at every extrema in the layout there is at least one sampling point initial fragmentation is done by inserting a fragment between each pair of consecutive inflection points. In this implementation it is guaranteed that at every extrema there is a sampling point.

Accuracy of an OPC computation may also depend on a size and location of a fragment in addition to a location of a sampling point. The following describes two approaches to accomplish adaptive fragmentation. In one approach an objective function is minimized subject to configurational and mask constraints by computing a sensitivity of the objective function to movements of fragment ends. left out 

 i Refine in locations where these jumps are large. This may indicate that the objective function is varying rapidly and hence requires finer discretization. Refinement can be accomplished inserting a fragment between two consecutive fragments when there is a large normal movement jump between an original pair of fragments.

 ii Unrefine or coarsen in locations where these jumps are small. This may indicate that the objective function variation is slow and hence does not need as much refinement. Coarsening can be accomplished by merging a pair of fragments.

In an implementation an adaptive fragmentation computation is performed iteratively until the aggregate objective function sensitivity vanishes in the former case and a normal fragment movement jump is below a certain user defined threshold in the later case.

In an implementation a combined algorithm of adaptive sampling and adaptive fragmentation is a min max algorithm. In this implementation the objective function is maximized in at least one fragment to obtain optimal sampling points and the aggregate objective function is minimized to obtain optimal fragmentation. In an implementation the objective function is maximized in each fragment to obtain optimal sampling points.

In an implementation all the operations are local. In this implementation this algorithm is ideal for distributed computing which may typically be the case. In another implementation one or more operations are local. The parallel nature of algorithms nicely fits into the parallel hardware found in graphics processing units for that matter any SIMD processing unit. In an implementation to accomplish this list of sampling points objective function is stored either as texture or global memory in a linear array. In an embodiment at least three points are used for evaluating optimal sampling locations. In this embodiment of the invention to compute an optimal location for sampling locations three values of the objective function from the current locations e.g. two from current fragment and one sampling point from the next fragment are transferred into a kernel along with the positions and then the optimal location is computed.

In the case of global memory the computed location can be updated. In the case of texture memory the computed optimal location may be first stored in a temporary buffer and at the end the calculation buffer is swapped with the texture memory. This may similarly apply for the case of adaptive fragmentation. In this case as in the case of adaptive sampling computations may be local.

Also since a number of sampling points and fragments are minimal for a given accuracy this algorithm is computationally efficient. Further since a number of fragments are minimal this may result in a minimal complexity mask resulting in cost and manufacturing efficiencies.

Section 7 Instruction Set Architecture based Hardware and Software Platform for Electronic Design Automation EDA 

The present invention describes a platform in which electronic design automation EDA algorithms can be described independently from underlying hardware software HW SW components and executed efficiently. This platform may facilitate and enable porting of electronic design automation algorithms to various hardware software platforms. Further this may be done without any need for compilation or major restructuring. This platform may be composed of an Instruction Set Architecture ISA that is specifically developed for an Electronic Design Automation algorithm or algorithms a scheduler a synchronizer a load balancer other requisite hardware software components for computations or any combination of these.

Current hardware software platforms used in the electronic design automation area typically rely on operating systems and software languages for both operation and performance. Commonly algorithms are tightly integrated with the underlying operating system OS and the specific language in which the algorithm has been coded. For example a vast majority of the electronic design automation algorithms are implemented on UNIX LINUX operating systems with the C C programming language. Although it fulfills the functional requirements of a VLSI chip design flow it may not produce optimum results due to limitations of the underlying hardware platform software platforms or hardware and software platforms such as the CPU or operating system. Since Electronic Design Automation algorithms are generally tailored for a specific hardware software platform converting them into new or different architectures such as Digital Signal Processors DSPs Field Programmable Gate Arrays FPGAs or Graphical Processing Units GPUs is extremely difficult and cumbersome without rewriting or restructuring entire computations.

Despite advances in CPU performance and speed over the years computational requirements of a chip design have been increased to an even faster rate necessitating new and improved methods other than single or multi threaded CPU utilization. The first examples of this shift in the industry have been observed with hardware simulation engines which convert an RTL description of a chip into a connected network of Field Programmable Gate Arrays to improve the simulation speed by about 100 fold.

Recently several EDA algorithms such as Design Rule Checkers and Extraction type of back end related geometric algorithms have been modified to work with a farm of CPUs e.g. several hundred CPUs in some cases . These efforts may require a total restructuring of existing computation methods for a specific farm of CPUs e.g. loosely connected CPU architecture . With ever changing hardware architectures a more efficient method technique or system is needed to map an algorithm or algorithms to a new hardware software architecture.

In a parallel processing system instead of having software carried out sequentially one instruction at a time several different entities of a computational scheme can be executed simultaneously.

An example from the personal computer PC realm is to use the CPU for calculations while using another entity of the program for handling the data input output I O and reading data into memory without intervention of the CPU.

 i Processes This component can execute an algorithm and can also manipulate resources in order to fulfill a mission of the algorithm. Furthermore in an implementation several processes can run on the same hardware or several hardware connected to each other. In an implementation the processes execute a given algorithm and manipulate all the requisite resources in order to fulfill the mission of the algorithm.

 ii Hardware This is a resource that can be used to execute a given process. In an embodiment of the present invention this can be one or more central processing units graphics processing units Field Programmable Gate Arrays or Digital Signal Processors or any combination of these properly connected.

 iii Schedulers This unit can determine when a process runs on which hardware platform it runs and in what order it is supposed to run. A scheduler may be control a single computation engine or several engines clustering .

In an embodiment the scheduling can be done by assigning a priority to each process. When several processes are in a queue the process with a highest priority runs on the hardware. In another embodiment Earliest Deadline First scheduling is employed to assign tasks to individual elements of computational engines to calculate a given EDA related task. The tasks can be assigned to individual elements such as one or more graphics processing units Digital Signal Processors or central processing units or other components.

 iv Synchronizers This unit can operate in conjunction with schedulers and monitors and controls the access of processes to resources. Depending on the design a synchronizer may allow only one single process to use a given resource at a time or it may allow several processes access to a given resource in a given order of priority.

 v Context Switching The scheme can be used to switch from one computational resource to another one. In an implementation such a specific unit is required. In this implementation an execution stack memory area and values contained in registers when last executing this process etc. can be preserved for continuity.

 vi Load Balancing When a multiplicity of hardware resources are used for computations a proper distribution of computations to the available resources may be implemented. This assignment can be done in the beginning or certain processes may be migrated from one computing resource to another one during its execution.

 vi Command Pipelining One or more computational steps in a given algorithm can be executed using different computational resources. Some examples of these computation resources are a central processing unit graphics processing unit Field Programmable Gate Array or Digital Signal Processor. A distribution of these small steps into an available hardware resource is the core of a parallel processing system. Command pipelining is a methodology that controls this by determining independent pieces of a given computational scheme.

A Virtual Machine VM is an abstract computing machine and a main feature of a Virtual Machine is its portability. With this capability one can use a program and execute it on various platforms without having to recompile.

The portability can be achieved in several layers. In a first layer programming software is developed such that variable types instruction set and encodings are defined independently of the underlying hardware software execution system. In a second layer the manner in which the instruction set is packaged at a class level e.g. binary encoding is defined in a machine independent fashion. In a third layer a core set of runtime classes and an associated set of platform specific native code abstract the interface between a Virtual Machine program and the underlying hardware software execution system.

A compiler transforms a Virtual Machine program into a set of instructions. The Virtual Machine interprets the instructions in order to run the program. A Virtual Machine can be called an interpreter. In addition the code can also be compiled straight or directly into native machine binary code.

The type of work a processor carries out can be defined by its set of instructions. These instructions are usually coded in binary and may depend on the processor s architecture.

Most modern processors have built in instructions specifically designed for certain applications such as audio and video processing. An example of this would be the MMX MultiMedia eXtension technology which Intel Corporation uses in its Pentium architecture. This special set of instructions allows for faster processing of audio and visual algorithms.

A method technique and apparatus to execute at least one electronic design algorithm using a set of instruction set architectures specifically designed for at least one phase of a electronic design process is described. An advantage of the present invention is that it yields more efficiency than other platforms such as a general purpose CPU based system.

The present invention discloses an Electronic Design Automation specific hardware and operating system independent architecture to program and execute at least one Electronic Design Automation computation. In an implementation is unnecessary to make drastic modifications such as restructuring and recompilation in the event of underlying hardware software or task changes. In an implementation the requisite EDA computations are executed without making drastic modifications.

The architecture can be based on an Instruction Set Architecture approach that can be applied to general purpose CPU architectures. An x86 Instruction Set Architecture architecture has been a core of personal computers. Once compiled for the x86 architecture a program can be executed on various hardware supporting this instruction set without compilation. Although this provides flexibility the x86 type Instruction Set Architecture has a limitation of being tightly coupled to the hardware architecture e.g. CPU .

A methodology of the present invention handles the design problems efficiently in the electronic design automation area.

Although the Instruction Set Architecture instructions might be different for several steps of the electronic design automation the Instruction Set Architecture based platform approach can unify the way to handle the problem.

In an implementation a hardware software platform includes a virtual machine and at least one component of a parallel processing system. In an implemenation the hardware software platform further includes components such as a scheduler or load balancer.

An Instruction Set can be designed to execute specific electronic design algorithms efficiently. In addition it can provide a description of one or more steps of an electronic design automation algorithm independent from an underlying hardware software execution platform.

An execution unit may combine reorder distribute or a combination of these the execution of the instructions based on capabilities of the underlying hardware software system to achieve an optimum performance. A sequence of instructions from selected Instruction Set Architectures can be executed on any platform supporting the Instruction Set Architecture without any modifications or reprogramming.

In an embodiment the graphics processing unit hardware and driver software with a graphics processing unit specific scheduler are utilized as platform components. In another embodiment the graphics processing unit hardware with Pixel and Vertex Shader Virtual Machines of DirectX are employed. Scheduling tasks can be casted to existing schedulers in the DirectX and graphics processing unit hardware.

In another embodiment the execution can be performed on a single CPU hardware with operating system and in another embodiment the graphics processing unit hardware with Pixel Shader Virtual machine is used.

Specific instructions sets can be utilized to accommodate a different nature of electronic design automation design phases such as Design Rule Checking DRC or Optical Proximity Correction OPC . Other design phases may also be used. This may unify the overall design process under a set of instructions. As a result a typical design task may be significantly simplified.

Similarly an Instruction Set Architecture based algorithm execution can provide flexibility to an electronic design engineer to decide on an execution platform based on execution needs of the design tasks.

Since electronic design tasks and computations are specific and speed of execution e.g. the time required to complete a specific task is important selection of an instruction set and an execution platform may not be trivial. The Instruction Set Architecture based approach provides faster design cycles and also allows design optimization for cost performance etc.

Since characteristics of tasks for typical VLSI design phases may be quite different from each other specific instruction sets may be developed for one or more phases. In an implementation specific instruction sets are developed for each phase. Some examples of these phases are routing layout timing analysis OPC calculation and design rule checking.

From a hardware standpoint the actual mechanism of the hardware can be hidden from a user. In this scenario the user deals only with parameters and memory models.

From a programmer s point of view electronic design automation and TCAD algorithms are to be written by using the instructions available.

In an embodiment the following set of instructions are used for accessing the graphics processing unit central processing unit hardware platform 

Section 8 Optimal Implementation of Computational Algorithms on Hardware Software Platforms with Graphical Processing Units

Type of functions self contained electronic device that can store and play data which can be in various media formats has wireless capacity to communicate data transfer. Media may be a signal such as an audio video image or any combination of these. Data may be stored in a memory unit such as a hard drive or a flash memory. Data may be a standard format such as MPEG MP3 JPEG or non standard. A battery operated device may have a display screen such as LCD or OLED. It may contain a card reader for data transfer.

A critical issue with a mobile system is the battery life. As feature sets constantly evolve power optimization becomes highly critical. Feature sets are usually associated with new developments in the radio frequency RF section and computation hardware such as central processing unit CPU core processors digital signal processors audio and video processors graphic processors communication processors and display lighting systems.

Today in a typical mobile device there is a power conversion unit which downconverts typically 3.6V battery output to 1.2V to conserve energy. Given their efficient power conversion DC DC buck converters may be preferred over linear regulators which work at around 40 efficiency. This section usually supplies power to the computation hardware.

A second system to consider is the radio frequency section. This section may include several different communication systems such as Bluetooth 802.11 Ethernet wireless LAN or 3G cellular system. Power requirements for the radio frequency section are different from those for the computational hardware because of the signal quality requirements. In order to achieve a better signal to noise ratio most radio frequency circuits operate from a 3V or 3.3V supply. In general current consumption of RF circuits usually runs much lower than the computation hardware.

Recent developments in the computation hardware area indicate that existing software is not written to benefit from the potential. Even though parallel environments such as multiprocessor and multicore platforms are being introduced performance of existing applications is not improving proportionally. To address this issue the existing software needs to be rewritten to utilize parallel computation capabilities in the new platforms.

As a consequence of this in an implementation all the software may have to be parallelized. In another implementation some software may have to be parallelized.

An approach may be to write a universal compiler and doing this automatically. Unfortunately today there is no compiler technology to parallelize a given software efficiently. Parallel compilers have been studied for more than 30 years and to this day there is no generic load balancing or scheduling technology that works efficiently for any given platform and for any given software.

In the present patent application a method technique and system to utilize existing computational capacity in mobile devices optimally is described. The method technique or system executes on a mobile hardware software system. The system typically includes a computation hardware such as graphical processing unit GPU Digital Signal Processors DSP or a CPU.

In an embodiment the hardware software system is composed of a hardware platform containing a radio frequency section central processing unit Digital Signal Processor graphical processing unit and an operating system such as Microsoft Windows Symbian Palm and any other requisite software.

The present invention exploits not only the task level but also fine grain instruction level parallelism of the hardware while utilizing high data bandwidth and parallel memory architecture. By distributing tasks optimally to the available hardware we achieve optimal hardware utilization to improve performance of at least one application minimization of power consumption improvement of system stability when executing multi tasks.

In an implemenation a dedicated hardware approach may be employed. In another implementation multiutilization for each hardware unit may be employed.

In an embodiment graphics processing units are utilized for display communication audio video signal processing and data decryption.

In another embodiment an audio digital signal processor is utilized for audio signal processing and for communication decoding.

The parallel nature of many mobile computations nicely fits into the parallel hardware found in graphics processing units. Specialized hardware existing in graphics processing units allows certain tasks to be performed in a parallel fashion much faster than the general purpose CPU architectures.

The present invention describes an optimization of source and mask with full chip capability. In an implementation a simultaneous optimization of source and mask with full chip capability is performed. To provide full chip processing capability a solution can be based on graphics processing units GPUs as well as central processing units CPUs and made scalable to a number of clusters while maintaining convergence. In an implementation at least one graphics processing unit and at least one central processing unit is made scalable to a large number of clusters. An approach can use a proprietary search algorithm to converge to an optimal solution in the sense of print quality maximization while obeying existing mask manufacturing lithography equipment and process technology constraints. A solution can be based on a proprietary optimization function that is applicable to both binary and phase shift masks.

Section 9.2. Keywords Source Mask Optimization Graphics Processors Inverse Lithography Computational Lithography Full Chip Genetic Search Process Window.

A generation of lithography steppers with customizable light source profiles can be used to extend the life of 193 nanometers wavelength lithography. A yield of a VLSI design for 32 nanometers and below can be improved to production levels with simultaneous source and mask optimization. This approach has not been widely applied in the field due to a variety of technical issues including i intractable computer run times and ii nonmanufacturable masks are synthesized.

Previous source and mask optimization approaches are computationally expensive. Using a suboptimal solution which selects a small subset of the layout and optimizes the light source shape accordingly has had a limited business and technical success. Presently there is no practical solution that addresses needs for full chip source mask optimization SMO . Fabrication houses can employ clusters comprising up to several hundred to several thousand processors. In an implemenation a feasible source mask optimization solution does not use more than this many processors. Compared against commonly employed computational hardware platforms it is clear that GPUs would be the best choice for computational lithography related modeling and simulation tasks.

Graphics processing units programming typically uses specific algorithms developed for a given problem. For example there may not be a universal tool that compiles given sequential technical computing software for a graphics processing unit hardware. For a given problem graphics processing unit specific algorithms utilizing the parallelism in the hardware may be developed to achieve an attractive performance advantage. By utilizing specialized hardware such as the texture interpolators as well as critical data organization techniques selected to maximize locality to leverage multicache graphics processing unit memory architecture an optimization algorithm may be designed to use graphics processing units as well as CPUs as computation hardware for a source mask optimization approach.

One way to formulate a simultaneous optimization of a light source profile and mask shape of a full chip integrate circuit layout layer can be a min max optimization problem max min 1 

where sis a source variable mis a mask variable of an ipattern and . . is a generalized function representing a printing quality for the ipattern whose variables can be a process window PW mask error enhancement factor MEEF or edge placement error EPE and others. In an implementation the ipattern can have its own print quality function . . to allow for different compromises.

This formulation can be viewed as finding one or more worse patterns among one or more patterns and maximizing their printing quality. Optimizing a source shape for a set of critical patterns might create a new set of critical patterns. In this case in an implementation the mask shapes may be optimized simultaneously. A shape may be critical or may not be critical.

In an implementation all shapes are critical. In another implementation not all shapes are critical. The critical shapes in a lithographical sense such as dense layouts and minimum feature shapes are likely the ones that predominantly determine the shape of the source. A technique for for selecting and weighting the shapes is described below.

In the present invention a method technique or system to determine a source shape for a full chip layout is described per the methodology in this patent application. Further a source mask optimization method technique or system for selected shapes is also described. We present an SMO optimization method for all the selected shapes in this patent application.

A goal of a source mask optimization method for full chip integrated circuit layouts is simultaneous modification of both source shape and mask features to ensure that one or more shapes in a target layout L are printed with a particular printing quality. In an implementation the particular printing quality is the maximum printing quality possible. A modification method can be applied to one or more shapes in the layout to guarantee the best results. Unfortunately just the modification of the mask shapes for a fixed source shape S known as optical proximity correction may be very computationally intensive. Furthermore inverse lithography technology ILT which may provide better results may be even more computationally intensive requiring an even larger number of computational resources than traditional OPC.

In lithography a light source shape may be selected that maximizes printing quality of user selected layout portions. However this approach can lead to poor printing quality because the user cannot always select the layout portions necessary for a globally optimal result.

In an implementation of the present invention a critical feature selection method is described that uses existing integrated circuit layout data hierarchy. There may be many shape repetitions in integrated circuit layouts such as bit cells for memory structures as well as logic gates.

A main idea behind this step is to identify unique shapes within an integrated circuit layout. A unique shape can be defined as a shape. This shape can be a polygon or part of a polygon having zero or more shapes within a predefined vicinity ambit and having a unique configuration in the two dimensional space. The unique shapes and their neighbors can define one or more shapes that are used to compose a given integrated circuit layout. These shapes can be considered as the basis functions of a given integrated circuit layout. Therefore an optimization of a light source profile and mask shapes may have the same quality of printing everywhere in the integrated circuit layout. In an implementation an optimization of a light source profile and mask shapes guarantee the same quality of printing everywhere in the integrated circuit layout. In another implementation an optimization of a light source profile and mask shapes may have the same quality of printing in at least two portions of the integrated circuit layout.

Two main reasons behind this motivation are i to shorten turn around time and ii to improve the fidelity of results e.g. repeated shapes are decorated identically to control variability in wafer contours .

In an implementation all unique shapes are the critical shapes. In another implementation one or more of the critical shapes are not a unique shape. In this implementation since not all the unique shapes are the critical shapes a heuristic method can be used to sort the basis shapes with respect to their criticality. In an implementation a heuristic method uses cell instance statistics e.g. a number of occurrences sizes etc. and cell characteristics e.g. a number of lithographically critical shapes distribution of the different width and pitches etc. gathered from a hierarchical integrated circuit layout representation. Not all shapes may contribute to the print quality. The densest shapes may dominate. In addition there may not be a single source shape that would optimize all the shapes in the layout.

This step can be viewed as ranking of unique shapes. In an implementation after this process is completed one can make an informed decision to exclude the shapes that are not critical and optimize the source profile for the remaining shapes. In an implementation to achieve a truly global optimum at the expense of increased computational cost all the unique shapes are used to design a source profile. A unique shape finding algorithm is presented in this patent application. This approach handles size adjustments for the ambit region to handle the SMO cases.

A strategy for ranking of unique shapes and selection of critical ones may be dependent on printability requirements and process variations. In an implementation commonly accepted measures such as normalized image light slope NILS and its variation within the expected CD may be used. Similarly a selection of gauging points or CD measurement locations may also affect the printability. The proposed ranking function uses the following sensitivity measure

where P is a number of gauge points i 1 2 . . . N where Nis a number of unique shapes M is a mask error enhancement factor MEEF function and is a normalized image light slope function which are defined as

where l S M is a light intensity distribution on a wafer e.g. calculated by using transmission cross coefficients TCC and a light source shape S and is a minimum width or spacing of a shape surrounding Gin either x or y direction. A selection of gauge point Gcan be based on one or more edges of a critical shape polygon.

A mask error enhancement factor term M can determine a sensitivity of a unique shape to mask manufacturing issues and a normalized image light slope term can define the sensitivity to a process variation. Many improvements to the ranking formulation can be made to represent the manufacturing specifics. For example in an implementation stepper settings are used.

After the r . . term is computed a subjective weighting can be applied to guide the selection process. In an implementation a frequency and distribution of dense shapes in unique shape configurations is used to calculate a rank 

In another implementation frequency and distribution of one or more dense shapes in one or more unique shape configurations are used to calculate the rank.

A selection of critical shape configurations M is done by a thresholding criteria. For example in an implementation a shape complying to S M where is a threshold is selected as a critical shape.

An optimization algorithm may consist of light source and mask shape synthesizers as well as an initialization stage. shows a block diagram of a proposed source mask optimization methodology.

To guide an optimization algorithm and provide better convergence properties an initialization step may be added. In this step both an initial source shape S and an initial decorated mask M are generated. In an implementation the initial source shape is generated before the initial decorated mask. In another implementation the initial decorated mask is generated before the initial source shape. In yet another implementation the initial source shape is generated substantially simultaneously with the initial decorated mask.

This algorithm can be implemented in two stages. In an implementation in each stage the lithography simulator running on graphics processing unit clusters is utilized for contour generation. In another implementation in one or more stages the lithography simulator running on graphics processing unit clusters is utilized for contour generation.

Stage 1 Given T and M find an initial source shape S that maximizes over one or more parameters of a given light source shape and its combination as described as explained in this patent application. As another example stage 1 can be Given T and M find an initial source shape S that maximizes over the parameters of given light source shapes and their combinations.

Stage 2 Given Sand M find a decorated mask M that maximizes the using inverse computations as described in this patent application.

In Stage 1 of the initialization the seed source shape parameters can be searched by using a parametric search algorithm. In an implementation one or more parameters such as inner outer quasar angle for one or more known source shapes such as annular quasar quadrupole dipole and their linear combinations are searched. In an implementation during these searches it is assumed that the source has a flat top profile. In other words the points that produce light always produce the same amount of light per solid angle independent of their location. To find a global solution the following genetic algorithm based search method is developed.

In an implementation while no more improvements or max iteration count is reached for each iteration i 

 i Generate a new generation for at least one offspring Owhich contains the following information light source type parameter . . . parameter where j 1 2 . . . N.

During this step the algorithm may utilize the mutation and cross breeding statistics as well as the strategy to generate new offspring.

 ii.c Compute for at least one gauge point gby using CDand TCCwhere p 1 2 . . . P some being implemented on the graphics processing unit based litho simulator cluster.

In another implementation while no more improvements or max iteration count is reached for at least one iteration i 

 i Generate a new generation for each offspring O which contains particular information. This information can be light source type parameter . . . parameter where j 1 2 . . . N.

During this step the algorithm may utilize mutation and cross breeding statistics as well as the strategy to generate new offspring.

 ii.b For each gauge point gin gauge set G compute wafer contours and critical dimension CD values CD using

 ii.c Compute for each gauge point g by using CDand TCCwhere p 1 2 . . . P all being implemented on the graphics processing unit based litho simulator cluster.

In an implementation to speed up this stage a parallel genetic algorithm is implemented on graphics processing units in addition to the graphics processing unit based litho simulator. Due to the parallel nature of the computation in this algorithm a mapping to a graphics processing units platform is done such that for each offspring in each generation the cost function is computed in parallel in each graphics processing units core in the cluster.

A convergence rate and a quality of the results in genetic algorithms may depend on the strategy used to generate and select the offsprings. In an implementation the following two steps can be used for this purpose.

 i Selection of candidates for next generation The present approach describes using a tournament selection method for selecting candidates by using the . . value of an offspring. A main advantage of this method is that the mating pool e.g. the pool of offsprings that is used for generation has a higher average fitness than the average population fitness. Performance advantages of this method in noisy fitness functions having modeling inaccuracies just like in the light shape search problem are superior.

 ii Generation of offsprings using mating pool An elitist method with high probability of mutation and crossover has been applied.

The computational complexity of a source shape initialization algorithm can be very high if special care is not taken. A new light source shape parameter is calculated for at least one offspring O which might require generation of at least one TCC coefficient. In addition a forward path lithography simulation for at least one critical shape C may be required to estimate the . . .

In an implementation new light source shape parameters are calculated for each offspring O which might require generation of TCC coefficients each time. In addition the forward path lithography simulation for each critical shape C is required to estimate the . . . For example for a full chip case a number of critical shapes may be in 1000s. In these types of nonlinear cost functions a required number of offsprings could be in 1000s and a typical solution may require 1000s of iterations. These assumptions suggest that the TCC coefficients and light simulations would be repeated 10times.

To reduce a number of computations e.g. requisite computations the following two observations are made.

 i A result of the initial light generation stage is just a seed that shall be used for optimization. Therefore the actual shape needs not to be exact. In this implementation the actual shape is not exact.

By using these observations we first perform a subsampling in the parameter space. For example if we search the parameter space of inner outer quasar angle with ten samples per parameter a total of 10 10 10 1000 samples is generated. These sample points do not need to be uniform. In an implementation these sample points are uniform. In another implementation these sample points are not uniform. Then the light profiles for each critical shape are computed. Following the example 10TCC and light computations shall be performed for each critical shape and the total light intensity computations can be reduced to a 10range. Assuming that 4 6 samples per parameter should suffice for a good approximation the total TCC and light intensity computations can be reduced to a 10range.

In an implementation during an iteration for at least one offspring O a light intensity is approximated by interpolating intensities from the closest parameter samples. In another implementation during each iteration for each offspring O a light intensity is approximated by interpolating the intensities from the closest parameter samples. For example if the parameter set has three variables the closest eight samples are used to estimate the light intensity value. Therefore for each offspring O the intensity computations can be reduced to simpler interpolations. Assuming that second to third order polynomials suffice to approximate the light value the total computational load for each light intensity can be reduced to 10s of multiplications.

However 10 . . computations may still be required. By restricting a size of the critical area a number of light interpolations can be further reduced. For example if an optical proximity ambit of 1 2 m is selected and the light intensities are computed with 10 nanometer spacing the total number of light intensities per . . is in the order of 100 100 10000s. Therefore the total computation is in the order of a number of . . computations a number of light intensity samples intensity interpolation computations 10 10 10 10floating point operations per second FLOPS .

On today s typical graphics processing units 10computations can be done in one second i.e. 1000 GFLOPS . Even on a single graphics processing unit desktop computer with 8 graphics processing unit cards computations can be completed within one hour. To complete similar types of calculations only on central processing units with 20 GFLOPS per core a system with a few hundred central processing unit cores is required.

In a second stage of initialization an initial decorated mask M can be synthesized using a seed source shape S found in the previous stage. A simplified version of an inverse method is utilized to find both the decorated shapes as well as the assist features SRAFs . Given the required computational complexity of these algorithms an embodiment of the present invention describes an approximate version which uses simplified light and process models. The calculations are computational complex.

 iii.b Compute intensity values mask error enhancement factor slopes for each gauge point gfor each process condition k 

In another implementation step iii.b can be Compute intensity values mask error enhancement factor slopes for at least one gauge point gfor at least one process condition k.

In an implementation a source mask optimization method employs an iterative algorithm. In an implementation in each iteration two separate optimization problems are solved sequentially as in the initialization algorithm and the result of each stage is fed to the next stage. In another implementation in at least one iteration at least one optimization problem is solved sequentially with another optimization problem. In this implementation a result of at least one stage is fed to another stage.

In a first stage of at least one iteration for a given fixed mask M computed from the previous iteration a light source shape S that maximizes the process window is searched. A pixelized light source space is utilized for facilitating the search. Due to the nonlinear nature of the light source shape modifications in at least one step may be constrained. In at least one iteration only light pixels that are within a given vicinity of the existing group of pixels are modified.

In another implementation in a first stage of each iteration for a given fixed mask M computed from the previous iteration the light source shape S that maximizes the process window is searched. A pixelized light source space is utilized for facilitating the search. Due to the nonlinear nature of the light source shape modifications in each step are constrained. At each iteration only the light pixels that are within a given vicinity of the existing group of pixels are modified. In addition some new groups may be generated in random locations outside the existing pixel groups.

 i Given a pixelized source shape S continuous transmission mask M halo thickness h and shape modification strategy 

 iii.a Generate a new generation at least one offspring O contains the following information source Shape S halo thickness shape modification strategy and fitness value.

 i Given a pixelized source shape S continuous transmission mask M halo thickness h and shape modification strategy 

 iii.a Generate a new generation each offspring O contains the following information source Shape S halo thickness shape modification strategy and fitness value.

To select and generate the offsprings a strategy similar to the one outlined in section Section 9.6.1.1 can be used.

Following the discussion in section 9.6.1.1 10TCC coefficients may be calculated and 10 10 10light intensities for this algorithm may be converged. Note that unlike Section 9.6.1.1 the TCC coefficients may not be predictable. However the following specific property of the designed algorithm allows us to reduce the computations for light intensities a variation in a light source profile between generations may be restricted to a few pixels. By using the superposition principle incremental light values are computed efficiently by the Abbe formulation.

Given a light source S a synthesis of the mask shapes M can be done. A method simultaneously optimizes mask shapes SRAF shapes and locations. The method can utilize a continuous transmission and nonpixelized mask representation to perform an initial search. The method can apply a legalization binarization mask constraints gradually by modifying the continuous tone continuous shape mask towards manufacturable mask transmission values e.g. 0 1 for binary and 0 1 1 for phase shift and mask shape constraints such as minimum spacing minimum area etc. In an implementation in a step of the source mask optimization process the following strategy can be used for the mask.

In general terms a mask synthesis can be done in two stages using an error norm as a part of a feedback loop 

 i In a first stage a pixelized mask M where each pixel s transparency varies continuously between an mand m is synthesized where mand mare the lower and upper boundaries for the final pixel value respectively.

 ii In a second stage Mis converted to M by pushing the pixel values towards either mor m but not exactly set to either mor myet. During this process a new cost function including initial terms and secondary binarization terms may be used.

In an implementation in at least one stage of the mask synthesis a conjugate gradient based optimization algorithm is employed. In another implementation in each stage of the mask synthesis a conjugate gradient based optimization algorithm is employed. A search space is selected as the complex Fourier coefficients of the mask M. These values are modified through finding the impact of each of these coefficients.

where F a continuous mask transmission fitness function is used to compute how well the contours generated from the mask M fit to the target layout L. This function may have several components. For example to account for the effects of process conditions during the optimization we compute error e.g. fitness of the mask M in four focus exposure conditions and at nominal ideal conditions and combine their effect with different weights.

F a binary fitness function is used to binarize the mask. After the initial phase of the optimization which produces the continuous transmission mask M an optimization loop starts binarizing the continuous mask M. In an implementation this can be achieved by drifting a transmission value of at least one pixel based on a warp function. For at least one pixel value the center peak is adjusted at a beginning of the binarization stage. In another implementation this can be achieved by drifting the transmission value of each pixel based on a warp function. For each pixel value this center peak is adjusted at the beginning of the binarization stage. This function has two important properties 

F a mask fitness function is used to complete the binarization process. In an implementation during the optimization a transmission of at least one pixel is modified. Since a transmission of at least one pixel is modified this value can go below a minimum value m and beyond a maximum value m. Although this produces a solution this infeasible solution is expected to be far from the feasible binary solution which then produces a sub optimal result. To prevent this from happening the Ffunction finds at least one pixel which has a transmission value bigger or greater or larger than mor smaller or less than mand computes a sum of the squared differences. In other words it computes a distance measure where at least one individual pixel can be viewed as a dimension.

In another implementation during the optimization the transmission of each pixel is modified. Since the transmission of each pixel is modified these values can go below a minimum value m and beyond a maximum value m. Although this produces a solution this solution is expected to be far from a feasible binary solution which then produces a suboptimal result. To prevent this from happening the Ffunction finds all the pixels which have transmission values bigger than mor smaller than mand computes a sum of the squared differences. In other words it computes a distance measure where each individual pixel can be viewed as a dimension. This algorithm is computational complex.

In this section simultaneous source mask optimization results are presented. In a 22 nanometer example a contact layer is selected to illustrate a progression of a methodology. As the printability function . . we have selected the product of dose and defocus tolerances under the constraint that the edge placement error should be less than 10 .

FIGS. . . show an example of a shape processed according to a specific embodiment of the invention. shows an original layout M. After a hierarchical analysis critical patterns in were identified. shows these critical patterns. By using these critical shapes the light source profile shown in is generated. shows a final decorated mask using the optimized light source profile. shows a final make after the inverse lithography technology. As a result of this optimization the printability function . . was improved by about 11 compared to the optimized quasar light source.

A method technique or system of an embodiment of the present invention is described that improves the printability of a given integrated circuit layout. In the method technique or system a simultaneous source profile and mask shape optimization algorithm may be used to improve the printability of a given integrated circuit layout. In an implementation an automated method guarantees source mask optimization optimality for a given layout by identifying the critical shapes the unique shapes and their neighboring shapes. This implementation may use a ranking methodology for optimizing a printability function. The present invention can be extended to include source profile manufacturability constraints and mask error enhancement factor.

This description of the present invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form described and many modifications and variations are possible in light of the teaching above. The embodiments were chosen and described in order to best explain the principles of the invention and its practical applications. This description will enable others skilled in the art to best utilize and practice the invention in various embodiments and with various modifications as are suited to a particular use. The scope of the invention is defined by the following claims.

