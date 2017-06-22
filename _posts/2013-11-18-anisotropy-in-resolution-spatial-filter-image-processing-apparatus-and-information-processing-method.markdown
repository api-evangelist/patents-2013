---

title: Anisotropy in resolution spatial filter image processing apparatus, and information processing method
abstract: An information processing method includes calculating a second spatial filter having a size of the number of elements larger than a blur size of an image using a finite first spatial filter having an anisotropy in resolution of the image and a finite filter in which a value of a total sum of elements is zero and at least two elements have a non-zero value, and generating a plurality of spatial filters having a predetermined number of elements or less from the second spatial filter.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09418406&OS=09418406&RS=09418406
owner: FUJITSU LIMITED
number: 09418406
owner_city: Kawasaki
owner_country: JP
publication_date: 20131118
---
This application is based upon and claims the benefit of priority from the prior Japanese Patent Application No. 2012 268753 filed on Dec. 7 2012 the entire contents of which are incorporated herein by reference.

The present disclosure relates to an image processing apparatus an information processing method and a program thereof.

The resolution of an image photographed by for example a digital camera is often degraded in the periphery of the image. In particular the resolution in the periphery tends to degrade with respect to a central portion around an optical axis due to the dependence of an angle of view of an aperture size or aberration of a lens optical system. The vignetting of an aperture is regarded as one of the causes of degradation. A circular shaped radial aperture formed in the circumferential direction is vignetted to form an elliptical aperture at an area where an angle of view is wide and thus an image becomes blurred. As a result the resolution in radial direction is degraded.

Regarding the degradation of resolution there is a technique in which an image is filtered using different filter data according to a target position of the image to be corrected for example in order to cope with the change of a PSF Point Spread Function according to the angle of incident light. See for example Japanese Laid Open Patent Publication No. 2012 23498.

The level of resolution tends to be different depending on a direction and the property is referred to as anisotropy in resolution. For example the level of resolution in the radial direction around an optical axis is different from that in the circumferential direction.

While a different filtering is performed according to the position of an image in conventional techniques to correct the blur of the image anisotropy in resolution may not be improved in the conventional techniques.

According to an aspect of the present disclosure there is provided an information processing method including calculating a second spatial filter having a size of the number of elements larger than a blur size of an image using a finite first spatial filter having an anisotropy in resolution of the image and a finite filter in which a value of a total sum of elements is zero and at least two elements have a non zero value and generating a plurality of spatial filters having a predetermined number of elements or less from the second spatial filter.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims. It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

Since the computation in frequency domain such as for example Fourier transformation requires a large amount operations a convolutional correction is normally performed with a finite spatial filter in order to provide a filtering function to the hardware such as a digital camera. However a spatial filter having anisotropy is limited to have a finite number of elements and thus the degradation levels of high frequency components become different with each other depending on the directions thereby generating Moir depending on the direction.

When the convolutional correction is performed with a finite spatial filter there is a demand to further reduce the number of elements in order to lower the cost of processing. For example when the finite spatial filter is installed in the hardware there are needs to reduce the size of the spatial filter to a predetermined number of filter elements e.g. 5 5 or less. When the number of filter elements is doubled the amount of calculations is quadrupled and thus the size of the spatial filter is desired to be limited to a predetermined number of filter elements or less.

However when the number of elements of the spatial filter becomes smaller the size of a PSF indicative of blur may become larger than the number of elements of the spatial filter. In this case an amount of blur information may be missed and thus the anisotropy in resolution or Moir may not be prevented from being generated.

Therefore the disclosed technique intends to provide an image processing apparatus capable of preventing the quality of image from being degraded when the spatial filter having anisotropy of resolution is limited to have a predetermined number of elements an information processing method and a program thereof.

An image processing apparatus according to one aspect of the present disclosure includes a calculation unit configured to calculate a finite first spatial filter having an anisotropy in resolution of an image and a second spatial filter having a larger number of filter elements than a blur size of an image using a finite filter in which a total sum of elements is zero and at least two elements have a value of non zero and a generation unit configured to generate a plurality of spatial filters having a predetermined number of elements or less from the second spatial filter.

According to the disclosed technique the quality of image may be prevented from being degraded when a spatial filter having anisotropy in resolution is limited to have a predetermined number of elements.

One cause of degradation of resolution will be described with reference to to . is a view illustrating an exemplary optical system. is a view illustrating exemplary apertures according to the position in an image. When the optical system illustrated in is used the aperture is circular at the center of the optical axis as illustrated in . However when an angle of view is wide a vignetting occurs due to the aperture. As illustrated in the shape of the apertures becomes an ellipsis according to the position in the image.

Subsequently an analysis of resolution performed by inventors of the present disclosure will be described. A tendency of degradation of resolution may be analyzed in detail by taking photographs of a Siemens star in which edges are radially distributed.

As illustrated in a subject which is widening radially for example a wedge shaped subject may be used and thus the resolution may be analyzed according to a direction MTF Modulation Transfer Function .

It may be seen from the analysis result illustrated in that not only the resolution is degraded but also the anisotropy in resolution occurs in the periphery including the end portion of the image. When the resolution of the Siemens stars are compared the dependence of an angle exists little in the central portion but the dependence of an angle exists in the end portion.

Here there is a correction method which utilizes a point spread function PSF in order to correct blur including degradation of resolution as described above. The PSF is for example a function representing blur. Hereinafter the function representing blur is also referred to as a blur function.

When it is assumed that an original image is x and the PSF is k the blur image y is an image obtained by convolving x with k and is represented as the following equation 1 . 1 

When the equation 1 is Fourier transformed the equation 1 is transformed into the following equation 2 . 2 

Subsequently when it is intended to simply obtain the inverse filter K the inverse filter Kis obtained by a reciprocal of K as represented by the following equation 3 . 1 3 

From this the Fourier transform X of the original image is obtained by the following equation 4 and the following equation 4 is subjected to an inverse Fourier transform to calculate the original image. 4 

As described above when the PSF is Fourier transformed to calculate an inverse filter function hereinafter simply referred to as inverse filter using the reciprocal a division by the spatial frequency is performed and thus a zero dividing may be performed in high frequency domain. The zero dividing means that it is divided by a value at zero or close to zero. When the high frequency is close to zero the reciprocal becomes an extremely high value and thus the high frequency component of noise is emphasized.

Therefore a correction term is inserted into the denominator as represented in the following equation 5 to prevent the noise at higher frequencies from being emphasized in order to reduce noise at higher frequencies. 1 5 

Since the inverse filter is a complex number the inverse filter is represented by the following equation 6 using conjugate complex number. 6 

Here a case where the PSF is an ellipsis is considered. is a view illustrating an example of an elliptical PSF. In the example illustrated in the resolution in the Dy direction is poorer than the resolution in the Dx direction. That is the resolution in the Dy direction is further degraded than the resolution in the Dx direction.

The PSF of ellipse represented by k r . The r represents a radius and represents a direction. For example the PSF of an ellipse is represented by a function of the radius r and the direction . When the PSF of an ellipse is Fourier transformed K w fk r . The f represents Fourier transform. For example the K w after Fourier transform is a function of a spatial frequency and the direction .

Therefore a correction term is inserted into the denominator to prevent the noise at higher frequencies from being emphasized in order to reduce the noise at higher frequencies. The following equation 8 represents the inverse filter which reduces a high frequency component of noise. 8 

Even when the blur function e.g. PSF is an elliptical shaped function a high frequency component of noise is reduced by a corrected weight A . However when the correction using the weight is performed the resolution in a direction along which the resolution is poor e.g. Dy direction may not be corrected and improved. Accordingly the anisotropy in resolution may not be improved only by simply applying weighting. Therefore the inventors found out that the anisotropy in resolution may be improved by calibrating an appropriate weight function according to a direction.

Subsequently description will be made with respect to the generation of the spatial filter for improving the anisotropy in resolution. An apparatus will be described using a method in which gain has been gradually dropped as illustrated in but is not limited to the method. For example even a method in which a predetermined value is added as in the anisotropy in resolution may be improved. In this method a predetermined value is added such that the Dy direction is more emphasized than the Dx direction.

An optical system condenses light from a subject K having a radial shape onto a surface on which image is captured. For example the optical system includes lenses and a diaphragm . The lenses and the diaphragm condense light from the subject K onto the image capturing surface of the image capturing element to image the subject. The driving control apparatus is able to control for example a location of the lenses or a degree of narrowing of the diaphragm . In the meantime a configuration of the optical system is not limited to a particular configuration.

The image capturing element converts light from the subject K condensed by the optical system to electrical signal analog signal . The image capturing element includes for example a two dimensional image capturing element such as a CCD CMOS and the two dimensional image capturing element converts an image of the subject into electrical signal image signal and output the converted signal to the AFE .

The AFE converts the analog signal of the captured image into digital signal. The AFE includes for example an A D analog to digital converter and a timing generator . The timing generator generates a timing pulse used for driving the image capturing element based on control signal from the control apparatus and outputs the timing pulse to the image capturing element and the A D converter .

The image processing unit maintains an image of the digital signal to perform a predetermined image processing on the image. The image processing unit includes for example a RAW memory in which an image RAW image is converted into the digital signal by the A D converter . The image processing unit may perform a predetermined processing on the RAW image. The image on which the predetermined processing is performed is recorded in the image memory .

The post processing unit performs further necessary processing on the image undergone a predetermined processing to generate a display image. The post processing unit reads for example the image undergone a predetermined processing from the image memory to perform a necessary processing and generates an image for displaying to output the image to the display unit .

The image memory stores an image after the predetermined processing. The display unit includes for example a VRAM in which an image is recorded and a display which outputs an image of the VRAM. In the meantime an image capturing apparatus may not necessarily include a display function and may be provided with a recording unit e.g. VRAM in which image for displaying is recorded instead of the display unit .

The driving control apparatus controls the optical system . The control apparatus controls the AFE and the post processing unit .

The coefficient analysis unit analyzes the resolution in each direction in each image position from the image for which the chart is photographed to determine an appropriate filter data for improving the anisotropy in resolution. Details of the coefficient analysis unit will be described later.

The filter data may be formed with a set of parameters necessary for filtering for an image correction similarly to for example a de convolution kernel. Specifically the de convolution kernel may be represented using an area in which a circular or an elliptical shaped subject image according to the PSF is distributed and data these data referred to as de convolution distribution which indicates weight of each pixel in the area.

The inverse filter utilized in the embodiment will be described. Hereinafter a calculation sequence of the inverse filter which improves anisotropy in resolution for example performs adjustment for a direction along which resolution is poor. Further the inverse filter is also simply referred to as a filter.

As represented by the equation 1 the original image x a PSF k and the blur image y are considered. When the original image x is obtained if the following equation 9 becomes a minimum in inverse problem an image close to the original image may be obtained. 9 

Normally a type of regularization term is applied in solving the inverse problem. Accordingly the inverse problem is solved from the following equation 10 in which a regularization term is added. 10 

In the corresponding problem directionality is needed and thus derivative term of a transversal direction horizontal direction and a derivative term in a longitudinal direction perpendicular direction of image as represented is added as a regularization term in the following equation 11 . 11 

where represents a weight coefficient and dand drepresent derivative filters in the direction of matrix. Here the dis d 1 1 and the dis

It is needed to make a result obtained by performing a partial differentiation of the equation 11 with x zero in order to make the equation 11 described above minimum. Also when the equation 11 is Fourier transformed and solved for the X the following equation 12 may be obtained.

When a conjugate complex number is used the above equation 14 is represented as the following equation 15 .

It is characterized in the embodiment that an axis of derivative coefficient is rotated in a direction with an angle of using a rotation matrix in order to adjust resolution in a direction along which resolution is poor as represented in the following equations 16 and 17 . cos sin 16 sin cos 17 

As described above the inverse filter may be made to have a directionality by using the rotation matrix.

The elliptical PSF is defined as k r here and the elliptical PSF having been Fourier transformed is defined such that K fk r . When a weight according to a direction is set while the equation 16 the equation 17 and the K are substituted in the equation 15 the following equation 18 is implemented.

where is a weight coefficient according to the direction of the inverse filter and is an weight coefficient.

With the equation 18 it becomes possible to perform a weight adjustment for the directionality of the inverse filter utilized in each embodiment. For example the coefficient analysis unit adjusts the weight for the direction Dy direction along which resolution is poor. The weight coefficient is made to be smaller and thus the resolution in the direction along which the resolution is poor may be improved.

Subsequently the coefficient analysis unit will be described. The coefficient analysis unit determines a spatial filter for improving anisotropy in resolution.

The resolution analysis unit analyzes the degradation of resolution of the image in which the subject having a radial shape is captured at least at two directions. The analysis method uses a method described in for example and . When the line pairs per pixel is defined in a transversal axis and the intensity of amplitude is defined in a longitudinal axis the resolution analysis unit may analyze MTF. The lines pairs per pixel may use line pairs per unit distance at a location of the subject. A chart having a wedge shape as well as radial shape is used and thus the MTF according to a direction may be analyzed as illustrated in in the embodiment.

The determination unit may calculate an ellipticity using a major axis and a minor axis obtained. The determination unit calculates the angle 1 geographically based on the position in the image. Further the determination unit may calculate the angle 1 using the major axis and the minor axis of the ellipsis of resolution. An angle may be calculated in line with an actual blur state in the calculation of the angle 1 using the major axis and the minor axis. Here when a concentric circle is plotted from a center of optical axis the blur in the radial direction is large as illustrated in .

The determination unit only needs to calculate for example an angle between a longitudinal direction and the radial direction. In the meantime the center of an optical axis is basically the center of an image but the center of the optical axis may be misaligned due to the offsetting of lens. The determination unit determines the PSF using the ellipticity and the angle calculated. An ellipsis of the determined PSF is rotated by 90 degrees from an ellipsis obtained from the contour lines of the MTF.

Referring back to the determination unit determines filter data having anisotropy of the inverse filter with respect to the image corrected by the filter e.g. the inverse filter described above according to the blur function PSF of the image based on the resolution analysis result for the image after correction.

Further the determination unit changes and determines the weight coefficient for example with respect to the derivative direction of the image. For example the weight coefficient of the Dx direction is set to 1 one and the weight coefficient of the Dy direction is set to the weight coefficient to change the . Accordingly the anisotropy in resolution may be improved.

Further the determination unit rotates the image e.g. with respect to the derivative direction to determine the weight coefficient. Accordingly a direction along which the resolution is poor may be detected and thus a filtering of an image may be made.

Specifically the determination unit adjusts for example the weight coefficients and to determine an appropriate weight coefficient and . The weight coefficient represents the weight coefficient of filter parameters of the direction along which resolution is poor. The filter parameters of the direction along which resolution is poor are for example Dy with respect to the weight coefficient of the equation 18 and a conjugate complex number of the Dy .

The determination unit includes an adjustment unit an image correction unit a coefficient determination unit and a filter determination unit in order to adjust and determine the weight coefficient.

The adjustment unit adjusts for example the weight coefficient E which does not depend on the direction and the weight coefficient which depends on the direction. The adjustment unit sets initial values of the weight coefficients and submits the initial values to the image the correction unit .

The image correction unit performs an image correction using the weight coefficient acquired from the adjustment unit . The image correction unit filters and corrects the image using the inverse filter indicated in the equation 18 . The image correction unit submits the image after correction to the resolution analysis unit to analyze degradation of resolution again.

The coefficient determination unit determines the weight coefficient such that the difference of degradation of resolution between two directions becomes small based on the resolution analysis result for the image after correction. The coefficient determination unit maintains analysis results of the image corrected by various weight coefficients and determines the weight coefficients and such that a difference between the values of spatial frequency becomes minimal for example in a predetermined intensity of amplitude determination process 1 .

Further the coefficient determination unit may determine the weight coefficients and such that the difference between the intensities of amplitude becomes minimal in the predetermined spatial frequency determination process 2 .

Plural threshold values 1 and threshold values 2 may be set and the coefficient determination unit may determine the weight coefficients such that sum of squares of the differences becomes minimum. In the meantime the coefficient determination unit may determine the weight coefficients such that a predetermined difference becomes a threshold value or less preset. The threshold value may be set by for example a preliminary experiment.

The coefficient determination unit may determine the weight coefficients such that the difference between sum of squares of the differences of resolution in two directions at a central portion of image and the sum of squares of the differences of resolution in two directions at the peripheral portion other than the central portion of image become a predetermined value or less. Further the coefficient determination unit may determine the weight coefficients such that sum of squares of the differences of resolution between the central portion of image and the peripheral portion of the image becomes minimal.

This is because when reducing anisotropy in resolution resolution in the central portion of the image and resolution in the peripheral portion of the image is made to equal such that the entire resolution of the image becomes equal in the directions and as a result the quality of image may be improved.

The determination for minimization by the coefficient determination unit may be calculated either by using a minimization function or by a person. The minimization function includes for example a simplex search method a steepest descent method or a conjugate gradient method.

The determination unit changes and adjusts the weight coefficient obtains the inverse filter using the weight coefficient after adjustment corrects the image using the obtained inverse filter and determines the optimum weight coefficient based on the resolution analysis result for the image after correction. The adjustment of the weight coefficient the calculation of the inverse filter the correction with filtering and the resolution analysis processing are repeated until the optimum weight coefficient is determined.

The filter determination unit calculates the inverse filter Kwhich utilizes the optimum weight coefficient determined by the coefficient determination unit as in the following equation 19 and obtains the inverse filter kin spatial domain from the inverse filter Kin frequency domain as in the following equation 20 . Hereinafter the inverse filter in spatial domain is referred to as a spatial filter.

The coefficient analysis unit performs the processes as described above at each position where the chart is present in the image. The coefficient analysis unit analyzes anisotropy in resolution at each position in the image and determines the spatial filter of which anisotropy is to be improved.

The processes described above are performed and thus the spatial filter of which anisotropy is to be improved may be determined while correcting the blur with respect to a predetermined the position of image. For example a direction along which resolution is poorer than other directions may be detected to determine the weight coefficient with which resolution in the direction having poorer resolution is more improved.

The coefficient analysis unit performs a calculation of the spatial filter at each position in the image. is a view illustrating an example of image in which twelve charts are photographed. The example illustrated in is only an example and even though the number of charts is not twelve charts each chart may be present in plural areas formed by dividing the image.

The coefficient analysis unit determines the filter data at each area in which each chart is present to calculate the spatial filter. The coefficient analysis unit prepares a table in which a position in the image and the spatial filter is mapped. Further the coefficient analysis unit may associate the size of the calculated ellipsis with the table.

Accordingly the image processing apparatus including the coefficient analysis unit may determine the spatial filter for which anisotropy in resolution is improved. The spatial filter for which anisotropy in resolution is improved is not limited to the example as described above and may include the spatial filter obtained by a technology described in for example Japanese Laid Open Patent Publication No. 2012 23498. In this case the spatial filter is made to have anisotropy in resolution.

The image processing unit may be configured by for example a DSP Digital Signal Processor . In this case the RAW memory may be a memory built in the DSP or an external memory. Further the post processing unit the image memory the coefficient analysis unit the VRAM for displaying may be formed integrally with an integral DSP together with an image processing unit . Further the coefficient analysis unit may be formed as an image processing apparatus formed as a single unit or including other processing units.

Alternatively a predetermined program may be executed not by a dedicated processor for specific processing such as a DSP but by a general processor such as a CPU to implement functions of the image processing unit or the coefficient analysis unit . The driving control apparatus the control apparatus and the post processing unit may also configured by at least one dedicated processor for specific processing or a general processor.

The program which causes the processor to serve as the image processing unit or the coefficient analysis unit and a recording medium in which the program is recorded are also included in the embodiments of the present disclosure. The recording medium is a non transitory medium and a transitory medium such as signal itself is not included as the recording medium in the embodiments of the present disclosure.

The problem followed by the finitization of the spatial filter will be described hereinafter. When the spatial filter having anisotropy is finitized information for a portion other than a portion where the extracted taps elements of the spatial filter are extracted is missed. The spatial filter has anisotropy and thus information which becomes missing is different depending on a direction. Further the sums that add the elements are not equal.

High frequency information is included in the missed information and thus when the image is corrected by the finite spatial filter a degree of correction becomes different depending on the direction of correction.

Therefore when the finite spatial filter is utilized the degree of correction is different depending on the direction. When the chart is corrected using the nine tap spatial filter as illustrated in Moir is generated. is a view illustrating an example of Moir generated in a corrected image. Moir caused by finitization of the spatial filter as illustrated in is generated.

Further when the spatial filter is installed there is a demand to limit the size of the spatial filter to the predetermined number of filter elements or less from a point of view of an amount of computation and a memory. Currently the spatial filter having a size of for example 5 5 elements or less may be used.

However when the number of elements of the spatial filter made to be small the size of the PSF indicating blur becomes larger than the number of elements and thus an amount of information is missed. Therefore the quality of image may be degraded.

In an example illustrated in the number of elements of the spatial filter is smaller than the size of blur and thus information of blur is missed when the image is corrected.

Therefore in the embodiment to be described below when the spatial filter having anisotropy in resolution is finitized to a predetermined number of elements or less an object to be solved in installation is achieved to prevent degradation of the image quality.

An outline of preventing generation of Moir will be described first. As described in detail the spatial filter having anisotropy in resolution is finitized and thus the missing level of high frequency information is different depending on the direction. Therefore Moir is generated. That is the degree of correction for degradation of frequency is different depending on the direction and thus Moir is generated.

Therefore an image signal is made to pass through a finite high pass filter to reduce a portion at which luminance abruptly varies and thus a difference in the degree of correction of high frequency information which is different depending on the direction is reduced. Accordingly the generation of Moir caused by the degradation of frequency information depending on the direction may be prevented.

A finite high pass filter may be a finite filter in which a total sum of values of elements is 0 zero and at least two elements have a value of non zero. Hereinafter description will be made using a finite high pass filter as the finite filter.

Further an object to be solved in installation may be achieved by dividing the calculated spatial filter to generate spatial filters in plural stages and each spatial filter has a predetermined number of elements or less.

In the embodiment to be described below with respect to the blur having anisotropy of which size is larger than the number of elements of the spatial filter plural inverse filters having anisotropy are formed and combined with plural spatial filters to improve anisotropy.

The image capturing apparatus including the image processing apparatus in the embodiment 1 will be described next. In the embodiment 1 the degradation of quality of image when the size of the spatial filter having anisotropy in resolution is finitized to a predetermined number of elements may be prevented.

The image processing unit includes a RAW the memory a filter control unit and a filter processing unit . The filter control unit maintains the spatial filter table illustrated in . The filter control unit calculates the spatial filter having the number of elements larger than the blur size with respect to each spatial filter in the spatial filter table.

The filter control unit then divides the calculated spatial filter into the spatial filters in plural stages to have a predetermined number of elements or less. The filter control unit outputs the spatial filters in plural stages to the filter processing unit . That is the filter control unit outputs the spatial filters in plural stages corresponding to each position in the image to be processed to the filter processing unit .

The filter processing unit performs a filtering at the corresponding position in the image using the spatial filters in plural stages acquired from the filter control unit . Accordingly the anisotropy in resolution which is different at each position in the image may be improved to prevent the generation of Moir and enhance the quality of the image.

The filter control unit and the filter processing unit in the embodiment 1 will be described next. is a block diagram illustrating an exemplary first schematic configuration of a filter control unit and a filter processing unit in the embodiment 1. The filter control unit will be described first. The filter control unit includes a filter storage unit a filter acquisition unit a filter calculation unit and a filter generation unit .

The filter storage unit stores at least a first spatial filter a second spatial filter and spatial filters in plural stages. Each filter may be stored in different storage areas respectively.

The first spatial filter is a spatial filter having an anisotropy in resolution. The first spatial filter corresponds to for example each filter in the spatial filter table illustrated in . The second spatial filter is a filter calculated by the filter calculation unit . The second spatial filter is a filter for example obtained by convolving the high pass filter with the first spatial filter . The spatial filters in plural stages are a group of spatial filters generated by the filter generation unit .

The filter acquisition unit acquires a finite spatial filter having anisotropy in resolution of the image. The filter acquisition unit acquires the first spatial filter from for example the filter storage unit . The filter acquisition unit outputs the first spatial filter acquired to the filter calculation unit .

The filter calculation unit calculates a second spatial filter by convolving a finite filter in which a total sum of values of elements is 0 zero and at least two elements have a value of non zero with the first spatial filter acquired from the filter acquisition unit .

In this case the filter calculation unit calculates the second spatial filter having the number of elements larger than the size of blur e.g. the size of an ellipsis of the PSF . The filter calculation unit includes a determination unit and the determination unit determines the blur size from for example the size of the PSF stored in the filter storage unit . Further the determination unit may determine the blur size from the acquired PSF in a case where the PSF may be acquired from a lens design value by simulation as described in for example Japanese Laid Open Patent Publication No. 2012 23498.

The filter calculation unit calculates the second spatial filter by convolving the first spatial filter having the number of elements larger than the size of the blur of image with the finite high pass filter.

The filter calculation unit maintains the finite high pass filter in advance. When the finite high pass filter is intended to be defined as for example a filter of having 3 3 elements the finite high pass filter may be obtained using the following equations 26 and 27 .

The anisotropy described in the embodiment depends on a filter at an angle in any direction and thus the filter of which all elements have coefficients of non zeros as represented in the equation 27 may be used.

The filter calculation unit defines the spatial filter kas a filter of 7 7 elements when the high pass filter is defined as a filter of 3 3 elements and convolves the two filters to calculate a filter of 9 9 elements. As described above the filter calculation unit convolves the high pass filter with the spatial filter to calculate the filter having the desired number of taps.

Here when a filter of 7 7 elements is denoted by F7 and the high pass filter is denoted by Lap a filter of 9 9 elements calculated in the filter calculation unit is represented by the following equation 28 . 9 7 28 

The filter calculation unit stores the second spatial filter F9 calculated by the equation 28 described above in the filter storage unit .

The filter calculation unit may be installed in a separate apparatus and the filter control unit may store the second spatial filter obtained from the separate apparatus.

The filter generation unit acquires the second spatial filter from the filter storage unit and generates the spatial filters in plural stages having a predetermined number of elements or less from the second spatial filter . Descriptions regarding the generation of the spatial filters in plural stages will be described later. The filter generation unit stores the generated spatial filters in plural stages in the filter storage unit .

The filter processing unit will be described next. The filter processing unit includes a convolution operation unit and a subtraction unit . The convolution operation unit acquires the image from the RAW memory and convolves the image in the spatial filters in plural stages to perform filtering.

The convolution operation unit may perform filtering on the image in such a manner that the spatial filter in plural stages causes a single convolution circuit to perform convolution plural times or prepares and causes plural convolution circuits to perform convolution. The convolution operation unit outputs the image after filtering to the subtraction unit .

The subtraction unit subtracts the image after filtering from the image acquired from the RAW memory to generate a corrected image. The corrected image is output to the post processing unit or the image memory .

The filter processing unit may obtain a pixel value of a target pixel here by performing a linear interpolation using adjacent spatial filters rather than using a single spatial filter on each pixel of each area of the image.

Further the filter processing unit may calculate the pixel value after the spatial filter itself for the target pixel is obtained with the linear interpolation. Further in the above example the number of spatial filters set four adjacent spatial filters but not limited thereto and may use different plural spatial filters. Additionally the linear interpolation using a distance is performed but other interpolation scheme may be used. Further interpolation may be performed for each sub area resulted from sub division of an area or performed for each pixel.

Other examples of the filter control unit and the filter processing unit will be described next. is a block diagram illustrating an exemplary second schematic configuration of the filter control unit and the filter processing unit in the embodiment 1. The filter control unit will be described first. The filter control unit includes a filter storage unit a filter acquisition unit a filter calculation unit and a filter generation unit .

In the configuration of the filter control unit illustrated in the same reference numerals will be given to the same configuration as .

The filter storage unit stores a third spatial filter calculated by the filter calculation unit and the spatial filters in plural stages calculated by the filter generation unit .

The filter calculation unit calculates a third spatial filter which does not need a subtracting process between the images described above. The filter calculation unit may make unnecessary subtracting process by performing deformation of equation using the equations 22 23 24 and 25 . In this example it is assumed that a third spatial filter F9 of 9 9 elements.

Accordingly the same result as described above may be obtained and thus the finite spatial filter F9 which does not need a subtracting process between the images may be generated.

The filter calculation unit stores the calculated spatial filter F9 in the filter storage unit . The spatial filter F9 is the third spatial filter .

The filter generation unit acquires the third spatial filter from the filter storage unit and generates the spatial filters in plural stages having the predetermined number of elements or less from the third spatial filter . Generation of the spatial filters in plural stages will be described later. The filter generation unit stores the generated spatial filters in plural stages in the filter storage unit .

The filter processing unit includes a convolution operation unit . The convolution operation unit performs convolution on the spatial filters in plural stages and generates a corrected image x .

The generation of spatial filters in plural stages will be described next. Hereinbelow an example in which the filter generation unit illustrated in generates the spatial filters in plural stages will be described but the filter generation unit illustrated in also generates the spatial filters in plural stages in the same manner.

First when the spatial filter having the number of elements larger than the size of the blur into a group of filters having a predetermined number of elements the filter generation unit assumes one filter as a basis for dividing and obtains other filters with optimization based on the assumed filter.

For example it may be assumed that the third spatial filter F9 is divided into two spatial filters of 5 5 elements each is defined as F5A and F5B . In this case the filter generation unit may define the following equation 29 . 9 55 29 

where the term e is an error of difference. Hereinafter a method of dividing into the spatial filters in plural stages performed by the inventors will be described.

In the division method 1 the spatial filter F5A is defined as a filter formed by extracting a central portion of 5 5 elements of the third spatial filter F9 .

In the division method 2 the spatial filter F5A in a first stage is defined as a filter having anisotropy. For example the spatial filter F5A is formed with just a reciprocal of an anisotropic PSF.

In the division method 3 the spatial filter F5A in a first stage is defined as a filter having isotropy. For example the spatial filter F5A is formed with just a reciprocal of an isotropic PSF.

In the division method 4 the spatial filter F5A in a first stage is defined as a filter having isotropy and formed by convolving the reciprocal of the PSF with the high pass filter.

Further in a case where the spatial filter in the first stage is isotropic information of anisotropy becomes a single filter and thus the number of elements becomes short.

There is a case where a desirable correction result may not be obtained in the division methods as describe above. Therefore a method for dividing a filter which has anisotropy and a large number of elements into plural stages more properly will be described.

Accordingly the high pass filter is formed in the first stage to prevent the generation of Moir and further a configuration for improving anisotropy is formed such that a filter is divided into filters in plural stages. Therefore it is possible to cope with the improvement of the blur having the size larger than the number of elements.

The filter generation unit may calculate the spatial filter F5B in the second stage by minimizing the estimation function using the third spatial filter F9 and the spatial filter F5A .

In the example illustrated in the filter processing unit generates a corrected image x using the following equations 33 34 35 and 36 . 1 5 33 50 5 34 51 35 50 5 36 

The spatial filter F5A is a combination of the spatial filter having anisotropy and the high pass filter and the spatial filter F5B is responsible for supplementing omission of the spatial filter having anisotropy. Further a convolution sequence may be reversed.

The filter generation units determine the numbers of spatial filters to be divided based on a size of a first spatial filter and a predetermined number of elements when dividing the spatial filters into the spatial filter in plural stages.

The filter generation unit first divide a second spatial filter of 13 13 elements or a third spatial filter of 13 13 elements into a spatial filter of 9 9 elements and the spatial filter of 5 5 elements. Subsequently the filter generation units divide the spatial filter of 9 9 elements into two stage spatial filters of 5 5 elements in the same manner.

When the predetermined number of elements is 3 3 elements the filter generation unit need to divide the spatial filter into more plural stages. Further when the number of elements of the first spatial filter generated by the filter calculation unit is 7 7 elements the filter generation units divide the spatial filter into two stage spatial filters of 5 5 elements and 3 3 elements. As such sizes of filters to be divided may differ from each other.

However when the number of elements of the spatial filter in plural stages are equal the filter processing unit uses one convolution circuit to repeatedly perform the same process at least two times. Therefore the spatial filter in plural stages having the same number of elements and having a larger size of the spatial filter is more efficient. Accordingly when the filter calculation unit sets the size of the first spatial filter larger than the blur to 9 9 elements the filter generation units may generate two stage spatial filters having the same number of elements for example 5 5 elements .

Here the error of difference e does not become zero with respect to the estimation function represented by the following equation 30 . Accordingly gain is set and multiplied to the spatial filter in plural stages obtained by minimizing the estimation function to improve accuracy.

In the equations 37 and 38 Gain1 and Gain2 are obtained by for example minimizing the estimation function using the chart illustrated in . The gain estimation function is for example a function which represents a distance of MTF in two directions and Gain1 and Gain2 that minimize the estimation function are obtained. Further the estimation function of gain may be for example a function which represents a distance of MTF in the middle of two directions. The gain calculation may be made by the post processing unit .

The gain multiplication unit multiplies a value after processing of each spatial filters divided in plural stages by a predetermined gain. The gain multiplication unit analyzes resolution before and after multiplication of gain is performed to acquire gain with which anisotropy may be best improved from the post processing unit as a predetermined gain.

The configuration illustrated in is based on the configuration of but the gain multiplication unit may be included in the convolution operation unit e.g. see .

The operations of the image processing unit in the embodiment 1 will be described next. is a flow chart illustrating an example of a filter generation process in the embodiment 1. The process illustrated in represents a filter generation process by the division method 5.

At step S the filter acquisition unit acquires the first spatial filter from the filter storage unit .

At step S the determination unit determines the blur size of PSF. The determination unit determines for example the blur size of PSF based on a major axis and a minor axis obtained with analysis of resolution. Further the determination unit may acquires the PSF which is a result acquired from a lens design value by simulation as described in Japanese Laid Open Patent Publication No. 2012 23498.

At step S the filter calculation unit extracts the spatial filter having the number of elements larger than the size of the blur from the first spatial filter and convolves the finite high pass filter to calculate the second spatial filter e.g. F9 .

Further the filter calculation unit subtracts the second spatial filter from a filter in which a value of the center element is 1 one and values of elements other than the center element is 0 zero to calculate the third spatial filter e.g. F9 .

At step S the filter generation unit divides the third spatial filter into plural spatial filters. For example the filter generation unit extracts the fourth spatial filter e.g. F3 from the first spatial filter.

Further the filter generation unit generates a filter e.g. F5A obtained by convolving a finite filter in which total sum of values of elements is 0 zero and at least two elements are non zero with the fourth spatial filter. The filter generation unit subtracts the generated filter from a filter in which a value of the center element is 1 one and values of elements other than the center element is 0 zero to calculate the fifth spatial filter e.g. F5A .

Further the filter generation unit minimizes the estimation function using the third spatial filter and the fifth spatial filter to calculate the sixth spatial filter e.g. F5B .

At step S the filter generation unit determines whether the fifth spatial filter and the sixth spatial filter are filters having the predetermined number of elements or less. When it is determined that each of the generated the spatial filters has the predetermined number of elements or less YES at step S the fifth spatial filter and the sixth spatial filter are defined as the spatial filter in plural stages. Further when at least one of the generated spatial filters have the number of elements larger than the predetermined number of elements the process goes back to step S. The above described process of generating plural spatial filters is repeated until each of the generated spatial filters becomes the predetermined number of elements or less.

The process for determining gain will be described next. is a flow chart illustrating an example of a gain determination process in the embodiment 1. At step S illustrated in the image capturing apparatus captures a chart image.

At step S the post processing unit analyzes resolution before correction. At step S the post processing unit set an initial value of gain.

At step S the image processing unit multiplies the above described plural spatial filter by the set gain to correct the image.

At step S the post processing unit analyzes resolution after correction. At step S the post processing unit determines whether the gain estimation function becomes minimal. When it is determined that the gain estimation function is minimal YES at step S the process proceed to step S. When the gain estimation function is not minimal No at step S the process goes back step S and gain is changed.

At step S the post processing unit determines gain with which the gain estimation function becomes minimal and sets the determine gain in the gain multiplication unit .

As described above according to embodiment 1 when the spatial filter having anisotropy in resolution is made to be finitized to have a predetermined number of elements degradation of image may be prevented.

An image capturing apparatus including an image processing apparatus in embodiment 2 will be described next. Noise emphasized by the correction performed for improving resolution is reduced in embodiment 2.

The flat portion as well as noise component are included in the captured image. Therefore even the flat portion causes an image to include a minute amplitude variation.

Here as illustrated in embodiment 1 when correction is made for the image to improve resolution an effect of amplitude magnification occurs but the noise component including the minute amplitude variation causes the amplitude to be magnified. Therefore the noise at the flat portion is emphasized.

A low pass filter is used to reduce noise. However the low pass filter filters the entire image and thus when the noise in the flat portion is to be reduced the edge portion originally intended to be corrected changes to a gentle shape.

Therefore it becomes important to reduce the noise non linearly for the flat portion and the edge portion. There is a coring process as a known non linear noise process. See for example Japanese Laid Open Patent Publication No. 2008 199448.

In the coring process when an input value is a threshold value or less an output is made to be 0 to prevent the noise from being emphasized. Further in the coring process when an input value is larger than a threshold value the amplitude of an output is reduced to be small such that a discontinuity is avoided.

The following object to be solved arises in a case where the coring process is just applied after the filtering of each spatial filtering of the embodiment 1.

As illustrated in the coring process accompanying the degradation of amplitude is applied in the filtering of filters in plural stages having anisotropy the degradation of gain varies depending on the direction and thus it is unable to improve anisotropy.

Therefore in the embodiment 2 to be described below a predetermined gain is determined with respect to an absolute value of a value after the filtering of the filter in such a manner that when the absolute value is equal to or less than a lower threshold value gain is set to 0 zero . When the absolute value is equal to or more than an upper threshold value gain is set to a constant value and when the absolute value is between the lower threshold value and the upper threshold value gain is made to be varied in stepwise fashion.

The image capturing apparatus in the embodiment 2 is similar to the image capturing apparatus in the embodiment 1 and thus the same reference numerals are given to the same components to describe the embodiment 2.

The filter processing unit in the embodiment 2 will be described next. is a block diagram illustrating another exemplary schematic configuration of the filter processing unit in the embodiment 2. The filter processing unit will be described. The filter processing unit includes a convolution operation unit a gain determination unit a gain multiplication unit a subtraction unit and a filter analysis unit .

The same reference numerals are given to the same configuration of the filter processing unit in the embodiment 2 as the configuration illustrated in in the embodiment 1.

The gain determination unit determines the threshold value of an absolute value of the luminance value subjected to convolution to determine gain. A gain determination process will be described later.

The gain multiplication unit multiplies the luminance value after the filtering by gain determined by the gain determination unit . Further the gain multiplication unit when convolution is performed at plural stages at least one gain multiplication may be performed or gain multiplication may be performed at all the plural stages.

The subtraction unit calculates the difference between the image to which gain is multiplied and the original image. The processing described above performed the number of times that is equals to the number of plural stages.

The filter analysis unit analyzes intensity of filter of the spatial filters in plural stages based on coefficients of filter and determines the spatial filter for which gain is multiplied based on a result of analysis. For example the filter analysis unit determines a spatial filter in such a manner that a value subjected to the filtering in the spatial filter having the strongest intensity of filter is multiplied by gain. In the meantime the filter analysis unit is not a necessary component for the filter processing unit . Further the filter analysis unit is just needed to determine that the intensity of filter is stronger as the difference between the maximum filter coefficient and the minimum filter coefficient becomes gradually larger.

The dy to which gain is multiplied is subtracted from the original image. The original image after subtraction is subjected to the filtering in a second stage. A corrected image is generated by subtracting the result of the second stage of the filtering from the original image after subtraction.

The effect according to the embodiment 2 will be described next. is a view for explaining an first effect in the embodiment 2. The expression threshold value processing is absent illustrated in represents a result of processing performed in the embodiment 1. The expression threshold value processing is present illustrated in represents a result of processing performed in the embodiment 2.

As illustrated in the degradation of amplitude is negligible in the threshold value processing is present compared to that in the threshold value processing is absent at a portion where the amplitude is large. is a view which magnifies a portion e.g. a flat portion where variation of amplitude is smaller than the threshold value. As illustrated in it may be seen that the amplitude in the threshold value processing is present is not much emphasized compared to that in the threshold value processing is absent at the flat portion.

As illustrated in the resolution in the threshold value processing is present increases compared to that in the before correction at a portion where the amplitude is large. Further as illustrated in the gain is set to zero in the threshold value processing is present and thus the threshold value processing is present is equal to before correction and noise is not emphasized at the flat portion.

The operations of the image processing unit in the embodiment 2 will be described next. is a view illustrating an example of a corrected image generation process in the embodiment 2. At step S illustrated in FIG. the convolution operation unit performs the first stage of the filtering on the original image.

At step S the gain determination unit determines gain based on a value after the first stage of the filtering. The gain determination process will be described later.

At step S the gain multiplication unit multiplies the value dy by the gain determined in the gain determination unit .

At step S the subtraction unit subtracts the value dy to which gain is multiplied from the original image.

At step S the convolution operation unit performs the second stage of the filtering on the original image for which subtraction is performed.

At step S the subtraction unit subtracts the result of the second stage of the filtering from the original image for which subtraction is performed to generate a corrected image.

While the gain is multiplied after the first stage of the filtering in the above described process the gain may be multiplied after the second stage of the filtering or after each filtering as described in later.

At step S the gain determination unit determines whether the absolute value Cth is equal to or more than the upper threshold Th1. When it is determined that the Cth is equal to or more than the Th1 Cth Th1 YES at step S the process proceeds to step S. When the Cth is less than the Th1 Cth

At step S the gain determination unit sets an output gain Gain th to the Gain . The Gain is a preset value and may be for example 1 one .

At step S the gain determination unit determines whether the absolute value Cth is equal to or less than the lower threshold value Th0 . When it is determined that the Cth is equal to or less than the Th0 Cth Th0 YES at step S the process proceeds to step S. When the Cth is larger than Th0 and less than Th1 Th0

At step S the gain determination unit obtains the output gain Gain th from the following equation 41. Gain  0 1 Gain 41 

At step S the gain determination unit determines whether the absolute value Cth is equal to or less than the lower threshold value Th0 . When it is determined that the absolute value Cth is equal to or less than the threshold value Th0 Cth Th0 YES at step S the process proceeds to step S. When the absolute value Cth is larger than the threshold value Th0 Cth Th0 NO at step S the process proceeds to step S.

At step S the gain determination unit obtains the output gain Gain th from the following equation 42. Gain  0 Keisya 42 .

As described above according to embodiment 2 anisotropy in resolution may be improved and noise may be prevented from being emphasized at the flat portion.

Other configuration of the gain processing in the embodiment 2 will be described first. is a view for explaining a second corrected image generation processing in the embodiment 2. In an example illustrated in the luminance value obtained by convolving a filter of 5 5 elements in second stage with the original image for which subtraction is performed is denoted by the value dy in . The gain determination unit determines gain according to the value of the dy . The gain multiplication unit multiplies the value dy by the determined gain.

An image after having been subjected to the first stage of the filtering is subtracted from the original image. The original image after subtraction is subjected to the second stage of the filtering. The luminance value after the second stage of the filtering is multiplied by gain. The corrected image is generated by subtracting the image after gain multiplication from the original image after subtraction.

The filter having a larger intensity is determined by the filter analysis unit based on the filter coefficient and the gain determination unit and the gain multiplication unit may perform the gain determination and the gain multiplication respectively after the filter determined by the filter analysis unit is subjected to the filtering.

The value dy after the first stage of the filtering is multiplied by gain and then the value is subtracted from the original image. The original image after subtraction is subjected to the second stage of the filtering. The value dy after the second stage of the filtering is multiplied by gain. The corrected image is generated by subtracting the image after gain multiplication from the original image after subtraction. In the meantime the example illustrated in may be applied in a case where intensity of filters in the first stage and the second stage are about the same degree of intensity.

In this case when the degree of emphasis of the corrected image is controlled the gain values may become the same in the first stage and the second stage. Therefore for example when the gain processing is performed only in the first stage filtering the gain multiplication unit needs to only multiply the maximum gain Gain which is the same as in the first stage of the filtering in the second stage of the filtering.

Further when the gain processing is performed only in the second stage filtering the gain multiplication unit needs to only multiply the maximum gain Gain which is the same as in the second stage filtering in the first stage filtering. Further when the gain processing is performed in both the first stage filtering and the second stage filtering the gain determination unit needs to make the maximum gain Gain in both the first stage filtering and the second stage filtering to be the same.

The image processing apparatus in the embodiment 3 will be described next. In the embodiment 3 the processing by the coefficient analysis unit described above and the processing of the image processing unit of the embodiment 1 or embodiment 2 is made to be performed respectively by for example the CPU or the DSP.

The control unit may be for example a CPU Central Processing Unit which controls various apparatus or operates or manipulates data in a computer. Further the control unit may be an operation apparatus which executes a program stored in the main storage unit or in the auxiliary storage unit .

Further the control unit may execute the program for a coefficient analysis processing or an image processing stored in the auxiliary storage unit to perform each processing as described above.

The main storage unit may include for example a ROM Read Only Memory or a RAM Random Access Memory and is a storage apparatus which temporarily stores data or a program such as an application software or an OS which is a basic software executed by the control unit .

The auxiliary storage unit may include for example a HDD Hard Disk Drive and may be a storage apparatus which stores data relating to for example the application software. Further the auxiliary storage unit may store the program for the coefficient analysis processing or the image processing acquired from for example the recording medium .

The communication unit may perform a wired or wireless communication. The communication unit may acquire a plurality of images from for example the server and stores the plurality of images in for example the auxiliary storage unit .

The recording medium I F interface unit is an interface between the recording medium e.g. a flash memory connected via a data transfer path such as a USB Universal Serial Bus and the image processing apparatus.

Further the image processing program or the coefficient analysis program described in the embodiment 1 and the embodiment 2 may be stored in the recording medium and the program stored in the recording medium may be installed in the image processing apparatus via the recording medium I F unit . Accordingly the coefficient analysis program and the image processing program installed may be executed by the image processing apparatus.

The camera I F unit is an interface which communicates with the camera . A chart image or an ordinary image to be corrected captured from the camera is acquired by the camera I F unit from the camera and is stored in for example the auxiliary storage unit .

The camera may photograph a chart image as illustrated in or ordinary scenes and people. The photographed image is received by the image processing apparatus via the camera I F unit . In the meantime the camera may be built in the image processing apparatus.

Accordingly the image processing apparatus may acquire the chart image and calculate the spatial filter at each position to correct the image to be correct using the calculated spatial filter.

Therefore the program for implementing the coefficient analysis processing or the image processing may be stored in the recording medium to cause the computer to perform the above described coefficient analysis processing or the image processing.

For example the program may be recorded in the recording medium and the recording medium in which the program is recorded may be allowed to be read by for example a computer a portable terminal a smart phone and a tablet terminal in order to implement the coefficient analysis processing or the image processing.

Further the recording medium may include various recording medium in which information is recorded optically electrically or magnetically such as for example a CD ROM a flexible disk an opto magnetic disk and a semiconductor memory. The recording medium may also include a ROM and a flash memory where information is electrically recorded. Further the recording medium does not include a transitory medium such a carrier wave.

Further the charts illustrated in to may be used as an exemplary chart. is a view illustrating an example of a first chart. In the chart illustrated in the resolution may be analyzed at least two directions.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiment s of the present invention has have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

