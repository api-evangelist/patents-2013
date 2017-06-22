---

title: Static timing analysis methods for integrated circuit designs using a multi-CCC current source model
abstract: In one embodiment of the invention, a multi-CCC current source model is disclosed to perform statistical timing analysis of an integrated circuit design. The multi-CCC current source model includes a voltage waveform transfer function, a voltage dependent current source, and an output capacitor. The voltage waveform transfer function receives an input voltage waveform and transforms it into an intermediate voltage waveform. The voltage dependent current source generates an output current in response to the intermediate voltage waveform. The output capacitor is coupled in parallel to the voltage dependent current source to generate an output voltage waveform for computation of a timing delay.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08966421&OS=08966421&RS=08966421
owner: Cadence Design Systems, Inc.
number: 08966421
owner_city: San Jose
owner_country: US
publication_date: 20130910
---
The present application is a divisional of and claims the benefit of U.S. patent application Ser. No. 12 965 886 entitled MULTI CCC CURRENT SOURCE MODELS AND STATIC TIMING ANALYSIS METHODS FOR INTEGRATED CIRCUIT DESIGNS filed on Dec. 12 2010 by Vinod Kariat et al. now issued on Sep. 10 2013 as U.S. Pat. No. 8 533 644. U.S. patent application Ser. No. 12 965 886 is a divisional of and claims the benefit of U.S. patent application Ser. No. 11 849 254 entitled SENSITIVITY AND STATIC TIMING ANALYSIS FOR INTEGRATED CIRCUIT DESIGNS USING A MULTI CCC CURRENT SOURCE MODEL filed on Aug. 31 2008 by Vinod Kariat et al. now issued on Aug. 20 2013 as U.S. Pat. No. 8 516 420.

The embodiments of the invention relate generally to integrated circuit design software tools such as static timing analysis software tools and signal integrity analysis software tools for designing integrated circuits.

Electronic computer aided design ECAD software tools for static timing analysis STA may be used to estimate timing delays in an electronic circuit such as that found in an integrated circuit. However as process technology improves so that smaller transistor channels of 65 nano meters nm and 45 nm become available there is an increased need for even more accurate timing analysis. Additionally with the smaller geometries there may be a number of unknown effects to electronic signal propagation that may be considered which may not have been as severe with more relaxed process technology nodes.

In the following detailed description of the embodiments of the invention numerous specific details are set forth in order to provide a thorough understanding. However it will be obvious to one skilled in the art that the embodiments of the invention may be practiced without these specific details. In other instances well known methods procedures components and circuits have not been described in detail so as not to unnecessarily obscure aspects of the embodiments of the invention.

At the graph level of abstraction the highest level the software tool works with the entire circuit design as a design graph. The graph level abstraction propagates quantities or metrics of interest from the inputs of the circuit design to the outputs of the circuit design. For example an STA tool may propagate arrival times throughout the circuit design.

At the net level of abstraction the STA software tool calculates quantities of interest for each of the nets in the design. While doing an SI analysis an SI analysis software tool may calculate the crosstalk glitch induced on a specific net.

At the shape level of abstraction the software tools work with information from the actual chip layout. The information may include device sizes and interconnect parasitics for example such as can be obtained from a parasitic extractor.

In some embodiments of the invention an electrical calculation engine component or delay calculator is provided for the net level abstraction layer of electrical analysis software tools.

Referring now to a block diagram of a multi CCC gate delay calculator EOS is illustrated. The multi CCC gate delay calculator EOS may also be referred to herein as an electrical calculator. The delay calculator receives characterization data and a netlist to generate timing delays e.g. max timing delay min timing delay including process sensitivities. The characterization data may be part of a cell library of logic cells.

The delay calculator includes an application programming interface API an interconnect reducer analysis engine a gate simulation engine and a multi CCC current source model coupled together as shown.

The interconnect reducer analysis engine receives the netlist including a defined interconnect of standard cells to reduce it down to a simplified model for use with the gate simulation engine . The interconnect reduction and analysis engine reduces the extracted parasitic network down to a simplified load model. Typically the extracted parasitic network corresponding to an output net can be very large. Since only the inputs and outputs of the net need to be monitored the interconnect network may be reduced to create a smaller electrically equivalent representation speeding up delay calculations while preserving the input to output electrical behavior of the net.

The multi CCC current source model described in further detail below receives the characterization data and models single CCC and multi CCC standard cells in response to the type of standard cell in the netlist that is being analyzed in a given stage of a delay path. The multi CCC current source model describes the electrical behavior of a standard cell in an abstract fashion in order to speed electrical calculations such as delay calculations and noise delay calculations and sensitivity calculations. The parameters of the gate model are usually derived by a library characterization process such as described below.

The gate simulation engine calculates the output waveform at the output of a given gate in response to the input stimulus as well as the multi CCC current source model and its parameters. A simplified load model may be used to model the effect of the interconnect loading on the gate. A noise model may also be used to model noise from aggressors in the standard cell.

The parameters for each standard cell to fashion its corresponding gate model are typically stored in a standard cell library. The IC netlist design data is stored in some form in the host tool. One or more application programming interfaces API interact with the library and the design data to read information there from. Another one or more APIs may be used by graph level engines operating at the graph level on the netlist to determine delays along data paths for example to call the delay calculator and obtain the timing results of the calculations at each gate along a graphed path.

A current source model for a multi CCC structure described below may be used for both delay and SI calculations. Thus a single characterization process may yield a gate model for both delay and SI calculations.

The delay paths DP DPi may have various stages of single CCC and multi CCC standard cells. A first delay path DP includes a single stage Stage1. A second delay path DP includes two stages Stage1 and Stage2. A third delay path DP includes M stages Stage1 through StageM. An idelay path Dpi includes N stages Stage1 through StageN.

Referring now to a schematic diagram of an exemplary standard cell in a netlist is illustrated. This is the view seen by the electrical delay calculator working at a gate or net level abstraction layer. The standard cell includes a driver the RC interconnect network connected to the output of the driver consisting of one or more resistors and one or more capacitors the extracted parasitics associated with the output net Vo see coupled together as shown. One or more receivers are coupled to the output net Vo and may add to the extracted parasitics . An aggressor driver may generate an aggressor signal coupled into the interconnect network . An aggressor receiver may also influence the generation of the aggressor signal adding additional parasitic load to the network .

Without any aggressor driver or when node is quiet the delay calculator may generate a relatively smooth output waveform A on the Vo output signal that has a timing delay TD not affected by coupling noise or crosstalk . When aggressor driver and node are switching the delay calculator may generate a noisy output waveform B on the Vo output signal that has a timing delay TDN which is affected by coupling noise that may be greater than the timing delay TD without coupling noise. That is the switching of the aggressor driver may cause additional delay in the signal generated by the stage on the output net Vo .

The multi CCC current source model used in the delay calculator may also be referred to herein as a ViVo II model. The multi CCC current source model is capable of accurately supporting standard cells with both single channel connected components single CCC and multi channel connected components multi CCC . Channel connected components CCCs are found within standard circuit cells or simply standard cells of a standard cell library.

A single channel connected component single CCC includes transistors connected to each other by their drain and or source terminals between paths from the positive power supply VDD to the negative power supply VSS or ground. The boundary of a CCC is at a gate terminal or an input or output terminal of the standard cell.

Standard cells with multi channel connected components multi CCCs include a plurality of single CCCs coupled in series together at gate terminals between inputs and outputs of the standard cell.

The ViVo II multi CCC current source model i treats standard cells with either single CCCs or multi CCS as black boxes during characterization ii compacts the model which is independent of output load and much less dependent on the number of input slews to use during characterization and iii encapsulates internal waveform distortion and internal delay in multi CCC standard cells efficiently.

The goal of ViVo II multi CCC current source model is to characterize the gate s driving capability and to provide a simple abstraction which captures the output current waveform in the presence of multiple internal stages. The current through a single CCC can be described accurately based on a two dimensional DC current function F Vi t Vo t . For a multi CCC cell the current Io t waveform at the output of the standard cell is dictated by the instantaneous input voltage at the last CCC which we denote as V t . Thus the current through a multi CCC standard cell is a function of the instantaneous input voltage at the last CCC which can be denoted by I F V t Vo t . In order to find V t from Vi t a waveform transfer function can be used to map the input voltage transition to an intermediate voltage transition.

A multi CCC current source model therefore may consist of two major components i the dc current function modeling drawn current as a function of instantaneous input and output voltages and their time derivatives of the last CCC of the cell and ii a waveform transfer function defining the waveform at the input of the last CCC as a function of the waveform at the cell s input.

A one straightforward way to construct these two parts is to perform a series of spice simulations where the node which is the input of the cell s lass CCC is directly probed or stimulated respectively. However while this approach is feasible an understanding of the internal topology of the cell s circuit and a partition of the circuit into one or more CCCs must be performed. Instead the embodiments of the invention treat a standard cell as a black box without having to understand the internal topology of a circuit and partition it into CCCs. Thus the construction of the two components of the model is done through fitting the results of a series of spice simulations where excitation and probing points are only the standard cell s interface e.g. input output pins.

The first part is an internal waveform transformation function which transforms the input voltage V t into the intermediate voltage V t by Equation 1 as follows 1 

Note that the intermediate voltage Vc t models a delay and distortion of the input signal transition as it propagates through a standard cell s circuit up until the input to the last CCC. Fitting techniques may be used to map the input signal to the intermediate voltage signal V t .

The second part is a voltage dependent current source which characterizes the driving CCC . It consists of a voltage dependent current source I F V V which gives the driving current for any Vand Vvalue and their derivatives 

In Equation 2 Fis a DC component of the current source defining the current value based on the values Vand V. The second and third terms in Equation 2 model the dynamic current due to Miller effect from input to the output of the last CCC of the cell and output pin capacitance of the cell. The coefficients of the two latter terms are nonlinear Miller and output pin capacitances which in general depend upon voltages Vc Vo. However since the contribution of the last dynamic term in Eq. 2 is usually small characterizing the Cfor the initial input voltage Vi t 0 suffices to provide sufficiently accurate results.

In Equation 3 F is a normalized time transfer function time versus time with time normalization being defined by

As shown by the intermediate voltage Vc t versus time chart of is the starting time of the transition in the intermediate voltage V t and T is the transition period of the intermediate voltage V t .

The function F captures the non linear waveform shape change from V t to V t . F and are all functions of the slew rate change in voltage over time of the input voltage V t and are stored in tables indexed by . illustrates an exemplary table of values for and as a function of a reference slew rate a fast slew rate and a slow slew rate of the input voltage V t . illustrates an exemplary table of values for F as a function of a reference slew rate a fast slew rate and a slow slew rate over the normalized time which varies from 0 to 1.

In its application the multi CCC current source model captures the slew rate from the voltage input waveform V t which is then used to look up the corresponding values for T and F V from look up tables such as the tables illustrated in and respectively. The model then applies the voltage transformation equation Eq. 3 to map the voltage points on V t to V t to convert an input waveform V t of slew rate to the intermediate voltage waveform V t in one embodiment of the invention. In another embodiment of the invention a lookup table is used to convert the waveform V t of slew rate to the intermediate voltage waveform V t .

With the intermediate voltage waveform V t the output current waveform may be computed by using the intermediate voltage waveform V t as the dependent input of the current source model I V V . The model may use a table to store I V V such as illustrated by which is indexed by both Vand V. To compute output current at time tn given a particular Vand Vat time t the model may first find the nearest voltages in the table and then perform a two dimensional interpolation to approximate the actual output current at Vand V. The model may also look up Cgiven Vfrom another table such as illustrated in . With the values of Iand Ccomputed at time t we can compute the value of Vand move on to the next time point t at which we look up Iand Cagain using Vand Vat time t. This process repeats until the whole output waveform is computed.

The ViVo II multi CCC model for gates is characterized from a blackbox view of a standard circuit cell. To characterize a ViVo II multi CCC model the voltage and current waveforms at inputs and outputs of the standard cell are observed. Characterization starts at block and jumps to block .

At block the output current Iis characterized for the driving stage of the multi CCC current source model. The flow chart of illustrates the characterization of the output current of the multi CCC standard cell in greater detail.

To characterize the driving stage I V V transient simulations with a SPICE transistor circuit simulator such as Spectre software by Cadence Design Systems Inc. are used to switch the input to the standard cell with its output voltage Vbeing fixed.

At block while holding the output voltage Vfixed a spice transistor simulation is run on the multi CCC standard cell.

At block one input of the multi CCC standard cell is switched using an input signal with an initial reference slew rate.

At block a determination is made as to whether or not the output voltage was set to the power supply voltage Vdd. If so the process ends at block . If not the process goes to block .

At block the output voltage is incremented to a new value and the process returns to block to determine the output current for the new fixed value of output voltage V.

In the case of standard cells with only one CCC performing a DC analysis by sweeping Vand Vis sufficient to find I V V . However for a multi CCC standard cell I V V a DC analysis may not be used since the input voltage Vdoes not equal the intermediate voltage Vc.

At block the voltage transform function V t of the multi CCC standard cell is characterized. The flow chart of illustrates the characterization of the voltage transform function V t of the multi CCC standard cell in greater detail. Characterizing the functional in Equation 1 requires extra simulations using different input slews than a reference slew rate .

At block of the input signal slew rate is set to a first slew rate that is different form the reference slew rate. For example the input slew rate may be changed to a slow slew rate .

At block the output voltage Vof the multi CCC current source model is fixed to of Vdd for a rising output and of Vdd for a falling output.

At block with the output voltage fixed SPICE transistor circuit simulations are run with the multi CCC current source model.

At block one input of the multi CCC standard cell is switched using the input signal with the differing slew rate than the reference slew rate.

At block the output current Iis measured and results may be tabulated. illustrates an I V V x V waveform which is obtained by changing input slew rate to where x is a fraction of for rising output and for falling output.

At block the output current waveform is compared with the input signal waveform to determine the extra delay time in the transition periods to extract and Tparameters for example.

From I V V x V waveform curve we observe that the output current waveform incurs an extra delay of and its transition period stretches from Tto Tcompared to the original reference current waveform I V V x V . Tand are stored in the table of for example for the input slew as part of the parameter for characterizing the functional . Moreover we can capture the non linear shape difference between I V V x V and I V V x V by normalizing the time axis

At block the output I V V x V waveform curve is normalized using and Tparameters. The reference waveform curve I V V x V is normalized using its and Tparameters. The normalized output waveform curve and the normalized reference curve are aligned together and equal current time points are recorded for each output current for their respective slew rates such as illustrated by . The equi current normalized time information further simplifies the computations and reduces the amount of information that need be stored to model a multi CCC standard cell. The equi current normalized time information is used to further transform the output waveform be it an output current waveform Ior an output voltage waveform V.

Referring now back to at block a determination is made if all desired slew rates differing from the reference slew rated have been simulated. If so the process goes to block and ends. If not the process goes to block .

At block the input signal slew rate is set to the next slew rate differing from the reference slew rate. The process then returns to block where the characterization process is repeated.

The current table of is characterized for at least one input voltage slew rate a reference slew rate or . In another embodiment of the invention it is characterized for two slew rates a fast slew rate or fast and a slow slew rate or . In another embodiment of the invention it is characterized for at least three slew rates the reference slew rate or the fast slew rate or and the slow slew rate or . The more characterization data the better the interpolation accuracy with respect to input slew.

To adapt the characterized output currents to input voltage signals with different slew rates the values in the current table are adjusted. With a multi CCC standard cell there are first and second order adjustments to be made. With a single CCC standard cell a first order adjustment for a different slew rate may only be made.

Referring now to a first order only transformation applying to the first order of the voltage input waveform Vi into an output current waveform Io is illustrated. A reference voltage input waveform was previously used to generate the tabulated output current waveform . A voltage input waveform with a new slew rate indicated by the slope and a delayed start indicated by the offset from time zero is coupled into the single CCC standard cell. The new voltage input waveform results in a new output current waveform . The output current waveform is the result of a SPICE transistor circuit simulation for comparison with the output current waveform of the multi CCC model.

A first order output adjustment to the output current waveform is due to the change input slew rate illustrated by the slope of waveform and the delayed start of the input illustrated by the time offset between waveforms and . The change in slope of the input waveform illustrated by the difference between waveforms and results in a change in slope in the output waveform as illustrated by the difference between output waveforms and . The delayed start in the input waveform illustrated by the difference between waveforms and results in a delayed start in the output waveform as illustrated by the difference between output waveforms and . The change in slope is established by a stretch parameter T. The change in start time is established by a shift parameter .

A second order output adjustment to the output current waveform is the result of the extra gate stages in a multi CCC standard cell. The new voltage input waveform is coupled into a different gate than that of the last driving stage of a multi CCC standard cell. The second order adjustment to the output current waveform is illustrated by the difference between output waveforms and . The second order output adjustment is modeled by a time transformation function that is responsive to the new input slew rate. If the standard cell is a simple single CCC standard cell the time transformation function is u where is the normalized time with respect to the current table and u is the normalized simulation time. That is there is no second order output adjustment to be made to a simple standard cell with a single CCC. The first order output adjustment may be made to a simple standard cell with a single CCC.

Referring now to the characterization of a time transformation function is now described. A voltage input waveforms Vand its respective output current Iover time are plotted in the left chart. Output current waveforms Io normalized for time are plotted in the right chart.

From the plots of voltage input waveforms Vi with different slew rates and their respective output current Io the shift parameters and the stretch parameters T are first measured. The shift parameters and the stretch parameters T for each voltage input waveform and its respective slew rate may be tabulated such as illustrated in .

The output current waveforms Io are aligned and normalized for time over U from zero to one such as illustrated in the right chart of . Three output current waveforms Io A C are illustrated in the right chart of with slew rates and respectively. A plurality of equi current points Iare selected and their normalized times U for all of the output current waveforms Io A C with their respective slew rates are recorded into a table such as the table illustrated in .

For example consider the equi current point Iillustrated in the right chart of that intersects the waveforms A C at points A C respectively. At point A on waveform A the normalized time is Z. At point C on waveform C the normalized time is Y. At point B on waveform B the normalized time is X. These normalized time points are tabulated in .

As another example consider the equi current point Iillustrated in the right chart of that intersects the waveforms A C at points A C respectively. At point A on waveform A the normalized time is Z. At point C on waveform C the normalized time is Y. At point B on waveform B the normalized time is X. These normalized time points are also tabulated in . Additional equi current points are selected and their respective normalized times for each waveform and slew rate are tabulated. The greater the number of equi current points selected the better the accuracy of the model. Additionally the greater the number of output currents characterized for different input slew rates the better the accuracy of the model.

Referring now to the equi current values of the output current waveform with their respective slew rates can be inverted and normalized with respect to time in order to form time transformation curves illustrated in . That is illustrates time versus time plots plotted from . Time transformation waveforms with respective slew rates of and are illustrated in .

With curves and a new intermediate voltage waveform with respect to a new slew rate may be readily interpolated by applying the second order adjustment. The interpolation is to construct an intermediate waveform for a multi CCC standard cell to assist in output current look up during simulation. The curves and of may be stored in a table such as illustrated in as piece wise linear time versus time curves.

The characterized time transformation curves of for the slew rates and may be saved and used as part of the multi CCC current source model. After determining a new slew rate of an input voltage waveform to a multi CCC standard cell the characterized time transformation curves of for the slew rates and respectively may be utilized to interpolate a new time transformation curve associated with the new slew rate of the input voltage waveform.

At a normalized time of uin curves and have normalized equi current values of Yand Z respectively. The new transformation curve has an interpolated value of Wat a normalized time of X. Equivalent ratios may be set up to interpolate all values of W along the curve as follows 

for all values of normalized time u and each respective value of y and z. The equation may be solved for the value w along the curve as follows 

Referring now to the left graph illustrated in the input voltage waveform is then normalized by shifting the starting time point to zero at the origin and scaling the time axis so that the normalized input waveform V goes from the normalized time of zero to one.

Using the new time transformation curve new time points are generated from the new input voltage waveform to begin its transformation into the intermediate voltage waveform V as illustrated by the right graph in .

Using the new slew rate values for a new shift parameter and a new stretch parameter may be interpolated from a parameter look up table such as the table illustrated in . A pair of parameter values and with respective slew rates and around the new slew rate are chosen. A new shift parameter may be interpolated from the equivalent ratios in the following equation 

A pair of parameter values Tand Twith respective slew rates and around the new slew rate are chosen. A new stretch parameter Tmay be interpolated from the equivalent ratios in the following equation 

Referring now to the intermediate voltage waveform V is further transformed by the stretch parameter value Tby stretching it into the intermediate voltage waveform V . The intermediate voltage waveform V is finally transformed by the shift parameter value by shifting it into the final intermediate voltage waveform V.

At block the parasitic capacitance of the standard cell for the multi CCC current source model is characterized. The flow chart of illustrates the characterization of the parasitics of the standard cell in greater detail.

At block all the inputs of the multi CCC standard cell are set to a constant logic level input voltage. At block a voltage source is coupled to the output of the multi CCC standard cell. With the input voltage Vi being held constant the intermediate voltage level Vc is also held constant.

At block while holding the inputs to the multi CCC standard cell fixed a SPICE transistor circuit simulation is run of the transistors in the given multi CCC standard cell.

At block to characterize C V the voltage source at output applies a voltage ramp with a slew rate at the output of the multi CCC standard cell.

At block the current I going through the voltage source at the output of the multi CCC standard cell which asserts the voltage ramp is measured.

At block the expected initial output current I V t 0 V may be looked up from a current table such as the table illustrated in given that we set the output voltage Vand we estimated the intermediate voltage V t 0 at time zero.

Referring now to and a method of characterizing the miller capacitance Cor C of the multi CCC current source model is now described.

At block all the inputs but one input of the multi CCC standard cell are set to a constant logic level input voltage. They may be set to a constant high logic level by coupling to the positive power supply voltage VDD or a constant low logic level by being coupled to ground VSS.

At block a fixed voltage source Vis coupled to the output of the multi CCC standard cell . The fixed voltage source Vmay be fixed to a constant positive power supply voltage level VDD in one embodiment of the invention or a constant zero volts in another embodiment of the invention.

At block while holding the output voltage of the multi CCC standard cell fixed to the fixed voltage source V a SPICE transistor circuit simulation is run of the transistors in the given multi CCC standard cell.

At block to characterize the miller capacitance C a voltage source applies a voltage ramp with a fast slew rate at the input to the multi CCC standard cell . The slew rate of the voltage ramp should be as fast as possible for best results.

At block the output current I going through the fixed voltage source is measured and plotted over time in response to the voltage ramp at the input of the multi CCC standard cell.

At block the miller current Ior Iis determined and a time delay S in the change of the output current is also determined from the plotted output current. The time delay S is used as the change in the time period for the voltage decay over the miller capacitor.

Referring now to plots of exemplary waveforms for the input voltage ramp Vi intermediate voltage Vc and the output current Iare illustrated in the case that the fixed voltage source is set to the positive power supply voltage VDD. illustrate plots of exemplary waveforms for the input voltage ramp Vi intermediate voltage Vc and the output current Iin the case that the fixed voltage source is set to the zero volts.

In either case the miller current is a current that results because the miller capacitor resists an instantaneous change in voltage. The miller current flows from the input to the driver stage of the multi CCC current source model through the miller capacitor to the output node Vo. The miller current is the instantaneous change in current illustrated in as a result in the initial change in the intermediate voltage Vc in . The driver stage of multi CCC current source model has yet to turn on and provide a current. Thus the measured output current is the miller current prior to the driver stage turning on and driving a current into the output node.

The current through a capacitor is known to be proportional to the product of the capacitance and a time derivative of the voltage. The latter can be approximated by a change in voltage divided by a change in time 

At block the change in voltage over time in the miller capacitor is estimated using the time delay S. That is dV dt is congruent to the positive power supply voltage VDD divided by the time delay S or VDD S.

At block the miller capacitance is calculated using Eq. 12 and the measured miller current Im through the miller capacitor Cm and the change in voltage over time VDD S across the miller capacitance. After the miller capacitance is determined for the given multi CCC standard cell it is stored with the other parameters of the multi CCC current source model.

After the miller capacitance is determined the characterization of the miller capacitance ends at block .

Generally the multi CCC current source model is efficient in the runtime that is required to characterize the model as well as the amount of data storage need to preserve its parameters. The multi CCC current source model can achieve sufficient accuracy by keeping seven V values and twenty time samples of I V t V for each Vin the I V V table of . C V may require only seven Vvalues in its table of . It is also sufficient to store values of T and F for three different input slew rates a reference input slew a slow input slew and a fast input slew that may be stored in tables such as tables illustrated in . Characterizing these parameters may take about ten transistor circuit simulations using a transistor circuit simulator such as Cadence Design Systems Inc. s Spectre transistor circuit simulator compared to about eighty transistor circuit simulations that may be required for other gate models.

The embodiments of the invention may be used with or in a static timing analyzer for analyzing the timing of an integrated circuit.

Referring now to and a timing analysis of the circuit netlist of may be made starting at block in which jumps to block .

At block a register transfer level netlist is analyzed to partition a circuit into stages. The stages are further levelized to perform static timing analysis. Each stage may include one or more standard cells and associated interconnect.

At block in each stage one or more standard cells are modeled using a multi CCC current source model. If a standard cell is a single CCC standard cell the multi CCC current source model may still be used with the voltage transform function having a unity value of one such that the intermediate voltage is the input voltage.

At block in each stage the coupled RC interconnect network may be generated from a parasitic extraction after a circuit is laid out or the parasitics may be generated in response to the netlist after logic synthesis and possibly a floor plan of the functional blocks of the circuit if available. The parasitics of the coupled RC interconnect network in each stage are modeled using a reduced order model ROM .

At block a determination is made as to whether or not the system is in a concurrent calculation mode. A concurrent calculation mode includes a noise or signal integrity analysis as part of the multi CCC current source model. If not the process goes to block . If so the process goes to block .

At block the delay in each stage is computed using the modeled current of the multi CCC current source model and the modeled parasitics of the reduced order model ROM . The process then goes to block .

At block for each stage assuming concurrent calculation mode the response on the output of each stage due to each noise aggressor transition is computed and tabulated. The process may then go to block .

At block for each stage the combined response on the output of each stage in response to all noise aggressor transitions may be computed and tabulated.

Next at block for each stage the delays and the sensitivities to all noise aggressors and process variations are computed via simulation using the multi CCC current source model and the reduced order model ROM for the associated RC interconnect. The receiving gates in each stage are modeled using constant capacitors. The process then goes to block .

At block the calculated delays of each stage are used by a static timing analysis tool to determine the critical delay paths. The process goes to block and ends.

The multi CCC current source model may be used to perform timing delay calculations on a stage of a circuit in the presence of process variations. Process variations can effect the interconnect as well as the transistors used in the logic cells of a standard cell library. For example a metallization process is used to manufacture the interconnect within an integrated circuit. During the metallization process the sheet resistance may vary in the metal as well as the width and thickness of metal lines due to process variations and change the impedance.

Referring now to a circuit stage is illustrated including a driver connected to a plurality of receivers A N through an interconnecting net . The stage is modeled by a circuit consisting of the net s parasitics and its driver and receivers A N. For the sake of simplicity a net is assumed to have a single driver as shown. However the methods may be adopted with modification for the general case of multiple driving stages.

For calculation of STA delays at the driver output X and receiver inputs Y YN A N the transition at the driver input is required. Correspondently the delay calculator computes voltage responses at the so called probing points Yd Y YN A N in FIG. nodes which are connected to output of the driving gate and inputs of receiving gates respectively.

For calculation of the responses at the probing points Yd Y YN A N a state space formulation is used. A vector of voltages V v . . . v is formed at nodes of the RC network in the stage . The vector V of voltages may be formed so that vdenotes v a voltage on the output node from the driver as shown in and v . . . vdenote respectively voltages at input nodes of the receiving gates V . . . V.

To enable an efficient and accurate delay calculation the nonlinear parts of the stage are approximated using appropriate models. The driver is modeled with the multi CCC current source model described previously. The driver includes a voltage controlled current source and a capacitance C. Calculation of responses at the stage s probing points is performed after responses are computed at the previous stages and parameters of input transitions such as slews and delays are determined at the inputs of the stage being analyzed.

During calculation of responses it is assumed that voltage at one of the inputs of the driving gate is transitioning either rising or falling and this causes some transition at the nodes of the driven interconnect. We can assume that for each input pin of the driving gate direction of transition at the input and output pins and logical values at other input pin there exists a unique current source model describing current at the output pin as a function of voltage transitions at the switching input and output pins I I v t v t . However since transition at the inputs of the driving gate are known at the time of delay calculation at the stage the driver current source can be represented as a function of time and voltage at the output node of the driving gate I I t v t .

For a given switching input pin directions of transitions at the input and the output of the driving gate and logical values at the other inputs the current drawn by the driver is thus a known function of time t and voltage vand may be designated as I t v .

Each of the receivers or receiving gates A N may be modeled using a constant input capacitor C extracted from a standard cell library for the respective type of cell or gate.

Kirchhoff s current law KCL equations regarding the principle of conservation of electric charge may be applied to describe the stage as follows 

In the left hand side of Eq. 13 C is a capacitance matrix G is a conductance matrix and v is the voltage vector. The vector y v v . . . v denotes voltages at the probing points which include output of the driver and inputs to the receiving gates of the M receivers A N as shown in .

In the right hand side of Eq.13 14 the matrices B and L are respectively input and output position matrices and Iis the current drawn by the driver current source.

The set of equations 13 14 is sufficient to calculate responses at the probing points which may be achieved via simulation of the circuit using numerical integration of the governing equations 13 14 . Note that the current source model for the driver is different for different input switching pins input and output direction transition and values at side other inputs. That is for each such configuration of the driver a separate simulation is required.

Since RC interconnect may include hundreds or even thousands of resistors and capacitors it is usually expensive to integrate Eqs. 13 14 with highly sparse matrices G C. In order to make simulation more efficient a model order reduction MOR may be performed to generate a load model a reduced order model ROM of the RC interconnect. Model order reduction is generally described in U.S. Patent Application Publication No. 2006 0095236A for U.S. patent application Ser. No. 10 932 406 filed on Sep. 2 2004 by Joel R. Phillips and incorporated herein by reference. The model order reduction results in much more compact state space equations with very little loss of accuracy. The reduction produces a reduced order model ROM for the interconnect parasitics which also includes receiver pin capacitors. After the reduced order model ROM for the interconnect parasitics is generated the state space equations can be formulated in this conventional form 

Note that matrix C in Eq. 16 is unrelated to the capacitance matrix used in Eq. 13 . The vector x is the state vector which usually has much smaller dimension that original vector of node voltages. Vector y is the vector of probing points as before and u in the right hand side of Eq. 15 is the driver current I. The input to the ROM which is the node where driver is connected to and the outputs which are nodes where receiving gates are connected to are often referred to as port and taps respectively. Matrices E A are of much smaller size than before reduction.

Generally both linear and nonlinear elements of a circuit are functions of process parameters. Let a vector X with n 1 . . . P denote a vector of interconnect and cell process parameters. It is assumed that the capacitance and the conductance matrices of the original state space system C G and driver current source I t v are known functions of process parameters. Likewise the state space matrices of the reduced system A E are also functions of process parameters. Moreover the capacitance matrix C the conductance matrix G the driver current source I t v of the original stage space system and the state space matrices A E of the reduced state space system can also be modeled so that the effects of variation of temperature and variation in power supply voltage Vdd can be accounted for.

For a fixed vector of process parameters the port and tap responses can be determined by solving both of the equations 5 6 . This may be done for instance using trapezoidal integration method. Since excitation u is a nonlinear function of the port voltage Newton Raphson iterations are used at each time step. This means that the responses and correspondent delays are implicitly functions of process parameters.

The delay calculation problem of the stage may be formulated as a problem of finding the port and tap responses y and the correspondent delays and slews as functions of vector . Some delay characteristics are of particular interest in the presence of process variations. The timing delay of the stage the stage delay is of interest at a particular point of the subspace of process parameters referred to as a process parameter vector PPV . The maximum and minimum values of the stage delay within a certain range subspace of process parameters may be of interest. Moreover the sensitivity of the stage delay with respect to process parameters at a particular process parameter vector may be of interest.

In the presence of large variations in process parameters one approach to model the stage delay is to choose a representative set of process parameter vectors often referred to as set of process corners and perform a delay calculation at each process corner. The selection of the corners is usually done in such a way as to cover the feasible space of process variations and ensure that the maximum and or minimum timing delays are reached at least one of the chosen corners. However with a large number of process parameters the number of corners to ensure a conservative analysis may be too high for the process corner approach of analyzing timing delays to be practical.

However all or several of the process parameters may vary within a relatively small range. In this case an efficient technique to model the timing delay with process variations is as a linear function of the process parameters. This approach is based on a sensitivity analysis. The sensitivity of delay is defined as a derivative of the timing delay with respect to a varying parameter. Since the behavior of timing delay in a sufficiently small vicinity of a chosen process parameter vector is linear with respect to the process parameters knowing the delay and its sensitivities at a process parameter vector provides a good model for the delay in the vicinity of the process parameter vector.

An algorithm for the calculation of the stage delay and delay sensitivity at a given process parameter vector is now described with reference to .

A state space system for the voltage responses at the output port of the driver and receiver inputs A N of the receivers A N in the presence of process variations may be written as

Since both matrices and excitation vector depend on process parameter vector the solution must depend on as well.

In order to find sensitivity of the stage delay with respect to process parameters at a given process parameter vector the state space system as well as responses are expanded in Taylor series around some nominal value of the process parameter vector .

Assuming that small variations of process parameters around their nominal values cause the variation of responses to be also small the circuit responses in the vicinity of the nominal vector of process parameters can be sought in the form of a Taylor series with respect to the deviation of the process parameter vector from its nominal value X . . . 19 . . . 20 . . . 21 . . . 22 

In equations 19 22 the zero order terms A E u x correspond to nominal matrices excitation and states which are taken at . In this approach which uses Z formulation the matrices B and C do not depend on process parameters and therefore do not need to be expanded. The first order terms are summations of a product of the deviation of process parameter from its nominal value and the sensitivity or partial derivative of the correspondent function with respect to this process parameter e.g.

Before formulating the first order problem allowing sensitivity calculations notice that since u I t v depends on process parameters via two latter arguments the sensitivity with respect to w.r.t. is

The two components in the first order correction of driver current are due respectively to variation of the gate driving strength itself and due to change in driver output response.

In equation 27 yis first element of vector y which is the sensitivity of driver output response w.r.t. parameter and it can be expressed via xusing Eq. 28 .

Equations 27 28 are linear with respect to sensitivity values. All quantities in the right hand side of equations 27 28 are known since they depend on the nominal response which is found from equations 23 24. The sensitivities can be calculated from equations 27 28 using different numerical methods for solving a set of linear ordinary differential equations. For instance a trapezoidal numerical integration method can be used to calculate the sensitivities using equations 27 28.

In another embodiment of the invention the total delay under nominal conditions may initially be computed. The non linear circuit equations for the stage including current source model for the driver Iand ROM for interconnect may be formulated in their parameterized form with respect to the process parameter vectors. The port and tap responses as well as the equations and the driver current equations may be expanded around the nominal values of process parameter. The sensitivities of the responses and hence delays to process variations may be determined from a set of linear equations 27 28 obtained by the application of a perturbation method to original equations 17 18 .

Digital electrical analysis engines are usually compared against a SPICE like transistor level circuit simulator such as Cadence Design Systems Inc. Spectre transistor level circuit simulator product. A number of tests have been performed to validate the accuracy of the multi CCC current source model. A comparison was made on a stage by stage basis. The basic structure of all netlists is a three stage gate chain. The test suite has thousands of combinations of input slews drivers interconnect topologies lengths and sizes. To validate nominal delay noise coupling capacitors of the interconnect if any are coupled to ground. Each of the cells in the standard cell library such as a commercial 90 nm technology cell library is completely characterized for the multi CCC current source model beforehand. The library models for the electrical simulation engine may also be fine tuned to achieve greater accuracy.

Referring now to voltage waveform results of a static timing analysis using the digital delay calculator with a multi CCC current source model and transistor level simulations generated by Cadence Design System Inc. s Spectre transistor level simulator are plotted for comparison.

The test case used to generate the plots of was three stages of AND gates coupled in series together with an interconnect network with a maximum span of 200 microns m . An AND gate is a multi CCC standard cell with its driver stage being an inverter. The ramp input voltage waveform V t coupled to the input of the multi CCC standard cell in the first stage had a slew rate of 100 pico seconds ps . The other curves plotted in are pairs of curves both generated at the following stages input voltage V t at stage 2 input voltage V t at stage 3 and output voltage V t at the output port of stage 3. The calculated results from the static timing analysis using the digital delay calculator and the simulated results of the transistor level simulator are substantially similar such that the pairs of curves are indistinguishable from each other at each stage.

Referring now to a plot of timing delays calculated with the delay calculator EOS versus those simulated with a spice transistor level simulator such as Spectre simulator by Cadence Design Systems Inc. is illustrated. A forty five degree line illustrating a perfect match is also drawn to see how well the static timing results match that of the transistor level simulated results. As shown in the timing delay determined using delay calculator EOS with a multi CCC current source model substantially matches the timing delay simulated by the Spectre transistor level simulator in most cases.

While the output results of the static timing analysis may be substantially similar there may be other cases where a lesser level of accuracy may be acceptable. Depending on the usage scenario different applications may need different levels of accuracy. For example during cell placement we may want to perform delay calculations using lookup models without considering any signal integrity issue. However during sign off of a integrated circuit design for manufacture it may be desirable to calculate the timing delays with noise effects using the fully extracted parasitics. For some critical paths the most accurate delay calculations may be desirable with results substantially similar to that achieved using a SPICE transistor level simulation. The software infrastructure of static timing analyzer EOS with the multi CCC current source model can support such different usage scenarios.

When implemented in software the elements of the embodiments of the invention are essentially the code segments to perform the necessary tasks. The program or code segments can be stored in a processor readable medium or transmitted by a computer data signal embodied in a carrier wave over a transmission medium or communication link. The processor readable medium may include any medium that can store or transfer information. Examples of the processor readable medium include an electronic circuit a semiconductor memory device a read only memory ROM a flash memory an erasable programmable read only memory EPROM a floppy diskette a CD ROM an optical disk and a magnetic disk. The program or code segments may be downloaded via computer networks such as the Internet Intranet etc.

The embodiments of the invention are thus described. While embodiments of the invention have been particularly described they should not be construed as limited by such embodiments. For example the delay calculator s primary use is as a common timing computing engine to perform static timing analysis. However its software infrastructure allows it to be portable and used with different design databases timing library environments and ECAD design tools. Instead the embodiments of the invention should be construed according to the claims that follow below.

