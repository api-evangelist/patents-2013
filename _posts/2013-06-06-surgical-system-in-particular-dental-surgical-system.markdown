---

title: Surgical system, in particular dental surgical system
abstract: Surgical system, in particular a dental system including a surgical instrument, in particular a dental instrument and a device for controlling the electronic instrument. The device for controlling the electronic instrument includes a first electronic module. The instrument includes a rotary motor for driving the tool and a second electronic module. The rotary motor of the instrument is electrically powered by the first electronic module of the control device through the first electrical conductors dedicated to supply the rotary motor. The instrument is powered and/or electrically controlled by the first electronic module of the control device only through the second electrical conductors distinct from the first electrical conductors. The system also includes a management module of the second electrical conductors for sending on the second electrical conductors a number of signals larger to a number of second electrical conductors.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09510916&OS=09510916&RS=09510916
owner: DASSYM SA
number: 09510916
owner_city: Hauterive
owner_country: CH
publication_date: 20130606
---
The present invention claims the priority of Swiss Patent Application CH20120000814 filed on Jun. 6 2012 and published under the number CH706607 the content of which is incorporated here by reference.

The present invention concerns a surgical system in particular a dental system comprising a dental or surgical instrument and a device for controlling the instrument.

Surgical systems in particular dental systems comprise an instrument having a hand part for example a counter angle which may be provided with a tool for example a milling cutter and a rotating motor that drives the tool. The hand part and the motor may be two separate pieces and interconnected by appropriate interfaces or may constitute a single piece. The instrument s controller device is often connected to the patient s chair and connected to the manual instrument by a flexible connection containing electric wires and tubes for passing air and water.

The rotary motors used in this type of hand held instruments are more and more motors without commutators and without brushes which have the advantage of being more robust and being capable of being sterilized completely. In order to avoid overheating of the instrument which can be rotated at high speeds for example up to 40 000 turns per minute or more three phase motors are preferable.

A rotary motor used in this type of hand held instruments generally consists of a magnetically rotor with two poles and a stator winding with three windings. In order to set the coils on a precise angular position of the rotor for rotation which extend from 0 t min it is possible to equip the rotary motor with sensors for example Hall effect sensors or magneto resistive sensors providing continuously rotor positions to the electronic control which is typically located at the exterior of the motor. Less precise solutions without sensors are also known.

In the medical field the allowable dimensions are very small and the bulky cables should be avoided. There is thus a need for new systems including hand tools providing mechanical and electronic miniaturization as well as an optimal reduction of the cables while preserving a maximum reliability.

The Document WO05037124 in the name of the Applicant discloses a surgical system including a dental system an embodiment of which is illustrated in . The illustrated system includes a manual instrument that includes a rotary motor M two Hall effect sensors H and H arranged to determine at least one operating parameter of the motor M and an electronic module .

The control device of the motor M comprises a first electronic module and a flexible connection comprising the electrical conductors L L L and C for electrically connecting the first electronic module with the second electronic module and thus the control device to the instrument. The second electronic module located inside the instrument processes output signals of the sensors H and H and transmits them to the controller device through the flexible connector.

The electrical conductor L is the conductive phase of the motor M. From the high frequency point of view this conductor corresponds to the neutral for example the phase I.

The electrical conductor L is the conductive phase of the motor M e.g. the phase II on which is transmitted the drive component of the motor M which is a low frequency signal and the power supply high frequency component of the embedded microprocessor .

The electrical conductor L is the conductor of the phase of the motor M for example the phase III on which the motor M drive component and the component of the data are transmitted from the microprocessor to the module .

The electrical conductor C is the power driver of an accessory such as an incandescent lamp or LED and the delivery driver of the information transmitted from the first electronic module to the microprocessor . The information destined to the embedded microprocessor in the instrument are encoded by frequency modulation on the electrical conductor C.

Communications between the first electronic module and the second electronic module are mainly done by high frequency modulation of the conductors C and L in particular of the phase III of the motor. This has several disadvantages it is in fact necessary to use lager volumes of magnetic elements such as the two transformers and respectively associated with L and C and a demodulator which rends the device expensive. The choice of the types of drivers of motor phases is accordingly limited by the fact that it should not interfere with high frequency signals. In addition the system is sensitive to disruptions in particular disruptions due to the existence of a common potential between four electrical conductors L L L and C. Finally the system has a high cost.

Moreover the use of the floating power supply comprising an expensive PWM driver in the first electronic module connected to the power supply and allowing powering both the second electronic module embedded in the manually actuated instrument and the motor M trough the conductor L and which is potentially associated with the phase I electrical conductor L of the motor M involves the use of a magnetic element in particular the transformer of lager volumes and therefore high cost.

U.S. Pat. No. 5 235 261 concerns a surgical system in particular a dental system comprising a rotating motor for driving an instrument tool. This instrument does not have an electronic module inside the motor second electronic module . This document does not describe an exchange of messages between a first and a second electronic module.

US2011266124 concerns a surgical system in particular a dental system comprising an electronic circuit second electronic module inside the motor consisting of a fixed hardware performing predefined functions. In other words this second electronic module does not include a microprocessor. These functions are notified to the electronic management first electronic module of the system through six conductors. Each of these conductors carries a single signal so that the number of signals six is equal to the number of conductors.

U.S. Pat. No. 5 538 423 relates to a method and a device for controlling operational parameters of a dental system comprising an instrument having a commutator motor. This motor does not include switchable three phases but only one variable voltage. The instrument does not have an electronic module inside the motor second electronic module .

EP0688539 Bien Air concerns a dental handheld part comprising an electric driving and powering module of a lamp and an electromagnetic motor with no commutator whose connector comprises four power supply wires i.e. three wires for the three motor coils and one wire for the lamp the connection of the lamp taking advantage of the negative power supply line of one of the wires or terminals . The lamp is thus connected to the power supply terminals of the motor which can create interference problems and or of electromagnetic compatibility EM .

EP1753360 Bien Air discloses a flexible pipe connecting a dental instrument and a power supply comprising an additional power line via a dual function connector conductive fluid and or electricity . The additional conductor is insulated from conductors for powering a lamp and the motor and can be used to transmit a single signal.

There is therefore a need for a surgical system especially dental system capable of solving at least one of the disadvantages of the prior art.

There is also a need for a surgical system especially a dental system which is less bulky and cheaper than the known solutions.

There is also a need for a surgical system especially a dental system which is more reliable and does not present problems of interference and or electromagnetic compatibility or EMC or having reduced interference problems compared to the known solutions.

An aim of the present invention is to provide a surgical system in particular a dental system that is exempts of at least one of the drawbacks of the known systems.

Another aim of the invention is to propose a surgical system that is less bulky and cheaper than known solutions

Another aim of the invention is to propose a surgical system in particular a dental system which does not present the problems of interference and or electromagnetic compatibility or does not presents reduced problems of interference and or electromagnetic compatibility compared to known solutions.

According to the invention these aims are achieved in particular by means of a surgical system in particular a dental system having 

The motor of the instrument is electrically supplied by the driver device through first electrical conductors dedicated to power supply of the motor. The instrument is supplied and or electrically controllable by the control device through second electrical conductors which advantageously are distinct from the first conductors.

Advantageously the system according to the invention further comprises a management module of the second electrical conductors for sending on the second electrical conductors a number of signals greater than the number of the second electrical conductors.

The system of the invention thus enables a complete separation between the power supply signals of the motor of which the first electrical conductors are dedicated and the driver and or power supply signals of the instrument and or accessory and or synchronization signals between the electronic modules which are associated with the second electrical conductors

In a preferred embodiment the second electrical conductors consists in two conductors and the management module of the second electrical conductor sends four signals on these second electrical conductors in particular a power supply signal of the second electronic module a power supply signal of an accessory such as a lamp a signal sent by the second electronic module to the first electronic module carrying at least information concerning the rotary motor and the general management information and a signal sent by the first electronic module to the second electronic module carrying information concerning the command given by the first electronic module to the second electronic module. Thus the number of signals sent on the second electrical conductors four is greater than the number of second electrical conductors two .

In a preferred embodiment the first electronic module comprises the management module. This management module may also be embedded in the second electronic module or be in both the first and the second electronic module.

Advantageously the system according to the invention allows the removal of the magnetic elements and therefore a saving of space and of money because no demodulator is required in the control device for demodulating the power supply signals of the rotary motor of the instrument.

Advantageously the system according to the invention does not have a floating power supply or decoupling inductors thus allowing space saving reliability and achieving a more economical solution.

Moreover the system according to the invention allows the use of digital communications with current loops which have a high degree of security and reliability.

According to the invention it is possible to have a high density of information and features on the second electrical conductors without using a high frequency modulation on the first electrical conductors.

In a preferred embodiment the rotary motor of the system is a motor with no commutator. It is preferably tri phases. In this variant the first electrical conductors consist in three conductors one for each of the three phases of the rotary motor.

It is therefore possible to have a total of five electrical conductors three dedicated exclusively for powering the rotary motor of the instrument and two galvanically completely independent of the phases of the motor that are dedicated to the control of the instrument and or of the power supply of the instrument and or accessories of the instrument and or the synchronization between the electronic modules. The accessory of the instrument is preferably an incandescent lamp or a LED for illuminating the work area but may also be for example a pushbutton or a sensor.

Advantageously sent signals on the second electrical conductors comprise a synchronizing signal between a first electronic module and a second electronic module and at least two of the following signals 

a second signal sent by the electronic module to the first electronic module carrying at least information relating to the rotary motor these information comprising the instantaneous position of the rotor of the rotary motor and general management information

a signal sent by the first electronic module to the second electronic module carrying information relating to the command given by the electronic module to the second electronic module.

Advantageously the signals on the second electrical conductors can be bidirectional they may be sent by the first electronic module to the second electronic module and or by the second electronic module to the first electronic module. In a preferred embodiment the first electronic module send signals to the second electronic module during a first time interval while the second electronic module sent signals to the first electronic module during a second time interval that is different from the first time interval. In other words the signals in both directions are not sent simultaneously on the second conductors.

In an embodiment the management module is arranged to send cycles of N periodic sequence on the second electrical conductors N being a positive number.

the first sequence corresponds to a clock signal sent by the first electronic module to the second electronic module

the second sequence corresponds to a signal sent by the first electronic module to the second electronic module

the third sequence corresponds to a signal sent by the second electronic module to the first electronic module

The fourth sequence corresponds to a power supply signal of the second electronic module and or the power supply signal of an accessory for example a lamp and or a power supply signal of auxiliary organs or auxiliary functions.

Advantageously the power supplying of the second electronic module by the first electronic module is provided only during the limited time period corresponding to the duration of the fourth sequence.

Advantageously the communications from the second electronic module to the first electronic module on the second electrical conductors are digitals in loop current produced by activation of different currents.

The invention further relates to a method for a surgical system in particular a dental system comprising 

a surgical instrument in particular a dental instrument with a rotary motor M for driving a tool for example a cutter and a second electronic module in the instrument

The motor M preferably includes a hanging or turbinate not shown for receiving a hand part not shown.

The instrument is preferably connected to a first electronic module by a flexible connection for example a flexible pipe not shown attached to the motor M. The instrument is supplied for example in water air and in electricity by this pipe.

In the case of the dental instrument of the pipe comprises five electrical conductors including three first electrical conductors L L and L and two second electrical conductors C and C.

The motor M of the instrument is electrically powered by the control device through the first electrical conductors L to L that is dedicated to supplying the motor. The instrument is powered and electrically controlled by the control device via the second electrical conductors C to C that are advantageously distinct from the first conductors.

In a preferred embodiment the rotary motor M of the system according to the invention is without commutator. It is preferably three phased. In this variant illustrated in the first electrical conductors L to L are three conductors one conductor for each of the three phases of the rotary motor.

It is therefore possible to have five total electrical conductors three L to L dedicated exclusively for supplying the rotary motor of the instrument and two C and C galvanically completely independent of motor s phases dedicated to the control and the supply of the instrument. The accessory of the instrument is preferably a light bulb for example a LED for illuminating the work area but any other types may also be envisaged for example a pushbutton or a sensor.

The flexible connector connecting the dental instrument to the control device may also comprise non illustrated pipes for the passage of air and or liquid. The pipes for the passage of air and or liquid. preferably comprise a water supply line for a spray and or also a cooling air supply line for cooling the motor M and or an air return line.

The motor M is for example a motor without brushes including a rotor and three coils. As discussed it may be for example a three phased motor with no commutator comprising three stator windings for example star assembled.

The rotary motor M may further comprise two sensors H H for determining at least one motor operating parameter. The sensors H H are for example analog Hall effect sensors or magneto resistive sensors for determining the instantaneous angular position of the motor s rotor. As illustrated in the two sensors H H are preferably arranged in order to form an angle of 90 between them.

Advantageously the system according to the invention also comprises a management module which in the illustrated example is in the first electronic module to send to the second electrical conductors C C a number of signals greater than the number of the second electrical conductors C C

In other words the management module manages the temporal sequences between electronic modules by performing a sort of time multiplexing of several signals on the second electrical conductors C and C wherein these signals are bidirectional some are sent by the first electronic module to the second module others sent by the second electronic module to the first module . As discussed in a preferred embodiment the signals in both directions are not simultaneous.

The system of the invention thus enables a complete separation between the supply signals of the motor to which the first electrical conductors L to L are dedicated and the clock and or control and or supply signals of the instrument and or accessory signals of the instrument associated with the second electrical conductors C and C.

Advantageously according to the invention the system allows the removal of the magnetic elements and therefore a substantial saving in space and money because the demodulator in the control device which allows a demodulation of supply signals of the rotary motor M of the instrument from other signals is no longer necessary.

The first electronic module includes a microprocessor a power supply a control module of the first electrical conductors L to L and the management module of the second electrical conductors C and C.

The second electronic module comprises a microprocessor a supply module an acquisition module of the positions of the rotary motor M and a module for managing digital communications on the second electrical conductors C and C in a continuous current loop as discussed below.

In the illustrated embodiment the second electronic module is connected to an accessory and to two position sensors H and H for example two Hall effect sensors.

Advantageously the system according to the invention has no floating power supply of and therefore no decoupling coils which allows space saving reliability and achieving a more economical solution.

Advantageously the system according to the invention does not have the demodulator of since it is no longer necessary to transmit the communication signals between the first and second electronic modules using a high modulation frequency in fact the presence of the second electrical conductors C C makes unnecessary the achievement of this modulation on the conductors L to L.

The second electrical conductors C and C can work by cycles of N periodic sequences N being a positive number. N sequences constitute a frame Tr. In the variant illustrated in N 4 and the sequences are numbered from Z to Z. illustrates an example of a voltage signal corresponding to the frame of

On the second electrical conductors C and C the signal for synchronization between the first electronic module and the second electronic module and at least two of the following signals are multiplexed 

the power signal from the second electronic module to the first electronic module this signal is a high speed signal meaning that at least 500 kBauds and carries information relating to the rotary motor M

the signal sent by the first electronic module to the second electronic module this signal is a medium speed signal meaning that at least 4800 Bauds and carries information regarding the command given by the first electronic module to the second electronic module .

In the variation of the sequence Z corresponds to a voltage signal V for example V 0 V which has a time duration t for example t 2 s. This signal is a clock signal sent by the first electronic module to the second electronic module .

The sequence Z corresponds to a voltage signal V for example V 5 V which has a time duration t for example t 8 s. In this example this signal is sent by the first electronic module to the second electronic module this signal is a medium speed signal meaning that at least 4800 Bauds and carries information regarding the command given by the first electronic module to the second electronic module .

The sequence Z corresponds to of a voltage signal V for example V 5 V which has a time duration t for example t 50 s. This signal in this example is sent by the second electronic module to the first electronic module this signal is a high speed signal meaning that at least 500 Kbauds and carries information regarding the position of the rotor of the motor M.

The sequence Z corresponds to a voltage signal V for example V 12 V which has a time duration t for example t 60 s. This signal is the power supply signal of the second electronic module and or the power supply signal of an accessory for example a lamp and or the power supply signal of organs or auxiliary functions.

The given voltage values V to V and the given time slots t to t are not exhaustive and may be modified by one skilled person according to the applications

Both the sequences shown in are also indicative and it is for instance possible to work in cycles of N periodic sequences N being a number different than four. It is also possible to use the frame Tr shown in with a different order of the sequences for example Z Z Z and Z.

In a preferred embodiment the sequence Z corresponds to the supply of the second electronic module by the first electronic module . This supply is carried out only during the time duration t which in a preferred embodiment is half of the total time duration of the frame Tr corresponding to t t t t. During the remaining time the second electronic module must rely on its own energy storage.

An embodiment of the hardware configuration of the supply of the second electronic module by the first electronic module is described in

As illustrated in the energy consumption of the second electronic module is performed only during the time duration of the sequence Z. One or more capacitors of the second electronic module allows an accumulation of energy as can be seen in . The stabilizer allows having a constant voltage signal and equal to V for example V 5V as can be seen in reference .

Auxiliary organs can be supplied either by the stabilizer in the case of low consumption either directly on the second electrical conductors C and C while assuming that the energy consumption stays within the confine zone Z.

In a preferred embodiment the two electronic modules and are synchronized. In a preferred embodiment the synchronizer unit is the first electronic module master and synchronized unit is the second electronic module slave .

The synchronization signal is preferably generated by the first electronic module master at the beginning of the cycle so in correspondence to the sequence Z by a reset of the second electrical conductors C and C. This zero potential is detected by the second electronic module which causes an interrupt signal on the embedded microprocessor as shown in

To the clock signal generated by the first electronic unit and shown in corresponds thus a reset of the second electrical conductors shown in . The interrupt signal shown in occurs at the moment when the tension of the second electrical conductors falls to zero. In this way the synchronization between the first and the second module is not dependent on the duration of the clock signal .

As discussed in a preferred embodiment the signals transmitted by the first electronic module toward the second electronic module communication correspond to the sequence Z in which has a duration t.

As discussed these signals are mid speed signals meaning that at least 4800 baud which carry information about the command sent by the first electronic module to the second electronic module . These signals are therefore general management API type signals not directly related to the rotation of the rotary motor M but addressed primarily to auxiliary functions such as lamp .

The microprocessor of the second electronic module as soon as the reception of the interrupt synchronization signal shown in which causes an interruption state Int in the microprocessor of the second electronic module shown in commits a timer signal shown in . This signal has a duration of a few s for example 6 s.

At the end of this timer signal the microprocessor of the second electronic module determines the nature of the data received. A data 0 corresponds to a synchronizing signal of short duration for example 2 s and a data 1 corresponds to a synchronizing signal of long duration for example 10 s.

The digital data messages sent by the first electronic module to the second module thus have the same frequency as the frame Tr of the second electrical conductors.

If the total duration of the frame Tr illustrated in and corresponding to t t t t is for example equals to 120 s the transmission speed of these messages is 8.33 KBauds. This rate although relatively slow is sufficient as orders for the overall management given to the motor M do not require instantaneous execution.

The data transmission protocol of the signals sent from the first electronic module to the second electronic module may for example be the API protocol illustrated in wherein 

As discussed the sequence Z corresponds to a signal sent by the second electronic module to the first electronic module .

This signal carries at least information concerning the rotary motor M these information comprising the instantaneous rotary position of the rotor of the motor M. This signal carries information that are similar to the general management information sent by the first electronic module to the second electronic module .

Since the messages sent by the second electronic module to the first electronic module carrier the instantaneous position of the rotor of the rotary brushless motor M position which must be known at all times by the first electronic module to ensure rotation of the motor M these messages require a higher transmission speed than the messages sent by the first electronic module to the second electronic module .

These communications occur during the sequence Z by a message which in a preferred embodiment is composed of 24 bits. An example of such a message is illustrated in where

As discussed the sequence Z does not generate energy consumption by the second electronic module it is thus possible to use energy only when transferring information. For example the bit 0 may correspond to the absence of energy consumption including current consumption while the bit 1 may correspond to a predetermined current consumption for example and not limited to a consumption of 50 mA.

Since there are preferably a synchronous communication between the microprocessor of the first electronic module and the microprocessor of the second electronic module a clock signal must be associated with the data to indicate the time of validity of the transmitted data to the receptor in particular to the first electronic module . Other solutions with no clock signal for example by using the fixed value of a first bit of a sequence may also be considered.

During the sequence Z the state 0 of the clock signal shown in can prohibit the consumption through the second electrical conductors and the state 1 can cause two different current consumptions I I shown in the according to the state of the corresponding data shown in

Therefore if the clock signal is zero the power consumption is always I which in a preferred embodiment corresponds to 0 mA.

If the clock signal is in the state 1 for a data bit equals to zero the current consumption by the second electronic module is I in a preferred embodiment I 25 mA.

If the clock signal is in the state 1 for a data bit equals to one the current consumption by the second electronic module is I in a preferred embodiment I 50 mA.

If the clock signal output from the microprocessor of the second module is in the state 0 diode D prevents transistor T T to be in conduction. If it is 1 and the data to 0 only the transistor T conducts and causes a current consumption of V R. In a variant V R 25 mA. On the other hand if the clock signal and the data are simultaneously at 1 T and T are conducting. In this case the current consumption is V R V R. In a variant V R V R 50 mA.

Transmissions by current consumption from the second electronic module to the first electronic module thus take the characteristics of the

The differential amplifier A converts the current variations I of the second electrical conductors C C in proportional voltage variations Uc k Ic referenced to the zero potential ground . From Uc a first trigger B can extract the state data 1 when Uc REFand a second trigger B reforms the signal clock a when Uc REF.

In order to have a correct acquisition of data by the microprocessor a time switch C generates a clock signal b by delaying it clock a . A time delay less than 1 s for example delay of about 100 ns is enough. In this way the clock acts on a stable state of the data.

In the shown examples in the clock and the data are two separate signals which allows simple encoding and decoding of signals. In another variant it is possible to have another arrangement of synchronous transmission in which the combination clock data is a mono signal. An example is given by the Manchester code shown in .

The management of an accessory such as a lamp is controlled by the microcontroller of the electronic module according to API commands given by the first electronic module as illustrated in .

In a variant the lamp supply is based on the PWM technique Pulse Width Modulation generated by the microcontroller of the second electronic module .

As discussed in a preferred embodiment the supply of the lamp is only allowed during the sequence Z the frequency of PWM is equals to the cycles of the second electrical conductors and the opening duration of PWM ranges from 0 to 50 or generally equals to an opening time t.

According to the lamp voltage Urequested by the command API the microcontroller of the second electronic control module controls an opening of the transistor T with equivalent duration. In one example the duty cycle is maximum 50 and the voltage V during Z is 12 Vdc the maximum lamp voltage is thus 6 Vdc.

Possible auxiliary organs can be supplied during the sequence Z in the same manner as the lamp for example by a second PWM or if their consumption is low for example less than 100 mA in the same way that the second electronic module .

