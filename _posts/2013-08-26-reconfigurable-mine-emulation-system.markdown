---

title: Reconfigurable mine emulation system
abstract: A mine emulation system includes a standard electronics section. The system can be reconfigured into several different mine shapes by the use of different end sections attached to the electronics section. The electronics sections can include an array of sensors, including magnetic, seismic, pressure and passive acoustic sensors. The electronics can be programmable such that the sensors can emulate the various mine types as well as differing mines within each type. An active acoustic communication system allows surface ships or RF buoy systems to communicate with the mine emulator. An operator can provide a release command to an acoustically operated release system via the acoustic communication system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09494395&OS=09494395&RS=09494395
owner: The United States of America as represented by the Secretary of the Navy
number: 09494395
owner_city: Washington
owner_country: US
publication_date: 20130826
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties.

The present invention relates to emulation systems. More particularly the present invention relates to a mine emulation system that uses a standard or common electronics section that can be reconfigured into several different mine shapes by the use of different end sections.

Mine simulators or emulation systems are used in navy training exercises. The mine simulators are placed in known locations and the exercises include training in the use of mine detection systems to detect the mine simulators. The mine simulators can be of numerous types including air dropped mines submarine launched mines bottom mines or moored mines.

As can be expected the maintenance requirements for systems subjected to underwater environments are substantial especially for electronic components. The various types of mine simulators each have their own configuration and simulation electronics. As a result current practices maintain an inventory of spare parts for each type of mine emulator. Also personnel responsible for maintenance are required to be familiar with each type of emulator and its spare parts requirements.

Accordingly there exists a need to standardize the components of the mine simulators such that fewer spare parts are needed to maintain the systems. Additionally there exists a need to standardize components to provide for reduced training requirements and easier maintenance of the mine emulation system.

It is therefore a general purpose and primary object of the present invention to provide a mine emulation system having functional mine emulators utilizing a standard or common electronics section. The system can be reconfigured into several different mine shapes by the use of different end sections attached to the standard electronics section. The end sections can be configured to emulate air dropped submarine launched bottom or moored mines.

The electronics section can include an array of sensors that emulate those of the various types of mines including magnetic seismic pressure and passive acoustic sensors. The electronics can be programmable to emulate the various mine types as well as differing mines within each type.

An active acoustic communication system allows surface ships or Rf buoy systems to communicate with a single mine emulator or a field of mine emulators for real time mine firing data. The acoustic communication system also allows for diver less deployment and recovery of the mine emulator. An operator can provide a release command to an acoustically operated release system via the acoustic communication system.

In one embodiment a mine emulation system has a plurality of configurations for emulating a plurality of mine types. The system includes an electronics section a plurality of forward sections and a plurality of rear sections. Each of the forward sections is connectable to a first end of the electronics section. Each of the rear sections is connectable to a second end of the electronics section opposite the first end. Each one of the plurality of configurations includes the electronics section one of the plurality of forward sections and one of the plurality of rear sections.

For a given configuration the electronics section can include a programmable processor running an emulation algorithm corresponding to that given configuration. The system can include one or more sensors in communication with the processor. The processor operates on signals from the sensors that correspond to the given configuration.

The electronics section can also include at least one communication hydrophone disposed on an outer casing of the electronics section. A releasable band can secure the electronics section to the rear section. The processor can operate to release the band based on a signal received at the communication hydrophone.

The electronics section can also include one or more passive hydrophones magnetometers seismic sensors pressure sensors or inclinometers. The seismic sensor is mounted to an inside surface of the electronics section so as to detect vibrational target signatures. A pressure port is in communication with the pressure sensor and is open to the medium surrounding the system. The electronics section further includes a power source. The central processor can include a power management system in communication with the power source such that quiescent equipment can be powered down.

In one embodiment a method for emulating a plurality of mines includes connecting one of a plurality of forward sections to a first end of an electronics section and connecting one of a plurality of rear sections to a second end of the electronics section opposite the first end. The electronics section the forward section and the rear section form a given mine configuration.

The electronics section monitors the surrounding environment for target signatures corresponding to the given configuration. The electronics section emulates a response for a mine corresponding to the given mine configuration when one of the target signatures is perceived. The method can further include receiving an acoustic release signal at the electronics section and disconnecting one or both of the forward section and the rear section from the electronics section based on the release signal.

Monitoring can include sensing acoustic communications signals acoustic target signatures magnetic target signatures vibrational target signatures a pressure of the surrounding environment and an orientation of the electronics section. Monitoring can also include powering down quiescent equipment within the electronics section.

Referring now. to there is shown a schematic side view of generic mine emulation system . System is generally cylindrical in cross section and includes forward section electronics section connected at one end to forward section and rear section connected to an opposite end of electronics section . System can reconfigured into several mine shapes by replacing forward or nose section and rear or tail section with appropriately shaped sections. Electronics section is common to each mine shape of system . Accordingly for generic system illustrated in forward section and rear section are shown in phantom.

Referring now to there is shown a detailed side view of electronics section . Casing is cylindrical in cross section with mounting flanges at each end to accommodate respective forward and rear sections and . Passive acoustic hydrophones are mounted on casino to detect passing targets used in the training exercises.

For illustration but not limitation passive acoustic hydrophones illustrated in as mounted in a row longitudinally and spaced 90 degrees apart radially. This configuration allows for passive acoustic hydrophones to be exposed off the ocean floor no matter which way electronics section lays on the ocean floor.

Similarly communication hydrophones are illustrated in as mounted in a row longitudinally and spaced 90 degrees apart radially on casing . Communication hydrophones allow communication to and from electronics section for data transmission and for communicating commands to electronics section .

Referring now to there is shown a schematic representation of electronics equipment housed within electronics section of . Electronics equipment includes passive and communications acoustic processors and connected to respective passive acoustic hydrophones and communications hydrophones one of each is shown in phantom in . Acoustic processors and can operate on incoming acoustic signals to discern acoustic signatures and communications from background noise.

Additionally electronic equipment includes triaxial magnetometer . As is known in the art triaxial magnetometer detects ship and submarine magnetic signatures employing both dc and ac magnetic signatures so as to minimize false alarms. Accordingly forward section rear section and electronics section are fabricated of non magnetic material. Also electronic equipment includes low frequency seismic sensor . As known in the art seismic sensor detects ship and submarine seismic signatures. Seismic sensor is mounted directly to inner surface of electronics section so as to use vibrations of electronics section to detect seismic events.

Electronics equipment further includes differential pressure sensor and inclinometer . As is known in the art pressure sensor detects the pressure signature being created by a ship or submarine. Pressure sensor is in communication with medium surrounding system via external port . For illustration but not limitation external port is shown extending from inner surface through casing of electronics section . Inclinometer tracks the orientation of system during deployment.

Acoustic processors and magnetometer sensors and and inclinometer are each connected to main controller . Additionally power source is connected to main controller and provides power for the operation of electronics equipment .

Referring now also to there is shown a schematic illustration of main controller . Main controller includes central processor signal conditioners and data storage . Additionally main controller includes active power management system in communication with power source . Power management system operates to conserve power during long exercises by shutting down quiescent equipment within electronics section while awaiting signals to be received at one or more of acoustic processors and magnetometer sensors and and inclinometer .

Central processor is programmed with one or more mine emulation algorithms and controls the operations of system . Signal conditioners condition incoming signals from one or more of acoustic processors and magnetometer sensors and and inclinometer all shown in for acceptance by central processor

Central processor compares the incoming data to the algorithm from the programmed mine emulation to determine if the signal is from a target. Results are stored in data storage . Data storage can include a plurality of hard or flash drives for redundancy which can be sealed separately for increased watertight integrity.

Referring now to there are illustrated various configurations of mine emulation system . Air drop configuration shown in mimics in appearance and emulates the operation of an air dropped service mine. Rear or tail section and forward or nose cone section are attached to flanges shown in of electronics section by the use of quick release bands and respectively.

Tail section is weighted in order to keep system configuration on the ocean floor. Nose section is positively buoyant to serve as a float that can bring electronics section to the surface. When a release command is received via communication hydrophones main controller shown in of electronics section can cause band to open thus releasing nose section and electronics section to float to the surface. A recovery line can be attached to tail section and nose section or tail section for retrieval.

Submarine launched configuration shown in mimics in appearance and emulates the operation of a submarine launched service mine. In addition to nose section and tail section configuration is equipped with drive section located between electronics section and tail section . Quick release band attaches drive section to tail section in a manner similar to bands and previously described herein.

To fully simulate a submarine launched service mine tail section includes rotor . Drive section can be fully operational so as to turn rotor and propel configuration . As in the case of configuration nose section is positively buoyant. When a release command is received via communication hydrophones main controller shown in of electronics section can cause band to open thus releasing nose section and electronics section to float to the surface. Again a recovery line can be attached to drive section and nose section or electronics section for retrieval.

Bottom mine configuration shown in includes weighted ballast tail section to maintain the mine on the ocean floor and positively buoyant nose section . As with configuration bands and attach respective tail and nose sections and to electronics section . Again a release command results in main controller shown in opening band such that nose section and electronics section can float to the surface. A recovery line can be attached to tail section and nose section and electronics section for retrieval.

Moored configuration shown in includes nose section and tail section attached to opposite ends of electronic section via respective bands and . When attached to each other the combination of the nose section tail section and electronics section is positively buoyant. Anchor is connected to tether which in turn connects to quick release ring attached to electronics section . When a release command is received at communication hydrophones main controller shown in opens ring to release entire moored configuration which floats to the surface for retrieval.

Referring now to there is shown a block diagram of method for emulating a plurality of mine configurations using system . At block one of the plurality of forward sections is connected to one end of electronics section . At block one of the plurality of rear sections is connected to the opposite end of the electronics section to form the desired mine configuration such as one of those illustrated in .

After the assembled mine configuration is deployed into a surrounding environment block such as on a seafloor the electronics section monitors the surrounding environment for target signatures corresponding to the given configuration block . Monitoring can include sensing acoustic communications signals acoustic target signatures magnetic target signatures vibrational target signatures a pressure of the surrounding environment and an orientation of the electronics section. If one of the target signatures is perceived block the electronics section emulates a response for a mine corresponding to the given mine configuration block .

In addition if an acoustic release signal is received at the electronics section block method can disconnect one or both of the forward section and the rear section from the electronics section block . Also if any of electronic equipment shown in is quiescent block e.g. signal conditioners shown in power management system also shown in shuts or powers down the quiescent equipment block to conserve power.

Obviously many modifications and variations of the present invention may become apparent in light of the above teachings. For example many other configurations are possible depending on the sections attached to electronics section . Central processor can be programmed to emulate the mine system matching the chosen configuration. Depending on the configuration additional sensors may be added or some sensors can be removed to minimize power requirements or costs.

Additionally external port can penetrate from electronics section to one or both of forward section and rear section which can be open to medium . Further the buoyancy of nose section can be sufficient to maintain one or more of configurations upright on the ocean floor.

What have thus been described are a mine emulation system and method having a standard or common electronics section with interchangeable nose and tail sections. The system can be reconfigured into several different mine shapes by the use of the different forward and rear sections attached to the standard electronics section. The forward and rear sections can be configured to emulate air dropped submarine launched bottom or moored mines. Additionally system can be configured in a myriad of novel ways.

The electronics section can include an array of sensors that emulate those of the various types of mines including magnetic seismic pressure and passive acoustic sensors. The electronics can be programmable to emulate the various mine types as well as differing mines within each type.

In addition the electronics section can include art active acoustic communication system that allows surface ships or RF buoy systems to communicate with a single mine emulator or a field of mine emulators for real time mine firing data. The acoustic communication system also allows for diver less deployment and recovery of the mine emulator. The nose or forward section in a number of configurations can be positively buoyant. An operator can provide a release command to an acoustically operated release system via the acoustic communication system such that the nose and electronics sections can be released from a weighted tail section.

As described herein the mine emulation system has a number of advantages over current mine emulation systems. The standardized electronics section of the mine emulation system requires fewer spare parts to maintain the system. Additionally the standardized components provide for reduced training requirements and easier maintenance of the mine emulation system.

It will be understood that many additional changes in details materials steps and arrangements of parts which have been described herein and illustrated in order to explain the nature of the invention may be made by those skilled in the art within the principle and scope of the invention as expressed in the appended claims.

