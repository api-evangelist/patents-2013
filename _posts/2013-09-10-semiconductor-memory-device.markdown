---

title: Semiconductor memory device
abstract: According to one embodiment, a semiconductor includes a memory cell, a bit line, a word line, a sense amplifier, and a control circuit. The memory cell stores n levels (where n is a natural number of two or greater). The control circuit controls potentials of the word line and the bit line. In a read of k−1 levels (k≦n) stored in the memory cell, the control circuit, upon applying a given voltage to the word line, determines read data based on first data corresponding to the voltage of the bit line read at a first timing by the sense amplifier and second data corresponding to the voltage of the bit line read, by the sense amplifier, at a second timing different from the first timing.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09190161&OS=09190161&RS=09190161
owner: KABUSHIKI KAISHA TOSHIBA
number: 09190161
owner_city: Tokyo
owner_country: JP
publication_date: 20130910
---
This application is based upon and claims the benefit of priority from Japanese Patent Application No. 2013 029342 filed Feb. 18 2013 the entire contents of which are incorporated herein by reference.

Embodiments described herein relate generally to a semiconductor memory device that can store two level data and multi level data for example a NAND flash memory.

NAND flash memories tend to have their threshold voltage distributions broadened and their data retention properties degraded as memory elements are miniaturized. Thus error checking and correction ECC such as a low density parity check LDPC may be used which has a powerful correcting capability. However ECC such as LDPC requires information referred to as soft values and which is different from values read at a normal read level. Thus a read operation soft bit read is performed at a level different from the normal read level and the results are used as soft values used for ECC such as LDPC. However this disadvantageously extends read time.

In general according to one embodiment a semiconductor includes a memory cell a bit line a word line a sense amplifier and a control circuit. The memory cell stores n levels where n is a natural number of two or greater . The bit line is connected to the memory cell. The word line is connected to the memory cell. The sense amplifier is connected to the bit line to detect a voltage of the bit line. The control circuit controls potentials of the word line and the bit line. In a read of k 1 levels k n stored in the memory cell the control circuit upon applying a given voltage to the word line determines read data based on first data corresponding to the voltage of the bit line read at a first timing by the sense amplifier and second data corresponding to the voltage of the bit line read by the sense amplifier at a second timing different from the first timing.

According to the present embodiment in a soft bit read using not only normal read levels but also different levels data is read by a read operation with a sense timing different from a sense timing for a normal read thus reducing the time required for the soft bit read.

Furthermore because of the level of data retention in memory cells a scheme has recently been proposed in which an optimum read level is determined for the data read. However this read scheme must perform a plurality of read operations in order to set the optimum read level requiring much time. Thus the present embodiment performs a read operation with a sense timing different from the sense timing for the normal read changed reducing the read time.

Additionally during data output the present embodiment reduces the number of bits in output data for the main part of a threshold voltage distribution while increasing the number of bits in output data for a skirt of the threshold voltage distribution which contains a small number of data thus reducing the total amount of output data.

The embodiment will be described below with reference to the drawings. The same components are denoted by the same reference numbers throughout the drawings.

A memory cell array includes a plurality of bit lines a plurality of word lines a common source line and memory cells arranged in a matrix and each of which comprises for example an EEPROM cell and allows data to be electrically rewritten. The memory cell array connects to a bit control circuit configured to control bit lines and a word line control circuit .

The bit line control circuit reads a memory cell in the memory cell array via the corresponding bit line detects the state of a memory cell in the memory cell array via the corresponding bit line and applies a write control voltage to a memory cell in the memory cell array via the corresponding bit line to write data to the memory cell. The bit line control circuit connects to a column decoder and a data input out I O buffer . The column decoder selects from data storage circuits in the bit line control circuit . Data from the memory cell read into the data storage circuit is externally output from a data I O terminal via the data I O buffer . The data I O terminal is connected to a host not shown in the drawings external to a memory chip. The host comprises for example a microcomputer and receives the data output from the data I O terminal . Moreover the host not shown various commands CMD that control the operation of the NAND flash memory addresses ADD and data DT. The write data input to the data I O terminal by the host is fed via the data I O buffer to the data storage circuit selected by the column decoder . The commands and addresses are fed to a control signal and control voltage generator .

The word line control circuit is connected to the memory cell array . The word line control circuit selects from the word lines in the memory cell array and applies a voltage required for a read write or erase to the selected word line.

The memory cell array the bit line control circuit the column decoder the data I O buffer and the word line control circuit are connected to the control signal and control voltage generator which controls the memory cell array the bit line control circuit the column decoder the data I O buffer and the word line control circuit . The control signal and control voltage generator is connected to a control signal input terminal and controlled by control signals ALE Address Latch Enable CLE Command Latch Enable WE Write Enable and RE Read Enable which are input by the host via the control signal input terminal . The control signal and control voltage generator generates voltages for the corresponding word line and bit line during a write and generates a voltage supplied to a well as described below. The control signal and control voltage generator includes a booster circuit for example a charge pump circuit and can generate a program voltage and other high voltages.

The bit line control circuit the column decoder the word line control circuit and the control signal and control voltage generator form a write circuit and a read circuit.

The bit line control circuit comprises a plurality of data storage circuits . Each of the data storage circuits connects to a pair of bit lines BL BL BL BL . . . BLie BLio or BLne BLno .

The memory cell array includes a plurality of blocks as shown by dashed lines. Each of the blocks comprises a plurality of NAND units and for example data is erased in units of the blocks. Additionally an erase operation is performed simultaneously on two bit lines connected to the data storage circuit .

Furthermore a plurality of memory cells MC arranged on every other bit line and connected to one word line the memory cells within a range enclosed by dashed lines forms a page. Data is written to and read from each page. That is half of the plurality of memory cells arranged in a row direction is connected to the corresponding bit lines. Thus a write operation or a read operation is performed on each half of the plurality of memory cells arranged in the row direction.

During a read operation a program verify operation and a program operation one of the two bit lines BLie BLio connected to the data storage circuit is selected in accordance with an externally supplied address signal YA YA . . . YAi . . . YAn . Moreover in accordance with the external address one word line is selected and two pages shown by dashed lines are selected. The two pages are switched based on addresses.

Storing two bits in one cell involves two pages. However storing one bit in one cell involves one page. Storing three bits in one cell involves three pages. Storing four bits in one cell involves four pages.

The following description is applicable to both the configuration shown in and the configuration shown in but the use of the configuration in will be described.

In addition a voltage supplied to a word line for an unselected cell during a write is denoted by Vpass and a voltage applied to an unselected word line during a read is denoted by Vread.

As shown in the sense amplifier comprises a plurality of N channel MOS transistors hereinafter referred to as NMOSs to a plurality of P channel MOS transistors hereinafter referred to as PMOSs and transfer gates and a latch circuit and a capacitor . The latch circuit comprises for example clocked inverter circuits and

One end of a current path in NMOS is connected to a node to which the power supply Vdd is supplied. The other end of the current path is grounded via transfer gate NMOS and transfer gate . A connection node between NMOS and transfer gate connects to one end of a current path in NMOS . The other end of NMOS is connected to the corresponding bit line BL in the memory cell array. NMOS connects in parallel with a series circuit of NMOSs and .

Furthermore one end of a current path in PMOS is connected to a node to which the power supply Vdd is supplied. The other end of the current path is connected via PMOS to an input end of inverter circuit included in the latch circuit and is grounded via NMOS . An input end of clocked inverter circuit cross connected to inverter circuit is connected to the data control unit DCU via NMOS . Furthermore the gate of PMOS is connected to a connection node between NMOSs and . The connection node connects to one end of the capacitor . The other end of the capacitor is supplied with a clock signal CLK.

The gate of NMOS is supplied with a signal BLX. The gate of the NMOS included in transfer gate is supplied with a signal LAT at an output end of inverter circuit included in the latch circuit . The gate of the PMOS transistor is supplied with a signal INV at an input end of inverter circuit . The gate of NMOS is supplied with a signal BLC and the gate of NMOS is supplied with a signal BLS.

The gate of PMOS is supplied with a signal STB and the gate of NMOS is supplied with a reset signal RST. The gate of NMOS is supplied with a signal NCO.

When data is written to a memory cell first signal STB is made high and the reset signal RST is momentarily made high to reset the latch circuit . LAT is made high and signal INV is made low.

Subsequently signal NCO is made high to retrieve data from the data control unit . If the data is low binary 0 which is indicative of a write signal LAT is made low and signal INV is made high. Furthermore if the data is high binary 1 which is indicative of a non write the data in the latch circuit is unchanged signal LAT is kept high and signal INV is kept low.

Then when signals BLX BLC and BLS are made high if signal LAT at the latch circuit is low and signal INV at the latch circuit is high write transfer gate is off and transfer gate is on to set the bit line BL to Vss. In this state when the word line is set to the program voltage Vpgm data is written to the memory cell.

On the other hand in the latch circuit if signal LAT is high and signal INV is low non write transfer gate is on and transfer gate is off and thus the bit line BL is charged to Vdd. Thus if the word line changes to Vpgm a channel of the cell is boosted to a higher potential preventing data from being written to the memory cell.

When a memory cell is read first the set signal RST is momentarily made high to reset the latch circuit signal LAT is made high and signal INV is made low. Subsequently signals BLS BLC BLX HLL and XXL are set to predetermined voltages to charge the bit line BL. In addition the node of the capacitor is charged to Vdd. If a threshold voltage for the memory cell is higher than the read level the memory cell is off and the bit line is kept high. That is the node is kept high. Furthermore if the threshold voltage for the memory cell is lower than the read level the memory cell is on and the bit line is discharged. Consequently the bit line BL is made low. Thus the node is made low.

Then when signal STB is made low if the memory cell is on the node is low and thus PMOS is on to make signal INV at the latch circuit high while making signal LAT at the latch circuit low. On the other hand if the memory cell is off signal INV at the latch circuit is kept low and signal LAT at the latch circuit is kept high.

Subsequently when signal NCO is made high NMOS is on to transfer the data in the latch circuit to the data control unit

A program verify operation of verifying the threshold voltage of the memory cell after the write operation is approximately similar to the above described read operation.

The data control unit shown in comprises an arithmetic circuit and a plurality of data latch circuits ADL BDL XDL and NMOS .

The arithmetic circuit comprises a bus hereinafter referred to as the IBUS transfer gates and connected to respective opposite ends of the IBUS and operating complementarily a latch circuit configured to latch data from the IBUS and a setting circuit configured to set levels for data latch circuits ADL BDL and XDL.

Transfer gate operates in accordance with complementary signals COND and CONS to connect a bus for the sense amplifier unit SAU hereinafter referred to as the SBUS and the IBUS together. Transfer gate operates in accordance with complementary signals CONS and COND to connect the IBUS to a bus to which data latch circuits ADL BDL and XDL are connected hereinafter referred to as the DBUS . While transfer gate is on transfer gate is off. While transfer gate is off transfer gate is on.

The latch circuit comprises a plurality of PMOSs to a plurality of NMOSs to and an inerter circuit . The gate of PMOS and the gate of NMOS are supplied with a set signal SET. The gate of PMOS is supplied with a reset signal REST. The gate of NMOS is supplied with a signal IFH. The gate of NMOS is supplied with a signal IFL. The gate of NMOS is connected to the IBUS via the inverter circuit . The gate of NMOS is connected to the IBUS.

The setting circuit comprises PMOSs to and NMOSs to . The gate of PMOS and the gate of NMOS are supplied with a signal FAIL. Signal FAIL is a signal at a connection node between PMOS and NMOS serving as one output end of the latch circuit . The gate of PMOS and the gate of NMOS are supplied with a signal MTCH. Signal MTCH is a signal at a connection node between PMOS and NMOS serving as the other output end of the latch circuit . Moreover the gate of PMOS is supplied with a signal MHB and the gate of PMOS is supplied with a signal FHB. The gate of NMOS is supplied with a signal FL and the gate of NMOS is supplied with a signal ML.

Data latch circuits ADL BDL and XDL have the same configuration and each comprise a latch circuit and a transfer gate configured to connect the latch circuit to the DBUS. Each transfer gate is controlled by signals BLCA BLCB BLCX BLCA B BLCB B and BLCX B. Data latch circuit XDL is connected to an external I O via NMOS . The gate of NMOS is supplied with a signal CSL.

Two bit write data supplied by a data I O buffer is latched by for example data latch circuits ADL and BDL via data latch circuit XDL so that each of data latch circuits ADL and BDL latches one of the two bits.

The arithmetic circuit shown in can perform arithmetic operations such as an AND operation an OR operation and an exclusive NOR operation on data in data latch circuits ADL and BDL. For an AND operation the data held in data latch circuits ADL and BDL are output to the DBUS and the IBUS. In this case the IBUS is made high only if both the data held in data latch circuits ADL and BDL are 1 and is otherwise made low. That is the IBUS is at 1 only during a non write and is at 0 during a write. A write is performed by transferring the data held in data latch circuits ADL and BDL to the sense amplifier unit shown in .

The arithmetic circuit shown in may be provided such that one arithmetic circuit is disposed for a plurality of the sense amplifier units SAU shown in and a plurality of data control units DCU shown in . This enables a reduction in circuit area.

The operation of the arithmetic circuit may be varied. For example various control methods are applicable to one logical operation and the control method may be changed as necessary.

The NAND flash memory according to the present embodiment is a multilevel memory and can thus store two bit data in one cell. The two bits are switched based on the addresses first page and second page . Storing two bits in one cell involves two pages but if three bits are stored in one cell each bit is switched based on the addresses first page second page and third page . Moreover if four bits are stored in one cell each bit is switched based on the addresses first page second page third page and fourth page .

According to the present embodiment one bit data can be stored in one cell but if two bit data is stored in one memory cell the two bit data is switched based on the addresses first page and second page . Furthermore if three bit data is stored in one memory cell the three bit data is switched based on the addresses first page second page and third page . Moreover if four bit data is stored in one memory cell the four bit data is switched based on the addresses first page second page third page and fourth page .

In the case described below for example data is written and read at a time to and from the memory cells arranged in the row direction as shown in and two bit four level data is stored in one cell.

As shown in an erase operation sets the threshold voltage for the data in the memory cell to 11. When data is written to the first page the memory cell remains in an erased state or the write is performed at level LMV and the threshold voltage for the data in the memory cell is set to 11 or 10.

As shown in when data is written to the second page the memory cell remains in the erased state or the write is performed at one of levels AV BV and CV and the threshold voltage for the data in the memory cell is set to 11 01 00 or 10. The verify level is set slightly higher for a write than for a read in order to provide a data retention margin. In and the read level is denoted by LMR AR BR and CR and the verify read level is denoted by LMV AV BV and CV.

A write is sequentially performed starting with memory cells closest to the source line. That is a write is sequentially performed starting with the memory cells connected to word line WL and ending with the memory cell connected to word line WL as shown in .

First the data for the first page to be written to word line WL is temporarily stored in data latch circuit XDL in the data storage circuit shown in .

Subsequently the data stored in data latch circuit XDL is written to the first page of each of the memory cells on word line WL.

Then the data for the first page to be written to word line WL is temporarily stored in data latch circuit XDL in the data storage circuit shown in .

Subsequently the data stored in data latch circuit XDL is written to the first page of the memory cells on word line WL.

Moreover the data for the second page to be written to word line WL is temporarily stored in data latch circuit XDL in the data storage circuit shown in .

Subsequently the data stored in data latch circuit XDL is written to the second page of the memory cells on word line WL.

When the data for the first and second pages is thus written such a threshold voltage distribution as shown in and is obtained.

Subsequently a write is performed on the first page on word line WL and then on the second page on word line WL.

On the other hand when data is read from a memory cell to which data has been written as described above soft bit read is performed. According to the present embodiment the soft bit read involves reading data with a sense timing different from the sense timing for the normal read.

During a read the corresponding bit line is supplied with a predetermined voltage for example 0.6 V Vfix a fixed voltage is denoted by Vfix and a selected word line is supplied with read level voltages AR BR and CR shown in . If the threshold voltage of the memory cell is lower than the voltage of the word line the memory cell is on and the voltage of the bit line is made low. If the threshold voltage of the memory cell is higher than the voltage of the word line the memory cell is off and the voltage of the bit line is made high.

Now the node in the sense amplifier unit shown in is precharged to make CLK high while setting signal XXL to for example 0.45 V Vth Vfix. Then when the potential of the bit line is low the node in the sense amplifier unit is made low. When the potential of the bit line is high the node in the sense amplifier unit is made high. Subsequently the clock signal CLK is made low and the voltage of the bit line is read.

Then during the first read from the first page first the potential of the word line is set to AR. If the threshold voltage of the memory cell is lower than AR the node in the sense amplifier unit is made low. On the other hand if the threshold voltage of the memory cell is higher than AR the node in the sense amplifier unit is made high. The result is held in one of data latch circuits ADL BDL and XDL for example ADL.

Subsequently during the second read from the first page the potential of the word line is set to CR. If the threshold voltage of the memory cell is lower than CR the node in the sense amplifier unit is made low. On the other hand if the threshold voltage of the memory cell is higher than CR the node in the sense amplifier unit is made high. The result is held in data latch circuit BDL.

The arithmetic circuit performs a logical operation for example an XNOR operation on the result of the second read held in data latch circuit BDL and the result of the first read held in data latch circuit ADL. As a result of the operation if the threshold voltage of the memory cell is lower than AR or higher than CR output is binary 1. If the threshold voltage of the memory cell is higher than AR and lower than CR output is binary 0.

ECC such as LDPC requires data referred to as a soft value and which is different from data read at the normal read level. shows relationships between read data and the read level during a soft bit read.

For the soft bit read the threshold voltages of memory cells are read at read levels AR d BR d and CR d set slightly lower than read levels AR BR and CR and read levels AR d BR d and CR d set slightly higher than read levels AR BR and CR and the results are subjected to an XNOR operation and then externally output.

Moreover an XNOR operation may be performed on the results of a soft bit read from the first page and the second page and the resultant one bit data may be externally output.

As shown in the range within which soft bit read data is 0 is not the main part of the threshold voltage distribution. Thus the data within this range is expected to be unlikely to be incorrect and ECC is carried out. In the conventional technique data is read from memory cells by three read operations at AR BR and CR respectively. However at each of the read levels a read operation must be performed at a read level set slightly lower than the original read level and at a read level set slightly higher than the original read level. Thus the conventional technique involves 3 3 9 read operations requiring much time for the read operations.

On the other hand for a memory cell with the threshold voltage thereof equal to read level BR d a read with the potential of the word line set to BR reduces the current in the memory cell. Thus as shown in the bit line is discharged slowly and thus a sense operation is performed with the time for the discharge of the bit line increased.

Specifically during a read after the discharge of the bit line is started signal HLL and the clock signal CLK are supplied three times signal HLL is supplied to the gate electrode of the transistor included in the sense amplifier unit shown in and the clock signal CLK is supplied to the capacitor . In accordance with this operation the potential of the node is held in the latch circuit . That is if the threshold voltage of the memory cell is much lower than the voltage of the word line the discharge time for the bit line is short. Thus when the first clock signal is supplied the potential of the node is low. Furthermore if the threshold voltage of the memory cell is slightly lower than the voltage of the word line the discharge time for the bit line is slightly short. Thus when the first clock signal is supplied the potential of the node fails to be made low. Then when the second clock signal is supplied the potential of the node is made low. Moreover if the threshold voltage of the memory cell is slightly lower than the voltage of the word line the discharge time for the bit line is slightly short. Thus when the second clock signal is supplied the potential of the node fails to be made low. Then when the third clock signal is supplied the potential of the node is made low. Furthermore if the threshold voltage of the memory cell is higher than the voltage of the word line the bit line is kept high. Thus even when the third clock signal is supplied the potential of the node is high. The potential of the node is held in the latch circuit .

Such a sense operation eliminates the need for three read operations with the level of the word line varied between one read level a slightly higher read level and a slightly lower read level. That is a read operation with the level of the word line unchanged and with the sense timing for the bit line changed exerts reading effects similar to those of a read operation at a plurality of levels.

First a second page read operation is performed. In the second page read operation data is read three times with the voltage of the selected word line fixed to for example BR and with the sense time for the bit line changed. That is as shown in the first sense the second sense and the third sense for the second page read allow three data to be read. The data resulting from the second sense at BR is the second page read data and may thus be externally output without change. A logical operation for example an XNOR operation is performed by the arithmetic circuit on data resulting from the first sense at BR and data resulting from the third sense at BR. These data are for example held in any of latches ADL BDL and XDL.

Then the first read operation on the first page is performed. In the first read operation on the first page data is read three times with the voltage of the selected word line fixed to for example AR and with the sense time for the bit line changed. That is as shown in the first sense the second sense and the third sense for the first read from the first page allow three data to be read. The data resulting from the second sense at AR is the first page AR read data. A logical operation for example an XNOR operation is performed by the arithmetic circuit on data resulting from the first sense at AR and data resulting from the third sense at AR. Moreover an XNOR operation may further be performed on the result of the XNOR operation at AR and the above described result of the XNOR operation at BR. These data are for example held in any of latches ADL BDL and XDL.

Finally the second read operation on the first page is performed. In the second read operation on the first page data is read three times with the voltage of the selected word line fixed to for example CR and with the sense time for the bit line changed. That is as shown in the first sense the second sense and the third sense for the second read from the first page read allow three data to be read. A logical operation for example an XNOR operation is performed by the arithmetic circuit on data resulting from the second sense at CR and data resulting from the second sense at AR. These data are read from the first page and are thus externally output.

A logical operation for example an XNOR operation is performed by the arithmetic circuit on data resulting from the first sense at CR and data resulting from the third sense at CR. Moreover an XNOR operation may further be performed on the result of the XNOR operation at CR and the above described results of the XNOR operations at AR and BR. These data are for example held in any of latches ADL BDL and XDL. The data are subsequently externally output.

An XNOR operation may be performed on the read data to obtain the same read data and soft bit data as the read data and soft bit data in .

The above described first embodiment enables a soft bit read by during a read applying the voltage at the predetermined level to the selected word line and changing the sense timing for the sense amplifier. The first embodiment thus enables a reduction in read time compared to a case where a soft bit read is carried out with the voltage of the word line changed.

The first embodiment uses one word line to carry out a soft bit read with one read data at two levels. However soft bit data may be read by for example using the normal read operation and changing the sense timing only for the soft bit read.

Furthermore reads at levels AR BR and CR and a soft bit read at the respective levels may be carried out at the level of one word line or several word lines.

When both the normal read and the soft bit read are carried out a slight deviation may occur between the normal read and the soft bit read but soft values including the deviation are subjected to ECC.

To allow the optimum read level to be determined a method has been proposed which involves changing the read level of the word line little by little searching for an end of the threshold voltage distribution determining the optimum read level and then performing a read operation. However this method disadvantageously takes a long time because the read level is changed little by little.

Thus as shown in the second embodiment uses as a word line potential one level or several levels based on the number of threshold voltage distributions and like the first embodiment changing during a read operation at each word line potential the sense timing of the sense amplifier with respect to the discharge time for the bit line to search for the end of the threshold voltage distribution. That is the potential of the bit line is detected with the sense timing changed and as shown in the end of the threshold voltage distribution is searched for based on the timing when the current starts increasing. The optimum read voltage is determined to be the searched for threshold voltage that is the threshold voltage plus an offset.

The second embodiment allows the optimum read level to be determined for each threshold voltage distribution. The second embodiment further eliminates having to perform a plurality of read operations with the word line level changed by setting a potential higher or lower than the potential of each word line. This enables the optimum read level to be searched for at high speed.

The read operation at a plurality of levels is effective for enabling the optimum read level to be determined to be the smallest value of the aggregated numbers of bit memory cells or the smallest value plus an offset.

The second embodiment changes the sense timing a plurality of times as shown in . An interval of time must be provided between the sense timings to achieve stability. This may hinder short timing intervals from being set.

The present embodiment searches for the end of the threshold voltage distribution. For example when the page is 16 KB in size the present embodiment enables the end of the distribution to be searched for based on for example 1 KB distribution data without having to search the distribution of all of 16 KB data. Thus the end of the threshold voltage distribution may be searched for by dividing a plurality of bit lines shown in or into a plurality of groups and varying the sense timing among the groups.

Furthermore a cell close to a word line drive circuit involves a shorter time until the sense timing is stabilized than a cell remote from the word line drive circuit because the corresponding word line rises earlier. Thus NAND units may be divided into a plurality of groups depending on the distance from the word line drive circuit to the corresponding bit line and the end of the threshold voltage distribution may be searched for each group. Of course also in this case the sense timing may be varied among the groups or the rise time of the word line may be set later than usual in order to change the sense timing.

Furthermore the second embodiment changes the read level of the word line little by little in order to determine the optimum read level and changes the sense timing a plurality of times to search for the end of the threshold voltage distribution. At this time data read at each read level of the word line or sense timing may be output to for example a controller located externally to the NAND flash memory so that the controller can process the data. However the time required to externally output the data may pose a problem.

In this case as shown in a cache function may be utilized such that while the results of a read at the first word line level or sense timing are being externally output a read is performed at the next second word line level or sense timing.

Alternatively externally outputting the read results may be avoided and a counter may be provided inside the NAND flash memory to count the read results inside the chip and to output only the count result externally to the chip.

Alternatively externally outputting the count result may be avoided and the count result may be held inside the chip so that the optimum read level can be automatically set based on the read results for a plurality of word line levels or sense timings.

Furthermore if the counter inside the NAND flash memory is used for counting the counting is carried out for every bit to every several bits and may thus take a long time.

In this case as shown in a cache function may be utilized such that while the read results are being counted at the first word line level or sense timing a read can be performed at the next second word line level or sense timing.

The third embodiment expresses the data corresponding to the main distribution a d g and j as two bits and expresses the other data as three bits or four bits enabling a reduction in total output data.

The first and second embodiments change the sense timing to obtain data corresponding to reads at a plurality of word line levels as shown in and respectively. However for the NAND flash memory it is known that the cell current Icell decreases with increasing number of erase and write times.

The reduced cell current can be increased by raising the level of the bit line during a read. Thus when the reduced cell current is to be avoided a region is provided in which the number of erase loops is stored for each block that is an erase unit. When erase is carried out the number of erases is stored in this region. Subsequently during a read or program operation the cell current can be increased by reading the number of erases stored in this region and changing the level of the bit line for a read and program verify read depending on the read number of erases.

Of course the level of the bit line for a read based on the number of erases can be used for a normal read and program verify read which are different from the soft bit read according to the first embodiment and the search for the end of the threshold voltage distribution according to the second embodiment.

While certain embodiments have been described these embodiments have been presented by way of example only and are not intended to limit the scope of the inventions. Indeed the novel embodiments described herein may be embodied in a variety of other forms furthermore various omissions substitutions and changes in the form of the embodiments described herein may be made without departing from the spirit of the inventions. The accompanying claims and their equivalents are intended to cover such forms or modifications as would fall within the scope and spirit of the inventions.

