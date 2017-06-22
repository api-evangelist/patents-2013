---

title: Universal serial bus (USB) thermal imaging camera kit
abstract: A system kit and a method for creating a thermal imaging camera by connecting an infrared radiation capturing device to an external platform are provided herein. The kit may include a front end module which may include an image capturing device comprising a micro bolometer detector; and a universal serial bus (USB) interface connected to the image capturing device. The kit may further include a backend module, comprising data sets which are specific to said micro bolometer detector and computer readable code which is executable by a computer processor located at a physical location other than the front end module, wherein said front end module is configured to obtain raw data from the micro bolometer detector and deliver it over the USB interface to said backend module, wherein said backend module code turns the raw data into thermal imagery and temperature readings.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09546910&OS=09546910&RS=09546910
owner: OPGAL OPTRONIC INDUSTRIES LTD.
number: 09546910
owner_city: Karmiel
owner_country: IL
publication_date: 20131212
---
This application is a National Phase Application of PCT International Application No. PCT IL2013 051026 International Filing Date Dec. 12 2013 entitled UNIVERSAL SERIAL BUS USB THERMAL IMAGING CAMERA KIT published on Aug. 7 2014 as International Patent Application Publication No. WO 2014 118768 claiming priority of U.S. Patent Application No. 61 757 754 filed Jan. 29 2013 both of which are incorporated herein by reference in their entireties.

The present invention relates to the field of thermal imaging cameras using microbolometer detectors and more particularly to a kit enabling using same on an off the shelf platform.

Prior to setting forth a short discussion of the related art it may be helpful to set forth definitions of certain terms that will be used hereinafter.

The term capturing device as used herein is defined as any hardware combination of optics and sensor that is configured to produce electrical signals representative of a scene in a pixel array format. Specifically a capturing device as discussed herein does not include any image processing capability implemented therein beyond converting the raw data a data format appropriate for conveying.

The term microbolometer detector as used herein relates to a detector which includes an array of pixels sealed in a vacuum package.

Infrared radiation with wavelengths typically between 7.5 14 m strikes the detector material heating it and thus changing its electrical resistance. This resistance change is measured and processed into temperatures which can be used to create an image. Unlike other types of infrared detecting equipment microbolometers do not require cooling

Many thermal imaging cameras make use of microbolometer detectors. Microbolometer detectors suffer from inherent technological issues which make them difficult to work with. When trying to transform the microbolometer readings into good image quality the raw data captured from the detector has to be corrected with corrections algorithms and correction data sets. Typical corrections are non uniformity correction NUC bad pixel replacement BPR and the like. These corrections are specific to each individual detector and need to be prepared in a special calibration environment as it requires special tooling and knowhow Oven Blackbody software and the like . More often corrections are required not only per specific detector but may also be needed for a specific combination of detector and lens.

Currently available thermal imaging cameras are comprised of a lens a detector and electronics. The electronic circuitry which is required for capturing and processing the raw IR data and turning it into a video signal is often called IR Engine or IR core. IR engines include a microbolometer detector which is mounted onto a PCB board integrated with additional appropriate circuitry needed for operating controlling powering and reading the detector. Since currently available detectors provide raw data using a parallel electrical interface either digital or analog the IR engine includes some computing platform such as FPGA ASIC DSP CPU and some form of memory in order to be able to perform the above mentioned corrections as well as other signal and image processing tasks. The fast development of global consumer electronics market brought the availability of strong processing power to the hands of millions of users. Such processors can well replace the processing functions of an IR Engine.

Another challenge for making thermal imaging available for consumers is the power requirements of a microbolometer based thermal imaging device. Due to its way of operation typical IR engine consume 0.6 W or above. Today s consumer electronics are often powered by low power batteries as for example mobile cellphones smartphones tablets etc. Adding thermal imaging capabilities to a mobile device as an add on is therefore a challenging task.

Embodiments of the present invention address the challenge of interfacing a power hungry micro bolometer infrared capturing front end FE device with an external platform by using the USB and specifically USB On The Go interface which provides a way to connect a thermal imaging device to a mobile device as long as the imaging device draws less than 500 mW.

According to one aspect a system for creating a thermal imaging camera by connecting an infrared radiation capturing device to an external platform is provided herein. The system may include a micro bolometer based capturing front end FE device and a universal serial bus USB interface connected to the FE wherein the USB interface is configured to deliver both data from the FE and power to the FE wherein the delivered data is only processed outside the system on an external platform connected to the USB interface. The external platform transforms the raw data into thermal imaging video and images by using specialty algorithms and a unique correction data set which is specific to the individual microbolometer detector in use.

These additional and or other aspects and or advantages of the present invention are set forth in the detailed description which follows possibly inferable from the detailed description and or learnable by practice of the present invention.

With specific reference now to the drawings in detail it is stressed that the particulars shown are by way of example and for purposes of illustrative discussion of the preferred embodiments of the present invention only and are presented in the cause of providing what is believed to be the most useful and readily understood description of the principles and conceptual aspects of the invention. In this regard no attempt is made to show structural details of the invention in more detail than is necessary for a fundamental understanding of the invention the description taken with the drawings making apparent to those skilled in the art how the several forms of the invention may be embodied in practice.

Before explaining at least one embodiment of the invention in detail it is to be understood that the invention is not limited in its application to the details of construction and the arrangement of the components set forth in the following description or illustrated in the drawings. The invention is applicable to other embodiments or of being practiced or carried out in various ways. Also it is to be understood that the phraseology and terminology employed herein is for the purpose of description and should not be regarded as limiting.

In operation front end module may be configured to obtain raw data from the micro bolometer detector and deliver it as USB serialized data over USB interface to backend module .

According to some embodiments of the present invention backend module is configured to process the raw data from the micro bolometer detector delivered in USB serialized format using the data sets and the computer readable code to yield processed data . According to some embodiments of the present invention the processed data comprise thermal imagery data. Processed data may be in the form of still or video imagery but can also relate to any parameters extracted from the raw data without generating first video or still images.

According to some embodiments computer readable code may include an API Application Programming Interface that will enable software developers to develop code for the external platform that will utilize processed data .

According to some embodiments of the present invention data sets may include correction datasets usable for correcting the raw data obtained from the microbolometer detector wherein the correction datasets is based on a production profile of said microbolometer detector. More specifically the production profile comprises data relating to at least one of bad pixels production deformations and pixel level variations of said microbolometer detector.

Processor may be further connected to transmitter receiver storage power supply and display . In operation backend module may utilize any of the aforementioned components as resources for processing the raw data obtained from the microbolometer detector. By doing so a user may enjoy the functionalities and computing power of the external platform with a very lean architecture of the aforementioned front end module and back end module .

According to some embodiments of the present invention front end module is further configured to receive a power supply from a power source via said USB interface .

According to some embodiments of the present invention the power source is located within a platform to which the processor is coupled. Alternatively the power source is located outside a platform to which the processor is coupled.

According to some embodiments of the present invention the backend module may further include a standard development kit SDK software module configured to enable adding processing and control operations applicable to the microbolometer detector. The invention embodied in the kit formation may be sold as USB thermal imaging KIT . Advantageously the USB micro bolometer thermal imaging kit will overcome the current difficulty of using thermal imaging by non technical users consumers software developers. The Kit will enable users of everyday consumer electronics to easily plug and play a thermal camera to their existing computing devices. It will also allow software application developers to easily develop advanced thermal imaging applications without the need to understand the complexities of an Infrared detector.

The kit will take advantage of the existing USB Universal Serial Bus standards and in particular the ability for two electrical devices e.g. a host computer and a camera to be connected thus enabling power feed and communication exchange between host and camera. The thermal kit Front End device consume very low power and is the only available IR that will require no external power feed other than the ones provided by the consumer device thru the standard USB connector USB standard calls for 

Unlike most currently available thermal cameras the front end will have no shutter mechanism Shutter is frequently used to allow periodic non uniformity correction NUC operations in the field . In order to simplify front end module thus reducing its power consumption almost all computational tasks may be carried out at the back end or by the external platform. The kit will eliminate the need for complicated preparations and correction as it include the required magnetic data software code documentation and software tools that will allow the user to easily install and operate the USB thermal imager.

Additional thermal Imaging Applications Apps and development tools SDK will also be available for sell.

Advantageously front end module is a very low power device which includes a micro bolometer thermal imaging detector. Front end module is a standalone USB device it is powered by a USB power feed and is providing raw video data via a standard USB serial interface. The front end will include the following functionality Since power is supplied by the BE thru the USB connection the front end will regulate prepare and feed the micro bolometer detector power supply needs to be very well regulated and clean of interferences in order to get good image quality .

The front end will provide clock and synchronization signals to the detector. Front end module will control the detector operation. Front end module will read temperature measurements and other parameters that are needed for optimal calculation by the BE. Front end will read the data from the detector. The data could be either digital or analog. In case the detector output is analog the front end will sample and convert the data to digital. Front end will packetize and serialize the data from the detector and any other information needed and will prepare the data into a format that is supported by the USB standard.

It is important to note that front end could be materialized either by mounting a standalone microbolometer on a PCB with some additional relevant circuitry or it could also be materialized by incorporating all the required functionality on a single Chip or single Package SoC System on Chip or SIP system in Package . It is possible to integrate USB serialization A2D conversion etc. inside the ROIC Read out Integrated Circuit of the detector thus achieving a one chip front end.

The external platform is an electrical device which has a computational capability and which has an operating environment that supports USB connectivity For example PC Tablet Laptop and SmartPhone . The device will provide power and will communicate with the front end thru a standard USB interface such as USB 2.0 and USB on the go OTG .

The device OS operating system will have the drivers and infrastructure to easily identify the front end when connected in a Plug and Play mode. The BE will have development environment that will enable software developers to develop imaging application that utilize the DSD data and the SDK which includes software Library elements .

In accordance with some embodiments USB interface may be of various forms e.g. a pig tail with a connector or a direct connector dongle it needs to comply with a Plug and Play USB standard mini USB Micro USB and the like. 

According to some embodiments a Dataset may be implemented by software executed on the processor of the external platform . A data package that include data which is specific to the particular front end device which includes information such as NUC Non Uniformity Correction data and BPR Bad Pixel Replacement data. Dataset may be generated during the manufacturing process of the front end device and is arranged as a data package so it could be read by the BE.

According to some embodiments a Software Kit may further be distributed with external platform a kit which includes appropriate software elements. The code of the Kit is to be used on the BE platform. It will handle the raw data acquisition from the USB IR detector and will apply the corrections using the Dataset . Specifically The Software kit may be configured to detect a one to one relationship between the Dataset and front end module . The detection may be achieved via a device specific ID e.g. Serial Number that is stored on a non volatile memory inside front end module and referenced by data sets .

In the above description an embodiment is an example or implementation of the invention. The various appearances of one embodiment an embodiment or some embodiments do not necessarily all refer to the same embodiments.

Although various features of the invention may be described in the context of a single embodiment the features may also be provided separately or in any suitable combination. Conversely although the invention may be described herein in the context of separate embodiments for clarity the invention may also be implemented in a single embodiment.

Embodiments of the invention may include features from different embodiments disclosed above and embodiments may incorporate elements from other embodiments disclosed above. The disclosure of elements of the invention in the context of a specific embodiment is not to be taken as limiting their used in the specific embodiment alone.

Furthermore it is to be understood that the invention can be carried out or practiced in various ways and that the invention can be implemented in embodiments other than the ones outlined in the description above.

The invention is not limited to those diagrams or to the corresponding descriptions. For example flow need not move through each illustrated box or state or in exactly the same order as illustrated and described.

Meanings of technical and scientific terms used herein are to be commonly understood as by one of ordinary skill in the art to which the invention belongs unless otherwise defined.

While the invention has been described with respect to a limited number of embodiments these should not be construed as limitations on the scope of the invention but rather as exemplifications of some of the preferred embodiments. Other possible variations modifications and applications are also within the scope of the invention.

