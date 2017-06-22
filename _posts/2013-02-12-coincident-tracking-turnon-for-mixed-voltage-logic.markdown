---

title: Coincident tracking turn-on for mixed voltage logic
abstract: A method for dealing with high inrush current when voltage is applied to mixed voltage logic integrated circuits is disclosed. A depletion N-Channel Metal Oxide Semiconductor Field Effect Transistor (MOSFET) or junction Field Effect Transistor (JFET) is added to a linear voltage regulator in mixed voltage logic integrated circuits. The Field Effect Transistor (FET) is utilized to allow the core voltage to come up with Input/Output voltage prior to turn-on of linear voltage regulator. Turn-on state of FET allows the core voltage to rise with Input/Output voltage until the FET threshold is reached across the gate. When threshold is reached, the FET turns off to allow linear voltage regulator turn on and take over supply power.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08994434&OS=08994434&RS=08994434
owner: BAE Systems Information and Electronic Systems Integration Inc.
number: 08994434
owner_city: Nashua
owner_country: US
publication_date: 20130212
---
This invention was made with United States Government support under Contract No. NNG10CR08C awarded by the National Aeronautics and Space Administration. The United States Government has certain rights in this invention.

This application claims rights under 35 USC 119 e from U.S. Application Ser. No. 61 597 999 filed 13 Feb. 2012 the contents of which are incorporated herein by reference.

Embodiments are generally related to Integrated Circuits ICs . Embodiments are also related to mixed voltage logic ICs. Embodiments are additionally related to methods dealing high inrush current when voltage is applied to mixed voltage logic ICs. Embodiments are also additionally related to coincident tracking turn on for mixed voltage logic.

Electronic systems employing analog circuitry along with microprocessors DSPs ASICs and FPGAs has many different power supply rails. The on off timing rise and fall rate order of application and magnitude of each of the supply voltages needs to be controlled for reliable repeatable operation. Power system design includes supply sequencing supply tracking supply voltage current monitoring and control. A variety of power management ICs exists to perform the functions of sequencing tracking and monitoring for both power up and power down.

Power supply tracking is based on the fact that power supplies cannot provide instantaneous changes in their voltage this can be used advantageously by power system designers in controlling the slew rate of each of the various supplies in relation to other supplies in the system.

Power supply tracking systems handle a variety of power up profiles to satisfy the requirements of digital logic circuits including FPGAs PLDs DSPs and microprocessors. Some applications require that the potential difference between two power supplies must never exceed a specified voltage. This requirement applies during power up and power down as well as during steady state operation often to prevent destructive latch up in a dual supply ASIC. Typically this result is achieved by ramping the supplies up and down together. In other applications it is desirable to have the supplies ramp up and down with fixed voltage offsets between them or to have them ramp up and down ratiometrically.

During turn on of dual voltage ICs circuits powered by Input Output IO voltage can be in state that draws excessive current because core voltage is below minimum voltage to ensure logic is in proper state. This condition may create a problem in some circumstances when supplies did not have the capability to provide this large current and consequently would not become operational. Typically boards are provided which have limited available voltages lower voltages must be generated on card which limits options on controlling sequencing.

Heretofore it has been necessary to provide oversized power systems or to add complex circuitry which requires the availability of board space and proper voltages for biasing.

A need therefore exists for an improved way to deal with a high inrush current when voltage is applied to mixed voltage logic.

The following summary is provided to facilitate an understanding of some of the innovative features unique to the disclosed embodiments and is not intended to be a full description. A full appreciation of the various aspects of the embodiments disclosed herein can be gained by taking the entire specification claims drawings and abstract as a whole.

It is therefore one aspect of the disclosed embodiments to provide an improved Integrated Circuits ICs .

It is further aspect of the disclosed embodiments to provide an improved method to deal high inrush current when voltage is applied to mixed voltage logic ICs.

It is yet further aspect of the disclosed embodiments to provide an improved method for coincident tracking turn on for mixed voltage logic.

The aforementioned aspects and other objectives and advantages can now be achieved as described herein. A method for dealing with high inrush current when voltage is applied to mixed voltage logic integrated circuits is disclosed. A depletion N Channel MOSFET or junction FET is added to a linear voltage regulator in mixed voltage logic integrated circuits. The FET is utilized to allow the core voltage to come up with Input output voltage prior to turn on of linear voltage regulator. Turn on state of FET allows the core voltage to rise with Input Output voltage until the FET threshold is reached across the gate. When threshold is reached the FET turns off to allow linear voltage regulator turn on and take over supply power.

The present invention provides a compact solution which is effectively out of circuit during normal operation so previous analysis and testing are still valid. Furthermore this solution has higher power efficiency since normal power does not pass through an isolate switch for Input Output voltage. It will also be appreciated that the invention also allows core voltage to immediately rise with Input Output voltage and is only limited by the FET device resistance which can be scaled to any desired value by device selection and or paralleling.

The particular values and configurations discussed in these non limiting examples can be varied and are cited merely to illustrate at least one embodiment and are not intended to limit the scope thereof.

The embodiments now will be described more fully hereinafter with reference to the accompanying drawings in which illustrative embodiments of the invention are shown. The embodiments disclosed herein can be embodied in many different forms and should not be construed as limited to the embodiments set forth herein rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the invention to those skilled in the art. Like numbers refer to like elements throughout. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises and or comprising when used in this specification specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

Referring to the schematic diagram of the device depicted in is shown. A FET depicted in can be a Junction FET or a MOSFET. In a depletion N channel MOSFET is utilized for coincident tracking turn on of mixed voltage logic . Turn on state of depletion N channel MOSFET allows the core voltage to rise with Input Output voltage until the depletion N channel MOSFET threshold is reached across the gate. When threshold is reached the depletion N channel MOSFET turns off to allow linear voltage regulator turn on and take over supply power. Note that in the source drain and gate of the depletion N channel MOSFET are denoted as S D and G respectively.

Referring to a graph with waveforms and shows how core voltage ramps up coincident with Input Output voltage. In accordance with the disclosed embodiments the waveforms and represent variation of core voltage and variation of Input output voltage with respect to time respectively by adding a FET to a regulator in mixed voltage logic ICs. The waveform shows variation of core voltage without FET in mixed voltage logic ICs. As shown in coincident tracking the waveforms and rise at the same rate and finish at different times.

Those skilled in the art will appreciate that the following variations would be possible. For example multiple FETs could be placed in parallel to increase capacity and lower effective resistance. Junction FET would be used instead of MOSFET. For lower core voltages bias could also be generated by a charge pump or similar circuit.

Those skilled in the art will also appreciated that the present invention provides a compact solution which is effectively out of circuit during normal operation so previous analysis and testing are still valid. Furthermore this solution has higher power efficiency since normal power does not pass through an isolate switch for Input Output voltage. It will also be appreciated that the invention also allows core voltage to immediately rise with Input Output voltage and is only limited by the FET device resistance which can be scaled to any desired value by device selection and or paralleling.

While the present invention has been described in connection with the preferred embodiments of the various figures it is to be understood that other similar embodiments may be used modifications and additions may be made to the described embodiment for performing the same function of the present invention without deviating there from. Therefore the present invention should not be limited to any single embodiment but rather construed in breadth and scope in accordance with the recitation of the appended claims.

