---

title: Arrangement for improving transient deviation compensation of an output voltage of a DC-to-DC converter
abstract: When generating a voltage Vof a DC-to-DC converter for a load which is connected to the converter, it is necessary to monitor the quality of the voltage, in particular its amplitude. For this, provision is made for a comparator to be arranged between the output of the DC-to-DC converter and a control input of the control unit, with a first input of the comparator being connected to the output of the DC-to-DC converter (V), the second input of the comparator being connected to a reference voltage (V) and the output of the comparator being connected to the control input of the control unit of the DC-to-DC converter, for controlling the voltage V.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09525345&OS=09525345&RS=09525345
owner: Zentrum Mikroelektronik Dresden AG
number: 09525345
owner_city: Dresden
owner_country: DE
publication_date: 20130708
---
This application claims priority of provisional application Ser. No. 61 668 691 filed on Jul. 6 2012 the entire contents of which is hereby incorporated by reference herein.

Voltage regulators can generally only compensate for rapid transient load changes to a limited extent i.e. the output voltage thereof experiences deviations from the control voltage so called transient deviations depending on the extent of the load change. The implemented control loops compensate for these control deviations generally over time. In the case of switching converters this is particularly problematic since they are usually operated in various operating modes for optimizing their efficiency. Thus a distinction is generally drawn between the discontinuous mode DCM and the continuous mode CCM . In this case the transition between the modes can take place continuously or in a manner triggered by thresholds by virtue of measuring a value proportional to the load current. The mentioned control deviations have a particularly negative effect in the case of switching converters since for example on transition from a low load to a high load the speed at which the connected coil can follow the load current changes is limited by its inductance and the speed of the implemented control loop. It should be noted that the implemented control loops generally need to meet stability criteria which make these control loops slow and therefore the transient deviation unnecessarily great.

The principle illustrated here makes it possible to compensate for transient deviations in accordance with the physical limitation of the coils used outside the conventional control loops. The physical and electrical properties of the components used in the system are used to detect and compensate for load current changes.

The principle illustrated is not restricted to an arrangement for generating one voltage. Such arrangements can also generate several voltages for example two three or four.

For optimum system performance provision is made for an automatic reproduction of the voltage amplitude or phase angles to take place without the need for a communication with a user.

The principle illustrated enables improved compensation of transient deviations of the control voltage V . For this purpose a control signal is provided which engages in the conventional control loop even before said control loop can correct the control deviations. Provision is made for this control signal to end the monitoring of the control voltage at a favorable point in time and this monitoring is then resumed again by the conventional control loop.

The principle is illustrated using the example of a 4 phase digital DC DC controller. It is not restricted to this embodiment. The illustrated method can also be used for single phase digital controllers or for analog multi phase and single phase controllers.

The mode of operation is illustrated with reference to a block circuit diagram in and to a graph illustrating the associated voltage time profiles in . The DC to DC converter illustrated in comprises by way of example a controller for controlling the arrangement itself logic gates gate drivers D to D the high side switches HS HS HS and HS the low side switches LS LS LS and LS and the inductances L to L at the output of the converter at which the output voltage control voltage Vis provided. A load Load is connected at the output. The current Iflows through this load. In order to regulate the value of the voltage V a comparator is interposed between the output of the converter and a control input of the controller said comparator generating a control signal Restore by means of a comparison voltage V.

It is assumed that at the beginning the DC to DC converter operates in a DCM PFM operating mode wherein a low load current flows at the output and or is operated with fewer than the maximum number of possible phases.

For the case where the load current Iincreases quickly the output voltage Vwill become correspondingly lower. This voltage dip is illustrated at time t in . The upper illustration in shows the two switching thresholds PWM limit and Panic limit at which the generated control signal Restore switches.

If the voltage V which is applied to the comparator shown in falls below the value of the voltage V which is applied as comparison voltage at an input of the comparator the control signal Restore is applied at the output of the comparator by said comparator. This corresponds to the time when the output voltage as indicated at the top in falls below the panic threshold. With this Restore signal all of the high side switches HS HS HS and HS are turned on by means of the logic gates and the PWM gate drivers D D D and D.

By virtue of this operation the drop in the voltage Vis compensated for and the voltage increases again as is illustrated in the lower part of with the rise of the current in all four phases after time t. This voltage rise of V taking into consideration the hysteresis of the comparator which can be implemented in programmable fashion results in a disconnection of the control signal Restore at the output of the comparator at the time when the output voltage reaches the PWM limit threshold as shown at the top in . This results in the transition to the normal PWM mode CCM mode of the DC to DC converter and in transfer to the normal control loop.

This method becomes more effective the more noticeable the parasitic physically provided resistances ESR and inductances ESL of the capacitances and the printed circuit board at the output. This is particularly the case in the case of rapid and high load current changes and when using low capacitances.

A second extended method for phase correction will be described below with reference to . In this regard shows an arrangement according to extended by a differentiating stage and shows the voltage time profiles associated with the arrangement shown in .

As previously it is assumed that at the beginning the DC to DC converter operates in a DCM PFM operating mode wherein a low load current is connected or operation is with fewer than the maximum number of possible phases.

When the load current Iincreases rapidly the output voltage Vbecomes correspondingly lower. This voltage dip is shown at time t in .

A ratio between the voltage change of Vout and its associated change over time in accordance with dVout dt is formed by means of the disclosed method with a means suitable for this purpose. illustrates this with a steep drop in the ratio dVout dt. The means is illustrated in as a differentiating stage connected upstream of the comparator. The already known comparator which generates the known control signal Restore at its output is actuated by means of a second control voltage generated by this differentiating stage. The control signal Restore generated in this way switches on all high side switches HS HS HS and HS by means of the logic gates and by means of the PWM gate drivers D D D and D as was previously the case. By virtue of this operation the drop in the voltage Vout is compensated for and the voltage increases again.

The ratio dVout dt is low in value as is illustrated by the rise of the function in . The voltage rise of Vout taking into consideration the hysteresis of the comparator results in a disconnection of the control signal Restore at the output of the comparator and therefore in the transition to the normal PWM mode of the DC to DC converter.

By virtue of the generation of the ratio dVout dt the compensation of the voltage dip of Vout already begins at time t as is illustrated in which enables even quicker compensation of faults in the voltage Vout in comparison with the first mentioned method shown in .

In one configuration of both variants provision is made for parasitic components of the load ESL and ESR to be used for generating the control signal as is illustrated in in order to achieve the above described rapid compensation for a voltage dip in the voltage Vout.

For this purpose a tap at the load is used as is illustrated in . This tap is either connected directly to the comparator input as shown in or can be connected to the differentiating element in a similar manner to that shown in in order to generate the control signal Restore . The principle is shown using the example of a 4 phase digital DC DC controller. It is not restricted to this embodiment. The method illustrated can also be used for single phase digital controllers or for analog multi phase and single phase controllers.

