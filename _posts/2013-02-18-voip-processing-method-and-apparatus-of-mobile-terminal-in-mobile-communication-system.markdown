---

title: VoIP processing method and apparatus of mobile terminal in mobile communication system
abstract: An improved VoIP (Voice over Internet Protocol) processing method and apparatus reduce the processing delay of a mobile terminal in the mobile communication system. The VoIP processing apparatus includes a Radio Frequency (RF) unit configured to transmit and receive a VoIP packet, and an audio processing unit configured to process audio signals. The apparatus also includes a voice engine configured to determine, when VoIP packet processing is requested, whether a dedicated voice path for processing the VoIP packet exists and control, when the dedicated voice path exists, to process voice signal input/output using a dedicated VoIP processing interface for processing the VoIP packet. The VoIP processing method and apparatus are capable of reducing voice delay by improving the audio paths between VoIP applications and terminal platform.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09226172&OS=09226172&RS=09226172
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09226172
owner_city: Suwon-Si
owner_country: KR
publication_date: 20130218
---
The present application is related to and claims the benefit under 35 U.S.C. 119 a of a Korean patent application filed in the Korean Intellectual Property Office on Feb. 16 2012 and assigned Serial No. 10 2012 0015661 the entire disclosure of which is hereby incorporated by reference.

The present disclosure relates to a mobile communication system and in particular to a VOIP Voice over Internet Protocol processing method and apparatus of a mobile terminal for improving voice communication service in the mobile communication system.

Internet telephony or voice communication over IP networks hereinafter referred to as VoIP may not be able to ensure Quality of Service QoS due to the possibility of excessive end to end delay packet loss high delay jitter and the like because the Internet Protocol IP network is a best effort network. Among these factors voice delay is one of the most significant factors influencing the service quality. The user starts feeling uncomfortable with the delay longer than 200 ms and if the delay becomes longer than 400 ms most people complain of significant inconvenience. Accordingly it is desirable to improve real time characteristics of voice communication by reducing the end to end delay. The end to end delay roughly includes processing delay and network delay.

The processing delay is the total delay incurred by both the sender and receiver while processing the voice signals with the exception of the time the packet propagates the network. The processing delay includes the transmitter delay of encoding the voice signal input through a microphone and transmitting encoded Real Time Protocol RTP packet and the receiver delay of decoding the received packet and outputting the decoded voice signal through a speaker. Research is being conducted for technologies to reduce the delays in capturing encoding decoding and rendering the voice signal.

Recently the VoIP service for the Android operating system based smartphone users is introduced by Social Network Service SNS providers as well as the network operators and the service competition is becoming intense. In spite of this situation the end to end delay of the conventional Android operating system based VoIP service does not meet the requirement of 400 ms regardless of the application and type of terminal and this is the big obstacle for securing the VoIP service quality on the Android platform.

To address the above discussed deficiencies of the prior art it is a primary object of the present disclosure to provide a method and apparatus for providing VoIP service with improved quality in a mobile communication system.

It is another object of the present disclosure to provide a method and apparatus for providing VoIP service that is capable of reducing the internal processing delay of the mobile terminal by introducing a VoIP packet dedicated voice path for processing the VoIP packet separate from the audio procession path provided by the operating system of the mobile terminal.

It is still another object of the present disclosure to provide a method and apparatus for providing VoIP service that is capable of reducing the end to end voice delay by minimizing extra delay caused by the Android platform and by installing delay reduction algorithms optimized for different types of terminals selectively.

In accordance with an aspect of the present disclosure a Voice over IP VoIP processing apparatus of a mobile terminal in a mobile communication system includes a Radio Frequency RF unit configured to transmit and receive a VoIP packet. The apparatus also includes an audio processing unit configured to process audio signals. The apparatus further includes a voice engine configured to determine when VoIP packet processing is requested whether a dedicated voice path for processing the VoIP packet exists and control when the dedicated voice path exists to process voice signal input output using a dedicated VoIP processing interface for processing the VoIP packet.

In accordance with another aspect of the present disclosure a Voice over IP VoIP processing method of a mobile terminal in a mobile communication system includes receiving a VoIP packet processing request. The method also includes determining whether a dedicated voice path for processing the VoIP packet exists. The method further includes processing when the dedicated voice path exists voice signal input output using a dedicated VoIP processing interface for processing the VoIP packet.

Before undertaking the DETAILED DESCRIPTION OF THE INVENTION below it may be advantageous to set forth definitions of certain words and phrases used throughout this patent document the terms include and comprise as well as derivatives thereof mean inclusion without limitation the term or is inclusive meaning and or the phrases associated with and associated therewith as well as derivatives thereof may mean to include be included within interconnect with contain be contained within connect to or with couple to or with be communicable with cooperate with interleave juxtapose be proximate to be bound to or with have have a property of or the like and the term controller means any device system or part thereof that controls at least one operation such a device may be implemented in hardware firmware or software or some combination of at least two of the same. It should be noted that the functionality associated with any particular controller may be centralized or distributed whether locally or remotely. Definitions for certain words and phrases are provided throughout this patent document those of ordinary skill in the art should understand that in many if not most instances such definitions apply to prior as well as future uses of such defined words and phrases.

Referring to the Android platform provides an Application Programming Interface API for voice input output through an audio recording audio track. The VoIP application operates in a Java Space through the API provided by the Android platform which controls the drivers in the Native Space . The Java has a drawback in that the processing performance is degraded due to the low execution speed as compared to the application generated in the Native Space . Accordingly the Voice Engine is implemented in the Native Space and the VoIP application controls the voice engine through Java Native Interface JNI on the Android platform. Although the VoIP application and the voice engine are separated in such a depiction is only for the purpose of functional distinction. That is the voice engine is a block responsible for one of the functions of the VoIP application and implemented in the native space and thus depicted as a separated block in .

The JNI provides an interface for communication between the modules e.g. C of the Java space and the native space . The JNI is used for fast processing speed routine creation hardware control and legacy C C program reuse.

The AudioRecord and AudioTrack of the Java Space are the Java threads on the Software Development Kit SDK that are generated for input AudioRecord output AudioTrack of audio data of an application program.

The AudioRecord and AudioTrack of the Native Space are the binder objects paired with the AudioRecord AudioTrack generated by the application program.

The AudioFlinger is a tread for calling an HAL API accessing the real input output device by mixing the AudioTrack AudioRecord data generated by a plurality of applications.

The audio hardware ALSA HAL is a library specifying the interface AudioHardware standardized for minimizing change on the higher layer depending on the hardware.

The ALSA library is a representative Audio standardization layer of Linux and provides various functions such as mixer and resampler as well as input output function. In some embodiments only the input output function is used on the Android platform.

Although not depicted in the Android platform is capable of including a Device Driver. The device driver is a device driver software implementing the function as specified in the standard of the sound device defined in the operating system and implemented differently depending on the hardware chipset.

The hardware is a function block for outputting the sound generated in software through an analog device DAC and converting the signal input through an analog device to digital data ADC .

A brief description is made of the general VoIP packet processing method based on the above described Android platform. If a VoIP packet arrives at the mobile terminal the voice engine of the VoIP application detects the VoIP packet and delivers the voice packet to the audio track of the Java space . The VoIP packet is processed into a VoIP object through the audio track and output in the form of voice through the path of audio track audio flinger audio hardware ALSA ALSA library and the speaker as a hardware device.

The analog voice signal input through the microphone is generated as a VoIP packet through the signal path adverse to the above described signal path to be transmitted to the recipient terminal.

For the Android VoIP application the VoIP call is processed through several operations of the Android framework as depicted in i.e. audio record audio track Java space audio record audio track native space audio flinger audioHAL and ALSA. As a consequence the Android platform i.e. framework causes extra delay of 150 200 ms regardless of the types of terminal and VoIP application.

When the voice engine is placed in the native space and uses the audio record track directly this also incurs extra delay caused by creation of audio record track thread and increase of stepwise buffer. The voice communication quality degradation caused by this extra delay is considered a limitation of the Android based VoIP service.

The present disclosure describes a method for reducing the end to end voice delay by minimizing the extra delay incurred on the Android platform and applying delay reduction algorithms optimized for different types of terminals selectively resulting in an improvement of VoIP service quality.

As shown in the VoIP processing apparatus according to an embodiment of the present disclosure includes a VoIP application Java Space a voice engine native space and an Android platform .

A description is made in more detail with reference to . The mobile terminal operates differently depending on the executed VoIP application and whether to process a received VoIP packet or and input voice signal.

The voice engine of the mobile terminal receives a VoIP packet transmitted using RTF protocol by means of the transceiver. The voice engine is the engine included logically in the VoIP application for processing VoIP voice and can be implemented in the Java space or the native space according to the developer s intention. In an embodiment of the present disclosure the voice engine is implemented in the native space however the present disclosure is not limited thereto.

Upon receipt of the VoIP packet the voice engine extracts the header of the VoIP packet to perform decoding. As a consequence the voice engine is capable of acquiring the original voice data. In this embodiment the voice engine calls the ALSA library in the native space to process the acquired original voice data and output the processed voice data through the speaker without involvement of the Android audio application .

As described above the VoIP dedicated voice path formed via the voice engine ALSA library and speaker according to an embodiment of the present disclosure is established through relatively simple processing operations as compared to the legacy voice path formed via the Android audio application. Since the audio track record operation is skipped it is possible to reduce the audio processing delay dramatically.

The audio input output of the VoIP application is controlled by means of the voice engine through JNI. The voice engine performs voice input output for VoIP packet using Advanced Linux Sound Architecture ALSA library.

In an embodiment of the present disclosure the audio playback and or recording of other Android applications with the exception of the VoIP packet application is processed through the same audio path as the legacy and droid application. In this embodiment the VoIP packet RTP packet and the legacy Android application audio data are mixed by a software mixer of the Advanced Linux Sound Architecture ALSA .

If a voice signal is input through the microphone after the execution of the VoIP application the VoIP packets are generated in the adverse order to the voice output processing order and transmitted to the counterpart terminal. That is the digital signal obtained by converting the signal input through the microphone is delivered to the voice engine through the mixer and ALSA library. The voice engine compresses the original voice data and adds a header to generate a VoIP packet which is transmitted through the transceiver.

In the legacy Android based terminal as depicted in the voice passes several stepwise audio paths resulting in voice delay. In the first embodiment of the present disclosure as depicted in a dedicated VoIP audio path is formed separately from the common audio path of the Android framework so as to reduce the number of stepwise paths of the VoIP packet resulting in reduction of voice delay.

As shown in the VoIP processing apparatus according to an embodiment of the present disclosure includes a VoIP application Java Space a voice engine native space and an Android platform .

Referring to if a VoIP application is executed in the mobile terminal and if a VoIP packet is received the voice engine of the VoIP application detects the receipt of the VoIP packet. The voice engine is capable of acquiring the original voice data from the VoIP packet.

Once the original voice data is acquired the voice engine controls the hardware directly through a voice input output interface of the call processor i.e. the dedicated VoIP processing interface to output the original voice data through the speaker without passing through the Android audio application . The dedicated VoIP processing interface is positioned in the kernel space and controls a voice subsystem a kind of chip for controlling the voice system in the hardware domain.

In the second embodiment as depicted in the voice engine calls the dedicated VoIP processing interface directly to process the VoIP packet.

Although the diagram has been depicted to show a logical configuration the dedicated VoIP processing interface can be configured to call the audio record track part of the Android platform operating system in the real system. In this situation the procedure following the operation where the dedicated VoIP processing interface calls the audio record track part can be configured to process the VoIP packet and normal voice packet distinctively to generate objects in different formats. That is the VoIP and normal voice packets are managed separately by creating a dedicated VoIP audio object for a VoIP packet including VoIP content and a normal audio object for a normal voice packet.

The VoIP and normal voice packets are mixed by the audio flinger in collision e.g. outputting push button sound in VoIP call processing. In this way it is possible to process the audio playback and or recording of the Android frame simultaneously in VoIP call processing according to an embodiment of the present disclosure.

Although the description has been directed to the procedure of processing VoIP packets received by the mobile terminal the present disclosure also can be applied to the procedure for processing the user voice input through the microphone of the mobile terminal into the voice packet.

If the VoIP application is executed the voice engine initializes the microphone and monitor to detect the input of user voice. The analog voice signal input through the microphone is converted to a digital voice signal. The voice engine detects the execution of the VoIP application and delivers the converted digital voice signal to the dedicated VoIP processing interface directly other than the Android framework. The voice engine encodes the digital voice signal and adds a header to generate a VoIP packet which is transmitted to the counterpart terminal.

It is assumed that the server and the mobile terminal are communicatively connected to each other. The connection can be established in various ways e.g. the mobile terminal is capable of accessing the server retaining the VoIP application to download the VoIP application or the server is capable of connecting to the mobile terminal through a radio management function to install the VoIP application.

The server acquires the information of the mobile terminal device information or DI in which the VoIP application is to be installed at operation S. The server checks the information such as device model and firmware version of the mobile terminal at operation S.

The server looks up the audio path mapping table based on the mobile terminal information at operation S. The mapping table sorts VoIP application types into groups by device type as shown in Table 1.

By referencing the mapping table the server checks the types of VoIP applications that can be installed in the mobile terminal at operation S. The server selects a VoIP application corresponding to the checked VoIP application type. According to an embodiment of the present disclosure if the type of the mobile terminal is Galaxy S2 the server checks that all VoIP application types of DAP DAP and DAP are supported and selects a VoIP application supporting all of the DAP DAP and DAP . The server transmits the selected VoIP application to the mobile terminal at operation S.

The mobile terminal receives the VoIP application transmitted by the server at operation S and installs the received VoIP application at operation S.

The mobile terminal attempts to acquire its own device information at operation S. The mobile terminal determines whether the information on its own device model and firmware version has been acquired at operation S and if not acquired returns the procedure to operation S.

If the information is acquired the mobile terminal references the audio path mapping table based on its own device information at operation S. The mapping table sorts VoIP application types into groups by device type and structured as shown in Table 1.

By referencing the mapping table the mobile terminal checks the types of VoIP applications and selects a VoIP application of the checked VoIP application type at operation S.

If a VoIP packet processing request is received the mobile terminal determines whether a dedicated voice path is provided at operation S. Determining whether a dedicated voice path is provided may include determining whether a VoIP application supporting DAP or DAP is installed.

If the dedicated voice path is provided the mobile terminal generates a dedicated VoIP packet audio track at operation S. This operation corresponds to the process of calling at the voice engine of the mobile terminal a voice input output interface e.g. dedicated VoIP processing interface of the call processor. As described above calling the dedicated VoIP processing interface is a logical process and can be implemented to call the audio record track part of the Android operating system in real system and operation S is provided to perform this calling operation.

In order to control the collision with other audio data e.g. button sound and effect sound the mobile terminal calls the HAL API at operation S. This corresponds to the process for the audio flinger of the Android operating system to call the audio hardware ALSA library. Through this process it is possible to avoid the collision between the VoIP packet and normal audio packet.

If no dedicated audio path is provided at operation S the mobile terminal establishes a normal audio track at operation S. This corresponds to the operation of calling at the Android audio application the audio record track of the Java space and native space. In more detail if the audio engine calls the audio record track a dedicated VoIP audio track is established. If the Android audio application calls the audio record track a normal audio track is established. In this way the VoIP processing method of the present disclosure creates and manages the dedicated VoIP audio track and the normal audio track distinctively.

If the normal audio track is created the mobile terminal writes the audio data at operation S. Next the mobile terminal determines whether resampling is required at operation S and if so performs resampling at operation S. Otherwise if resampling is not required the mobile terminal performs audio flinger mixing at operation S. This operation is to mix the data of audio tracks created by multiple applications. The mobile terminal calls the HLR API to control collision with other audio data e.g. button sound and effect sound at operation S.

Next the mobile terminal calls the device driver at operation S and outputs the audio signal at operation S.

The RF unit is responsible for radio communication the VoIP processing apparatus for transmitting receiving data. The RF unit includes an RF transmitter for up converting and amplifying a signal to be transmitted and an RF receiver for low noise amplifying and down converting the received signal. The RF unit also outputs the data received through a radio channel to the voice engine and transmits the data output by the voice engine to the counterpart terminal through the radio channel.

In an embodiment of the present disclosure the RF unit is capable of transmitting receiving audio data and especially in the VoIP voice communication mode the VoIP packet using the RTP protocol.

The voice engine controls the sequential processes for providing the VoIP service with improved quality in the mobile communication system. For this purpose the voice engine processes the VoIP packets through a dedicated voice path separate from the audio processing path provided by the operating system of the mobile terminal.

In detail the voice engine detects a VoIP packet processing request and determines whether a dedicated VoIP packet processing path exists. If the dedicated VoIP packet processing path exists the voice engine controls such that the voice signal input output is processed through a dedicated VoIP processing interface for processing the VoIP packet dedicatedly. The dedicated VoIP processing interface is implemented in the kernel space and provides communication means for controlling the hardware related to the audio processing unit directly.

If no dedicated VoIP packet processing path exists the voice engine controls such that the voice signal input output is processed through the audio application OS audio application embedded in the operating system of the mobile terminal. In an embodiment the OS audio application may include the audio record and audio track in the Java space the audio record and audio track in the native space audio flinger audio hardware Advanced Linux Sound Architecture or ALSA and ALSA library.

The audio engine is implemented in the native space and if the VoIP packet and normal voice packet are generated simultaneously controls to process the VoIP packet and normal voice packet as mixed.

The audio processing unit includes a codec pack composed of a data codec for processing packet data and an audio codec for processing the audio signal including voice. The audio processing unit converts a digital audio signal to an analog audio signal by means of the audio codec to output through the audio signal through a speaker and converts an analog signal input through a microphone to a digital audio signal by means of the audio codec.

As described above the VoIP processing method and apparatus of the present disclosure reduce voice delay by improving the audio paths between VoIP applications and terminal platform.

Although the present disclosure has been described with an exemplary embodiment various changes and modifications may be suggested to one skilled in the art. It is intended that the present disclosure encompass such changes and modifications as fall within the scope of the appended claims.

