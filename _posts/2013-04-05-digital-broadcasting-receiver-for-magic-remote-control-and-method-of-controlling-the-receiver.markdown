---

title: Digital broadcasting receiver for magic remote control and method of controlling the receiver
abstract: The present invention relates to a digital broadcasting receiver for a magic remote control and a method of controlling the receiver. The digital broadcasting receiver for the magic remote control according to an embodiment of the present invention may include: a receiving unit receiving a control signal, wherein the control signal includes a first signal representing that a button of the magic remote control is pressed, a second signal representing the drag state of the magic remote control while the button of the magic remote control is pressed, and a third signal representing that the button of the magic remote control is released; a display unit; a processor; and a platform.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09319734&OS=09319734&RS=09319734
owner: LG ELECTRONICS INC.
number: 09319734
owner_city: Seoul
owner_country: KR
publication_date: 20130405
---
This application is the National Phase of PCT International Application No. PCT KR2013 002836 filed on Apr. 5 2013 which claims priority under 35 U.S.C. 119 e to U.S. Provisional Application No. 61 620 460 filed on Apr. 5 2012 all of which are hereby expressly incorporated by reference into the present application.

The present invention relates to a digital broadcast receiver having a user interface UI which is implemented to execute a TV function only with minimum input in use of a magic remote controller for controlling the digital broadcast receiver and a method of controlling the digital broadcast receiver. In addition the present invention relates to an apparatus and method for implementing a magic remote controller UI for controlling a digital broadcast receiver and various external input devices in an integrated manner.

A remote controller through which a user inputs a command is used for a digital broadcast receiver such as a smart TV. The remote controller basically includes power channel change volume control external input change keys numeral keys etc. Furthermore the remote controller is additionally provided with keys for supporting setting of the digital broadcast receiver a key for executing a 3D function a key for accessing a smart TV menu in the case of a smart TV etc.

This remote controller based on numeral keys is manufactured for terrestrial broadcasts in order to control the digital broadcast receiver while easily changing a limited number of channels. However the digital broadcast receiver currently supports various functions such as watching terrestrial broadcasts watching cable broadcasts through connection of a set top box execution of an extended function through connection of an external device such as a DVD player use of the Internet through a browser etc.

As the purpose of the digital broadcast receiver is extended a magic remote controller using a gyroscope appears. According to the magic remote controller movement of the remote controller is sensed through the gyroscope and the sensed movement is converted into coordinates in the digital broadcast receiver and a pointer corresponding to the coordinates is displayed on the screen of the receiver. To this end a user interface UI of the digital broadcast receiver is modified such that the pointer can be moved and selected.

When a conventional UI is used a function of the digital broadcast receiver is executed by 1 calling a menu by moving a button or a pointer on the magic remote controller 2 moving the pointer to a desired function on the menu and 3 selecting the desired function by clicking the pointer.

However the aforementioned operation is performed only when a function included in the called menu is executed. Since additional keys for functions such as channel change volume control and the like which are necessary to watch a broadcast are allocated to the magic remote controller the UE cannot be unified.

Furthermore a conventional magic remote controller does not use a drag operation. The magic remote controller having no drag function does not meet requirements of users accustomed to use touch based devices.

In addition when an external device is present functions such as playback and search used in the external device are not included in the conventional UI and thus the digital broadcast receiver and the external device cannot be controlled in an integrated manner using the magic remote controller. For example when a user mainly watches cable broadcasts instead of terrestrial broadcasts the user does not use the magic remote controller for purposes other than power and volume control.

An object of the present invention devised to solve the problem lies in a control method and control apparatus for allowing users to use a digital broadcast receiver and external devices connected thereto on the basis of user experience in using touch based devices such as smartphones so as to meet requirements of users accustomed to touch based devices such as a smartphone smartpad etc.

Another object of the present invention provides a control method and apparatus for touching a screen using a magic remote controller by moving the screen through an improved UI through a drag operation of the magic remote controller.

Another object of the present invention provides a control method and a control apparatus for providing an integrated UI in control of various TV functions and or a connected external device by using one magic remote controller.

In an aspect of the present invention a digital broadcast receiver for a magic remote controller includes a receiving unit for receiving a control signal from the magic remote controller through Bluetooth wherein the control signal includes a first signal representing a state in which a button of the magic remote controller is pressed a second signal representing a drag state of the magic remote controller with the button of the magic remote controller pressed and a third signal representing a state in which the button of the magic remote controller is released a display unit for displaying an OSD according to broadcast images and or the received controller a processor configured to calculate a position of the magic remote controller so as to sense the control signal to indicate the position and motion of the magic remote controller as a pointer on a screen to display the pointer while moving the pointer in a direction in which the magic remote controller is moved when the receiver receives the second signal and to determine whether to perform predetermined screen change according to the control signal and a platform for capturing the broadcast images when the predetermined screen change is performed generating phased images for the predetermined screen change using the captured images and controlling the phased images to be displayed on the screen.

When the predetermined screen change corresponds to screen change according to channel change the platform may capture a first image with respect to a still image of broadcast images of a current channel and a second image with respect to a still image of broadcast images of a neighboring channel when the receiver receives the first signal the platform sequentially displaying the first image a third image obtained by blending the first and second images and the second image when the receiver receives the second signal the platform displaying the first image or the second image when the receiver receives the third signal.

The processor may control information on the neighboring channel to be displayed as an OSD when the pointer is located in an upper or lower area of the screen.

The platform may control areas of the first image and the second image included in the blended third image on the basis of a degree by which the magic remote controller is dragged according to the second signal and the processor may control the digital broadcast receiver to tune to the current channel when the area of the first image included in the third image is larger than the area of the second image at a time when the third signal is received and control the digital broadcast receiver to tune to the neighboring channel when the area of the second image included in the third image is larger than the area of the first image.

When the predetermined screen change corresponds to screen change according to EPG Electronic Program Guide display 

the screen may include a first area displaying current channel and input information according to the control signal a second area displaying detailed information on a current channel and input according to the control signal a third area displaying a channel list according to the control signal and a fourth area displaying the EPG according to the control signal and the processor may display the first area on the screen when the receiver receives the first signal display the second or third area on the screen when the receiver receives the second signal and display the fourth area on the screen when the receiver receives the third signal.

When the receiver receives the second signal the processor may display the second area on the screen when the pointer is moved from the first area to the second area and display the third area on the screen when the pointer is moved from the first area to the third area.

Channels may be searched using the pointer in the third and fourth areas according to the second signal and a channel may be changed according to the first and third signals.

In another aspect of the present invention an apparatus for implementing a magic remote controller UI includes a digital broadcast receiver receiving a control signal from a magic remote controller through Bluetooth an external device connected to the digital broadcast receiver and the magic remote controller receiving an IR code corresponding to the external device from the digital broadcast receiver when the digital broadcast receiver receives the control signal and sending the received IR code to the external device through IR output wherein the control signal includes a first signal representing a state in which a button of the magic remote controller is pressed a second signal representing a drag state of the magic remote controller with the button of the magic remote controller pressed and a third signal representing a state in which the button of the magic remote controller is released wherein the digital broadcast receiver comprises a receiving unit for receiving the control signal a display unit for displaying OSD according to broadcast images and or the received controller a processor configured to calculate a position of the magic remote controller so as to sense the control signal to indicate the position and motion of the magic remote controller as a pointer on a screen to display the pointer while moving the pointer in a direction in which the magic remote controller is moved when the receiver receives the second signal and to determine whether to perform predetermined screen change according to the control signal and a platform for capturing the broadcast images when the predetermined screen change is performed generating phased images for the predetermined screen change using the captured images and controlling the phased images to be displayed on the screen.

The platform may receive the IR code through the Internet when the IR code corresponding to the external device is not present.

When the predetermined screen change corresponds to screen change according to channel change the platform may capture a first image with respect to a still image of broadcast images of a current channel and capture a second image with respect to a black mute screen when the receiver receives the first signal the platform sequentially displaying the first image a third image obtained by blending the first and second images and the second image when the receiver receives the second signal the platform displaying the first image or the second image when the receiver receives the third signal.

The processor may control information on a neighboring channel to be displayed as an OSD when the pointer is located in an upper or lower area of the screen.

The platform may control areas of the first image and the second image included in the blended third image on the basis of a degree by which the magic remote controller is dragged according to the second signal and the processor may control the digital broadcast receiver to tune to the current channel when the area of the first image included in the third image is larger than the area of the second image at a time when the third signal is received and control the digital broadcast receiver to tune to the neighboring channel when the area of the second image included in the third image is larger than the area of the first image.

When the predetermined screen change corresponds to screen change according to a trick mode the processor may toggle playback or pause state when the button of the magic remote controller is double clicked control current images displayed on the screen to be played fast when the receiver receives the second signal and control a playback mode to be converted to a normal playback mode when the receiver receives the first signal during fast playback.

When the predetermined screen change corresponds to screen change according to the trick mode the processor may toggle playback or pause state when the button of the magic remote controller is double clicked and control content of a neighboring chapter to be displayed when the receiver receives the second signal wherein when the receiver continuously receives a plurality of second signals respectively corresponding to different directions in which the magic remote controller is moved the processor controls content of a neighboring chapter according to the finally received second signal to be displayed.

In another aspect of the present invention a method for controlling a digital broadcast receiver for a magic remote controller includes transmitting a control signal from the magic remote controller to the digital broadcast receiver through Bluetooth wherein the control signal includes a first signal representing a state in which a button of the magic remote controller is pressed a second signal representing a drag state of the magic remote controller with the button of the magic remote controller pressed and a third signal representing a state in which the button of the magic remote controller is released calculating a position of the magic remote controller so as to sense the control signal indicating the position and motion of the magic remote controller as a pointer on a screen and displaying the pointer while moving the pointer in a direction in which the magic remote controller is moved when the second signal is received determining whether predetermined screen change is performed according to the control signal capturing broadcast images when the predetermined screen change is performed generating phased images for the predetermined screen change using the captured images and controlling the phased images to be displayed on the screen.

In another aspect of the present invention a method for implementing a magic remote controller UI includes transmitting a control signal from a magic remote controller to a digital broadcast receiver through Bluetooth wherein the control signal includes a first signal representing a state in which a button of the magic remote controller is pressed a second signal representing a drag state of the magic remote controller with the button of the magic remote controller pressed and a third signal representing a state in which the button of the magic remote controller is released transmitting from the digital broadcast receiver to the magic remote controller an IR code corresponding to an external device connected to the digital broadcast receiver transmitting the IR code from the magic remote controller to the external device through IR output calculating a position of the magic remote controller so as to sense the control signal indicating the position and motion of the magic remote controller as a pointer on a screen and displaying display the pointer while moving the pointer in a direction in which the magic remote controller is moved when the second signal is received determining whether predetermined screen change is performed according to the control signal capturing broadcast images when the predetermined screen change is performed generating phased images for the predetermined screen change using the captured images and controlling the phased images to be displayed on the screen.

According to the digital broadcast receiver for a magic remote controller and the method of controlling the same of the present invention it is possible to provide various user command input schemes and to provide user experience as if a user who is spaced apart from the digital broadcast receiver by a predetermined distance or more directly touches a screen of the digital broadcast receiver.

In addition it is possible to maintain consistent user experience in watching images channel and input change checking an EPG and external device control through an enhanced UI.

The configuration operation and other features of the present invention will readily be understood with embodiments of the present invention described with reference to the attached drawings.

The configuration and operation of the present invention which are illustrated in and described by the accompanying drawings are described as at least one embodiment. However it will be apparent to those skilled in the art that the technical spirit and essential configuration and operation of the present invention are not limited to the specific embodiment as set forth herein.

Referring to a screen of the conventional digital broadcast receiver for the magic remote controller may be segmented into a menu area a keypad area and a channel information area and the UI of the conventional digital broadcast receiver for the magic remote controller may include a menu a keypad and channel information . The position and motion of the magic remote controller can be indicated by a pointer on the screen.

The UI of the conventional digital broadcast receiver for the magic remote controller can be configured to display OSDs and representing functions corresponding to specific areas and upon movement of the pointer indicated on the screen to the specific areas and on the screen. When the pointer is moved to an item corresponding to a desired function on the displayed OSD and clicked the desired function can be executed in the digital broadcast receiver.

However when the UI of the conventional digital broadcast receiver for the magic remote controller is used user experience is not combined. Specifically the UI of the conventional digital broadcast receiver for the magic remote controller does not include functions such as power on off channel change and the like and additional keys corresponding to the functions are provided to the magic remote controller such that the functions are executed using the keys irrespective of the UI.

In addition when an external device is present functions corresponding to a play key search key color key and the like which are mainly used in the external device are not included in the UI of the conventional digital broadcast receiver for the magic remote controller and thus the magic remote controller cannot be used as a unified remote controller for the external device.

Accordingly to solve the aforementioned problems the present invention proposes a newly configured UI of a digital broadcast receiver.

Referring to the UI of the digital broadcast receiver for the magic remote controller may display OSDs with respect to specific functions such as channel change and and external input change and in top bottom left and right areas and of the screen of the digital broadcast receiver.

The magic remote controller may be recognized as a pointer on the screen of the digital broadcast receiver. When the pointer is moved to the specific areas and OSDs and with respect to predetermined specific functions are displayed. Upon display of the OSDs and the UI may be changed to a drag based UI. According to the drag based UI a state in which a button of the magic remote controller is pressed and a state in which the button is released are separately recognized such that a drag operation can be used to control the digital broadcast receiver for the magic remote controller. The predetermined specific functions may be channel change and and or external input change and as shown in .

The present invention proposes a UI of the digital broadcast receiver which is newly configured to control the digital broadcast receiver according to a drag operation while minimizing the number of buttons of the magic remote controller on the basis of the UI configuration shown in .

Specifically 1 the screen of the digital broadcast receiver is segmented a UI with respect to a predetermined operation is displayed when the magic remote controller is moved to a segmented area or a button of the magic remote controller is pressed and the predetermined operation is performed when the button is released or clicked and 2 an operation of moving the screen similarly to touchscreen operation is implemented in a drag state to achieve natural screen change. In addition 3 a system is configured to interoperate with an external device through two input channels such as Bluetooth WiFi IR Infrared etc. when the external device is present such that operations of the external device can be included in a digital broadcast receiver viewing experience.

The digital broadcast receiver according to an embodiment of the present invention may include a receiving unit a processor a platform and or a display unit .

The receiving unit may receive information on the position and motion of the magic remote controller through a Bluetooth channel. The magic remote controller according to an embodiment of the present invention may control functions of the digital broadcast receiver only using two keys corresponding to a power button and a function button. A user can press a corresponding button of the magic remote controller move the magic remote controller with the button pressed and release the pressed button. User command input is defined by a position and motion of the magic remote controller.

The processor may convert information on the position and motion of the magic remote controller into a pointer on the screen of the digital broadcast receiver. The position and motion of the magic remote controller can be indicated as the pointer on the screen. The processor may convert the position and motion of the magic remote controller into coordinates and moving speed of the pointer on the screen. The processor may recognize the position and motion of the pointer and thus determine whether to execute a function of the digital broadcast receiver according to user command input.

The platform may execute a function according to a user command. To execute a function a screen displaying broadcast images being played may be changed. Images necessary for screen change may be generated in such a manner that the broadcast images being played are captured by the platform and the captured images are configured as phased images. The phased images may be composed of capture images of the broadcast images being played and a target input image. For example the phased images can include part of broadcast images being played and part of the target input image. As the screen changes the phased images may be synthesized 1 such that part of broadcast images being played included in the phased images has a larger area than part of the target input image 2 such that part of the broadcast images being played has an area having the same size as part of the target input image or 3 such that part of the broadcast images being played has a smaller area than part of the target input image.

The display unit may display broadcast images phased images necessary for screen change and an OSD representing information on execution of a function according to a user command on the screen of the digital broadcast receiver.

The digital broadcast receiver for the magic remote controller which can be controlled by a magic remote controller and or an IR remote controller according to an embodiment of the present invention may include Ethernet WiFi a USB Bluetooth an IR interface an Ethernet MAC a USB controller a microcomputer a peripheral a 2CH tuner a demodulator a system DEMUX an HDMI High Definition Multimedia Interface DVI Digital Visual Interface cable an HDMI DVI controller a CVBS Composite Video Banking Sync RGB Red Green Blue Comp an analog FE ADC Analog to Digital Converter an input scene capture manager a 2CH external input MUX a CPU GPU a video decoder a DVR Digital Video Recorder engine an HD display engine a graphics engine a hardware image CODEC OSD On Screen Display PIP Photo Interpretive Program an FRC Frame Rate Control a display a system memory and or a data bus .

The magic remote controller may send information on the position and motion thereof to the digital broadcast receiver through the USB Bluetooth and or IR interface .

The RI remote controller which transmits receives signals using infrared light may transmit information on the position and motion thereof to the digital broadcast receiver through the IR interface .

The USB Bluetooth may be an interface between the magic remote controller and the digital broadcast receiver. The USB Bluetooth may be used to transmit receive signals between the magic remote controller and the digital broadcast receiver through a USB port and or a Bluetooth channel.

The IR interface may be an interface between the IR remote controller and the digital broadcast receiver. The IR interface is used to transmit receive signals between the magic remote controller and the digital broadcast receiver through an IR channel.

The peripheral may be an interface between signals received by the digital broadcast receiver and components that handle the signals and various engines.

The system DEMUX may separate an audio stream and a video stream of a broadcast image from each other.

The CVBS RGB Comp may represent a luminance signal expressing luminance and or a color signal expressing color.

The capture manager may control capture of a broadcast image. The 2CH tuner can capture a small image such as a thumbnail.

The 2CH external input MUX may be a path through which external signals input to the digital broadcast receiver are controlled.

The graphics engine may generate phased images using captured images. The phased images may be displayed during screen change. The graphics engine may control a process of displaying the phased images for natural screen change.

The hardware image CODEC may compress an image file and decompress a compressed image file. The OSD PIP may display a menu on the screen of the digital broadcast receiver or control the resolution of the screen. The OSD may be implemented in full HD to be suited to full HD broadcast images. A data bandwidth of 32 bits or more may be secured between the OSD and the CPU to implement the full HD OSD .

The system memory may be a memory having a sufficient space to capture and store images necessary for channel change.

The data bus may be a path through which data signals are transmitted to components of the digital broadcast receiver.

The magic remote controller according to one embodiment may include an IR controller a Bluetooth controller a gyroscope a keypad a microcomputer and or a memory .

The IR controller may transmit a signal of the magic remote controller as infrared rays. A unique code may be defined per key for each external device to be controlled by the magic remote controller. Infrared rays may be used for power control of the digital broadcast receiver.

The Bluetooth controller may be an interface used for the magic remote controller to control the digital broadcast receiver. Two way communication can be performed according to characteristics of Bluetooth. The digital broadcast receiver may transmit signals through a Bluetooth channel using the magic remote controller.

The gyroscope generates information on the position and motion of the magic remote controller. The gyroscope may transmit the information on the position and motion of the magic remote controller to the microcomputer .

The microcomputer may control interface with the IR controller and the Bluetooth controller . The microcomputer may process the information on the position and motion of the magic remote controller received from the gyroscope to convert the information into coordinate information on the screen of the digital broadcast receiver. The microcomputer may process an input value of the keypad and transmit the processed value to the digital broadcast receiver.

The memory may be used as a storage space necessary for an IR key code related to the digital broadcast receiver and execution of a program for operations of the magic remote controller.

A software layer of the digital broadcast receiver for the magic remote controller may include an application layer a middleware and or a hardware system layer .

The application layer may include a smart TV application necessary to execute functions of a smart TV. The application layer may include a subtitle necessary to execute a conventional TV function an EPG Electronic Program Guide a remote interface and or an embedded UI .

The middleware may include a browser and or a smart TV platform . In addition the middleware may include a UI input platform referred to as a platform hereinafter .

The hardware system layer may include a hardware H W graphics a system API Application Programming Interface an A V decoder and or digital TV hardware .

As shown in the digital broadcast receiver according to the present invention may include a software platform for smooth screen change in order to implement a UI similar to a UI of a touch based device such as a smartphone. The platform is a layer capable of supporting operation of the magic remote controller capture for screen change and composition of phased images through the graphics engine in a software manner. The embedded UI may be used for user command input such as channel change input change or the like and image output. Screen change effect and OSD may be achieved in the platform .

The software platform of the digital broadcast receiver for the magic remote controller may include a magic remote controller interface a command interpreter an external input command database an Ethernet WiFi interface a system interface an OSD generator a capture image manager an image blender an intermediate motion trigger an intermediate image buffer and or a display interface .

The magic remote controller interface is an interface between the magic remote controller and the digital broadcast receiver. The magic remote controller interface may receive information on the position and motion of the pointer according to user command input and information on whether the button on the magic remote controller is pressed.

The command interpreter may interpret the user command on the basis of the position and motion of the pointer and whether the button is pressed and transmit the interpreted command to the system. The command interpreter may generate phased images corresponding to the interpreted command and control the phased image to be smoothly displayed by controlling the intermediate motion trigger . The command interpreter may manage a UI related to a current input state such as channel information a view mode volume or the like.

The external input command database may extract an IR code for controlling an external device from the digital broadcast receiver when the external device is present. The IR code for controlling the external device is generated when the digital broadcast receiver receives information on the position and motion of the magic remote controller. The external input command database may transmit the extracted IR code to the magic remote controller and the magic remote controller may transmit the received IR code as an internal IR output.

The Ethernet WiFi interface may operate as an interface in the platform when the Ethernet and or WiFi are used.

The system interface may control execution of functions of the digital broadcast receiver by transmitting software information on user command input to the digital broadcast receiver system.

The OSD generator may generate a graphic image screen such as a menu information window EPG or the like which displays information on the user command input.

The capture image manager may manage capture images of broadcast images which are necessary for screen change.

The image blender may generate phased images. The image blender may generate the phased images by blending OSD generated by the OSD generator and images managed by the capture image manager and store the phased images in the intermediate image buffer . The image blender may use a 2D graphic acceleration function.

The intermediate motion trigger may generate a signal for controlling a UI image to be naturally displayed.

The embodiment illustrated in shows a process of changing from a currently broadcast channel to a neighboring upper channel.

The embodiment illustrated in shows a process of changing from a currently broadcast channel to a neighboring lower channel.

When the pointer of the magic remote controller is moved to a side area of the screen OSD with respect to channel change or input change may be displayed on the screen. The side area may be set as a region spaced apart from the edge of the screen by a predetermined distance and used to recognize the position of the magic remote controller. The predetermined distance may be changed according to design.

A pointer sensing region or may be set on a screen or on which a broadcast image is displayed having a predetermined distance from the upper lower edge of the screen. When the pointer of the magic remote controller is located in the pointer sensing region or OSDs and or and with respect to the neighboring upper lower channel may be displayed on the basis of the position of the pointer. The OSDs and or and with respect to the channel may include a channel number and a channel name.

When the button of the magic remote controller is pressed while the OSDs and or and with respect to the channel is displayed a channel change command signal is input. The displayed broadcast image may be stopped according to the channel change command signal. Then the video frame of the stopped broadcast image is captured a broadcast image corresponding to the upper lower channel is captured and loaded.

When the magic remote controller is moved with the button thereof pressed to drag the pointer on the screen the captured video frame or is moved in the drag direction. Here the capture image or of the broadcast image corresponding to the neighboring channel may be displayed in a vacant area of the screen which is generated when the captured video frame or is moved according to drag operation. That is the captured video frame or and the capture image or of the broadcast image of the neighboring channel may be blended to form phased images in a screen transition procedure. Image blending may be performed on the basis of 2D graphics acceleration.

Specifically the result of may be obtained according to drag direction. When the pointer is dragged downward with the button of the magic remote controller pressed the capture image corresponding to the neighboring upper channel may be blended with the captured video frame and displayed as shown in . When the pointer is dragged upward with the button of the magic remote controller pressed the capture image corresponding to the neighboring lower channel may be blended with the captured video frame and displayed as shown in .

When the button of the magic remote controller is released after the drag operation the previous channel may be maintained or transition to the neighboring channel may be performed. Here a release time is predicted in consideration of acceleration of movement of the pointer on the screen according to movement of the magic remote controller. A channel transition result may depend on a blended image state at the predicted release time.

For example when more than 50 of the total area of the blended image corresponds to the captured video frame or of the previously displayed broadcast image the broadcast image of the previous channel can be displayed. When more than 50 of the total area of the blended image corresponds to the capture image or of the neighboring upper lower channel transition to the neighboring upper lower channel can be performed. When the previous channel is maintained or changed to the neighboring channel after button release information or on the previous channel or changed channel may be displayed as OSD and a broadcast image or of the corresponding channel may be displayed.

The embodiment illustrated in shows input change to a smart TV application menu referred to as a smart TV menu hereinafter during display of a broadcast image.

A pointer sensing region or may be set on a screen or on which a broadcast image is displayed having a predetermined distance from the upper lower edge of the screen. When the pointer of the magic remote controller is located in the pointer sensing region or OSD or with respect to input change such as smart TV menu external input may be displayed on the basis of the position of the pointer. Simultaneously OSD or indicating information about a currently broadcast program may be displayed. The OSD with respect to external input may include an external input name or an external device name.

When the button of the magic remote controller is pressed while the OSD or with respect to input change is displayed an input change command signal is input. The displayed broadcast image may be paused according to the input change command signal. Then the video frame of the paused broadcast image is captured and an image corresponding to the smart TV menu or external input is captured and loaded.

When the magic remote controller is moved with the button thereof pressed to drag the pointer on the screen the captured video frame or is moved in the drag direction. Here the image or corresponding to the smart TV menu or external input may be displayed in a vacant area of the screen which is generated when the captured video frame or is moved according to drag operation. That is the captured video frame or and the image or corresponding to the smart TV menu or external input may be blended to form phased images in a screen change process. Image blending may be performed on the basis of 2D graphics acceleration.

Specifically the result of may be obtained according to drag direction. When the pointer is dragged to the right with the button of the magic remote controller pressed the smart TV menu image may be blended with the captured video frame and displayed as shown in . When the pointer is dragged to the left with the button of the magic remote controller pressed the external input image may be blended with the captured video frame and displayed as shown in .

When the button of the magic remote controller is released after the drag operation the previous channel may be maintained or input change to the smart TV menu or external input may be performed. Here a release time is predicted in consideration of acceleration of movement of the pointer on the screen according to movement of the magic remote controller. A channel transition result may depend on blended image state at the predicted release time.

For example when more than 50 of the total area of the blended image corresponds to the captured video frame or of the previously displayed broadcast image the broadcast image of the previous channel can be displayed. When more than 50 of the total area of the blended image corresponds to the image or corresponding to the smart TV menu or external input input change to the corresponding image can be performed. When the previous channel is maintained after button release information on the previous channel may be displayed as OSD and the broadcast image of the previous channel may be displayed. Upon input change to the smart TV menu the smart TV menu image may be displayed on the overall area of the screen. Upon change to the external input OSD representing information on the external input may be displayed and the image corresponding to the external input may be displayed.

Referring to the EPG display screen may be segmented into a first area displaying OSD with respect to current channel and input information a second area displaying OSD with respect to detailed information on the current channel and input a third area displaying OSD with respect to a channel list and a fourth area displaying OSD with respect to EPG.

Upon display of the OSD with respect to the current channel and input information in the first area a pointer capable of dragging the OSD may be displayed in the form of a bookmark arrow or triangle along with the OSD.

Upon display of the OSD with respect to the detailed information on the current channel and input in the second area a pointer capable of dragging the OSD may be displayed in the form of a bookmark arrow or triangle along with the OSD.

Upon display of the OSD with respect to the channel list in the third area a pointer capable of dragging the OSD may be displayed in the form of a bookmark arrow or triangle along with the OSD.

Upon display of the OSD with respect to the EPG in the fourth area a pointer capable of dragging the OSD may be displayed in the form of a bookmark arrow or triangle along with the OSD.

When the magic remote controller is moved to move the pointer on the screen to the first area or the button of the magic remote controller is pressed OSD with respect to current channel and input information may be displayed in the first area . When the pointer is dragged to upper left the current channel and input information OSD may disappear from the screen. When the pointer is dragged to the second area that is to the right OSD with respect to detailed information on the current channel and input may be displayed . When the pointer is dragged to the third area that is to lower left OSD with respect to the channel list may be displayed . When the pointer is dragged to the fourth area that is to the lower right EPG OSD may be displayed .

The OSD with respect to the detailed information on the current channel and input may be displayed in the second area . When the pointer is dragged to the left the OSD may disappear. The EPG OSD may be displayed when the pointer is dragged to the fourth area that is downward .

The channel list OSD may be displayed in the third area . The channel list OSD may disappear when the pointer is dragged upward. The EPG OSD may be displayed when the pointer is dragged to the fourth area that is to the right.

A user may drag the pointer by moving the magic remote controller on the channel list OSD so as to search channels. In addition the user may select or change a channel by locating the pointer on the corresponding channel and clicking the pointer. In the case of channel change the channel list OSD may be maintained or disappear.

When the button of the magic remote controller is released the EPG may be displayed on the screen along with the current channel and input information detailed information and channel list . The user may check a program schedule through the EPG .

The EPG OSD may be displayed in the fourth area. The EPG OSD may disappear when the pointer is dragged to the upper left. The OSD representing the detailed information on the current channel and input may be displayed when the pointer is dragged to the second area that is upward. The channel list OSD may be displayed when the pointer is dragged to the third area that is to the left.

The user may drag the pointer by moving the magic remote controller on the displayed EPG and the channel list OSD so as to search channels. Specifically according to preferred examples and of the present invention shown in the channel list OSD can be searched by dragging the pointer up and down and a time line indicating program scheduling can be searched by dragging the pointer to the left and right.

In addition the user may display additional information on the OSD representing the detailed information on the current channel and input in the third area by clicking the title of a desired program on the EPG OSD . The user may perform reservation and recording of a program through the displayed additional information.

In the EPG display UI described with reference to the currently displayed broadcast image can be continuously displayed without being stopped. All OSDs and related to the EPG may be displayed in a transparent manner such that a displayed background image can be seen. Transparent OSD may be implemented according to alpha blending.

Display of the OSDs and during display of the background image may be implemented according to a 2D graphics acceleration engine.

Referring to the digital broadcast receiver using the magic remote controller may include a UI a UI input platform an HD display engine a graphics engine and or an input scene capture manager .

When a command signal from a user is input to the magic remote controller information on the position and movement of the magic remote controller and the user command signal may be transmitted to the UI of the digital broadcast receiver through a Bluetooth channel. When the user moves the magic remote controller to a specific side region of the screen the UI may calculate the position of the pointer through coordinates. OSD with respect to channel input change or EPG may be displayed at the calculated position S 

When the user presses the button of the magic remote controller a user command signal with respect to channel input change or EPG display is input to the UI . Display of a currently displayed broadcast image may be paused according to the user command signal. Simultaneously the UI may transmit to the platform information on the currently displayed broadcast image and a target input image along with channel input change start information. The target input image may be a broadcast image of a neighboring channel a smart TV menu an image corresponding to external input or an EPG display image S .

The platform may capture still images of the currently displayed broadcast image and the target input image through the HD display engine and the input scene capture manager S .

When the user drags the pointer while pressing the button of the magic remote controller the UI may calculate the position of the pointer and acceleration information and transmit the calculation result to the platform . The platform may display an image corresponding to the position and movement of the pointer on the screen through the UI S .

When the user releases the button of the magic remote controller the UI calculates the position of the pointer and acceleration information. The UI determines whether the channel input is changed or EPG is displayed through the calculated position and acceleration information. The platform may display phased images and complete screen change effect S .

Upon completion of channel input change OSD with respect to information on the corresponding channel input may be displayed S .

The apparatus for implementing the magic remote controller UI according to the present invention may include a magic remote controller a digital broadcast receiver and or an external device . Preferred examples of the external device may include cable a set top box a BluRay player and or a game console. The digital broadcast receiver and the external device may be connected . Preferred examples of connection between the digital broadcast receiver and the external device may include connection according to HDMI.

The digital broadcast receiver has evolved to provide a TV broadcasting function using cable Internet services entertainment services and various multimedia information provision services in addition to TV broadcasting functions using aerial propagation. Accordingly user experience in controlling the TV broadcasting function is required even when an external device connected to the digital broadcast receiver is controlled.

According to the apparatus for implementing the magic remote controller UI illustrated in even the external device connected to the digital broadcast receiver can be controlled using the magic remote controller and the UI consistent with TV use experience can be provided even when the external device is connected to the digital broadcast receiver .

A Bluetooth channel and an IR channel may be used for a signal transmission mechanism among the magic remote controller the digital broadcast receiver and the external device . Since the external device cannot directly recognize the position and motion of the magic remote controller the digital broadcast receiver converts information on the position and motion of the magic remote controller into an IR code and sends the IR code to the magic remote controller. The magic remote controller sends the received IR code to the external device .

When a user command signal is input to the magic remote controller information on the position and motion of the magic remote controller and the user command signal may be sent to the digital broadcast receiver through the Bluetooth channel . The UI of the digital broadcast receiver can detect the type of the external device in an external input mode. When connection of the digital broadcast receiver and the external device is achieved by HDMI a function of detecting the code of the external device can be supported. When other connection schemes are used the user may directly input the code.

The digital broadcast receiver may send the IR code to the magic remote controller using the Bluetooth channel . The IR code corresponds to a remote control code of the external device and may be obtained from an IR code database included in the digital broadcast receiver or the Internet.

The magic remote controller may send the IR code to the external device using IR output. Upon reception of the IR code the external device can recognize the information on the position and motion of the magic remote controller and the user command signal. Accordingly a function corresponding to the user command signal can be executed after the external device receives the IR code.

The embodiment illustrated in discloses a channel change process when an external device is connected to the digital broadcast receiver.

In the channel change and input change process when the external device is connected to the digital broadcast receiver the same UI as that of a digital broadcast receiver receiving broadcast signals according to aerial propagation may be implemented. That is channel input change in image reproduction by the external device can be performed in the same manner as channel input change in the digital broadcast receiver for the magic remote controller described with reference to .

In channel input change in image reproduction by the external device however a capture image of a target input image is not immediately loaded and black mute screens and can be loaded. That is it is possible to display the black mute screens and instead of capture images and of the target input image for a screen change standby time of about one to two seconds. The capture images and of the target input image can replace the black mute screens and after the lapse of the screen change standby time. When it is difficult to display the capture images and of the target input image the target input image may be immediately displayed upon completion of channel input change.

Referring to the trick mode display screen may include OSDs with respect to pause play fast forward FF rewind REW previous chapter and next chapter . The OSDs and shown in may be displayed along with played images on the screen on which the played images are displayed.

When the pointer corresponding to the magic remote controller is dragged to the left and right with the button of the magic remote controller pressed and then the button is released during playback of images images being played at a normal speed can be played at an increased speed . Specifically according to the example illustrated in a fast forward command signal can be transmitted and FF OSD representing a fast forward function can be displayed when the pointer is dragged to the left . When the fast forward command signal is transmitted twice or more by repeatedly dragging the pointer to the left a fast forward speed can be increased. On the contrary a rewind command signal can be transmitted and REW OSD representing a rewind function can be displayed when the pointer is dragged to the right. When the rewind command signal is transmitted twice or more by repeatedly dragging the pointer to the right a rewind speed can be increased. When the button of the magic remote controller is clicked during fast playback the fast playback mode changes to the normal playback mode.

When the pointer is dragged upward downward with the button of the magic remote controller pressed and then the button is released during playback of images chapter change can be performed . Specifically a command signal for changing to the previous chapter can be transmitted and OSD representing the previous chapter can be displayed when the pointer is dragged upward. On the contrary a command signal for changing to the next chapter can be transmitted and OSD representing the next chapter can be displayed when the pointer is dragged downward.

When the pointer is dragged in one direction and then dragged again in a different direction with the button of the magic remote controller pressed a command signal according to the first drag can be ignored whereas the final command signal according to the final drag can be considered to be valid. Accordingly OSD according to the first drag can be deleted and OSD according to the final drag can be displayed.

The flowchart illustrated in shows a UI implementation mechanism of an apparatus for implementing a magic remote controller UI when the external device is connected to the digital broadcast receiver which is described with reference to .

Referring to the apparatus for implementing the magic remote controller UI may include a magic remote controller a UI a UI input platform an external device and or a TV server . A preferred example of the external device may include a set top box STB . A preferred example of the TV server may include the Internet.

The UI implementation mechanism when the external device is connected to the digital broadcast receiver can be divided into an input change process S S and S and an external device using process S S S and S.

For input change the user may input a command signal for changing an input mode of the digital broadcast receiver UI to an external input mode using the magic remote controller . Upon input of the input mode change command signal the platform can change the input mode of the digital broadcast receiver UI to the external input mode S .

The platform may read information on the external device connected to the digital broadcast receiver S . The information on the external device can be automatically detected when the external device is connected to the digital broadcast receiver through HDMI and the user can directly input the information on the external device when the external device is connected to the digital broadcast receiver through other connection schemes. The information on the external device may include the name type etc. of the external device .

The platform may search the IR database of the digital broadcast receiver for an IR code corresponding to the external device S . When the IR database does not include the information on the external device the TV server or the Internet may be requested to provide the IR codes or to update the IR database and the IR code may be received S .

Upon input mode change the external device may be used through interaction of the magic remote controller the UI and the external device .

Upon input of a user command signal to the magic remote controller information on the position and motion of the magic remote controller and the user command signal may be send to the UI of the digital broadcast receiver through a Bluetooth channel. The UE may deliver the information on the position and motion of the magic remote controller and the user command signal to the platform S .

The platform may search the IR database for the IR code corresponding to the external device and send the IR code to the UI S .

The platform may transmit the IR code to the magic remote controller through the Bluetooth channel S .

The magic remote controller may send a user input command signal according to the IR code to the external device using IR output. The external device may execute a corresponding function according to the received user input command signal S .

The mechanism S of executing the function corresponding to the user input command may be achieved through the digital broadcast receiver UI platform HD display engine graphics engine and or capture manager S to S as shown in .

Specifically illustrates embodiments of the method for controlling a digital broadcast receiver according to the present invention described with reference to .

The magic remote controller can transmit control signals to the digital broadcast receiver through Bluetooth. Here the control signals may include a first signal representing a state in which the button of the magic remote controller is clicked a second signal representing a state in which the magic remote controller is dragged with the button thereof clicked and a third signal representing a state in which the button of the magic remote controller is released S .

Specifically as shown in a user command signal is input to the magic remote controller information on the position and motion of the magic remote controller and the user command signal may be sent to the UI of the digital broadcast receiver through the Bluetooth channel S .

Specifically when the user moves the magic remote controller to a specific side area of the screen the UI can calculate the position of the pointer through coordinates as illustrated in . OSD with respect to channel input change or EPG may be displayed at the calculated position S . When the user presses the button of the magic remote controller a user command signal with respect to channel input change or EPG display is input to the UI S . The position and motion of the magic remote controller can be indicated through the pointer on the screen. When the second signal is received the pointer may be displayed being moved in a direction in which the magic remote controller is moved S .

Specifically as illustrated in when the user moves the magic remote controller while pressing the button thereof drag according to the second signal the UI can calculate the position and acceleration information of the pointer and send the calculation result to the platform S .

Whether predetermined screen change is performed may be determined according to the control signal S .

Specifically as illustrated in when the user releases the button of the remote controller the UI calculates the position and acceleration information of the pointer. The UI may determine whether channel input change is performed or EPG is displayed through the calculated position and acceleration information S .

Specifically as illustrated in the platform may capture still images of a currently displayed image and a target input image through the HD display engine and the capture manager S .

Specifically as illustrated in the platform may form phased images necessary for screen change using the graphics engine S . When the user moves the magic remote controller the platform may display images corresponding to the position and motion of the pointer on the screen through the UI S .

Specifically as illustrated in the platform may display phased images thereby achieving screen change effect S . When screen change effect is achieved the UI may perform channel input change or EPG display S . Upon completion of channel input change OSD with respect to corresponding channel input information may be displayed S .

Specifically shows embodiments of the method for implementing the magic remote controller UI according to the present invention described with reference to .

The magic remote controller may send control signals to the digital broadcast receiver through Bluetooth. The control signals may include a first signal representing a state in which the button of the magic remote controller is clicked a second signal representing a state in which the magic remote controller is dragged with the button thereof clicked and a third signal representing a state in which the button of the magic remote controller is released S .

Specifically as shown in a user command signal is input to the magic remote controller information on the position and motion of the magic remote controller and the user command signal may be sent to the UI of the digital broadcast receiver through the Bluetooth channel. The UI may send the information on the position and motion of the magic remote controller and the user command signal to the platform S .

The digital broadcast receiver may send an IR code corresponding to an external device connected to the digital broadcast receiver to the magic remote controller S .

Specifically as illustrated in the platform may search the IR database for the IR code corresponding to the external device and send the IR code to the UI S . The platform may transmit the IR code to the magic remote controller through Bluetooth S .

Specifically as shown in the magic remote controller may transmit a user input command signal according to the IR code to the external device using UI output S . The external device may execute a function corresponding to the received user input command signal.

Specifically when the user moves the magic remote controller to a specific side area of the screen the UI can calculate the position of the pointer through coordinates as illustrated in . OSD with respect to channel input change or EPG may be displayed at the calculated position S . When the user presses the button of the magic remote controller a user command signal with respect to channel input change or EPG display is input to the UI S .

The position and motion of the magic remote controller can be indicated through the pointer on the screen. When the second signal is received the pointer may be displayed being moved in a direction in which the magic remote controller is moved S .

Specifically as illustrated in when the user moves the magic remote controller while pressing the button thereof drag according to the second signal the UI can calculate the position and acceleration information of the pointer and send the calculation result to the platform S .

Whether predetermined screen change is performed may be determined according to the control signal S .

Specifically as illustrated in when the user releases the button of the remote controller the UI calculates the position and acceleration information of the pointer. The UI may determine whether channel input change is performed or EPG is displayed through the calculated position and acceleration information S .

Specifically as illustrated in the platform may capture still images of a currently displayed image and a target input image through the HD display engine and the capture manager S .

Specifically as illustrated in the platform may form phased images necessary for screen change using the graphics engine S . When the user moves the magic remote controller the platform may display images corresponding to the position and motion of the pointer on the screen through the UI S .

Specifically as illustrated in the platform may display phased images thereby achieving screen change effect S . When screen change effect is achieved the UI may perform channel input change or EPG display S . Upon completion of channel input change OSD with respect to corresponding channel input information may be displayed S .

The present invention relates to a digital broadcast receiver for a magic remote controller and a method of controlling the same. The present invention is not limited to the aforementioned embodiments and various equivalent modifications are possible within the spirit and scope of the present invention as those skilled in the relevant art will recognize and appreciate. As indicated these modifications may be made to the present invention in light of the foregoing description of illustrated embodiments of the present invention and are to be included within the spirit and scope of the present invention.

