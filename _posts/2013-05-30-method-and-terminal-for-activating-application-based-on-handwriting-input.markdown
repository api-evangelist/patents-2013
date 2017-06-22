---

title: Method and terminal for activating application based on handwriting input
abstract: A method for controlling an application based on a handwriting input includes recognizing a handwriting input received on a touch panel of a terminal; determining a symbol corresponding to the handwriting input; selecting an application capable of being associated with the symbol; and associating the symbol with a function of the application. A terminal to control an application based on a handwriting input includes a determination unit to recognize a handwriting input received on a touch panel of the terminal, and to determine a symbol corresponding to the handwriting input; and a processor configured to select an application capable of being associated with the symbol, and to associate the symbol with a function of the application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09448652&OS=09448652&RS=09448652
owner: Pantech Co., Ltd.
number: 09448652
owner_city: Seoul
owner_country: KR
publication_date: 20130530
---
This application claims priority from and the benefit of Korean Patent Application No. 10 2012 0058961 filed on Jun. 1 2012 which is hereby incorporated by reference in its entirety for all purposes as if fully set forth herein.

Exemplary embodiments of the present invention relate to a method and a terminal for activating an application based on handwriting input.

When a message is received in a communication terminal a user may view the received message through a screen indicating the arrival of the message and select a reply button to respond to the received message.

If the user selects the reply button an application for sending a reply message may be executed and the user may select a message typing interface or a content input box as the application for sending the message is executed and then a reply may be created through the interface. When the user completes the reply and sends the message via multiple manipulations and conversions of displayed images the user may have an inconvenient experience of manipulations including launching and terminating one or more applications e.g. terminating the application for sending the message. The user may be incapable of replying to the received message without running a separate application or a separate window for sending the message. Further even in a handwriting recognition enabled terminal an application supporting a handwriting input may need to be activated for recognizing the handwriting input in order to write a reply through the recognized handwriting after a message is received. Also multiple manipulation processes described above is involved in sending a message e.g. launching and terminating a handwriting recognition application thereby causing an inconvenience to the user.

Referring to the communication terminal hereinafter a terminal supports a user interface UI to notify a user of a message arrival event such as an arrival of a message and to receive a selection input of the user with respect to the event for example whether to check the message or to reply.

Specifically the terminal provides a user notification to the user such as a notification of arrival of the message by a pop up window on a home screen of the terminal as shown in a screen if the message is received by the terminal.

If a user selects a reply button in the pop up window to reply to the received message the terminal launches a message application for sending a message as shown in a screen .

The user selects a text entry field from the application to input a text message and activates an input editor as shown in a screen . When the user inputs a reply in the activated input editor and selects a send button the reply message is sent to an addressee SKY as shown in a screen .

Referring to if a new message is received by a terminal through a message application installed in the terminal in an operation the message application analyzes the new message and activates a user interface UI for outputting a user notification if a message arrival notification is allowed for a user in an operation . Hereinafter the UI for user notification may be referred to as a user notification UI.

The user notification UI activated by the message application allocates a resource needed for the UI and initiates operating procedures in operation .

Subsequently the user notification UI may analyze pieces of information to be added in activating the message application in operation . The pieces of information may include information related to the received message and notification for example information to be displayed and information of a function that may be executed by an interface e such as a button e.g. the REPLY button and CHECK button in .

The user notification UI is allocated a window other than a window used by an executed application activated in the foreground thereby preparing a resource for displaying a screen in operation . Allocating of the user notification UI may be performed without significantly disturbing the activation and or the display of the executed application activated in the foreground.

The user notification UI displays information received from the message application on the allocated screen in operation .

The user notification UI registers a user event and a selected area in operation . Here the user notification UI registers a basic processing event defined in a relevant UI for example an exit event and a selection event and a touch selection area such as a button of the user notification UI analyzed in operation .

The user notification UI receives various types of events input through the terminal for example a key input and a touch and determines whether the events input correspond to the registered user events as registered in the operation in operation .

If a touch start point where an event is detected in operation is not a registered area of the display screen of the terminal a subsequent touch event may be ignored. Subsequently the user notification UI returns all resources allocated when the activation of the UI is initiated and terminates the operation in operation .

If the touch start point where the event is detected in operation is a registered area the user notification UI determines whether to select or terminate a function of a registered event and performs operations accordingly.

If a function registered in the message application is selected in operation the user notification UI activates the registered function in operation and then terminates the operation in operation .

For example if a message reply function of is selected in operation activation of the reply function is defined in the analysis of the UI. When the defined activation is performed the message application is called and launched based on a defined activation type. A conversation list of a relevant number may need to be defined.

As such when a user notification event occurs such as a message arrival notification the user may need to operate the terminal with multiple touch inputs to activate an application or a particular function. Therefore aspects of the present invention suggest an approach to resolve such issues. The above information disclosed in this Background section is only for enhancement of understanding of the background of the invention and therefore it may contain information that does not form any part of the prior art nor what the prior art may suggest to a person of ordinary skill in the art.

Exemplary embodiments of the present invention provide a method and terminal for controlling an application based on a handwriting input.

Additional features of the invention will be set forth in the description which follows and in part will be apparent from the description or may be learned by practice of the invention.

Exemplary embodiments of the present invention provide a method for controlling an application based on a handwriting input the method including recognizing a handwriting input received on a touch panel of a terminal determining a symbol corresponding to the handwriting input selecting an application capable of being associated with the symbol and associating the symbol with a function of the application.

Exemplary embodiments of the present invention provide a method for controlling an application based on a handwriting input in a first terminal the method including receiving a message from a second terminal displaying a notification indicating the message receipt on a touch screen display of the first terminal receiving a handwriting input on the touch screen display of the first terminal without launching a message application determining a symbol corresponding to the handwriting input and associating the symbol with a function of the message application.

Exemplary embodiments of the present invention provide a terminal to control an application based on a handwriting input the terminal including a determination unit to recognize a handwriting input received on a touch panel of the terminal and to determine a symbol corresponding to the handwriting input and a processor configured to select an application capable of being associated with the symbol and to associate the symbol with a function of the application.

It is to be understood that both forgoing general descriptions and the following detailed description are exemplary and explanatory and are intended to provide further explanation of the invention as claimed. Other features and aspects will be apparent from the following detailed description the drawings and the claims.

The invention is described more fully hereinafter with reference to the accompanying drawings in which exemplary embodiments of the invention are shown. This invention may however be embodied in many different forms and should not be construed as limited to the exemplary embodiments set forth herein. Rather these exemplary embodiments are provided so that this disclosure is thorough and will fully convey the scope of the invention to those skilled in the art. In the drawings the size and relative sizes of layers and regions may be exaggerated for clarity. Like reference numerals in the drawings denote like elements.

In the following description the term terminal may collectively include any electronic device capable of processing a handwriting input through a touch screen display such as a mobile terminal a tablet an electronic pad a plasma display panel PDP a personal digital assistant PDA a personal computer PC a laptop computer and the like. Also the units modules elements devices and components of the apparatuses and or mobile terminals herein described may include hardware and software may also include firmware to perform various operations of the terminal including those described herein and may be combined or remain separate as described.

Referring to a terminal to activate an application based on a handwriting input hereinafter terminal may detect a touch event from a touch display in operation . Here the terminal may be configured to receive a handwriting input on a handwriting input area in a separate layer of a touch display not in an existing layer e.g. a home screen display layer.

As the touch event is detected in operation the terminal may determine whether the touch event is a valid input of handwriting or a simple touch non handwriting touch in operation .

Here the simple touch includes any touch motion which is not defined as a handwriting input for example icon clicking or home screen flicking.

The terminal may determine whether the touch event occurring in a preset area is a valid input of handwriting in operation . Here the preset area may be a part of the display independently allocated to a target application or an entire touch recognition area of the touch display.

The terminal may display a boundary or edge of the entire touch recognition area or the part of the touch display in a distinguishable color or a temporarily flickering mode so that the preset area is recognizable by a user. In particular a handwriting area for a handwriting input on the touch display may be distinguished by the boundary.

The terminal may determine whether the touch event is a valid input of handwriting by activating a handwriting recognition module in operation .

As a result of the determination in operation if the touch event is determined as a valid input of handwriting the terminal may convert the input of handwriting into a text in operation . For example the terminal may use a handwriting conversion engine to convert the input of handwriting into the text. The handwriting conversion engine may be a software engine which calculates a value corresponding to a coordinate acquired from the touch event input on the touch display to convert the touch event into a predefined symbol e.g. a text a number or a special symbol. A user may define a new symbol that corresponds to a handwriting input.

If it is determined that the touch event is not a valid input of handwriting e.g. a simple touch in operation the terminal may terminate a process of activating an application based on a handwriting input. The terminal may select a target application among a plurality of applications in operation if the handwriting input is successfully converted into a text. The selection of the target application may be performed based on UIs for basic functions of the terminal presented on a screen of the touch display or icons and buttons for activating various types of applications selected by the user or automatically set by a program.

The method of activating the application based on the input of handwriting described herein may be widely applied to Android based terminals as well as Microsoft Windows based terminals Real Time Executive Operating System REX OS based feature phones iOS based phones and terminals using other types of operating systems.

Referring to a terminal determines whether a touch event detected by a touch screen display is an input of handwriting in operation . If it is determined that the touch event is not an input of handwriting in operation e.g. a simple touch the terminal may terminate a process of activating an application based on a handwriting input.

If it is determined that the touch event is an input of handwriting in operation the terminal may display the input of handwriting on the touch display in operation . If the touch event is a valid input of handwriting the terminal may display contents of the handwriting input e.g. a recognized text from the handwriting input on a screen to enable the user to identify the recognized contents and to perform a corresponding function. The terminal may display the handwriting input as a handwriting image on a touch screen corresponding to the location of the handwriting input without converting the handwriting input into a text until the handwriting input is completed or converting the handwriting input into a corresponding symbol when each symbol is identified from the handwriting input.

A method of determining whether the input of handwriting is completed in operation will be described in more detail with reference to .

If it is determined that the input of handwriting is completed in operation the terminal converts the input of handwriting into a text in operation . A handwriting conversion engine may be used to convert the input of handwriting into the text and the converted text may be stored. If it is determined that the input of handwriting is not completed the terminal returns to the operation and enters a stand by mode. The handwriting input is displayed on the touch display until the handwriting input is completed.

In operation the terminal may determine whether the text input to the target application selected in operation is a valid input for the target application. For example the terminal may determine whether a function corresponding to the text is registered as registration information for the application selected by the user.

The text input for the target application may be determined to be valid if the text or the format of the text is registered in a database for the target application as the registration information of the target application. For example if a function of the target application corresponding to the text exists in information on functions of the target application included in the registration information the text input to the target application may be determined to be valid.

If the function of the target application corresponding to the text exists in the information on functions of the target application included in the registration information the terminal may extract information about the function of the target application corresponding to the text from the registration information on the target application. For example the function of the target application may include an Action pertaining to an execution command in a mobile operating system e.g. an Android platform.

If it is determined that the text input to the target application is not valid in operation the terminal may terminate a process of activating an application based on a handwriting input.

If it is determined that the text input to the target application is valid in operation the terminal may provide the text to the target application in operation .

Referring to when a message arrives at a communication terminal a terminal of a user the terminal provides a user notification e.g. a message arrival notification on a screen . A pop up window may be displayed on a portion of an upper layer of the home screen layer to display the message arrival notification. If the message arrival notification is displayed on the screen as shown in a handwriting recognition module may be executed to recognize a handwriting input received on a touch screen display.

The window is configured to include a plurality of layers. For example an indicator bar on which the remaining power of a battery and a reception status of an antenna are displayed may be located on a top layer and thus may be always displayed on the screen. An application may be displayed in a lower layer than the indicator bar and hidden when the indicator bar is pulled down over the application.

Further in an exemplary embodiment adopting such a layer concept an additional transparent layer may be launched over a layer in which a call application is implemented thereby receiving a handwriting input through the transparent layer without disturbing the call application. The user notification UI displays information received from the message application on the allocated screen. If the user notification UI displays the information received from the message application on a part of the screen an unused or the remaining area of the allocated window may be displayed to be transparent and the display area for the displayed information is drawn.

After the display of the message arrival notification the user may input a handwriting input YES as a reply on a touch screen display as shown on a screen . Here an area for the user to input the reply may be a separately assigned area from an area for displaying the message arrival notification for example an area disposed above the area for the message arrival notification. However the aspects are not limited as such. The area to input the handwriting input as a reply may be an entire touch recognition area of the touch display.

If the user activates a reply button as shown on a screen the terminal identifies whether a handwriting input action exists in registration information about the reply button. In this example the registration information may include English alphabets and each of the characters Y E and S may be recognized. If information corresponds to the handwriting input action exist in the registration information the terminal recognizes the handwriting input and activates a reply message transmitting action to a telephone number corresponding to the message arrival notification in background by the input written contents. Further by associating a message corresponding to the handwriting input to the message transmitting action a reply to the telephone number is sent with the message corresponding to the handwriting input. Here the reply button may be associated with a handwriting input action and a reply message transmitting action such that a handwriting recognition module and a message transmission function of a message application are activated.

As the reply message transmitting action is activated the message notification is terminated and the terminal displays a result of the activation in background for example a result of a reply message transmission as shown on a screen . Further the message corresponding to the handwriting input may also be displayed as the result.

As described above with reference to and a message reply process with respect to a message arrival notification generally involves a plurality of manipulation operations 1. Notification UI 2. Select a reply 3. Activate a message application 4. Select an input 5. Input a reply message 6. Select a send 7. Terminate the message application and 8. Go back to a state before a message arrives.

However according to the method of activating the application based on the input of handwriting a reply to a message may be sent by implementing a reduced process including 1. Notification UI 2. Input a message via a handwriting input 3. Select a reply to send a message 4. Go back to a state before a message arrives. Here a message transmission may be processed as a background function.

Further the user may process a function on the notification UI directly without activating a separate message application.

Although a message arrival notification has been illustrated in the above a simple UI such as an on the phone or screen menu may be expanded to various functions thereby providing a user with improved convenience. Hereinafter examples of the user interface associated with a handwriting input will be described.

Referring to a handwriting input may be associated with a selected application. For example a handwriting input may be linked to a phone application according to a selection of the dial button associated with the phone application for a registered action corresponding to the button to be performed.

As an example if a user generates a handwriting input corresponding to a phone number e.g. 114 and 911 on a touch screen display as shown in a screen and then selects the dial button with a finger or a pen. Here the action registered in the dial button may include an action of generating a call associated with the number recognized from the handwriting input and registration information about the dial button may include a telephone number input action for generating a call. Thus if the written number e.g. 114 is provided to the target application by selecting the dial button associated with the target application the phone application the terminal may generate a call as shown in a screen .

Referring to the user may input handwriting on a home screen of a touch screen display and the terminal may convert the handwriting input into a text in a predetermined time after the user inputs the handwriting.

The terminal may convert the handwriting input into the text and store the text or display the converted text for example Hi how are you today on the home screen as shown in a screen . The converted text may be displayed in a predetermined or set area with respect to the home screen or other application screens. For example the converted text may be displayed in a blank area of the home screen as shown in the screen .

If the text displayed on the touch display includes a substantial length of handwriting an initial portion of the handwriting e.g. Hi how are you may be displayed in the predetermined area with smaller font size among the entire written contents. For example Hi how are you may be displayed with a smaller font size and the remaining portion TODAY may be displayed with a larger font size as displayed on the screen . Such an arrangement enables the user to verify whether the handwriting is input correctly.

Further if the user completes an input of handwriting on the touch screen display and selects the message icon and registration information of the message icon includes a message input action the terminal may link the recognized text with an application driver. Accordingly an action registered in accordance with the message icon is activated.

If the user inputs the handwriting and then selects the message icon the terminal may activate a message write action using the texts converted from the handwriting input as displayed on a screen . The activation of the message write action may be performed with reference to the registration information of the message icon.

After linking the text converted from the handwriting input with the application driver the terminal may receive an input of handwriting about additional information from the user in a touch recognition area or a preset area of the touch screen display to include the additional information. The preset area may be independently allocated to the target application.

Further if the user inputs information via handwriting on the home screen and then selects a note icon the input information may be stored as a note in a note application. When selecting an icon a launcher e.g. an icon driver may have a priority of an action in registration information about the selected application and provide an extending function enabling an application with an information processing action to be executed.

A pen function may be used to capture a screen through a hardware key or a pen button and to display the captured screen in the background of a note application by activating the note application to enable handwriting to be input. In particular the pen function provides a function of enabling characters to be written by hand with the note application supporting handwriting input formatting the handwritten characters into an image and storing and using the image. However the pen function may be limited to an image sharing function only. Thus the user may not be able to activate a function registered in a particular application such as a function of converting input contents into a text and sending the text as a message or may not be able to provide handwritten contents to the particular application without activating the particular application.

Moreover if the pen function is activated by an application enabling handwriting input e.g. a note application the pen function may be realized within the note application. Unlike the pen function described above a handwriting function may be implemented independently of an operation of a target application and may be implemented without activating an additional application and execute an action of an application downloaded from an application market.

Referring to a user may input Hi in handwriting on a touch screen display as shown in a screen and then select a messenger icon. Registration information about the messenger icon may include a message input action an interlocutor selection action an interlocutor addition action and a message send action and the interlocutor selection action may be defined as a registered action. If the interlocutor selection action is defined as the registered action the terminal may activate the interlocutor addition action of adding an interlocutor to whom input contents are sent as shown in a screen in response to the selection of the messenger icon after receiving the handwriting input. Here the terminal may send the text converted from the handwriting input e.g. the text Hi to an interlocutor selected when the interlocutor addition action is activated.

As described above the terminal may include a handwriting recognition function and implement various functions including activation of an application through the handwriting recognition. The user may process a function with fewer manipulations via the handwriting recognition function.

A handwriting recognition module which is configured in a software block of may be activated through settings in an upper application.

The handwriting recognition module may include a touch recognition unit a display unit a handwriting determination unit an extraction unit and a transfer unit not shown .

Referring to if a touch event is detected on a touch screen display the touch recognition unit of the handwriting recognition unit may recognize and temporarily store touch information of handwriting input and determine whether the touch event is a valid input of handwriting or a simple touch in operation .

Specifically the touch recognition unit of the handwriting recognition module may recognize the start of the touch event when a touch Touch Down on the touch screen display is recognized. As the start of the touch event is recognized the touch recognition unit traces and retains handwriting input information such as a coordinate change based on a drag Touch Move motion. Subsequently if a release of the touch Touch Up is recognized the touch recognition unit waits for a Touch Down for a valid time to input next handwriting.

Here a Touch Down may refer to a state of starting a touch event by the user touching the touch screen display.

Further a Touch Move may refer a state of the movement of the touch on the touch screen display while touching the touch screen display and a Touch Up may refer to a state of the touch being detached from the touch screen display after the Touch Down or the Touch Up. 

If the valid time for another input of handwriting expires without receiving a handwriting input the touch recognition unit may initialize a handwriting recognition process. The touch event information may be deleted if the handwriting recognition process is completed.

If the user inputs another handwriting input within the valid time that is a Touch Down on the touch screen display is detected the touch recognition unit determines whether the handwriting input is a valid handwriting input and temporarily stores the touch event information generated by the subsequent handwriting input and displays the handwriting input on the touch screen display through the display unit in operation .

The handwriting determination unit of the handwriting recognition module determines whether the handwriting input is completed and returns to the START operation show in if a touch event is absent for a long duration that is a preset period of time after completion of the handwriting. Further the handwriting determination unit determines a cancellation of the current operation if no input is received after the preset period of time elapses in operation .

If a request for use of handwriting is made from a target application or an action corresponding to a text included in registration information about the target application the extraction unit of the handwriting input module extracts the contents of the handwriting as a text from the handwriting input in operation . For example if the user activates an action or function associated with a handwriting input a notification UI requests the use of handwriting and accordingly the terminal may convert the contents of the handwriting into a text through a handwriting detection engine.

The transfer unit of the handwriting recognition module delivers the contents to the application in a current state when the extracted contents is determined to be a correct text and delivers a message that the extracted text is erroneous when the converted handwriting input does not correspond to a correct text in operation . If the extracted text includes an error in the conversion process the conversion error may be corrected by the user and re delivered to the application.

Referring to if a new message arrives through a message application installed in a terminal in operation the message application analyzes the new message and activates a user notification UI if a message arrival notification is determined to be displayed for the user in operation .

The user notification UI activated by the message application allocates a resource for the UI and starts an operation in operation .

The user notification UI analyzes pieces of information added in activating the message application in operation . The pieces of information may include information to be displayed and information on a function e.g. a button.

The user notification UI is allocated to a window other than a window used by an application being activated in the foreground. Thus a resource for displaying a screen is prepared in operation . Allocating of the user notification UI is performed to prevent a disturbance of the current foreground application by the activation and the display of the message application.

The user notification UI displays information received from the message application on the allocated screen in operation .

Here the user notification UI registers a basic processing event defined in a relevant UI such as an exit event and a selection event and a touch selection area such as a button of the user notification UI analyzed in operation .

The user notification UI determines whether a handwriting recognition function is available by the terminal and may activate the handwriting recognition module in operation if the handwriting recognition function is available.

If the handwriting recognition function is not available by the terminal in operation the user notification UI may determine whether the basic event is detected in operation select a function and conduct operation or terminate the operation in operation .

If the handwriting recognition module is activated in operation the terminal may detect a touch event a handwriting input on a screen. The touch event may be detected on a screen other than an area where the touch event is previously detected.

Then the handwriting recognition module determines whether the touch event corresponds to a valid handwriting input in operation .

If it is determined that the touch event corresponds to a valid handwriting input in operation the handwriting recognition module displays the handwriting input on the screen in operation . If it is determined that the touch event is not a valid handwriting input in operation for example the input touch event is determined to be a simple touch the handwriting recognition module may enter a stand by mode until a valid handwriting input is provided.

If the user selects a function corresponding to the detection of the basic event e.g. a reply or answer function in operation a handwriting input may be completed in operation . If the handwriting input is completed the user notification UI reports that the basic event is selected by the user and requests conversion of text data from the handwriting recognition module.

After the completion of the handwriting input the handwriting input may be converted into a text by the handwriting conversion engine in operation .

If the text converted in operation is a normal text a portion of or the entire handwriting input is successfully converted into one or more characters of the text data the text may be extracted and displayed on the screen of the touch display in operation . If the converted text is an abnormal text a portion of or entire handwriting input is not successfully converted into one or more characters the text or the corresponding handwriting input may be initialized.

A determination as to whether the displayed text is to be used may be made by user identification after the extraction in operation .

Subsequently it is determined whether normal text data exists in operation . If normal text data is absent a defined function is activated without the text data in operation .

If normal text data exists a defined function is activated in association with the text data in operation .

Further resources allocated in a process of activating the user notification UI in operation and the resource of the handwriting recognition module are returned and the user notification UI is terminated in operation .

Although a description of the detection of the basic event in operation of is provided regarding selection of a button similar operations may be performed when an icon is selected.

For example an icon driver e.g. an icon launcher may extract action information registered in registration information about a drive application of an icon through the handwriting recognition module and activate the application by an action using input information for example an input of handwriting.

Hereinafter a method of inputting text to a home screen or a menu such as an application list via a handwriting input and selecting an application icon will be described.

When a message icon is selected a message writing action may be activated and contents of handwriting may be added as message contents. When a contact information icon is selected a contact information search action may be performed using the contents of handwriting and a search result may be displayed if a corresponding search result is available. When a dial icon is selected a call may be made to a telephone number corresponding to the contents of handwriting. When a note icon is selected the contents of handwriting may be stored in a note application.

If the user provides a handwriting input on the touch screen display while talking over the phone and then selects a message button written contents may be sent to an interlocutor or stored separately. Further if the message button is selected after receiving a handwriting input the written contents may be sent to a contact designated by the user.

In operations to may be performed by the application while operations to may be performed by a software block. The operations performed by the application may be associated with a UI in which a user makes a selection for activating the application.

As the user selects an application icon in operation a request to activate a corresponding application is generated thereby requesting an application activating action in operation .

If the application activating action is requested an application driver is activated in the software block in operation .

In operation the application driver requests information from a handwriting recognition module as to whether handwriting contents of the user exist. In operation the handwriting recognition module returns or provides handwriting contents according to the request for the handwriting contents from the application driver.

The application driver provided with the handwriting contents from the handwriting recognition module determines whether handwriting contents exist and detects handwriting in operation . If handwriting contents are not exist or inappropriate for further processing in operation the application driver activates an application selected based on the request of the user without associating the handwriting contents in operation . If it is determined that handwriting contents exist in operation the application driver collects application action information in operation .

The application driver determines whether an action using contents of a text is registered in registration information about the application selected by the user in operation .

If corresponding action information does not exist in operation the application driver processes operation to activate the application selected by the user by a basic action without associating the handwriting contents.

If corresponding action information exists in operation the application driver generates an action to activate an action of the application selected by the user based on the handwriting contents and activates the application by the generated action in operation .

If an additional input of the user is required for activating the action of the application in operation the application driver may receive the additional input from the user. The additional input may be a handwriting input. In conjunction with the application being activated by the action generated in operation an application action using the handwriting contents is activated in operation .

Referring to the mobile device includes a hardware layer a platform for processing and transmitting a signal input in the hardware layer and an application program layer including various types of application programs configured to be run based on the platform .

The platform may be classified into an Android platform a Windows Mobile platform and an iOS platform according to an operating system of the mobile device and the respective platforms may have different structures in detailed configurations but serve the same basic functions.

Hereinafter a mobile operating system will be described with respect to the Android platform as an illustrative example but aspects of the present invention are not limited thereto.

The Android platform includes a Linux Kernel layer responsible for managing various types of hardware transmitting a request from an application program to hardware and transmitting a response of hardware to the application program a Library layer formed of C or C and linking hardware and a Framework layer and the Framework layer to manage various types of application programs. In addition the Android platform may include an Android Runtime layer including a Dalvik Virtual Machine for an operation in an Android execution environment and a Core Library for the Android execution environment.

The Window Mobile platform includes a Window Core layer corresponding to the Linux Kernel layer and an Interface layer linking the Core layer and an Application Program layer and supporting various kinds of languages and functions.

The iOS platform includes a Core OS layer corresponding to the Linux Kernel layer a Core Service layer similar to the Library layer and the Framework layer a Media layer providing a multimedia function and a Cocoa Touch layer for various kinds of applications.

Here each layer may be also referred to as a block and the Framework layer and corresponding layers are defined as a software block . The present invention may be implemented on the platforms of the mobile device described above. However the platforms described above are exemplary and other platform models may be applicable for the implementation.

The software block may provide an Application Programming Interface API required for developing an application such as an application framework.

The software block includes components to create an application. Specifically the software block may include an Activity Manager a Window Manager a Contents Provider a View System a Package Manager a Telephony Manager a Resource Manager a Location Manager and a Notification Manager.

The application program layer may include basic applications for example an e mail client a short message service SMS program a calendar a map and a browser.

A module implementing the methods of activating the application based on the handwriting input described with reference to to may be located in the software block . For example if a mobile device is based on the Android operating system the module implementing the methods of activating the application based on the handwriting input may be configured through the Activity Manager.

According to the Android based configuration a handwriting mode configuration may be transmitted from the Activity Manager of the soft block responsible for configuring a screen and processing an event to HW Touch Linux Kernel Android Runtime and Activity Manager sequentially.

If a touch event is transmitted to the Activity Manager the event is transmitted to a lower View or a lower View Group.

The touch event is also transmitted to the touch recognition unit of the handwriting recognition module of and a Button View of the lower View. If a Touch Down occurs in a button area and then a Touch Up occurs within the area the event is recognized as a selection of the button and thus a button action may be activated.

A handwriting input area and a button area may be distinguished from each other on the screen of the touch screen display or the entire display region may be used as the handwriting input area without separating the button area.

If the button area is separated the selection of a button may be distinguished from other types of recognition of a touch and thus an entire area other than the button area may be activated or inactivated. Thus without activating only the button area such as a reply button when a text message is received an area for receiving a handwriting input other than the button area may also be activated.

For example the user may input a handwriting input and then touch a button while talking over the phone.

The handwriting input may be configured to be received in the area other than the button area where a functional button e.g. a call button end button is disposed on the screen of the touch screen display. For example the terminal may divide the screen of the touch screen display into multiple areas to provide the user with an area for receiving a handwriting input and an area for button touch. For example an area where an icon is disposed may be the area for a button which is distinguished from another button area or the area for receiving a handwriting input. A terminal may determine a touch event detected through the area for receiving a handwriting input as a handwriting input. As such if a handwriting input is configured to be input only in the handwriting input area it may be determined that a handwriting input is completed as a touch event is made after the completion of the handwriting input in the dedicated handwriting input area. If the icon is touched the input received on the icon is not determined as a handwriting input and a function of the icon may be performed without analyzing whether the input corresponds to a handwriting input.

If the entire display area is configured to receive a handwriting input without distinguishing the handwriting input area from the button area the user may not be able to select an icon to be selected by the user after a handwriting input even though the icon is displayed on because the icon may be hidden under the transparent handwriting input area. For example the user may need to wait for a period of time to elapse until a handwriting input is completely recognized. In this case the handwriting input may not be linked to an application before completing the recognition of the handwriting input.

If the user presses a menu of an application or an application icon within a predetermined time after receiving a handwriting input on the handwriting input area the terminal may temporarily analyze and store contents of the handwriting input and link the handwriting input to the application when the application or the application icon is selected within the predetermined time. The terminal may display a pop up message asking whether to temporarily store the contents of the handwriting input or the terminal may display a list of linkable applications which are not disposed on the home screen through a pop up message or a list to the user. The handwriting input may be provided to an application selected by the user as a target application among the list of the applications displayed to the user.

Further if the entire display area is used for receiving a handwriting input without distinguishing the handwriting input area from the button area the terminal may generate a layer for displaying a menu of an application or an application icon or a layer for button input separately from a layer for receiving the handwriting input to enable a handwriting input to be input through the separate transparent layer. The transparent layer for the handwriting input may be disposed on the layer for the menu of an application the application icon or a button when the handwriting input is activated such that the entire screen can be used as the handwriting input area.

Further according to a type of a handwriting input a menu of associated applications or associated application icons may be displayed. Specifically if the user inputs numbers without a character as a handwriting input an application related to a dial e.g. a call application may be displayed. Different types of applications may be further recommended or displayed when characters are input as a handwriting input.

Referring to the terminal includes a first determination unit a storage unit a conversion unit a selection unit and a providing unit . Further the terminal may further include a reception unit and a second determination unit .

The first determination unit determines whether a touch event occurring in a touch recognition area of a touch screen display not shown is a handwriting input. If the touch recognition area is a preset area of the touch screen display the preset area may be independently allocated to a target application. The preset area may be independently allocated to the target application. Further the touch recognition area may be the entire touch recognition area of the touch screen display.

The handwriting determination unit may activate a handwriting recognition module to determine whether the touch event is a valid handwriting input or a simple touch. The handwriting recognition module may detect the touch event occurred in the preset area to determine whether the touch event is a valid handwriting input.

If a recognized touch event corresponds to a text e.g. a character a number or a defined symbol when converted by a handwriting conversion engine the touch event may be a valid handwriting input.

The storage unit stores the converted text and may temporarily store the text until the text is associated with the target application based on handwriting input settings.

The conversion unit converts the handwriting input into a text. The conversion unit may convert the handwriting input into a text using the handwriting conversion engine when the touch event is determined to be a handwriting input. The handwriting conversion engine may include a software engine which calculates a value corresponding to a coordinate acquired from the touch event occurred on the touch screen display to convert the touch event into a text.

The conversion unit may convert the handwriting input into a text using the handwriting conversion engine. The conversion may be performed when the input of handwriting is completed or the conversion may be performed during the occurrence of the touch event. The text converted by the conversion unit may be stored in the storage unit .

The selection unit selects the target application among a plurality of applications according to a setting or a selection of a user.

The reception unit may receive an additional input of handwriting in the touch recognition area of the touch screen display after the converted text is provided to the target application.

The second determination unit may determine whether the text is a valid input for the target application based on registration information of the target application.

Further the second determination unit may determine whether a function of the target application corresponding to the text exists based on information about functions of the target application included in the registration information.

Further according to aspects of the present invention one or more processors not shown may be included in the terminal to process one or more operations described above. For example the one or more processors may execute a portion of or all the operations of the determination units and the conversion unit the selection unit and the providing unit . Further a processor may determine whether the handwriting input corresponds to a message to be transferred to another user. If the handwriting input is determined to be a message to be transferred to another user e.g. contents of a reply message the image of the handwriting input may be transferred to the other user without converting the handwriting input into a symbol e.g. a text message.

A touch panel to receive a handwriting input may be provided on the terminal. The touch panel may be a touch screen display to receive a touch input including the handwriting input and to display various images. A separate touch panel may be provided on the terminal to receive the handwriting input and a touch screen display or a display may be separately provided. A touch panel may be a touch recognition device and may include or may not include a display. Further the handwriting recognition module may be activated according to an occurrence of an event and or a detection of an input. For example if the first determination unit recognizes a defined symbol e.g. an alphabet c from a touch input received on a touch panel or a touch screen display the first determination unit may activate the handwriting recognition module based on the event. A hardware key or a touch sensing button disposed on a terminal or a software button displayed on the touch screen display may be associated with the initiation of the handwriting recognition module. If one of the keys and buttons are pressed or touched by a user a handwriting recognition mode may be initiated.

As described above a handwriting input may be converted into a symbol such as a text and the converted text may be displayed on a screen. If an error in the converted text is recognized by a user the user may correct the error by inputting a correction input on the terminal. For example the user may touch the touch panel to generate the correction input on the location corresponding to the erroneously recognized symbol. Referring to if the user wishes to erase the symbol the user may generate a strikethrough touch input on the touch screen corresponding to the location of the handwriting input . If the user wishes to erase HI the user may generate a strikethrough touch input on the touch screen corresponding to the location of the converted text HI .

The user may input a handwriting input into multiple fields. For example the user may input a first handwriting input 7032001004 and a second handwriting input John . The first handwriting input and the second handwriting input may be stored as a first data field and a second data field respectively. The first handwriting input and the second handwriting input may be distinguished by changing a line when inputting the first and second handwriting inputs but aspects are not limited thereto. If the user selects an application or an icon of the application after generating the first and second handwriting inputs the two data fields may be associated with the selected application. For example if the user writes 7032001004 in the first line writes John in the second line and selects a contact application contact information of another user John may be stored in the contact application. Further if the user selects multiple applications or icons thereof after generating the first and second handwriting inputs the two data fields corresponding to the first and second handwriting inputs may be associated with the selected multiple applications. Further the first data field corresponding to the first handwriting input and the second data field corresponding to the second handwriting input may be associated with a first selected application and a second selected application respectively.

The methods according to the exemplary embodiments may be recorded in computer readable media including program instructions to implement various operations embodied by a computer. The media may also include alone or in combination with the program instructions data files data structures and the like. The media and program instructions may be those specially designed and constructed for the purposes of the present invention or they may be of the kind well known and available to those having skill in the computer software arts. Examples of computer readable media include magnetic media such as hard disks floppy disks and magnetic tape optical media such as CD ROM discs and DVD magneto optical media such as floptical discs and hardware devices that are specially configured to store and perform program instructions such as read only memory ROM random access memory RAM flash memory and the like. Examples of program instructions include both machine code such as produced by a compiler and files containing higher level code that may be executed by the computer using an interpreter. The described hardware devices may be configured to act as one or more software modules in order to perform the operations of the above described embodiments of the present invention and vice versa.

It will be apparent to those skilled in the art that various modifications and variation can be made in the present invention without departing from the spirit or scope of the invention. Thus it is intended that the present invention cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

