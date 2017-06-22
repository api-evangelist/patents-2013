---

title: Image processor for and method of upscaling and denoising using contextual video information
abstract: The disclosed method uses contextual information obtained during upscaling and/or denoising of frames. Relevant correspondences between patches within a frame and between frames, are detected, managed and exploited. The correspondence information is simultaneously used and updated while video frames are being processed. Two approaches may be used: 1. keeping, searching for and updating a database of useful patches, by adding frequently visible similar patches, aggregating high-frequency, low-noise information associated with the similar patches, and removing less-observed patches; 2. Using the high-resolution and noise-reduced information that was collected from earlier video frames, and is expressed by the output of latest processed frame, for upscaling and/or noise-reducing the next processed frame.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09235874&OS=09235874&RS=09235874
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09235874
owner_city: Suwon-Si, Gyeonggi-Do
owner_country: KR
publication_date: 20131030
---
This application claims priority under 35 U.S.C. 119 to Korean Patent Application No. 10 2013 0038165 filed on Apr. 8 2013 the disclosure of which is incorporated by reference in its entirety.

The inventive concept described herein relates to a semiconductor device and more particularly relate to an image processor and an image processing method of the image processor.

As mobile image processing techniques and image processing devices are developed images may be widely utilized in mobile devices such as smartphones tablets and other consumer electronics devices. Images may be used to visually provide information to a user and may have a higher effectiveness compared with typical texts and voice. Images may be captured by image sensors such as a CMOS image sensor a CCD image sensor and so on.

The quality e.g. resolution of an image captured through an image sensor generally depends upon the resolution and performance of the image sensor. While a high performance image sensor captures an image with the high quality its inclusion in a mobile device may cause an increase in the manufacturing cost.

An aspect of the inventive concept prevent an increase in the manufacturing cost while enabling high quality images to be acquired using a low quality image captured by a low priced image sensor. In particular exemplary embodiments of an image sensor used in a mobile device according an exemplary embodiment of the inventive concept may have characteristics such as a small size a light weight low power consumption. An aspect of the inventive concept provides a technique capable of acquiring high quality images using a low quality image acquired through a low priced light small low power image sensor. An aspect of the inventive concept is directed to provide an image processor capable of acquiring high quality images from low quality images with the improved reliability and accuracy and an image processing method thereof.

One aspect of the inventive concept is directed to provide an image processing method of an image processor that comprises upscaling an input frame based on a patch dictionary unit including a plurality of patches being frame fragments the size of each frame fragment being smaller than that of a frame updating the patch dictionary unit according to an upscale result wherein at upscaling of the input frame a high frequency component of the upscaled frame is reinforced based on the patch dictionary unit.

In an exemplary embodiment the patch dictionary unit is updated based on at least one patch used at the upscaling.

In an exemplary embodiment the upscaling an input frame comprises selecting a magnified patch of the upscaled input frame detecting a descriptor indicating a low frequency component of the magnified patch from the magnified patch searching for a first patch in a relevant area of the input frame based on the descriptor searching for a second descriptor in the patch dictionary unit based on the descriptor and modifying the magnified patch using one closer to the magnified patch from among the first and second patches.

In an exemplary embodiment the updating the patch dictionary unit according to an upscale result comprises calculating similarity difference between the first patch and the second patch and updating the patch dictionary unit with the first patch or ignoring the first patch according to the calculated similarity difference.

In an exemplary embodiment the updating the patch dictionary unit according to an upscale result comprises calculating the difference between the first patch and the second patch replacing the second patch stored in the patch dictionary unit with the first patch if the calculated difference is less than a threshold value determining whether the first patch is closer to the magnified patch than the second patch i.e. determining whether the difference between the first patch and the magnified patch is less than the difference between the second patch and the magnified patch if the calculated difference is not less than a threshold value adding the first patch to the patch dictionary unit if the first patch is closer to the magnified patch than the second patch and ignoring the first patch if the first patch is not closer to the magnified patch than the second patch.

In an exemplary embodiment the updating the patch dictionary unit according to an upscale result further comprises increasing the score of a patch used at the upscaling from among patches stored in the patch dictionary unit assigning a predetermined score to a new patch if the new patch is added to the patch dictionary unit and decreasing the scores of patches stored in the patch dictionary unit if the predetermined number of search operations is executed at the patch dictionary unit.

In an exemplary embodiment the updating the patch dictionary unit according to an upscale result further comprises deleting a patch having a score lower than a threshold value from among patches stored in the patch dictionary unit after the scores are decreased.

In an exemplary embodiment the updating the patch dictionary unit according to an upscale result further comprises deleting a patch having a score lower than a threshold value from among patches stored in the patch dictionary unit if the size of the patch dictionary unit reaches a predetermined limit value upon adding of a new patch to the patch dictionary unit.

In an exemplary embodiment the updating the patch dictionary unit according to an upscale result further comprises combining a new patch and similar patches if the number of the similar patches similar to the new patch from among patches stored in the patch dictionary unit is larger than a threshold value upon adding of the new patch to the patch dictionary unit.

In an exemplary embodiment if the patch dictionary unit is initialized remaining patches other than baseline patches are deleted from the patch dictionary unit.

In an exemplary embodiment the upscaling an input frame comprises selecting a magnified patch of the upscaled input frame searching for at least one first patch similar to the magnified patch in a relevant area of the upscaled input frame searching for a second patch similar to the magnified patch in the patch dictionary unit executing refinement using the at least one first patch and the second patch and replacing the magnified patch with the refined patch.

In an exemplary embodiment the updating the patch dictionary unit according to an upscale result comprises updating the patch dictionary unit with the at least one first patch if the second patch is not searched for.

In an exemplary embodiment the updating the patch dictionary unit according to an upscale result comprises increasing the score of the second patch if the second patch is searched for at the patch dictionary unit adding the at least one first patch to the patch dictionary unit with a first initial score if the second patch is not searched for in the patch dictionary unit and the at least one first patch is searched for and adding the magnified patch to the patch dictionary unit with a second initial score smaller than the first initial score if the second patch is not searched for in the patch dictionary unit and the at least one first patch is not searched for.

In an exemplary embodiment the image processing method further comprises downscaling a previous frame upscaled generating a motion field by performing motion detection on the downscaled frame and the input frame and generating a partially upscaled frame by copying patches of the previous frame upscaled based on the motion field wherein the upscaling is executed with respect to the partially upscaled frame.

In an exemplary embodiment the updating the patch dictionary according to an upscale result comprises adding frequently visible similar patches in upscaled frames to the patch dictionary unit aggregating high frequency and low noise information associated with the plurality of patches in the patch dictionary unit and removing less observed patches in the upscaled frames from the patch dictionary unit.

In an exemplary embodiment the upscaling an input frame based on a patch dictionary unit comprises upscaling or noise reducing the input frame using the high frequency and low noise information which are collected from a plurality of previous input frames.

One aspect of the inventive concept is directed to provide an image processor which comprises a patch dictionary unit for storing a plurality of patches being frame fragments the size of each frame fragment being smaller than the size of a frame an upscale unit configured to receive an input frame upscale the input frame and to reinforce a high frequency component of the upscaled frame referring to the input frame and the patch dictionary unit and a dictionary management unit configured to update the patch dictionary unit based on the patches used by the upscale unit.

In an exemplary embodiment the image processor further comprises a patch refinement unit configured to execute refinement of a patch of the upscaled input frame and a patch of the patch dictionary unit searched for by the upscale unit and wherein the upscale unit executes an upscale on the input frame using the refined patches and the dictionary management unit updates the patch dictionary unit based on the refined patches.

In an exemplary embodiment the image processor further comprises a downscale unit configured to downscale an output frame of the upscale unit a motion estimation unit configured to perform motion estimation using a frame downscaled by the downscale unit and an initial input frame and a motion compensation unit configured to generate a partially upscale frame by copying patches of the output frame based on a motion field estimated by the motion estimation unit the partially upscale frame being sent to the upscale unit as the input frame.

One aspect of the inventive concept is directed to provide an image processor comprising a motion estimation unit configured to perform motion estimation using a first upscaled then downscaled frame output by a downscale unit and an upscale unit and second initial input frame and a motion compensation unit configured to generate a partial frame by copying patches of the first upscaled then downscaled frame based on a motion field estimated by the motion estimation unit the partial frame being sent to the upscale unit.

Embodiments will be described in detail with reference to the accompanying drawings. The inventive concept however may be embodied in various different forms and should not be construed as being limited only to the illustrated embodiments. Rather these embodiments are provided as examples so that this disclosure will be thorough and complete and will fully convey the concept of the inventive concept to those skilled in the art. Accordingly known processes elements and techniques are not described with respect to some of the embodiments of the inventive concept. Unless otherwise noted like reference numerals denote like elements throughout the attached drawings and written description and thus descriptions will not be repeated. In the drawings the sizes and relative sizes of layers and regions may be exaggerated for clarity.

It will be understood that although the terms first second third etc. may be used herein to describe various elements components regions and or sections these elements components regions and or sections should not be limited by these terms. These terms are only used to distinguish one element component region or section from another region or section. Thus a first element component region or section discussed below could be termed a second element component region or section without departing from the teachings of the inventive concept. The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the inventive concept. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this inventive concept belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and or the present specification and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

The processor controls the overall step of the computing device and performs logic and calculations. For example the processor may be a system on chip SoC . The processor may be a general purpose processor an application processor or a specific purpose processor.

The processor may include an image processor . The image processor is configured to process images. The image processor may receive and process low resolution images to output high resolution images. The image processor can be formed of an intellectual property IP known to persons skilled in the art.

The memory is accessed by the processor . The memory may be a working memory or a main memory of the processor or of the computing device . The memory may include volatile memories such as a static RAM SRAM a dynamic RAM DRAM a synchronous DRAM SDRAM and so on and or nonvolatile memories such as a flash memory a phase change RAM PRAM a magnetic RAM MRAM a resistive RAM RRAM a ferroelectric RAM FRAM and so on.

In an exemplary embodiment the memory and the storage may be formed of the same type of nonvolatile memories. In this case the memory and the storage may be integrated to one semiconductor integrated circuit.

The modem may communicate with an external device according to the control of the processor . For example the modem may perform wire or wireless communication with the external device. The modem may perform communications based on at least one of various wireless communications manners such as LTE Long Term Evolution WiMax GSM Global System for Mobile communication CDMA Code Division Multiple Access Bluetooth NFC Near Field Communication WiFi RFID Radio Frequency IDentification and so on or various wire communications manners such as USB Universal Serial Bus SATA Serial AT Attachment SCSI Small Computer Small Interface Firewire PCI Peripheral Component Interconnection and so on.

The user interface may communicate with a user according to the control of the processor . For example the user interface may include user input interfaces such as a keyboard a keypad a button a touch panel a touch screen a touch pad a touch ball a camera a microphone a gyroscope equivalent sensor a vibration sensor and so on. The user interface may include user output interfaces such as an LCD Liquid Crystal Display an OLED Organic Light Emitting Diode display device an AMOLED Active Matrix OLED display device a beam projector an LED a speaker a motor solenoid and so on.

The computing device may be a mobile device such as a smart phone a smart pad a smart camera or the like. The computing device may be a device such as a smart television a computer a notebook computer a netbook or the like.

The image processor according to an exemplary embodiment of the inventive concept provides two functions. One function is a frame generation. The image processor takes current frame and upscales and denoises it using a patch dictionary. Another function is a patch dictionary management for managing the patch dictionary. The image processor updates the patch dictionary by new information from the current frame. Those two functions are performed in parallel and thus the updating of the patch dictionary is performed online or on the fly manner. The two functions are described referring four examples.

A first exemplary embodiment upscales an input frame to output a magnified frame. The first exemplary embodiment searches patches from the patch dictionary and the input frame and modify high frequency components of a magnified patch using the searched for patches. The patch dictionary is updated based on a patch used at the magnifying. The first exemplary embodiment is described referring through .

A second exemplary embodiment searches for patches from a patch dictionary and a magnified frame. The second exemplary embodiment restores high frequency components of a magnified patch by aligning similar patches of the same scale. The patch dictionary is updated based on a result of the aligning. Variations of the first exemplary embodiment can be applied to obtain a second third and fourth exemplary embodiment. The second exemplary embodiment is described referring to through .

A third exemplary embodiment takes advantage of high correlation between frames. A high resolution output of a previous frame is used to generate a high resolution output of a current frame using hybrid techniques such as a motion compensation a gap filling etc. The third exemplary embodiment reconstructs the high resolution current frame using the motion compensation and executes a patch search and a patch dictionary management at gaps. The third exemplary embodiment is described referring to and .

A fourth exemplary embodiment combines the second exemplary embodiment and the third exemplary embodiment. The fourth exemplary embodiment restores gaps by aligning patches of the same scale. The fourth exemplary embodiment is described referring to through .

Examples of the inventive concept can update the patch dictionary by adding frequently visible similar patches in pre processed upscaled frames to the patch dictionary aggregate high frequency and now noise information associated with patches in the patch dictionary and remove less observed patches in the pre processed upscaled frames from the patch dictionary. Furthermore the examples of the inventive concept can upscale or noise reduce an input frame using the high frequency and low noise information that are collected from a plurality of previous input frames.

The upscale unit may receive a low resolution frame LRF . The upscale unit can upscale the input frame LRF referring to the input frame LRF or an input image and the patch dictionary unit . The upscale unit can output the upscaled frame as a high resolution frame HRF.

The patch dictionary unit can store a plurality of patches. The patches may be frame fragments each having a size less than the size of the input frame LRF and less than the size of the output frame HRF. The patch dictionary unit may store predetermined baseline patches or patches acquired by learning.

The dictionary management unit is configured to manage the patch dictionary unit . The dictionary management unit receives patch use data PUD from the upscale unit . The patch use data PUD may include information about patches that are used during upscaling of the upscale unit . The dictionary management unit manage the patch dictionary unit based on the patch use data PUD. For example the dictionary management unit can add patches to the patch dictionary unit change patches stored in the patch dictionary unit or delete patches stored in the patch dictionary unit .

In there is illustrated an example in which the patch dictionary unit is a component of the image processor . However the inventive concept is not limited thereto. For example the patch dictionary unit may be provided at a computing device without location limitations and performs as a storage medium in which a plurality of patches are stored. The patch dictionary unit may be implemented in the storage as a type of database.

In step S a patch dictionary unit updates according to an upscale result. The dictionary management unit updates the patch dictionary unit according to the upscale result. For example the patch dictionary unit may be updated using the searched for patches. The dictionary management unit may update the patch dictionary unit according to similarity between the searched for patches.

A process in which steps S and S are performed is illustrated in the example of . Referring to an input frame IF input patch IP a magnified frame MF and a magnified patch MP may be illustrated. The input patch IP may be a patch on the input frame IP and corresponds to the magnified patch MP.

Referring to and in step S a descriptor indicating a low frequency component of the magnified patch MP is detected. The descriptor is detected from the magnified patch MP. In an exemplary embodiment the descriptor includes information about a low frequency component of a region including the magnified patch MP. An exemplary descriptor is disclosed in a paper published by Jianchao Yang et als 2010 entitled IMAGE SUPER RESULTION VIA SPARSE REPRESENTATION http ieeexplore.ieee.org Digital Object Identifier 10.1109 TIP.2010.2050625 the contents of which are incorporated by reference herein.

In step S a first patch is searched for from a relevant area of the input frame based on the descriptor. For example a patch having a characteristic similar to the descriptor may be searched for at the relevant area of the input frame.

In step S a second patch may be searched for in a patch dictionary unit based on the descriptor. For example there may be a search for a descriptor similar to a calculated descriptor from among patches stored in the patch dictionary unit . The patch dictionary unit performs a search operation using one of various methods such as exhaustive search tree based search hash based search index based search and so on. The patch dictionary unit may be searched according to an ANN Advanced approximate Nearest Neighbors Search method or a search method in which an index is added to each area and the ANN and index based search are combined. The ANN is disclosed in a paper published by Marius Muja and David G. Lowe 2009 entitled FAST APPROXIMATE NEAREST NEIGHBORS WITH AUTOMATIC ALGORITHM CONFIGURATION the contents of which are herein incorporated by reference.

A process in which steps S and S are performed is illustrated in the example of . Referring to a magnified frame MF an input frame IF and a patch dictionary unit are illustrated.

The input frame IF is an original frame that becomes magnified. The input frame IF may include a relevant area RA. The relevant area RA may be an area including an input patch IP on the input frame IF corresponding to the magnified patch MP. The size of the relevant area RA may be less than that of the input frame IF or equal to that of the input frame IF. A first patch P having a characteristic similar to a descriptor of the magnified frame MP may be searched for at the relevant area RA. The descriptor of the magnified frame MP may include information about a low frequency component of the magnified patch MP for example. Thus the first patch P searched for at the relevant area RA may be a patch which has a low frequency component similar to the magnified patch MP. The size of the first patch P is equal to that of the magnified patch MP.

A second patch P may be searched for in the patch dictionary unit . Like the first patch P the second patch P searched for at the relevant area RA may be a patch which has a low frequency component similar to the magnified patch MP. The size of the second patch P is equal to that of the magnified patch MP.

Referring to and in step S the magnified patch MP is modified using the patch closer to the magnified patch MP selected from among the first and second patches P and P. For example the first patch P searched for in the input frame IF before magnification may include a high frequency component. The second patch P searched for in the patch dictionary unit may include a high frequency component.

A high frequency component of the magnified patch MP may be reinforced using a high frequency component of a patch closer to the magnified patch MP selected from among the first and second patches P and P. For example the step of selecting a patch closer to the magnified patch MP from among the first and second patches P and P may be performed based on the magnified patch MP and descriptors of the first and second patches P and P.

An exemplary method of reinforcing the high frequency component from one patch to another is disclosed in Example Based Super Resolution IEEE Computer Graphics and Applications Vol. 22 pp. 56 65 March 2002 published in Apr. 22 2002 by W. T. Freeman et al which is incorporated herein as a reference.

In the magnified frame MF the magnified patch MP may be replaced with a patch the high frequency component of which is reinforced. When reinforcing of high frequency components on patches of the magnified frame MF is ended there may be generated a frame the high frequency component of which is reinforced. The frame the high frequency component of which is reinforced may be output as the output frame HRF.

The patches P and P used during an upscale operation and the differences between the patches P and P and the magnified patch MP may be transferred to the dictionary management unit as patch use data PUD.

In an exemplary embodiment the difference or similarity between patches may be calculated according to one of various methods such as SAD Sum of Absolute Difference correlation and so on.

The patch update unit receives patch use data PUD from an upscale unit . The patch update unit updates patches stored in a patch dictionary unit based on the patch use data PUD. For example the patch update unit may add a patch included in the patch use data PUD to the patch dictionary unit . The patch update unit may replace a patch stored in the patch dictionary unit with a patch included in the patch use data PUD. The patch update unit may combine the patch stored in the patch dictionary unit and the patch included in the patch use data PUD.

The score management unit is configured to manage patches registered at the patch dictionary unit . Each of the patches registered at the patch dictionary unit has a score. The score management unit may increase or decrease scores of patches of the patch dictionary unit . Alternatively the score management unit may set scores of patches of the patch dictionary unit to predetermined values.

The patch remove unit may be configured to remove e.g. delete a patch from the patch dictionary unit . The patch remove unit may remove a patch from the patch dictionary unit based on a predetermined event or scores of patches.

The initialization unit is configured to initialize the patch dictionary unit . At initialization the initialization unit deletes all patches of the patch dictionary unit for example. At initialization the initialization unit may delete the remaining patches of the patch dictionary unit other than predetermined baseline patches. The initialization unit may perform initialization by deleting all patches of the patch dictionary unit and adding baseline patches to the patch dictionary unit . When an image processor starts to process an image the initialization unit may initialize the patch dictionary unit . The initialization unit may initialize the patch dictionary unit when the image processor detects a video cut or scene change.

The high frequency component in the table of patches indicates a high frequency component which a patch has. The high frequency component may be used to reinforce a magnified patch.

The descriptor may include information about a low frequency component extracted from an area including a patch. For example when a patch has a high frequency component of a frame fragment having a 5 5 size the descriptor of the patch may be information about a low frequency component extracted from a 15 15 size of frame fragment including the patch. The descriptor may be used to calculate the difference from a magnified patch MP.

In there are illustrated exemplary patches each including a descriptor a high frequency component and a score. However the inventive concept is not limited thereto. For example patches stored in the patch dictionary unit may include information to be compared with a magnified patch MP and information used to reinforce a high frequency component of the magnified patch MP.

In step S whether the calculated difference is less than a threshold value is determined. If the calculated difference is less than the threshold value in step S the second patch P may be replaced with the first patch P. If the difference between the first patch P and the second patch P is less than the threshold value the first patch and second patches P and P may include very similar information. In this case the first patch P later than the second patch P searched for in a patch dictionary unit may include information suitable for current and next frames. Thus the second patch P registered at the patch dictionary unit may be replaced with the first patch P searched for in an input frame IF.

In step S whether the first patch P is closer to a magnified patch MP than the second patch P may be determined. In exemplary embodiments the difference between the first patch P and the magnified patch MP and the difference between the second patch P and the magnified patch MP may be calculated or received as patch use data PUD.

If the first patch P is closer to the magnified patch MP than the second patch P then in step S the first patch P may be added to the patch dictionary unit . In the case that the first and second patches P and P are not sufficiently similar No branch of decision step S and the first patch P newly searched for is closer to the magnified patch MP than the second patch P the first patch P newly searched for is added to the patch dictionary unit . Thus in the case that the first patch P newly searched for includes useful information not stored in the patch dictionary unit the first patch P newly searched for is added to the patch dictionary unit . When the first patch P is added it may be added to the patch dictionary unit to have a predetermined score. The predetermined score assigned to the first patch P may be decided according to the difference between the first patch P and the magnified patch MP. For example as the difference between the first patch P and the magnified patch MP increases the score assigned to the first patch P may decrease.

If the first patch P is not closer to the magnified patch MP than the second patch P in step S the first patch P newly searched for may be ignored and the patch dictionary unit is not updated. Thus in the case that the first patch P newly searched for does not include information more useful than patches stored in the patch dictionary unit the first patch P newly searched for may be ignored.

In exemplary embodiments instead of replacing the second patch P with the first patch P such a patch that the first and second patches P and P are combined to replace the second patch P. Thus the first patch P newly searched for may be combined with the second patch registered at the patch dictionary unit . The first and second patches P and P may be combined based on one of various methods such as an average a weighted average a moving average and so on. The combination may include refinement.

In step S the score of a patch used is increased. For example the score of a patch used in an upscale operation from among patches stored in a patch dictionary unit is increase. As described in step S of replacement with a first patch P newly searched for may be performed or the score of a patch combined with the first patch newly searched for may increase. As described in step S of the score of a patch used for reinforcement of a high frequency component of a magnified patch MP may increase.

In step S whether a patch is added is determined. For example as described in step S of whether the first patch P newly searched for is added to the patch dictionary unit is determined. If a patch is added in step S a score may be assigned to the patch added.

For example its score may be decided according to the difference or similarity between the added patch and the magnified patch MP. Its score may increase in proportion to a decrease in the difference between the added patch and the magnified patch MP or in proportion to an increase in the similarity between the added patch and the magnified patch MP. As the added patch includes information useful to upscale the score of the added patch may increase.

For example its score may be decided according to the difference or similarity between the added patch and patches stored in the patch dictionary unit . The score of the patch added may increase in proportion to an increase in the difference between the added patch and patches stored in the patch dictionary unit or in proportion to a decrease in the similarity between the added patch and patches stored in the patch dictionary unit . Thus as the added patch includes information distinguishable from patches stored in the patch dictionary unit the score of the added patch may increase.

In step S whether a search operation has been performed by a predetermined unit of search is determined. For example it is determined whether a search operation has been performed by a line unit of an input frame LRF by a unit of two or more lines thereof or by a frame unit. In the case that a search operation is performed by a predetermined unit in step S scores of all patches stored in the patch dictionary unit may decrease. The scores of the patches may decrease by a predetermined value. In exemplary embodiments scores of the remaining patches other than baseline patches may only decrease.

In steps S and S the scores of patches stored in the patch dictionary unit decrease whenever a search operation is performed by a predetermined unit. Thus the scores of patches not used at an upscale unit may gradually decrease.

As described above patches stored in the patch dictionary unit are managed. The score of a patch frequently used at an upscale operation may be managed to be high.

In step S whether a score lower than a threshold value exists is determined. For example whether a patch having a score lower than the threshold value from among patches stored in the patch dictionary unit exists is determined. If a score lower than a threshold value does not exist removing of patches is not performed.

If a score lower than a threshold value exists in step S a patch having a score lower than a threshold value is removed or deleted from the patch dictionary unit .

As described with reference to the score of a patch not used at an upscale operation may decrease. Patches having scores or unused levels lower than a threshold value from among patches stored in the patch dictionary unit are removed from the patch dictionary unit through the operating method of . It is possible to prevent the patch dictionary unit from taking a capacity excessively by removing unused patches from the patch dictionary unit . In general a mobile device may have limited resources e.g. a memory capacity battery energy etc. in comparison with a fixed device. If unused patches are removed from the patch dictionary unit it is possible to optimizing a mobile device that includes an image processor to perform an upscale operation referring to the patch dictionary unit .

In step S whether the number of similar patches of patches stored in the patch dictionary unit is larger than a threshold value is determined. For example the number of patches similar to an added patch from among patches stored in the patch dictionary unit may be detected. The number of patches having a difference from an added patch less than a reference value from among patches stored in the patch dictionary unit may be detected. The detected number may be compared with a threshold value.

In step S similar patches are combined. For example patches having a score lower than a second reference value from among the detected patches may be combined one another. Descriptors high frequency components and scores of patches may be combined one another. The descriptors high frequency components and scores of the patches may be combined based on one of various algorithms such as an average a weighted average a moving average and so on. The combination may include refinement.

As described with reference to the score of a patch not used at an upscale operation may decrease. Patches having scores or unused levels lower than a threshold value from among patches stored in the patch dictionary unit may be combined into one patch at the patch dictionary unit through the operating method of . It is possible to prevent the patch dictionary unit from taking up capacity excessively by combining unused patches.

In step S whether the size inventory of a patch dictionary unit has reached its limit is determined. For example whether the number of patches stored in the patch dictionary unit reaches a predetermined limit value is determined. For example whether a free storage capacity of the patch dictionary unit has decreased down to a predetermined limit value is determined. If the inventory size of the patch dictionary unit has not reached the limit removing of a patch may not be performed. If the inventory size of the patch dictionary unit has reached the limit in step S a patch having the lowest score from among patches stored in the patch dictionary unit is removed.

Referring to in step S an event indicating adding of a patch is detected. For example as described with reference to step S of the operating method of may be performed after execution of an operation where a first patch P newly searched for is added to a patch dictionary unit .

In step S whether the number of non index patches is larger than a threshold value is determined. If the number of non index patches is not larger than the threshold value the method may be ended. If the number of non index patches is larger than the threshold value steps S and S are performed.

In step S an index of a patch is removed from the patch dictionary unit . In step S an index is rebuilt.

In exemplary embodiments rebuilding of indexes may be executed whenever the number of patches added to the patch dictionary unit reaches a threshold value. At rebuilding of indexes indexes of deleted patches may be deleted. Exhaustive search may be executed with respect to patches not having indexes.

In there is described an example in which rebuilding of indexes is executed whenever the number of patches added to the patch dictionary unit reaches a threshold value. However the inventive concept is not limited thereto. For example the rebuilding of indexes may be executed periodically. The rebuilding of indexes may be executed whenever frame based search is ended or whenever a search operation performed by a line unit of a frame or by a unit of two or more lines of the frame is ended.

In exemplary embodiments the rebuilding of indexes may be executed when the patch dictionary unit an image processor or a processor is at an idle state.

Referring to in step S an event indicating adding of a patch is detected. For example as described with reference to step S of the operating method of may be performed after execution of an operation where a first patch P newly searched for is added to a patch dictionary unit .

In step S the index of a relevant patch is detected. For example the index of a patch similar to an added patch from among patches stored in a patch dictionary unit may be detected.

In step S the detected local index structure is rebuilt to include an index of the added patch. For example an index structure of a sub tree belonging to subordination to the detected patch may be rebuilt. For example a local index structure may be rebuilt such that an index of the added patch is included in a sub tree of the detected patch.

Likewise when a specific patch is deleted from the patch dictionary unit a local index structure associated with the deleted patch may be detected and the detected local index structure may be rebuilt.

The patch refinement unit may be configured to execute refinement based on a plurality of patches. For example the patch refinement unit may be configured to restore high frequency components of two or more patches through alignment of two or more similar patches. The alignment may be executed with a sub pixel resolution. An example of a patch refining method is disclosed in a paper published by Michal Irani and Shmuel Peleg June 1990 entitled SUPER RESOLUTION FROM IMAGE SEQUENCES www.cs.huji.ac.i1 peleg papers icpr90 SuperResolutionSequences.pdf the contents of which are incorporated by reference.

Patches of the same scale as a magnified patch may be searched for in the patch dictionary unit and in a magnified frame. The patch refinement unit may execute a refinement using the searched for patches and the magnified patch. The dictionary management unit may update the patch dictionary unit based on the result of the refinement. For example if patches are not searched for in the patch dictionary unit the dictionary management unit may update the patch dictionary unit with the searched for patches from the magnified frame.

In step S a magnified patch in the magnified frame is selected. This may be executed by an upscale unit .

In step S at least one first patch is searched for in a relevant area of the magnified frame. This may be executed by the upscale unit .

In step S a second patch may be searched for in a patch dictionary unit . In exemplary embodiments the upscale unit may search the patch dictionary unit based on a selected patch. A search step of the patch dictionary unit may be executed based on a descriptor as described with reference to .

A method of executing steps S and S is illustrated in . Referring to two first patches P may be searched for in a relevant area of a magnified frame MF. For example first patches P similar to a magnified patch MP or having a difference from the magnified patch MP less than a reference value may be searched for in the relevant area RA. A predetermined number of first patches P most similar to the magnified patch MP or having the smallest difference from the magnified patch MP may be searched for in the relevant area RA. The number of first patches P searched for in the relevant area RA may not be limited.

A second patch P may be searched for in a patch dictionary unit . For example a second patch P most similar to the magnified patch MP or having the smallest difference may be searched for in the patch dictionary unit . A second patch P having the difference from the magnified patch MP less than a reference value may be searched for in the patch dictionary unit .

Referring to in step S refinement may be executed using the searched for patches. For example the refinement may be executed by aligning the first patches P searched for in the relevant area RA and the second patch P searched for in the patch dictionary unit . A patch refinement unit may receive the magnified patch MP from the upscale unit and the first and second patches P and P to execute refinement.

In exemplary embodiments in the case that a second patch P is not searched for in the patch dictionary unit and at least one first patch P is searched for in the relevant area RA the refinement unit may execute refinement based on the magnified patch MP and the at least one first patch P. In the case that a second patch P is searched for in the patch dictionary unit and at least one first patch P is not searched for in the relevant area RA the refinement unit may execute refinement based on the magnified patch MP and the second patch P. In the case that a second patch P is not searched for in the patch dictionary unit and at least one first patch P is not searched for in the relevant area RA the refinement unit may not execute refinement.

In step S the magnified patch MP is replaced with a refined patch. The upscale unit replaces the magnified patch MP with the refined patch. In exemplary embodiments if the magnified patch MP is not refined it may be maintained.

If the method in is performed with respect to all patches of a magnified frame MP high frequency components of the magnified frame MF may be restored.

In step S whether at least one first patch P is searched for is determined. If at least one first patch P is searched for in the relevant area RA of a magnified frame MF refinement may be executed based on a magnified patch MP and the at least one first patch P. Since the second patch P is not searched for in the patch dictionary unit the refined patch may be a patch which is not similar to patches stored in the patch dictionary unit . The refined patch may be a patch having the difference from patches stored in the patch dictionary unit larger than a reference value. In step S the refined patch may be added to the patch dictionary unit . The refined patch may be added with an initial score. The initial score may be decided according to the difference or similarity between the refined patch and patches stored in the patch dictionary unit .

If at least one first patch P is not searched for a patch similar to the magnified patch MP may not exist at the patch dictionary unit and the relevant area RA. In step S a dictionary management unit may add the magnified patch MP to the patch dictionary unit . The magnified patch MP may be stored with a second initial score. A value of the second initial score may be smaller than that of the initial score set forth at step S. In exemplary embodiments the second score may be set such that the magnified patch MP is maintained at the patch dictionary unit while a search operation is executed by a frame unit a line unit of a frame or a unit of predetermined lines of a frame.

In exemplary embodiments patches stored in the patch dictionary unit may be removed according to the method described with reference to so as to be initialized. The patch dictionary unit may include baseline patches.

In the pointer based management manner patches may be managed according to a pointer to specific location a pointer to frame and a frame.

A frame may be a copy of a magnified frame MF. The patch dictionary unit may store a frame. A pointer to frame may indicate that a patch belongs to any frame. The pointer to specific location may indicate that a patch corresponds to any location of a frame designated by the pointer of frame.

In exemplary embodiments in the case that the number of patches stored in the patch dictionary unit is less most magnified patches of the magnified frame MF may not be refined. Magnified patches not refined may be stored in the patch dictionary unit . Thus most patches of the magnified frame MF may be added to the patch dictionary unit . At this time in the case that the pointer based management is used patches may be simply expressed using one magnified frame MF and pointers according to the magnified frame MF. In the case that the number of patches stored in the patch dictionary unit is less the pointer based management may be used such that the magnified frame MF is stored in the patch dictionary unit .

In the contents based management manner contents may be stored and managed at the patch dictionary unit . In exemplary embodiments descriptors and high frequency components of patches may be stored in the patch dictionary unit . In the case that the number of patches stored in the patch dictionary unit is many most magnified patches of the magnified frame MF may be refined. Magnified patches may be independently refined based on the first patch P of the relevant area RA and the second patch P of the patch dictionary unit . A refined patch may be replaced with the second patch P of the patch dictionary unit . Patches independently refined and updated may be managed based on pointers to frame. In the case that the number of patches stored in the patch dictionary unit is many the contents based management manner may be used to manage patches independently.

In step S whether the number of matched patches is larger than a threshold value is determined. For example the number of specific patches of magnified patches of the upscaled frame may be counted. Each of the specific patches may have a second patch searched for in a patch dictionary unit or at least one first patch P searched for in a relevant area RA. Whether the counted value is larger than the threshold value may be determined.

If the number of matched patches is not larger than the threshold value in step S pointer based management is selected. An input frame LRF may be stored in a patch dictionary unit and magnified patches may be stored in the patch dictionary unit with a pointer. In this case refined patches may be managed according to contents based management.

If the number of matched patches is larger than the threshold value in step S the contents based management is selected. Both the refined patches and unrefined patches may be stored in the patch dictionary unit with contents.

In exemplary embodiments selection of steps S and S may be applied to a search step of a next frame or a next line. The selection of steps S and S may be applied to a search step of a next frame or a next line not applied to a current search operation.

In exemplary embodiments if a patch managed according to the pointer based management manner is refined and updated it may be managed according to a contents based management manner.

In exemplary embodiments if the number of patches of a specific frame managed according to the pointer based management manner decreases below a reference value a management manner of the patches may be switched into the contents based management manner.

The downscale unit receives an output frame HRF of the upscale unit for example a previous output frame. The downscale unit downscale the output frame HRF to have a resolution of the input frame LRF. Downscale may be executed according to one of various methods such as bilinear downscale having an anti aliasing characteristic.

The motion estimation unit receives the input frame LRF for example a current input frame and the downscaled frame from the downscale unit . The motion estimation unit estimates a motion by comparing the input frame LRF and the downscaled frame. The motion estimation unit generates a motion field according an estimation result.

The motion compensation unit can generate a partial frame upscaled HRF P by copying patches of the output frame HRF based on the motion field generated by the motion estimation unit . The upscaled partial frame HRF P may have gaps or holes that are not processed by copying of patches based on the motion field.

The upscale unit may receive the partial upscaled frame HRF P from the motion compensation unit . The upscale unit may reinforce high frequency components of gaps or holes of the partial upscaled frame HRF P referring to the patch dictionary unit . In exemplary embodiments the upscale unit may reinforce high frequency components of gaps or holes according to a method described with reference to . The dictionary management unit may manage the patch dictionary unit according to a method described with reference to .

In various exemplary embodiments the downscale unit may be omitted. In this case the motion estimation unit may compare a previous input frame and a current input frame to generate a motion map. The motion compensation unit may generate the partial upscaled frame HRF P based on the motion map.

The upscale unit may modify patches of gaps or holes of the partial upscaled frame HRF P. The dictionary management unit may update the patch dictionary unit according to patches related with the gaps or holes.

In step S a motion may be detected based on a current input frame LRF and a previous output frame HRF and a motion field may be generated.

In step S a partial upscaled frame HRF P is generated by copying patches of the previous output frame HRF.

In step S searching and reinforcing of high frequency components on gaps or holes of the partial upscaled frame HRF P and a current output frame HRF are generated.

In exemplary embodiments when a patch corresponding to a gap or a hole is not searched for in a patch dictionary unit reinforcement on the gap or hole may be made according to in painting.

In the image processor as described with reference to a partial upscaled frame HRF P may be generated.

Refinement on the partial upscaled frame HRF P may be executed referring to the patch dictionary unit as described with reference to .

The upscale unit modifies patches of gaps or holes of the partial upscaled frame HRF P using the patch refinement unit . The dictionary management unit updates the patch dictionary unit according to patches related with the refinement.

In step S a motion may be detected based on a current input frame LRF and a previous output frame HRF and a corresponding motion field is generated.

In step S a partial upscaled frame HRF P is generated by copying patches of the previous output frame HRF.

In step S refinement on the partial upscaled frame HRF P may be performed referring to a patch dictionary unit and a current output frame HRF may be generated. The whole of the partial upscaled frame HRF P may be refined.

In step S a motion may be detected based on a current input frame LRF and a previous output frame HRF and a motion field may be generated.

In step S a partial upscaled frame HRF P is generated by copying patches of the previous output frame HRF.

In step S refinement on gaps or holes of the partial upscaled frame HRF P is performed and a current output frame HRF is generated.

Steps S to S may be repeated after steps S to S are performed. Thus predetermined frames may be accumulated and refined. Motion estimation and motion compensation on the refined and accumulated frames may not be performed.

If accumulation and refinement are completed motion estimation and motion compensation may be executed from a next frame. At this time refinement may be additionally executed only with respect to holes or gaps of the partial upscaled frame HRF P. Additional refinement may not be executed with respect to accumulated and refined frames. If refinement is executed only with respect to holes or gaps coherency between a previous frame and a current frame may be maintained.

As described above with embodiments of the inventive concept upscale on a low resolution input frame may be executed based on self similarity and a patch dictionary unit . As upscale on frames is executed the patch dictionary unit may be reinforced. Thus upscale accuracy may be improved and a noise may be reduced. A dictionary management unit may manage the patch dictionary unit such that the consumption of the capacity of the patch dictionary unit does not increase excessively. Thus although upscale is continuously executed a resource taken by the patch dictionary unit may be maintained within a predetermined range.

The patch dictionary unit may be updated according to a process of a continuous video stream in an on line manner or an on the fly manner. The patch dictionary unit may utilize coherency between frames by updating patches based on frames of a continuous video stream. As coherency between frames by updating patches is utilized the quality of upscale may be maintained highly. Also it is possible to maintain the capacity of the patch dictionary unit to be suitable for a low resource device such as a mobile device.

In exemplary embodiments when an image processor starts to upscale frames the patch dictionary unit may not store patches or may store baseline patches. At this time reinforcement on a high frequency component of an output frame HRF may not be sufficiently executed. Also a noise of the output frame HRF may not be sufficiently removed.

When frames are acquired using a capture device such as a camera a pre step such as view finding may be performed. Also when input frames are displayed a pre step such as framing may be performed. During the pre operation learning of the patch dictionary unit may be made. Thus during the pre operation patches may be added to the patch dictionary unit . Frames displayed after the pre operation may be processed by the patch dictionary unit reinforced. Thus reinforcement on an output frame HRF and removing of a noise can be sufficiently executed.

In exemplary embodiments an input frame LRF may include a contents rich area and a contents less area. The contents rich area may be processed based on self similarity and the patch dictionary unit according to embodiments of the inventive concept while the contents less area may be upscaled using a simple algorithm such as bilinear or bicubic. For example in a magnified frame MF the contents less area may be ignored and high frequency components of the contents rich area may be reinforced.

In exemplary embodiments the patch size may be decided to optimize an operating performance of the image processor . For example the patch size on specific frames may be changed and upscale may be executed. A patch size having the highest operating performance may be selected according to an upscale result.

In the above described embodiments various threshold values reference values or predetermined values may be mentioned. The threshold values reference values or predetermined values may be values which are decided according to algorithms and a design rule applied to the image processor or constituent elements of the image processor .

Embodiments of the inventive concept may be applied to various devices which capture frames to store or display the captured frames. For example embodiments of the inventive concept may be applied to devices such as a camera a smart phone a smart pad a smart camera and so on. In particular embodiments of the inventive concept may be applied to devices which display high resolution frames using a low resolution camera and support an optical zoom.

Embodiments of the inventive concept may be applied to devices which receive and display frames. For example embodiments of the inventive concept may be applied to devices such as a smart phone a smart pad a smart camera a notebook computer a desktop computer a smart television and so on. In particular the embodiments of the inventive concept may be applied to devices which receive low resolution frames to display high resolution frames.

With embodiments of the inventive concept upscale on an input image may be executed referring to patches stored in a patch dictionary unit. Patches stored in the patch dictionary unit may be updated according an upscale result. Thus it is possible to acquire high quality images from low quality images with the improved reliability and accuracy.

While the inventive concept has been described with reference to exemplary embodiments it will be apparent to those skilled in the art that various changes and modifications may be made without departing from the spirit and scope of the inventive concept. Therefore it should be understood that the above embodiments are not limiting but illustrative.

