---

title: Method for discriminating between military operations in urban terrain (MOUT) targets
abstract: A method of autonomously tailoring a detonation delay time of a gun launched munition by utilizing target impact signatures including but not limited to a MOUT target set; earth and timber bunker, triple brick wall, double reinforced concrete, and light armor. While the present method is applicable to countless munition configurations, the projectile architecture used to develop the discrimination algorithm includes a tandem warhead configuration. Upon target impact the forward warhead detonates and pre-damages the target to allow the rear warhead to break through. Target impact data is used to set a detonation delay in the rear warhead providing increased performance behind the target.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09441928&OS=09441928&RS=09441928
owner: The United States of America as Represented by the Secretary of the Army
number: 09441928
owner_city: Washington
owner_country: US
publication_date: 20130926
---
This application claims the benefit under 35 USC 119 e of U.S. provisional patent application 61 816 845 filed on Apr. 29 2013 titled Method For Discriminating Between Military Operations In Urban Terrain MOUT Targets which is incorporated by reference in its entirety.

The invention described herein may be manufactured and used by or for the Government of the United States for governmental purposes without the payment of any royalties thereon.

The present invention generally relates to the field of munitions such as explosive projectiles. Particularly the present invention relates to a target discriminating munition for use against military operations in urban terrain MOUT targets including but not limited to earth and timber bunkers triple brick walls double reinforced concrete and armored targets. More specifically the present method relates to an algorithm for use for example with a dual warhead design and is capable of autonomously discriminating between and defeating numerous targets including a MOUT target set.

The survival of a military unit depends to a great extent on its ability to defeat enemy armor and field fortifications. Substantial improvements in the effectiveness of armor and fortifications to withstand exploding munitions has occurred. Reinforced structures are generally designed to deflect the explosive force of a munition away from a target or to absorb part of the destructive force as a way to dissipate the damaging effects of the munition. Munitions with a delayed warhead detonation after target impact have increased effectiveness in damaging or destroying the target.

The delayed timing of an exploding munition after impact may be required for several reasons. The purpose of the delay is to produce the greatest target effect or efficiency from the warhead. Some munitions penetrate the target without detonating and then function once inside. Other munitions utilize timing between multiple warheads to create the greatest effect against armor.

In addition to delayed timing target discrimination is an important factor to produce the optimal penetration. Target discrimination has been under continuous development. One such development includes a bunker defeat munition BDM which is a shoulder fired munition that is capable of discriminating between two targets. These targets are classified as either soft or hard i.e. sand or armor to set a detonation delay time.

Reference is made to U.S. Pat. No. 8 091 478 that describes an exemplary BDM discrimination method and which is incorporated herein by reference. The BDM discrimination algorithm samples the state of an acceleration switch during a target impact. Following a predetermined sample period a circuit determines if the majority of samples were logic high or logic low and uses that determination to set an appropriate detonation delay time. The BDM algorithm uses a binary signal from the switch to decide between two outcomes or two target types.

Although this BDM technology has proven to be useful it would be desirable to present additional improvements. In particular it would be useful to autonomously discriminate between more than two discrete target media in order to increase munition effectiveness against a wide range of targets.

There is therefore a need for a target discriminating algorithm which can be implemented into a munition for use against military operations in urban terrain MOUT targets including but not limited to earth and timber bunkers triple brick walls double reinforced concrete and armored targets. The need for such a target discriminating algorithm has heretofore remained unsatisfied.

The present invention addresses the challenges of the conventional target discrimination method for munition fuzing and presents a new target discrimination method for use against multiple discrete targets including but not limited to earth and timber bunkers triple brick walls double reinforced concrete and armored targets.

In one exemplary embodiment the autonomous target discrimination algorithm is used in conjunction with a dual warhead munition architecture. This dual warhead configuration includes a forward precursor warhead and a secondary bash through warhead.

The fuzing system of the dual warhead munition includes at least one fuze per warhead. In the description of the exemplary embodiment a precursor fuze is associated with the forward precursor warhead and a bash through fuze is associated with the rear bash through warhead.

Upon projectile impact with the target the precursor fuze causes the precursor warhead to detonate. The precursor warhead detonation and subsequent bash through warhead impact event provide a stimulus to the bash through fuze. This stimulus is used by the bash through fuze to set a detonation delay time unique to the target impact event.

The dual warhead architecture contributes to a series of stimuli that can be used to build capability into the fuzing system. The first recognizable impulse is the initial impact of the projectile precursor warhead on the target. This initial impact event is present whether the munition architecture contains a single or dual warhead.

The second event is the detonation of the precursor warhead. This second event while present in a dual warhead configuration may not be available in differing munition architectures. In the case of a single warhead the initial impact event can be substituted.

The final stimulus or impact event is the bash through warhead detonation. This fourth event while not used in the current description could be utilized to include increased capability into the present discrimination algorithm. The present discrimination algorithm is executed during the time period starting with the precursor warhead target impact event and completing before the bash through warhead detonation event.

Although the present invention will be described in connection with a dual warhead architecture it should be understood that the present invention is applicable to a singular e.g. bash through warhead and could function independently in the absence of a precursor warhead.

To this end the present method can be used in a munition having a singular warhead to provide autonomous target discrimination. The method includes the step of sensing an impact between the munition and the target. Upon sensing the impact the present method allows the munition to break through the target. The present method further uses the impact and the penetration of the munition as stimuli to concurrently monitor a combination of states of a plurality of switches and to set a selective detonation delay of the munition for providing increased performance behind the target.

Similar numerals refer to similar elements in the drawings. It should be understood that the sizes of the different components in the figures are not necessarily in exact proportion or to scale and are shown for visual clarity and for the purpose of explanation.

With reference to the present invention utilizes an exemplary multi warhead multi fuze target discriminating munition illustrated herein as a projectile for use against military operations in urban terrain MOUT targets including but not limited to earth and timber bunkers triple brick walls double reinforced concrete and armored targets according to the present invention.

The munition generally includes a plurality of interconnected sections a tail for tail section a rear body a main body and a nose cone . The tail generally includes a plurality of fins and possibly a tail boom as is known in the field. As a result the tail will not be described in greater detail. Similarly the nose cone is known in the field and will not be described herein in detail. The outer shape of the nose cone is selected to maintain standard aerodynamic properties.

According to a preferred embodiment of the present invention the munition comprises a precursor warhead also referred to herein as forward warhead and a bash through warhead also referred to herein as rear warhead . It should however be understood that the munition does not necessarily require dual warheads and could include a larger number of distributed warheads or a single warhead.

In this exemplary embodiment the precursor warhead is the nose cone that impacts the MOUT target before the bash through warhead . The bash through warhead is comprised of the rear body and the main body .

The precursor warhead is designed to pre damage the target . The bash through warhead is designed to penetrate through the damaged target and to detonate after a predetermined delay.

Upon impact of the munition with the target the precursor fuze causes the precursor warhead to detonate. Based on the data collected from the impact of the precursor warhead with the target the detonation of the precursor warhead and the impact of the bash through warhead with the target the bash through fuze sets an appropriate detonation delay time for the bash through warhead .

The present dual warhead architecture contributes to a series of stimuli that can be used to build capability into the fuzing system. The first recognizable impulse is the initial impact of the precursor warhead on the target . This event is followed by the detonation of the precursor warhead . Following the latter detonation is the impact of the bash through warhead with the target . The next stimulus is the detonation of the bash through warhead . The discrimination algorithm that forms part of the fuzing system is executed during the time period between the precursor warhead target impact event and the bash through warhead detonation event.

Having summarily described the general mode of operation of the munition the design and operation of the munition will now be described in more detail.

The precursor fuze circuitry generates an output to a piston actuator and an output to a detonator . The power regulator controls the level of the power delivered to the microcontroller . The microcontroller stores a logic or a software application for authorizing the delivery of the output control signal to the piston actuator included in a safe and arm mechanism S A in order to arm the S A mechanism.

Additionally the microcontroller logic controls the delivery of the output control signal to the detonator of the S A mechanism in order to detonate the precursor fuze .

In addition the microcontroller receives as input a status signal from the MEMS G switch in order to initiate the output to the piston actuator after setback and to initiate the output to the detonator on target impact as it will be explained later in connection with . The MEMS G switch has a high natural frequency and a small distance that the MEMS G switch contact must travel during operation. This affords the MEMS G switch a fast response time under high frequency stimuli. For this reason the MEMS G switch is used to sense the projectile initial impact with the target as it will provide a very fast response.

The bash through fuze circuitry generates the output to the piston actuator and the output to the detonator . The power regulator controls the level of the power delivered to the microcontroller . The microcontroller stores a logic or a software application for further authorizing the delivery of an output control signal to a piston actuator of the safe and arm mechanism S A in order to arm the S A mechanism.

Additionally the microcontroller logic controls the delivery of the output control signal to the detonator of the S A mechanism in order to detonate the bash through fuze .

The microcontroller receives as input a status signal from each of a MEMS G switch a conventional G switch and an impact switch that form part of the bash through fuze in order to implement the autonomous target discrimination algorithm as it will be explained later in connection with . While the switch or sensor is referred to herein as conventional G switch it should be understood that this reference is used for clarity of illustration of the present invention and does not limit the use of the present invention to conventional switches. The conventional G switch can alternatively be referred to as a 6000 G switch or high acceleration switch as the algorithm can be modified as required by adjusting the threshold value of the conventional G switch .

The conventional G switch has a lower relative natural frequency than that of the MEMS G switch and requires that a larger relative distance for the conventional G switch contact to travel during operation. This affords the conventional G switch a higher trigger threshold and filtering when exposed to high frequency stimuli. For this reason the conventional G switch is used to sense the target penetration as it requires more energy to trigger.

The microcontrollers and comprise a commercially available microcontroller. In one embodiment the software application or program that controls the operation of the munition is stored on the microcontrollers or . Alternatively the target discrimination application may be hardware software or firmware on any integrated or discrete circuitry or may comprise a similar analog logic with associated hardware.

The use and operation of the munition will now be described in more detail in connection with . includes and represents a flow chart that illustrates a method or process of operation of the target discriminating munition of .

At step of the process is initiated with the application of unregulated input power to both the precursor fuze and the bash through fuze respectively. Each of the precursor fuze and the bash through fuze functions independently i.e. charging sensing launch arming etc. beginning at step .

A setback event resulting from the launch is sensed by a temporary closure of the Micro Electro Mechanical Systems MEMS G switches of of . At steps and following a predetermined brief delay e.g. in the range of approximately 50 ms to allow the MEMS G switches to relax and return to the open state from the onset of the setback event the microcontrollers of of start monitoring the MEMS G switches of of for a subsequent change in state initiated by target impact. It should be clear that while exemplary numeral values are provided throughout the present description for illustration purpose these values are not exclusive will vary based on munition configuration and do not in any way limit the present invention to these specific values.

If at decision step the microcontrollers of of determine that the MEMS G switches of of remain opened and thus do not detect a change in state the microcontrollers of of continue monitoring the MEMS G switches of of until a change in state is detected by the microcontrollers of of . It should be reiterated that the response of the MEMS G switches of of are completely independent of one another as well as the associated responses of the microcontrollers of of .

Upon target impact of the precursor warhead the MEMS G switches of of will change state i.e. close . The change of state will be detected by the microcontrollers of of at step of the process . Furthermore and with reference to plot of graph the initial impact of the precursor warhead with the target is shown as peak .

The initial precursor target impact is followed by the detonation of the precursor warhead at step of and as further illustrated by peak of the plot . The detonation of the precursor warhead damages the MOUT target in preparation for the penetration of the bash through warhead .

With further reference to once the initial precursor warhead target impact event is sensed the autonomous target discrimination algorithm residing on the microcontroller uses both the initial impact event and the detonation of the precursor warhead as stimuli to start two concurrent functions . Depending on the performance of the precursor warhead on the target the bash through warhead may or may not penetrate the target . The munition does not classify the actual material or construction of the target . Rather it uses the ability of the bash through warhead to penetrate the target for timing the detonation of the bash through warhead .

The first function that is initiated by the microcontroller is the commencement of a delay counter at step . In this illustration an exemplary delay of approximately 750 s is set at step . As stated earlier the numerical value of this delay could be modified to any acceptable level depending on the target signature characteristics. The purpose of this delay is to prevent the microcontroller or microprocessor from discriminating the high frequency impact signature.

According to the second function the impact switch also referred to herein as hard target impact switch or sensor is monitored by the microcontroller for a change in state. The impact switch is designed to open change of state from high to low when a threshold acceleration level is exceeded in a specific direction for example when impact occurs with a heavy armor target or upon an impact event that causes the bash though warhead to break apart. The hard target impact switch bypasses the target detection logic and forces detonation of the bash through warhead on impact in order to prevent the breakup of the bash through warhead on heavy armor targets .

If the bash through impact event causes the impact switch to open as determined at decision step of process then the microcontroller causes the bash through warhead to detonate immediately at step on the premise that the MOUT target is not penetrable by the munition .

If however the bash through impact event does not cause the impact switch to change state i.e. to open as determined at decision step then process proceeds to decision step at the end of the delay period . In other terms the vertical line denotes the initiation of the final determination for the timing of the bash through warhead detonation.

Returning to decision step the microcontroller inquires if the state of the conventional G switch is low or high. At this time the impact switch could be disabled by the microcontroller . However the impact switch could remain enabled if it is determined or expected that a secondary hard target event could occur after the initial impact.

If at decision step the microcontroller determines that the conventional G switch has opened its state is now low then the microcontroller will cause the bash through warhead to detonate at step on the premise that the target is not a hard target and that it has already been penetrated by the munition . Alternatively the detonation could be scheduled to occur after a short delay for example in the range of approximately 15 to 25 s. Such a model will be experienced during an impact with a thin light target such as plywood drywall or glass.

If however at decision step the microcontroller determines that the conventional G switch remains closed its state is still high then the microcontroller will concurrently schedule a timeout following a predetermined period of time such as 40 msec and will also start monitoring the state of the conventional G switch at step .

To this end the microcontroller uses a preset minimum threshold to decide whether or not the bash through warhead has penetrated the target . This minimum threshold is denoted by a horizontal line in and is set by the threshold trigger level of the conventional G switch . For illustration purpose only the threshold for this specific embodiment is set at approximately 6 000 Gs. The microcontroller sets a decision logic feedback loop that is executed between the conventional G switch and the microcontroller .

More specifically if at decision step the process determines that the timeout has been reached even without a change of state of the conventional G switch then the microcontroller will cause the bash through warhead to detonate at step on the premise that the target is soft by comparison and that the munition has sufficiently buried to allow for efficient function.

If however at decision step the microcontroller determines that during the current monitor loop the timeout has not been reached then the microcontroller inquires at step if the state of the conventional G switch is low open or high closed . If the state is high then the microcontroller determines that the minimum threshold has not been crossed and continues to monitor the state of the conventional G switch at step as well as the time that it has been looping at step .

The process will continue this monitoring loop until the first of two conditions is met either the conventional G switch opens step or the timeout has been reached step as explained earlier. Upon determination at step that the state of the conventional G switch is low open then the microcontroller determines that the bash through warhead has penetrated the target at step and sets a predetermined delay at step prior to detonation at step .

With reference to a penetration point which is the intersection of plot and the minimum threshold line denotes such penetration of the bash through warhead through the target . For illustration purpose only the penetration point occurs after approximately 1.25 msec from the initial precursor warhead target impact event .

The setting of the delay at step is intended to ensure that the bash through warhead has sufficiently penetrated the target prior to detonation. In this embodiment the delay is set to approximately 12 ms although other values can alternatively be used.

In this particular embodiment of the munition the combination states of the impact switch and the conventional G switch identifies a total of six targets including but not limited to a hard target projectile breakup plywood drywall glass target light armor triple brick wall concrete earth and timber bunker and circuit timeout .

It should be understood that other modifications might be made to the present munition design without departing from the spirit and scope of the invention.

