---

title: Image display apparatus having a graphical user interface for a plurality of input ports and method for operating the same
abstract: An image display apparatus and a method for operating the same are disclosed. The method for operating an image display apparatus includes displaying a first image, displaying per-input port images that are being received or have been received through a plurality of input ports on a per-input port basis so that the per-input port images are distinguished from one another according to the input ports, upon receipt of a per-input port image view input, selecting one of the per-input port images, and displaying an image corresponding to an input port through which the selected per-input port image is being received or has been received. The per-input port images are displayed overlapped with one another.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08804043&OS=08804043&RS=08804043
owner: LG Electronics Inc.
number: 08804043
owner_city: Seoul
owner_country: KR
publication_date: 20130315
---
This application claims the benefit of Korean Patent Application No. 10 2012 0153436 filed on Dec. 26 2012 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

The present invention relates to an image display apparatus and a method for operating the same and more particularly to an image display apparatus and a method for operating the same which can increase user convenience.

An image display apparatus has a function of displaying images to a user. The image display apparatus can display a broadcast program selected by the user on a display from among broadcast programs transmitted from broadcasting stations. The recent trend in broadcasting is a worldwide shift from analog broadcasting to digital broadcasting.

As it transmits digital audio and video signals digital broadcasting offers many advantages over analog broadcasting such as robustness against noise less data loss ease of error correction and the ability to provide high definition clear images. Digital broadcasting also allows interactive viewer services compared to analog broadcasting.

Therefore the present invention has been made in view of the above problems and it is an object of the present invention to provide an image display apparatus and a method for operating the same which can increase user convenience.

It is another object of the present invention to provide an image display apparatus and a method for operating the same which can readily display input images.

In accordance with an aspect of the present invention the above and other objects can be accomplished by the provision of a method for operating an image display apparatus including displaying a first image displaying per input port images that are being received or have been received through a plurality of input ports on a per input port basis so that the per input port images are distinguished from one another according to the input ports upon receipt of a per input port image view input selecting one of the per input port images and displaying an image corresponding to an input port through which the selected per input port image is being received or has been received. The per input port images are displayed overlapped with one another.

In accordance with another aspect of the present invention there is provided an image display apparatus including a display to display a first image an interface unit having a first plurality of input ports to receive per input port images through a second plurality of input ports and a controller to upon receipt of a per input port image view input control display of per input port images that are being received or have been received through the second plurality of input ports on a per input port basis so that the per input port images are distinguished from one another according to the input ports and when one of the per input port images is selected to control display of an image corresponding to an input port through which the selected per input port image is being received or has been received. The per input port images are displayed overlapped with one another.

Embodiments of the present invention will be described below with reference to the attached drawings.

The terms module and unit used to signify components are used herein to help the understanding of the components and thus they should not be considered as having specific meanings or roles. Accordingly the terms module and unit may be used interchangeably.

An image display apparatus as set forth herein is an intelligent image display apparatus equipped with a computer support function in addition to a broadcast reception function. Thus the image display apparatus may have user friendly interfaces such as a handwriting input device a touch screen or a three dimensional 3D pointing device. Further because the image display apparatus supports wired or wireless Internet it is capable of e mail transmission reception Web browsing banking gaming etc. by connecting to the Internet or a computer. To implement these functions the image display apparatus may operate based on a standard general purpose Operating System OS .

That is various applications can be freely added to or deleted from a general purpose OS kernel in the image display apparatus according to the present invention. Therefore the image display apparatus may perform a number of user friendly functions. The image display apparatus may be for example a smart TV.

Referring to an image display apparatus may receive various input images through a plurality of input ports.

In accordance with an embodiment of the present invention upon receipt of an input for viewing images on a per input port basis hereinafter referred to as a per input port image view input the image display apparatus may separately display images that are being received or have been received through input ports on a per input port basis.

That is upon receipt of a per input port image view input the image display apparatus may display images that are being received or have been received through input ports in such a manner that the images can be distinguished from one another according to the input ports. The simplified display of input images in the image display apparatus increases user convenience.

A plurality of images received through a plurality of input ports may be displayed distinctively from one another overlapped with one another. Since the images can be displayed at the same time in this manner the image display apparatus can increase user convenience.

Upon selection of one of the images received through the input ports the image display apparatus displays the selected image full screen thereby allowing the user to view the image readily.

If any of a plurality of input ports provides recorded images the image display apparatus displays the images received from the input port only when playback of the images is not completed. Thus the user can readily identify only input images to view.

Display of images on a per input port basis in response to a per input port image view input according to an embodiment of the present invention will be described in detail later with reference to .

Referring to the image display apparatus according to an embodiment of the present invention includes a broadcasting receiver a network interface an external device interface a memory a user input interface a controller a display an audio output unit and a power supply . The broadcasting receiver may include a tuner and a demodulator . When needed the broadcasting receiver may further include the network interface .

The tuner selects a Radio Frequency RF broadcast siyiial corresponding to a channel selected by a user or an RF broadcast signal corresponding to each of pre stored channels from among a plurality of RF broadcast signals received through an antenna and downconverts the selected RF broadcast signal into a digital Intermediate Frequency IF signal or an analog baseband Audio Video A V signal.

More specifically if the selected RF broadcast signal is a digital broadcast signal the tuner downconverts the selected RF broadcast signal into a digital IF signal DIF. On the other hand if the selected RF broadcast signal is an analog broadcast signal the tuner downconverts the selected RF broadcast signal into an analog baseband A V signal CVBS SIF.

The tuner may sequentially select a number of RF broadcast signals corresponding to all broadcast channels previously stored in the image display apparatus by a channel add function from a plurality of RF signals received through the antenna and may downconvert the selected RF broadcast signals into IF signals or baseband A V signals.

The demodulator receives the digital IF signal DIF from the tuner and demodulates the digital IF signal DIF.

The demodulator may perform demodulation and channel decoding on the digital IF signal DIF thereby obtaining a stream signal TS. The stream signal TS may be a signal in which a video signal an audio signal and a data signal are multiplexed.

The stream signal TS may be input to the controller and thus subjected to demultiplexing and A V signal processing. The processed video and audio signals are output to the display and the audio output unit respectively.

The external device interface may serve as an interface between a connected external device and the image display apparatus . For interfacing the external device interface may include an A V Input Output I O unit not shown .

The external device interface may be connected to an external device such as a Digital Versatile Disk DVD player a Blu ray player a game console a camera a camcorder a computer e.g. a laptop computer or a set top box wirelessly or by wire. Then the external device interface may transmit and receive signals to and from the external device.

In order to allow input of video and audio signals from the external device to the image display apparatus the A V I O unit of the external device interface may include a Universal Serial Bus USB port a Composite Video Banking Sync CVBS port a Component port an S Video port analog a Digital Visual Interface DVI port a High Definition Multimedia Interface HDMI port a Red Green Blue RGB port and a D SUB port.

In addition the external device interface may be connected to various set top boxes through at least one of the above described ports to transmit signals to or receive signals from the set top boxes.

The network interface serves as an interface between the image display apparatus and a wired wireless network such as the Internet. The network interface may receive content or data from the Internet a Content Provider CP or a Network Provider NP over a network.

The network interface may access a specific Web page over a connected network or another network linked to the connected network. That is the network interface may access a specific Web page over a network and may transmit data to or receive data from a server. Besides the network interface may receive content or data from a CP or an NP.

Further the network interface may selectively receive an intended application from among applications open to the public through a network.

The network interface may include a wired communication module not shown and a wireless communication module not shown .

The wireless communication module of the network interface may perform short range wireless communication with other electronic devices. The image display apparatus may be connected to other electronic devices over a network in conformance to communication standards such as Bluetooth Radio Frequency Identification RFID Infrared Data Association IrDA Ultra WideBand UWB ZigBee Digital Living Network Alliance DLNA etc.

The memory may store various programs necessary for the controller to process and control signals and may also store processed video audio and data signals.

The memory may temporarily store a video audio and or data signal received from the external device interface or the network interface . The memory may store information about broadcast channels by the channel add function.

The memory may store an application or an application list received from the external device interface or the network interface .

The image display apparatus may open a content file e.g. a video file a still image file a music file a text file an application file etc. to the user.

While the memory is shown in as configured separately from the controller to which the present invention is not limited the memory may be incorporated into the controller for example.

The user input interface transmits a signal received from the user to the controller or transmits a signal received from the controller to the user.

For example the user input interface may receive various user input signals such as a power on off signal a channel selection signal and a screen setting signal from the remote controller provide the controller with user input signals received from local keys not shown such as inputs of a power key a channel key a volume key and a setting key transmit a control signal received from a sensor unit not shown for sensing a user gesture to the controller or transmit a signal received from the controller to the sensor unit.

The controller may demultiplex the stream signal TS received from the tuner the demodulator or the external device interface into a number of signals and process the demultiplexed signals into audio and video data.

The video signal processed by the controller may be displayed as an image on the display . The video signal processed by the controller may also be transmitted to an external output device through the external device interface .

The audio signal processed by the controller may be output to the audio output unit . Also the audio signal processed by the controller may be transmitted to the external output device through the external device interface .

While not shown in the controller may include a demultiplexer DEMUX and a video processor which will be described later with reference to .

In addition the controller may provide overall control to the image display apparatus . For example the controller may control the tuner to tune to an RF broadcast signal corresponding to a user selected channel or a pre stored channel.

The controller may control the image display apparatus according to a user command received through the user input interface or according to an internal program. Especially the controller may connect to a network and download a user intended application or application list to the image display apparatus through the network.

For example the controller receives a signal of a channel selected according to a specific channel selection command received through the user input interface by controlling the tuner and processes a video audio or data signal of the selected channel. The controller outputs information about the user selected channel along with the processed video or audio signal to the display or the audio output unit .

In another example the controller outputs a video or audio signal received from an external device for example a camera or a camcorder according to an external device video play command received through the user input interface to the display or the audio output unit .

The controller may also control the display to display images. The image displayed on the display may be a two Dimensional 2D or 3D still image or video.

The controller may control a particular object in the image displayed on the display to be rendered as a 3D object. For example the particular object may be at least one of a linked Web page e.g. of a newspaper a magazine etc. an Electronic Program Guide EPG a menu a widget an icon a still image a video or text.

The controller may locate the user based on an image captured by a camera unit not shown . Specifically the controller may measure the distance a z axis coordinate between the user and the image display apparatus . In addition the controller may calculate x axis and y axis coordinates corresponding to the position of the user on the display .

Upon selection of an application view menu item the controller may control display of an application or application list that are available in the image display apparatus or can be downloaded from an external network.

The controller may control installation and execution of applications downloaded from the external network as well as various User Interfaces UIs . The controller may also control display of an image related to an executed application on the display according to user selection.

The display generates drive signals by converting a processed video signal a processed data signal and an On Screen Display OSD signal received from the controller or a video signal and a data signal received from the external device interface to RGB signals.

The display may be various types of displays such as a Plasma Display Panel PDP a Liquid Crystal Display LCD an Organic Light Emitting Diode OLED display and a flexible display. The display may also be capable of displaying 3D images.

The display may also be a touch screen that can be used not only as an output device but also as an input device.

The audio output unit may receive a processed audio siynal from the controller and output the received audio signal as voice.

The power supply supplies power to the image display apparatus . Particularly the power supply may supply power to the controller the display and the audio output unit which may be implemented as a System On Chip SOC .

For supplying power the power supply may include a converter not shown for converting Alternating Current AC into Direct Current DC . If the display is configured with for example a liquid crystal panel having a plurality of backlight lamps the power supply may further include an inverter not shown capable of performing Pulse Width Modulation PWM for luminance change or dimming driving.

The remote controller transmits a user input to the user input interface . For the transmission of a user input the remote controller may operate in conformance to various communication standards such as Bluetooth RF IR UWB and ZigBee.

In addition the remote controller may receive a video signal audio signal and or data signal from the user input interface and output the received signal as an image sound or vibrations.

The remote controller may transmit coordinate information corresponding to its movement to the image display apparatus so that a pointer may be displayed in correspondence with the movement of the remote controller on the display of the image display apparatus . Since a pointer is displayed at a shifted position according to movement in a 3D space the remote controller may be referred to as a 3D pointing device.

The block diagram of the image display apparatus illustrated in is an exemplary embodiment of the present invention. The image display apparatus is shown in as having a number of components in a given configuration. However the image display apparatus may include fewer components or more components than those shown in in alternative embodiments. Also two or more components of the image display apparatus may be combined into a single component or a single component thereof may be separated into two more components in alternative embodiments. The functions of the components of the image display apparatus as set forth herein are illustrative in nature and may be modified for example to meet the requirements of a given application.

Unlike the configuration illustrated in the image display apparatus may be configured so as to receive and playback a broadcast video through the network interface or the external device interface without the tuner and the demodulator .

Referring to the controller may include a DEMUX a video processor a processor an OSD generator a mixer a Frame Rate Converter FRC and a formatter according to an embodiment of the present invention. The controller may further include an audio processor not shown and a data processor not shown .

The DEMUX demultiplexes an input stream. For example the DEMUX may demultiplex an MPEG 2 TS into a video signal an audio signal and a data signal. The input stream signal may be received from the tuner the demodulator or the external device interface .

The video processor may process the demultiplexed video signal. For video signal processing the video processor may include a video decoder and a scaler .

The video decoder decodes the demultiplexed video signal and the scaler scales the resolution of the decoded video signal so that the video signal can be displayed on the display .

The processor may provide overall control to the image display apparatus or the controller . For example the processor may control the tuner to tune to RF broadcasting corresponding to a user selected channel or a pre stored channel.

The processor may also control the image display apparatus according to a user command received through the user input interface or an internal program. The processor may control data transmission through the network interface or the external device interface .

The processor may control operations of the DEMUX the video processor and the OSD generator in the controller .

The OSD generator generates an OSD signal autonomously or according to user input. For example the OSD generator may generate signals by which a variety of information is displayed as images or text on the display according to user input signals or control signals. The OSD signal may include various data such as a UI screen a variety of menu screens widgets icons etc.

For example the OSD generator may generate a signal by which captions are displayed for a broadcast image or EPG based broadcasting information.

Considering that the OSD generator generates an OSD signal or a graphic signal the OSD generator may be referred to as a graphic processor.

The mixer may mix the decoded video signal received from the video processor with the OSD signal received from the OSD generator and output the mixed signal to the formatter . As the decoded broadcast video signal or the external input signal is mixed with the OSD signal an OSD may be overlaid on the broadcast image or the external input image.

The FRC may change the frame rate of an input image. It is also possible for the FRC to simply output the input image without frame rate conversion.

The formatter changes the format of the signal received from the FRC to be suitable for the display . For example the formatter may convert a received signal into an RGB data signal. The RGB data signal may be output in the form of a Low Voltage Differential Signal LVDS or mini LVDS.

The formatter may change the format of a 3D video siynal or convert a 2D image to a 3D image. The audio processor not shown of the controller may process the demultiplexed audio signal. For audio signal processing the audio processor may have a plurality of decoders.

The data processor not shown of the controller may process the data signal obtained by demultiplexing the input stream signal. For example if the data siynal is an encoded signal the data processor may decode the data siynal. The coded data signal may be an EPG which includes broadcast information specifying the start time end time etc. of scheduled broadcast TV or radio programs.

The block diagram of the controller illustrated in is an embodiment of the present invention. Depending upon the specifications of the controller the components of the controller may be combined or omitted. Or new components are added to the controller .

A platform for the image display apparatus may have OS based software to implement the above described various operations according to an embodiment of the present invention.

Referring to a platform for the image display apparatus is a separate type according to an embodiment of the present invention. The platform may be designed separately as a legacy system platform and a smart system platform . An OS kernel may be shared between the legacy system platform and the smart system platform .

The legacy system platform may include a stack of a driver middleware and an application layer on the OS kernel . On the other hand the smart system platform may include a stack of a library a framework and an application layer on the OS kernel .

The OS kernel is the core of an OS. When the image display apparatus is driven the OS kernel may be responsible for operation of at least one of hardware drivers security protection for hardware and processors in the image display apparatus efficient management of system resources memory management hardware interfacing by hardware abstraction multi processing or scheduling associated with the multi processing. Meanwhile the OS kernel may further perform power management.

The hardware drivers of the OS kernel may include for example at least one of a display driver a Wireless Fidelity Wi Fi driver a Bluetooth driver a USB driver an audio driver a power manager a binder driver or a memory driver.

Alternatively or additionally the hardware drivers of the OS kernel may be drivers for hardware devices within the OS kernel . The hardware drivers may include a character device driver a block device driver and a network device driver. The block device driver may need a buffer for buffering as much data as a unit because data is transmitted in blocks. The character device driver may not need a buffer since data is transmitted on a basic data unit basis that is on a character basis.

The OS kernel may be implemented based on any of various OSs such as Unix Linux Windows etc. The OS kernel may be a general purpose open OS kernel which can be implemented in other electronic devices.

The driver is interposed between the OS kernel and the middleware . Along with the middleware the driver drives devices for operations of the application layer . For example the driver may include a driver s for a microcomputer a display module a Graphic Processing Unit GPU the FRC a General Purpose Input Output GPIO pin a High Definition Multimedia Interface HDMI a System Decoder SDEC or DEMUR a Video Decoder VDEC an Audio Decoder ADEC a Personal Video Recorder PVR and or an Inter Integrated Circuit I2C . These drivers operate in conjunction with the hardware drivers of the OS kernel . In addition the driver may further include a driver for the remote controller especially a 3D pointing device to be described below. The 3D pointing device driver may reside in the OS kernel or the middleware instead of the driver .

The middleware resides between the OS kernel and the application layer . The middleware may mediate between different hardware devices or different software programs for data transmission and reception between the hardware devices or the software programs. Therefore the middleware can provide standard interfaces support various environments and enable interaction between tasks conforming to heterogeneous communication protocols.

Examples of the middleware in the legacy system platform may include Multimedia and Hypermedia information coding Experts Group MHEG and Advanced Common Application Platform ACAP as data broadcasting related middleware PSIP or SI middleware as broadcasting information related middleware and DLNA middleware as peripheral device communication related middleware.

The application layer that runs atop the middleware in the legacy system platform may include for example UI applications associated with various menus in the image display apparatus . The application layer may allow editing and updating over a network by user selection. With use of the application layer the user may enter a desired menu among various UIs by manipulating the remote controller while viewing a broadcast program.

The application layer may further include at least one of a TV guide application a Bluetooth application a reservation application a Digital Video Recorder DVR application and a hotkey application.

In the smart system platform the library is positioned between the OS kernel and the framework forming the basis of the framework . For example the library may include Secure Socket Layer SSL being a security related library WebKit being a Web engine related library c library libc and Media Framework being a media related library specifying for example a video format and an audio format. The library may be written in C or C . Also the library may be exposed to a developer through the framework .

The library may include a runtime with a core Java library and a Virtual Machine VM . The runtime and the library form the basis of the framework .

The VM may be a virtual machine that enables concurrent execution of a plurality of instances that is multi tasking. For each application of the application layer a VM may be allocated and executed. For scheduling or interconnection between instances the binder driver not shown of the OS kernel may operate.

In the smart system platform the framework includes programs on which applications of the application layer are based. The framework is compatible with any application and may allow component reuse movement or exchange. The framework may include supporting programs and programs for interconnecting different software components. For example the framework may include an activity manager related to activities of applications a notification manager and a CP for abstracting common information between applications. This framework may be written in Java.

The application layer above the framework includes a variety of programs that are executed and displayed in the image display apparatus . The application layer may include for example a core application that is a suit having at least one solution of e mail Short Message Service SMS calendar map or browser. The application layer may be written in Java.

In the application layer applications may be categorized into user undeletable applications stored in the image display apparatus that cannot be modified and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus .

With the applications of the application layer a variety of functions such as Internet telephony Video ON Demand VOD Web album Social Networking Service SNS Location Based Service LBS map service Web browsing and application search may be performed through network access. In addition other functions such as gaming and schedule management may be performed by the applications.

Referring to a platform for the image display apparatus according to another embodiment of the present invention is an integrated type. The integrated platform may include an OS kernel a driver middleware a framework and an application layer .

Compared to the separate type platform illustrated in the integrated type platform is characterized by the absence of the library and the application layer being an integrated layer. The driver and the framework correspond to the driver and the framework of respectively.

The library of may be incorporated into the middleware . That is the middleware may include both the legacy system middleware and the image display system middleware. As described before the legacy system middleware includes MHEG or ACAP as data broadcasting related middleware PSIP or SI middleware as broadcasting information related middleware and DLNA middleware as peripheral device communication related middleware whereas the image display system middleware includes SSL as a security related library WebKit as a Web engine related library libc and Media Framework as a media related library. The middleware may further include the afore described runtime.

The application layer may include a menu related application a TV guide application a reservation application etc. as legacy system applications and e mail SMS a calendar a map and a browser as image display system applications.

In the application layer applications may be categorized into user undeletable applications that are stored in the image display apparatus and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus .

The platforms illustrated in may be general purpose ones that can be implemented in many other electronic devices as well as in the image display apparatus.

The platforms illustrated in may be stored or loaded in the memory the controller or any other processor not shown .

The user may move or rotate the remote controller up and down side to side and back and forth . Since the pointer moves in accordance with the movement of the remote controller in 3D space the remote controller may be referred to as a pointing device or 3D pointing device.

Referring to if the user moves the remote controller to the left the pointer also moves to the left on the display .

A sensor of the remote controller detects the movement of the remote controller and transmits motion information corresponding to the result of the detection to the image display apparatus . Then the image display apparatus determines the movement of the remote controller based on the motion information received from the remote controller and calculates the coordinates of a target point to which the pointer should be shifted in accordance with the movement of the remote controller based on the result of the determination. The image display apparatus then displays the pointer at the calculated coordinates.

Referring to while pressing a predetermined button of the remote controller the user moves the remote controller away from the display . Then a selected area corresponding to the pointer may be zoomed in and enlarged on the display . On the contrary if the user moves the remote controller toward the display the selection area corresponding to the pointer is zoomed out and thus contracted on the display . The opposite case is also possible. That is when the remote controller recedes from the display the selection area may be zoomed out and when the remote controller approaches the display the selection area may be zoomed in.

With the predetermined button pressed on the remote controller the up down left and right movements of the remote controller may be ignored. That is when the remote controller recedes from or advances toward the display only the back and forth movements of the remote controller may be sensed while the up down left and right movements of the remote controller may be ignored. Unless the predetermined button is pressed in the remote controller the pointer may move in accordance with the up down left or right movement of the remote controller .

The speed and direction of the pointer may correspond to the speed and direction of the remote controller .

Referring to the remote controller may include a wireless communication module a user input unit a sensor unit an output unit a power supply a memory and a controller .

The wireless communication module transmits signals to and receives signals from one of the afore described image display apparatuses according to embodiments of the present invention. The following description will be given in the context of the image display apparatus .

In the embodiment of the present invention the wireless communication module may include an RF module for transmitting RF signals to and or receiving RF signals from the image display apparatus according to an RF communication standard. The wireless communication module may also include an IR module for transmitting IR signals to and or receiving IR signals from the image display apparatus according to an IR communication standard.

The remote controller may transmit motion information regarding its movement to the image display apparatus through the RF module .

The remote controller may also receive signals from the image display apparatus through the RF module . The remote controller may transmit commands such as a power on off command a channel switching command or a sound volume change command to the image display apparatus through the IR module as needed.

The user input unit may include a keypad a plurality of buttons a touch pad and or a touch screen. The user may enter commands to the image display apparatus by manipulating the user input unit . If the user input unit includes a plurality of hard key buttons the user may input various commands to the image display apparatus by pressing the hard key buttons. Alternatively or additionally if the user input unit includes a touch screen displaying a plurality of soft keys the user may input various commands to the image display apparatus by touching the soft keys. The user input unit may also include various input tools other than those set forth herein such as a wheel key a scroll key and or a jog key which should not be construed as limiting the present invention.

The sensor unit may include a gyro sensor and or an acceleration sensor . The gyro sensor may sense the movement of the remote controller

For example the gyro sensor may sense the movement of the remote controller for example in X Y and Z axis directions and the acceleration sensor may sense the moving speed of the remote controller . The sensor unit may further include a distance sensor for sensing the distance between the remote controller and the display .

The output unit may output a video and or audio signal corresponding to a manipulation of the user input unit or a signal transmitted by the image display apparatus . The user may easily identify whether the user input unit has been manipulated or whether the image display apparatus has been controlled based on the video and or audio signal output from the output unit .

The output unit may include a Light Emitting Diode LED module which is turned on or off whenever the user input unit is manipulated or whenever a signal is received from or transmitted to the image display apparatus through the wireless communication module a vibration module which generates vibrations an audio output module which outputs audio data and a display module which outputs an image.

The power supply supplies power to the remote controller . If the remote controller is kept stationary for a predetermined time or longer the power supply may for example reduce or cut off supply of power to the remote controller in order to save power. The power supply may resume supply of power if a specific key on the remote controller is manipulated.

The memory may store various programs and application data for controlling or operating the remote controller . The remote controller may wirelessly transmit signals to and or receive signals from the image display apparatus in a predetermined frequency band through the RF module . The controller of the remote controller may store information regarding the frequency band used for the remote controller to wirelessly transmit signals to and or wirelessly receive signals from the paired image display apparatus in the memory and may then refer to this information for use at a later time.

The controller provides overall control to the remote controller . For example the controller may transmit a signal corresponding to a key manipulation detected from the user input unit or a signal corresponding to motion of the remote controller as sensed by the sensor unit to the image display apparatus through the wireless communication module .

Referring to the image display apparatus displays a first image S . The controller may control display of a content image on the display according to a user input.

For example it is possible to display various content images including a broadcast image received through the broadcasting receiver an image stored in the memory a menu image generated from the OSD generator an external input image received through the external device interface a Web page received through the network interface etc.

The image display apparatus may include an interface unit having a variety of input ports. The term interface unit may cover the afore described external device interface network interface and broadcasting receiver . That is all ports through which external images are received may collectively form the interface unit.

The HDMI port the Component port and the RGB port may be provided in the external device interface . The VOD port may reside in the wired communication module or wireless communication module of the network interface . The antenna port may be included in the broadcasting receiver .

Subsequently the image display apparatus determines whether a per input port image view input has been received S . Upon receipt of the per input port image view input the image display apparatus displays images received through a plurality of input ports S .

The controller of the image display apparatus determines whether a per input port image view input has been received. For example when a specific key of the remote controller is manipulated the controller may determine that the per input port image view input has been received. In another example the controller may determine whether the per input port image view input has been received by monitoring a user voice input a gesture or a local key.

Upon receipt of the per input port image view input the controller of the image display apparatus controls display of images received through respective input ports. Especially the controller may control display of images that are being received or have been received through the input ports on a per input port basis so that the images can be distinguished from one another according to the input ports. The controller may control overlapped display of the images that are being received or have been received through the input ports. Especially the controller may display images received through input ports available for image reception among a plurality of input ports on a per input port basis.

Because images received through a plurality of input ports are displayed overlapped with one another in such a manner that the images may be distinguished from one another according to the respective input ports as described above all of the images can be displayed at one time. Therefore user convenience can be increased.

In the broadcast image corresponding to the broadcast image illustrated in may be highlighted to indicate that it is live. While the periphery cursor of the broadcast image is shown in as bold compared to those of the other images and the highlight effect may be exerted in many other manners. For example at least one of the size periphery thickness or brightness of the broadcast image may be set to be larger than that of any other displayed image. Or the broadcast image may be displayed at a foremost position on the screen.

The images and may be still images except for the broadcast image . Especially the images and may be still images stored in the memory . More especially at least one of the images and may be a still image which is a last reproduced image displayed on the image display apparatus . Thus when an external input image is displayed on the display the memory may capture the displayed image and store the captured image periodically. Especially the memory may store only a latest playback image through periodic storage and update.

When a plurality of per input port images are displayed according to the manipulation of the input key of the remote controller the controller may control arrangement of the images in order of the latest use.

In the illustrated case of the broadcast image is placed at the foremost position followed by the RGB image the Component image and the VOD image in this order. It is noted from this arrangement that the broadcast image is now playing through the antenna port the RGB image was reproduced through the RGB port earlier than the broadcast image the Component image was reproduced through the Component port earlier than the RGB image and the VOD image was reproduced through the VOD port earlier than the Component image . In this manner the history of using external input ports is known from the image arrangement.

The controller may control display of objects indicating the respective input ports corresponding to the per input port images on the display .

In a TV object representing the antenna port an RGB object representing the RGB port a Component object representing the Component port and a VOD object representing the VOD port are displayed over the respective images and . Therefore the user can readily identify the input ports through which the per input port images to are being received or have been received.

Since all of the plurality of per input port images to are displayed on the display at one time each of the per input port images to illustrated in is smaller than the broadcast image illustrated in .

If any of the images to is a live image while not shown in an object indicating live may be displayed over the live image.

The image display apparatus determines whether one of the displayed per input port images has been selected S . Upon selection of one of the displayed per input port images the image display apparatus full screens an image corresponding to the selected input port S .

Upon receipt of an input for selecting one of the displayed per input port images the controller of the image display apparatus controls display of the image corresponding to the selected input port in full screen on the display .

For example the Component image may be selected through manipulation of a left directional key and an OK key of the remote controller in . Specifically the user may move a cursor to the Component image by pressing the left directional key twice and then may select the Component image by pressing the OK key .

Then an image received through the Component port corresponding to the selected component image may be displayed in full screen on the display as illustrated in .

Upon selection of the play object the image display apparatus may play back an image received through the Component port on the display .

When the input key of the remote controller is manipulated the three per input port images may be displayed on the display as illustrated in . illustrates exemplary sequential arrangement of a broadcast image at the foremost position followed by an RGB image and a Component image . The images and may include objects and representing the antenna port the RGB port and the Component port respectively.

Compared to a VOD image is not displayed in . In the case of an input port providing recorded images among a plurality of input ports the controller may control display of an image received through the input port on the display as far as playback of the recorded images has not ended yet.

Since the VOD image is completely played back and thus no more VOD images remain to be played back in a VOD image may not be displayed on the display despite reception of the per input port image view input.

The per input port images may be arranged in different orders from that illustrated in . For example priority may be given to the earliest reproduced image before the current input image.

Unlike it is also possible to give a highest priority to an input image reproduced and displayed shortly before the current displayed input image. That is the RGB image may be displayed at the foremost position.

The broadcast image is placed at the foremost position highlighted followed sequentially by the RGB image the Component image and the VOD image in .

The component image is placed at the foremost position at time Tc in the VOD image is placed at the foremost position at time Td in and the broadcast image returns to the foremost position at time Te in .

As the arrangement order of per input order images is changed with the passage of time the user can select an image of an intended input port simply without any special operation for example just by pressing the OK key .

In upon receipt of a per input port image view input the image display apparatus displays even an image corresponding to an unavailable external input port. Specifically since the HDMI port is not connected the HDMI image is shown as a blank image in .

In the TV object representing the antenna port the RGB object representing the RGB port the Component object representing the Component port the VOD object representing the VOD port and an HDMI object representing the HDMI port are displayed over the respective images and .

Upon receipt of the HDMI image by the left directional key and the OK key of the remote controller an object indicating that the HDMI port is not connected may be displayed over a blank image as illustrated in . Therefore the user can readily perceive that the HDMI port is not connected.

As is apparent from the above description upon receipt of a per input port image view input an image display apparatus can display images that are being received or that have been received on a per input port basis so that they are distinguished from one another according to the input ports. Since input images are displayed simply in the image display apparatus in this manner user convenience can be increased.

A plurality of per input port images can be displayed overlapped with one another so that they are distinguished from one another according to the input ports. Thus all of the per input port images can be displayed at one time thereby increasing user convenience.

Upon selection of one of the per input port images the selected image is full screened thereby enabling the user to view the input image easily.

In the case of an input port providing recorded images among the plurality of input ports corresponding to the displayed image only when playback of the recorded images has not ended yet the image display apparatus displays an image received through the input port. Accordingly the user can readily identify an input image to view.

The image display apparatus and the method for operating the image display apparatus according to the foregoing exemplary embodiments are not restricted to the exemplary embodiments set forth herein. Therefore variations and combinations of the exemplary embodiments set forth herein may fall within the scope of the present invention.

The method for operating the image display apparatus according to the foregoing exemplary embodiments may be implemented as code that can be written on a computer readable recording medium and thus read by a processor in the portable terminal and the image display apparatus. The computer readable recording medium may be any type of recording device in which data is stored in a computer readable manner. Examples of the computer readable recording medium include a ROM a RAM a CD ROM a magnetic tape a floppy disc an optical data storage and a carrier wave e.g. data transmission over the Internet . The computer readable recording medium can be distributed over a plurality of computer systems connected to a network so that computer readable code is written thereto and executed therefrom in a decentralized manner. Programs code and code segments to realize the embodiments herein can be construed by one of ordinary skill in the art.

While the present invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the following claims.

