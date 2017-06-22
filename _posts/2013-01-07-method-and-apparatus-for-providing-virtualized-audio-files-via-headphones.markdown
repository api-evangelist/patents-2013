---

title: Method and apparatus for providing virtualized audio files via headphones
abstract: Embodiments of the subject invention relate to a method and apparatus for providing virtualized audio files. Specific embodiments relate to a method and apparatus for providing virtualized audio files to a user via in-ear speakers or headphones. A specified embodiment can provide Surround Sound virtualization with DTS Surround Sensations software. Embodiments can utilize the 2-channel audio transmitted to the headphones. In order to accommodate for the user moving the headphones in one or more directions, and/or rotating the headphones, while still allowing the user to perceive the origin of the audio remains is a fixed location, heading data regarding the position of the headphones, the angular direction of the headphones, the movement of the headphones, and/or the rotation of the headphones can be returned from the headphones to a PC or other processing device. Additional processing of the audio files can be performed utilizing all or a portion of the received data to take into account the movement of the headphones.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09363602&OS=09363602&RS=09363602
owner: BIT CAULDRON CORPORATION
number: 09363602
owner_city: Gainesville
owner_country: US
publication_date: 20130107
---
The present application claims the benefit of U.S. Provisional Application Ser. No. 61 584 055 filed Jan. 6 2012 which is hereby incorporated by reference herein in its entirety including any figures tables or drawings.

Music is typically recorded for presentation in a concert hall with the speakers away from the listeners and the artists. Many people now listen to music with in ear speakers or headphones. The music recorded for presentation in a concert hall when presented to users via in ear speakers or headphones often sounds like the music originates inside the user s head.

Providing virtualized audio files to a headphone user can allow the user to experience the localization of certain sounds such as 3D sound over a pair of headphones. Such virtualization can be based on head related transfer function HRTF technology or other audio processing that results in the user perceiving sounds originating from two or more locations in space and preferably from a wide range of positions in space.

Embodiments of the subject invention relate to a method and apparatus for providing virtualized audio files. Specific embodiments relate to a method and apparatus for providing virtualized audio files to a user via in ear speakers or headphones. A specified embodiment can provide Surround Sound virtualization with DTS Surround Sensations software. Embodiments can utilize the 2 channel audio transmitted to the headphones. In order to accommodate for the user moving the headphones in one or more directions and or rotating the headphones while still allowing the user to perceive the origin of the audio remains is a fixed location heading data regarding the position of the headphones the angular direction of the headphones the movement of the headphones and or the rotation of the headphones can be returned from the headphones to a PC or other processing device. Additional processing of the audio files can be performed utilizing all or a portion of the received data to take into account the movement of the headphones.

Embodiments of the subject invention relate to a method and apparatus for providing virtualized audio files. Specific embodiments relate to a method and apparatus for providing virtualized audio files to a user via in ear speakers or headphones. A specified embodiment can provide Surround Sound virtualization with DTS Surround Sensations software. Embodiments can utilize the 2 channel audio transmitted to the headphones. In order to accommodate for the user moving the headphones in one or more directions and or rotating the headphones while still allowing the user to perceive the origin of the audio remains is a fixed location heading data regarding the position of the headphones the angular direction of the headphones the movement of the headphones and or the rotation of the headphones can be returned from the headphones to a PC or other processing device. Additional processing of the audio files can be performed utilizing all or a portion of the received data to take into account the movement of the headphones.

In specific embodiments the data relating to movement and or rotation of the headphones which can be provided by for example one or more accelerometers provides data that can be used to calculate the position and or angular direction of the headphones. As an example an initial position and heading of the headphones can be inputted along with acceleration data for the headphones and then the new position can be calculated by double integrating the acceleration data to recalculate the position. However errors in such calculations meaning differences between the actual position and the calculated position of the headphones and differences between the actual angular direction and the calculated angular direction can grow due to the nature of the calculations e.g. double integration. The growing errors in the calculations can result in the calculated position and or angular direction of the headphones being quite inaccurate. In specific embodiments data relating to the position and or heading direction for example position and or angular direction of the headphones can be used to recalibrate the calculated position and or angular direction of the headphones for the purposes of continuing to predict the position and or angular direction of the headphones. Such recalibration can occur at irregular intervals or at regular intervals where the intervals can depend on for example the magnitude of the measured acceleration and or the duration and or type of accelerations. In an embodiment recalibration of the position and or the angular direction can be accomplished at least every 0.1 sec at least every 0.01 sec at least every 0.005 sec at least every 0.004 sec at least every 0.003 sec at least every 0.002 sec and or at least every 0.001 sec or at some other desired regular or variable interval. For this purpose absolute heading data can be sent from the headphones or other device with a known orientation with respect to the headphones to a portion of the system that relays the heading data to the portion of the system processing the audio signals. Such angular direction data can include for example an angle a known axis of the headphones makes with respect to a reference angle in a first plane e.g. a horizontal plane and or an angle the known axis of the headphone makes with respect to a second plane e.g. a vertical plane .

The headphones can receive the virtualized audio files via a cable or wirelessly e.g. via RF or Bluetooth.

An embodiment can use a printed circuit board PCB to incorporate circuitry for measuring acceleration in one or more directions position data and or heading angular direction data into the headphones with the following interfaces PCB fits inside wireless Bluetooth headphones use existing audio drivers and add additional processing mod wire out to existing connectors use existing battery add heading sensors. In an embodiment the circuitry incorporated with the headphones can receive the virtualized audio files providing a 3D effect based on a reference position of the headphones and the circuitry incorporated with the headphones can apply further processing to transform the signals based on the position angular direction and or past acceleration of the headphones. Alternative embodiments can apply the transforming processing in circuitry not incorporated in the headphones.

In a specific embodiment a Bluetooth Button and a Volume Up Down Button can be used to implement the functions described in the table below 

An embodiment can incorporate equalization such as via a 5 Band equalization for example applied upstream in the player.

Preferably embodiments use the same power circuit provided with the headphones. The power output can also preferably be about as much as an iPod such as consistent with the description of iPod power output provided in various references such as Y. Kuo et al. Hijacking Power and Bandwidth from the Mobile Phone s Audio Interface Electrical Engineering and Computer Science Department University of Michigan Ann Arbor Mich. 48109 .

Embodiments can use as the source a PC performing the encoding and a headphone performing the decoding. The PC based encoder can be added between a sample source and the emitter.

Heading information can be deduced from one or more accelerometers and a digital compass on the headphones and this information can then be available to the source.

A reference point and or direction can be used to provide one or more references for the 3D effect with respect to the headphones. For example the front of the sound stage can be used and can be determined by for example one or more of the following techniques 

Various embodiments can incorporate a heading sensor. In a specific embodiment the headphones can have a digital compass accelerometer and tilt sensor. From the tilt sensor and accelerometer the rotation of the viewers forward facing direction through the plane of the horizon should be determined. In a specific embodiment the tilt sensor data can be combined with the accelerometer sensor data to determine which components of each piece of rotation data are along the horizon.

This rotation data can then be provided to the source. The acceleration data provides high frequency information as to the heading of the listener headphones . The digital compass es in the headphones and the heading sensor provide low frequency data preferably a fixed reference of the absolute angle of rotation in the plane of the horizon of the listener on the sound stage e.g. with respect to front . This data can be referenced as degrees left or right of parallel to the heading sensor from 180 to 180 degrees as shown in the table below.

Which data is fused in the PC and which data is fused in the headphones can vary depending on the implementation goals. After the data is combined the data can be made available via for example an application programming interface API to the virtualizer. Access to the output of the API can then be provided to the source which can use the output from the API to get heading data as frequently as desired such as every audio block or some other rate. The API is preferably non blocking so that data is available for example every millisecond if needed.

The method according to embodiment 1 wherein capturing information comprises capturing information regarding the position and the angular direction of the transducer apparatus.

The method according to embodiment 2 wherein capturing information comprises capturing information regarding movement acceleration and rotational acceleration of the transducer apparatus.

The method according to embodiment 3 wherein processing the virtualized audio file based on the captured information comprises 

The method according to embodiment 4 wherein the new position is calculated via double integrating the acceleration information.

The method according to embodiment 5 wherein the new angular direction is calculated via double integrating the acceleration information wherein the acceleration data comprises angular acceleration data.

The method according to embodiment 9 wherein the measured angular direction is a measured angular direction of a device with a known orientation with respect to the transducer apparatus.

The method according to embodiment 9 where recalibrating the new position and the new angular direction is accomplished at least every 0.01 sec.

The method according to embodiment 9 where recalibrating the new position and the new angular direction is accomplished at least every 0.005 sec.

The method according to embodiment 9 where recalibrating the new position and the new angular direction is accomplished at least every 0.001 sec.

The method according to embodiment 9 wherein the measured angular direction is measured via a digital compass.

The method according to embodiment 8 wherein the measured angular direction comprises a first angle with respect to a first reference angle in a horizontal plane.

The method according to embodiment 13 wherein the measured angular direction comprises a second angle with respect to a second reference angle in a vertical plane.

The method according to embodiment 13 wherein the measured angular direction is measured via a heading sensor.

The method according to embodiment 8 wherein the measured angular direction is measured via a tilt sensor and at least one accelerometer.

The method according to embodiment 8 wherein the measured angular direction is provided in a number of degrees with respect to a fixed reference heading in a horizontal plane.

Aspects of the invention such as receiving heading position and or acceleration data processing audio files in conjunction with such received data and presenting sounds via headphones based on such processed audio files may be described in the general context of computer executable instructions such as program modules being executed by a computer. Generally program modules include routines programs objects components data structures etc. that perform particular tasks or implement particular abstract data types. Moreover those skilled in the art will appreciate that the invention may be practiced with a variety of computer system configurations including multiprocessor systems microprocessor based or programmable consumer electronics minicomputers mainframe computers and the like. Any number of computer systems and computer networks are acceptable for use with the present invention.

Specific hardware devices programming languages components processes protocols and numerous details including operating environments and the like are set forth to provide a thorough understanding of the present invention. In other instances structures devices and processes are shown in block diagram form rather than in detail to avoid obscuring the present invention. But an ordinary skilled artisan would understand that the present invention may be practiced without these specific details. Computer systems servers work stations and other machines may be connected to one another across a communication medium including for example a network or networks.

As one skilled in the art will appreciate embodiments of the present invention may be embodied as among other things a method system or computer program product. Accordingly the embodiments may take the form of a hardware embodiment a software embodiment or an embodiment combining software and hardware. In an embodiment the present invention takes the form of a computer program product that includes computer useable instructions embodied on one or more computer readable media.

Computer readable media include both volatile and nonvolatile media transient and non transient media removable and nonremovable media and contemplate media readable by a database a switch and various other network devices. By way of example and not limitation computer readable media comprise media implemented in any method or technology for storing information. Examples of stored information include computer useable instructions data structures program modules and other data representations. Media examples include but are not limited to information delivery media RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile discs DVD holographic media or other optical disc storage magnetic cassettes magnetic tape magnetic disk storage and other magnetic storage devices. These technologies can store data momentarily temporarily or permanently.

The invention may be practiced in distributed computing environments where tasks are performed by remote processing devices that are linked through a communications network. In a distributed computing environment program modules may be located in both local and remote computer storage media including memory storage devices. The computer useable instructions form an interface to allow a computer to react according to a source of input. The instructions cooperate with other code segments to initiate a variety of tasks in response to data received in conjunction with the source of the received data.

The present invention may be practiced in a network environment such as a communications network. Such networks are widely used to connect various types of network elements such as routers servers gateways and so forth. Further the invention may be practiced in a multi network environment having various connected public and or private networks.

Communication between network elements may be wireless or wireline wired . As will be appreciated by those skilled in the art communication networks may take several different forms and may use several different communication protocols. And the present invention is not limited by the forms and communication protocols described herein.

All patents patent applications provisional applications and publications referred to or cited herein are incorporated by reference in their entirety including all figures and tables to the extent they are not inconsistent with the explicit teachings of this specification.

It should be understood that the examples and embodiments described herein are for illustrative purposes only and that various modifications or changes in light thereof will be suggested to persons skilled in the art and are to be included within the spirit and purview of this application.

