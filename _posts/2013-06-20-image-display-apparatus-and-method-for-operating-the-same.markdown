---

title: Image display apparatus and method for operating the same
abstract: An image display apparatus and a method for operating the same are disclosed. The method for operating the image display apparatus includes displaying a home screen including at least one card object including a content list, displaying a card object generation screen if card object generation input is received, and, if at least one content item displayed on the card object generation screen is selected, adding the selected content item to a card object to be generated. Therefore, it is possible to increase user convenience.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09182890&OS=09182890&RS=09182890
owner: LG Electronics Inc.
number: 09182890
owner_city: Seoul
owner_country: KR
publication_date: 20130620
---
This application claims the priority benefit of Korean Patent Application Nos. 10 2013 0011281 and 10 2013 0011282 filed on Jan. 31 2013 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

The present invention relates to an image display apparatus and a method for operating the same and more particularly to an image display apparatus and a method for operating the same which are capable of increasing user convenience.

An image display apparatus functions to display images to a user. A user can view a broadcast program using an image display apparatus. The image display apparatus can display a broadcast program selected by the user on a display from among broadcast programs transmitted from broadcasting stations. The recent trend in broadcasting is a worldwide transition from analog broadcasting to digital broadcasting.

Digital broadcasting transmits digital audio and video signals. Digital broadcasting offers many advantages over analog broadcasting such as robustness against noise less data loss ease of error correction and the ability to provide clear high definition images. Digital broadcasting also allows interactive viewer services compared to analog broadcasting.

Therefore the present invention has been made in view of the above problems and it is an object of the present invention to provide an image display apparatus and a method for operating the same which are capable of increasing user convenience.

In accordance with an aspect of the present invention the above and other objects can be accomplished by the provision of a method for operating an image display apparatus including displaying a home screen including at least one card object including a content list displaying a card object generation screen if card object generation input is received and if at least one content item displayed on the card object generation screen is selected adding the selected content item to a card object to be generated.

In accordance with another aspect of the present invention there is provided an image display apparatus including a network interface configured to exchange data with a server a display configured to display a home screen including at least one card object including a content list and to display a card object generation screen if card object generation input is received and a controller configured to if at least one content item displayed on the card object generation screen is selected add the selected content item to a card object to be generated.

Exemplary embodiments of the present invention will be described with reference to the attached drawings.

The terms module and unit attached to describe the names of components are used herein to help the understanding of the components and thus they should not be considered as having specific meanings or roles. Accordingly the terms module and unit may be used interchangeably.

An image display apparatus described in the present specification is for example an intelligent image display apparatus including not only a broadcast reception function but also a computer support function and includes a more conveniently used interface such as a handwriting type input device a touchscreen or a 3D pointing device by adding an Internet function while accurately performing the broadcast reception function. In addition the image display apparatus is connected to the Internet or a computer by a wired or wireless Internet module so as to perform functions such as email web browsing banking or games. For such various functions a standardized general purpose operating system OS may be used.

Accordingly the image display apparatus of the present invention may perform various user friendly functions because various applications may be freely added to or deleted from a general purpose OS kernel. For example the image display apparatus of the present invention may be a smart TV.

Referring to the image display apparatus according to the embodiment of the present invention displays an image and includes a display of . The image display apparatus may include a camera for capturing an image of a user.

Although a camera is placed on an upper side of the image display apparatus in the camera may be placed at various locations. Unlike the image display apparatus and the camera may be mounted as separate devices.

The image display apparatus may exchange data with adjacent external devices such as a home appliance a home server a mobile terminal etc. or may share predetermined content data with the adjacent external devices. The home appliance may include a set top box audio equipment a refrigerator a cleaner an air conditioner a washing machine a cooker etc.

The image display apparatus may exchange data with external servers . . . over a network . The external serves . . . may be content providers for providing a variety of content.

Unlike the figure the image display apparatus may exchange data with the mobile terminal over the network .

The image display apparatus may operate in correspondence with a remote control signal from a remote controller . The image display apparatus and the remote controller may exchange data through a pairing operation.

In particular the image display apparatus according to the embodiment of the present invention may display a pointer corresponding to movement of the remote controller or display letters by pressing a letter key of the remote controller by data exchange.

The image display apparatus described in the present specification may include a TV receiver a monitor a projector a laptop computer a digital broadcast terminal etc.

The image display apparatus according to the embodiment of the present invention displays an image and may include a fixed image display apparatus or a mobile image display apparatus.

First referring to operation keys such as a power key may be placed on the first surface front surface of the remote controller.

The various operation keys will now be described. The power key is used to turn the image display apparatus on off. A home key is used to display a home screen if the home screen of the image display apparatus is set. A search key may be used to display a search window on the image display apparatus or to search by keyword.

Four direction keys are used to move a pointer or a cursor up down right and left and an up key a down key a left key and a right key may be integrally formed. A wheel key may be placed in the center of the four direction keys .

The wheel key is used to move a screen or an item displayed on the image display apparatus . The wheel key may move up and down and thus the screen or the item of the image display apparatus may move up and down.

A back key is used to move a screen or an item displayed on the image display apparatus to a previous screen or a previous item. A menu key is used to display a set menu of the image display apparatus . A pointer key is used to display a pointer on the image display apparatus .

A 3D key may be used to switch a two dimensional 2D image displayed on the image display apparatus to a three dimensional 3D image or may be used to display a 3D image list which is able to be displayed on the image display apparatus .

A PIP key is used to display a plurality of images on the image display apparatus . By manipulating the PIP key a plurality of images may be displayed on the display in a picture in picture PIP manner. Alternatively a plurality of images may be arranged in parallel.

Any one of a plurality of images may float such that the location of the image is changed. In this case a PIP image may be referred to as a dynamic screen image.

In the figure a pointer key for displaying a pointer a guide key for displaying a guide a mute key a color key etc. are further displayed.

Next referring to a second surface back surface of the remote controller may be opposite to the first surface front surface of the remote controller . A letter key and a display may be placed on the second surface back surface of the remote controller .

The letter key may include a numeric key and an alphabetic key . The letter key may further include an enter key a function key a spacebar key etc.

If the letter key is manipulated the remote controller transmits letter key information to the image display apparatus .

The remote controller may transmit coordinate information corresponding to movement of the remote controller to the image display apparatus . Thus the pointer corresponding to the movement of the remote controller may be displayed on the display of the image display apparatus. Since the pointer is moved according to the movement of the remote controller in a 3D space the remote controller may be referred to as a 3D pointing device.

Referring to the image display apparatus according to the embodiment of the present invention includes a broadcast reception unit a network interface an external device interface a memory a user input interface a controller a display an audio output unit a power supply and a camera . The broadcast reception unit may include a tuner unit and a demodulator . Alternatively the broadcast reception unit may further include a network interface .

The tuner unit tunes to a Radio Frequency RF broadcast signal corresponding to a channel selected by a user from among RF broadcast signals received through an antenna or RF broadcast signals corresponding to all channels previously stored in the image display apparatus. The tuned RF broadcast is converted into an Intermediate Frequency IF signal or a baseband Audio Video AV signal.

For example the tuned RF broadcast signal is converted into a digital IF signal DIF if it is a digital broadcast signal and is converted into an analog baseband AV signal Composite Video Banking Sync Sound Intermediate Frequency CVBS SIF if it is an analog broadcast signal.

The tuner unit may sequentially select a number of RF broadcast signals corresponding to all broadcast channels previously stored in the image display apparatus by a channel storage function from a plurality of RF signals received through the antenna and may convert the selected RF broadcast signals into IF signals or baseband A V signals.

The demodulator receives the digital IF signal DIF from the tuner unit and demodulates the digital IF signal DIF.

The demodulator may perform demodulation and channel decoding thereby obtaining a stream signal TS. The stream signal may be a signal in which a video signal an audio signal and a data signal are multiplexed.

The stream signal output from the demodulator may be input to the controller and thus subjected to demultiplexing and A V signal processing. The processed video and audio signals are output to the display and the audio output unit respectively.

The external device interface may connect an external device and the image display apparatus . For connection the external device interface may include an A V Input Output I O unit not shown .

The external device interface may be connected to an external device such as a Digital Versatile Disc DVD player a Blu ray player a game console a camera a camcorder or a computer e.g. a laptop computer wirelessly or by wire so as to perform an input output operation with respect to the external device.

The A V I O unit may include a universal serial bus USB port a composite video banking sync CUBS port a component port a S video port analog a Digital Visual Interface DVI port a High Definition Multimedia Interface HDMI port a Red Green Blue RGB port a D SUB port etc. in order to provide audio and video signals received from the external device to the image display apparatus .

The external device interface may be connected to various set top boxes via at least one of the above described various ports to perform transmit and receive data to and from the set to boxes.

The network interface serves as an interface between the image display apparatus and a wired wireless network such as the Internet. The network interface may receive content or data provided by an Internet or content provider or a network operator over a network.

The network interface may access a predetermined web page over a connected network or another network linked to the connected network. That is the network interface access a predetermined web page to transmit or receive data to or from a corresponding server. In addition the network interface may receive content or data provided by a content provider or a network operator.

The network interface may select and receive a desired application among applications opened to the public over a network.

The network interface may include a wired communication unit not shown or a wireless communication unit not shown .

The wireless communication unit may perform short range wireless communication with another electronic apparatus. The image display apparatus may be connected to another electronic apparatus over a network according to a communication standard such as Bluetooth Radio Frequency Identification RFID InfraRed Data Association IrDA Ultra Wideband UWB ZigBee Digital Living Network Alliance DLNA etc.

The memory may store various programs necessary for the controller to process and control signals and may also store processed video audio and data signals.

The memory may temporarily store a video audio and or data signal received from the network interface or the external device interface . The memory may store information about a predetermined broadcast channel by the channel storage function of a channel map.

In addition the memory may store an application or an application list received from the network interface or the external device interface .

The image display apparatus may play a content file a moving image file a still image file a music file a text file an application file etc. stored in the memory back to be provided to a user.

While the memory is shown in as being configured separately from the controller to which the present invention is not limited the memory may be incorporated into the controller .

The user input interface transmits a signal input by the user to the controller or transmits a signal received from the controller to the user.

For example the user input interface may transmit receive various user input signals such as a power on off signal a channel selection signal and a screen setting signal from a remote controller may provide the controller with user input signals received from local keys not shown such as inputs of a power key a channel key and a volume key and setting values or provide the controller with a user input signal received from a sensor unit not shown for sensing a user gesture or transmit a signal received from the controller to a sensor unit not shown .

The controller may demultiplex the stream signal received from the tuner unit the demodulator or the external device interface into a number of signals process the demultiplexed signals into audio and video data and output the audio and video data.

The video signal processed by the controller may be displayed as an image on the display . The video signal processed by the controller may also be transmitted to an external output device through the external device interface .

The audio signal processed by the controller may be output to the audio output unit . Also the audio signal processed by the controller may be transmitted to the external output device through the external device interface .

While not shown in the controller may include a DEMUX a video processor etc. which will be described in detail later with reference to .

The controller may control the overall operation of the image display apparatus . For example the controller controls the tuner unit to tune to an RF signal corresponding to a channel selected by the user or a previously stored channel.

The controller may control the image display apparatus by a user command input through the user input interface or an internal program. In particular the controller may be connected to the network to download an application or application list desired by a user into the image display apparatus.

For example the controller controls the tuner unit such that a signal of a channel selected according to a predetermined channel selection command received through the user input interface is received and processes the video audio or data signal of the selected channel. The controller may output the processed video or audio signal such as the channel information selected by the user through the display or the audio output unit .

As another example the controller may output through the display or the audio output unit a video signal or an audio signal from an external device such as a camera or a camcorder received through the external device interface according to an external device image playback command received through the user input interface .

The controller may control the display to display images. The image displayed on the display may be a Two Dimensional 2D or Three Dimensional 3D still or moving image.

The controller may generate and display a predetermined object of an image displayed on the display as a 3D object. For example the object may be at least one of a screen of an accessed web site newspaper magazine etc. an electronic program guide EPG various menus a widget an icon a still image a moving image text etc.

The controller recognizes the position of the user based on an image captured by a camera unit not shown . For example a distance z axis coordinate between the user and the image display apparatus may be detected. An x axis coordinate and a y axis coordinate in the display corresponding to the position of the user may be detected.

If an application view menu item is selected the controller may control display of applications or a list of applications that are available in the image display apparatus or downloadable from an external network.

The controller may control installation and execution of an application downloaded from the external network along with various user interfaces. Also the controller may control display of an image related to the executed application on the display upon user selection.

The controller may receive a user image captured by the camera . The controller may recognize the user based on the captured user image and control the recognized user to log in to the image display apparatus . The controller may provide a service to each user who logs in to the image display apparatus.

Alternatively the controller may recognize a user gesture from a user image captured by the camera . In particular the controller may recognize the face and hand of the user from the captured image and recognize a specific gesture.

The display converts a video signal a data signal or an OSD signal processed by the controller or a video signal and a data signal received by the external device interface into RGB signals and generates a drive signal.

The display may be various types of displays such as a Plasma Display Panel PDP a Liquid Crystal Display LCD an Organic Light Emitting Diode OLED display a flexible display and a 3D display.

The display may also be a touchscreen that can be used not only as an output device but also as an input device.

The audio output unit may receive a processed audio signal from the controller and output the received audio signal as sound.

The power supply supplies power to the image display apparatus . Particularly the power supply may supply power to the controller which may be implemented as a System On Chip SOC the display for displaying an image and the audio output unit for outputting the audio signal.

For supplying power the power supply may include a converter not shown for converting Alternating Current AC into Direct Current DC . If the display is implemented as for example a liquid crystal panel having a plurality of backlight lamps the power supply may further include an inverter not shown capable of performing Pulse Width Modulation PWM for luminance change or dimming driving.

The camera may capture an image of a user and transmit the captured image to the controller of the image display apparatus . Although the number of cameras is 1 in a plurality of cameras may be included. The camera may be a 2D camera or a 3D camera.

The remote controller transmits user input to the user input interface . For transmission of user input the remote controller may use various communication techniques such as RF communication IR communication Bluetooth Ultra Wideband UWB and ZigBee.

In addition the remote controller may receive a video signal an audio signal or a data signal from the user input interface . The remote controller output the received signals visually audibly or through vibrations based on the received video audio or data signal.

The block diagram of the image display apparatus illustrated in is only exemplary. Depending upon the specifications of the image display apparatus in actual implementation the components of the image display apparatus may be combined or omitted or new components may be added. That is two or more components may be incorporated into one component or one component may be configured as separate components as needed. In addition the function of each block is described for the purpose of describing the embodiment of the present invention and thus specific operations or devices should not be construed as limiting the scope and spirit of the present invention.

Unlike the image display apparatus may not include the tuner unit and the demodulator shown in and may receive broadcast content via the network interface or the external device interface and play the broadcast content back.

Referring to the controller according to the embodiment of the present invention may include a DEMUX a video processor a processor an OSD generator a mixer a Frame Rate Converter FRC and a formatter . The controller may further include an audio processor not shown and a data processor not shown .

The DEMUX demultiplexes an input stream. For example the DEMUX may demultiplex an MPEG 2 TS into a video signal an audio signal and a data signal. The stream signal input to the DEMUX may be received from the tuner unit the demodulator or the external device interface .

The video processor may process the demultiplexed video signal. For video signal processing the video processor may include a video decoder and a scaler .

The video decoder decodes the demultiplexed video signal and the scaler scales the resolution of the decoded video signal so that the video signal can be displayed on the display .

The processor may control the overall operation of the image display apparatus or the controller . For example the processor controls the tuner unit to tune to an RF signal corresponding to a channel selected by the user or a previously stored channel.

The processor may control the image display apparatus by a user command received through the user input interface or an internal program.

The processor may control data transmission of the network interface or the external device interface .

The processor may control the operation of the DEMUX the video processor and the OSD generator of the controller .

The OSD generator generates an OSD signal autonomously or according to user input. For example the OSD generator may generate signals by which a variety of information is displayed as graphics or text on the display according to user input signals or control signals. The OSD signal may include various data such as a User Interface UI a variety of menus widgets icons etc.

The OSD generator may generate a signal for displaying broadcast information based on a caption or EPG of a broadcast image.

The OSD generator generates an OSD signal or a graphic signal and thus may be referred to as a graphics processing unit.

The mixer may mix the decoded video signal processed by the video processor with the OSD signal generated by the OSD generator . The mixed signal is provided to the formatter . By mixing the decoded broadcast image signal or the external input signal and the OSD signal the OSD may be overlaid and displayed on the broadcast image or the OSD or the external input image.

The FRC may change the frame rate of an input image. The FRC may maintain the frame rate of the input image without frame rate conversion.

The formatter changes the signal output from the FRC to be suitable for the display . For example the formatter may convert a received signal into an RGB data signal and output the RGB data signal. The RGB data signal may be output in the form of a Low Voltage Differential Signal LVDS or mini LVDS.

The formatter may change the format of a 3D video signal or convert a 2D video signal into a 3D video signal.

The audio processor not shown of the controller may process the demultiplexed audio signal. For audio signal processing the audio processor may have various decoders.

The audio processor not shown of the controller may also adjust the bass treble or volume of the audio signal.

The data processor not shown of the controller may process the demultiplexed data signal. For example if the demultiplexed data signal was encoded the data processor may decode the data signal. The encoded data signal may be Electronic Program Guide EPG information including broadcasting information such as the start time and end time of broadcast programs of each channel.

The block diagram of the controller shown in is exemplary. The components of the block diagrams may be integrated or omitted or a new component may be added according to the specifications of the controller .

The platform of the image display apparatus according to the embodiment of the present invention may include OS based software in order to perform the above described various operations.

First referring to the platform of the image display apparatus according to an embodiment of the present invention is a separate type according to an exemplary embodiment of the present invention. The platform may be designed separately as a legacy system platform and a smart system platform . An OS kernel may be shared between the legacy system platform and the smart system platform .

The legacy system platform may include a driver middleware and an application layer on the OS kernel . The smart system platform may include a library a framework and an application layer on the OS kernel .

The OS kernel is a core of an operating system. When the image display apparatus is driven the OS kernel may be responsible for at least one of hardware driver driving security protection for hardware and processors in the image display apparatus efficient management of system resources memory management hardware interfacing by hardware abstraction multi processing and scheduling associated with the multi processing. Meanwhile the OS kernel may further perform power management.

The hardware drivers of the OS kernel may include for example at least one of a display driver a Wi Fi driver a Bluetooth driver a USB driver an audio driver a power manager a binder driver and a memory driver.

The hardware drivers of the OS kernel may be drivers for hardware devices within the OS kernel and include a character device driver a block device driver and a network device driver. The block device driver may require a buffer for buffering data on a block basis because data is transmitted on a block basis. The character device driver may not require a buffer since data is transmitted on a basic data unit basis that is on a character basis.

The OS kernel may be implemented based on any of various OSs such as Unix Linux Windows etc. The OS kernel may be a general purpose open OS kernel that can be implemented in other electronic devices.

The driver is installed between the OS kernel and the middleware . Along with the middleware the driver drives devices for operations of the application layer . For example the driver may include a driver s for a microcomputer a display module a graphics processing unit GPU the FRC a General Purpose Input Output GPIO pin a High Definition Multimedia Interface HDMI a System Decoder SDEC or DEMUX a Video Decoder VDEC an Audio Decoder ADEC a Personal Video Recorder PVR and or an Inter Integrated Circuit I2C . These drivers operate in interaction with the hardware drivers of the OS kernel .

In addition the driver may further include a driver for the remote controller especially a below described 3D pointing device. The driver for the 3D pointing device may reside in the OS kernel or the middleware instead of the driver .

The middleware is located between the OS kernel and the application layer . The middleware may mediate between different hardware devices or different software programs for data transmission and reception between the hardware devices or software programs. Therefore the middleware can provide standard interfaces support various environments and enable interaction between tasks conforming to heterogeneous communication protocols.

Examples of the middleware in the legacy system platform may include Multimedia and Hypermedia information coding Experts Group MHEG and Advanced Common Application Platform ACAP as data broadcasting related middleware PSIP or SI middleware as broadcast information related middleware and Digital Living Network Alliance DLNA middleware as peripheral device communication related middleware.

The application layer that resides on the middleware in the legacy system platform may include for example UI applications associated with various menus in the image display apparatus . The application layer that resides on the middleware may allow editing and updating over a network by user selection. With use of the application layer the user may enter a desired menu among various UIs by manipulating the remote controller during viewing of a broadcast program.

The application layer in the legacy system platform may further include at least one of a TV guide application a Bluetooth application a reservation application a Digital Video Recorder DVR application and a hotkey application.

In the smart system platform the library is located between the OS kernel and the framework forming the basis of the framework . For example the library may include a Secure Socket Layer SSL being a security related library WebKit being a Web engine related library c library libc and Media Framework being a media related library such as specifying a video format and an audio format. The library may be written in C or C . Additionally the library may be accessible to a developer through the framework .

The library may include a runtime with a core Java library and a Virtual Machine VM . The runtime and the library form the basis of the framework .

The VM may be a virtual machine that enables concurrent execution of a plurality of instances that is multi tasking. For each application of the application layer a VM may be allocated and executed. For scheduling or interconnection between instances the binder driver not shown of the OS kernel may operate.

In the smart system platform the framework includes programs on which applications of the application layer are based. The framework is compatible with any application and may allow component reuse movement or exchange. The framework may include support programs and programs for interconnection of different software components. For example the framework may include a resource manager an activity manager related to activities of applications a notification manager and a content provider CP for abstracting common information between applications. This framework may be written in Java.

The application layer on top of the framework includes a variety of programs that are executed and displayed in the image display apparatus . The application layer may include for example a core application that has at least one of an e mail Short Message Service SMS calendar map and browser. Function may be provided. The application layer may be written in Java.

In the application layer applications may be categorized into user undeletable applications stored in the image display apparatus and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus .

With the applications of the application layer a variety of functions may be performed by network access including Internet telephony VoD Web album Social Networking Service SNS Location Based Service LBS map service Web browsing and application search. In addition the user may enjoy games and manage schedules using applications.

Referring to a platform for the image display apparatus according to another embodiment of the present invention is an integrated type platform. The integrated type platform may include an OS kernel a driver middleware a framework and an application layer .

Compared to the separate type platform illustrated in the integrated type platform of is characterized by the absence of the library and the application layer being an integrated layer. The driver and the framework correspond to the driver and the framework of respectively.

The library of may be incorporated into the middleware . That is the middleware may include both the legacy system middleware and the image display system middleware. As described above the legacy system middleware includes MHEG or ACAP as data broadcasting related middleware PSIP or SI middleware as broadcast information related middleware and DLNA middleware as peripheral device communication related middleware whereas the image display system middleware includes SSL as a security related library WebKit as a Web engine related library WebKit libc and Media Framework as a media related library. The middleware may further include the above described runtime.

The application layer may include menu related applications a TV guide application a reservation application etc. as legacy system applications and e mail SMS a calendar a map and a browser as image display system applications.

In the application layer applications may be categorized into user undeletable applications that are stored in the image display apparatus and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus .

The platforms illustrated in may be general purpose ones that can be implemented in many other electronic devices as well as in image display apparatuses.

The platforms illustrated in may be loaded on the memory the controller or any other processor not shown .

First FIG. A a shows the case in which the pointer is displayed in correspondence with the remote controller at a predetermined position of the display .

The user may move the remote controller up and down side to side FIG. A b and back and forth FIG. A c . The pointer displayed on the display of the image display apparatus moves in accordance with the movement of the remote controller . In this context the remote controller may be referred to as a pointing device or a 3D pointing device.

Referring to FIG. A b if the user moves the remote controller to the left the pointer displayed on the display of the image display apparatus moves to the left accordingly.

Information about the movement of the remote controller sensed by the sensor of the remote controller is transmitted to the image display apparatus. The image display apparatus may calculate the coordinates of the pointer from the information about the movement of the remote controller . Then the image display apparatus may display the pointer at the calculated coordinates.

Referring to FIG. A c while pressing a predetermined button of the remote controller the user moves the remote controller away from the display . Then a selection area corresponding to the pointer may be zoomed in upon and enlarged on the display . On the contrary if the user moves the remote controller toward the display the selection area corresponding to the pointer is zoomed out and thus contracted on the display . Alternatively when the remote controller moves away from the display the selection area may be zoomed out and when the remote controller approaches the display the selection area may be zoomed in on.

With the predetermined button pressed in the remote controller the up down left and right movements of the remote controller may be ignored. That is when the remote controller moves away from or approaches the display only the back and forth movements of the remote controller are sensed while the up down left and right movements of the remote controller are ignored. Unless the predetermined button is pressed in the remote controller the pointer moves in accordance with the up down left or right movement of the remote controller .

The speed and direction of the pointer may correspond to the speed and direction of the remote controller .

For example if a first alphabetic key a second alphabetic key and a third alphabetic key of the letter key are sequentially manipulated the remote controller transmits the key information corresponding thereto to the image display apparatus . Then the image display apparatus may display the corresponding characters abc in a display window .

Referring to the remote controller may include a radio transceiver a user input portion a sensor portion an output portion a power supply a memory and a controller .

The radio transceiver transmits and receives signals to and from any one of the image display apparatuses according to the embodiments of the present invention. Among the image display apparatuses according to the embodiments of the present invention for example one image display apparatus will be described.

In accordance with the exemplary embodiment of the present invention the radio transceiver may be provided with an RF module for transmitting and receiving signals to and from the image display apparatus according to an RF communication standard. Additionally the radio transceiver may include an IR module for transmitting and receiving signals to and from the image display apparatus according to an IR communication standard.

In the present embodiment the remote controller may transmit information about movement of the remote controller to the image display apparatus via the RF module .

The remote controller may receive the signal from the image display apparatus via the RF module . The remote controller may transmit commands associated with power on off channel switching volume change etc. to the image display apparatus through the IR module .

In the present embodiment the user input portion may include an operation key input portion for performing operation key input and a letter key input portion for performing letter key input.

The operation key input portion may include various operation keys placed on the front surface of the remote controller as described with reference to . The operation key input portion may include for example the power key the home key the search key the four direction key the wheel key the back key the menu key the volume key the 3D key the channel key etc.

The letter key input portion may include various letter keys placed on the back surface of the remote controller as described with reference to . The letter key input portion may include for example the numeric key the alphabetic key etc.

The user may enter a command for remotely controlling the image display apparatus to the remote controller by manipulating the user input portion . If the user input portion includes hard keys the user may enter commands related to the image display apparatus to the remote controller by pushing the hard keys. If the user input portion is provided with a touchscreen the user may enter commands related to the image display apparatus to the remote controller by touching soft keys on the touchscreen. Additionally the user input portion may have a variety of input means which may be manipulated by the user such as a scroll key a jog key etc. to which the present invention is not limited.

The sensor portion may sense and output motion information of the remote controller. The sensor portion may include a gyro sensor or an acceleration sensor .

The gyro sensor may sense information about movement of the remote controller . For example the gyro sensor may sense information about movement of the remote controller along x y and z axes.

The acceleration sensor may sense information about the velocity of the remote controller . For example the acceleration sensor may sense information about the speed of the remote controller along x y and z axes.

The sensor portion may further include a distance measurement sensor for sensing a distance from the display .

The motion information output from the sensor portion may include the information about movement of the remote controller from the gyro sensor and the information about the speed of the remote controller from the acceleration sensor and further include the distance information.

The output portion may output a video or audio signal corresponding to manipulation of the user input portion or a signal transmitted by the image display apparatus . The user may be aware from the output portion as to whether the user input portion has been manipulated or the image display apparatus has been controlled.

For example the output portion may include a Light Emitting Diode LED module for illuminating when the user input portion has been manipulated or a signal is transmitted to or received from the image display apparatus through the radio transceiver a vibration module for generating vibrations an audio output module for outputting audio or a display module for outputting video.

The power supply supplies power to the remote controller . When the remote controller is kept stationary for a predetermined time the power supply blocks power from the remote controller thereby preventing waste of power. When a predetermined key of the remote controller is manipulated the power supply may resume power supply.

The memory may store a plurality of types of programs required for control or operation of the remote controller or application data. When the remote controller transmits and receives signals to and from the image display apparatus wirelessly through the RF module the remote controller and the image display apparatus perform signal transmission and reception in a predetermined frequency band. The controller of the remote controller may store information about the frequency band in which to wirelessly transmit and receive signals to and from the image display apparatus paired with the remote controller in the memory and refer to the information.

The controller may transmit a signal corresponding to predetermined key manipulation on the user input portion or a signal corresponding to an movement of the remote controller sensed by the sensor portion to the image display apparatus through the radio transceiver .

The user input interface of the image display apparatus receives key manipulation information or motion information. The user input interface may have a radio transceiver .

The radio transceiver may include an RF module for performing RF communication with the remote controller and an IR module for performing IR communication with the remote controller .

The user input interface may further include coordinate calculator for calculating the coordinates of the pointer using information corresponding to movement of the remote controller .

The coordinates of the pointer may be calculated by the controller instead of the coordinate calculator . For calculation of the coordinates of the pointer the user input interface may send the information corresponding to movement of the remote controller to the controller .

If a home screen is set to be displayed when the image display apparatus is powered on the home screen may be automatically displayed when the image display apparatus is powered on. Alternatively if home screen display input is received based on the remote controller a local key not shown user voice a user gesture etc. the controller may display the home screen on the display .

The home screen may include a dashboard area including card objects each including content and a launcher bar area including frequently used application items.

Movable replaceable switchable card objects may be placed in the dashboard area . An object not shown indicating a logged in user and time information may be displayed in the dashboard area .

A live broadcast image may be displayed in the live TV card object . In addition live broadcast information an external input object capable of selecting external input a settings object for setting the image display apparatus and an advertisement image may be further displayed.

The live broadcast image may be a broadcast image extracted from a live broadcast signal received by the above described broadcast reception unit . In particular the live broadcast signal may be received through the tuner unit of the broadcast reception unit or the network interface .

Broadcast information related to a live broadcast program may be program guide information of a broadcast signal or broadcast information separately received from a broadcast station server or another server over a network.

If the external input object capable of selecting external input is selected a screen for selecting an external input image received through an HDMI port a VOD port a component port an RGB port or an antenna port among various input ports of the image display apparatus may be displayed.

If the settings object for setting the image display apparatus is selected a settings screen for setting the image display apparatus may be displayed.

The advertisement image may be based on an advertisement included in a broadcast signal an advertisement provided by a network provider for providing a network to the image display apparatus or an advertisement provided by a broadcast station for providing a broadcast image to the image display apparatus .

The premium apps card object may include a card object name and a content list . In particular the content list may include content items provided by a manufacturer of the image display apparatus . In the figure application items are shown as content items and are installed in the image display apparatus in advance. If any one application item of the content list is selected an application corresponding to the application item may be executed and a screen on which the application is executed may be displayed on the display .

The content items and more particularly the application items of the premium apps card object may be displayed to be distinguished from other application items when the overall application list is displayed.

The 3D world card object may include a card object name and a content list . In particular the content list may include 3D content items. The 3D content items may be shortcut items for 3D content execution. If any one 3D content item of the content list is selected 3D content corresponding to the 3D content item is played back and a screen on which the 3D content may be played back may be displayed on the display .

Although three card objects and are shown in if an additional card object is further present a portion of the additional card object may be displayed on the display as shown in . Therefore the user can be intuitively aware that the additional card object to be searched for is present.

The tube card object of may include a card object name an object indicating content list switching and a content list corresponding to any one subcategory.

In particular the content list may include content items stored in a server managed by a video provider.

In order to display predetermined content items among a plurality of content items stored in the server managed by the video provider in the tube card object subcategories associated with genre date region age and gender may be set. Content lists may be separately configured according to such subcategories.

The content list of the tube card object shown in may be a content list including recently featured items. That is a first content list corresponding to a first subcategory may be displayed.

If the object indicating content list switching is selected the content list of the tube card object may be a content list including most viewed items a content list including trending video items or a content list including 3D content items.

The smart share card object of may include a card object name an object indicating content list switching and a content list corresponding to any one subcategory.

In particular the content list may be a content list including content items stored in an adjacent electronic apparatus.

In order to display predetermined content items among a plurality of content items stored in the adjacent electronic apparatus in the smart share card object subcategories associated with genre date etc. may be set. Content lists may be separately configured according to such subcategories.

The content list of the smart share card object shown in is a content list including new content items.

If the object indicating content list switching is selected the content list of the smart share card object may be a content list including movie content items a content list including photo content items or a content list including music content items.

The my interest card object of may include a card object name an object for setting interesting content and a content list corresponding to any one interesting item.

In particular the content list may be a content list including content items provided by a specific server.

In order to display predetermined content items among a plurality of content items provided by the specific server in the my interest card object subcategories associated with genre date etc. may be set. Content lists may be separately configured according to such subcategories.

The content list of the my interest card object shown in is a content list including world news items.

If top stories and business items are further set in addition to the world news items by selection of the object for setting interesting content the content list displayed in the object for setting interesting content may be a content list including world news items a content list including top stories news items or a content list including business news items.

The application list of the launcher bar area may be displayed without change when the home screen is switched for example when the home screen of is switched to the home screen of .

For example the video item the application store item the web item the search item etc. may not be deleted and the TV item the 3D item etc. may be edited or deleted.

The application list screen including a plurality of application items may be displayed on the image display apparatus as a full screen as shown in .

At this time if an additional application item to be displayed is further present a portion of the additional application item to be displayed may be displayed on the display . In the portion of the additional application item to be displayed is displayed in a lower region of the application list screen . Therefore the user can be intuitively aware that the additional application item to be searched for is present.

Unlike the figure the portion of the additional application item to be displayed may be displayed in a right region of the application list screen .

Selection focusing etc. of the application item may be changed by direction key input of the remote controller in addition to the pointer based on movement of the remote controller .

In the figure a cursor is located on a predetermined application item according to direction key input of the remote controller . If direction key input of the remote controller is received the pointer based on movement of the remote controller may not be displayed.

Next shows an application list screen according to screen movement. If screen downward movement input is received on the application list screen of the application list screen of may be displayed. Screen movement input may be pointer input direction key input or scroll bar input etc. In the figure the cursor is located on a predetermined application item according to the direction key input of the remote controller .

The shared content according to the embodiment of the present invention may include content stored in an electronic apparatus connected to the image display apparatus and may include other content for example content stored in an external server over a network. More specifically if a first user logs in to the image display apparatus the first user may share content stored in the electronic apparatus connected to the image display apparatus or the content stored in the external server in the smart share card object or on the smart share screen . For sharing the first user requires to log in to the external server. Alternatively the login of the external server may be automatically performed when the user logs in to the image display apparatus . Therefore it is possible to further activate a content sharing function.

The smart share screen of includes a home network content list and an external network content list . shows the case in which the user logs in to the image display apparatus through the camera such that an icon indicating the user is displayed on the smart share screen

The settings object may be displayed on the smart share screen . Various settings may be performed through the settings object . For example content sharing is set to be restricted to the home network or to extend to the external network. As another example shared content may be set to be displayed on a per user basis or all shared content may be set to be displayed regardless of the user. Alternatively shared content may be set to be displayed on a per age basis. Alternatively a lock function may be set to be activated on a per content basis. Alternatively subcategories other than new movie photo and music may be further set. Alternatively only newly added content may be set to be displayed by setting new shared content. A synchronization period with a home network may be set. Upon shared content update a time when a content list is displayed may be set. For example if a new content list is received through a home network the new content list may be immediately displayed. Alternatively a content list to be displayed may be updated at a predetermined time interval and a new content list may be displayed upon update.

In the figure a refrigerator item a laptop item and a home server item are included in the list of electronic apparatuses connected to the image display apparatus and a tablet item a computer item and a washing machine item are included in the list of electronic apparatuses which are not connected to the image display apparatus .

If the computer item is selected from the list of electronic apparatuses that are not connected to the image display apparatus a separate menu may be displayed and thus a remote power on operation of the computer may be performed.

A card object corresponding to the smart share screen shown in may be displayed on the home screen. Therefore it is possible to easily confirm electronic apparatuses connected to the image display apparatus and electronic apparatuses which are not connected to the image display apparatus .

The image display apparatus determines whether card object generation input is received S and displays a card object generation screen S if it is determined that card object generation input is received.

In order to generate a card object in a state of displaying the home screen the settings object for setting the image display apparatus on the home screen may be selected.

The settings screen may include a home dashboard edit item a customize home item a home and all apps settings item and a system settings item .

Then as shown in a home dashboard edit screen for editing the dashboard area of the home screen may be displayed. At this time the launcher bar area may be empty.

The home dashboard edit screen is similar to the home screen of but is different therefrom in that card objects and may be edited. Unlike the home dashboard edit screen may further include a card object generation item and an edit completion item .

On the home dashboard edit screen content list settings of a specific card object may be changed a card object name may be changed or the position of a card object may be changed.

For display of the home dashboard edit screen of the home dashboard edit screen may be displayed using other methods instead of selection of the settings object of the home screen and selection of the home dashboard edit item of the settings screen .

For example if the pointer is located in any one of the card objects and in a state of displaying the home screen of and then long tap or long press input is received as shown in the home dashboard edit screen for editing the dashboard area may be displayed on the home screen.

As another example if the menu key of the remote controller is manipulated in a state of displaying the home screen of the settings screen related to the image display apparatus shown in may be displayed. If the home dashboard edit item is selected the home dashboard edit screen may be displayed.

As another example if the menu key of the remote controller is manipulated in a state in which the pointer of the remote controller is located in the dashboard area of the home screen of the home dashboard edit screen for editing the dashboard may be immediately displayed.

The card object generation screen may include a first region including a card object to be generated and a second region for displaying an application list .

The card object to be generated may include an icon associated with a user of a generated card object a card object name input window an application area in which application items are placed a generation completion item etc.

The icon associated with the user of the generated card object may indicate a user who generates the card object or a user who will use the generated card object. The icon may be set by selecting any one of an icon list or may be set to include an image of a user captured using the camera .

As a method of adding an application to the application area a predetermined application item of the application list may be added to the application area by dragging and dropping of the pointer .

Alternatively as shown in in the case in which each of the application items displayed in the application list includes a selection window when a selection window is selected an application item corresponding thereto may be automatically added to the application area .

In the application area application items and corresponding to the selected application items and may be displayed.

For example a card object name may be entered using the letter key placed on the back surface of the remote controller . As another example if the pointer is located on the card object name input window a screen keyboard may be displayed on the display and thus the card object name may be entered. Alternatively the card object name may be entered based on voice input using a microphone not shown included in the remote controller .

In this case as shown in a card object generation completion message may be displayed. Therefore the user may be aware that card object generation has been normally completed.

Next after card object generation has been completed the home screen may be displayed. In particular the home screen including the generated card object may be displayed.

When the card object is generated as shown in the icon associated with the user of the generated card object may be based on the captured image of the user. For example the image of the user may be captured using the camera a user face area may be extracted from the captured image and the icon associated with the user of the generated card object may be automatically generated based on the extracted face image.

As another example the icon associated with the user of the generated card object may be set by selecting any one icon from a separate icon list.

When a card object is generated rights to application items added to the card object to be generated may be differently set. For example all users may have the right to confirm a first application item shown in and only a user who generates a card object may have the right to confirm a second application item shown in . Alternatively when the second application item is executed a lock function such as password input or user face captured may be set. Therefore since my content items may be added to the generated card object it is possible to increase user convenience.

When a card object is generated an application item added to the card object to be generated may be deleted.

For example as shown in the application item added to the card object to be generated may be selected using the pointer indicating movement of the remote controller. In the figure a selection window included in the application item is activated.

As shown in the selected application item is removed. In the selected application item in the card object to be generated is removed and only the pointer is displayed.

The application item in the card object to be generated may be deleted by dragging and dropping of the pointer. That is if the selected application item is dragged to the outside of the card object to be generated the application item may be deleted.

Although show that the case in which the object etc. is selected using the pointer indicating movement of the remote controller the present invention is not limited thereto and various modifications are possible.

For example the object etc. may be selected using the direction key and the OK key of the remote controller . As another example the object etc. may be selected according to a user gesture based on the image of the user captured using the camera . As another example user voice may be recognized and the object etc. may be selected based on the recognized voice.

For example the image display apparatus may display a hand shaped pointer corresponding to the hand of a user based on the image of the user captured using the camera .

In a state of displaying the home screen shown in if hand movement of the user corresponds to a tap gesture for selecting a specific application item in the application list it may be determined that the application item is selected. A plurality of application items may be sequentially selected. In the figure five application items are selected by the user tap gesture.

Next as shown in if the user makes a gist gesture and then makes a leftward movement gesture the image display apparatus may group the selected five application items by the grip gesture and move the selected five application items to the left by the leftward movement gesture that is add the selected five application items to the card object to be generated based on the image of the user captured using the camera . Therefore it is possible to easily move a plurality of items.

As another example the remote controller including a microphone not shown may receive and send user voice to the image display apparatus .

First after the five application items are selected using the direction key etc. of the remote controller if the user outputs voice Please add the selected content to the card object the remote controller may collect and send data of such voice to the image display apparatus . The image display apparatus may analyze user voice using a voice recognition function and recognize a command for moving the five application items.

Therefore as shown in the five application items may be moved to and displayed in the card object to be generated.

The command for selecting the image display apparatus may be input through the direction key and the OK key the user gesture user voice etc. in addition to the pointer of the remote controller. Hereinafter although the pointer indicating movement of the remote controller is focused upon the direction key the OK key the user gesture user voice etc. may be used as described above.

Although generation of the card object is described in various kinds of the card objects may be generated.

For example as shown in a home network card object indicating a connection state of an adjacent electronic apparatus for providing shared content may be generated. The home network card object may include the list of electronic apparatuses connected to the image display apparatus and the list of electronic apparatuses which are not connected to the image display apparatus as shown in .

As another example an integrated electronic apparatus control card object capable of simultaneously monitoring and remotely controlling a plurality of electronic apparatuses may be generated. In such a card object information for monitoring and remotely controlling home appliances such as a refrigerator a washing machine an air conditioner a cooker a TV etc. may be displayed.

The generated card object is a per user card object and may be viewed by a corresponding user which will be described with reference to .

The controller compares the image previously stored in the memory with the captured image of the user and performs user recognition. Then login of the recognized user is performed.

Login may be performed based on at least one of the captured image of the user password input or user voice recognition. User voice may be acquired using a microphone included in the remote controller .

The controller may provide an individual home screen according to the logged in user. That is as shown in a card object generated by the first user may be displayed on the home screen.

The card object generated by the first user may include an icon associated with the user of the generated card object a card object name an object for setting content and a content list including generated application items.

The controller may control display of a recent card object in which content recently used by the logged in user is collected to the user. That is the recent card object indicating the recently used content may be automatically generated and displayed without generating a separate card object.

Although the card object generated by the first user and the recent card object shown in are provided after login of the first user modifications thereof are possible.

For example the card object generated by the first user may be provided after login of the first user but the recent card object may be displayed regardless of login of the first user.

That is the recent card object may not include the content items recently executed by the first user but may include content items recently executed by all users. In this case the recent card object may be displayed on the home screen regardless of login when the user uses the image display apparatus.

Next shows the case in which a second user uses the image display apparatus to which the first user logs in.

In this case the camera of the image display apparatus captures the image of the second user and sends the captured image of the second user to the controller . The controller compares the image previously stored in the memory with the captured image of the user and performs user recognition.

At this time since the first user has already logged in to the image display apparatus the controller informs the second user that another user has logged in to the image display apparatus and displays a message indicating whether the second user will log in to the image display apparatus again. If a new login input item is selected the controller performs login of the recognized second user.

Login may be performed based on at least one of the captured image of the user password input or user voice recognition. User voice may be acquired using a microphone included in the remote controller .

If login is performed the image display apparatus may display an icon indicating the logged in second user.

The controller may provide an individual home screen according to the logged in user. That is the home screen of may be provided to the first user and the home screen of may be provided to the second user.

The card object generated by the second user may include an icon associated with the user of the generated card object a card object name an object for setting content and a content list including generated application items.

Although not shown the controller may control display of a recent card object in which content recently used by the logged in user is collected.

For example if the second user uses the image display apparatus to which the first user has logged in the second user may immediately log in to the image display apparatus without new user login. That is multi login is possible.

As shown in the card object generated by the first user and the card object generated by the second user may be displayed together on the home screen.

If the card objects are displayed together according to multi login and common content is present in the card objects the common content item may be highlighted and displayed. Such a highlight function corresponds to content recommendation. By recommending the common content of the two users it is possible to increase user convenience.

Upon multi login unlike one common card object may be displayed. At this time the common card object may include a content item in the card object generated by the first user and a content item in the card object generated by the second user. At this time the common content item may be highlighted and displayed. Alternatively the common card object may include only the common content item.

Next shows the case in which the second user uses the image display apparatus to which the first user has logged in.

In this case the camera of the image display apparatus captures the image of the second user and sends the captured image of the second user to the controller . The controller compares the image previously stored in the memory with the captured image of the user and performs user recognition.

At this time since the first user has already logged in to the image display apparatus the controller informs the second user that another user has logged in to the image display apparatus and displays a message indicating whether the second user will log in to the image display apparatus again. If a new login input item is selected the controller performs login of the recognized second user.

Login may be performed based on at least one of the captured image of the user password input or user voice recognition. User voice may be acquired using a microphone included in the remote controller .

If login is performed the image display apparatus may display an icon indicating the logged in second user.

On the home screen displayed on the image display apparatus various settings may be performed in addition to card object generation. Hereinafter various settings will be described in detail.

As shown in the settings screen related to the image display apparatus may be displayed. shows the case in which the customize home item of the settings screen is selected based on the pointer displayed in correspondence with movement of the remote controller .

As shown in an application list edit screen for editing the launcher bar area may be displayed on the home screen. At this time the dashboard area may be empty.

The application list edit screen is similar to the application list of and is different therefrom in that the application items are switched to an editable state. Unlike the application list edit screen may further include a widget addition item and an addition completion item .

On the application list edit screen content list settings of a specific card object may be changed a card object name may be changed or the position of a card object may be changed.

For display of the application list edit screen of the application list edit screen may be displayed using other methods instead of selection of the settings object of the home screen and selection of the application list edit item of the settings screen .

For example if the pointer is located in the application list in a state of displaying the home screen of and then long tap or long press input is received as shown in the application list edit screen for editing the launcher bar area may be displayed on the home screen.

As another example if the menu key of the remote controller is manipulated in a state of displaying the home screen of the settings screen related to the image display apparatus shown in may be displayed. If the application list edit item is selected the application list edit screen may be displayed.

As another example if the menu key of the remote controller is manipulated in a state in which the pointer of the remote controller is located in the launcher bar area of the home screen of the application list edit screen for editing the launcher bar area may be immediately displayed.

As shown in a widget screen may be displayed. If various widgets which may be installed in the image display apparatus are present screen switching objects and for switching the screen may be further displayed. Accordingly widget items desired by the user may be installed in the image display apparatus.

The installed widgets may be displayed on the image display apparatus when the widget item of is selected. If the widget item of is selected once more the home screen may be displayed on the image display apparatus again. That is the installed widget screen and the home screen may be alternately displayed according to widget screen selection.

Next shows the case in which in the state of displaying the settings screen related to the image display apparatus the home and all apps settings items are selected based on the pointer displayed in correspondence with movement of the remote controller .

Then as shown in a home and all apps settings screen for setting the home screen may be displayed. At this time the dashboard area may be empty.

In the figure a startup application item for executing applications to be displayed when the image display apparatus is powered on a show hide application item for setting show hide of application items installed in the image display apparatus a wallpaper item and a restore item for restoring an originally installed item are shown as the plurality of sub items of the home and all apps settings screen .

If the startup application item is selected based on the pointer displayed in correspondence with movement of the remote controller as shown in a startup settings screen for executing applications to be displayed when the image display apparatus is powered on is displayed.

Since the home screen is not immediately displayed when the image display apparatus is powered on the startup settings screen may include items for setting the applications to be displayed at a period from a time when power is turned on to a time when the home screen is displayed.

In the figure a default item for displaying a live broadcast a none item for non display a 3D item for displaying a 3D image and an application item for executing a specific application are shown as the items of the startup settings screen .

In the figure the default item for displaying the live broadcast is set as the items of the startup settings screen . In this case since the home screen is not immediately displayed when the image display apparatus is powered on a live broadcast program received through the broadcast reception unit may be displayed as the full screen in a period from a time when power is turned on to a time when the home screen is displayed.

Then an application grid screen shown in may be displayed. The application grid screen may include a plurality of application items and more particularly application items displayed in the launcher bar area .

Then a wallpaper settings screen shown in may be displayed. The wallpaper settings screen may include a plurality of wallpaper items.

Then a wallpaper screen shown in may be displayed. As a result it is possible to easily set the wallpaper when the home screen is displayed.

Next shows the case in which in the state of displaying the settings screen related to the image display apparatus the system settings item is selected based on the pointer displayed in correspondence with movement of the remote controller .

The system settings screen sets all items of the image display apparatus and may include a recent menu item a network item a video input item a picture and sound item a channel settings item a 3D settings item etc.

When the recent menu item is selected a list of recently set menu items may be displayed. When the network item is selected a list for setting information zip code address information etc. about a region in which the image display apparatus is mounted information about a network service provider corresponding to the region etc. may be displayed. When the video input item is selected a list for setting resolution coding rate and codec of displayed video may be displayed.

In addition if the picture and sound item is selected a list for setting resolution coding rate and codec of displayed picture or output sound may be displayed. If the channel settings item is selected a list for setting an automatic channel search range a manual channel search range etc. may be displayed. If the 3D settings item is selected a list for setting a 3D image output format depth of a 3D image a frame frequency etc. may be displayed.

The system settings screen may include a search window for easily searching for numerous setting items with various depths. In addition a voice recognition icon may be displayed in the vicinity of the search window such that search is performed through voice recognition.

Predetermined letters may be entered in the search window using the letter key of the remote controller or the letter key of the screen keyboard and the setting items corresponding to the entered letters may be immediately searched for and displayed. Accordingly the user can easily search for a desired setting item.

Step S of displaying the home screen is equal to step S of displaying the home screen and thus a description thereof will be omitted.

The image display apparatus determines whether a broadcast information related application on the home screen is selected S and a screen for executing the application is displayed S if the application is selected.

As shown in in the state of displaying the home screen if the primetime TV movie item of the application list is selected the image display apparatus may display a primetime application execution screen to be displayed as shown in .

The primetime application executed by selection of the primetime item may be provided by a current live broadcast program a VOD such as drama or animation which is capable of being streamed at a user request a movie which is capable of being streamed at a user request.

In order to provide such a service the network of the image display apparatus is preferably set in advance. For example region information and information about a broadcast service provider and a network service provider according to the region information is preferably set in advance. Network settings are described with reference to .

In the primetime application the live broadcast program the VOD such as drama or animation or the movie provided to the image display apparatus may be changed according to the set region and network service provider.

Among the respective live broadcast images and of the channels the live broadcast image of the channel displayed on the home screen of may be highlighted. Alternatively a live broadcast image of a channel having highest real time ratings among the respective live broadcast images and of the channels may be highlighted. In addition a live broadcast image which is most viewed by the user among the respective live broadcast images and of the channels may be highlighted.

The highlighted live broadcast image may have a largest size may be arranged at a foremost side or may have a largest amount of displayed information. That is the highlighted live broadcast image may be highlighted with a priority higher than the live broadcast images of the other channels.

In the figure the highlighted live broadcast image includes a channel name a program name of the program broadcast on the channel brief broadcast information of the program and a detailed information view object of the program.

The live broadcast image of each channel may be a broadcast program image provided by a broadcast service provider for providing a broadcast service.

The displayed broadcast information may be broadcast information provided by a broadcast service provider for providing a broadcast service. Upon primetime application execution the image display apparatus may access a broadcast service provider server for providing the broadcast service. Here the broadcast service provider may include a local cable operator.

In the live broadcast image other than the highlighted live broadcast image includes only a channel name and a program name of the program broadcast on the corresponding channel. That is the live broadcast image and the highlighted live broadcast image are different in terms of information provided.

By highlighting any one live broadcast program of the live broadcast program list user interest in the highlighted live broadcast program may be assumed high.

The primetime application screen may display a setting item and region information of the image display apparatus .

According to the region information of the image display apparatus the number of broadcast channels and a broadcast channel number provided to the image display apparatus may be changed. Settings related to the primetime application may be performed through the setting item . This will be described below with reference to .

Unlike the live broadcast images of the live broadcast program list may have the same size and the arrangement order thereof may be changed according to real time ratings. In this case if any one live broadcast content of the live broadcast program list is focused upon by movement of the cursor or the pointer the broadcast information of the live broadcast content may be displayed in the form of a pull down menu. Accordingly the user can easily confirm desired information.

Next shows the case in which the live broadcast program item is selected and thus a broadcast information screen is displayed. The broadcast information screen may be an EPG screen.

The broadcast information screen may include broadcast information centered on the live broadcast program displayed on the home screen of . Since the live broadcast program of Channel 5 is displayed on the home screen of the broadcast information screen of is displayed to be centered on Channel 5 along with broadcast information of Channels 6 to 8. In particular an item The following broadcast by SBC on Channel 5 displayed in may be highlighted. Therefore the user can easily confirm the broadcast information of the channel.

In case of a program provided by a major broadcast station such broadcast information may be included in a broadcast signal transmitted by the major broadcast station. The image display apparatus may extract broadcast information from the broadcast signal and generate and display the OSD shown in the figure.

As another example in case of a program provided by a cable broadcast station such broadcast information may be included in a broadcast signal transmitted by the cable broadcast station or may be received from a server of the cable broadcast station over a network. The image display apparatus may extract the broadcast information from the broadcast signal or receive the broadcast information over the network and generate and display the OSD shown in the figure.

If the broadcast information is received via a plurality of routes for example is received from the major broadcast station and the cable broadcast station over the network the image display apparatus may simultaneously display all broadcast information on the broadcast information screen or display a selection menu and display only one piece of broadcast information.

Next shows the case in which the live broadcast program item is selected and thus the broadcast information screen is displayed. Unlike the broadcast information screen may be displayed on a per genre basis.

For example if the genre of The Following broadcast by SBC on Channel 5 displayed in is thriller the broadcast information screen may display broadcast information aligned on a per genre basis.

In the figure District 13 broadcast by YTC on Channel 23 shooter broadcast by CCC on Channel 130 and Deja vu of VAN of Channel 527 equal to or similar to The Following broadcast by SBC on Channel 5 in terms of genre are displayed. Therefore the user can easily confirm broadcast information on a per genre basis.

At this time information about the number of viewers of each channel may be displayed. The number of viewers may be the number of viewers in the same region. In the figure the region information and the information about the number of viewers of each channel are displayed.

Although the broadcast information on the broadcast information screen is aligned on a per genre basis in such settings may be changed. If the settings object is selected to change a broadcast information alignment criterion the broadcast information may be aligned according to the changed criterion. The broadcast information alignment criterion may be channel genre ratings age person and place related to the viewed program etc.

If the user has logged in to the image display apparatus the broadcast information screen may be provided on a per user preference or genre basis. If a child has logged in to the image display apparatus a broadcast information screen related to a children s program may be provided. If a female adult has logged in to the image display apparatus a broadcast information screen related to a cooking program or drama may be provided.

The VOD list may include a plurality of VOD moving images and . The VOD moving images of the VOD list may be divided according to servers or genres. A popular image or a most downloaded image among the plurality of VOD moving images and may be highlighted. In the figure the first VOD moving image is highlighted. The first VOD moving image may include a VOD moving image a VOD name and the number of views. In particular the first VOD moving image may further include the number of views as compared to the other VOD moving images.

The VOD moving image may be provided by a content provider for a VOD moving image. The image display apparatus may access a server of a content provider to receive a VOD moving image.

Upon display of the VOD moving image list a setting item and region information of the image display apparatus may be continuously displayed.

Unlike the VOD moving images of the VOD moving image list may have the same size and the arrangement order thereof may be changed according to popularity or download count. In this case if any one VOD moving image content of the VOD moving image list is focused upon by movement of the cursor or the pointer the information of the VOD moving image content may be displayed in the form of a pull down menu. Accordingly the user can easily confirm desired information.

The movie list may include a plurality of movies. The movies of the movie list may be divided according to servers or genres. The arrangement order of the plurality of movies may be changed according to popularity or download count.

If any one movie on the movie list is focused upon by movement of the cursor or the pointer information on the movie may be displayed in the form of a pull down menu. Accordingly the user can easily confirm desired information.

The movie content may be provided by a content provider for providing movie content. The image display apparatus may access a server of a content provider to receive movie content.

Upon displaying the movie list a setting item and region information of the image display apparatus may be continuously displayed.

Although an object is selected using the pointer indicating movement of the remote controller in the present invention is not limited thereto and various modifications are possible.

For example the object may be selected using the direction key and the OK key of the remote controller . As another example the object etc. may be selected in correspondence with a user gesture based on the image of the user captured using the camera . As another example user voice may be recognized and the object etc. may be selected based on the user voice.

For example the image display apparatus may display a hand shaped pointer corresponding to the hand of a user based on the image of the user captured using the camera .

In a state of displaying the home screen shown in if hand movement of the user corresponds to a tap gesture for selecting the primetime item TV movie item it may be determined that the corresponding item is selected. Any one of the screens of may be displayed. That is the live broadcast program list may be displayed as shown in or the broadcast information screen or of or D may be displayed.

As another example the remote controller including a microphone not shown may receive and send user voice to the image display apparatus .

In a state of displaying the home screen shown in if the user outputs voice please execute primetime the remote controller may collect and send data of such voice to the image display apparatus . The image display apparatus may analyze the user voice through the voice recognition function and recognize a primetime application execution command. Then the live broadcast program list may be displayed as shown in or the broadcast information screen or of or D may be displayed.

The selection command of the image display apparatus may be performed using the direction key and the OK key a user gesture user voice etc. in addition to the pointer of the remote controller. Although the pointer indicating movement of the remote controller is focused upon in the following description the direction key and the OK key a user gesture user voice etc. may be used.

If the personalization item is selected on the settings screen of based on the pointer displayed in correspondence with movement of the remote controller a personalization related screen shown in may be displayed.

The personalization related screen may include an email account related item a content rating related item and an application store related item .

The settings screen may include a home dashboard edit item a customize home item a home and all apps settings item and a system settings item .

The system settings screen is used to set all items of the image display apparatus and may include a recent menu item a network item a video input item a picture and sound item a channel settings item a 3D settings item etc.

When the recent menu item is selected a list of recently set menu items may be displayed. When the network item is selected a list for setting information zip code address information etc. about a region in which the image display apparatus is mounted information about a network service provider an Internet service provider etc. corresponding to the region etc. may be displayed. When the video input item is selected a list for setting resolution coding rate and codec of displayed video may be displayed.

In addition if the picture and sound item is selected a list for setting resolution bit rate coding rate and codec of displayed picture or output sound may be displayed. If the channel settings item is selected a list for setting an automatic channel search range a manual channel search range etc. may be displayed. If the 3D settings item is selected a list for setting a 3D image output format depth of a 3D image a frame frequency etc. may be displayed.

The system settings screen may include a search window for easily searching for numerous setting items with various depths. In addition a voice recognition icon may be displayed in the vicinity of the search window such that search is performed through voice recognition.

Predetermined letters may be entered in the search window using the letter key of the remote controller or the letter key of the screen keyboard and the setting items corresponding to the entered letters may be immediately searched for and displayed. Accordingly the user can easily search for a desired setting item.

For network setting of the image display apparatus a list for setting information zip code address information etc. about a region in which the image display apparatus is mounted information about a network service provider an Internet service provider etc. corresponding to the region etc. may be displayed. Thus region information input network service provider input or selection may be performed.

The app store screen related to the image display apparatus may include a search window for searching for an application a first application list and a second application list . The first application list may include popular or new application items and the sizes of the application items of the first application list may be greater than those of the application items of the second application list .

If a web item of the application list of the home screen is selected in a web screen shown in may be displayed. Then it is possible to immediately use the Internet.

If the pointer displayed in correspondence with movement of the remote controller is moved to a lower side of a content region that is to a position corresponding to the launcher bar area of the home screen the application list may be displayed as shown in . That is the application list may be displayed even when the home screen is not displayed. Therefore it is possible to increase user convenience.

When a card object is generated according to the method for operating the image display apparatus described with reference to the method for operating the image display apparatus of is applicable. That is if an application item related to broadcast information of an application list of a home screen is selected after a card object is generated a broadcast information related application screen including a live broadcast image item for viewing a live broadcast image list and a moving image item for viewing a moving image list may be displayed.

On the contrary after a broadcast information related application screen according to the method for operating the image display apparatus described with reference to is displayed a card object may be generated in a state of displaying a home screen.

In the image display apparatus according to the embodiment of the present invention when an object or a menu is selected or focused upon the object or the menu may be highlighted. Although not shown in or the contour of the selected or focused object or menu may be made thick or at least one of the size color or the luminance of the selected or focused object or menu may be changed. Therefore the user can intuitively perceive selection or focusing of the object or menu.

According to one embodiment of the present invention an image display apparatus displays a screen for generating a card object to be displayed on a home screen according to card object generation input and adds a predetermined content item to the card object to be generated if the predetermined content item is selected. Therefore the user can easily generate a desired card object. As a result it is possible to increase user convenience.

In particular the card object to be generated is displayed in a first region of the screen for generating the card object and content items to be added are displayed in a second region such that desired content items are easily added to the card object to be generated on one screen.

The card object may be generated on a per user basis and when a user logs in a card object corresponding to the user may be displayed. Thus the user can view the card object including content items desired by the user.

If system settings input is received a system settings screen including network settings video settings channel settings and 3D image settings is displayed and a search window for searching for a settings item is displayed such that a desired settings item among a plurality of search items is immediately searched for.

According to another embodiment of the present invention an image display apparatus displays a broadcast information related application screen including a live broadcast image item for viewing a live broadcast image list and a moving image item for viewing a moving image list if a broadcast information related application item in an application list on a home screen is selected. Therefore the user can easily view desired content.

If a live broadcast image list is displayed on the broadcast information related application screen at least one of the size or arrangement order of broadcast images in the live broadcast image list or the amount of display information related to the broadcast images is changed according to real time ratings. Therefore it is possible to increase user convenience.

If a moving image list is displayed on the broadcast information related application screen at least one of the size or arrangement order of moving images in the moving image list or the amount of display information related to the moving images is changed according to download counts of the moving images. Therefore it is possible to increase user convenience.

The image display apparatus and the method for operating the same according to the foregoing embodiments are not restricted to the embodiments set forth herein. Therefore variations and combinations of the exemplary embodiments set forth herein may fall within the scope of the present invention.

The method for operating an image display apparatus according to the foregoing embodiments may be implemented as code that can be written to a computer readable recording medium and can thus be read by a processor. The computer readable recording medium may be any type of recording device in which data can be stored in a computer readable manner. Examples of the computer readable recording medium include a ROM a RAM a CD ROM a magnetic tape a floppy disk an optical data storage and a carrier wave e.g. data transmission over the Internet . The computer readable recording medium can be distributed over a plurality of computer systems connected to a network so that computer readable code is written thereto and executed therefrom in a decentralized manner. Functional programs code and code segments to realize the embodiments herein can be construed by one of ordinary skill in the art.

Although the preferred embodiments of the present invention have been disclosed for illustrative purposes those skilled in the art will appreciate that various modifications additions and substitutions are possible without departing from the scope and spirit of the invention as disclosed in the accompanying claims.

