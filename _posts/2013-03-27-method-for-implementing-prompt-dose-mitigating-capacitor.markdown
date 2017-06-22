---

title: Method for implementing prompt dose mitigating capacitor
abstract: A method for implementing a prompt dose mitigating capacitor is disclosed. Initially, a flip chip is provided with multiple capacitors. The flip chip is then placed on top of a substrate having multiple electronic devices connected to a set of power rails. The terminals of the capacitors within the flip chip are subsequently connected to the power rails within the substrate in order to regulate voltages appeared on the power rails during a radiation pulse.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09027226&OS=09027226&RS=09027226
owner: BAE Systems Information and Electronic Systems Integration Inc.
number: 09027226
owner_city: Nashua
owner_country: US
publication_date: 20130327
---
The present invention was made with United States Government support under contract number DTRA01 03 D 0007 0001 awarded by the Defense Threat Reduction Agency. The United States Government has certain rights in the present invention.

The present invention relates to integrated circuits in general and in particular to a method for fabricating radiation tolerant integrated circuit devices.

Most of today s high density integrated circuit IC devices have been fabricated with complementary metal oxide semiconductor CMOS processing technology that is well known to those skilled in the art of semiconductor processing. Two biggest advantages of CMOS IC devices are high noise immunity and low power dissipation. As such CMOS IC devices are desirable in most commercial applications. However standard CMOS IC devices may not be very suitable for aerospace applications because those environments tend to be characterized by high levels of radiation particularly charged particles and standard CMOS IC devices are notorious for having a relatively low radiation tolerance.

Prompt dose upset PDU and prompt dose transients PDT are terms used to describe a response of an electronic circuit to a radiation pulse. A radiation pulse generates multiple electron hole pairs in the semiconductor material through an ionization process. The electrons are swept toward and collected at the positive circuit nodes creating a negative pulse. In conjunction the holes are collected in the ground terminal s . Because an electronic circuit has inherent impedance the above mentioned photo current creates undesired voltage drops resulting in a rail span collapse i.e. a collapse of voltage across the circuit nodes which in turn cause logical or storage errors. The collapse of power rails in input output I O circuits create temporary transients resulting in signal changes at the output of the I O circuits. The effect of the radiation pulse worsens as power supply voltage is reduced with advance technologies thus reducing the overhead margin and with increase in device size and complexity which increases the amount of photo current .

In accordance with a preferred embodiment of the present invention a flip chip is provided with multiple capacitors. The flip chip is then placed on top of a substrate having multiple electronic devices connected to a set of power rails. The terminals of the capacitors within the flip chip are subsequently connected to the power rails within the substrate in order to regulate voltages appeared on the power rails during a radiation pulse.

All features and advantages of the present invention will become apparent in the following detailed written description.

In order to mitigate the photo current effect high speed switching capacitors are commonly used on circuit boards or even in electronic packages to supply the required charge and regulate the supply voltage during a radiation pulse. However some of the effectiveness of this regulation is lost due to the impedance of the path between capacitors and semiconductor devices.

The above mentioned deficiency can be addressed by placing prompt dose mitigating capacitors directly on a semiconductor device in order to reduce the impedance of the path to the circuit. One method to implement prompt dose mitigating capacitors is to use a separate metal insulator metal capacitor MIMCAP flip chip that can be mounted on top of a semiconductor device.

Referring now to the drawings and in particular to there are illustrated a method for implementing prompt dose mitigating capacitors in accordance with a preferred embodiment of the present invention. Initially electrical devices are fabricated on a substrate preferably via a complementary metal oxides semiconductor CMOS process that is well known to those skilled in the art as shown in . Substrate is preferably made of silicon. Electrical devices within substrate are connected to various power rails such as Vdd Vdd and Vdd within substrate and ground rails such as GND and GND within substrate .

A flip chip is then placed on top of substrate via a ball grid array as depicted in . Flip chip includes multiple capacitors such as MIMCAP. Alternatively flip chip may include multiple deep trench capacitors. Positive terminals of the capacitors within flip chip are connected to the corresponding power rails not shown within substrate . For example the positive terminals of the capacitors can be connected to various power rails such as Vdd Vdd or Vdd. Similarly negative terminals of the capacitors within flip chip are connected to the corresponding ground rails not shown within substrate . For example the negative terminals of the capacitors can be connected various ground rails such as GND or GND. The capacitors within flip chip should be placed as close to electrical device as possible in order to maximize their voltage regulation effectiveness.

The required capacitance of the capacitors within flip chip needs to be significantly large in order to store enough charge to counteract the effect of radiation induced photo current.

A typical radiation pulse of 1 10 Si s magnitude generated several amperes of current in a semiconductor device approximately 1 10 A . A typical radiation pulse from a flash X ray source lasts about 20 ns thus creating 20 200 nC of charge. A typical operating voltage is approximately 1 V and needs to be regulated to 0.1 V during the radiation pulse in order to operate error free through the event. This necessitates a capacitance of 0.2 2 F. If MIMCAPs are being used within flip chip and each of the MIMCAPs has a characteristic capacitance of around 10 fF m the total area of the MIMCAP needs to be about 20 200 mm.

As has been described the present invention provides a method for implementing prompt dose mitigating capacitors.

While the invention has been particularly shown and described with reference to a preferred embodiment it will be understood by those skilled in the art that various changes in form and detail may be made therein without departing from the spirit and scope of the invention.

