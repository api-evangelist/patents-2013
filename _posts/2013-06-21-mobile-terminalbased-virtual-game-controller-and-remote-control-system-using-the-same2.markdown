---

title: Mobile terminal-based virtual game controller and remote control system using the same
abstract: Disclosed herein are a virtual controller client mobile terminal-based virtual game controller and a remote control system using the same. The remote control system includes a virtual controller server and a virtual controller client. The virtual controller server generates button setting information including mapping relationship between key inputs and virtual input messages, transfers the button setting information, extracts a key input from a virtual input message, and provides the key input to the application. The virtual controller client specifies an arrangement and attributes of virtual buttons based on the button setting information, generates a virtual button screen on the touch screen of the mobile terminal, generates a touch input message based on touch event objects generated based on touch signals for regions corresponding to the virtual buttons, and converts the touch input message into a virtual input message and outputs the virtual input message.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09612709&OS=09612709&RS=09612709
owner: RESEARCH & BUSINESS FOUNDATION SUNGKYUNKWAN UNIVERISTY
number: 09612709
owner_city: Suwon-si
owner_country: KR
publication_date: 20130621
---
This application claims the benefit under 35 U.S.C. 119 a of Korean Patent Application No. KR 10 2012 0067288 filed on Jun. 22 2012 in the Korean Intellectual Property Office the entire disclosure of which is incorporated herein by reference for all purposes.

The present invention relates generally to a user controller and more particularly to a mobile terminal based remote control system.

Most games running on personal computers and game consoles are chiefly played in such a manner that a gamer manipulates the movement of principal characters or principal objects or interactions with a game environment. This manipulation may be performed using a proprietary controller such as a proprietary joystick or a joypad in the case of a game console or a general purpose user controller such as a mouse or a keyboard in the case of a personal computer.

There is a contradiction in the playing of games in various genres and forms on a specific game console using a proprietary controller. That is a single common controller becomes expensive and complicated if it is used to deal with various game manipulation rules and game manipulation rules should be simplified if a controller is constructed in a simple form.

Meanwhile when a general purpose user controller such as a mouse or a keyboard is used the inherited limitations and disadvantages of the mouse or keyboard are maintained because they are not manufactured only for games. For example although a mouse is easy to manipulate the number of buttons thereof is limited and the combinations of buttons are limited. In contrast although a keyboard can deal with various game manipulation rules but may be clumsy because of so many keys and so large the size of the keyboard.

As a result if the interface of a controller can be optimized for each one of games having various manipulation methods a single controller can be applied to various games.

Accordingly the present invention has been made keeping in mind the above problems occurring in the prior art and an object of the present invention is to provide a mobile terminal based virtual controller capable of manipulating an application running on a remote computer and a remote control system using the same.

According to an aspect of the present invention there is provided a virtual controller client the virtual controller client operating based on a mobile terminal so that the virtual controller client can remotely communicate with a virtual controller server running on a computer for remote key input on an application running on the computer the virtual controller client including 

a button setting adjusting unit configured to receive button setting information including mapping relationship between key inputs to the application and virtual input messages from the virtual controller server and to specify an arrangement and attributes of virtual buttons based on the received button setting information 

a user virtual button interface configured to generate a virtual button screen in which touch regions corresponding to the virtual buttons are visually displayed and to display the virtual button screen on a touch screen of the mobile terminal 

a touch event filter configured to generate touch input messages that can be recognized as key inputs by the application based on touch event objects that are generated based on touch signals for regions corresponding to the virtual buttons which belong to touch signals input via the touch screen and

a client message interfacing unit configured to convert the touch input message into a virtual input message in a form that can be received by the virtual controller server and to output the virtual input message.

The user virtual button interface may activate an acceleration sensor of the mobile terminal so that movements of the mobile terminal can be detected 

the virtual controller client may further include an acceleration data filter configured to generate a movement input message that can be recognized as a key input by the application based on acceleration data that is generated based on an acceleration signal generated by the acceleration sensor and

the client message interfacing unit may operate such that the client message interfacing unit converts the touch input message or movement input message into a virtual input message in a form that can be received by the virtual controller server and outputs the virtual input message.

According to another aspect of the present invention there is provided a virtual controller server the virtual controller server operating on a computer so that the virtual controller server can remotely communicate with a virtual controller client running on a remote mobile terminal including a touch screen for remoter key input on an application running on the computer the virtual controller server including 

a button setting generating unit configured to generate button setting information including mapping relationship between key inputs to the application and virtual input messages 

a server message interfacing unit configured to transmit a setting message including the button setting information to the virtual controller client and to receive a virtual input message generated based on a touch on the touch screen from the virtual controller client and

a key mapping unit configured to identify a key input value mapped to the received virtual input message based on the button setting information.

The mobile terminal may further include an acceleration sensor configured to detect movements and the server message interfacing unit may operate such that it receives a virtual input message generated based on a movement of the mobile terminal.

The key mapping unit may transfer a key input value to the application via the message transfer architecture of an operating system that runs the application on the computer.

The key mapping unit may transfer a key input value to the application via the input and output application programming interface API of an operating system that runs the application on the computer.

According to another aspect of the present invention there is provided a remote control system including 

a virtual controller server configured to run on a computer such that it generates button setting information including mapping relationship between key inputs to an application running on the computer and virtual input messages transfers the button setting information to a virtual controller client extracts a key input from a virtual input message received from the virtual controller client and provides the key input to the application and

a virtual controller client configured to remotely communicate with the computer configured to run on a mobile terminal including a touch screen and configured to specify an arrangement and attributes of virtual buttons based on the button setting information received from the virtual controller server to generate a virtual button screen in which touch regions corresponding to the virtual buttons are visually displayed on the touch screen of the mobile terminal to generate a touch input message that can be recognized as a key input by the application based on touch event objects generated based on touch signals for regions corresponding to the virtual buttons which belong to touch signals input via the touch screen and to convert the touch input message into a virtual input message in a form that can be recognized by the virtual controller server and output the virtual input message.

the virtual controller client may operate such that it activates an acceleration sensor of the mobile terminal so that movements corresponding to the virtual buttons can be detected generates a movement input message that can be recognized as a key input by the application based on acceleration data that is generated based on an acceleration signal generated by the acceleration sensor and converts the touch input message or movement input message into a virtual input message in a form that can be received by the virtual controller server and then outputs the virtual input message.

According to still another aspect of the present invention there is provided a remote controller interfacing method the remote controller interfacing method using a virtual controller server running on a computer and a virtual controller client running based on a remote mobile terminal including a touch screen in order to perform key input on an application running on the computer the remote controller interfacing method including 

generating by the virtual controller server button setting information including mapping relationship between key inputs required by the application and virtual input messages to be transmitted by the virtual controller client and transferring by the virtual controller server the button setting information to the virtual controller client 

specifying by the virtual controller client an arrangement and attributes of virtual buttons based on the button setting information and displaying by the virtual controller client a virtual button screen in which virtual button regions are visually arranged on the touch screen 

generating by the virtual controller client touch event objects based on a touch signal generated by the touch screen and generating by the virtual controller client a touch input message based on the valid touch event objects 

outputting by the virtual controller client a virtual input message generated based on the touch input message 

identifying by the virtual controller server a key input value mapped to the received virtual input message based on the button setting information and

generating by the virtual controller client a movement input message that can be recognized as a key input by the application based on acceleration data that is generated based on an acceleration signal generated by the acceleration sensor and

converting by the virtual controller client the movement input message into a virtual input message in a form that can be received by the virtual controller server and outputting by the virtual controller client the virtual input message.

The key input value identified by the virtual controller server may be transferred to the application via the message transfer architecture of an operating system that runs the application on the computer.

The key input value identified by the virtual controller server may be transferred to the application via the input and output API of an operating system that runs the application on the computer.

Specific structural and functional descriptions of embodiments of the present invention will be given merely for the illustration of the present invention. Therefore embodiments of the present invention may be embodied in various forms and should not be interpreted as being limited to the embodiments that will be described below.

The embodiments of the present invention will be described in detail below with reference to the accompanying drawings. Like reference numerals will be assigned to like elements throughout the accompanying drawings and redundant descriptions of the like elements will be omitted.

Referring to the virtual controller server is executed as a background task in the personal computer on which a game application to be controlled is running and the virtual controller client is executed as a foreground task in the mobile terminal .

The personal computer may be schematically viewed as including a wired wireless communication interface an application layer a subsystem layer and a kernel mode . In this case the game application and the virtual controller server may be viewed as running in the application layer and the subsystem layer respectively.

Although the game application is referred to for the sake of illustration the present invention is not limited to game applications but may be applied to any types of applications that require users to remotely control functions and operations of the applications somewhat apart from screens.

The virtual controller server generates button setting information including mapping relationship between key inputs required by the game application for example directional key inputs related to the movement of a game character direction key inputs related to the gaze direction of a game character operation key inputs related to the actions of a game character and function key inputs related to the playing of a game and virtual input messages to be transmitted from the virtual controller client . It also transfers a setting message encapsulating the button setting information to the virtual controller client of the mobile terminal extracts a key input intended by a gamer from a virtual input message received from the virtual controller client and provides information about the key input to the game application .

For these purposes the virtual controller server may include a button setting generating unit a server message interfacing unit a key mapping unit and a message converting unit . The virtual controller server may use a legacy input output processing unit for the input and output of a keyboard and a mouse in the kernel mode and a Direct Input application programming interface API in the application layer .

The mobile terminal may include a wired wireless communication interface a touch screen configured to display a virtual button screen to a user and to generate a touch signal based on a location touched by a user an acceleration sensor configured to generate an acceleration signal in response to the tilt or movement of the mobile terminal in a 3 dimensional space and a mobile OS platform on which the virtual controller client runs.

The virtual controller client runs on the mobile OS platform and may extract the button setting information from the setting message transferred from the virtual controller server of the personal computer via the wired wireless communication interface generate a virtual button screen according to the extracted button setting information and display the virtual button screen on the touch screen .

Thereafter the virtual controller client generates a virtual input message for the game application in an integrated manner based on a touch input message generated by the touch screen that identifies a location where a user has performed a touch operation on a displayed virtual button screen and a movement input message generated by the acceleration sensor that detects movement when a user moves the mobile terminal .

For this purpose the virtual controller client may include a button setting adjusting unit a user virtual button interface a touch event generating unit a touch event filter an acceleration data generating unit an acceleration data filter and a client message interfacing unit .

In an embodiment more than one single virtual controller client may be connected to a single virtual controller server . In this case the virtual controller server may bind virtual input messages input from a plurality of virtual controller clients and then provide the virtual input messages to the application .

In such an embodiment for example a plurality of gamers may control a plurality of game characters at the same time within a single game and a plurality of mobile terminals may generate a large virtual button screen as a whole by causing the plurality of mobile terminals to display respective portions of a single virtual button screen.

The operations of the virtual controller server and the virtual controller client will be sequentially described below.

First a gamer runs the virtual controller server and the application on the personal computer then runs the virtual controller client on the mobile terminal and manipulates the personal computer and the mobile terminal to recognize each other on a single wired wireless network via the wired wireless communication interfaces and .

The wired wireless communication interfaces and may appropriately use a serial wired interface based on an open or proprietary standard or well known or commonly used short distance bi directional wireless communication technologies such as IrDA Bluetooth WiFi WiFi Direct or 2.4 GHz band RF interfacing technology.

In order to enable the mobile terminal to display a virtual button screen optimized for the performance of a game of the game application the button setting generating unit of the virtual controller server generates button setting information including mapping relationship between key inputs required by the application and virtual input messages to be transmitted by the virtual controller client .

The button setting information is information indicating which key input should be mapped to a specific virtual input message when the virtual controller client returns the specific virtual input message to the virtual controller server .

In other words a button setting information is a kind of information that indicates which form of virtual input message should be provided from the virtual controller client for a specific key input value to the game application .

For example if the application is set such that it recognizes the s key of a keyboard as a character forward movement key the button setting information may be generated such that the s key of the keyboard is mapped to a virtual input message based on a touch input message that is generated by touching the forward movement button region of the virtual button screen. In another example if the application is set such that it recognizes the movement of a mouse as a character gaze direction key the button setting information may be generated such that a mouse movement key is mapped to a virtual input message based on a movement input message that is generated by tilting the mobile terminal .

This button setting information may be previously generated by a game producer or may be generated in accordance with the intention of a gamer.

Furthermore the button setting information may be dynamically changed while playing a game. For example to make a progress in a game sometimes a character needs to move in a field and in another time a character needs to grow up. Those cases may require different game interfaces. In these cases the virtual controller server may dynamically change the button setting information in accordance with a game environment and apply on the fly the changed button setting information to the virtual controller client .

The button setting generating unit transfers the button setting information to the server message interfacing unit and the server message interfacing unit in turn transmits the button setting information to the mobile terminal via the wired wireless communication interface .

The button setting information received via the wired wireless communication interface of the mobile terminal is transferred to the button setting adjusting unit .

The button setting adjusting unit may generate the virtual button setting information by specifying the arrangement and attributes of virtual buttons that will generate virtual input messages that should be provided to the virtual controller server by the virtual controller client based on the button setting information. The button setting adjusting unit may specify the arrangement or attributes of buttons as previously predetermined or in accordance with the intention of a gamer.

For example the button setting adjusting unit may generate the virtual button setting information so that a relatively wide touch region on the left side of a virtual button screen is mapped to four direction keys related to the movement of a game character a plurality of relatively small touch regions on the right side of the virtual button screen are mapped to an operation key related to the operation of the game character and function keys related to the playing of a game and the direction of movement of the mobile terminal is mapped to a game character gaze direction key.

The user virtual button interface generates a virtual button screen on which touch regions corresponding to virtual buttons are visually displayed in accordance with the virtual button setting information displays the virtual button screen on the touch screen and activates the acceleration sensor corresponding to the virtual buttons.

In this case the virtual button screen is not limited to the commonly used button arrangement of a game controller that is an arrangement that includes direction keys on the left side and control buttons on the right side. For example the virtual button screen may be generated based on various skins that are created by imitating a piano keyboard a drum set the steering wheel of a Formula 1 F1 car the control board of an airplane etc.

Furthermore one or more mobile terminals may be enabled to display respective portions of one big virtual button screen thereby overcoming a limitation related to the limited screen size of the mobile terminal.

By doing so a gamer is ready to control the playing of a game running on a personal computer or the like while holding the mobile terminal in his or her hands.

While playing a game a gamer may touch the virtual buttons visually displayed on the touch screen of the mobile terminal freely move the mobile terminal in a 3D space to adjust the roll the pitch and the yaw.

When a gamer touches the virtual button regions displayed on the touch screen touch signals are generated and transferred to the touch event generating unit .

The touch event generating unit generates touch event objects based on valid touch signals related to regions corresponding to the virtual buttons which belong to input touch signals.

The touch event filter may generate touch input messages that can be finally recognized as key inputs by the game application based on the valid touch event objects. For example from a touch event object generated as a shaped touch region has been touched on the touch screen for one second a touch input message equivalent to a key input that is generated when the s key of the keyboard has been pressed for one second may be generated.

Furthermore when a gamer tilts or moves the mobile terminal the acceleration sensor generates an acceleration signal. The generated acceleration signal is input to the acceleration data generating unit and processed so as to be valid acceleration data.

The acceleration data filter may generate a movement input message that can be finally recognized as a key input by the game application based on the valid acceleration data.

The client message interfacing unit converts the touch input message or the movement input message into a virtual input message in a form that can be acknowledged by the virtual controller server and transmits the virtual input message to the personal computer via the wired wireless communication interface .

The virtual input message received by the wired wireless communication interface of the personal computer is transferred to the key mapping unit via the server message interfacing unit .

The key mapping unit may identify the key input value mapped to the virtual input message received from the virtual controller client based on the button setting information previously set by the button setting generating unit .

The key input value identified through the mapping may be input to the application using a plurality of methods.

One of these methods uses a message transfer architecture that is provided by the operating system of the personal computer . For example the key input value is transferred to the application using the Windows message architecture of the personal computer like a keyboard input or mouse input.

Another method uses an input output API that is provided by the operating system of the personal computer . For example the key input value is transferred to the application via the legacy input output processing unit and the Windows direct input API that process the keyboard input and output of the personal computer .

From the point of view of the application the key input based on the virtual input message generated and provided by the virtual controller client is indistinguishable from the key input generated by a keyboard or a mouse installed in the actual personal computer .

Referring to the illustrative virtual button screen is displayed on the touch screen of the mobile terminal . The illustrative virtual button screen includes four direction movement button regions and four function button regions.

When a gamer touches the movement button region or function button region of the touch screen while holding the mobile terminal a virtual input message is generated based on a touch signal. The generated virtual input message is transmitted from the mobile terminal to the personal computer and is then provided as a movement key or a function key input to the game application that is running on the personal computer .

Referring to first it is assumed that the virtual controller server and the application are run on the personal computer the virtual controller client is run on the mobile terminal having the touch screen and the acceleration sensor and the personal computer and the mobile terminal are connected to each other via the wired wireless communication interfaces and .

At step S the virtual controller server generates button setting information including mapping relationship between key inputs required by the application and virtual input messages to be transmitted from the virtual controller client and transfers a setting message including the button setting information to the virtual controller client of the mobile terminal .

At step S the virtual controller client specifies the arrangement and attributes of virtual buttons based on the button setting information extracted from the received setting message and displays a virtual button screen on which virtual button regions are visually arranged on the touch screen or activates the acceleration sensor .

At step S the virtual controller client generates touch event objects based on a touch signal that is generated when a gamer touches the virtual button region of the touch screen and generates a touch input message based on the valid touch event objects.

At step S the virtual controller client generates acceleration data based on an acceleration signal that is generated by the acceleration sensor when a gamer tilts or moves the mobile terminal and generates a movement input message based on the valid acceleration data.

At step S the virtual controller client converts the touch input message or movement input message into a virtual input message in a form that can be transmitted to the virtual controller server and transmits the virtual input message to the personal computer via the wired wireless communication interface .

At step S the virtual controller server identifies a key input value mapped to the virtual input message received from the virtual controller client based on the button setting information.

At step S the virtual controller server transfers the identified key input value to the application via a Windows message architecture or a direct input API in the same way as the key input of a legacy controller such as a keyboard or a mouse.

According to the mobile terminal based virtual controller and the remote control system using the same of the present invention a user can configure the virtual controller so that it has an arrangement of buttons that is optimized for each game.

According to the mobile terminal based virtual controller and the remote control system using the same of the present invention a user can run the virtual controller on a mobile terminal such as a smart phone.

According to the mobile terminal based virtual controller and the remote control system using the same of the present invention a user can operate a mobile terminal such as a smart phone as a controller for a game or a remote controller for any one of various purposes.

Although the preferred embodiments of the present invention have been disclosed for illustrative purposes those skilled in the art will appreciate that various modifications additions and substitutions are possible without departing from the scope and spirit of the invention as disclosed in the accompanying claims.

