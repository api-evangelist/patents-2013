---

title: System and method of variable filter length local tomography
abstract: Methods, processes and systems of image reconstruction using variable filter length local tomography, for reconstructing internal body images in medical applications, and the like. The system and method of the present invention utilizes less radiation and less computer power than the prior art, without using iteration algorithms so that all target sizes from large to small can be reconstructed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08929637&OS=08929637&RS=08929637
owner: iTomography Corporation
number: 08929637
owner_city: Barker
owner_country: US
publication_date: 20131114
---
This invention was made with government support under NSF National Science Foundation award DMS 0806304 and DMS 1211164. The government has certain rights in this invention.

This application claims priority to co pending U.S. patent application Ser. No. 13 722 383 entitled Variable Filter Length Local Tomography filed Dec. 20 2012 the contents of which are herein incorporated in their entirety.

This invention relates to image reconstruction and in particular to methods processes and systems of image reconstruction using variable filter length local tomography for reconstructing internal body images in medical applications and the like.

Recognition of the dangers of ionizing radiation has become more focused over time. The recent focus on reducing dose became more urgent with the advent of cardiac Computed Tomography CT . See for example Raff G. L. Radiation dose from coronary CT angiography Five years of progress. Journal of Cardiovascular Computed Tomography 2010 4 365 374. These are inherently high dose procedures. Attempts to reduce dose include adaptive iterative reconstructions and modulating the tube potential during the scan.

See for example Sato J. M. Akahane. S. Inano et al. Effect of radiation dose and adaptive statistical iterative reconstruction on image quality of pulmonary computed tomography. Jpn J Radiol 2012 30 146 153 and Park Y J Kim J W Lee et al. Automatic Tube Potential Selection with Tube Current Modulation APSCM in coronary CT angiography Comparison of image quality and radiation dose with conventional body mass index based protocol. Journal of Cardiovascular Computed Tomography 2012 6 184 190.

Suppose one is interested in reconstructing a region of interest ROI inside a patient. In our case the ROI is the cardiac region. Conventional also known as global reconstruction requires that the entire cross section of the patient be irradiated. This means that during the scan one has to transmit x rays through parts of the patient located far from the ROI. In the past 10 15 years a group of algorithms called Local Tomography LT was developed. See for example Ramm A. and A. Katsevich The Radon transform and local tomography CRC Press Boca Raton Fla. 1996 and Katsevich A. Improved cone beam local tomography Inverse Problems 22 2006 . 627 643.

The main idea of LT is based on transmitting only those X rays through the patient that intersect the Region of Interest ROI inside the patient. The X rays that do not pass through the ROI are blocked from reaching the patient which results in a reduction of the dose of a CT scan.

Conventional Computed Tomography CT reconstructs the distribution of the x ray attenuation coefficient inside the object being scanned. Normally is measured in Hounsfield units. Local Tomography LT computes not but B where B is some operator that enhances singularities of e.g. edges . Thus the information about the actual values of inside the ROI is not recovered.

In two dimensions the main mathematical basis for LT is provided by the following two formulas A and B 

where tilde over f is the Fourier transform of f Fis the inverse Fourier transform and g represents the CT data.

The fact that the first formula A contains only one integral demonstrates that LT reconstruction is local. The presence of the growing factor in the second formula proves that LT enhances edges. The useful property of LT which also follows from the second equation is that it preserves all geometric features inside the ROI. In other words the sharp features of e.g. location of edges coincide with sharp features of B . See for example Ramm A. and A. Katsevich The Radon transform and local tomography CRC Press. Boca Raton Fla. 1996 and Faridani A. K. Buglione P. Huabsomboon et al. Introduction to local tomography Radon transforms and tomography. Contemp. Math. 278 Amer. Math. Soc. 2001 pp. 29 47. Thus in some sense LT is close to the gradient of the true image f.

In the cone beam setting e.g. in helical scanning the situation is more complicated. The reason is that B may add sharp features that are not present in . See for example Katsevich. A. Cone beam local tomography SIAM Journal on Applied Mathematics 1999 . 2224 2246. This manifests itself as artifacts. However it was shown by one of the subject inventors that by choosing an appropriate direction of filtering one can significantly reduce the strength of the artifacts and potentially reduce dose. See for example Katsevich A. Improved cone beam local tomography Inverse Problems 22 2006 627 643.

In classical cone beam LT the convolution kernel is very short because it is equivalent to computing some kind of derivative on the detector. See for example Louis A. K. and P. Maass Contour reconstruction in 3 D X ray CT IEEE Transactions on Medical Imaging 12 1993 764 769 and Katsevich A. Improved cone beam local tomography Inverse Problems 22 2006 627 643.

A main disadvantage of LT is that LT images look different from conventional CT images which may result in a loss of diagnostic information. Since LT emphasizes edges and does not reconstruct in Hounsfield units it is sometimes hard to differentiate between tissue types and even see the presence of contrast.

A primary objective of the present invention is to provide methods processes and systems for image reconstruction of internal body images in medical applications and the like which allows for both differentiation between tissue types and detect the presence of contrast in the blood.

A secondary objective of the present invention is to provide methods processes and systems for image reconstruction of internal body images in medical applications and the like that uses less radiation less x rays to target body areas for image reconstruction than prior art techniques.

A third objective of the present invention is to provide methods processes and systems for image reconstruction of internal body images in medical applications and the like to reconstruct in close to real time in seconds .

A fourth objective of the present invention is to provide methods processes and systems for image reconstruction of internal body images in medical applications and the like that do not use iterative algorithms and use less computational power than that needed to perform iterative image reconstruction.

A fifth objective of the present invention is to provide methods processes and systems for image reconstruction of internal body images in medical applications and the like with improved spatial resolution and contrast resolution that doesn t miss small targets.

A sixth objective of the present invention is to provide methods processes and systems for image reconstruction using variable filter length local tomography for reconstructing internal body images in medical applications and the like.

A seventh objective of the present invention is to provide methods processes and systems for image reconstruction of internal body images in medical applications and the like which would be a compromise between the local and global tomographics.

An eighth objective of the present invention is to provide methods processes and systems for image reconstruction of internal body images in medical applications and the like to find a convolution kernel which is sufficiently short so that only a small neighborhood of the ROI Region of Interest would need to be irradiated resulting in a reduced dose while assuring that the kernel was sufficiently long so that reconstructed images could differentiate tissue types.

A method for reconstructing an image from cone beam CB projection data provided by at least one detector comprising the steps of a. scanning an object to collect cone beam projection data b. loading the CB cone beam projection data into a computer c. using the CB projection data for reconstructing an image of the object and d. repeat loading and using additional CB projection data until image reconstruction is finished at all reconstruction points x wherein during step c only truncated CB data are used at one or more reconstruction points x inside the object wherein the said truncated CB data are defined as data which are insufficient for theoretically exact reconstruction at a point x wherein the step c. of reconstructing includes the substeps of c.i. filtering the truncated CB data c.ii. back projection updating of the image being reconstructed wherein the substep c.i. uses a filter of length longer than the length of a filter associated with computing a derivative typically 2 4 points but shorter than the length of a filter associated with theoretically exact reconstruction of infinite length or of length equal to a support of the object along the line of filtration wherein the image reconstructed in step d is not intended to approximate a theoretically exact reconstruction but allows differentiation of tissue types that comprise the object being scanned.

The reconstruction points can be confined to a region of interest ROT strictly in the interior of the object being scanned.

The substep c.i. of filtering can use a filter which is different from a truncated version of a ramp filter 

The filter can be modified so that differentiation of materials that constitute the object being scanned using the reconstructed image is improved 

The loading step can include the step of denoting the projection data as D s u v CB projection corresponds to source position y s and detector surface corresponding to the x ray source located at y s is denoted DP s .

The following detailed description of the presently preferred embodiments which are illustrated schematically in the accompanying drawings.

Before explaining the disclosed embodiments of the present invention in detail it is to be understood that the invention is not limited in its applications to the details of the particular arrangements shown since the invention is capable of other embodiments. Also the terminology used herein is for the purpose of description and not of limitation.

One of the subject inventors Dr. Alexander Katsevich has patented image reconstruction that includes local tomography. See for example U.S. Pat. Nos. 5 539 800 5 550 892 5 717 211 all to Katsevich which in their entirety are all incorporated by reference. Additionally Dr. Katsevich has patented an invention in cone beam local tomography. See for example. U.S. Pat. No. 7 590 216 to Katsevich which in its entirety is also incorporated by reference. The prior patents include but are not limited to collecting cone beam CB projection data from at least one detector in order to reconstruct images of an object.

The subject invention can use the same equipment described in these patents with a novel computer run algorithm which is described below.

For the subject invention the mathematical description of the algorithm is given by the following formula 0.1 where s is a parameter along the source trajectory fis the image to be reconstructed x is a reconstruction point K u is a reconstruction kernel w s x is a weight function u and v are row and column coordinates on the detector respectively u s x and v s x are the row and column coordinates of the projection of a reconstruction point x on the detector corresponding to the source position y s and Dis the cone beam data. In discrete form equation 1.1 can be written as follows 

The Local tomography is quite flexible and a wide variety of weight functions and reconstruction kernels is possible. For example we can choose

An example of a weight function is as follows where R is the radius of the helix x xare the in plane coordinates of a reconstruction point and y s y s are the in plane coordinates of the current source position y s .

The interval of integration in 1.1 and correspondingly the range of summation in 1.2 may depend on the specifics of the image reconstruction problem. In the case of cardiac CT when image reconstruction at a certain cardiac phase is required the weight function w s x will include additional factors that go to zero farther away from the desired phase. More generally the weight function may include factors that go to zero near the detector boundary to reduce data truncation artifacts. The cone beam data D s u v are measured by the detector at a discrete set of points u ui v vi where idenotes the index of a detector row and idenotes the index of a detector column. Thus in what follows for simplicity the detector data are denoted D s i i .

As stated equation 1.1 does not involve weighting of the CB data D s u v prior to convolution. Other embodiments of the algorithm are possible in which the CB data are multiplied by a weight factor prior to the convolution. Regardless of whether the CB data are weighted prior to convolution or not in both cases we say that the CB data are filtered.

The filter K j of the present invention is similar to the filter described by equation 6 in Z. Chen Local volume reconstruction from width truncated cone beam projections by convolution backprojection Optical Engineering volume 47 2008 issue 1. The main difference between the two filters is the value of K 0 . As is known the filter needs to satisfy the equation

The filter in equation 1.3 satisfies equation 1.4 . In an effort to make reconstruction from truncated data as close to conventional reconstruction as possible in paper Z. Chen Local volume reconstruction from width truncated cone beam projections by convolution backprojection Optical Engineering volume 47 2008 issue 1 the author truncates the conventional filter at some length and keeps all other filter values the same. Consequently as the filter length n becomes increasingly small the filter in Z. Chen Local volume reconstruction from width truncated cone beam projections by convolution backprojection Optical Engineering volume 47 2008 issue 1 violates equation 1.4 more strongly and the corresponding reconstructions become increasingly worse as confirmed by the following quote from the paper . . . a short kernel incurs a large error as revealed in FIG. 2b .

Conceptually the main difference between the approach in Z. Chen Local volume reconstruction from width truncated cone beam projections by convolution backprojection Optical Engineering volume 47 2008 issue 1 and the approach in the present invention is that the former attempts to make reconstruction from truncated data as close to conventional reconstruction as possible which in particular necessitates the use of data extrapolation. In the present invention the goal is to come up with an image that only looks qualitatively similar to conventional reconstruction. In particular the algorithm of the present invention can be used with non truncated data as well.

The main steps for running the algorithm in detail are in steps . is a flowchart of the steps for reconstruction using variable length tomography.

Step . Load the current CB cone beam projection D s u v into computer memory. Suppose that this CB projection corresponds to the source position y s . The detector surface corresponding to the x ray source located at y s is denoted DP s .

Step Filtering. For each detector row convolve the data with a filter. Let ibe the index of a detector row ibe the index of a detector column and let D s i i be the CB projection data in the i i location on the detector. We use the following equation cf. equation 1.2 

By itself the filtering step is well known in the field and can be implemented for example as shown and described in U.S. Pat. No. 5 881 123 to Tam which is incorporated by reference. Alternative implementation of the convolution can be based on the Fast Fourier Transform FFT .

Step . Fix a reconstruction point x which represents a point inside the patient where it is required to reconstruct the image.

Step . Find the projection circumflex over x of x onto the detector surface DP s Let i i be the row and column coordinates of circumflex over x on the detector.

Step . If circumflex over x projects onto the detector the said filtered CB data affects the image at x and one performs Steps . If circumflex over x projects outside the detector then the said filtered CB data are not used for image reconstruction at x. In this case go back to Step and choose another reconstruction point.

Step . Identify the rows and columns on the detector that are close to the said projection circumflex over x . This will give a few values of g s i i for i i close to i i .

Step . With interpolation estimate the value of g s i i from the said values of g s i i for i i close to i i .

Step . Compute the contribution from the said filtered CB data to the image being reconstructed at the point x by multiplying g s i i by a weight function s x .

Step . Add the said contribution to the image being reconstructed at the point x according to a pre selected scheme for example the Trapezoidal scheme for approximate evaluation of the integral in equation 1.1 according to 1.2 .

Step . Go to Step and load the next CB projection into computer memory. The image can be displayed at all reconstruction points x for which the image reconstruction process has been completed that is all the subsequent CB projections are not needed for reconstructing the image at those points . Discard from the computer memory all the CB projections that are not needed for image reconstruction at points where the image reconstruction process has not completed. The algorithm concludes when the scan is finished or the image reconstruction process has completed at all the required points.

As is seen from the description of Steps the algorithm of the present invention is computationally efficient. It contains steps like filtering backprojection multiplication by a weight function and the like. Most importantly for each source position the filtering on the detector is performed along a one parametric family of curves. The algorithms of prior art that reconstruct images from truncated data are generally computationally expensive in view of the extra computer power time and memory needed. The invention can consist of minimal steps that do not require the extra computer power time and memory needed. For example filtered back projection is an example of an algorithm that only requires minimal extra steps in addition to filtering and backprojection to operate. The minimal steps can include but are not limited to multiplication of data non filtered and filtered by a weight function linear interpolation smoothing and the like. The invention does not include any iterative steps filling in of the missing data using wavelets curvelets and the like.

A study of image reconstruction using the novel algorithm occurred at the Texas Medical Center in Houston. The first part of this study was retrospective analysis of patients comparing anatomy on selected slices of the coronary computed tomography angiogram CCTA with reconstructions using LT tomography at the same level s . Subsequently to test the feasibility of viewing anatomy that was comparable on the two types of reconstructions other subjects who would consent were prospectively recruited from all patients that presented to the hospital CT scanner in whom a cardiac computed tomography angiogram was ordered by the referring physician.

Following patient consent scans were obtained on a CB CT scanner utilizing helical scanning and dose modulated retrospective ECG gating. The contrast agent was utilized.

For all cases raw CT data was stripped of identifying information assigned a study number and transferred to an external hard drive for subsequent analysis by the local tomography LT algorithm that comprise this invention. In a parallel fashion the scanner raw CT data was processed and reconstructed in a routine manner and transferred to a CT visualization workstation for review and clinical reading and report by a radiologist or cardiologist responsible for the normal workflow. For the study this reconstructed data was also stripped of patient identifiers and used for the study. Two experienced readers compared the LT images and the conventional CT images for diagnostic accuracy spatial resolution and contrast resolution and an assessment of whether all lesions seen on the conventional CTA were identified by the LT reconstructed images.

An estimate was made about the range of potential radiation dose savings based upon the individual geometry of the scan regions of interest.

Feedback from the two experienced readers from the Texas Medical Center showed that the LT of the present invention provides excellent anatomical rendering including differentiation of tissue types and the contrast is clearly visible as well. Our estimations showed that LT has potential to decrease radiation by 50 .

Although the invention is primarily directed to image reconstruction of internal body images of cardiac and other organs body parts the invention can be used in other applications. For example the novel algorithm can be used for security screening and non destructive evaluation of cargo at airports and shipping ports. The invention can be used for scanning small and large machine parts for defects. The invention can further be used in wood working applications to determine the location of knots and cracks.

The algorithm of the invention reconstructs an image at a reconstruction point x using tomographic data corresponding to integrals along lines passing through a neighborhood of x. Therefore the algorithm is suitable for reconstructing a region of interest inside an object from truncated data. On the other hand the algorithm can be used for reconstructing the entire object from non truncated data since it can visualize certain features inside the object better than the traditional theoretically exact methods iterative and non iterative .

The present invention may be embodied on various computing platforms that perform actions responsive to software based instructions. The following provides an antecedent basis for the information technology that may be utilized to enable the invention.

The computer readable medium described in the claims below may be a computer readable signal data medium or a computer readable data storage medium. A computer readable storage medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus or device or any suitable combination of the foregoing. More specific examples a non exhaustive list of the computer readable storage medium would include the following an electrical connection having one or more wires or wireless connection a portable computer diskette or other data storage device a hard disk a random access memory RAM a read only memory ROM an erasable programmable read only memory EPROM or Flash memory an optical fiber a portable compact disc read only memory CD ROM an optical storage device a magnetic storage device other data storage device or any suitable combination of the foregoing. In the context of this document a computer readable storage medium may be any tangible medium that can contain or store a program for use by or in connection with an instruction execution system apparatus or device.

A computer readable signal data medium may include a propagated data signal with computer readable program code embodied therein for example in baseband or as part of a carrier wave. Such a propagated signal may take any of a variety of forms including but not limited to electro magnetic optical or any suitable combination thereof. A computer readable signal data medium may be any computer readable medium that is not a computer readable storage medium and that can communicate propagate or transport a program for use by or in connection with an instruction execution system apparatus or device.

Program code embodied on a computer readable data medium may be transmitted using any appropriate medium including but not limited to wireless wire line optical fiber cable radio frequency etc. or any suitable combination of the foregoing. Computer program code for carrying out operations for aspects of the present invention may be written in any combination of one or more programming languages including an object oriented programming language such as Java C C Fortran scripting languages or the like and conventional procedural programming languages such as the C programming language or similar programming languages.

Aspects of the present invention are described below with reference to flowchart illustrations and or block diagrams of methods apparatus systems and computer program products according to embodiments of the invention. It will be understood that each block of the flowchart illustrations and or block diagrams and combinations of blocks in the flowchart illustrations and or block diagrams can be implemented by computer program instructions. These computer program instructions may be provided to a processor of a general purpose computer special purpose computer or other programmable data processing apparatus to produce a machine such that the instructions which execute via the processor of the computer or other programmable data processing apparatus create means for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

These computer program instructions may also be stored in a computer readable medium that can direct a computer other programmable data processing apparatus or other devices to function in a particular manner such that the instructions stored in the computer readable medium produce an article of manufacture including instructions which implement the function act specified in the flowchart and or block diagram block or blocks.

The computer program instructions may also be loaded onto a computer other programmable data processing apparatus or other devices to cause a series of operational steps to be performed on the computer other programmable apparatus or other devices to produce a computer implemented process such that the instructions which execute on the computer or other programmable apparatus provide processes for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

Back projection updating use of a backprojection algorithm for reconstruction of an image. Generally backprojection refers to the step of using projection data for updating the image volume being reconstructed.

Computer a general purpose device that can be programmed to carry out a set of arithmetic or logical operations.

Cone beam CB projection data two dimensional data provided by a detector array integral to a computed tomography CT imaging system.

Curvelets a higher dimensional generalization of the wavelet transform designed to represent images at different scales and different angles.

Filtering a mathematical process by which one two or higher dimensional data arrays are transformed with the purpose of changing the frequency content of the said arrays. Those purposes may include but are not limited to suppression of noise and smoothing edge enhancement and resolution recovery.

Ramp filter a high pass filter whose graph in the frequency domain looks like a linearly increasing ramp function. To avoid artifacts at the highest frequencies the ramp filter may go to zero in a smooth fashion.

Truncated CB data CB data which is insufficient for theoretically exact reconstruction at a given point.

While the invention has been described disclosed illustrated and shown in various terms of certain embodiments or modifications which it has presumed in practice the scope of the invention is not intended to be nor should it be deemed to be limited thereby and such other modifications or embodiments as may be suggested by the teachings herein are particularly reserved especially as they fall within the breadth and scope of the claims here appended.

