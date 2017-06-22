---

title: Shift register unit, gate driving circuit, array substrate and display apparatus
abstract: A shift register unit, a gate driving circuit, an array substrate and a display apparatus are disclosed to reduce noises generated at an output of a next stage shift register unit caused by an output of a pervious stage shift register unit. The shift register unit at each stage comprises at least a signal inputting terminal INPUT, a signal outputting terminal OUTPUT and a capacitor CAP connected with the outputting terminal OUTPUT so as to provide an output signal to the outputting terminal OUTPUT, wherein the shift register unit further comprises a switch located between the capacitor CAP and the outputting terminal OUTPUT, and the switch is in a turned-off state when the capacitor CAP is charged.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09269455&OS=09269455&RS=09269455
owner: BOE TECHNOLOGY GROUP CO., LTD.
number: 09269455
owner_city: Beijing
owner_country: CN
publication_date: 20131028
---
The present invention relates to a field of display technique and particularly to a shift register a gate driving circuit an array substrate and a display apparatus.

A flat panel display has developed rapidly because of its ultrathin and energy saving. Most of the flat panel displays use shift registers. Currently the shift register realized by a GOA Gate on Array method not only can be integrated on a gate driving Integrated Circuit IC but also can cut down a manufacture procedure for a display panel therefore it saves cost. As a result the GOA technique has been applied widely to a manufacture process for the flat panel display recently.

A schematic diagram of an inner structure of the above shift register unit S R n is shown in . As shown in the shift register consists of 12 Thin Film field effect Transistors TFT labeled as M1 M2 M3 M4 M5 M6 M8 M9 M10 M11 M12 and M13 in respectively and one capacitor CAP labeled as C1 in and its corresponding control timing diagram is as illustrated in . For each shift register unit S R n it may be in three control states as follows 1 the inputting terminal INPUT and a clock signal CLKB are at a high level a clock signal CLK is at a low level and the M1 M13 M9 M8 M5 M6 and M12 are in a turned on state and other TFTs are in a turned off state at this time thereby the inputting terminal INPUT inputs a signal in this case and thus the outputting terminal OUTPUT outputs a low level signal since the CLK is at the low level 2 the inputting terminal INPUT and the CLKB are at the low level the CLK is at the high level and the M3 M9 M5 M6 and M8 are in the turned on state and other TFTs are in the turned off state at this time thereby the outputting terminal OUTPUT outputs a high level signal in this case 3 the CLKB is at the high level the inputting terminal INPUT and the CLK are at the low level and the M13 M12 M11 M10 M2 M4 M5 and M9 are in the turned on state and other TFTs are in the turned off stage at this time thereby a resetting operation is performed for a shift register unit at a previous stage in this case.

It can be seen from the description above that since the shift register unit at the Nth stage uses an output signal of the shift register unit at the N 1 th stage as an input signal the outputting terminal OUTPUT of the shift register unit at the Nth stage will output noise due to the existence of the capacitor C1 when the shift register unit at the Nth stage is in the first control state described above.

To address the technical problems existing in the prior art there are provided in embodiments of the present invention a shift register unit a gate driving circuit an array substrate and a display apparatus to reduce noises generated at an output of a next stage shift register unit at caused by an output of a pervious stage shift register unit.

A shift register unit in accordance with the embodiments of the present invention each stage of the shift register unit comprises at least a signal inputting terminal INPUT a signal outputting terminal OUTPUT and a capacitor CAP connected with the outputting terminal OUTPUT to provide an output signal to the outputting terminal OUTPUT. The shift register unit further comprises a switch located between the capacitor CAP and the outputting terminal OUTPUT and the switch is in a turned off state when the capacitor CAP is charged.

A gate driving circuit provided in the embodiments of the present invention comprises the shift register unit described above.

An array substrate provided in the embodiments of the present invention comprises the gate driving circuit described above.

A display apparatus provided in the embodiments of the present invention comprises the array substrate described above.

In the shift register unit the gate driving circuit the array substrate and the display apparatus according to the embodiments of the present invention by adding a switch between the capacitor CAP and the outputting terminal OUTPUT which is in the turned off state when the inputting terminal INPUT charges the capacitor CAP the outputting terminal OUTPUT is avoided to couple with the capacitor CAP and output the noises. Thus when a plurality of the shift register units are layered and connected in cascade to construct a shift register the noises generated at the output of the next stage shift register unit caused by the output of the pervious stage shift register unit can be reduced.

Other features and advantages of the present invention will be explained in following description and will partly become apparent from the detailed description given hereinafter or will be know by practice of the present invention. Features and other advantages of the present invention may be achieved and acquired by structures recited specially in the disclosed specification claims and the drawings.

In order to reduce noises generated at the output of the next stage shift register unit caused by the output of the pervious stage shift register unit there are provided in the embodiments of the present invention a shift register unit a gate driving circuit an array substrate and a display apparatus.

Exemplary embodiments of the present invention will be described in conjunction with the accompanying drawings. It should be understood that the exemplary embodiments described herein are only used to illustrate and explain the present invention but not to limit the present invention and the embodiments of the present invention and features in the embodiments may be combined with each other in a case of no conflicts.

The embodiments of the present invention provide a shift register unit and shows a schematic diagram of a circuit structure of a shift register unit according to the embodiments of the present invention. As shown in a switch is added between a capacitor CAP identified as C1 in and a signal outputting terminal OUTPUT on a basis of in the shift register unit according to the embodiments of the present invention. Optionally the switch may be but not limited to a TFT. The switch is in a turned off state when a signal inputting terminal INPUT charges the CAP so that the outputting terminal may be avoided to couple with the CAP and output noises. A connection manner is as follows when the switch is the TFT the newly added TFT is identified as M7 in a source of the TFT is connected with the CAP a drain thereof is connected with the outputting terminal OUTPUT and a gate thereof is connected with a clock signal CLK. In a specific implementation the shift register unit may further comprise a resetting signal terminal RESET a reference signal terminal VSS a pulling up node PU and a capacitor CAP located between the pulling up node PU and the outputting terminal OUTPUT wherein 

when an input signal received by the inputting terminal INPUT is at a high level CLKB is at the high level CLK is at a low level while the pulling up node PU and the capacitor CAP are in a charging state and at this time an output signal at the outputting terminal OUTPUT is at the low level 

when the input signal received by the inputting terminal INPUT is at the low level CLKB is at the low level and CLK is at the high level a potential at the node PU is pulled high so that the output signal at the outputting terminal OUTPUT is at the high level 

when the input signal received by the inputting terminal INPUT is at the low level CLKB is at the high level and CLK is at the low level a potential at the node PU is pulled low so that the output signal at the outputting terminal OUTPUT is at the low level 

the resetting terminal RESET is connected with an signal outputting terminal of a next stage shift register with respect to the current stage shift register 

the reference signal terminal VSS is used for inputting a low level signal in order to provide a reference voltage.

The shift register unit illustrated in comprises a first thin film transistor M1 a second thin film transistor M2 a third thin film transistor M3 a fourth thin film transistor M4 a fifth thin film transistor M5 a sixth thin film transistor M6 a seventh thin film transistor M7 an eighth thin film transistor M8 a ninth thin film transistor M9 a tenth thin film transistor M10 an eleventh thin film transistor M11 a twelfth thin film transistor M12 a thirteenth thin film transistor M13 a capacitor C1 a pulling up node PU a pulling down node PD and a pulling down connection node PD CN wherein 

a gate and a drain of M1 are connected with the signal inputting terminal INPUT and a source thereof is connected with the pulling up node PU 

a gate of M2 is connected with the resetting signal terminal RESET a drain thereof is connected with the pulling up node PU and a source thereof is connected with the reference signal terminal VSS 

a gate of M3 is connected with the pulling up node PU a drain thereof is connected with the clock signal CLK and a source thereof is connected with the signal outputting terminal OUTPUT 

a gate of M4 is connected with the resetting signal terminal RESET a drain thereof is connected with the signal outputting terminal OUTPUT and a source thereof is connected with the reference signal terminal VSS 

a gate of M5 is connected with the pulling down connection node PD CN a drain thereof is connected with the clock signal CLKB and a source thereof is connected with the pulling down node PD 

a gate of M6 is connected with the pulling up node PU a drain thereof is connected with the pulling down node PD and a source thereof is connected with the reference signal terminal VSS 

a gate of M7 is connected with the clock signal CLK a drain thereof is connected with the signal outputting terminal OUTPUT and a source thereof is connected with the capacitor C1 

a gate of M8 is connected with the pulling up node PU a drain thereof is connected with the pulling down connection node PD CN and a source thereof is connected with the reference signal terminal VSS 

a gate and a drain of M9 are connected with the clock signal CLKB and a source thereof is connected with the pulling down connection node PD CN 

a gate of M10 is connected with the pulling down node PD a drain thereof is connected with the pulling up node PU and the source thereof is connected with the reference signal terminal VSS 

a gate of M11 is connected with the pulling down node PD a drain thereof is connected with the signal outputting terminal OUTPUT and a source thereof is connected with the reference signal terminal VSS 

a gate of M12 is connected with the clock signal CLKB a drain thereof is connected with the signal outputting terminal OUTPUT a source thereof is connected with the reference signal terminal VSS 

a gate of M13 is connected with the clock signal CLKB a drain thereof is connected with the signal inputting terminal INPUT and the source thereof is connected with the pulling up node PU.

An operating principle of the embodiments of the present invention will be described thereafter in connection with the schematic diagram of the control timing as shown in . When the inputting terminal INPUT and CLKB are at the high level CLK is at the low level the inputting terminal INPUT and CLKB charge the C1 up to VGH a starting voltage through the M1 and M13 at the same time the M12 is turned on and pulls down an output at the outputting terminal OUTPUT and M6 M8 M9 are turned on to pull down the nodes PD CN and PD to VSS the reference voltage so that the M10 M11 are in the turned off state M7 is in the turned off state at this time since CLK is at the low level such that the outputting terminal OUTPUT is avoided to couple with the C1 and output the noises and all of other TFTs are in the turned off state when the inputting terminal INPUT and CLKB are at the low level CLK is at the high level M1 M13 M9 and M5 are in the turned off state and at this time M3 M7 are turned on CLK is outputted to the outputting terminal OUTPUT via M3 and coupled to the node PU thereby the node PU is pulled up and other TFTs are in the turned off state when the inputting terminal INPUT and CLK are at the low level CLKB is at the high level M2 M4 are turned on to pull down the node PU and the outputting terminal OUTPUT M9 M5 are turned on to pull up the node PD M11 and M10 are turned on to continually pull down the node PU and the outputting terminal OUTPUT further the M12 is turned on at this time to pull down the outputting terminal OUTPUT also and other TFTs are in the turned off state such that the resetting operation of the previous stage shift register unit is implemented.

In the embodiments of the present invention there is further provided a gate driving circuit comprising the shift register unit described above.

In the embodiments of the present invention there is further provided a display apparatus comprising any array substrate as described above. The display apparatus may be a liquid crystal panel a piece of electronic paper an Organic Light Emitting Diode OLED panel a mobile phone a tablet computer a television a display a notebook computer a digital photo frame a navigation machine and any other product or means having a displaying function.

The above described liquid crystal panel may comprise a color film substrate an array substrate and a liquid crystal disposed between the color film substrate and the array substrate and the array substrate in the liquid crystal display panel comprises the shift register according to the embodiments of the present invention.

It should be noted that in the embodiments of the present invention the circuit structure of the shift register unit is not limited thereto. and illustrate the schematic diagram of the circuit structures of another two shift register units according to the embodiments of the present invention which differ from the structure in only in the circuit structure of the original shift register unit. Also a switch identified as M7 both in and is added between a capacitor C1 and an outputting terminal. Taking the newly added switch being a TFT as an example the connection structure of this switch is the same as that of the shift register unit illustrated in that is a source of the TFT is connected with a capacitor CAP a drain thereof is connected with an outputting terminal OUTPUT and a gate thereof is connected with a clock signal CLK. Since the principle for reducing the output noise in the shift register units shown in and are the same as that of the shift register unit as illustrated in their specific operations may be referred to the description of and the details will not be repeated herein.

The shift register unit illustrated in comprises a first thin film transistor M1 a second thin film transistor M2 a third thin film transistor M3 a fourth thin film transistor M4 a fifth thin film transistor M5 a sixth thin film transistor M6 a seventh thin film transistor M7 an eighth thin film transistor M8 a ninth thin film transistor M9 a tenth thin film transistor M10 an eleventh thin film transistor M11 a twelfth thin film transistor M12 a thirteenth thin film transistor M13 a fourteenth thin film transistor M14 a capacitor C1 a pulling up node PU a pulling down node PD and a pulling down connection node PD CN wherein 

a gate and a drain of M1 are connected with the signal inputting terminal INPUT and a source thereof is connected with the pulling up node PU 

a gate of M2 is connected with the resetting signal terminal RESET a drain thereof is connected with the pulling up node PU and a source thereof is connected with the reference signal terminal VSS 

a gate of M3 is connected with the pulling up node PU a drain thereof is connected with the clock signal CLK and a source thereof is connected with the signal outputting terminal OUTPUT 

a gate of M4 is connected with the resetting signal terminal RESET a drain thereof is connected with the signal outputting terminal OUTPUT and a source thereof is connected with the reference signal terminal VSS 

a gate of M5 is connected with the pulling down connection node PD CN a drain thereof is connected with the clock signal CLKB and a source thereof is connected with the pulling down node PD 

a gate of M6 is connected with the pulling up node PU a drain thereof is connected with the pulling down node PD and a source thereof is connected with the reference signal terminal VSS 

a gate of M7 is connected with the clock signal CLK a drain thereof is connected with the signal outputting terminal OUTPUT and a source thereof is connected with the capacitor C1 

a gate of M8 is connected with the clock signal CLKB a drain thereof is connected with the pulling down connection node PD CN and a source thereof is connected with the reference signal terminal VSS 

a gate and a drain of M9 are connected with the clock signal CLKB and a source thereof is connected with the pulling down connection node PD CN 

a gate of M10 is connected with the pulling down node PD a drain thereof is connected with the pulling up node PU and the source thereof is connected with the reference signal terminal VSS 

a gate of M11 is connected with the pulling down node PD a drain thereof is connected with the signal outputting terminal OUTPUT and a source thereof is connected with the reference signal terminal VSS 

a gate of M12 is connected with the clock signal CLKB a drain thereof is connected with the signal outputting terminal OUTPUT a source thereof is connected with the reference signal terminal VSS 

a gate of M13 is connected with the clock signal CLKB a drain thereof is connected with the signal inputting terminal INPUT and the source thereof is connected with the pulling up node PU 

a gate of M14 is connected with the clock signal CLKB a drain thereof is connected with the pulling down node PD and a source thereof is connected with the reference signal terminal VSS.

The shift register unit illustrated in comprises a first thin film transistor M1 a second thin film transistor M2 a third thin film transistor M3 a fourth thin film transistor M4 a fifth thin film transistor M5 a seventh thin film transistor M7 an eighth thin film transistor M8 a ninth thin film transistor M9 a tenth thin film transistor M10 an eleventh thin film transistor M11 a capacitor C1 a pulling up node PU and a pulling down node PD wherein 

a gate and a drain of M1 are connected with the signal inputting terminal INPUT and a source thereof is connected with the pulling up node PU 

a gate of M2 is connected with the resetting signal terminal RESET a drain thereof is connected with the pulling up node PU and a source thereof is connected with the reference signal terminal VSS 

a gate of M3 is connected with the pulling up node PU a drain thereof is connected with the clock signal CLK and a source thereof is connected with the signal outputting terminal OUTPUT 

a gate of M4 is connected with the resetting signal terminal RESET a drain thereof is connected with the signal outputting terminal OUTPUT and a source thereof is connected with the reference signal terminal VSS 

a gate and a drain of M5 are connected with the clock signal CLKB and a source thereof is connected with the pulling down node PD 

a gate of M7 is connected with the clock signal CLK a drain thereof is connected with the signal outputting terminal OUTPUT and a source thereof is connected with the capacitor C1 

a gate of M8 is connected with the pulling up node PU a drain thereof is connected with the pulling down node PD and a source thereof is connected with the reference signal terminal VSS 

a gate of M9 is connected with the resetting signal terminal RESET a drain thereof is connected with the clock signal CLKB and a source thereof is connected with the pulling down node PD 

a gate of M10 is connected with the pulling down node PD a drain thereof is connected with the pulling up node PU and the source thereof is connected with the reference signal terminal VSS 

a gate of M11 is connected with the pulling down node PD a drain thereof is connected with the signal outputting terminal OUTPUT and a source thereof is connected with the reference signal terminal VSS.

It is obvious that those skilled in the art can make various alternations and modifications to the present invention without departing from the spirit and scope of the present invention. Therefore these alternations and modifications are intended to be included in the present invention if they fall into the scope of the claims and their equivalent techniques.

