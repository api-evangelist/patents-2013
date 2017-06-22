---

title: Method for stimulating living body more accurately and apparatus using the same
abstract: Disclosed is a method of more accurately stimulating a living body and an apparatus using the method. The method includes determining targeted bio-information, deriving bio-stimulation information required to achieve the targeted bio-information using complicated time space data indicative of bio-responses interacting at a plurality of different positions in response to bio-stimulation composed of pieces of time-series data having a specific frequency, and applying a stimulation signal to the living body in response to the derived bio-stimulation information. The method is advantageous in that it can derive a systematic algorithm between bio-related information and stimulation information so that more accurate and safely stimulation is made upon applying bio-stimulation based on acquired bio-related information, can minimize a process of trial and error using a systematic algorithm, and can more accurately stimulate a living body by exactly determining a specific target stimulation position.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09265943&OS=09265943&RS=09265943
owner: YBRAIN INC.
number: 09265943
owner_city: 
owner_country: KR
publication_date: 20130913
---
The present invention relates in general to a method of more accurately stimulating a living body and an apparatus using the method and more particularly to a method that is capable of more accurately stimulating a living body by deriving a systematic algorithm between bio related measurement information and stimulation information and to an apparatus using the method.

Methods of stimulating a specific portion of a brain are mainly classified into invasive stimulation methods and non invasive stimulation methods.

Generally such an invasive stimulation method is a method of exactly installing an electrode at a specific target position via surgery applying an electrical signal to the electrode and then directly stimulating a specific portion of the brain.

The invasive stimulation method is an accurate and effective stimulation method but has a limitation in that a danger caused by brain surgery may be present and thus this method is limitedly used only in the case of very serious brain diseases such as Parkinson s disease.

A non invasive stimulation method is a method of attaching an electrode to a specific position of the scalp applying electrical and magnetic signals to the electrode and stimulating a specific portion of the brain.

Such a non invasive stimulation method is limited in that it is difficult to exactly stimulate the specific portion of the brain thus requiring a process of trial and error.

Therefore the non invasive stimulation method must include the step of stimulating a specific position of the scalp for a predetermined period of time the step of determining whether the specific position that is targeted is actually stimulated by using a brain signal measurement device such as Electroencephalography EEG equipment or a functional Magnetic Resonance Imaging fMRI scanner and the step of if it is determined that the specific position has not been stimulated changing the position of the electrode stimulating a new specific position of the scalp and determining whether the new position is actually stimulated by the repositioned electrode.

That is the non invasive stimulation method is problematic in that it requires a process of trial and error thus repeatedly stimulating inaccurate positions.

In particular when such inaccurate positions are repeatedly stimulated the non invasive stimulation method may not obtain targeted effects or may obtain effects lower than the targeted effects and may cause a problem in safety because a stimulation time is lengthened.

Such conventional cranial nerve stimulation technology includes U.S. Pat. No. 7 460 903 entitled Method and system for a real time adaptive system for effecting changes in cognitive emotive profiles .

Such a conventional cranial nerve stimulation technology includes the step of acquiring various bioelectric signals required to determine a current psychological state the step of comparing the current psychological state so as to extract a multi dimensional cognitive emotive profile based on the bioelectric signals mapping the cognitive emotive profile onto a set of commands the step of delivering brain stimulation commands to drive therapeutic and non therapeutic stimulus intervention and the step of applying a prolonged change to the cognitive emotive profile.

However such conventional cranial nerve stimulation technology is problematic in that it is implemented using a method in which acquired information matches a command set in which output information corresponding to input information is preset thus requiring the above described process of trial and error so as to create the preset command set.

Further since the command set used in this way is either created depending on experience rules or created using the mechanism of bio related information that is academically identified there is a limitation in that the command set is dependent on incomplete experience rules or limited biological mechanisms thus causing restrictions in precision and accuracy.

Accordingly the present invention has been made keeping in mind the above problems occurring in the prior art and an object of the present invention is to provide a method of deriving a systematic algorithm between bio related information and stimulation information which can make more accurate and safely stimulation upon applying bio stimulation based on acquired bio related information.

Another object of the present invention is to provide a method for stimulating a living body and an apparatus using the method which can minimize a process of trial and error using a systematic algorithm.

A further object of the present invention is to provide a method that is capable of more accurately stimulating a living body by exactly determining a specific target stimulation position using a systematic algorithm and an apparatus using the method.

In order to accomplish the above objects the present invention provides a method of more accurately stimulating a living body including determining targeted bio information deriving bio stimulation information required to achieve the targeted bio information using complicated time space data indicative of bio responses interacting at a plurality of different positions in response to bio stimulation composed of pieces of time series data having a specific frequency and applying a stimulation signal to the living body in response to the derived bio stimulation information.

Preferably information about bio responses to the bio stimulation may be a relation between the bio stimulation and the bio response information the relation being analyzed by performing applying the bio stimulation and acquiring information about a bio response to the applied bio stimulation.

Preferably the relation between the bio stimulation and the bio response information may be configured to set information about the bio stimulation as variables in an X matrix m t set the bio response information as variables in a Y matrix n t derive an A matrix n m satisfying Y AX and use the A matrix as the relation between the bio stimulation and the bio response information.

Preferably values in the A matrix may be determined to be mean values of values derived during respective repetitions.

Preferably values in the A matrix may be derived using a pseudo inverse method when a plurality of types of bio stimulation and information about a plurality of bio responses to the bio stimulation are acquired.

Further the present invention provides an apparatus for more accurately stimulating a living body including a stimulation unit for applying a bio stimulation signal in close vicinity to a living body and a control unit for deriving bio stimulation information required to achieve targeted bio information using information about a bio response to bio stimulation and controlling the stimulation unit so that the stimulation unit applies the bio stimulation signal in response to the derived bio stimulation information.

Preferably the apparatus may further include an environment sensor for acquiring surrounding environmental information of the living body and a measurement unit for acquiring bio related information in close vicinity to the living body wherein the control unit analyzes a relation between the surrounding environmental information of the living body acquired by the environment sensor and the bio related information acquired by the measurement unit and uses the relation to derive bio stimulation information required to achieve the targeted bio information.

The above and other objects features and advantages of the present invention will be more clearly understood from the following detailed description taken in conjunction with the accompanying drawings. However the present invention is not limited by the following embodiments and may be implemented in various forms. The present embodiments are configured to merely make the disclosure of the present invention complete and are provided to fully describe the scope of the present invention to those having ordinary knowledge in the art to which the present invention pertains and the present invention is merely defined by the scope of the accompanying claims. Meanwhile the terms used in the present specification are intended to describe embodiments and are not intended to limit the scope of the present invention.

The stimulation unit applies a bio stimulation signal capable of causing a bio response in close vicinity to the living body.

For example the stimulation unit may use electrical stimulation magnetic stimulation photic stimulation ultrasonic stimulation etc.

Electrical stimulation may be provided using a scheme for applying Direct Current DC stimulation pulse stimulation Alternating Current AC stimulation or random noise stimulation through an electrode installed in close vicinity to a living body. Magnetic stimulation may enable a magnetic stimulus to be applied using a coil for generating a magnetic field in close vicinity to a living body. Further photic stimulation may enable a stimulus to be applied by emitting infrared rays near infrared rays visible rays or laser light to a living body. Furthermore ultrasonic stimulation may enable a stimulus to be applied via an ultrasonic transducer or an ultrasound transceiver which creates an ultrasonic vibration when in contact with the living body.

Preferably the stimulation unit applies stimulation to the brain among portions of the living body and may use transcranial direct current stimulation tDCS transcranial alternating current stimulation tACS transcranial pulsed current stimulation tPCS etc.

Further preferably the stimulation unit may be configured to be included in a portable headset worn on the head and may be designed to easily apply stimulation to the brain among the portions of the living body.

The apparatus for more accurately stimulating the living body according to the embodiment of the present invention further includes a measurement unit for acquiring bio related information in close vicinity to the living body.

Preferably the measurement unit measures the activities of the brain using brain waves a brain evoked potential brain activity magnetoencephalogram ultrasonic waves etc.

For example the measurement unit may be implemented using an Electroencephalogram EEG sensor a near infrared spectrophotometer or near infrared spectroscopy NIRS magnetoencephalography MEG equipment an ultrasound transceiver or the like.

In an example the measurement unit is implemented as an electrode attached to the scalp and is capable of measuring the electrical activities of the brain and the brain wave measurement electrode may be implemented using a capacitive electrode which has conductivity but has a surface coated with a nonconductive material.

In another example the measurement unit is implemented as an electrode attached to the scalp and is capable of measuring the magnetic activities of the brain.

In a further example the measurement unit may measure a brain evoked potential. The brain evoked potential refers to the electrophysiological response of the brain to stimulation and any of sensible cognitive and motional stimuli may be applied as such stimulation.

As detailed examples the measurement unit may measure EEG from a body to which electrical magnetic photic or ultrasonic stimulation is applied and may determine the measured EEG to be the brain evoked potential.

In yet another example the measurement unit may acquire brain activity using a near infrared spectrophotometer or NIRS that exploits a light source for radiating light having a specific wavelength such as near infrared rays and a light receiving device photodetector for analyzing light absorption caused by the activities of the brain.

In this case the measurement unit may include a plurality of light sources and photodetectors so as to detect the activation of the brain depending on positions at the brain.

In still another example the measurement unit may be implemented using an ultrasonic coupler and an ultrasonic receiver or an ultrasound transceiver which is a combination thereof and may measure the structure of the brain and the activities of blood vessels.

Preferably the measurement unit may be configured to acquire bio information using a plurality of electrical magnetic photic or ultrasonic components. According to the configuration of the measurement unit the stimulation unit may be configured to apply bio stimulation using the plurality of electrical magnetic photic or ultrasonic components.

The control unit derives bio stimulation information required to achieve targeted bio information using information about a bio response to bio stimulation and controls the stimulation unit so that it applies a bio stimulation signal in response to the derived bio stimulation information.

In accordance with a preferred embodiment of the present invention the control unit repeatedly performs a procedure for applying bio stimulation and acquiring information about a bio response to the applied bio stimulation derives a relation between the bio stimulation and the bio response information and uses the relation as the information about the bio response to the bio stimulation.

In accordance with another preferred embodiment of the present invention the control unit sets information about bio stimulation as variables in an X matrix m t sets information about the bio response to the bio stimulation as variables in a Y matrix n t derives an A matrix n m satisfying Y AX and uses the derived A matrix as information about the bio response to the bio stimulation.

Preferably m may be the type of stimulation where identical stimulation at different positions may be regarded as separate stimuli n may be the type of bio information where identical bio information at different positions may be regarded as pieces of separate bio information and t may be the number of repetitions or the number of stimulation values and bio information values acquired for a predetermined period of time .

That is the control unit sets the targeted bio information as a Y matrix using the derived A matrix derives an X matrix satisfying Y AX and determines bio stimulation information corresponding to a required type or a required position according to the X matrix.

In accordance with the preferred embodiment of the present invention values in the A matrix are determined to be mean values of values derived during respective repetitions.

Preferably values in the A matrix are determined in such a way as to limit the type of stimulation for example a value is applied only to single stimulation and the remaining values are set to 0 acquire a base vector of the A matrix using the acquired bio information and determine the values in the A matrix to be mean values of values of base vectors obtained by repeating a base vector acquisition procedure.

In accordance with another embodiment of the present invention values in the A matrix may be obtained using a pseudo inverse method.

For example when a plurality of stimulation values and a plurality of bio information values are repeatedly acquired a pseudo inverse matrix may be configured and thereafter values in the A matrix may be obtained.

When there are a number of equations more than a number of unknown values a method using the pseudo inverse matrix is used to obtain a least squares solution and this method may be usefully applied to the present invention.

In the simplest example a method using a pseudo inverse matrix is used to obtain the least squares solution when the number of pieces of information about values to be obtained from a quadratic equation is greater than two pairs and then a solution cannot be obtained.

For example such a method is configured to if it is assumed that A matrix a b is obtained for X matrix

In an example of the method applied to the present invention the control unit changes variables in the X matrix as bio stimulation has changed and changes variables in the Y matrix as bio information which is the bio response to the bio stimulation has changed and then a plurality of equations Y AX are derived. In this case there may occur a case where the control unit cannot determine the solution of the A matrix to be a single solution due to measurement noise or the like. In this case the A matrix for minimizing error may be obtained using the pseudo inverse matrix.

The method using the pseudo inverse matrix is advantageous in that even when relations between stimulation values and bio information values are unclear due to noise or the like the A matrix for minimizing error may be derived.

More preferably the control unit may derive and use the A matrix by performing repetitive stimulation and measurement on a single living body via the stimulation unit and the measurement unit .

Further the control unit may derive bio stimulation information required to achieve targeted bio information based on the A matrix derived via stimulation and measurement performed on a plurality of living bodies.

Although in the above description for the convenience of description an object for deriving the A matrix is described as being the apparatus of the present invention to be claimed the A matrix is not necessarily calculated by the apparatus including both the measurement unit and the stimulation unit and a case where the A matrix obtained according to the above description is obtained from the outside of the apparatus and is then used may also be included in the scope of the present invention.

The apparatus for more accurately stimulating a living body according to another preferred embodiment of the present invention further includes an environment sensor for acquiring the surrounding environmental information of a living body.

In this case the control unit analyzes a relation between the surrounding environmental information of the living body acquired by the environment sensor and bio related information acquired by the measurement unit similarly to a manner in which the relation between the stimulation information and the bio response information is derived.

Preferably the surrounding environmental information of the living body acquired by the environment sensor may be used as variables in the X matrix upon deriving the A matrix.

Preferably the environment sensor is a device for measuring temperature humidity illuminance noise or the like in surrounding environment that may influence bio signals.

The apparatus for more accurately stimulating a living body according to a further embodiment of the present invention may be configured to transmit acquired information to a platform database DB via a communication terminal or its own communication unit.

The platform DB stores the bio response information the bio stimulation information and the A matrix which is a relation between the bio response information and the bio stimulation information as complicated space time data.

Preferably the platform DB stores the bio response information as frequency variation information over time using a wavelet transform.

Preferably the platform DB additionally stores analysis results derived using phase synchrony partial directed coherence PDC or granger causality analysis methods.

Further the platform DB preferably stores surrounding environmental noise and environmental information measured by a gyroscope and an accelerometer with the noise and the environmental information time locked to the bio response information the bio stimulation information and the A matrix which is the relation between the two types of information.

The platform DB may individually map such various types of information to a multi dimensional space and store the various types of information so that they may be classified for respective features.

The platform DB has big data storage characteristics and may have the form of a distributed DB with high update performance such as a Cassandra DB or the form of a distributed file system DFS with high processing throughput such as a Hadoop DB. Alternatively the platform DB may have both the two forms.

As described above with reference to the apparatus or the terminal has bio stimulation information and bio response information and transmits the information to the server through a signal processing unit.

Preferably the apparatus or the terminal transmits not only bio stimulation information and bio response information but also A matrix data signal processed metadata the location of the apparatus or the terminal personal information etc. using various communication methods.

The server transforms or processes the information received from the apparatus or the terminal into a data format that can be processed by the server by performing information processing on the received information based on a preset event action rule.

Preferably the DB includes a primary DB with a high update speed for example the above described distributed DB a detailed example a Cassandra DB and a secondary DB having high semantic information extraction performance for example the above described DFS a detailed example a Hadoop DB .

The secondary DB extracts semantic information from the stored DB according to a preset statistical or algorithmic scheme and stores or processes the extracted semantic information.

The server stores the transformed or processed data in the primary DB and stores some data which can be stored or deleted or which enables semantic information thereof to be processed according to the type and format of data in the secondary DB .

The server may extract data from the DB and provide the extracted data when the second user terminal requests data.

Preferably the server may be configured to permit only the access of the second user terminal the apparatus or the terminal which conforms to a program corresponding to a preset scheme for example Software Development Kit SDK or Application Programming Interface API with respect to respective attempts to access.

Referring to in the method for of more accurately stimulating a living body according to the embodiment of the present invention the stimulation apparatus performs the step S of acquiring an A matrix and the step S of determining targeted bio information.

The stimulation apparatus may first determine targeted bio information or may first acquire the A matrix. However the A matrix must be acquired before bio stimulation information is derived.

The step S of acquiring the A matrix may be configured such that the stimulation apparatus acquires the A matrix by repeating the application of stimulation and measurement of response information or derives the A matrix by acquiring information from the outside or acquires the A matrix by receiving a completed A matrix.

In accordance with a preferred embodiment of the present invention the stimulation apparatus may perform the step S of acquiring surrounding environmental information and the step S of acquiring bio related information under the condition of the acquired surrounding environmental information. These steps are required to perform the A matrix change step S of further advancing the A matrix wherein in this case the stimulation apparatus must perform the A matrix acquisition step S before the A matrix change step S is performed.

Thereafter since the stimulation apparatus acquires the targeted bio information and the A matrix as information it performs the step S of deriving bio stimulation information required to achieve targeted bio information based on the information and the step S of stimulating the living body based on the derived bio stimulation information.

Further the stimulation apparatus according to a predetermined embodiment of the present invention may perform the step S of transmitting the acquired information to the server and such information transmission may be performed at any step.

Referring to in the method of deriving an A matrix according to the embodiment of the present invention an analysis device for deriving an A matrix may sequentially perform the step S of stimulating a living body the step S of acquiring information about a bio response to such stimulation and the step S of deriving an A matrix which is a relation between the bio stimulation and the bio response.

Preferably the analysis device may further perform the step S of determining whether a predetermined number of pieces of information have been acquired so as to repeat the step S of stimulating the living body and the step S of acquiring bio response information until a predetermined number of pieces of information are accumulated.

As described above the present invention is advantageous in that it derives a systematic algorithm between bio related information and stimulation information which can make more accurate and safely stimulation upon applying bio stimulation based on acquired bio related information.

Further the present invention is advantageous in that it can minimize a process of trial and error using a systematic algorithm.

Furthermore the present invention is advantageous in that it can more accurately stimulate a living body by exactly determining a specific target stimulation position.

Although the preferred embodiments and applied embodiments of the present invention have been illustrated and described those skilled in the art will appreciate that the present invention is not limited by the above described specific embodiments and applied embodiments and various modifications are possible without departing from the scope and spirit of the invention as disclosed in the accompanying claims. These modifications should not be understood separately from the technical spirit or prospect of the present invention.

